---
title: JavaScript - Manejo de Errores y Excepciones
description: Las excepciones, son imprevistos que ocurren durante la ejecucion de un programa; anormalidades que impiden o alteran el comportamiento o flujo normal de un software.  
categories: Blog
comments: true
---

{% comment%}
Bugs y manejo de errores
https://hectorip.github.io/Eloquent-JavaScript-ES-online/chapters/08_error.html
{% endcomment%}

Hay tres tipos de errores en la programacion: (a) Errores de sintaxis, (b) Errores de tiempo de ejecucion y (c) Errores logicos.

### Errores de sintaxis

Los errores de sintaxis, tambien llamados errores de analisis, ocurren en tiempo de compilacion en lenguajes de programacion tradicionales y en tiempo de interpretacion en JavaScript.

Por ejemplo, la siguiente linea causa un error de sintaxis porque le falta un parentesis de cierre.

```html
<script type = "text/javascript">
   <!--
      window.print(;
   //-->
</script>
```

Cuando se produce un error de sintaxis en JavaScript, solo el codigo que se encuentra en el hilo donde se produce el error de sintaxis se ve afectado y el resto del codigo en otros hilos se ejecuta asumiendo que nada de ellos depende del codigo que contiene el error.

### Errores de tiempo de ejecucion

Los errores de tiempo de ejecucion, tambien llamados excepciones, ocurren durante la ejecucion (despues de la compilacion / interpretacion).

Por ejemplo, la siguiente linea causa un error de tiempo de ejecucion porque aqui la sintaxis es correcta, pero en tiempo de ejecucion, esta intentando llamar a un metodo que no existe.

```html
<script type = "text/javascript">
   <!--
      window.printme();
   //-->
</script>
```

Las excepciones tambien afectan el hilo en el que ocurren, permitiendo que otros hilos de JavaScript continuen la ejecucion normal.

### Errores logicos

Los errores logicos pueden ser el tipo de error mas dificil de rastrear. Estos errores no son el resultado de un error de sintaxis o tiempo de ejecucion. En cambio, ocurren cuando comete un error en la logica que impulsa su script y no obtiene el resultado que esperaba.

No puede detectar esos errores, ya que depende de los requisitos de su programa, que tipo de logica desea poner.

### La sentencia try...catch...finally

Las ultimas versiones de JavaScript agregaron capacidades de manejo de excepciones. JavaScript implementa el constructor `try ... catch ... finally`, asi como el operador `throw` para manejar excepciones.

Puede detectar excepciones generadas por el programador y en tiempo de ejecucion, pero no puede detectar errores de sintaxis de JavaScript.

Aqui esta el bloque la sintaxis `try...catch...finally`

```html
<script type = "text/javascript">
   <!--
      try {
         // Code to run
         [break;]
      } 
      
      catch ( e ) {
         // Code to run if an exception occurs
         [break;]
      }
      
      [ finally {
         // Code that is always executed regardless of 
         // an exception occurring
      }]
   //-->
</script>
```

El bloque `try` debe ir seguido de un bloque `catch` o un bloque `finally` (o uno de ambos). Cuando ocurre una excepcion en el bloque `try`, la excepcion se coloca en `e` y se ejecuta el bloque `catch`. El bloque opcional `finLLY` se ejecuta incondicionalmente despues de `try / catch`.

#### Ejemplos

Aqui hay un ejemplo en el que estamos tratando de llamar a una funcion no existente que a su vez esta generando una excepcion. Veamos como se comporta sin `try ... catch`−

```html
<html>
   <head>      
      <script type = "text/javascript">
         <!--
            function myFunc() {
               var a = 100;
               alert("Value of variable a is : " + a );
            }
         //-->
      </script>      
   </head>
   
   <body>
      <p>Click the following to see the result:</p>
      
      <form>
         <input type = "button" value = "Click Me" onclick = "myFunc();" />
      </form>      
   </body>
</html>
```

Ahora intentemos detectar esta excepcion usando `try ... catch` y mostrar un mensaje facil de usar. Tambien puede suprimir este mensaje, si desea ocultar este error a un usuario.

```html
<html>
   <head>
      
      <script type = "text/javascript">
         <!--
            function myFunc() {
               var a = 100;
               try {
                  alert("Value of variable a is : " + a );
               } 
               catch ( e ) {
                  alert("Error: " + e.description );
               }
            }
         //-->
      </script>
      
   </head>
   <body>
      <p>Click the following to see the result:</p>
      
      <form>
         <input type = "button" value = "Click Me" onclick = "myFunc();" />
      </form>
      
   </body>
</html>
```

Puede usar el bloque `finally`  que siempre se ejecutara incondicionalmente despues del `try / catch`. Aqui hay un ejemplo.

```html
<html>
   <head>
      
      <script type = "text/javascript">
         <!--
            function myFunc() {
               var a = 100;
               
               try {
                  alert("Value of variable a is : " + a );
               }
               catch ( e ) {
                  alert("Error: " + e.description );
               }
               finally {
                  alert("Finally block will always execute!" );
               }
            }
         //-->
      </script>
      
   </head>
   <body>
      <p>Click the following to see the result:</p>
      
      <form>
         <input type = "button" value = "Click Me" onclick = "myFunc();" />
      </form>
      
   </body>
</html>
```

### La sentencia throw

Puede usar la instruccion `throw` para aumentar sus excepciones integradas o excepciones personalizadas. Mas tarde, estas excepciones se pueden capturar y puede tomar una accion adecuada.

#### Ejemplo

El siguiente ejemplo muestra como usar una instruccion `throw`.

```html
<html>
   <head>
      
      <script type = "text/javascript">
         <!--
            function myFunc() {
               var a = 100;
               var b = 0;
               
               try {
                  if ( b == 0 ) {
                     throw( "Divide by zero error." ); 
                  } else {
                     var c = a / b;
                  }
               }
               catch ( e ) {
                  alert("Error: " + e );
               }
            }
         //-->
      </script>
      
   </head>
   <body>
      <p>Click the following to see the result:</p>
      
      <form>
         <input type = "button" value = "Click Me" onclick = "myFunc();" />
      </form>
      
   </body>
</html>
```

Puede generar una excepcion en una funcion utilizando una cadena, un entero, un booleano o un objeto y luego puede capturar esa excepcion en la misma funcion que hicimos anteriormente o en otra funcion utilizando un bloque `try ... catch`.

### El metodo onerror()

El controlador de eventos `onerror` fue la primera caracteristica para facilitar el manejo de errores en JavaScript. El evento `error` se activa en el objeto ventana cada vez que se produce una excepcion en la pagina.

```html
<html>
   <head>
      
      <script type = "text/javascript">
         <!--
            window.onerror = function () {
               alert("An error occurred.");
            }
         //-->
      </script>
      
   </head>
   <body>
      <p>Click the following to see the result:</p>
      
      <form>
         <input type = "button" value = "Click Me" onclick = "myFunc();" />
      </form>
      
   </body>
</html>
```

El controlador de eventos `onerror` proporciona tres piezas de informacion para identificar la naturaleza exacta del error:

- Mensaje de error: el mismo mensaje que el navegador mostraria para el error dado

- URL: el archivo en el que se produjo el error

- Numero de linea: el numero de linea en la URL dada que causo el error

Aqui esta el ejemplo para mostrar como extraer esta informacion.

#### Ejemplo


```html
<html>
   <head>
   
      <script type = "text/javascript">
         <!--
            window.onerror = function (msg, url, line) {
               alert("Message : " + msg );
               alert("url : " + url );
               alert("Line number : " + line );
            }
         //-->
      </script>
      
   </head>
   <body>
      <p>Click the following to see the result:</p>
      
      <form>
         <input type = "button" value = "Click Me" onclick = "myFunc();" />
      </form>
      
   </body>
</html>
```

Puede mostrar la informacion de la forma que considere mejor.

Puede usar un metodo `onerror`, como se muestra a continuacion, para mostrar un mensaje de error en caso de que haya algun problema al cargar una imagen.

```html
<img src="myimage.gif" onerror="alert('An error occurred loading the image.')" />
```

Puede usar `onerror` con muchas etiquetas HTML para mostrar mensajes apropiados en caso de errores.

### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
