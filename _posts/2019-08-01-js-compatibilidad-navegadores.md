---
title: JavaScript - Compatibilidad de Navegadores
description: Los desarrolladores deben tener claro desde el principio que a pesar de la supuesta compatibilidad entre navegadores, JavaScript es interpretado de modo diferente segun sea el navegador utilizado. 
categories: Blog
comments: true
---

Es importante comprender las diferencias entre los diferentes navegadores para manejar cada uno de la forma en que se espera. Por lo tanto, es importante saber en que navegador se esta ejecutando su pagina web.

Para obtener informacion sobre el navegador en el que se ejecuta actualmente su pagina web, use el objeto incorporado `navegator`.

### Propiedades del navegador

Existen varias propiedades relacionadas con el navegador que puede usar en su pagina web. La siguiente es una lista de los nombres y descripciones de cada uno.

| Sr.No. |	Propiedad & Descripcion  |
|--------|---------------------------|
| 1      | `appCodeName`             |
|        | Esta propiedad es una cadena de caracteres que contiene el nombre navegador, Netscape para Netscape y Microsoft Internet Explorer para Internet Explorer. |
| 2      | `appVersion`              |
|        | Esta propiedad es una cadena cadena de caracteres que contiene la version del navegador, su idioma y compatibilidad. |
| 3      | `language`                |
|        | Esta propiedad contiene la abreviatura de dos letras para el idioma que utiliza el navegador. Solo Netscape. |
| 4      | `mimTypes[]`              |
|        | Esta propiedad es una matriz que contiene todos los tipos MIME admitidos por el cliente. Solo Netscape. |
| 5      | `platform[]`              |
|        | Esta propiedad es una cadena de caracteres que contiene la plataforma para la cual se compilo el navegador. |
| 6      | `plugins[]`               |
|        | Esta propiedad es una matriz que contiene todos los complementos que se han instalado en el cliente. Solo Netscape. |
| 7      | `userAgent[]`             |
|        | Esta propiedad es una cadena de caracteres que contiene el nombre del codigo y la version del navegador. Este valor se envia al servidor de origen para identificar al cliente. |

### Metodos de navegador

Existen varios metodos especificos del navegador. Aqui hay una lista de sus nombres y descripciones.

| Sr.No. |	      Descripcion        |
|--------|---------------------------|
| 1      | `javaEnabled()`           |
|        | Este metodo determina si JavaScript esta habilitado en el cliente. Si JavaScript esta habilitado, este metodo devuelve verdadero; de lo contrario, devuelve falso. |
| 2      | `plugings.refresh`        |
|        | Este metodo hace que los complementos recien instalados esten disponibles y llena la matriz de complementos con todos los nuevos nombres de complementos. Solo Netscape. |
| 3      | `preference(name,value)`  |
|        | Este metodo permite que un script firmado obtenga y establezca algunas preferencias de Netscape. Si se omite el segundo parametro, este metodo devolvera el valor de la preferencia especificada; de lo contrario, establece el valor. Solo Netscape. |
| 4      | `taintEnabled()`          |
|        | Este metodo devuelve verdadero si la contaminacion de datos esta habilitada; de lo contrario falso. |

### Deteccion de navegador

Hay un JavaScript simple que se puede utilizar para averiguar el nombre de un navegador y, en consecuencia, se puede servir una pagina HTML al usuario.

```html
<html>   
   <head>
      <title>Browser Detection Example</title>
   </head>
   
   <body>      
      <script type = "text/javascript">
         <!--
            var userAgent   = navigator.userAgent;
            var opera       = (userAgent.indexOf('Opera') != -1);
            var ie          = (userAgent.indexOf('MSIE') != -1);
            var gecko       = (userAgent.indexOf('Gecko') != -1);
            var netscape    = (userAgent.indexOf('Mozilla') != -1);
            var version     = navigator.appVersion;
            
            if (opera) {
               document.write("Opera based browser");
               // Keep your opera specific URL here.
            } else if (gecko) {
               document.write("Mozilla based browser");
               // Keep your gecko specific URL here.
            } else if (ie) {
               document.write("IE based browser");
               // Keep your IE specific URL here.
            } else if (netscape) {
               document.write("Netscape based browser");
               // Keep your Netscape specific URL here.
            } else {
               document.write("Unknown browser");
            }
            
            // You can include version to along with any above condition.
            document.write("<br /> Browser version info : " + version );
         //-->
      </script>      
   </body>
</html>
```

### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
