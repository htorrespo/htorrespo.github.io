---
title: Javascript - Codigo javaScript en documento HTML
description: Internet Explorer, Firefox, chrome y Opera
categories: 
  - Blog
  - Javascript
comments: true
---

Existe flexibilidad en cuanto a introducir código JavaScript en cualquier parte de un documento HTML. Sin embargo, las formas preferidas de incluir JavaScript en un archivo HTML son las siguientes:

- Script en la sección `<head> ... </head>`.

- Guión en la sección `<body> ... </body>`.

- Guión en las secciones `<body> ... </body>` y `<head> ... </head>`.

- Haga un script en un archivo externo y luego incluya en la sección `<head> ... </head>`.

En la siguiente sección, veremos cómo podemos introducir JavaScript en un archivo HTML de maneras diferentes.

## JavaScript en la sección `<head>...</head>`

Si desea que un script ejecute algún evento, como cuando un usuario hace clic en algún lugar, escriba este script en la sección `<head>` de la siguiente manera:

```html
<html>
   <head>      
      <script type = "text/javascript">
         <!--
            function sayHello() {
               alert("Hello World")
            }
         //-->
      </script>     
   </head>
   
   <body>
      <input type = "button" onclick = "sayHello()" value = "Say Hello" />
   </body>  
</html>
```

## JavaScript en la sección `<body>...</body>`

Si necesita que una secuencia de comandos se ejecute a medida que carga la página para generar contenido, la secuencia de comandos entra en la seccion `<body>` del documento. En este caso, no tendrías ninguna función definida usando JavaScript. Echa un vistazo al siguiente código.

```html
<html>
   <head>
   </head>
   
   <body>
      <script type = "text/javascript">
         <!--
            document.write("Hello World")
         //-->
      </script>
      
      <p>This is web page body </p>
   </body>
</html>
```

## JavaScript en las seciones `<body>` y `<head>`

Puede escribir el código JavaScript en la sección `<body>` y `<head>` de la siguiente manera:

```html
<html>
   <head>
      <script type = "text/javascript">
         <!--
            function sayHello() {
               alert("Hello World")
            }
         //-->
      </script>
   </head>
   
   <body>
      <script type = "text/javascript">
         <!--
            document.write("Hello World")
         //-->
      </script>
      
      <input type = "button" onclick = "sayHello()" value = "Say Hello" />
   </body>
</html>
```
## JavaScript en archivo externo

A medida que comience a trabajar más extensamente con JavaScript, es probable que encuentre casos en los que está reutilizando código idéntico en varias páginas de un sitio.

No está restringido a mantener un código idéntico en varios archivos HTML. La etiqueta de secuencia de comandos proporciona un mecanismo que le permite almacenar JavaScript en un archivo externo y luego incluirlo en sus archivos HTML.

Este es un ejemplo para mostrar cómo puede incluir un archivo JavaScript externo en su código HTML usando la etiqueta de script y su atributo src.

```html
<html>
   <head>
      <script type = "text/javascript" src = "filename.js" ></script>
   </head>
   
   <body>
      .......
   </body>
</html>
```

Para usar JavaScript desde un archivo externo, debe escribir todo el código fuente en un archivo de texto simple con la extensión ".js" y luego incluir ese archivo como se muestra arriba.

Por ejemplo, puede mantener el siguiente contenido en el archivo `filename.js` y luego puede usar la función `sayHello` en su archivo HTML después de incluir el archivo `filename.js`.

```javascript
function sayHello() {
   alert("Hello World")
}
```

### Contacto

- Envienos sus comentarios al correo `henrytorrespo@yahoo.com`
