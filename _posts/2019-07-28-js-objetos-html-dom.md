---
title: JavaScript - HTML DOM
description: DOM permite a los programadores web acceder y manipular las páginas XHTML como si fueran documentos XML.  
categories: Blog
comments: true
---

Cada pagina web reside dentro de una ventana del navegador que puede considerarse como un objeto.

Un objeto documento representa al documento HTML que se muestra en esa ventana. El objeto documento tiene varias propiedades que se refieren a otros objetos que permiten el acceso y la modificación del contenido del documento.

La forma en que se accede y modifica el contenido de un documento se denomina Modelo de Objeto Documento, o DOM. Los objetos están organizados en una jerarquía. Esta estructura jerarquica se aplica a la organización de objetos en un documento web.

- Objeto ventana - Inicio de la jerarquia. Es el elemento mas externo de la jerarquía de objetos.

- Objeto documento: cada documento HTML que se carga en una ventana se convierte en un objeto documento. El documento contiene los contenidos de la pagina.

- Objeto Formulario: todo lo que se incluye en las etiquetas `<form> ... </form>` corresponde al objeto Formulario.

- Elementos de control de formulario: el objeto Formulario contiene todos los elementos definidos para ese objeto, como campos de texto, botones, botones de opcion y casillas de verificacion.

Existen varios modelos DOM

- El DOM Lejendario: este es el modelo que se introdujo en las primeras versiones del lenguaje JavaScript. Es compatible con todos los navegadores, pero permite el acceso solo a ciertas partes clave de los documentos, como formularios, elementos de formulario e imagenes.

- W3C DOM: este modelo de objeto documento permite el acceso y  modificacion de todo el contenido del documento y esta estandarizado por el World Wide Web Consortium (W3C). Este modelo es compatible con casi todos los navegadores modernos.

- El DOM de IE4: este modelo de objeto documento se introdujo en la Versión 4 del navegador Internet Explorer de Microsoft. IE 5 y las versiones posteriores incluyen soporte para la mayoría de las funciones basicas de W3C DOM.

### Compatibilidad DOM

Si desea escribir un script con la flexibilidad de usar W3C DOM o IE 4 DOM segun su disponibilidad, entonces puede usar un enfoque de prueba de capacidad que primero verifique la existencia de un metodo o propiedad para determinar si el navegador tiene La capacidad que deseas. Por ejemplo

```JavaScript
if (document.getElementById) {
   // If the W3C method exists, use it
} else if (document.all) {
   // If the all[] array exists, use it
} else {
   // Otherwise use the legacy DOM
}
```

{% comment%}

Referencia DOM de Gecko: se ve completo
https://developer.mozilla.org/es/docs/Referencia_DOM_de_Gecko

Introduccion a la manipulacion de DOM  conjavaScript
http://www.maestrosdelweb.com/dom/

Elementos DOM
https://lenguajejs.com/p/javascript/caracteristicas/elementos-dom

{% endcomment%}

### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
