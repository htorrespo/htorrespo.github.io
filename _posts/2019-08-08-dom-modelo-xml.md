---
title: DOM - Modelo XML
description: XML es un lenguaje de marcado similar a HTML. Significa Extensible Markup Language (Lenguaje de Marcado Extensible) y es una especificacion de W3C como lenguaje de marcado de proposito general.
categories: 
  - Blog
  - Javascript
comments: true
---

Ahora que sabemos lo que significa DOM, veamos que es una estructura DOM. Un documento DOM es una coleccion de nodos o piezas de informacion, organizadas en una jerarquia. Algunos tipos de nodos pueden tener nodos secundarios de varios tipos y otros son nodos hoja que no pueden tener nada debajo de ellos en la estructura del documento. A continuacion se incluye una lista de los tipos de nodos, con una lista de los tipos de nodos que pueden tener como hijos:



- **Document** − Element (maximo uno), ProcessingInstruction, Comment, DocumentType (maximo uno)

- **DocumentFragment** − Element, ProcessingInstruction, Comment, Text, CDATASection, EntityReference

- **EntityReference** − Element, ProcessingInstruction, Comment, Text, CDATASection, EntityReference

- **Element** − Element, Text, Comment, ProcessingInstruction, CDATASection, EntityReference

- **Attr** − Text, EntityReference

- **ProcessingInstruction** − Sin hijos

- **Comment** − Sin hijos

- **Text** − Sin hijos

- **CDATASection** − Sin hijos

- **Entity** − Element, ProcessingInstruction, Comment, Text, CDATASection, EntityReference

- **Notation** − Sin hijos

#### Ejemplo

Considere la representacion DOM del siguiente documento XML `node.xml`.

```xml
<?xml version = "1.0"?>
<Company>
   <Employee category = "technical">
      <FirstName>Tanmay</FirstName>
      <LastName>Patil</LastName>
      <ContactNo>1234567890</ContactNo>
   </Employee>
   
   <Employee category = "non-technical">
      <FirstName>Taniya</FirstName>
      <LastName>Mishra</LastName>
      <ContactNo>1234667898</ContactNo>
   </Employee>
</Company>
```
El DOM del documento XML anterior seria el siguiente:

- El objeto *node* solo puede tener un objeto *node padre*. Esto ocupa la posicion sobre todos los nodos. Aqui esta la *comapny*.

- El *node padre* puede tener multiples nodos llamados *node child*. Estos nodos hijos pueden tener nodos adicionales llamados nodos de *attribute*. En el ejemplo anterior, tenemos dos nodos atributos *Technical* y *Non-Technical*. El nodo de atributo no es en este momento un elemento hijo del elemento *node*, pero aun esta asociado con el.

- Estos nodos hijos a su vez pueden tener multiples nodos hijos. El texto dentro de los nodos se llama nodo *text*.

- Los objetos de nodo en el mismo nivel se llaman hermanos.

El DOM identifica -

- los objetos para representar la interfaz y manipular el documento.

- La relacion entre los objetos y las interfaces.

### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
