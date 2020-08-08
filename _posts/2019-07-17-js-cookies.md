---
title: JavaScript - Cookies
description: Una cookie es un archivo creado por un sitio web que contiene pequeñas cantidades de datos y que se envian entre un emisor y un receptor.
categories: 
  - Blog
  - Javascript
comments: true
---

### Que son las cookies?

Los navegadores y servidores web utilizan el protocolo HTTP para comunicarse, pero HTTP es un protocolo sin estado. Sin embargo, para un sitio web comercial, se requiere conservar informacion de la sesion entre diferentes paginas para mejorar la experiencia del usuario. Por ejemplo, un registro de usuario finaliza despues de completar muchas paginas. Pero como mantener la informacion de sesion de los usuarios en todas las paginas web.

En muchas situaciones, el uso de cookies es el metodo mas eficaz para recordar y rastrear preferencias, compras, comisiones y otra informacion requerida para una mejor experiencia del visitante o estadisticas del sitio.

### Como funciona?

Su servidor envia algunos datos al navegador del visitante en forma de una cookie. El navegador puede aceptar la cookie. Si lo hace, se almacena como un registro de texto sin formato en el disco duro del visitante. Ahora, cuando el visitante llega a otra pagina de su sitio, el navegador envia la misma cookie al servidor para su recuperacion. Una vez recuperado, su servidor sabe / recuerda lo que se almaceno anteriormente.

Las cookies son un registro de datos de texto sin formato de 5 campos de longitud variable:

- `Expires`: fecha en que caducara la cookie. Si esta en blanco, la cookie caducara cuando el visitante salga del navegador.

- `Domain`: nombre de dominio de su sitio.

- `Path`: ruta al directorio o pagina web que establece la cookie. Puede estar en blanco si desea recuperar la cookie de cualquier directorio o pagina.

- `Secure`: si este campo contiene la palabra `secure`, la cookie solo se puede recuperar con un servidor seguro. Si este campo esta en blanco, no existe tal restriccion.

- `Name = Value`: las cookies se configuran y recuperan en forma de pares clave-valor

Las cookies fueron diseñadas originalmente para programacion CGI. Los datos contenidos en una cookie se transmiten automaticamente entre el navegador web y el servidor web, por lo que los scripts CGI en el servidor pueden leer y escribir los valores de las cookies que se almacenan en el cliente.

JavaScript tambien puede manipular las cookies utilizando la propiedad `cookie` del objeto `Document`. JavaScript puede leer, crear, modificar y eliminar las cookies que se aplican a la pagina web actual.

### Almacenamiento de cookies

La forma mas sencilla de crear una cookie es asignar un valor de cadena de caracteres al objeto `document.cookie`, que se ve asi.

```javascript
document.cookie = "key1 = value1;key2 = value2;expires = date";
```

Aqui el atributo `expires` es opcional. Si entrega este atributo con una fecha u hora validas, la cookie caducara en una fecha u hora determinada y, posteriormente, el valor de las cookies no sera accesible.

Nota: los valores de las cookies no pueden incluir puntos y comas, ni espacios en blanco. Por este motivo, es posible que desee utilizar la funcion `escape()` de JavaScript para codificar el valor antes de almacenarlo en la cookie. Si lo hace, tambien tendra que usar la funcion `unescape()` correspondiente cuando lea el valor de la cookie.

#### Ejemplo

Intenta lo siguiente. Asigna un nombre de cliente a una cookie de entrada.

```html
<html>
   <head>   
      <script type = "text/javascript">
         <!--
            function WriteCookie() {
               if( document.myform.customer.value == "" ) {
                  alert("Enter some value!");
                  return;
               }
               cookievalue = escape(document.myform.customer.value) + ";";
               document.cookie = "name=" + cookievalue;
               document.write ("Setting Cookies : " + "name=" + cookievalue );
            }
         //-->
      </script>      
   </head>
   
   <body>      
      <form name = "myform" action = "">
         Enter name: <input type = "text" name = "customer"/>
         <input type = "button" value = "Set Cookie" onclick = "WriteCookie();"/>
      </form>   
   </body>
</html>
```

Ahora su maquina tiene una cookie llamada `name`. Puede configurar varias cookies utilizando varios pares `key = value` separados por comas.

### Cookies de lectura

Leer una cookie es tan simple como escribir una, porque el valor del objeto `document.cookie` es la cookie. Por lo tanto, puede utilizar esta cadena de caracteres cada vez que desee acceder a la cookie. La cadena `document.cookie` mantendra una lista de pares `name = value` separados por punto y coma, donde `name` es el nombre de una cookie y `value` es su valor.

Puede usar la funcion `split()` para dividir una cadena de caracteres en `key` y `values` de la siguiente manera:

#### Ejemplo

Prueba el siguiente ejemplo para obtener todas las cookies.

````html
<html>
   <head>   
      <script type = "text/javascript">
         <!--
            function ReadCookie() {
               var allcookies = document.cookie;
               document.write ("All Cookies : " + allcookies );
               
               // Get all the cookies pairs in an array
               cookiearray = allcookies.split(';');
               
               // Now take key value pair out of this array
               for(var i=0; i<cookiearray.length; i++) {
                  name = cookiearray[i].split('=')[0];
                  value = cookiearray[i].split('=')[1];
                  document.write ("Key is : " + name + " and Value is : " + value);
               }
            }
         //-->
      </script>      
   </head>
   
   <body>     
      <form name = "myform" action = "">
         <p> click the following button and see the result:</p>
         <input type = "button" value = "Get Cookie" onclick = "ReadCookie()"/>
      </form>      
   </body>
</html>
```

Nota: aqui `length` es un metodo de la clase `Array` que devuelve la longitud de una matriz. Discutiremos Arrays mas adelante. Por el momento, por favor trate de digerirlo. Puede que ya existan otras cookies configuradas en su maquina. El codigo anterior mostrara todas las cookies asignadas en su maquina.


### Configuracion de fecha de caducidad a las cookies

Puede extender la vida util de una cookie mas alla de la sesion actual del navegador configurando una fecha de vencimiento y guardandola en su interior. Esto se puede hacer configurando el atributo `expires` con una fecha y hora.

#### Ejemplo

Prueba el siguiente ejemplo. Ilustra como extender la fecha de caducidad de una cookie por 1 mes.

```html
<html>
   <head>   
      <script type = "text/javascript">
         <!--
            function WriteCookie() {
               var now = new Date();
               now.setMonth( now.getMonth() + 1 );
               cookievalue = escape(document.myform.customer.value) + ";"
               
               document.cookie = "name=" + cookievalue;
               document.cookie = "expires=" + now.toUTCString() + ";"
               document.write ("Setting Cookies : " + "name=" + cookievalue );
            }
         //-->
      </script>      
   </head>
   
   <body>
      <form name = "myform" action = "">
         Enter name: <input type = "text" name = "customer"/>
         <input type = "button" value = "Set Cookie" onclick = "WriteCookie()"/>
      </form>      
   </body>
</html>
```
### Borrando una cookie

A veces deseara eliminar una cookie para que intentos posteriores de leer la cookie no devuelvan nada. Para hacer esto, solo necesita establecer la fecha de caducidad a una hora en el pasado.

#### Ejemplo

Prueba el siguiente ejemplo. Ilustra como eliminar una cookie al establecer fecha de caducidad para un mes posterior a la fecha actual.

```html
<html>
   <head>   
      <script type = "text/javascript">
         <!--
            function WriteCookie() {
               var now = new Date();
               now.setMonth( now.getMonth() - 1 );
               cookievalue = escape(document.myform.customer.value) + ";"
               
               document.cookie = "name=" + cookievalue;
               document.cookie = "expires=" + now.toUTCString() + ";"
               document.write("Setting Cookies : " + "name=" + cookievalue );
            }
          //-->
      </script>      
   </head>
   
   <body>
      <form name = "myform" action = "">
         Enter name: <input type = "text" name = "customer"/>
         <input type = "button" value = "Set Cookie" onclick = "WriteCookie()"/>
      </form>      
   </body>
</html>
```

### Contacto

- Envia Tus comentarios al correo `henrytorrespo@yahoo.com`
