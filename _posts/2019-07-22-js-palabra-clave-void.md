---
title: JavaScript - Palabra clave void
description: Este operador especifica una expresion para ser evaluada sin devolver un valor.
categories: Blog
comments: true
---

void es una palabra clave importante en JavaScript que se puede usar como un operador unario que aparece antes de su unico operando, que puede ser de cualquier tipo. Este operador especifica una expresion para ser evaluada sin devolver un valor.

### Sintaxis

La sintaxis de `void` puede ser cualquiera de los dos siguientes:

```html
<head>
   <script type = "text/javascript">
      <!--
         void func()
         javascript:void func()
         or:
         void(func())
         javascript:void(func())
      //-->
   </script>
</head>
```

#### Ejemplo 1

El uso mas comun de este operador es en el codigo javascript:URL del lado del cliente, donde le permite evaluar una expresion por sus efectos secundarios sin que el navegador muestre el valor de la expresión evaluada.

Aquí se evalua la expresion alerta ('¡Warning!') Pero no se vuelve a cargar en el documento actual -

```html
<html>
   <head>      
      <script type = "text/javascript">
         <!--
         //-->
      </script>   
   </head>
   
   <body>   
      <p>Click the following, This won't react at all...</p>
      <a href = "javascript:void(alert('Warning!!!'))">Click me!</a>     
   </body>
</html>
```

#### Ejemplo 2

Echa un vistazo al siguiente ejemplo. El siguiente enlace no hace nada porque la expresión "0" no tiene efecto en JavaScript. Aqui se evalua la expresión "0", pero no se vuelve a cargar en el documento actual.

```html
<html>
   <head>   
      <script type = "text/javascript">
         <!--
         //-->
      </script>      
   </head>
   
   <body>   
      <p>Click the following, This won't react at all...</p>
      <a href = "javascript:void(0)">Click me!</a>      
   </body>
</html>
```

#### Ejemplo 3

Otro uso de `void` es generar deliberadamente el valor indefinido de la siguiente manera.

```html
<html>
   <head>      
      <script type = "text/javascript">
         <!--
            function getValue() {
               var a,b,c;
               
               a = void ( b = 5, c = 7 );
               document.write('a = ' + a + ' b = ' + b +' c = ' + c );
            }
         //-->
      </script>      
   </head>
   
   <body>
      <p>Click the following to see the result:</p>
      <form>
         <input type = "button" value = "Click Me" onclick = "getValue();" />
      </form>     
   </body>
</html>
```

### Contacto

- Envia Tus comentarios al correo `henrytorrespo@yahoo.com`
