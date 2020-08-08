---
title: Groovy - Sintaxis basica
description: Para comprender la sintaxis basica de Groovy, veamos primero un programa simple de Hello World.
categories: 
  - Blog
  - Groovy
comments: true
---

### Creando tu primer programa Hello World

Crear su primer programa `hello world` es tan simple como ingresar la siguiente linea de codigo:

```groovy
class Example {
   static void main(String[] args) {
      // Usando una declaracion println para imprimir la salida a la consola
      println('Hello World');
   }
}
```

### Declaracion de importacion en Groovy

La declaracion `import` se puede usar para importar la funcionalidad de otras bibliotecas  en su codigo. Esto se hace usando la palabra clave `import`.

El siguiente ejemplo muestra como usar importacion simple de la clase `MarkupBuilder`, que es probablemente una de las clases mas utilizadas para crear marcado HTML o XML.

```groovy
import groovy.xml.MarkupBuilder 
def xml = new MarkupBuilder() 
```

De forma predeterminada, Groovy incluye las siguientes bibliotecas en su codigo, por lo que no necesita importarlas explicitamente.

```groovy
import java.lang.* 
import java.util.* 
import java.io.* 
import java.net.* 

import groovy.lang.* 
import groovy.util.* 

import java.math.BigInteger 
import java.math.BigDecimal
```

### Tokens en Groovy

Un token es una palabra clave, un identificador, una constante, un literal de cadena o un simbolo.

```groovy
println(“Hello World”);
```

En la linea de codigo anterior, hay dos tokens, el primero es la palabra clave println y el siguiente es el string "Hello World".

### Comentarios en Groovy

Los comentarios se utilizan para documentar codigo. Los comentarios en Groovy pueden ser de una sola linea o de varias lineas.

Los comentarios de una sola linea se identifican utilizando `//` en cualquier posicion de la linea. A continuacion se muestra un ejemplo:

```groovy
class Example {
   static void main(String[] args) {
      // Usando una declaracion println para imprimir la salida a la consola
      println('Hello World');
   }
}
```

Los comentarios multilinea se identifican con `/*` al principio y `*/` para identificar el final del comentario multilinea.

```groovy
class Example {
   static void main(String[] args) {
      /* Este programa es el primer programa
       Este programa muestra como mostrar hello world */
      println('Hello World');
   }
}
```

### Punto y coma

Al igual que el lenguaje de programacion Java, se requiere tener punto y coma para distinguir entre declaraciones multiples en Groovy.

```groovy
class Example {
   static void main(String[] args) {
      // Se puede ver el uso de un punto y coma despues de cada declaracion
      def x = 5;
      println('Hello World');  
   }
}
```

El ejemplo anterior muestra puntos y comas que se utilizan para distinguir entre diferentes lineas de sentencias de codigo.

### Identificadores

Los identificadores se utilizan para definir variables, funciones u otras variables definidas por el usuario. Los identificadores comienzan con una letra, un dolar o un guion bajo. No pueden comenzar con un numero. Aqui hay algunos ejemplos de identificadores validos:

```groovy
def employeename 
def student1 
def student_name
```

donde `def` es una palabra clave utilizada en Groovy para definir un identificador.

Aqui hay un ejemplo de codigo de como se puede usar un identificador en nuestro programa Hello World.

```groovy
class Example {
   static void main(String[] args) {
      // Se puede ver el uso de un punto y coma despues de cada declaracion
      def x = 5;
      println('Hello World'); 
   }
}
```

En el ejemplo anterior, la variable x se usa como identificador.

### Palabras clave

Las palabras clave como su nombre indica son palabras especiales que estan reservadas en el lenguaje de programacion Groovy. La siguiente tabla enumera las palabras clave que se definen en Groovy.

```terminal
as      assert     break       case
catch   class     const        continue
def     default   do           else
enum    extends   false        Finally
for     goto      if           implements
import  in        instanceof   interface
new     pull      package      return
super   switch    this         throw
throws  trait     true         try
while 
```

### Espacios en blanco

Espacio en blanco es el termino utilizado en un lenguaje de programacion como Java y Groovy para describir espacios en blanco, tabs, caracteres de nueva linea y comentarios. El espacio en blanco separa una parte de una declaracion de otra y permite al compilador identificar donde esta un elemento en una declaracion.

Por ejemplo, en el siguiente ejemplo, hay un espacio en blanco entre la palabra clave `def` y la variable `x`. Esto es para que el compilador sepa que `def` es la palabra clave que debe usarse y que `x` debe ser el nombre de la variable que debe definirse.

```groovy
def x = 5;
```

### Literales

Un literal es una notacion empleada para representar un valor fijo en groovy. El lenguaje groovy tiene anotaciones para enteros, numeros de coma flotante, caracteres y cadenas. Estos son algunos ejemplos de literales en el lenguaje de programacion Groovy:

```groovy
12 
1.45 
‘a’ 
“aa”
```

### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
