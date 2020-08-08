---
title: JavaScript - Sentencia while
description: Crea un bucle que ejecuta una sentencia especificada mientras cierta condicion se evalúe como verdadera.
categories: 
  - Blog
  - Javascript
comments: true
---

Mientras escribe un programa, puede encontrarse con una situacion en la que necesita realizar una accion una y otra vez. En tales situaciones, necesitaria escribir instrucciones de bucle para reducir el numero de lineas.

JavaScript soporta todos los bucles necesarios para aliviar la presion de la programacion.

### Sentencia `while`

El bucle más basico en JavaScript es el bucle `while`. El proposito de un bucle `while` es ejecutar una instruccion o un bloque de codigo repetidamente siempre que una expresion sea verdadera. Una vez que la expresion se vuelve falsa, el bucle termina.

#### Sintaxis

La sintaxis de una instruccion `while` basica es la siguiente:

```javascript
while (expression) {
   Statement(s) to be executed if expression is true
}
```


#### Ejemplo

Pruebe el siguiente ejemplo para comprender como funciona la instruccion `while`.

```html
<html>
   <body>
      
      <script type = "text/javascript">
         <!--
            var count = 0;
            document.write("Starting Loop ");
         
            while (count < 10) {
               document.write("Current Count : " + count + "<br />");
               count++;
            }
         
            document.write("Loop stopped!");
         //-->
      </script>
      
      <p>Set the variable to different value and then try...</p>
   </body>
</html>
```

### Sentencia `do ... while`

El bucle `do ... while` es similar al bucle `while`, excepto que la verificacion de la condicion ocurre al final del bucle. Esto significa que el bucle siempre se ejecutara al menos una vez, incluso si la condicion es falsa.

#### Syntax

La sintaxis para el el bucle `do ... while` es la siguiente.

```javascript
do {
   Statement(s) to be executed;
} while (expression);
```

Nota: No olvides el punto y coma usado al final del ciclo `do ... while`

#### Ejemplo

Pruebe el siguiente ejemplo para aprender a implementar un bucle `do ... while` en JavaScript.

```html
<html>
   <body>   
      <script type = "text/javascript">
         <!--
            var count = 0;
            
            document.write("Starting Loop" + "<br />");
            do {
               document.write("Current Count : " + count + "<br />");
               count++;
            }
            
            while (count < 5);
            document.write ("Loop stopped!");
         //-->
      </script>      
      <p>Set the variable to different value and then try...</p>
   </body>
</html>
```

### Contacto

- Envienos sus comentarios al correo `henrytorrespo@yahoo.com`
