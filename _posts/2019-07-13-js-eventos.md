---
title: JavaScript - Eventos
description: Los eventos hacen posible que los usuarios transmitan informacion a los programas. 
categories: Blog
comments: true
---

### Que es un evento?

La interaccion de JavaScript con HTML se maneja a traves de eventos que ocurren cuando el usuario o el navegador manipulan una pagina.

Cuando la pagina se carga, se llama un evento. Cuando el usuario hace clic en un boton, ese clic tambien es un evento. Otros ejemplos incluyen eventos como presionar cualquier tecla, cerrar una ventana, cambiar el tamaño de una ventana, etc.

Los desarrolladores pueden usar estos eventos para ejecutar respuestas codificadas en JavaScript, lo que hace que los botones cierren las ventanas, los mensajes se muestren a los usuarios, los datos se validen y practicamente cualquier otro tipo de respuesta imaginable.

Los eventos forman parte del Nivel 3 del Modelo de Objetos de Documento (DOM) y cada elemento HTML contiene un conjunto de eventos que pueden activar el codigo JavaScript.

### Evento `onclick`

Este es el tipo de evento utilizado con mas frecuencia que ocurre cuando un usuario hace clic en el boton izquierdo de su mouse. Puede poner su validacion, advertencia, etc., contra este tipo de evento.

#### Ejemplo

Pruebe con el siguiente ejemplo

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
      <p>Click the following button and see result</p>      
      <form>
         <input type = "button" onclick = "sayHello()" value = "Say Hello" />
      </form>      
   </body>
</html>
```

### Evento `onsubmit`

`onsubmit` es un evento que ocurre cuando intenta enviar un formulario. Puede poner la validacion de formulario contra este tipo de evento.

#### Ejemplo

El siguiente ejemplo muestra como usar `onsubmit`. Aqui estamos llamando a una funcion `validate()` antes de enviar un formulario de datos al servidor web. Si la funcion `validate()` devuelve `true`, el formulario se enviara, de lo contrario no enviara los datos.

Prueba el siguiente ejemplo.

````html
<html>
   <head>   
      <script type = "text/javascript">
         <!--
            function validation() {
               all validation goes here
               .........
               return either true or false
            }
         //-->
      </script>      
   </head>
   
   <body>   
      <form method = "POST" action = "t.cgi" onsubmit = "return validate()">
         .......
         <input type = "submit" value = "Submit" />
      </form>      
   </body>
</html>
```

### `onmouseover` y `onmouseout`

Estos dos tipos de eventos te ayudaran a crear efectos agradables con imagenes o incluso con texto. El evento `onmouseover` se activa cuando coloca el mouse sobre cualquier elemento y el activador `onmouseout` cuando mueve el mouse desde ese elemento. Prueba el siguiente ejemplo.

```html
<html>
   <head>   
      <script type = "text/javascript">
         <!--
            function over() {
               document.write ("Mouse Over");
            }            
            function out() {
               document.write ("Mouse Out");
            }            
         //-->
      </script>      
   </head>
   
   <body>
      <p>Bring your mouse inside the division to see the result:</p>      
      <div onmouseover = "over()" onmouseout = "out()">
         <h2> This is inside the division </h2>
      </div>         
   </body>
</html>
```

### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
