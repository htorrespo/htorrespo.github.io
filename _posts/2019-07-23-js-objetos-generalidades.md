---
title: JavaScript - Generalidades de los Objetos
description: JavaScript es un lenguaje de programacion orientada a objetos (OOP).
categories: Blog
comments: true
---

JavaScript es un lenguaje de programacion orientada a objetos (OOP). Un lenguaje de programacion puede denominarse orientado a objetos si proporciona cuatro capacidades basicas a los desarrolladores:

- **Encapsulacion**: la capacidad de almacenar informacion relacionada, ya sea en datos o metodos, ambos en un objeto.

- **Agregacion**: la capacidad de almacenar un objeto dentro de otro objeto.

- **Herencia**: la capacidad de una clase de confiar en otra clase (o numero de clases) para algunas de sus propiedades y metodos.

- **Polimorfismo**: la capacidad de escribir una funcion o metodo que funciona de diferentes maneras.

Los objetos estan compuestos de atributos. Si un atributo contiene una funcion, se considera un metodo del objeto, de lo contrario el atributo se considera una propiedad.

### Propiedades de los objetos

Las propiedades de los objetos pueden ser cualquiera de los tres tipos de datos primitivos, o cualquiera de los tipos de datos abstractos, como otro objeto. Las propiedades de los objetos suelen ser variables que se utilizan internamente en los metodos del objeto, pero tambien pueden ser variables visibles a nivel global que se utilizan en toda la pagina.

La sintaxis para agregar una propiedad a un objeto es:

```JavaScript
objectName.objectProperty = propertyValue;
```

Por ejemplo: el siguiente codigo obtiene el titulo del documento usando la propiedad `title` del objeto del documento.


```JavaScript
var str = document.title;
```

### Metodos de los objetos

Los métodos son funciones que permiten que el objeto haga algo o que se le haga algo. Hay una pequeña diferencia entre una funcion y un metodo: una funcion es una unidad independiente de sentencias y un metodo esta ligado a objeto al que se puede hacer referencia con la palabra clave.

Los metodos son utiles para todo, desde mostrar el contenido del objeto a la pantalla hasta realizar operaciones matematicas complejas a un grupo de propiedades y parametros locales.

Por ejemplo, el siguiente es un ejemplo simple para mostrar como usar el metodo `write()` del objeto `document` para escribir cualquier contenido en el documento.

```JavaScript
document.write("This is test");
```

### Objetos definidos por el usuario

Todos los objetos definidos por el usuario y los objetos incorporados son descendientes de un objeto llamado `Object`.

#### El operador `new`

El operador `new` se utiliza para crear una instancia (objeto) de un objeto. Para crear un objeto, el operador `new` es seguido por el metodo del constructor.

En el siguiente ejemplo, los metodos del constructor son `Object()`, `Array()` y `Date()`. Estos constructores estan incorporados en las funciones de JavaScript.

```JavaScript
var employee = new Object();
var books = new Array("C++", "Perl", "Java");
var day = new Date("August 15, 1947");
```

#### El Constructor `Object()`

Un constructor es una funcion que crea e inicializa un objeto. JavaScript proporciona una funcion constructora especial llamada `Object()` para construir el objeto. El valor de retorno del constructor`Object()` se asigna a una variable.

La variable contiene una referencia al nuevo objeto. Las propiedades asignadas al objeto no son variables y no se definen con la palabra clave `var`.

#### Ejemplo 1

Pruebe el siguiente ejemplo; Demuestra como crear un objeto.

```JavaScript
<html>
   <head>
      <title>User-defined objects</title>     
      <script type = "text/javascript">
         var book = new Object();   // Create the object
         book.subject = "Perl";     // Assign properties to the object
         book.author  = "Mohtashim";
      </script>      
   </head>
   
   <body>  
      <script type = "text/javascript">
         document.write("Book name is : " + book.subject + "<br>");
         document.write("Book author is : " + book.author + "<br>");
      </script>   
   </body>
</html>
```

#### Ejemplo 2

Este ejemplo muestra como crear un objeto con una funcion definida por el usuario. Aqui esta palabra clave se utiliza para referirse al objeto que se ha pasado a una funcion.

```JavaScript
<html>
   <head>   
   <title>User-defined objects</title>
      <script type = "text/javascript">
         function book(title, author) {
            this.title = title; 
            this.author  = author;
         }
      </script>      
   </head>
   
   <body>   
      <script type = "text/javascript">
         var myBook = new book("Perl", "Mohtashim");
         document.write("Book title is : " + myBook.title + "<br>");
         document.write("Book author is : " + myBook.author + "<br>");
      </script>      
   </body>
</html>
```

### Definiendo metodos para un objeto

Los ejemplos anteriores demuestran como el constructor crea el objeto y asigna propiedades. Pero necesitamos completar la definicion de un objeto asignandole matodos.

#### Ejemplo

Pruebe el siguiente ejemplo; muestra como agregar una funcion a un objeto.

```JavaScript
<html>
   
   <head>
   <title>User-defined objects</title>
      <script type = "text/javascript">
         // Define a function which will work as a method
         function addPrice(amount) {
            this.price = amount; 
         }
         
         function book(title, author) {
            this.title = title;
            this.author  = author;
            this.addPrice = addPrice;  // Assign that method as property.
         }
      </script>      
   </head>
   
   <body>   
      <script type = "text/javascript">
         var myBook = new book("Perl", "Mohtashim");
         myBook.addPrice(100);
         
         document.write("Book title is : " + myBook.title + "<br>");
         document.write("Book author is : " + myBook.author + "<br>");
         document.write("Book price is : " + myBook.price + "<br>");
      </script>      
   </body>
</html>
```

### La palabra clave `with`

La palabra clave `with`se utiliza como una forma abreviada para hacer referencia a las propiedades o métodos de un objeto.

El objeto especificado como argumento `with` se convierte en el objeto predeterminado para el bloque siguiente. Las propiedades y los metodos para el objeto se pueden usar sin nombrar el objeto.

#### Sintaxis

La sintaxis para con objeto es la siguiente:

```JavaScript
with (object) {
   properties used without the object name and dot
}
```

#### Ejemplo

Prueba el siguiente ejemplo.

```JavaScript
<html>
   <head>
   <title>User-defined objects</title>   
      <script type = "text/javascript">
         // Define a function which will work as a method
         function addPrice(amount) {
            with(this) {
               price = amount;
            }
         }
         function book(title, author) {
            this.title = title;
            this.author = author;
            this.price = 0;
            this.addPrice = addPrice;  // Assign that method as property.
         }
      </script>      
   </head>
   
   <body>   
      <script type = "text/javascript">
         var myBook = new book("Perl", "Mohtashim");
         myBook.addPrice(100);
         
         document.write("Book title is : " + myBook.title + "<br>");
         document.write("Book author is : " + myBook.author + "<br>");
         document.write("Book price is : " + myBook.price + "<br>");
      </script>      
   </body>
</html>
```

### Objetos nativos de JavaScript

JavaScript tiene varios objetos incorporados o nativos. Estos objetos son accesibles en cualquier parte de su programa y funcionaran de la misma manera en cualquier navegador que se ejecute en cualquier sistema operativo.

Aqui esta la lista de todos los objetos nativos de JavaScript importantes:

- Objeto `Number` de JavaScript

- Objeto `Boolean` de JavaScript

- Objeto `String` de JavaScript

- Objeto `Array` de JavaScript

- Objeto `Date` de JavaScript

- Objeto `Math` de JavaScript

- Objeto `RegExp` de JavaScript
	

### Contacto

- Envia Tus comentarios al correo `henrytorrespo@yahoo.com`
