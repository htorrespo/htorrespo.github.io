---
title: JavaScript - Multimedia
description: El objeto navigator de  JavaScript incluye un objeto hijo que se llama complementos. Este objeto es basicamente una matriz, con una entrada para cada complemento instalado en el navegador.
categories: 
  - Blog
  - Javascript
comments: true
---

El objeto `navigator` de JavaScript incluye un objeto hijo llamado `plugins`. Este objeto es una matriz, con una entrada para cada complemento  o plugin instalado en el navegador. El objeto `navigator.plugins` solo es compatible con Netscape, Firefox y Mozilla unicamente.

#### Ejemplo

Aqui hay un ejemplo que muestra como enumerar todos los complementos instalados en su navegador:

```html
<html>
   <head>
      <title>List of Plug-Ins</title>
   </head>
   
   <body>
      <table border = "1">
         <tr>
            <th>Plug-in Name</th>
            <th>Filename</th>
            <th>Description</th>
         </tr>
         
         <script language = "JavaScript" type = "text/javascript">
            for (i = 0; i<navigator.plugins.length; i++) {
               document.write("<tr><td>");
               document.write(navigator.plugins[i].name);
               document.write("</td><td>");
               document.write(navigator.plugins[i].filename);
               document.write("</td><td>");
               document.write(navigator.plugins[i].description);
               document.write("</td></tr>");
            }
         </script>
      </table>      
   </body>
</html>
```

### Comprobacion de complementos

Cada complemento tiene una entrada en la matriz. Cada entrada tiene las siguientes propiedades:

- **name**: es el nombre del complemento.

- **filename**: es el archivo ejecutable que se cargo para instalar el complemento.

- **description**: es una descripcion del complemento, suministrado por el desarrollador.

- **mimeTypes**: es una matriz con una entrada para cada tipo MIME admitido por el complemento.

Puede usar estas propiedades en una secuencia de comandos para descubrir los complementos instalados, y luego, usando JavaScript, puede reproducir el archivo multimedia apropiado. Eche un vistazo al siguiente ejemplo.

```html
<html>   
   <head>
      <title>Using Plug-Ins</title>
   </head>
   
   <body>   
      <script language = "JavaScript" type = "text/javascript">
         media = navigator.mimeTypes["video/quicktime"];
         
         if (media) {
            document.write("<embed src = 'quick.mov' height = 100 width = 100>");
         } else {
            document.write("<img src = 'quick.gif' height = 100 width = 100>");
         }
      </script>      
   </body>
</html>
```

NOTA - Aqui estamos usando la etiqueta HTML `<embed>` para insertar un archivo multimedia.

### Control de multimedia

Tomemos un ejemplo real que funciona en casi todos los navegadores:

```html
<html>   
   <head>
      <title>Using Embeded Object</title>
      
      <script type = "text/javascript">
         <!--
            function play() {
               if (!document.demo.IsPlaying()) {
                  document.demo.Play();
               }
            }
            function stop() {
               if (document.demo.IsPlaying()) {
                  document.demo.StopPlay();
               }
            }
            function rewind() {
               if (document.demo.IsPlaying()) {
                  document.demo.StopPlay();
               }
               document.demo.Rewind();
            }
         //-->
      </script>
   </head>
   
   <body>      
      <embed id = "demo" name = "demo"
         src = "http://www.amrood.com/games/kumite.swf"
         width = "318" height = "300" play = "false" loop = "false"
         pluginspage = "http://www.macromedia.com/go/getflashplayer"
         swliveconnect = "true">
      
      <form name = "form" id = "form" action = "#" method = "get">
         <input type = "button" value = "Start" onclick = "play();" />
         <input type = "button" value = "Stop" onclick = "stop();" />
         <input type = "button" value = "Rewind" onclick = "rewind();" />
      </form>      
   </body>
</html>
```

### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
