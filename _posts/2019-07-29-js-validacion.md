---
title: JavaScript - Validacion de formularios
description: La principal utilidad de JavaScript en el manejo de los formularios es la validacion de los datos introducidos por los usuarios.
categories: 
  - Blog
  - Javascript
comments: true
---

La validacion de formularios normalmente se realizaba en el servidor, despues de que el cliente ingresa todos los datos requeridos y luego presiono el boton Enviar. Si los datos ingresados ​​por un cliente eran incorrectos o simplemente faltaban, el servidor tendria que enviar todos los datos al cliente y solicitar que el formulario se vuelva a enviar con la informacion correcta. Este fue realmente un proceso largo que solia poner mucha carga en el servidor.

JavaScript proporciona una forma de validar los datos del formulario en la computadora del cliente antes de enviarlo al servidor web. La validacion de formularios generalmente realiza dos funciones.

- **Validacion basica**: en primer lugar, se debe verificar que completen todos los campos obligatorios. Se requeriria solo un ciclo a traves de cada campo en el formulario y verificar los datos.

- **Validacion de formato de datos**: en segundo lugar, se debe verificar la forma y el valor correctos de los datos ingresados. Su codigo debe incluir la logica apropiada para probar la exactitud de los datos.

#### Ejemplo

Tomaremos un ejemplo para comprender el proceso de validacion. Aqui hay una forma simple en formato html.

```html
<html>   
   <head>
      <title>Form Validation</title>      
      <script type = "text/javascript">
         <!--
            // Form validation code will come here.
         //-->
      </script>      
   </head>
   
   <body>
      <form action = "/cgi-bin/test.cgi" name = "myForm" onsubmit = "return(validate());">
         <table cellspacing = "2" cellpadding = "2" border = "1">
            
            <tr>
               <td align = "right">Name</td>
               <td><input type = "text" name = "Name" /></td>
            </tr>
            
            <tr>
               <td align = "right">EMail</td>
               <td><input type = "text" name = "EMail" /></td>
            </tr>
            
            <tr>
               <td align = "right">Zip Code</td>
               <td><input type = "text" name = "Zip" /></td>
            </tr>
            
            <tr>
               <td align = "right">Country</td>
               <td>
                  <select name = "Country">
                     <option value = "-1" selected>[choose yours]</option>
                     <option value = "1">USA</option>
                     <option value = "2">UK</option>
                     <option value = "3">INDIA</option>
                  </select>
               </td>
            </tr>
            
            <tr>
               <td align = "right"></td>
               <td><input type = "submit" value = "Submit" /></td>
            </tr>
            
         </table>
      </form>      
   </body>
</html>
```

### Validacion basica de formularios

Primero veamos como hacer una validacion basica. En el formulario anterior, estamos llamando a `validate()` para validar datos cuando se produce un evento de envio. El siguiente codigo muestra la implementacion de esta funcion.

```html
<script type = "text/javascript">
   <!--
      // Form validation code will come here.
      function validate() {
      
         if( document.myForm.Name.value == "" ) {
            alert( "Please provide your name!" );
            document.myForm.Name.focus() ;
            return false;
         }
         if( document.myForm.EMail.value == "" ) {
            alert( "Please provide your Email!" );
            document.myForm.EMail.focus() ;
            return false;
         }
         if( document.myForm.Zip.value == "" || isNaN( document.myForm.Zip.value ) ||
            document.myForm.Zip.value.length != 5 ) {
            
            alert( "Please provide a zip in the format #####." );
            document.myForm.Zip.focus() ;
            return false;
         }
         if( document.myForm.Country.value == "-1" ) {
            alert( "Please provide your country!" );
            return false;
         }
         return( true );
      }
   //-->
</script>
```

### Validacion de formato de datos

Ahora veremos como podemos validar nuestros datos ingresados sl formulario ​​antes de enviarlos al servidor web.

El siguiente ejemplo muestra como validar una direccion de correo electronico ingresada. Una direccion de correo electronico debe contener al menos un signo `@`  y un punto (.). Ademas, la `@` no debe ser el primer caracter de la direccion de correo electronico, y el ultimo punto debe ser al menos un caracter despues del signo `@`.

#### Ejemplo

Pruebe el siguiente codigo para la validacion de correo electronico.

```html
<script type = "text/javascript">
   <!--
      function validateEmail() {
         var emailID = document.myForm.EMail.value;
         atpos = emailID.indexOf("@");
         dotpos = emailID.lastIndexOf(".");
         
         if (atpos < 1 || ( dotpos - atpos < 2 )) {
            alert("Please enter correct email ID")
            document.myForm.EMail.focus() ;
            return false;
         }
         return( true );
      }
   //-->
</script>
```

### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
