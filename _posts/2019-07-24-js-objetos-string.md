---
title: JavaScript - Objeto String
description: El objeto `String` es un objeto envolvente / Wrapper que permite trabajar con cadenas de caracteres. 
categories: 
  - Blog
  - Javascript
comments: true
---

El objeto `String` le permite trabajar con una serie de caracteres; envuelve el tipo de datos primitivos de cadena de caracteres en Javascript con varios metodos de ayuda.

Como JavaScript convierte automaticamente entre primitivas de cadena de caracteres y objetos `String`, puede llamar a cualquiera de los metodos auxiliares del objeto `String` desde una primitiva de cadena de caracteres.

Utilice la siguiente sintaxis para crear un objeto `String`.

```terminal
var val = new String(string);
```

El parametro `string` es una cadena de caracteres.

### Propiedades de `String`

Aquí hay una lista de las propiedades del objeto `String`:

| Sr.No. |	Propiedad & Descripcion  |
|--------|---------------------------|
| 1      | `constructor`             |
|        | Devuelve una referencia a la funcion `String` que creó el objeto. |
| 2      | `length`                  |
|        | Devuelve la longitud de la cadena de caracteres. |
| 3      | `prototype`               |
|        | La propiedad `prototype` permite agregar propiedades y metodos a un objeto. |

Mas adelante tendremos algunos ejemplos para ilustrar las propiedades del objeto `String`.


### Metodos de `String`

Aquí hay una lista de los metodos del objeto `String` y su descripción.

| Sr.No. |	Metodo & Descripcion  |
|--------|---------------------------|
| 1      | `charAt()`              |
|        | Devuelve el caracter en el índice especificado. |
| 2      | `charCodeAt()`          |
|        | Devuelve un numero que indica el valor Unicode del caracter en el índice dado. |
| 3      | `concat()`              |
|        | Combina el texto de dos cadenas de caracteres y devuelve una nueva cadena. |
| 4      | `indexOf )`             |
|        | Devuelve el índice dentro del objeto `String` de llamada de la primera aparición del valor especificado, o -1 si no se encuentra. |
| 5      | `lastIndexOf()`         |
|        | Devuelve el índice dentro del objeto `String` de llamada de la ultima aparicion del valor especificado, o -1 si no se encuentra. |
| 6      | `localeCompare()`       |
|        | Devuelve un numero que indica si una cadena de referencia aparece antes o despues o si es igual a la cadena dada en orden de clasificacion. |
| 7      | `match()`               |
|        | Se utiliza para hacer coincidir una expresion regular con una cadena. |
| 8      | `replace()`             |
|        | Se utiliza para encontrar una coincidencia entre una expresión regular y una cadena, y para reemplazar la subcadena coincidente con una nueva subcadena. |
| 9      | `search()`                |
|        | Ejecuta la busqueda de una coincidencia entre una expresion regular y una cadena especificada. |
| 10     | `slice()`               |
|        | Extrae una seccion de una cadena y devuelve una nueva cadena.|
| 11     | `split()`               |
|        | Divide un objeto `String` en una matriz de cadenas separando la cadena en subcadenas. |
| 12     | `substr()`              |
|        | Devuelve los caracteres en una cadena que comienza en la ubicacion especificada a traves del numero especificado de caracteres.|
| 13     | `substring()`           |
|        | Devuelve los caracteres en una cadena entre dos índices en la cadena.|
| 14     | `toLocaleLowerCase()`   |
|        | Los caracteres dentro de una cadena se convierten a minusculas respetando la configuración regional actual.|
| 15     | `toLocaleUpperCase()`   |
|        | Los caracteres dentro de una cadena se convierten a mayusculas respetando la configuración regional actual.|
| 16     | `toLowerCase()`         |
|        | Devuelve el valor de la cadena de llamada convertido a minusculas.|
| 17     | `toString()`            |
|        | Devuelve una cadena que representa el objeto especificado.|
| 18     | `toUpperCase()`         |
|        | Devuelve el valor de la cadena de llamada convertido a mayusculas.|
| 19     | `valueOf()`             |
|        | Devuelve el valor primitivo del objeto especificado.|

Mas adelante tendremos algunos ejemplos para demostrar el uso de los metodos de `String`.

### Envoltorios / Wrappers de String HTML

Aquí hay una lista de los metodos que devuelven una copia de la cadena envuelta dentro de una etiqueta HTML apropiada.

| Sr.No. |	Metodo & Descripcion  |
|--------|---------------------------|
| 1      | `anchor()`             |
|        | Crea un ancla HTML que se utiliza como un hipertexto objetivo.|
| 2      | `big()`                |
|        | Crea una cadena que se mostrara en una fuente grande como si estuviera en una etiqueta `<big>`. |
| 3      | `blink()`              |
|        | Crea una cadena para parpadear como si estuviera en una etiqueta `<blink>`. |
| 4      | `bold()`               |
|        | Crea una cadena que se mostrara en negrita como si estuviera en una etiqueta `<b>`. |
| 5      | `fixed()`              |
|        | Hace que una cadena se muestre en una fuente de tono fijo como si estuviera en una etiqueta `<tt>` |
| 6      | `fontcolor()`          |
|        | Hace que una cadena se muestre en el color especificado como si estuviera en una etiqueta `<font color = "color">`. |
| 7      | `fontsize()`           |
|        | Hace que una cadena se muestre en el tamaño de fuente especificado como si estuviera en una etiqueta `<font size = "size">`.|
| 8      | `italics()`            |
|        | Hace que una cadena este en cursiva, como si estuviera en una etiqueta `<i>`. |
| 9      | `link()`               |
|        | Crea un enlace hipertexto HTML que solicita otra URL.|
| 10     | `small()`              |
|        | Hace que una cadena se muestre en una fuente pequeña, como si estuviera en una etiqueta `<small>`.|
| 11     | `strike()`             |
|        | Hace que una cadena se muestre como texto tachado, como si estuviera en una etiqueta `<strike>`.|
| 12     | `sub()`                |
|        | Hace que una cadena se muestre como un subíndice, como si estuviera en una etiqueta `<sub>`.|
| 13     | `sup()`                |
|        | Hace que una cadena se muestre como un superíndice, como si estuviera en una etiqueta `<sup>`. |

Mas adelante tendremos algunos ejemplos para demostrar el uso de los metodos de `String`.


### Contacto

- Envia Tus comentarios al correo `henrytorrespo@yahoo.com`
