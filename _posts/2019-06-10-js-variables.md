---
title: Javascript - Tipos de Datos
description: Variables globales y locales, nombre de variables, palabras reservadas 
categories: Blog
comments: true
---

Una de las características fundamentales de un lenguaje de programación son los tipos de datos que admite. Estos es los tipos de valores que se pueden representar y manipular en un lenguaje de programación.

JavaScript permite trabajar con tres tipos de datos primitivos:

- Números, por ejemplo. 123, 120.50 etc.

- Cadenas de caracteres, p. "Esta cadena de texto" etc.

- Booleano por ejemplo verdadero o falso.

JavaScript también define dos tipos de datos triviales, null y undefined, cada uno de los cuales define un solo valor. Además de estos tipos de datos primitivos, JavaScript admite un tipo de datos compuesto conocido como objeto. Cubriremos los objetos en detalle en otro capítulo.

Nota: JavaScript no hace una distinción entre valores enteros y valores de punto flotante. Todos los números en JavaScript se representan como valores de punto flotante. JavaScript representa los números en formato de punto flotante de 64 bits definido por el estándar IEEE 754.

## Variables en JavaScript

Como muchos lenguajes de programación, JavaScript tiene variables. Las variables se pueden considerar como contenedores con nombre. Puede colocar datos en estos contenedores y luego referirse a los datos simplemente nombrando el contenedor.

Antes de utilizar una variable en un programa, debe declararla. Las variables se declaran con la palabra clave var de la siguiente manera.

```html
<script type = "text/javascript">
   <!--
      var money;
      var name;
   //-->
</script>
```

Puede declarar múltiples variables con la palabra clave `var` de la siguiente manera:

```html
<script type = "text/javascript">
   <!--
      var money, name;
   //-->
</script>
```

Almacenar un valor en una variable se llama inicialización de variable. Puede realizar la inicialización de variables en el momento de la creación de la variable o en un momento posterior cuando necesite esa variable.

Por ejemplo, puede crear una variable llamada money y asignarle el valor 2000.50 más adelante. Para otra variable, puede asignar un valor en el momento de la inicialización de la siguiente manera.

```html
<script type = "text/javascript">
   <!--
      var name = "Ali";
      var money;
      money = 2000.50;
   //-->
</script>
```

Nota: utilice la palabra clave `var` para la declaración o inicialización. No debe declarar de nuevo la misma variable dos veces.

JavaScript es un lenguaje no tipado. Esto significa que una variable de JavaScript puede contener un valor de cualquier tipo de datos. A diferencia de muchos otros idiomas, no tiene que decirle a JavaScript durante la declaración de variables qué tipo de valor tendrá la variable. El tipo de valor de una variable puede cambiar durante la ejecución de un programa y JavaScript se encarga de ello automáticamente.

## Alcance de Variables en JavaScript 

El alcance de una variable es la región en la que se define. Las variables de JavaScript tienen solo dos ámbitos.

- **Variables globales**: una variable global tiene un alcance global, lo que significa que puede definirse en cualquier parte de su código JavaScript.

- **Variables locales**: una variable local será visible solo dentro de una función donde está definida. Los parámetros de función son siempre locales a esa función.

Dentro del cuerpo de una función, una variable local tiene prioridad sobre una variable global con el mismo nombre. Si declara una variable local o un parámetro de función con el mismo nombre que una variable global, se oculta la variable global. Echa un vistazo al siguiente ejemplo.

```html
<html>
   <body onload = checkscope();>   
      <script type = "text/javascript">
         <!--
            var myVar = "global";      // Declare a global variable
            function checkscope( ) {
               var myVar = "local";    // Declare a local variable
               document.write(myVar);
            }
         //-->
      </script>     
   </body>
</html>
```

Esto produce el siguiente resultado:

```html
local
```

## Nombres de variables en JavaScript

Al nombrar variables en JavaScript, tenga en cuenta las siguientes reglas.

- No utilizar ninguna de las palabras clave reservadas de JavaScript como variable. Estas palabras clave se mencionan en la siguiente sección. Por ejemplo, los nombres de variable `break` o `boolean` no son válidos.

- Los nombres de variables en JavaScript no deben comenzar con un número (0-9). Deben comenzar con una letra o un carácter de subrayado. Por ejemplo, `123test` es un nombre de variable no válido pero `_123test` es válido.

- Los nombres de variables en JavaScript distinguen entre mayúsculas y minúsculas. Por ejemplo, `Nombre` y `nombre` son  variables diferentes.

## Palabras reservadas en JavaScript

En la siguiente tabla se proporciona una lista de palabras reservadas en JavaScript. No se pueden utilizar en nombres de variables, funciones, métodos, etiquetas de bucle o nombres de objetos de JavaScript.

| abstract | else | instanceof | switch |  
|---------|--------|----------|--------|
| boolean| enum | int | synchronized |   
| break | export  | interface  | this  |   
| byte  |  extends | long  | throw  |   
| case | false  | native | throws  |   
| catch  | final  | new  | transient  |   
| char  | finally  | null  | true  |   
| class | float  | package  |  try |   
| const  | for  | private  | typeof  |   
| continue  | function  | protected  | var  |   
| debugger  | goto  | public  | void  |   
| default  | if  | return  | volatile  |   
| delete  | implements  | short  | while  |   
| do  | import  | static  | with  |   
| double  | in  | super  |   |   

### Contacto

- Envienos sus comentarios al correo `henrytorrespo@yahoo.com`
