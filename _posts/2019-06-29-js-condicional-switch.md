---
title: JavaScript - Sentencia switch
description: La sentencia switch evalua una expresion, comparando el valor de esa expresion con una instancia case, y ejecuta sentencias asociadas a ese case, así como las sentencias en los case que siguen. 
categories: Blog
comments: true
---

Puede usar varias instrucciones `if ... else ... if`, para realizar bifurcaciones multiples. Sin embargo, esta no es siempre la mejor solucion, especialmente cuando todas las bifurcaciones dependen del valor de una sola variable.

A partir de JavaScript 1.2, puede usar una sola declaracion que maneje esta situacion, y lo hace con mayor eficiencia en lugar de las ssentencias `if ... else ... if`

### Sentencia `Switch Case`

El objetivo de la instruccion `switch` es dar una **expresion** para *evaluar* y diferentes instrucciones para *ejecutar* en funcion del valor de la **expresion**. El intérprete compara cada caso con el valor de la **expresion** hasta que encuentra una coincidencia. Si nada coincide, se utilizara una condicion por defecto.

#### Sintaxis

La sintaxis de una instruccion `switch` basica es la siguiente:

```javascript
switch (expression) {
   case condition 1: statement(s)
   break;
   
   case condition 2: statement(s)
   break;
   ...
   
   case condition n: statement(s)
   break;
   
   default: statement(s)
}
```

Las declaraciones de ruptura (`break`) indican el final de un `case` particular. Si se omitieran, el interprete continuaria ejecutando cada sentencia en los siguientes `case`.

Vamos a explicar la declaracion de ruptura `break` posteriormente.

#### Ejemplo

Pruebe el siguiente ejemplo para comprender como funciona la instruccion `switch`.

```html
<html>
   <body>   
      <script type = "text/javascript">
         <!--
            var grade = 'A';
            document.write("Entering switch block<br />");
            switch (grade) {
               case 'A': document.write("Good job<br />");
               break;
            
               case 'B': document.write("Pretty good<br />");
               break;
            
               case 'C': document.write("Passed<br />");
               break;
            
               case 'D': document.write("Not so good<br />");
               break;
            
               case 'F': document.write("Failed<br />");
               break;
            
               default:  document.write("Unknown grade<br />")
            }
            document.write("Exiting switch block");
         //-->
      </script>      
      <p>Set the variable to different value and then try...</p>
   </body>
</html>
```

Las declaraciones de ruptura juegan un papel importante en las declaraciones de cambio de `case`. Pruebe el siguiente codigo que usa la instruccion `switch-case` sin ninguna instruccion `break`.

```html
<html>
   <body>      
      <script type = "text/javascript">
         <!--
            var grade = 'A';
            document.write("Entering switch block<br />");
            switch (grade) {
               case 'A': document.write("Good job<br />");
               case 'B': document.write("Pretty good<br />");
               case 'C': document.write("Passed<br />");
               case 'D': document.write("Not so good<br />");
               case 'F': document.write("Failed<br />");
               default: document.write("Unknown grade<br />")
            }
            document.write("Exiting switch block");
         //-->
      </script>      
      <p>Set the variable to different value and then try...</p>
   </body>
</html>
```

### Contacto

- Envienos sus comentarios al correo `henrytorrespo@yahoo.com`
