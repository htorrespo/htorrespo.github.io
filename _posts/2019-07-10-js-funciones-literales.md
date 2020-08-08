---
title: JavaScript - Funciones Literales
description: una funcion literal es una expresion que produce una funcion que no se ha definido en otro lugar
categories: 
  - Blog
  - Javascript
comments: true
---

JavaScript 1.2 introduce el concepto funciones literales, que es otra forma de definir funciones. Una funcion literal es una expresion que define una funcion sin nombre.

### Sintaxis

La sintaxis de una funcion literal es muy parecida a una instruccion de `function`, excepto que se usa como una expresion en lugar de una declaracion y no se requiere ningun nombre de funcion.

```html
<script type = "text/javascript">
   <!--
      var variablename = function(Argument List) {
         Function Body 
      };
   //-->
</script>
```

Sintacticamente, puede especificar un nombre de funcion mientras crea una funcion literal de la siguiente manera.

```html
<script type = "text/javascript">
   <!--
      var variablename = function FunctionName(Argument List) {
         Function Body
      };
   //-->
</script>
```

Pero este nombre no tiene ningun significado, asi es que no vale la pena utilizarlo.

#### Ejemplo

Prueba el siguiente ejemplo. Muestra el uso de funciones literales.

```html
<html>
   <head>
      <script type = "text/javascript">
         <!--
            var func = function(x,y) { 
               return x*y 
            };
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
