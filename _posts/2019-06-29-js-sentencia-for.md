---
title: JavaScript - Sentencia for
description: Crea un bucle que consiste en tres expresiones opcionales, encerradas en parentesis y separadas por puntos y comas, seguidas de una sentencia ejecutada en un bucle. 
categories: Blog
comments: true
---

El bucle `for` es la forma más compacta de bucle. Incluye las siguientes tres partes importantes:

- La **inicializacion** del bucle donde empezamos con nuestro contador a un valor de inicio. La instruccion de inicializacion se ejecuta antes de que comience el bucle.

- La **declaracion** de prueba que verificara si una condicion dada es verdadera o no. Si la condicion es verdadera, entonces el codigo dado dentro del bucle se ejecutara, de lo contrario, el control saldra del bucle.

- La instruccion de **iteracion** donde puede aumentar o disminuir su contador.

Puede poner las tres partes en una sola línea separadas por punto y coma.


#### Sintaxis

La sintaxis de una instruccion `for` basica es la siguiente:

```javascript
for (initialization; test condition; iteration statement) {
   Statement(s) to be executed if test condition is true
}
```

#### Ejemplo

Pruebe el siguiente ejemplo para comprender como funciona la instruccion `for`.

```html
<html>
   <body>      
      <script type = "text/javascript">
         <!--
            var count;
            document.write("Starting Loop" + "<br />");
         
            for(count = 0; count < 10; count++) {
               document.write("Current Count : " + count );
               document.write("<br />");
            }         
            document.write("Loop stopped!");
         //-->
      </script>      
      <p>Set the variable to different value and then try...</p>
   </body>
</html>
```

### Contacto

- Envienos sus comentarios al correo `henrytorrespo@yahoo.com`
