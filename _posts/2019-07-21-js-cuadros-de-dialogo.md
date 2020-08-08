---
title: JavaScript - Cuadros de dialogo
description: Estos cuadros de dialogo se pueden utilizar para activar y alertar, o para obtener confirmacion de cualquier entrada
categories: 
  - Blog
  - Javascript
comments: true
---

JavaScript admite tres tipos importantes de cuadros de dialogo. Estos cuadros de dialogo se pueden utilizar para activar y alertar, o para obtener confirmacion de cualquier entrada o para recibir algun tipo de informacion de los usuarios. Aqui discutiremos cada cuadro de dialogo uno por uno.

### Cuadro de dialogo de alerta

Un cuadro de dialogo de alerta se usa principalmente para dar un mensaje de advertencia a los usuarios. Por ejemplo, si un campo de entrada requiere ingresar algun texto pero el usuario no proporciona ninguna entrada, entonces, como parte de la validacion, puede usar un cuadro de alerta para enviar un mensaje de advertencia.

No obstante, un cuadro de alerta se puede utilizar para mensajes mas amigables. El cuadro de dialogo de alerta solo da un boton "OK" para seleccionar y continuar.

#### Ejemplo

```html
<html>
   <head>   
      <script type = "text/javascript">
         <!--
            function Warn() {
               alert ("This is a warning message!");
               document.write ("This is a warning message!");
            }
         //-->
      </script>     
   </head>
   
   <body>
      <p>Click the following button to see the result: </p>      
      <form>
         <input type = "button" value = "Click Me" onclick = "Warn();" />
      </form>     
   </body>
</html>
```

### Cuadro de dialogo de confirmacion

Un cuadro de dialogo de confirmacion se utiliza principalmente para obtener el consentimiento del usuario en cualquier opcion. Muestra un cuadro de dialogo con dos botones: Aceptar y Cancelar.

Si el usuario hace clic en el boton Aceptar, el metodo de ventana `confirm()` devolvera verdadero. Si el usuario hace clic en el boton Cancelar, `confirm()` devuelve falso. Puede utilizar un cuadro de dialogo de confirmacion de la siguiente manera.

#### Ejemplo

```html
<html>
   <head>   
      <script type = "text/javascript">
         <!--
            function getConfirmation() {
               var retVal = confirm("Do you want to continue ?");
               if( retVal == true ) {
                  document.write ("User wants to continue!");
                  return true;
               } else {
                  document.write ("User does not want to continue!");
                  return false;
               }
            }
         //-->
      </script>     
   </head>
   
   <body>
      <p>Click the following button to see the result: </p>      
      <form>
         <input type = "button" value = "Click Me" onclick = "getConfirmation();" />
      </form>      
   </body>
</html>
```

### Cuadro de dialogo de peticion

El cuadro de dialogo de peticion es muy util cuando desea abrir un cuadro de texto para obtener una entrada del usuario. Por lo tanto, le permite interactuar con el usuario. El usuario debe completar el campo y luego hacer clic en Aceptar.

Este cuadro de dialogo se muestra mediante un metodo llamado `prompt()` que toma dos parametros: (i) una etiqueta que desea mostrar en el cuadro de texto y (ii) una cadena predeterminada para mostrar en el cuadro de texto.

Este cuadro de dialogo tiene dos botones: Aceptar y Cancelar. Si el usuario hace clic en el botón Aceptar, el indicador de metodo de `window()` devolvera el valor ingresado en el cuadro de texto. Si el usuario hace clic en el botón Cancelar, el indicador de metodo de `window()` devuelve un valor nulo.

#### Ejemplo

```html
<html>
   <head>     
      <script type = "text/javascript">
         <!--
            function getValue() {
               var retVal = prompt("Enter your name : ", "your name here");
               document.write("You have entered : " + retVal);
            }
         //-->
      </script>      
   </head>
   
   <body>
      <p>Click the following button to see the result: </p>      
      <form>
         <input type = "button" value = "Click Me" onclick = "getValue();" />
      </form>      
   </body>
</html>
```


### Contacto

- Envia Tus comentarios al correo `henrytorrespo@yahoo.com`
