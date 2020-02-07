---
title: JavaScript - Codigos utiles .htaccess para sitios web
description: Como redireccionar a tus visitantes desde el puerto estandar http hacia el puerto seguro https si dispones de un certificado de seguridad SSL instalado en tu dominio para garantizar que la informacion se transmita de forma segura.
categories: Blog
comments: true
---

Hoy en dia, la mayoria de ofertas de alojamiento web son para el servidor web Apache. Es una solucion mucho mas barata en comparación con la plataforma IIS en Windows. Apache es bien conocido por su capacidad para usar `.htaccess`, donde podemos controlar determinados aspectos de nuestro sitio web, incluyendo el rendimiento.

### Redirección con .htaccess

Inserta el siguiente codigo en el archivo `.htaccess` ubicado en el directorio publico `/public_html` de tu plan de alojamiento web. Puedes editar el contenido del archivo `.htaccess` accediendo por ftp o haciendo uso de la utilidad **Administrador de Archivos** del Panel de Control de tu plan de alojamiento.

```terminal
RewriteEngine On
RewriteCond %{HTTPS} off
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```
**Nota**: Es posible que el archivo `.htaccess` contenga otras directivas imprescindibles para el correcto funcionameinto de tu página web, haz una copia de seguridad antes de realizar modificaciones.

Antes de avanzar, seguramente te habras preguntado ¿donde localizo el archivo .htaccess? El archivo `.htaccess` es un archivo *oculto* (el . delante del nombre indica que se trata de archivo oculto).

Para poder visualizarlo debes:

1. Accede a tu cPanel.

2. Ingrese al **Administrador de Archivos**, navegue hasta encontrar la carpeta `/public_html`. 

3. En la parte superior derecha seleccione **Configuracion**. Se un cuadro de dialogo con varias opciones, seleccione *Mostrar archivos ocultos (dotfiles)*.

4. Abrir la carpeta `/public_html`. Ahora podras ver el archivo `.htaccess` (no confundir con `htaccess.txt` que si es visible).

5. Click **Editar** en el menu del **Administrador de Archivos** (se sugiere hacer una copia del archivo original)

6. Inserte el codigo de redireccion


Ahora que ya lo tienes claro, seguiremos conociendo otros codigos que puedes utilizar en tu archivo `.htaccess`.


{% comment %} 
https://hostingecuador.ec/como-configurar-una-redireccion-https
{% endcomment %}


### Como cambiar de la URL con alias www a la URL sin alias www

El siguiente codigo debe redirigir al usuario de la dirección URL de tu dominio con www a la dirección URL sin www.

```terminal
RewriteEngine On
RewriteCond %{HTTP_HOST} ^www.tuempresa.com [NC]
RewriteRule ^(.*)$ http://tuempresa.com/$1 [L,R=301]
```

### Redirigir siempre al alias www cualquier dominio apuntado

Este codigo es util para redirigir uno o varios dominios para que trabajen con el alias www usando comodines `www.*.*`:

```terminal
RewriteCond %{REQUEST_URI} !^/robots\.txt$ [NC]
RewriteCond  %{HTTP_HOST} !^www\.[a-z-]+\.[a-z]{2,6} [NC]
RewriteCond %{HTTP_HOST} ([a-z-]+\.[a-z]{2,6})$   [NC]
RewriteRule  ^/(.*)$ http://%1/$1 [R=301,L]
```

Si tenemos varios dominios gestionando en la cuenta de Hosting, para no tener que crear una redireccion `301` de uno en uno cada dominio, otra forma de hacerlo es redirigiendo todos los `.tld` de los dominios utilizados *sin alias www* a dominios *con alias www*:

```terminal
RewriteEngine On
RewriteCond %{HTTP_HOST} !^www\.
RewriteRule ^(.*)$ http://www.%{HTTP_HOST}/$1 [R=301,L]
```

{% comment %} 
Redirecciona urls de forma correcta usando cPanel y htaccess 
https://www.webempresa.com/blog/redirecciona-urls-de-forma-correcta-usando-cpanel-y-htaccess.html
{% endcomment %}


### Redirigir url de una carpeta a otra carpeta del mismo dominio

Una Redireccion `301` es util cuando cometemos el error de indicar una carpeta nombrada de forma incorrecta o que fue renombrada posteriormente, de forma que podamos redireccionar peticiones que vayan a `/carpeta1/` para que aterricen en `/carpeta2/`.

Se deben añadir este tipo de redirecciones en la parte más alta del archivo `.htaccess`,  :

```terminal
Options +FollowSymLinks
RewriteEngine On
RewriteRule ^carpeta1/(.*)$ http://dominio.com/carpeta2/$1 [R=301,L]
```

### Redirigir un dominio a otro dominio

Para evitar que las urls se vean afectadas por cambio de un dominio a otro es conveniente que hacer la siguiente redireccion en `.htaccess` de forma que quienes vengan de enlaces de la antigua url aterricen en la nueva url de forma correcta, lo contrario afectaría al posicionamiento y habria un aumento de pérdida de tráfico.

```terminal
<IfModule mod_rewrite.c>
  RewriteEngine On
  RewriteCond %{HTTP_HOST} ^anteriordominio.com$ [OR]
  RewriteCond %{HTTP_HOST} ^www.anteriordominio.com$
  RewriteRule (.*)$ http://www.nuevodominio.com/$1 [R=301,L]
</IfModule>
```

### Redirigir del localhost (tu PC) a un dominio remoto

Con esta regla puedes redireccionar de localhost (tu ordenador) a tu sitio web remoto (Hosting):

```terminal
RewriteEngine On
RewriteCond %{HTTP_HOST} ^localhost$
RewriteRule (.*)$ http://www.dominio.com/$1 [R=301,L]
```

Si solo quieres redireccionar un subdominio concreto puedes crear la siguiente regla en tu `.htaccess`:

```terminal
RewriteEngine On
RewriteCond %{HTTP_HOST} ^subdominio.dominio.com$
RewriteRule (.*)$ http://www.nuevodominio.com/$1 [R=301,L]
```

Una forma mas sencilla de hacer esto con comodines, creando una regla en `.htaccess` como la siguiente:

```terminal
Redirect 301 (.*)$ http://www.nuevodominio.com/$1
```

### Impedir listar el directorio

Si tienes una carpeta en el servidor web utilizada para almacenar archivos como eBooks, software legal, etc., si la carpeta no tiene archivo index.html, los visitantes pueden ver todos los archivos dentro de la carpeta sin problemas. En este caso puedes utilizar el siguiente codigo para evitar que esto suceda.

```terminal
Options -Indexes
```

### Orden de ejecucion de archivos

Si tienes tanto el archivo `index.html` como el archivo `index.php` en la carpeta `/public_html`, el archivo `index.html` tiene mayor prioridad y se ejecutara en primer lugar. Aunque la mayoria de scripts web utilizan el archivo `index.php` como punto de partida. Si se elimina el archivo `index.html`, se soluciona el problema, aunque no siempre es asi y en estos casos hay una mejor solucion que es utilizar el siguiente codigo para dar prioridad al archivo `index.php` en lugar de `index.html`.

```terminal
DirectoryIndex index.php index.html
```

### Comprimir archivos CSS, JavaScript, XML y texto

El siguiente codigo esta diseñado para comprimir el codigo de salida CSS, JavaScript, XML y de texto antes de ser mostrado en el navegador. La idea basica es ahorrar tiempo en la carga y no consumir tanto ancho de banda.

```terminal
<ifmodule>
 AddOutputFilterByType DEFLATE text/html text/plain text/xml text/css text/javascript application/x-javascript
</ifmodule>
```

### Almacenamiento de imágenes en cache

Cada vez que recibimos visitas en la web, el servidor web obtiene todos los archivos necesarios, tales como archivos CSS y JavaScript, así como fotos e imagenes para poder mostrarla. Podemos usar el codigo de abajo para gestionar los archivos cache, y que cuando un visitante vuelva a visitarnos por segunda vez, el servidor cargue el archivo de la cache lo que acelerara el tiempo de carga sitio web.

```terminal
<IfModule mod_expires.c>
ExpiresActive On
ExpiresByType image/gif A432000
ExpiresByType image/jpg A432000
ExpiresByType image/jpeg A432000
ExpiresByType image/png A432000
ExpiresByType image/ico A432000
ExpiresByType image/bmp A432000
ExpiresByType text/css A432000
ExpiresByType text/javascript A432000
ExpiresByType application/javascript A432000
ExpiresByType application/x-javascript A432000
</ifmodule>
```

El anterior codigo guarda cache de los archivos durante cinco días o 432.000 segundos. Puedes cambiar el periodo de almacenamiento en cache, asegurándote de utilizar el valor expresado en segundos.

### Proteger el archivo `.htaccess`

El siguiente codigo evita que tu archivo `.htaccess` puedan ser leído directamente desde el navegador web.

```terminal
<Files .htaccess>
Order allow,deny
Deny from all
</Files>
```

### Prevenir el hotlinking

A veces, otros webmasters, hacen suyas las imagenes de nuestras webs, articulos, etc., afectando con ello el ancho de banda que disponemos en nuestro Hosting. Si ademas ellos tienen una gran cantidad de visitantes al día, estos van a utilizar nuestro ancho de banda del servidor para visualizar nuestras imagenes en la web ajena a nosotros.

Se puede utilizar el codigo que se muestra a continuacion para evitar el hotlinking, y de esta forma reemplazar la imagen original por otra con algun aviso para hacerles saber que la imagen es nuestra o que el hotlinking es una mala practica.

```terminal
RewriteEngine On
RewriteCond %{HTTP_REFERER} !^http://(.+\.)?webempresa\.com/ [NC]
RewriteCond %{HTTP_REFERER} !^$
RewriteRule .*\.(jpg|gif|bmp|png)$ http://hotlink.webempresa.com/no_se_permite_hotlinking.jpg [L]
```

Puedes subir la imagen a un sitio de alojamiento de imagenes como ImageShack para evitar que tu ancho de banda se vea afectado.

### Cambiar la ubicacion de la carpeta de dominio a otra carpeta de `/public_html`

Si ya tienes un sitio web en `/public_html`, y quieres actualizar la pagina web, pero no quieres que los demas lo vean, pero tampoco quieres afectar al sitio web en produccion existente, la forma mas facil es la construccion de la nueva pagina web en una subcarpeta de `/public_html`, por ejemplo, `/public_html/web2`.

Al finalizar todas las pruebas y mejoras, necesitas reemplazar el antiguo sitio web con el nuevo, pero transferir archivos y carpetas a la carpeta /public_html es bastante molesto. La mejor solucion es usar `.htaccess` para decirle a Apache que utilice la carpeta `/public_html/web2` en lugar de `/public_html` para el dominio.

```terminal
RewriteEngine On
RewriteCond %{HTTP_HOST} ^tuempresa\.com$ [OR]
RewriteCond %{HTTP_HOST} ^www\.tuempresa\.com$
RewriteCond %{REQUEST_URI} !^/web2/
RewriteRule (.*) /web2/$1 [L]
```

### Crear URLs de uso facil o *amigables*

¿Cual de las dos URL a continuación parece más amigable?

```terminal
http://tusitio.com/acercade
http://tusitio.com/paginas/acercade.html
```

Cuando se trata de direcciones URL, siempre y cuando el significado sea claro, cuanto mas corto mejor. `htaccess` con una llamada al modulo de Apache `mod_rewrite` permite configurar las direcciones URL como quieras. El servidor puede mostrar el contenido de `/paginas/acercade.html` cada vez que alguien visita `http://tusitio.com/acercade`.

A continuación algunos ejemplos:

```terminal
RewriteEngine on
RewriteRule ^acercade/$    /paginas/acercade.html [L]
RewriteRule ^caracteristicas/$ /caracteristicas.php [L]
RewriteRule ^comprar/$      /comprar.html [L]
RewriteRule ^contacto/$  /paginas/contacto.htm [L]
```

### Forzar el uso de SSL

Este codigo fuerza a utilizar SSL, no permitiendo conexiones http. Para evitar escuchas en `http://` utilizamos por debajo la directiva `ErrorDocument`.

```terminal
SSLOptions + StrictRequire
SSLRequireSSL
```

Cuando una línea comienza por `#` es un comentario que no tiene efecto alguno.

Si alguien visita tu sitio el servidor web Apache verifica si tiene un archivo `.htaccess` en algun lugar de su espacio web a partir de la carpeta raiz o la carpeta principal y rastrea todas las carpetas hasta llegar al archivo solicitado. Si encuentra un archivo `.htaccess`, sus directivas se aplican a la solicitud actual.

Es importante saber que el archivo `.htaccess` debe ser legible por el servidor Apache. Por tanto es importante consultar con su Hosting si se requiere algun permiso especial que hayan establecido para los archivos `.htaccess`. En general los permisos correctos para este archivo son `644`.

### Redireccionar de HTTP a HTTPS

Cabe decir que es necesario disponer de un Certificado SSL instalado en el Hosting para poder hacer uso de este protocolo mas seguro.

```terminal
RewriteEngine On
RewriteCond %{ENV:HTTPS} !on [NC]
RewriteCond %{HTTP_HOST} ^tu_dominio\.com$ [OR]
RewriteCond %{HTTP_HOST} ^www\.tu_dominio\.com$
RewriteRule ^(.*)$ https://tudominio.com/$1 [R=301,L,NE]
```
Pueden existir casos en los que queramos añadir excepciones en el forzado de la redireccion de HTTP a HTTPS (por ejemplo, la pagina de notificacion de Redsys). Esto lo podemos hacer añadiendo una linea de codigo adicional. Si por ejemplo, queremos añadir una excepcion para la url `https://tudominio.com/?wc-api=WC_redsys` habría que dejar el codigo anterior de la siguiente forma:

```terminal
RewriteEngine On
RewriteCond %{ENV:HTTPS} !on [NC]
RewriteCond %{QUERY_STRING} !wc-api [NC]
RewriteCond %{HTTP_HOST} ^tu_dominio\.com$ [OR]
RewriteCond %{HTTP_HOST} ^www\.tu_dominio\.com$
RewriteRule ^(.*)$ https://tudominio.com/$1 [R=301,L,NE]
```

Redsys es una compañia que ofrece sus servicios a entidades financieras, siendo estas las que formalizan los contratos con los comercios y quienes, en consecuencia, se encargan de todos los aspectos relacionados con su gestion.

Otro ejemplo: si no queremos forzar el uso del HTTPS para la url `https://tudominio.com/blog/entrada1.html` tendremos que poner un codigo como el siguiente:

```terminal
RewriteEngine On
RewriteCond %{ENV:HTTPS} !on [NC]
RewriteCond %{REQUEST_URI} !\/blog\/entrada1\.html$ [NC]
RewriteCond %{HTTP_HOST} ^tu_dominio\.com$ [OR]
RewriteCond %{HTTP_HOST} ^www\.tu_dominio\.com$
RewriteRule ^(.*)$ https://tudominio.com/$1 [R=301,L,NE]
```

### Redireccionar de HTTPS a HTTP

Puede darse el caso que aun teniendo un Certificado SSL instalado (Comodo, Let's Encrypt, etc) quieras forzar el trafico encriptado SSL para que se sirva con HTTP por diversas razones (pruebas con plugins conflictivos, configuracion de una pasarela pago que no trabaja bien por HTTPS, etc), en cuyo caso codigos como el siguiente te permitiran pasar de HTTPS a HTTP sin desinstalar el Certificado SSL de tu Hosting.

```terminal
RewriteEngine On
RewriteCond %{ENV:HTTPS} on [NC]
RewriteCond %{HTTP_HOST} ^tu_dominio\.com$ [OR]
RewriteCond %{HTTP_HOST} ^www\.tu_dominio\.com$
RewriteRule ^(.*)$ http://tudominio.com/$1 [R=301,L,NE]
```

Este codigo debes colocarlo por encima de cualquier otro codigo de redireccionamiento, al principio del archivo `.htaccess`.

### Forzar la carga de contenido mixto bajo HTTPS en lugar de HTTP

Si tenemos instalado un Certificado SSL para servir la web bajo protocolo https pero por alguna razon estamos entregando contenido bajo protocolo http como contenido mixto, podemos añadir la siguiente directiva en el archivo `.htaccess` para forzar que los contenidos *no seguros* sean forzados a cargar bajo protocolo HTTPS.

Esta directiva es compatible con la mayoría de navegadores actuales.

```terminal
<ifModule mod_headers.c>
Header always set Content-Security-Policy "upgrade-insecure-requests;"
</IfModule>
```

### Forzar la carga de `index.html`

Para que un sitio HTML funcione sin añadir `index.html` deberas apuntar un dominio o un subdominio directamente a la carpeta que contenga la web, de modo que solo llamando a `http://dominio.com` o `subdominio.dominio.com` por ejemplo, cargue la web HMTL sin necesidad de añadir el archivo `index.html`.

Si una web se llama desde una ruta como `http://domino.com/otra_carpeta/` es normal que tengas que añadir el archivo `index.html` para que el navegador sepa que debe cargar.

No obstante puedes forzar mediante `.htaccess` para que cargue el archivo `index.html` sin tener que escribirlo en el navegador.

```terminal
RewriteEngine on
RewriteRule ^(.*)\.php$ $1.html%{QUERY_STRING} [L]
```

### Contacto

- Envia Tus comentarios al correo `henrytorrespo@yahoo.com`

Códigos útiles .htaccess para sitios web
https://www.webempresa.com/blog/codigos-utiles-htaccess-para-sitios-web.html

