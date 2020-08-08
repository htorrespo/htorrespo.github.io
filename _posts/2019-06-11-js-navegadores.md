---
title: Javascript - Navegadores
description: Internet Explorer, Firefox, chrome y Opera
categories: 
  - Blog
  - Javascript
comments: true
---

Todos los navegadores modernos tienen soporte para JavaScript. Con frecuencia, es posible que necesite habilitar o deshabilitarlo manualmente. Este capítulo explica el procedimiento para habilitar y deshabilitar el soporte de JavaScript en navegadores: Internet Explorer, Firefox, chrome y Opera.

## JavaScript en Internet Explorer

Aquí algunos pasos para activar o desactivar JavaScript en Internet Explorer:

- Siga Herramientas -> Opciones de Internet en el menú.

- Seleccione la pestaña Seguridad del cuadro de diálogo.

- Haga clic en el botón Nivel personalizado.

- Desplácese hacia abajo hasta que encuentre la opción de secuencias de comandos.

- Seleccione Habilitar el botón de opción en Active scripting.

- Finalmente haga clic en OK y salga

Para deshabilitar la compatibilidad con JavaScript en Internet Explorer, debe seleccionar Deshabilitar el botón de radio en Active scripting.

## JavaScript en Firefox

Estos son los pasos para activar o desactivar JavaScript en Firefox:

- Abra una nueva pestaña -> escriba `about: config` en la barra de direcciones.

- Luego encontrarás el diálogo de advertencia. Seleccione `¡Tendré cuidado, lo prometo!`

- Luego encontrará la lista de `opciones de configuración` en el navegador.

- En la barra de búsqueda, escriba `javascript.enabled`.

- Allí encontrará la opción para habilitar o deshabilitar javascript haciendo clic con el botón derecho en el valor de esa opción -> `seleccionar alternar`.

Si `javascript.enabled` es verdadero; se convierte en falso al hacer clic en `alternar`. Si javascript está deshabilitado; se habilita al hacer clic en `alternar`.

## JavaScript en Chrome

Estos son los pasos para activar o desactivar JavaScript en Chrome:

- Haga clic en el menú de Chrome en la esquina superior derecha de su navegador.

- Seleccione Configuraciones.

- Haga clic en Mostrar configuración avanzada al final de la página.

- En la sección Privacidad, haga clic en el botón Configuración de contenido.

- En la sección "Javascript", seleccione "No permitir que ningún sitio ejecute JavaScript" o "Permitir que todos los sitios ejecuten JavaScript (recomendado)".

## JavaScript en Opera

Estos son los pasos para activar o desactivar JavaScript en Opera:

- Siga Herramientas -> Preferencias en el menú.

- Seleccione la opción Avanzada en el cuadro de diálogo.

- Seleccione el contenido de los elementos enumerados.

- Seleccione la casilla de verificación Habilitar JavaScript.

- Finalmente haga clic en Aceptar y salga.

Para deshabilitar el soporte de JavaScript en su Opera, no debe seleccionar la casilla de verificación Habilitar JavaScript.


## Advertencia para navegadores sin JavaScript

Si tiene que hacer algo importante usando JavaScript, entonces puede mostrar un mensaje de advertencia al usuario usando etiquetas `<noscript>`.

Puede agregar un bloque de noscript inmediatamente después del bloque de script de la siguiente manera:

```html
<html>
   <body>
      <script language = "javascript" type = "text/javascript">
         <!--
            document.write("Hello World!")
         //-->
      </script>
      
      <noscript>
         Sorry...JavaScript is needed to go ahead.
      </noscript>      
   </body>
</html>
```

Ahora, si el navegador del usuario no admite JavaScript o JavaScript no está habilitado, el mensaje de `</noscript>` se mostrará en la pantalla.


### Contacto

- Envienos sus comentarios al correo `henrytorrespo@yahoo.com`
