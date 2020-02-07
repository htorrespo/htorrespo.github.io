---
title: JavaScript - Sentencia for...in
description: La sentencia for...in itera sobre todos los elementos de un objeto, en un orden arbitrario. Para cada uno de los elementos, se ejecuta la sentencia especificada.
categories: Blog
comments: true
---

El bucle `for ... in` se utiliza para recorrer las propiedades de un objeto. Como no hemos discutido Objetos todavía, puede que no se sienta cómodo con este bucle. Pero una vez que entienda como se comportan los objetos en JavaScript, encontrara este bucle muy util.

#### Sintaxis

La sintaxis de un bucle `for...in` es la siguiente:

```javascript
for (variablename in object) {
   statement or block to execute
}
```

En cada iteración, una propiedad del objeto se asigna a `variablename` y este bucle continúa hasta que se agotan todas las propiedades del objeto.


#### Ejemplo

Pruebe el siguiente ejemplo para implementar el bucle `for...in`. Imprime el objeto Navigator del navegador web.

```html
<html>
   <body>      
      <script type = "text/javascript">
         <!--
            var aProperty;
            document.write("Navigator Object Properties<br /> ");        
            for (aProperty in navigator) {
               document.write(aProperty);
               document.write("<br />");
            }
            document.write ("Exiting from the loop!");
         //-->
      </script>      
      <p>Set the variable to different object and then try...</p>
   </body>
</html>
```

### Contacto

- Envienos sus comentarios al correo `henrytorrespo@yahoo.com`
