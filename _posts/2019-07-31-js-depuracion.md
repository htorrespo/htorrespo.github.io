---
title: JavaScript - Depuracion
description: La utilizacion de una herramienta de depuracion es esencial para trabajar con JavaScript.
categories: 
  - Blog
  - Javascript
comments: true
---

De vez en cuando, los desarrolladores cometen errores al codificar. Un error en un programa o un script se conoce como error.

El proceso de encontrar y corregir errores se llama depuracion y es una parte normal del proceso de desarrollo. Esta seccion cubre herramientas y tecnicas que pueden ayudarlo con las tareas de depuracion.

### Mensajes de error en IE

La forma mas basica de rastrear errores es activando la informacion de errores en su navegador. De forma predeterminada, Internet Explorer muestra un icono de error en la barra de estado cuando se produce un error en la pagina.

Hacer doble clic en este icono lo lleva a un cuadro de dialogo que muestra informacion sobre el error especifico que ocurrio.

Dado que este icono es facil de pasar por alto, Internet Explorer le ofrece la opcion de mostrar automaticamente el cuadro de dialogo Error cada vez que se produce un error.

Para habilitar esta opcion, seleccione Herramientas > Opciones de Internet > pestaña Avanzado. y, finalmente, marque la opcion del cuadro "Mostrar una notificacion sobre cada error de script".

### Mensajes de error en Firefox o Mozilla

Otros navegadores como Firefox, Netscape y Mozilla envian mensajes de error a una ventana especial llamada JavaScript Console o Error Consol. Para ver la consola, seleccione Herramientas > Consola de errores o Desarrollo web.

Desafortunadamente, dado que estos navegadores no dan indicaciones visuales cuando ocurre un error, debe mantener la consola abierta y observar si hay errores mientras se ejecuta el script.

### Notificaciones de error

Las notificaciones de error que aparecen en la consola o en los cuadros de dialogo de Internet Explorer son el resultado de errores de sintaxis y de tiempo de ejecucion. Estas notificaciones de error incluyen el numero de linea en el que ocurrio el error.

Si esta usando Firefox, puede hacer clic en el error disponible en la consola de error para ir a la linea exacta en el script que tiene el error.

### Como depurar un script

Hay varias formas de depurar tu JavaScript:

#### Utilice un validador de JavaScript

Una forma de verificar si su codigo JavaScript tiene errores extraños es ejecutarlo a traves de un programa que lo verifique para asegurarse de que sea valido y que siga las reglas de sintaxis oficiales del lenguaje. Estos programas se denominan analizadores de validacion o solo validadores para abreviar, y a menudo vienen con editores comerciales de HTML y JavaScript.

El validador mas conveniente para JavaScript es la JavaScript Lint de Douglas Crockford, que esta disponible de forma gratuita en la JavaScript Lint de Douglas Crockford.

Simplemente visite esa pagina web, pegue el codigo JavaScript (solo JavaScript) en el area de texto proporcionada y haga clic en el boton jslint. Este programa analizara el codigo JavaScript, asegurando que todas las definiciones de variables y funciones sigan la sintaxis correcta. Tambien verificara las declaraciones de JavaScript, como `if` y `while`, para asegurarse de que tambien sigan el formato correcto

#### Agregue codigo de depuracion a sus programas

Puede usar los metodos `alert()` o `document.write()` en su programa para depurar el codigo. Por ejemplo, puede escribir algo de la siguiente manera:

```javascript
var debugging = true;
var whichImage = "widget";

if( debugging )
   alert( "Calls swapImage() with argument: " + whichImage );
   var swapStatus = swapImage( whichImage );

if( debugging )
   alert( "Exits swapImage() with swapStatus=" + swapStatus );
```

Al examinar el contenido y orden de `alert()` cuando aparecen, puede examinar la salud de su programa facilmente.

#### Use un depurador JavaScript

Un depurador es una aplicacion que pone todos los aspectos de la ejecucion del script bajo el control del programador. Los depuradores proporcionan un control preciso sobre el estado del script a traves de una interfaz que le permite examinar y establecer valores, asi como controlar el flujo de ejecucion.

Una vez que se ha cargado un script en un depurador, se puede ejecutar una linea a la vez o indicarle que se detenga en ciertos puntos de interrupcion. Una vez que se detiene la ejecucion, el programador puede examinar el estado del script y sus variables para determinar si algo esta mal. Tambien puede ver las variables para ver los cambios en sus valores.

### Consejos utiles para desarrolladores

Puede tener en cuenta los siguientes consejos para reducir la cantidad de errores en sus scripts y simplificar el proceso de depuracion:

- Use muchos comentarios. Los comentarios le permiten explicar por que escribio el script de la manera en que lo hizo y explicar secciones de codigo particularmente dificiles.

- Utilice siempre sangria para que su codigo sea facil de leer. Las instrucciones con sangria tambien facilitan la combinacion de etiquetas iniciales, finales, llaves y otros elementos HTML y de script.

- Escribir codigo modular Siempre que sea posible, agrupe sus declaraciones en funciones. Las funciones le permiten agrupar declaraciones relacionadas y probar y reutilizar partes de codigo con un minimo esfuerzo.

- Sea coherente en la forma en que nombra sus variables y funciones. Intente usar nombres que sean lo suficientemente largos para ser significativos y que describan el contenido de la variable o el proposito de la funcion.

- Utilice una sintaxis coherente al nombrar variables y funciones. En otras palabras, mantengalos todos en minusculas o en mayusculas; si prefiere la notacion del Camello, usela de manera consistente.

- Pruebe guiones largos de forma modular. En otras palabras, no intente escribir el script completo antes de probar cualquier parte del mismo. Escriba una pieza y pongala a trabajar antes de agregar la siguiente porcion de codigo.

- Use nombres descriptivos de variables y funciones y evite usar nombres de un solo caracter.

- Mira tus comillas. Recuerde que las comillas se usan en pares alrededor de las cadenas y que ambas comillas deben ser del mismo estilo (simple o doble).

- Mira tus signos iguales. No debe usar un solo = para fines de comparacion.

- Declare variables explicitamente usando la palabra clave `var`.

### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
