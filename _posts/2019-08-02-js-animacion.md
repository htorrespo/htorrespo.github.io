---
title: JavaScript - Animacion
description: Existen dos metodos principales para crear animaciones en la web, CSS y JavaScript. Puede usar JavaScript para crear una animacion compleja. 
categories: Blog
comments: true
---

Puede usar JavaScript para crear una animacion compleja que tenga, entre otros, los siguientes elementos:

- Fuegos artificiales

- Efecto de desvanecimiento

- Roll-in o Roll-out

- Pagina de entrada o salida de pagina

- Movimientos de objetos

Este tutorial proporciona una comprension basica de como usar JavaScript para crear una animacion.

JavaScript se puede usar para mover varios elementos DOM (`<img/>`, `<div>` o cualquier otro elemento HTML) alrededor de la pagina de acuerdo con algun tipo de patron determinado por una ecuacion o funcion logica.

JavaScript proporciona las siguientes funciones para ser utilizadas con frecuencia en programas de animacion.

- `setTimeout(function, duration)`: esta funcion llama a `function` despues de `duration` en milisegundos a partir de ahora.

- `setInterval(funcion, duracion)`: esta funcion llama a `function` despues de cada `duration` en milisegundos.

- `clearTimeout(setTimeout_variable)`: esta funcion llama a cualquier temporizador establecido por las funciones `setTimeout()`.

JavaScript tambien puede establecer una serie de atributos de un objeto DOM, incluida su posicion en la pantalla. Puede establecer el atributo superior e izquierdo de un objeto para colocarlo en cualquier lugar de la pantalla. Aqui esta su sintaxis.

```html
// Set distance from left edge of the screen.
object.style.left = distance in pixels or points; 

or

// Set distance from top edge of the screen.
object.style.top = distance in pixels or points;
```

### Animacion manual

Implementemos una animacion simple usando propiedades del objeto DOM y  funciones JavaScript de la siguiente manera. La siguiente lista contiene diferentes metodos DOM.

- Estamos utilizando la funcion de JavaScript `getElementById()` para obtener un objeto DOM y luego asignarlo a una variable global `imgObj`.

- Hemos definido una funcion de inicializacion `init()` para inicializar `imgObj` donde hemos establecido sus atributos `position` y `left`.

- Estamos llamando a la funcion de inicializacion en el momento de la  carga de la ventana.

- Finalmente, estamos llamando a la funcion `moveRight()` para aumentar la distancia izquierda en 10 pixeles. Tambien puede establecerlo en un valor negativo para moverlo hacia el lado izquierdo.
	
#### Ejemplo

Prueba el siguiente ejemplo.

````html
<html>   
   <head>
      <title>JavaScript Animation</title>      
      <script type = "text/javascript">
         <!--
            var imgObj = null;
            
            function init() {
               imgObj = document.getElementById('myImage');
               imgObj.style.position= 'relative'; 
               imgObj.style.left = '0px'; 
            }
            function moveRight() {
               imgObj.style.left = parseInt(imgObj.style.left) + 10 + 'px';
            }
            
            window.onload = init;
         //-->
      </script>
   </head>
   
   <body>   
      <form>
         <img id = "myImage" src = "/images/html.gif" />
         <p>Click button below to move the image to right</p>
         <input type = "button" value = "Click Me" onclick = "moveRight();" />
      </form>      
   </body>
</html>
```

### Animacion automatizada

En el ejemplo anterior, vimos como una imagen se mueve hacia la derecha con cada clic. Podemos automatizar este proceso utilizando la funcion de JavaScript `setTimeout()` de la siguiente manera:

Aqui hemos agregado mas metodos. Asi que veamos que hay de nuevo aqui:

- La funcion `moveRight()` esta llamando a la funcion `setTimeout()` para establecer la posicion de `imgObj`.

- Hemos agregado una nueva funcion `stop()` para borrar el temporizador establecido por la funcion `setTimeout()` y para llevar el objeto en su posicion inicial.

#### Ejemplo

Pruebe el siguiente codigo de ejemplo.

```html
<html>   
   <head>
      <title>JavaScript Animation</title>      
      <script type = "text/javascript">
         <!--
            var imgObj = null;
            var animate ;
            
            function init() {
               imgObj = document.getElementById('myImage');
               imgObj.style.position= 'relative'; 
               imgObj.style.left = '0px'; 
            }
            function moveRight() {
               imgObj.style.left = parseInt(imgObj.style.left) + 10 + 'px';
               animate = setTimeout(moveRight,20);    // call moveRight in 20msec
            }
            function stop() {
               clearTimeout(animate);
               imgObj.style.left = '0px'; 
            }
            
            window.onload = init;
         //-->
      </script>
   </head>
   
   <body>   
      <form>
         <img id = "myImage" src = "/images/html.gif" />
         <p>Click the buttons below to handle animation</p>
         <input type = "button" value = "Start" onclick = "moveRight();" />
         <input type = "button" value = "Stop" onclick = "stop();" />
      </form>      
   </body>
</html>
```

### Rollover con un evento de mouse

Aqui hay un ejemplo simple que muestra la renovacion de imagen con un evento de mouse.

Veamos que estamos usando en el siguiente ejemplo:

- En el momento de cargar esta pagina, la instruccion `if` verifica la existencia del objeto `image`. Si el objeto `image` no esta disponible, este bloque no se ejecutara.

- El constructor `Image()` crea y precarga un nuevo objeto `image` llamado `image1`.

- A la propiedad src se le asigna el nombre del archivo imagen externo llamado `/images/html.gif`.

- Del mismo modo, hemos creado el objeto `image2` y asignado `/images/http.gif`.

- El `#` (marca hash) deshabilita el enlace para que el navegador no intente ir a una URL cuando se hace clic. Este enlace es una imagen.

- El controlador de eventos `onMouseOver` se activa cuando el mouse del usuario se mueve hacia el enlace, y el controlador de eventos `onMouseOut` se activa cuando el mouse del usuario se aleja del enlace (`image`).

- Cuando el mouse se mueve sobre `image`, la imagen HTTP cambia de la primera imagen a la segunda. Cuando el mouse se aleja de la imagen, se muestra la imagen original.

- Cuando el mouse se aleja del enlace, la imagen inicial `html.gif` volvera a aparecer en la pantalla.

```html
<html>
   
   <head>
      <title>Rollover with a Mouse Events</title>
      
      <script type = "text/javascript">
         <!--
            if(document.images) {
               var image1 = new Image();     // Preload an image
               image1.src = "/images/html.gif";
               var image2 = new Image();     // Preload second image
               image2.src = "/images/http.gif";
            }
         //-->
      </script>
   </head>
   
   <body>
      <p>Move your mouse over the image to see the result</p>
      
      <a href = "#" onMouseOver = "document.myImage.src = image2.src;"
         onMouseOut = "document.myImage.src = image1.src;">
         <img name = "myImage" src = "/images/html.gif" />
      </a>
   </body>
</html>
```

### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
