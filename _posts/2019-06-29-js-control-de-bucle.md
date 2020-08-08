---
title: JavaScript - Control de bucle
description: 
categories: 
  - Blog
  - Javascript
comments: true
---

JavaScript proporciona un control total para manejar bucles y  sentencias switch. Puede haber una situacion en la que necesite salir de un bucle sin llegar al fondo. Tambien puede haber una situacion en la que desee omitir parte de un bloque de codigo y comenzar la siguiente iteracion del bucle.

Para manejar todas estas situaciones, JavaScript proporciona declaraciones de ruptura y continuación. Estas declaraciones se utilizan para salir inmediatamente de cualquier bucle o para iniciar la siguiente iteracion de cualquier bucle, respectivamente.

### La sentencia `break`

La instruccion `break`, que se introdujo brevemente con la instrucción `switch`, se utiliza para salir de un bucle de manera temprana.

#### Ejemplo

El siguiente ejemplo ilustra el uso de una instruccion `break` con un bucle `while`. Observe como el bucle se rompe de forma  temprana una vez que x llega a 5 y llega a la declaracion `document.write(..)`.

```html
<html>
   <body>     
      <script type = "text/javascript">
         <!--
         var x = 1;
         document.write("Entering the loop<br /> ");
         
         while (x < 20) {
            if (x == 5) {
               break;   // breaks out of loop completely
            }
            x = x + 1;
            document.write( x + "<br />");
         }         
         document.write("Exiting the loop!<br /> ");
         //-->
      </script>
      
      <p>Set the variable to different value and then try...</p>
   </body>
</html>
```

Ya hemos visto el uso de la instruccion `break` dentro de una instruccion `switch`.

### La sentencia `continue`

La instruccion `continue` le indica al interprete que inicie inmediatamente la siguiente iteracion del bucle y que omita el bloque de codigo restante. Cuando se encuentra una declaración `continue`, el flujo del programa se mueve a la expresion de comprobacion de bucle inmediatamente y, si la condicion sigue siendo verdadera, comienza la siguiente iteracion, de lo contrario, el control sale del bucle.

#### Ejemplo

Este ejemplo ilustra el uso de una instruccion `continue` con un bucle `while`. Observe como se usa la instruccion para omitir la impresion cuando el indice que se mantiene en la variable x alcanza 5.

```html
<html>
   <body>      
      <script type = "text/javascript">
         <!--
            var x = 1;
            document.write("Entering the loop<br /> ");
         
            while (x < 10) {
               x = x + 1;
               
               if (x == 5) {
                  continue;   // skip rest of the loop body
               }
               document.write( x + "<br />");
            }         
            document.write("Exiting the loop!<br /> ");
         //-->
      </script>      
      <p>Set the variable to different value and then try...</p>
   </body>
</html>
```
### Uso de etiquetas para control de flujo

A partir de JavaScript 1.2, se puede utilizar una etiqueta con `break` y `continue` para controlar el flujo con mayor precision. Una etiqueta es simplemente un identificador seguido de dos puntos (:) que se aplica a una declaracion o un bloque de codigo. Veremos dos ejemplos para entender como usar las etiquetas con `break` y `continue`.

Nota: no se permiten saltos de línea entre la declaracion `break` o `continue` y su nombre de etiqueta. Ademas, no debe haber ninguna otra declaracion entre un nombre de etiqueta y un bucle asociado.

Pruebe los siguientes ejemplos para una mejor comprensióo de las etiquetas.

#### Ejemplos

El siguiente ejemplo muestra cómo implementar Label con una instrucción `break`.

Ejemplo 1

```html
<html>
   <body>      
      <script type = "text/javascript">
         <!--
            document.write("Entering the loop!<br /> ");
            outerloop:        // This is the label name         
            for (var i = 0; i < 5; i++) {
               document.write("Outerloop: " + i + "<br />");
               innerloop:
               for (var j = 0; j < 5; j++) {
                  if (j > 3 ) break ;           // Quit the innermost loop
                  if (i == 2) break innerloop;  // Do the same thing
                  if (i == 4) break outerloop;  // Quit the outer loop
                  document.write("Innerloop: " + j + " <br />");
               }
            }        
            document.write("Exiting the loop!<br /> ");
         //-->
      </script>      
   </body>
</html>
```

Ejemplo 2

```html
<html>
   <body>
   
      <script type = "text/javascript">
         <!--
         document.write("Entering the loop!<br /> ");
         outerloop:     // This is the label name
         
         for (var i = 0; i < 3; i++) {
            document.write("Outerloop: " + i + "<br />");
            for (var j = 0; j < 5; j++) {
               if (j == 3) {
                  continue outerloop;
               }
               document.write("Innerloop: " + j + "<br />");
            }
         }
         
         document.write("Exiting the loop!<br /> ");
         //-->
      </script>
      
   </body>
</html>
```

### Contacto

- Envienos sus comentarios al correo `henrytorrespo@yahoo.com`
