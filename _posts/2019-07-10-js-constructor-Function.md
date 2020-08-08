---
title: JavaScript - El constructor Function()
description: crea funciones anonimas (sin nombre) para evitar el uso de variables globales
categories: 
  - Blog
  - Javascript
comments: true
---

La declaracion de `function` no es la unica manera de definir una nueva funcion; puede definir su funcion dinamicamente usando el constructor `Function()` con el nuevo operador.

Nota: Constructor es una terminologia de Programacion Orientada a Objetos. Es posible que no se sienta comodo por primera vez, lo cual esta bien.

### Sintaxis

A continuacion se muestra la sintaxis para crear una funcion utilizando el constructor `Function()` junto con el nuevo operador.

```html
<script type = "text/javascript">
   <!--
      var variablename = new Function(Arg1, Arg2..., "Function Body");
   //-->
</script>
```

El constructor `Function()` espera cualquier numero de argumentos de cadena de caracteres. El ultimo argumento es el cuerpo de la funcion: puede contener sentencias de JavaScript arbitrarias, separadas entre si por punto y coma.

Observe que al constructor `Function()` no se le pasa ningun argumento que especifique un nombre para esta funcion que se crea. Las funciones sin nombre creadas con el constructor `Function()` se llaman funciones anonimas.

#### Ejemplo

Pruebe el siguiente ejemplo.

```html
<html>
   <head>
      <script type = "text/javascript">
         <!--
            var func = new Function("x", "y", "return x*y;");
            function secondFunction() {
               var result;
               result = func(10,20);
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
