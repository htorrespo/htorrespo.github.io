---
title: JavaScript - Objeto Date
description: El objeto `Date` Permite trabajar con fechas y horas.  
categories: 
  - Blog
  - Javascript
comments: true
---

El objeto `Date` es un tipo de datos integrado en el lenguaje JavaScript. Los objetos de fecha se crean con la `new Date()` como se muestra a continuacion.

Una vez que se crea un objeto `Date`, varios metodos le permiten operar en el. La mayoria de los metodos simplemente le permiten obtener y establecer los campos año, mes, dia, hora, minuto, segundo y milisegundos del objeto, utilizando la hora local o la hora UTC (universal o GMT).

El estandar ECMAScript requiere que el objeto `Date` pueda representar cualquier fecha y hora, con una precision de milisegundos, dentro de los 100 millones de días antes o despues de 1/1/1970. Este es un rango de mas o menos 273,785 años, por lo que JavaScript puede representar la fecha y la hora hasta el año 275755.

Puede usar cualquiera de las siguientes sintaxis para crear un objeto Date utilizando el constructor `Date()`.

```terminal
new Date( )
new Date(milliseconds)
new Date(datestring)
new Date(year,month,date[,hour,minute,second,millisecond ])
```

**Nota**: los parametros entre parentesis son siempre opcionales.

A continuacon una descripcion de los parametros:

**Sin argumento**: sin argumentos, el constructor `Date()` crea un objeto Fecha en la fecha y hora actuales.

**milliseconds**: cuando se pasa un argumento numerico, se toma la representación numerica interna de la fecha en milisegundos, segun lo devuelto por el método `getTime()`. Por ejemplo, pasar el argumento 5000 crea una fecha que representa cinco segundos después de la medianoche de 1/1/70.

**datestring**: cuando se pasa un argumento de cadena, es una representación de cadena de caracteres de una fecha, en el formato aceptado por el método `Date.parse()`.

**7 argumentos**: para utilizar la ultima forma del constructor que se muestra arriba. Ahora una descripción de cada argumento:



### Propiedades de `Date`

Aquí hay una lista de las propiedades del objeto `Array`:

| Sr.No. |	Propiedad & Descripcion  |
|--------|---------------------------|
| 1      | `constructor`             |
|        | Especifica la funcion que crea el prototipo de un objeto.|
| 2      | `prototype`               |
|        | La propiedad prototipo le permite agregar propiedades y metodos a un objeto.|


Mas adelante tendremos algunos ejemplos para ilustrar las propiedades del objeto `Date`.


### Metodos de `Date`

Aquí hay una lista de los metodos del objeto `Array` y su descripcion.

| Sr.No. |	Metodo & Descripcion  |
|--------|------------------------|
| 1      | `Date()`               |
|        | Devuelve la fecha y hora de hoy. |
| 2      | `getDate()`            |
|        | Devuelve el día del mes para la fecha especificada segun la hora local.|
| 3      | `getDay()`             |
|        | Devuelve el día de la semana para la fecha especificada segun la hora local.|
| 4      | `getFullYear()`        |
|        | Devuelve el año de la fecha especificada segun la hora local.|
| 5      | `getHours()`           |
|        | Devuelve la hora en la fecha especificada segun la hora local.|
| 6      | `getMilliseconds()`    |
|        | Devuelve los milisegundos en la fecha especificada segun la hora local.|
| 7      | `getMinutes()`         |
|        | Devuelve los minutos en la fecha especificada segun la hora local.|
| 8      | `getMonth()`           |
|        | Devuelve el mes en la fecha especificada segun la hora local.|
| 9      | `getSeconds()`         |
|        | Devuelve los segundos en la fecha especificada segun la hora local.|
| 10     | `getTime()`            |
|        | Devuelve el valor numerico de la fecha especificada como el numero de milisegundos desde el 1 de enero de 1970, 00:00:00 UTC.|
| 11     | `getTimezoneOffset()`   |
|        | Devuelve el desplazamiento de zona horaria en minutos para la configuracion regional actual.|
| 12     | `getUTCDate()`          |
|        | Devuelve el día (fecha) del mes en la fecha especificada segun la hora universal.|
| 13     | `getUTCDay()`           |
|        | Devuelve el día de la semana en la fecha especificada segun la hora universal.|
| 14     | `getUTCFullYear()`      |
|        | Devuelve el año en la fecha especificada segun horario universal.|
| 15     | `getUTCHours()`         |
|        | Devuelve las horas en la fecha especificada segun hora universal.|
| 16     | `getUTCMilliseconds()`  |
|        | Devuelve los milisegundos en la fecha especificada segun la hora universal.|
| 17     | `getUTCMinutes()`       |
|        | Devuelve los minutos en la fecha especificada segun la hora universal.|
| 18     | `getUTCMonth()`         |
|        | Devuelve el mes en la fecha especificada segun hora universal.|
| 19     | `getUTCSeconds()`       |
|        | Devuelve los segundos en la fecha especificada segun la hora universal.|
| 20     | `getYear()`             |
|        | En desuso: devuelve el año en la fecha especificada segun la hora local. Use `getFullYear()` en su lugar.|
| 21     | `setDate()`             |
|        | Establece el día del mes para una fecha específica de acuerdo con la hora local.|
| 22     | `setFullYear()`         |
|        | Establece el año completo para una fecha específica de acuerdo con la hora local.|
| 23     | `setHours()`            |
|        | Establece las horas para una fecha específica de acuerdo con la hora local.|
| 24     | `setMilliseconds()`     |
|        | Establece los milisegundos para una fecha específica de acuerdo con la hora local.|
| 25     | `setMinutes()`          |
|        | Establece los minutos para una fecha específica de acuerdo con la hora local.|
| 26     | `setMonth()`            |
|        | Establece el mes para una fecha específica de acuerdo a la hora local.|
| 27     | `setSeconds()`          |
|        | Establece los segundos para una fecha específica segun la hora local.|
| 28     | `setTime()`             |
|        | Establece el objeto `Date` a la hora representada por una cantidad de milisegundos desde el 1 de enero de 1970, 00:00:00 UTC.|
| 29     | `setUTCDate()`          |
|        | Establece el día del mes para una fecha específica de acuerdo con la hora universal.|
| 30     | `setUTCFullYear()`      |
|        | Establece el año completo para una fecha específica de acuerdo con la hora universal.|
| 31     | `setUTCHours()`         |
|        | Establece la hora para una fecha específica de acuerdo a la hora universal.|
| 32     | `setUTCMilliseconds()`  |
|        | Establece los milisegundos para una fecha específica de acuerdo con la hora universal.|
| 33     | `setUTCMinutes()`       |
|        | Establece los minutos para una fecha específica de acuerdo a la hora universal.|
| 34     | `setUTCMonth()`         |
|        | Establece el mes para una fecha específica de acuerdo a la hora universal.|
| 35     | `setUTCSeconds()`       |
|        | Establece los segundos para una fecha específica de acuerdo a la hora universal.|
| 36     | `setYear()`             |
|        | En desuso: establece el año para una fecha específica de acuerdo con la hora local. Use `setFullYear()` en su lugar.|
| 37     | `toDateString()`        |
|        | Devuelve la porcion "date" de  `Date` como una cadena de caracteres legible.|
| 38     | `toGMTString()`         |
|        | En desuso: convierte una fecha en una cadena de caracteres, utilizando las convenciones de GMT de Internet. Utilice `toUTCString()` en su lugar.|
| 39     | `toLocaleDateString()`  |
|        | Devuelve la parte "date" de `Date` como una cadena de caracteres, usando las convenciones de la configuración regional actual.|
| 40     | `toLocaleFormat()`      |
|        | Convierte una fecha en una cadena de caracteres, utilizando un formato.|
| 41     | `toLocaleString()`      |
|        | Convierte una fecha en una cadena de caracteres , usando las convenciones de la configuración regional actual.|
| 42     | `toLocaleTimeString()`  |
|        | Devuelve la parte "time" de `Date` como una cadena de caracteres, utilizando las convenciones de la configuración regional actual.|
| 43     | `toSource()`            |
|        | Devuelve una cadena de caracteres que representa la fuente para un objeto `Date` equivalente; Puedes usar este valor para crear un nuevo objeto.|
| 44     | `toString()`               |
|        | Devuelve una cadena de caracteres que representa el objeto `Date`  especificado.|
| 45     | `toTimeString()`           |
|        | Devuelve la parte de "time" de  `Date` como una cadena legible por el hombre.|
| 46     | `toUTCString()`            |
|        | Convierte una fecha en una cadena de caracteres, utilizando la convención de tiempo universal.|
| 47     | `valueOf()`
|        | Devuelve el valor primitivo de un objeto `Date`.|

Convierte una fecha en una cadena, utilizando la convención de tiempo universal.

{% comment%}

La redaccion de la tabla anterior se puede mejorar con la traduccion realzada por el siguente link:
https://www.aprenderaprogramar.com/index.php?option=com_content&view=article&id=846:formato-fechas-javascript-tostring-tolocaledatestring-tolocaletimestrig-totimestring-ejemplo-cu01163e&catid=78&Itemid=206

{% endcomment%}


### Métodos de fecha estática

Además de los todos metodos de instancia enumerados anteriormente, el objeto `Date` también define dos metodos estaticos. Estos metodos se invocan a traves del propio constructor `Date`.

| Sr.No. |	Metodo & Descripcion  |
|--------|------------------------|
| 1      | `Date.parse( )`        |
|        | Analiza una representacion de cadena de caracteres de fecha y hora y devuelve la representacion interna en milisegundos de esa fecha.|
|2       | `Date.UTC( )`          |
|        | Devuelve la representacion en milisegundos de la fecha y hora UTC especificadas.|

Mas adelante tendremos algunos ejemplos para demostrar el uso de los metodos de `Date`.

### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
