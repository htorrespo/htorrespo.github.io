---
title: Javascript - Sentencias if..else
description: Al escribir un programa, puede haber una situación en la que necesite adoptar uno de un conjunto determinado de rutas. 
categories: Blog
comments: true
---

Al escribir un programa, puede haber una situación en la que necesite adoptar uno de un conjunto determinado de rutas. En tales casos, necesita usar sentencias condicionales que le permitan a su programa tomar decisiones correctas y realizar acciones correctas.

JavaScript admite sentencias condicionales que se utilizan para realizar diferentes acciones basadas en diferentes condiciones. Aquí explicaremos la sentencia `if..else`.

## Sentencia `if--else`

JavaScript admite las siguientes formas de Sentencia `if..else`:

- Sentencia `if`

- Sentencia `if .. else`

- Sentencia `if .. else if`

### Sentencia `if`

La sentencia `if` es la sentencia de control fundamental que permite a JavaScript tomar decisiones y ejecutar sentencias condicionalmente.

#### Sintaxis

La sintaxis de una instrucción `if` básica es la siguiente:

```javascript
if (expression) {
   Statement(s) to be executed if expression is true
}
```

Aquí se evalúa una expresión JavaScript. Si el valor resultante es verdadero, se ejecutan las instrucciones dadas. Si la expresión es falsa, entonces no se ejecutará ninguna instrucción. La mayoría de las veces, utilizará operadores de comparación al tomar decisiones.

#### Ejemplo

Pruebe el siguiente ejemplo para comprender cómo funciona la instrucción `if`.

```html
<html>
   <body>     
      <script type = "text/javascript">
         <!--
            var age = 20;
         
            if( age > 18 ) {
               document.write("<b>Qualifies for driving</b>");
            }
         //-->
      </script>      
      <p>Set the variable to different value and then try...</p>
   </body>
</html>
```

### Sentencia `if .. else`

La Sentencia `if ... else` es la siguiente forma de declaración de control que permite que JavaScript ejecute declaraciones de una manera más controlada.

#### Sintaxis

```javascript
if (expression) {
   Statement(s) to be executed if expression is true
} else {
   Statement(s) to be executed if expression is false
}
```

Aquí se evalúa la expresión de JavaScript. Si el valor resultante es verdadero, se ejecutan las instrucciones dadas en el bloque `if`. Si la expresión es falsa, entonces se ejecutan la (s) declaración (es) en el bloque `else`.

#### Ejemplo

Pruebe el siguiente código para aprender a implementar una sentencia `if-else` en JavaScript

```html
<html>
   <body>   
      <script type = "text/javascript">
         <!--
            var age = 15;
         
            if( age > 18 ) {
               document.write("<b>Qualifies for driving</b>");
            } else {
               document.write("<b>Does not qualify for driving</b>");
            }
         //-->
      </script>     
      <p>Set the variable to different value and then try...</p>
   </body>
</html>
```

### Sentencia `if ... else if ..`

La declaración `if ... else if ...` es una forma avanzada de `if ... else` que permite a JavaScript tomar una decisión correcta en varias condiciones.

#### Sintaxis

La sintaxis de una sentencia `if-else-if` es la siguiente:

```javascript
if (expression 1) {
   Statement(s) to be executed if expression 1 is true
} else if (expression 2) {
   Statement(s) to be executed if expression 2 is true
} else if (expression 3) {
   Statement(s) to be executed if expression 3 is true
} else {
   Statement(s) to be executed if no expression is true
}
```

No hay nada especial en este código. Es solo una serie de sentencias `if`, donde cada una de ellas forma parte de la cláusula else de la sentencia anterior. Las sentencias se ejecutan en función de la condición verdadera, si ninguna de las condiciones es verdadera, se ejecuta el bloque else.

#### Ejemplo

Pruebe el siguiente código para aprender a implementar una declaración `if-else-if` en JavaScript.

```html
<html>
   <body>   
      <script type = "text/javascript">
         <!--
            var book = "maths";
            if( book == "history" ) {
               document.write("<b>History Book</b>");
            } else if( book == "maths" ) {
               document.write("<b>Maths Book</b>");
            } else if( book == "economics" ) {
               document.write("<b>Economics Book</b>");
            } else {
               document.write("<b>Unknown Book</b>");
            }
         //-->
      </script>      
      <p>Set the variable to different value and then try...</p>
   </body>
<html>
```

### Contacto

- Envienos sus comentarios al correo `henrytorrespo@yahoo.com`
