---
title: JavaScript - Objeto RegExp
description: Crea un objeto `RegExp` para encontrar texto de acuerdo a un patron.  
categories: 
  - Blog
  - Javascript
comments: true
---

Una expresion regular es un objeto que describe un patron de caracteres.

La clase `RegExp` de JavaScript representa expresiones regulares, y tanto `String` como `RegExp` definen metodos que usan expresiones regulares para realizar potentes funciones de comparacion de patrones y busqueda y reemplazo en el texto.

Una expresión regular podría definirse con el constructor `RegExp()`, de la siguiente manera:

```terminal
var pattern = new RegExp(pattern, attributes);
or simply
var pattern = /pattern/attributes;
```

Aqui esta la descripcion de los parametros:

- **patron**: una cadena que especifica el patron de la expresion regular u otra expresion regular.

- **atributos**: una cadena opcional que contiene cualquiera de los atributos "g", "i" y "m" que especifican coincidencias globales, sin distincion de mayusculas y minusculas, respectivamente.

### Corchetes

Los corchetes (`[]`) tienen un significado especial cuando se usan en el contexto de expresiones regulares. Se utilizan para encontrar un rango de caracteres.

| Sr.No. |  Expresion & Descripcion  |
|--------|---------------------------|
| 1      | `[...]`                   |
|        | Cualquier caracter entre los parentesis.|
| 2      | `[^...]`                  |
|        | Cualquier caracter no presente entre los parentesis.|
| 3      | `[0-9]`                   |
|        | Coincide con cualquier digito decimal de 0 a 9.|
| 4      | `[a-z]`                   |
|        | Coincide con cualquier caracter desde una `a` minuscula a una `z` minuscula.|
| 5      | `[A-Z]`                   |
|        | Coincide con cualquier caracter desde una `A` mayuscula a una `Z` mayuscula.|
| 6      | `[a-Z]`                   |
|        | Coincide con cualquier caracter desde una `a` minuscula a  una `z` mayuscula.|

Los rangos mostrados antes son generales; tambien puede usar el rango `[0-3]` para hacer coincidir cualquier dígito decimal que oscile entre 0 y 3, o el rango `[b-v]` para hacer coincidir cualquier caracter en minuscula que vaya desde b hasta v.

### Cuantificadores

La frecuencia o posición de las secuencias de caracteres entre corchetes y los caracteres individuales se pueden denotar con un caracter especial. Cada caracter especial tiene una connotacion específica. Las banderas `+`, `*`,`?` Y `$` siguen una secuencia de caracteres.

| Sr.No. |  Expresion & Descripcion  |
|--------|---------------------------|
| 1      | `p+`                      |
|        | Coincide con cualquier cadena que contiene una o mas p.|
| 2      | `p*`                      |
|        | Coincide con cualquier cadena que contenga cero o mas p.|
| 3      | `p?`                      |
|        | Coincide con cualquier cadena que contenga como máximo una p.|
| 4      | `p{N}`                    |
|        | Coincide con cualquier cadena que contenga una secuencia de N p.|
| 5      | `p{2,3}`                  |
|        | Coincide con cualquier cadena que contenga una secuencia de dos o tres p.|
| 6      | `p{2, }`                  |
|        | Coincide con cualquier cadena que contenga una secuencia de al menos dos p.|
| 7      | `p$`                      |
|        | Coincide con cualquier cadena con p al final de ella.|
| 8      | `^p`                      |
|        | Coincide con cualquier cadena con p al principio de ella.|

#### Ejemplo

Los siguientes ejemplos explican mas acerca de los caracteres coincidentes.

| Sr.No. |  Expresion & Descripcion  |
|--------|---------------------------|
| 1      | `[^a-zA-Z]`               |
|        | Coincide con cualquier cadena que no contenga ninguno de los caracteres que van desde la a a la z y de la A a la Z.|
| 2      | `p.p`                     |
|        | Coincide con cualquier cadena que contenga p, seguida de cualquier caracter, seguida de otra p.|
| 3      | `^.{2}$`                  |
|        | Coincide con cualquier cadena que contiene exactamente dos caracteres.|
| 4      | `<b>(.*)</b>`             |
|        | Coincide con cualquier cadena encerrada entre `<b>` y `</b>`.|
| 5      | `p(hp)*`                  |
|        | Coincide con cualquier cadena que contenga una p seguida de cero o mas instancias de la secuencia hp.|

### Caracteres Literals

| Sr.No. |   Caracter & Descripcion  |
|--------|---------------------------|
| 1      | `Alphanumeric`            |
|        | Itself                    |
| 2      | `\0`                      |
|        | El caracter NUL  (\u0000)|
| 3      | `\t`                      |
|        | Tab (\u0009               |
| 4      | `\n`                      |
|        | Newline (\u000A)          |
| 5      | `\v`                      |
|        | Tab vertical (\u000B)     |
| 6      | `\f`                      |
|        | Form feed (\u000C)        |
| 7      | `\r`                      |
|        | Carro de retorno (\u000D)  |
| 8      | `\xnn`                    |
|        | El caracter latino especificado por el numero hexadecimal nn; por ejemplo, `\x0A` es lo mismo que `\n`| 
| 9      | `\uxxxx`                  |
|        | El caracter Unicode especificado por el numero hexadecimal xxxx; por ejemplo, `\u0009` es lo mismo que `\t`.|
| 10     | `\cX`                     |
|        | El caracter de control `^X`; por ejemplo, `\cJ` es equivalente al caracter de nueva línea `\n`. |

### Metacaracteres

Un metacaracter es simplemente un caracter alfabetico precedido por una barra invertida que actua para darle a la combinación un significado especial.

Por ejemplo, puede buscar una gran suma de dinero utilizando el metacaracter `\ d`: `/ ([\ d] +) 000 /`, Aqui `\ d` buscara cualquier cadena de caracteres numericos.

La siguiente tabla enumera un conjunto de metacaracteres que se pueden usar en las expresiones regulares al estilo PERL.

| Sr.No. |   Caracter & Descripcion  |
|--------|---------------------------|
| 1      | `.`                       |
|        | Un unico caracter.         |
| 2      | `\s`                      |
|        | Un caracter espacio (space, tab, newline).|
| 3      | `\S`                      |
|        | Un caracter que no es espacio.  |
| 4      | `\d`                      |
|        | Un digito (0-9)             |
| 5      | `\D`                      |
|        | Un no digito               |
| 6      | `\w`                      |
|        | Un caracter(a-z, A-Z, 0-9, `_`).|
| 7      | `\W`                      |
|        | Un no caracter      |
| 8      | `[\b]`                    |
|        | Un literal de retroceso (caso especial).|
| 9      | `[aeiou]`                 |
|        | coincide con un solo caracter en el conjunto dado.|
| 10     | `[^aeiou]`                |
|        | coincide con un solo caracter diferente del conjunto dado.| 
| 11     | `(foo|bar|baz)`           |
|        | coincide con cualquiera de las alternativas especificadas.|

### Modificadores

Hay varios modificadores disponibles que pueden simplificar la forma en que trabaja con expresiones regulares, como la sensibilidad a las mayusculas y minusculas, la busqueda en varias líneas, etc.

| Sr.No. | Modificador & Descripcion |
|--------|---------------------------|
| 1      | `i`                       |
|        | Realiza el emparejamiento insensible.|
| 2      | `m`                       |
|        | Especifica que si la cadena tiene caracteres de nueva línea o de carro de retorno, los operadores `^` y `$` ahora coincidirán con un límite de nueva línea, en lugar de limite de cadena.|
| 3      | `g`                       |
|        | Realiza una coincidencia global, es decir, encuentra todas las coincidencias en lugar de detenerte despues de la primera.|

### Propiedades RegExp

Aqui hay una lista de las propiedades asociadas con `RegExp` y su descripcion.

| Sr.No. |  Propiedad & Descripcion  |
|--------|---------------------------|
| 1      | `constructor`             |
|        | Especifica la funcion que crea el prototipo de un objeto.|
| 2      | `global`                  |
|        | Especifica si el modificador "g" esta configurado..|
| 3      | `ignoreCase`              |
|        | Especifica si el modificador "i" esta configurado..|
| 4      | `lastIndex`               |
|        | El índice en el que se empieza la proxima partida.|
| 5      | `multiline`               |
|        | Especifica si el modificador "m" esta configurado.|
| 6      | `source`                  |
|        | El texto del patron.|



### Metodos de `RegExp`

Aquí hay una lista de las metodos del objeto `RegExp`:

| Sr.No. |    Metodo & Descripcion   |
|--------|---------------------------|
| 1      | `exec()`                  |
|        | Ejecuta la busqueda de una coincidencia en su parametro `String`.
| 2      | `test()`                  |
|        | Prueba de una coincidencia en su parametro `String`.|
| 3      | `toSource()`              |
|        | Devuelve un objeto literal que representa el objeto especificado; Puedes usar este valor para crear un nuevo objeto.|
| 4      | `toString()`              |
|        | Devuelve una cadena que representa el objeto especificado.|

### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
