---
title: JavaScript - Objeto Array
description: El objeto `Array` o matriz es un conjunto ordenado de valores al que se refiere con un nombre y un índice.  
categories: Blog
comments: true
---

El objeto `Array` le permite almacenar muchos valores en una sola variable. Almacena un conjunto secuencial de elementos del mismo tipo de tamaño fijo . Una matriz se utiliza para almacenar un conjunto de datos, pero a menudo es mas util pensar en una matriz como un conjunto de variables del mismo tipo.


Utilice la siguiente sintaxis para crear un objeto `Array`.

```terminal
var fruits = new Array( "apple", "orange", "mango" );
```

El parametro `Array` es una lista de cadenas de caracteres o enteros. Cuando especifica un solo parametro numerico con el constructor `Array`, especifica la longitud inicial de la matriz. La longitud maxima permitida para una matriz es 4,294,967,295.

Puede crear una matriz simplemente asignando valores de la siguiente manera:

```terminal
var fruits = [ "apple", "orange", "mango" ];
```

Utilizara los numeros ordinales para acceder y establecer valores dentro de una matriz de la siguiente manera.

```terminal
fruits[0] is the first element
fruits[1] is the second element
fruits[2] is the third element
```

### Propiedades de `Array`

Aquí hay una lista de las propiedades del objeto `Array`:

| Sr.No. |	Propiedad & Descripcion  |
|--------|---------------------------|
| 1      | `constructor`             |
|        | Devuelve una referencia a la funcion de la matriz que creo el objeto. |
| 2      | `index`                   |
|        | La propiedad representa el indice base cero de la coincidencia en la cadena. |
| 3      | `input`                   |
|        | Esta propiedad solo esta presente en matrices creadas por coincidencias de expresiones regulares. |
| 4      | `length`                  |
|        | Refleja el numero de elementos en una matriz. |
| 5      | `prototype`               |
|        | La propiedad `prototype` le permite agregar propiedades y metodos a un objeto.  |

Mas adelante tendremos algunos ejemplos para ilustrar las propiedades del objeto `Array`.


### Metodos de `Array`

Aquí hay una lista de los metodos del objeto `Array` y su descripcion.

| Sr.No. |	Metodo & Descripcion  |
|--------|------------------------|
| 1      | `concat()`             |
|        | Devuelve una nueva matriz compuesta por esta matriz unida con otra matriz y valores. |
| 2      | `every()`              |
|        | Devuelve verdadero si cada elemento de esta matriz satisface la funcion de prueba. |
| 3      | `filter()`             |
|        | Crea una nueva matriz con todos los elementos de esta matriz para los que la funcion de filtrado devuelve verdadero.|
| 4      | `forEach()`            |
|        | Llama una funcion para cada elemento de la matriz.|
| 5      | `indexOf()`            |
|        | Devuelve el primer (menor) índice de un elemento dentro de la matriz igual al valor especificado, o -1 si no se encuentra ninguno.|
| 6      | `join()`               |
|        | Une todos los elementos de una matriz en una cadena de caracteres.|
| 7      | `lastIndexOf()`        |
|        | Devuelve el ultimo índice (el mas grande) de un elemento dentro de la matriz igual al valor especificado, o -1 si no se encuentra ninguno.|
| 8      | `map()`                |
|        | Crea una nueva matriz con los resultados del llamado a una función proporcionada en cada elemento de esta matriz.|
| 9      | `pop()`                |
|        | Elimina el ultimo elemento de una matriz y devuelve ese elemento.|
| 10     | `push()`               |
|        | Agrega uno o mas elementos al final de una matriz y devuelve la nueva longitud de la matriz.|
| 11     | `reduce()`             |
|        | Aplique una funcion simultaneamente contra dos valores de la matriz (de izquierda a derecha) para reducirla a un solo valor.|
| 12     | `reduceRight()`        |
|        | Aplique una funcion simultaneamente contra dos valores de la matriz (de derecha a izquierda) para reducirla a un solo valor.|
| 13     | `reverse()`            |
|        | Invierte el orden de los elementos de una matriz: el primero se convierte en el ultimo y el ultimo en el primero.|
| 14     | `shift()`              |
|        | Elimina el primer elemento de una matriz y devuelve ese elemento.|
| 15     | `slice()`              |
|        | Extrae una seccion de una matriz y devuelve una nueva matriz.|
| 16     | `some()`               |
|        | Devuelve verdadero si al menos un elemento en esta matriz satisface la función de prueba provista.|
| 17     | `toSource()`           |
|        | Representa el codigo fuente de un objeto.|
| 18     | `sort()`               |
|        | Ordena los elementos de una matriz.|
| 19     | `splice()`             |
|        | Agrega y / o elimina elementos de una matriz.|
| 20     | `toString()`           |
|        | Devuelve una cadena que representa la matriz y sus elementos.|
| 21     | `unshift()`            |
|        | Agrega uno o mas elementos al frente de una matriz y devuelve la nueva longitud de la matriz.|

Mas adelante tendremos algunos ejemplos para demostrar el uso de los metodos de `Array`.

### Contacto

- Envia Tus comentarios al correo `henrytorrespo@yahoo.com`
