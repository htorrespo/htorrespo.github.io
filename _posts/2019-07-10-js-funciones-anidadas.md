---
title: JavaScript - Funciones Anidadas
description: Las funciones anidadas solo pueden ser llamadas desde el interior de la funcion que las contiene.
categories: 
  - Blog
  - Javascript
comments: true
---

Antes de JavaScript 1.2, la definicion de funcion solo estaba permitida en el ambito global, pero JavaScript 1.2 permite que las definiciones de funcion se aniden tambien dentro de otras funciones. Aun hay restriccion en cuanto a que la definicion de funciones no pueden aparecer dentro de bucles o condicionales. Estas restricciones en la definicion de las funciones se aplican solo a declaraciones de funciones con la sentencia `function`.

Como veremos mas adelante, las funciones literales (otra caracteristica introducida en JavaScript 1.2) pueden aparecer dentro de cualquier expresion de JavaScript, lo que significa que pueden aparecer dentro de `if` y otras declaraciones.

#### Ejemplo

Pruebe el siguiente ejemplo para aprender a implementar funciones anidadas.

```html
<html>
   <head>
      <script type = "text/javascript">
         <!--
            function hypotenuse(a, b) {
               function square(x) { return x*x; }
               return Math.sqrt(square(a) + square(b));
            }
            function secondFunction() {
               var result;
               result = hypotenuse(1,2);
               document.write ( result );
            }
         //-->
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

### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
