---
title: JavaScript - Objeto Math
description: El objeto `Math` permite trabajar con constantes y funciones matematicas.  
categories: 
  - Blog
  - Javascript
comments: true
---

El objeto `Math` le proporciona propiedades y metodos para  constantes y funciones matematicas. A diferencia de otros objetos globales, `Math` no es un constructor. Todas las propiedades y metodos de `Math` son estaticos y pueden invocarse utilizando `Math` como un objeto sin crearlo.

Así, te refieres a la constante pi como `Math.PI` y llamas a la funcion seno como `Math.sin(x)`, donde x es el argumento del metodo.


La sintaxis para llamar a las propiedades y metodos de `Math` son las siguientes

```terminal
var pi_val = Math.PI;
var sine_val = Math.sin(30);
```


### Propiedades de `Math`

Aquí hay una lista de las propiedades del objeto `Math`:

| Sr.No. |  Propiedad & Descripcion  |
|--------|---------------------------|
| 1      | `E \`                     |
|        | Constante de Euler y base de los logaritmos naturales, aproximadamente 2.718.|
| 2      | `LN2`                     |
|        | Logaritmo natural de 2, aproximadamente 0.693.|
| 3      | `LN10`                     |
|        | Logaritmo natural de 10, aproximadamente 2.302.|
| 4      | `LOG2E`                    |
|        | Base 2 del logaritmo de E, aproximadamente 1.442.|
| 5      | `LOG10E`                    |
|        | Representa el logaritmo base 10 de E, aproximadamente 0.434.|
| 6      | `PI`                       |
|        | Relacion / cociente de la circunferencia de un círculo a su diametro, aproximadamente 3.14159.|
| 7      | `SQRT1_2`                    |
|        | Raiz cuadrada de 1/2; equivalentemente, 1 sobre la raíz cuadrada de 2, aproximadamente 0.707.|
| 8      | `SQRT2`                     |
|        | Raiz cuadrada de 2, aproximadamente 1.414.|

Mas adelante tendremos algunos ejemplos para ilustrar las propiedades del objeto `Math`.


### Metodos de `Math`

Aquí hay una lista de los metodos del objeto `Math` y su descripcion.

| Sr.No. |  Metodo & Descripcion  |
|--------|------------------------|
| 1      | `abs()`                |
|        | Devuelve el valor absoluto de un numero.|
| 2      | `acos()`               |
|        | Devuelve el arco coseno (en radianes) de un numero.|
| 3      | `asin()`               |
|        | Devuelve el arcoseno (en radianes) de un numero.|
| 4      | `atan()`               |
|        | Devuelve el arctangente (en radianes) de un numero.|
| 5      | `atan2()`               |
|        | Devuelve el arctangente del cociente de sus argumentos.|
| 6      | `ceil()`               |
|        | devuelve el entero mayor o igual más proximo a un numero dado.|
| 7      | `cos()`                  |
|        | Devuelve el coseno de un numero dado.|
| 8      | `exp()`                  |
|        | Devuelve $E^N$, donde N es el argumento y E es la constante de Euler, la base del logaritmo natural.|
| 9      | `floor()`                |
|        | Devuelve el maximo entero menor o igual a un numero dado.|
| 10     | `log()`                  |
|        | Devuelve el logaritmo natural (base E) de un numero.|
| 11     | `max()`                  |
|        | Devuelve el mayor valor de uno o mas numeros.|
| 12     | `min()`                  |
|        | Devuelve el menor de cero o mas numeros.|
| 1      | `pow()`                  |
|        | Devuelve la base a la potencia del exponente, es decir, el exponente base.|
| 1      | `random()`               |
|        | Devuelve un numero pseudoaleatorio entre 0 y 1.|
| 15     | `round()`                |
|        | Devuelve el valor de un numero redondeado al entero mas cercano.|
| 16     | `sin()`                  |
|        | Devuelve el seno de un numero.|
| 17     | `sqrt()`                 |
|        | Devuelve la raiz cuadrada de un numero.|
| 18     | `tan()`                  |
|        | Devuelve la tangente de un numero.|
| 19     | `toSource()`                |
|        | Devuelve la cadena "Math".|

Convierte una fecha en una cadena, utilizando la convención de tiempo universal.


### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
