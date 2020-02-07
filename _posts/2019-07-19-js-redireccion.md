---
title: JavaScript - Redireccion de paginas
description: Redireccionar pagina web con javascript
categories: Blog
comments: true
---

### ¿Que es la redireccion de paginas?

Es posible que haya encontrado una situacion en la que hizo clic en una URL para llegar a una página X, pero internamente fue dirigido a otra pagina Y. Esto ocurre por la redireccion de pagina. Este concepto es diferente a la actualizacion de pagina JavaScript.

Puede haber varias razones por las que le gustaria redirigir a un usuario desde la pagina original. Estas son algunas de las razones

- No le gusto el nombre del dominio y se esta mudando a uno nuevo. En tal caso, es posible que desee direccionar a todos sus visitantes al nuevo sitio. Aqui puede mantener su dominio anterior, pero coloque una sola pagina con una redireccion de pagina para que todos sus visitantes del dominio anterior puedan acceder a su nuevo dominio.

- Ha creado varias paginas basadas en las versiones del navegador o sus nombres o puede basarse en diferentes paises, entonces, en lugar de usar la redireccion de pagina del lado del servidor, puede usar la redireccion de  pagina del lado del cliente para que sus usuarios lleguen a la pagina correspondiente.

- Es posible que los motores de busqueda ya hayan indexado sus paginas. Pero al pasar a otro dominio, no le gustaria perder a sus visitantes que llegan a traves de los motores de busqueda. Asi que puede usar la redireccion de la pagina del lado del cliente. Pero tenga en cuenta que esto no se debe hacer para engañar al motor de busqueda, ya que podria hacer que su sitio sea prohibido.

### ¿Como funciona la redireccion de pagina?

Las implementaciones de redireccion de pagina son las siguientes.

#### Ejemplo 1

Es bastante simple hacer una redireccion de pagina usando JavaScript en el lado del cliente. Para redireccionar a los visitantes de su sitio a una nueva pagina, solo necesita agregar una linea en la seccion principal de la siguiente manera.

```html
<html>
   <head>
      <script type = "text/javascript">
         <!--
            function Redirect() {
               window.location = "https://www.tutorialspoint.com";
            }
         //-->
      </script>
   </head>
   
   <body>
      <p>Click the following button, you will be redirected to home page.</p>
      
      <form>
         <input type = "button" value = "Redirect Me" onclick = "Redirect();" />
      </form>
      
   </body>
</html>
```

#### Ejemplo 2

Puede mostrar un mensaje apropiado a los visitantes de su sitio antes de redireccionarlos a una nueva pagina. Esto tendria un tiempo de retraso para cargar la pagina. El siguiente ejemplo muestra como implementar el mismo. Aqui `setTimeout()` es una funcion de JavaScript que se puede utilizar para ejecutar otra funcion despues de un intervalo de tiempo determinado.

```html
<html>
   <head>
      <script type = "text/javascript">
         <!--
            function Redirect() {
               window.location = "https://www.tutorialspoint.com";
            }            
            document.write("You will be redirected to main page in 10 sec.");
            setTimeout('Redirect()', 10000);
         //-->
      </script>
   </head>
   
   <body>
   </body>
</html>
```

#### Ejemplo 3

El siguiente ejemplo muestra como redireccionar a los visitantes de su sitio a una pagina diferente segun sus navegadores.

```html
<html>
   <head>     
      <script type = "text/javascript">
         <!--
            var browsername = navigator.appName;
            if( browsername == "Netscape" ) {
               window.location = "http://www.location.com/ns.htm";
            } else if ( browsername =="Microsoft Internet Explorer") {
               window.location = "http://www.location.com/ie.htm";
            } else {
               window.location = "http://www.location.com/other.htm";
            }
         //-->
      </script>      
   </head>
   
   <body>
   </body>
</html>
```

### Contacto

- Envia Tus comentarios al correo `henrytorrespo@yahoo.com`
