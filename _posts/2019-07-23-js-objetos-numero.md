---
title: JavaScript - Objeto Number
description: El objeto `Number` es un objeto envolvente que permite trabajar con valores numericos. 
categories: Blog
comments: true
---

El objeto `Number` representa una fecha numerica, ya sea numeros enteros o numeros en coma flotante. En general, no tiene que preocuparse por los objetos numericos porque el navegador convierte automaticamente los literales numericos en instancias de la clase `Number`.
	
La sintaxis para crear un objeto `Number` es la siguiente:

```JavaScript
var val = new Number(number);
```

Si en lugar de `number`, si proporciona un argumento que no sea un numero, el argumento no se puede convertir a un numero, en ese cas devuelve `NaN` (No es un numero).

### Propiedades de `Number`

Aquí hay una lista de cada propiedad y su descripcion.

| Sr.No. |	Propiedad & Descripcion  |
|--------|---------------------------|
| 1      | `MAX_VALUE`               |
|        | El mayor valor posible que puede tener un número en JavaScript. 1.7976931348623157E+308|
| 2      | `MIN_VALUE`               |
|        | El valor mas pequeño posible que puede tener un numero en JavaScript. 5E-324                 |
| 3      |  `NaN`                    |
|        | Igual a un valor que no es un número. |
| 4      | `NEGATIVE_INFINITY`       |
|        | Un valor que es menor que `MIN_VALUE`.|
| 5      | `POSITIVE_INFINITY`       |
|        | Un valor que es mayor que `MAX_VALUE`. |
| 6      | `prototype`               |
|        | Una propiedad estatica del objeto `Number`. Use la propiedad `prototype` para asignar nuevas propiedades y metodos al objeto `Number` en el documento actual            |
| 7      | `constructor`             |
|        | Devuelve la funcion que creo la instancia de este objeto. Por defecto, este es el objeto `Number`.|

### Metodos de `Number`

El objeto `Number` solo contiene los metodos predeterminados que forman parte de la definicion de cada objeto.

| Sr.No. |	Propiedad & Descripcion  |
|--------|---------------------------|
| 1      | `toExponential()`         |
|        | Hace que un numero se muestre en notacion exponencial, incluso si el numero esta en el rango en el que JavaScript normalmente usa la notacion estandar.            |
| 2      | `toFixed()`               |
|        | Formatea a un numero especifico de digitos a la derecha del decimal.    |
| 3      | `toLocaleString()`        |
|        | Devuelve una cadena de caracteres del numero actual en un formato que puede variar de acuerdo con la configuracion local del  navegador. |
| 4      | `toPrecision()`           |
|        | Define cuantos dígitos totales (incluidos los dígitos a la izquierda y derecha del decimal) utiliza para mostrar un numero. |
| 5      | `toString()`              |
|        | Devuelve la representación de cadena de caracteres del valor del numero. |
| 6      | `valueOf()`               |
|        | Devuelve el valor del numero. |


### Contacto

- Envia Tus comentarios al correo `henrytorrespo@yahoo.com`
