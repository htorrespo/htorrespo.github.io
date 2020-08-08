---
title: Uso de sass en proyectos Jekyll
description: Jekyll y Sass
categories: 
  - Blog
  - HTML
  - Jekyll
comments: true
---

Una de las particularidades de Jekyll es que permite al diseñador, realmente diseñar. Jekyll no impone ningún tipo de estructura o restriccion, ni clases, convenciones de diseño o codificacion predeterminadas. Eres libre de estructurar y diseñar tu contenido como mejor te parezca. Así es que, la planeacion y construccion de estilos dependen totalmente de ti. Sin embargo, hay algunas cosas que debes tener en cuenta al escribir CSS para un sitio Jekyll.

## Ubicacion

Normalmente me gusta mantener los estilos en un directorio titulado _css. Esta convención no funciona para Jekyll, ya que un subrayado al principio de un directorio le indica a Jekyll que procese el contenido del directorio y no lo incluya en la estructura final del directorio. Como tal, para asegurarse de que su CSS se copie al sitio final, asegúrese de nombrarlo css o un nombre similar que no comience con un guión bajo

## Linking

Basicamente, hay dos formas de vincular a recursos externos como CSS dentro de las páginas y plantillas de Jekyll. Una sería usar el sitio `baseURL` para prefijar tus archivos CSS:

```html
<link rel="stylesheet" href="{{ site.baseurl }}/css/main.css">
```

Si tu sitio siempre se publica desde la carpeta raíz, puede eliminar el objeto `site.url` y simplemente usar un enlace relativo del sitio:

```html
<link rel="stylesheet" href="/css/main.css">
```

Es importante tener en cuenta que los enlaces relativos para assets como CSS pueden ser difíciles cuando se alojan sitios en Github Pages. Esencialmente, hay dos formas de alojar páginas en Github Pages, como páginas `user/organization` o páginas `project`.

Las páginas de usuarios y organizaciones viven en un repositorio de GitHub dedicado solo a los archivos de las páginas de GitHub y se almacenan en la rama `master`. Este repositorio debe tener el nombre de la cuenta, que será `username.github.io`.

Las páginas del proyecto se almacenan en el mismo repositorio que el proyecto, excepto que el contenido del sitio web se almacena en una rama `gh-pages`. La rama maestra puede contener el proyecto en sí, o incluso estar vacía.

Si el sitio se sirve a través de una página proyecto, su `baseURL` cambia a medida que el sitio se sirve a través de una sub-ruta de su dominio de usuario en `username.github.io/project`. Esto significa que en estos casos, deberá configurar su baseURL a `/project-name`. Tenga en cuenta hay una barra diagonal inicial y ninguna barra diagonal final. Esto también puede ocasionar problemas al probar los archivos localmente, así que asegúrese de leer la documentación de Jekyll sobre el hospedaje con Github Pages para obtener una cuenta completa.

## Jekyll y SASS

Jekyll viene con soporte incorporado para SASS, por lo que no es necesario instalar o modificar su configuración para que funcione. Sin embargo, hay una o dos cosas que debe tener en cuenta al trabajar con SASS en Jekyll.

Primero, para garantizar que Jekyll procese los archivos SASS, debe introducir una cadena de caracteres `front matter` al principio en la parte superior de la página. Puedes incluir un comentario si lo deseas, pero en realidad no importa. Así que incluye esto en la parte superior de cada archivo SASS:

```html
---
# Front matter added to ensure Jekyll processes file.
---

// write styles after front matter
```

Si observa la estructura de directorios predeterminada de Jekyll, sin duda verá el directorio `_sass`, lo que puede llevar a cierta confusión sobre dónde colocar los archivos SASS. Jekyll copia sobre cualquier archivo SASS procesado en la misma ubicación en la que se procesó. Por lo tanto, si tiene el archivo `css/styles.scss`, se procesará y colocará en `css/styles.css` en el sitio generado. El directorio `_sass` es para archivos de importación SASS. Si pone los archivos `.scss` parciales que está importando y usa `@import` para ensamblarlos en su hoja de estilo principal, Jekyll los procesará y los reunirá en tiempo de ejecución.

Así que si haces algo como esto en tu archivo `.scss` principal:

```html
---
# Front matter added to ensure Jekyll processes file.
---

// Imports
@import "type";
@import "layout";
@import "components";

//styles
```

Ponga los archivos `type.scss`, `layout.scss` y `components.scss` en el directorio `_sass` y Jekyll hará el resto.

Además, deberá asegurarse de que `sass_dir` esté configurado en el directorio base que contiene archivos Sass de otros frameworks como Bootstrap, Maximize u otros:

```html
sass:
    sass_dir: _sass
```

El convertidor Sass predeterminará la opción de configuración `sass_dir` a `_sass`.

También puede especificar el estilo de salida con la opción de estilo en su archivo `_config.yml`:

```html
sass:
    sass_dir: _sass
    style: compressed
```

### Contacto

- Envienos sus comentarios al correo `henrytorrespo@yahoo.com`
