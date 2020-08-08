---
title: JavaScript - Mapa de imagenes
description: HTML nos permite la opcion de crear diferentes enlaces url dentro de una misma imagen. Es decir, podemos hacer que diferentes partes de una imagen tengan enlaces que nos permitan ir a diferentes destinos
categories: 
  - Blog
  - Javascript
comments: true
---

Puede usar JavaScript para crear un mapa de imagen del lado del cliente. Los mapas de imagenes del lado del cliente estan habilitados por el atributo `usemap` para la etiqueta `<img/>` y definidos por etiquetas especiales de extension `<map>` y `<area>`.

La imagen que va a formar el mapa se inserta en la pagina usando el elemento `<img/>` de forma normal, excepto que lleva un atributo adicional llamado `usemap`. El valor del atributo `usemap` es el valor del atributo de nombre en el elemento `<map>`, que esta a punto de cumplir, precedido por una libra o un signo hash.

El elemento `<map>` en realidad crea el mapa para la imagen y generalmente sigue directamente despues del elemento `<img/>`. Actua como un contenedor para los elementos `<area/>` que realmente definen los puntos de acceso en los que se puede hacer clic. El elemento `<map>` lleva solo un atributo, el atributo `name`, que es el nombre que identifica el mapa. Asi es como el elemento `<img/>` sabe que elemento `<map>` usar.

El elemento `<area>` especifica la forma y las coordenadas que definen los limites de cada punto de acceso en el que se puede hacer clic.

El siguiente codigo combina mapas de imagenes y JavaScript para producir un mensaje en un cuadro de texto cuando el mouse se mueve sobre diferentes partes de una imagen.

```html
<html>   
   <head>
      <title>Using JavaScript Image Map</title>
      
      <script type = "text/javascript">
         <!--
            function showTutorial(name) {
               document.myform.stage.value = name
            }
         //-->
      </script>
   </head>
   
   <body>
      <form name = "myform">
         <input type = "text" name = "stage" size = "20" />
      </form>
      
      <!-- Create  Mappings -->
      <img src = "/images/usemap.gif" alt = "HTML Map" border = "0" usemap = "#tutorials"/>
      
      <map name = "tutorials">
         <area shape="poly" 
            coords = "74,0,113,29,98,72,52,72,38,27"
            href = "/perl/index.htm" alt = "Perl Tutorial"
            target = "_self" 
            onMouseOver = "showTutorial('perl')" 
            onMouseOut = "showTutorial('')"/>
         
         <area shape = "rect" 
            coords = "22,83,126,125"
            href = "/html/index.htm" alt = "HTML Tutorial" 
            target = "_self" 
            onMouseOver = "showTutorial('html')" 
            onMouseOut = "showTutorial('')"/>
         
         <area shape = "circle" 
            coords = "73,168,32"
            href = "/php/index.htm" alt = "PHP Tutorial"
            target = "_self" 
            onMouseOver = "showTutorial('php')" 
            onMouseOut = "showTutorial('')"/>
      </map>
   </body>
</html>
```

### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
