---
title: Javascript - Tipos de Operadores
description: Operadores, artimeticos, comparacion, logicos, binarios, asignacion,  
categories: 
  - Blog
  - Javascript
comments: true
---

## ¿Qué es un operador?

Tomemos una expresión simple. 4 + 5 es igual a 9. Aquí 4 y 5 se llaman operandos y `+` se llama operador. JavaScript soporta los siguientes tipos de operadores.

- Operadores aritméticos

- Operadores de comparación

- Operadores lógicos (o relacionales)

- Operadores de Asignación

- Operadores condicionales (o ternarios)

## Operadores aritméticos

JavaScript es compatible con los siguientes operadores aritméticos:

Supongamos que la variable A contiene 10 y la variable B tiene 20, entonces

|No. | Operador & Descripcion |
|----|------------------------|
|1 	| `+` (Adicion)          |
|    | agrega dos operandos   |
|    | Ej: `A + B` devuelve `30` |
|2 	| `-` (Substraccion)        |
|    | Resta el segundo operando del primero |
|    | Ej: `A - B` devuelve `-10`            |
|3 	| `*` (Multiplicacion)                  |
|    | Multiplica ambos operandos            |
|    | Ej: `A * B` devuelve `200`            |
|4 	| `/` (Division)                        |
|    | Divide el numerador sobre el denominador |
|    | Ej: `B / A` devuelve `2`                 |
|5 	| `%` (Modulo)                             |
|    | Devuelve el remanente de la division entera |
|    | Ej: `B % A`  devuelve `0`                   |
|6 	| `++` (Incremento)                           |
|    | Incrementa el valor de un entero en la unidad |
|    | Ej: `A++` devuelve `11`                       |
|7 	| `--` (Decremento)                             |
|    | Diminuye un entero en la unidad               |
|    | Ej: `A--` devuelve 9                          |

Nota: el operador de adición (+) funciona tanto para números como para cadenas. p.ej. "a" + 10 dará "a10".

### Ejemplo

El siguiente código muestra como usar operadores aritmeticos en JavaScript.

```html
<html>
   <body>
   
      <script type = "text/javascript">
         <!--
            var a = 33;
            var b = 10;
            var c = "Test";
            var linebreak = "<br />";
         
            document.write("a + b = ");
            result = a + b;
            document.write(result);
            document.write(linebreak);
         
            document.write("a - b = ");
            result = a - b;
            document.write(result);
            document.write(linebreak);
         
            document.write("a / b = ");
            result = a / b;
            document.write(result);
            document.write(linebreak);
         
            document.write("a % b = ");
            result = a % b;
            document.write(result);
            document.write(linebreak);
         
            document.write("a + b + c = ");
            result = a + b + c;
            document.write(result);
            document.write(linebreak);
         
            a = ++a;
            document.write("++a = ");
            result = ++a;
            document.write(result);
            document.write(linebreak);
         
            b = --b;
            document.write("--b = ");
            result = --b;
            document.write(result);
            document.write(linebreak);
         //-->
      </script>
      
      Set the variables to different values and then try...
   </body>
</html>
```

## Operadores de comparación

JavaScript es compatible con los siguientes operadores de comparación:

Supongamos que la variable A contiene 10 y la variable B tiene 20, entonces -

|No. |	Operador & Descripcion |
|----|-------------------------|
|1 	 | `= =` (Igual)|
|    | Comprueba si el valor de dos operandos es igual o no, si es así, entonces la condición se vuelve verdadera.|
|    | Ej: `(A == B)` no es verdadero / is not true.|
|2 	 | `!=` (No Igual)|
|    | Comprueba si el valor de dos operandos es igual o no, si los valores no son iguales, entonces la condición se vuelve verdadera. |
|    | Ej: `(A != B)` es verdadero. |
|3 	 | `>` (Mayor que)|
|    | Comprueba si el valor del operando izquierdo es mayor que el valor del operando derecho, si es así, entonces la condición se vuelve verdadera. |
|    | Ej: `(A > B)` no es cierto.|
|4 	 | `<` (Menor que) |
|    | Comprueba si el valor del operando izquierdo es menor que el valor del operando derecho, si es así, entonces la condición se vuelve verdadera. |
|    | Ej: `(A < B)` es verdadero.|
|5 	 | `>=` (Mayor que o Igual a) |
|    | Comprueba si el valor del operando izquierdo es mayor o igual que el valor del operando derecho, si es así, entonces la condición se vuelve verdadera.|
|    | Ej: `(A >= B)` no es cierto.|
|6 	 | `<=` (Menor que o igual a)|
|    | Comprueba si el valor del operando izquierdo es menor o igual que el valor del operando derecho, si es así, entonces la condición se vuelve verdadera. |
|    | Ej: `(A <= B)` es cierto.|

### Ejemplo

El siguiente código muestra como usar operadores de comparacion en JavaScript.

```html
<html>
   <body>  
      <script type = "text/javascript">
         <!--
            var a = 10;
            var b = 20;
            var linebreak = "<br />";
      
            document.write("(a == b) => ");
            result = (a == b);
            document.write(result);
            document.write(linebreak);
         
            document.write("(a < b) => ");
            result = (a < b);
            document.write(result);
            document.write(linebreak);
         
            document.write("(a > b) => ");
            result = (a > b);
            document.write(result);
            document.write(linebreak);
         
            document.write("(a != b) => ");
            result = (a != b);
            document.write(result);
            document.write(linebreak);
         
            document.write("(a >= b) => ");
            result = (a >= b);
            document.write(result);
            document.write(linebreak);
         
            document.write("(a <= b) => ");
            result = (a <= b);
            document.write(result);
            document.write(linebreak);
         //-->
      </script>      
      Set the variables to different values and different operators and then try...
   </body>
</html>
```

## Operadores logicos

JavaScript es compatible con los siguientes operadores lógicos:

Supongamos que la variable A contiene 10 y la variable B tiene 20, entonces -

|No. |	Operator & Description |
|----|-------------------------|
|1 	 | `&&` (Logico AND) |
|    | Si ambos operandos son distintos de cero, la condición se cumple. |
|    | Ej: `(A && B)` es cierto. |
| 2  | `||` (Logico OR) |
|    | Si alguno de los dos operandos es distinto de cero, la condición se cumple.|
|    | Ej: `(A || B)` es cierto.|
| 3  | `!` (Logico NOT) |
|    | Invierte el estado lógico de su operando. Si una condición es verdadera, entonces el operador lógico NOT lo hará falso.|
|    | Ej: `! (A && B)` es falso.|

### Ejemplo

Pruebe el siguiente código para implementar operadores lógicos en JavaScript.

```html
<html>
   <body>   
      <script type = "text/javascript">
         <!--
            var a = true;
            var b = false;
            var linebreak = "<br />";
      
            document.write("(a && b) => ");
            result = (a && b);
            document.write(result);
            document.write(linebreak);
         
            document.write("(a || b) => ");
            result = (a || b);
            document.write(result);
            document.write(linebreak);
         
            document.write("!(a && b) => ");
            result = (!(a && b));
            document.write(result);
            document.write(linebreak);
         //-->
      </script>      
      <p>Set the variables to different values and different operators and then try...</p>
   </body>
</html>
````
## Operadores Binarios (bit a bit)

JavaScript es compatible con los siguientes operadores binarios:

Supongamos que la variable A tiene 2 y la variable B tiene 3, entonces -

|No. |	Operator & Description |
|----|-------------------------|
|1 	 | `&` (BitWise AND) |
|    | Realiza una operación AND booleana en cada bit de sus argumentos enteros.|
|    | Ej: `(A & B)` es 2.|
|2 	 | `|` (BitWise OR) |
|    | Realiza una operación OR booleana en cada bit de sus argumentos enteros. |
|    | Ej: `(A | B)` es 3.|
|3 	 | `^` (Bitwise XOR) |
|    | Realiza una operación OR exclusiva booleana en cada bit de sus argumentos enteros. Exclusivo XOR significa que el operando uno es verdadero o el operando dos es verdadero, pero no ambos.|
|    | Ejx `(A ^ B)` es 1. |
|4 	 | `~` (Bitwise Not) |
|    | Es un operador unario y opera invirtiendo todos los bits en el operando. |
|    | Ej: `(~B)` es -4.|
|5 	 | `<<` (Shift izquierdo) |
|    | Mueve todos los bits en su primer operando a la izquierda por el número de lugares especificados en el segundo operando. Los nuevos bits están llenos de ceros. Desplazar un valor dejado por una posición equivale a multiplicarlo por 2, desplazar dos posiciones equivale a multiplicar por 4, y así sucesivamente.|
|    | Ej: `(A << 1)` es 4. |
|6 	 | `>>` (Shift derecho) |
|    | Operador de cambio a la derecha binario. El valor del operando izquierdo se mueve hacia la derecha por el número de bits especificado por el operando derecho.|
|    | Ej: `(A >> 1)` es 1. |
|7 	 | `>>>` (shift derecho con cero) |
|    | Este operador es igual que el operador `>>`, excepto que los bits desplazados a la izquierda siempre son cero. |
|    | Ej: `(A >>> 1)` es 1.|

### Ejemplo

Pruebe el siguiente código para implementar el operador Bitwise en JavaScript.

```html
<html>
   <body>   
      <script type = "text/javascript">
         <!--
            var a = 2; // Bit presentation 10
            var b = 3; // Bit presentation 11
            var linebreak = "<br />";
         
            document.write("(a & b) => ");
            result = (a & b);
            document.write(result);
            document.write(linebreak);
         
            document.write("(a | b) => ");
            result = (a | b);
            document.write(result);
            document.write(linebreak);
         
            document.write("(a ^ b) => ");
            result = (a ^ b);
            document.write(result);
            document.write(linebreak);
         
            document.write("(~b) => ");
            result = (~b);
            document.write(result);
            document.write(linebreak);
         
            document.write("(a << b) => ");
            result = (a << b);
            document.write(result);
            document.write(linebreak);
         
            document.write("(a >> b) => ");
            result = (a >> b);
            document.write(result);
            document.write(linebreak);
         //-->
      </script>      
      <p>Set the variables to different values and different operators and then try...</p>
   </body>
</html>
```

## Operadores de Asignación

JavaScript es compatible con los siguientes operadores de asignación:

|No.  |	Operator & Description|
|-----|-----------------------|
|1 	  | `=` (Asignacion simple) |
|     | Asigna valores del operando del lado derecho al operando del lado izquierdo |
|     | Ej: `C = A + B` asignara el valor de A + B into C |
|2 	  | 

+= (Add and Assignment)

It adds the right operand to the left operand and assigns the result to the left operand.

Ex: C += A is equivalent to C = C + A
3 	

−= (Subtract and Assignment)

It subtracts the right operand from the left operand and assigns the result to the left operand.

Ex: C -= A is equivalent to C = C - A
4 	

*= (Multiply and Assignment)

It multiplies the right operand with the left operand and assigns the result to the left operand.

Ex: C *= A is equivalent to C = C * A
5 	

/= (Divide and Assignment)

It divides the left operand with the right operand and assigns the result to the left operand.

Ex: C /= A is equivalent to C = C / A
6 	

%= (Modules and Assignment)

It takes modulus using two operands and assigns the result to the left operand.

Ex: C %= A is equivalent to C = C % A

**Nota** - La misma lógica se aplica a los operadores bit a bit por lo que llegarán a ser como `<< =`, `>> =`, `>> =`, Y `=`, `| = y ^ =`.

### Ejemplo

Pruebe el siguiente código para implementar el operador de asignación en JavaScript.

```html
<html>
   <body>   
      <script type = "text/javascript">
         <!--
            var a = 33;
            var b = 10;
            var linebreak = "<br />";
         
            document.write("Value of a => (a = b) => ");
            result = (a = b);
            document.write(result);
            document.write(linebreak);
         
            document.write("Value of a => (a += b) => ");
            result = (a += b);
            document.write(result);
            document.write(linebreak);
         
            document.write("Value of a => (a -= b) => ");
            result = (a -= b);
            document.write(result);
            document.write(linebreak);
         
            document.write("Value of a => (a *= b) => ");
            result = (a *= b);
            document.write(result);
            document.write(linebreak);
         
            document.write("Value of a => (a /= b) => ");
            result = (a /= b);
            document.write(result);
            document.write(linebreak);
         
            document.write("Value of a => (a %= b) => ");
            result = (a %= b);
            document.write(result);
            document.write(linebreak);
         //-->
      </script>      
      <p>Set the variables to different values and different operators and then try...</p>
   </body>
</html>
```

## Operador Misceláneo

Aquí discutiremos dos operadores que son bastante útiles en JavaScript: el operador condicional (? :) y el operador typeof.

### Operador Condicional (? :)

El operador condicional primero evalúa una expresión para un valor verdadero o falso y luego ejecuta una de las dos declaraciones dadas, dependiendo del resultado de la evaluación.

|No. 	| Operator and Description|
|-------|-------------------------|
|1 	    | ? : (Conditional ) |
|       | If Condition is true? Then value X : Otherwise value Y|

### Ejemplo

Pruebe el siguiente código para comprender cómo funciona el operador condicional en JavaScript.


```html
<html>
   <body>   
      <script type = "text/javascript">
         <!--
            var a = 10;
            var b = 20;
            var linebreak = "<br />";
         
            document.write ("((a > b) ? 100 : 200) => ");
            result = (a > b) ? 100 : 200;
            document.write(result);
            document.write(linebreak);
         
            document.write ("((a < b) ? 100 : 200) => ");
            result = (a < b) ? 100 : 200;
            document.write(result);
            document.write(linebreak);
         //-->
      </script>      
      <p>Set the variables to different values and different operators and then try...</p>
   </body>
</html>
```
### operador typeof

El operador typeof es un operador unario que se coloca antes de su operando único, que puede ser de cualquier tipo. Su valor es una cadena que indica el tipo de datos del operando.

El operador typeof se evalúa como "número", "cadena" o "booleano" si su operando es un número, cadena o valor booleano y devuelve verdadero o falso según la evaluación.

Aquí hay una lista de los valores de retorno para el tipo de Operador.

|Type | String Returned by typeof|
|-----|--------------------------|
Number 	"number"
String 	"string"
Boolean 	"boolean"
Object 	"object"
Function 	"function"
Undefined 	"undefined"
Null 	"object"

### Ejemplo

El siguiente código muestra cómo implementar el operador typeof.

```html
<html>
   <body>      
      <script type = "text/javascript">
         <!--
            var a = 10;
            var b = "String";
            var linebreak = "<br />";
         
            result = (typeof b == "string" ? "B is String" : "B is Numeric");
            document.write("Result => ");
            document.write(result);
            document.write(linebreak);
         
            result = (typeof a == "string" ? "A is String" : "A is Numeric");
            document.write("Result => ");
            document.write(result);
            document.write(linebreak);
         //-->
      </script>      
      <p>Set the variables to different values and different operators and then try...</p>
   </body>
</html>
```
### Contacto

- Envienos sus comentarios al correo `henrytorrespo@yahoo.com`
