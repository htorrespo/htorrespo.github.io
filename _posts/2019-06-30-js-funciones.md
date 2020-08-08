---
title: JavaScript - Funciones
description: En terminos generales, una funcion es un subprograma 
categories: 
  - Blog
  - Javascript
comments: true
---

Una funcion es una seccion de codigo reutilizable que se puede llamar en cualquier parte de un programa. Esto elimina la necesidad de escribir el mismo codigo una y otra vez. Ayuda a los programadores a escribir codigos modulares. Las funciones permiten que un programador divida un programa grande en una serie de funciones pequeñas y manejables.

Al igual que cualquier otro lenguaje de programacion avanzado, JavaScript tambien admite todas las funciones necesarias para escribir codigo modular utilizando funciones. Debe haber visto funciones como alert () y write () antes. Usamos estas funciones una y otra vez, pero habian sido escritas en el corazon de JavaScript.

JavaScript nos permite escribir nuestras propias funciones. Esta seccion explica como escribir nuestras propias funciones en JavaScript.

### Definición de la función

Antes de usar una funcion, necesitamos definirla. La forma más comun de definir una funcion en JavaScript es mediante el uso de la palabra clave de `function`, seguida de un nombre de funcion, una lista de parametros (que pueden estar vacios) y un bloque de instrucciones rodeado de llaves.

#### Sintaxis

La sintaxis de una instruccion `function` basica es la siguiente:

```html
<script type = "text/javascript">
   <!--
      function functionname(parameter-list) {
         statements
      }
   //-->
</script>
```

#### Ejemplo

Prueba el siguiente ejemplo. Define una funcion llamada `sayHello` que no toma parámetros

```html
<script type = "text/javascript">
   <!--
      function sayHello() {
         alert("Hello there");
      }
   //-->
</script>
```

### Llamado de una funcion

Para invocar una funcion en algun lugar en el script, simplemente deber escribir el nombre de esa funcion como se muestra en el siguiente codigo.

```html
<html>
   <head>   
      <script type = "text/javascript">
         function sayHello() {
            document.write ("Hello there!");
         }
      </script>
      
   </head>
   
   <body>
      <p>Click the following button to call the function</p>      
      <form>
         <input type = "button" onclick = "sayHello()" value = "Say Hello">
      </form>      
      <p>Use different text in write method and then try...</p>
   </body>
</html>
```

### Parametros de funciones

Hasta ahora, hemos visto funciones sin parametros. Pero se pueden pasar varios parametros al llamar a una funcion. Estos parametros ​​se introducen dentro de la funcion y cualquier manipulacion se hace sobre esos parametros. Una funcion puede tomar multiples parametros separados por comas.


#### Ejemplo

Prueba el siguiente ejemplo. Hemos modificado la funcion sayHello. Ahora se necesitan dos parametros.

```html
<html>
   <head>   
      <script type = "text/javascript">
         function sayHello(name, age) {
            document.write (name + " is " + age + " years old.");
         }
      </script>      
   </head>
   
   <body>
      <p>Click the following button to call the function</p>      
      <form>
         <input type = "button" onclick = "sayHello('Zara', 7)" value = "Say Hello">
      </form>      
      <p>Use different parameters inside the function and then try...</p>
   </body>
</html>
```

### La sentencia `return`

Una funcion en JavaScript puede tener una declaracion `return` opcional. Es necesaria si desea que la funcion devolva un valor. Esta declaracion debe ser la última declaracion en una funcion.

Por ejemplo, puede pasar dos numeros en una funcion y luego puede esperar que la funcion devuelva su multiplicacion en su programa.

#### Ejemplo

Prueba el siguiente ejemplo. Define una funcion que toma dos parametros y los concatena antes de devolver la resultante en el programa.

```html
<html>
   <head>  
      <script type = "text/javascript">
         function concatenate(first, last) {
            var full;
            full = first + last;
            return full;
         }
         function secondFunction() {
            var result;
            result = concatenate('Zara', 'Ali');
            document.write (result );
         }
      </script>      
   </head>
   
   <body>
      <p>Click the following button to call the function</p>      
      <form>
         <input type = "button" onclick = "secondFunction()" value = "Call Function">
      </form>      
      <p>Use different parameters inside the function and then try...</p>  
  </body>
</html>
```

Hay mucho que aprender sobre las funciones en JavaScript, sin embargo, hemos cubierto los conceptos mas importantes en este tutorial.


### Contacto

- Envienos sus comentarios al correo `henrytorrespo@yahoo.com`
