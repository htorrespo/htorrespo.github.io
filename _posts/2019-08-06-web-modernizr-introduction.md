---
title: Modernizr - Deteccion de compatibilidad de navegadores
description: Modernizr es una biblioteca de JavaScript que estaiseñada para detectar caracteristicas de HTML5 y CSS3 en varios navegadores, lo que le permite a JavaScript evitar el uso de funciones no implementadas o usar una solucion alternativa como un shim para emularlas
categories: 
  - Blog
  - Javascript
comments: true
---

{% comment %}
04-ene-2016
https://bbvaopen4u.com/es/actualidad/modernizr-biblioteca-javascript-para-hacer-paginas-web-todoterreno
January 15, 2019 
 https://www.lambdatest.com/blog/feature-detection-with-modernizr-for-cross-browser-compatibility/
{% endcomment %}

Cuando un profesional se dedica al desarrollo de proyectos digitales hay una maxima, lo que se ve en el navegador es lo que es. Da igual que backend o que estilos tenga nuestra pagina web si a la hora de renderizarlo en el navegador se ve de forma distinta a la esperada. La libreria JavaScript Modernizr es la solucion para evitar disgustos: es el mejor testeador posible para detectar cuales son las caracteristicas del proyecto que soporta cada navegador.

Concretamente, Modernizr es una libreria que revisa 18 caracteristicas de estilos CSS3 y 40 mas relacionadas con el documento HTML, sobre todo su ultima version disponible, HTML5. Esto es interesante porque los navegadores mas modernos ejecutan recursos que los mas antiguos no pueden. La idea es aprovechar las ventajas de los primeros sin dejar de servir en los segundos. Asi se ajusta el diseño a la experiencia de usuario real que tendra la web para todos los navegadores. Facilita la creacion de proyectos digitales todoterreno.

## Instalacion y herramientas de Modernizr 

1.Para realizar la deteccion de funciones con Modernizr, debe agregarel archivo `modernizr.js` a su proyecto. Esto se puede hacer de 2 maneras:

a.Descargar [descargar el archivo con el codigo fuente de Modernizr](https://modernizr.com/download/).desde: visite el sitio web oficial para crear y descargar el archivo JavaScript. Haga clic en "Add your detects" para seleccionar manualmente las caracteristicas que desee de acuerdo con las necesidades de su proyecto o haga clic en "Development build" para ser redirigido a la pagina de compilacion con todas las opciones de pruebas / detecciones preseleccionadas. Haga clic en el boton de compilacion para descargar el archivo.

b.Usando npm y linea de comando: Modernizr tambien se puede instalar Node Packet Manager o NPM. Puedes instalar NPM aqui. Despues de instalar npm, abra la linea de comando e ingrese:

```terminal
npm install -g modernizr
```
Modernizr para la deteccion de funcionalidades realiza 3 funciones basicas: -

- Agrega clases que indican soporte de caracteristicas que se pueden usar para aplicar condicionalmente reglas de estilo CSS a diferentes elementos.

- Crea un objeto javascript para verificar o validar la compatibilidad con cualquier funcion HTML o CSS en un navegador.

- Permite suministrar condicionalmente scripts JS personalizados o polyfills para imitar caracteristicas que faltan.

Es importante recordar que la deteccion de funcionalidades con Modernizr es solo para funciones que son compatibles. Para esas funciones no compatibles de un navegador antiguo se logra mediante "polyfilling".

2.Ahora incluya el archivo Modernizr descargado en la seccion de su pagina.

Para usar esta libreria JavaScript es necesario incorporar el script de Modernizr en el `<head>` de la web, justo despues de las declaraciones de estilos CSS del site. Primero cargan los estilos y despues la libreria. El script que habria que añadir en el `<head>` del proyecto es el siguiente:

```html
<script src="modernizr.js"></script>
```

3.Agregue la clase `"no-js"` a la etiqueta `<html>`.

```html
<!DOCTYPE html>
<html class="no-js">
<head>
<script src="modernizr-custom.js"></script>
</head>
```

Esta clase `"no-js"` es una alternativa necesaria si el usuario ha deshabilitado JavaScript en su navegador o si el navegador en si no admite JavaScript. Una vez que se carga la pagina y en caso de que el navegador admita JavaScript, la clase `"no-js"` sera reemplazada por la clase "js" automaticamente por Modernizr para la deteccion de caracteristicas.

4.Modernizr agrega varias clases CSS en el elemento raiz `<html>`. Estas clases se agregan en funcion de las capacidades del navegador: las clases se agregan para las funciones que son compatibles y las clases se agregan con un prefijo "no" para las funciones que no son compatibles.

Por ejemplo, si el navegador admite Flexbox, la clase `"flexbox"` se agregara a la etiqueta `<html>`. Si no es compatible, se agrega la clase `"no-flexbox"`.

Clases agregadas a la etiqueta `<html>` por Modernizr para pruebas de deteccion de caracteristicas en IE9

```html
<html class="js no-flexbox canvas canvastext 
no-webgl no-touch geolocation postmessage 
no-websqldatabase no-indexeddb hashchange 
no-history draganddrop no-websockets rgba 
hsla multiplebgs backgroundsize no-borderimage 
borderradius boxshadow no-textshadow opacity 
no-cssanimations no-csscolumns no-cssgradients 
no-cssreflections csstransforms no-csstransforms3d no-csstransitions fontface generatedcontent 
video audio localstorage sessionstorage 
no-webworkers no-applicationcache svg inlinesvg 
smil svgclippaths">
```
## Deteccion de caracteristicas JavaScript con Modernizr

Objeto JavaScript. Modernizr ejecuta una serie de comprobaciones o pruebas basadas en JavaScript en segundo plano durante la carga de la pagina para detectar si el navegador admite o no las funciones. Una vez instalada y cargada la libreria Modernizr, el objeto JavaScript permite detectar que funcionalidades del proyecto estan soportadas en cada navegador, tanto lenguaje HTML como estilos CSS. Este tipo de deteccion de funcionalidades disponibles se produce a traves de variables booleanas de true (cierto) o false (falso). True significa que el navegador soporta la funcionalidad; false que no lo hace.

Podemos acceder a varias propiedades de este objeto "Modernizr" para la deteccion de caracteristicas utilizando "Modernizr.featureName". Por ejemplo, Modernizr.video devolvera "verdadero" si el navegador admite el elemento de video, y falso si el navegador no lo hace.

```html
if (Modernizr.awesomeNewFeature) {
    showOffAwesomeNewFeature();
  } else {
    getTheOldLameExperience();
  } 
```

Dos casos practicos a partir del ejemplo teorico de arriba. El primero prueba si el navegador usado por el usuario soporta los eventos touch de nuestro proyecto. El segundo detecta si se pueden aplicar sombras:

```html
if (Modernizr.touch){

  //el navegador soporta eventos touch

} else {

  //el navegador no soporta eventos touch

}

 

if (Modernizr.boxshadow) {
   // Podemos aplicar sombras!
} else {
   // La propiedad box-shadow no esta disponible
}
```

El siguiente ejemplo muestra como probar los gradientes lineales CSS utilizando JavaScript y agregando la clase de gradiente lineal para los navegadores que lo admiten.

``` html
$(document).ready(function () {

    if (Modernizr.cssgradients) {
        alert("This browser supports CSS Gradients");
        $('#box').addClass('cssgradients');
    }
        
    if (Modernizr.cssgradients) {
        alert("This browser doesn't support CSS Gradients");
        $('#box').addClass('no-cssgradients');
    }

});
```

Ademas de la deteccion de funciones usando javascript para probar si un navegador admite esa tecnologia web en particular o no, Modernizr tambien se puede usar para cargar polyfills / shims para imitar las funciones que un navegador carece o no admite.

## Deteccion de caracteristicas CSS con Modernizr

Estas clases se agregan a la etiqueta `<html>` de Modernizr para la deteccion de caracteristicas de las propiedades de estilo CSS en funcion de si una caracteristica es compatible con un navegador determinado o no. Las clases con el prefijo `"no"` se aplicaran automaticamente en los navegadores que no admitan esas funciones correspondientes.

Por ejemplo, si la propiedad box-shadow es compatible con un navegador, la clase Modernizr `"boxshadow"` se agrega a la etiqueta `<html>`. Si no es compatible, se agrega la clase Modernizr `"no-boxshadow"`. Podemos usar solo estas 2 clases CSS para dirigir efectivamente a todos los navegadores independientemente de su soporte para esta caracteristica en particular. La clase `".boxshadow"` se puede usar para diseñar una sombra de cuadro alrededor de un `div` con desplazamiento horizontal y desplazamiento vertical de 10px, desenfoque de 8px y separacion de 15px para todos los navegadores compatibles y la clase `".no_boxshadow"` se puede usar para codificar con un ancho de borde mas grueso para compensar la falta de sombra para todos los navegadores no compatibles.

```html
.boxshadow #box {
    border: 2px solid black;
    -webkit-box-shadow: 10px 10px 8px 10px #888888;
    -moz-box-shadow: 10px 10px 8px 10px #888888;
}
   
.no-boxshadow #box {
    border: 5px solid black;
}
```

Por lo tanto, en lugar de escribir montones de codigo para dirigirse a navegadores individuales, la deteccion de caracteristicas con Modernizr reduce la tarea a codificar solo 2 bloques de codigo, uno para navegadores compatibles y el otro para no compatibles.

Otro ejemplo para gradientes lineales CSS:

```html
.no-cssgradients .header {
  background: url("https://unsplash.it/640/425?image=44");
}
 
.cssgradients .header {
background-image: url("https://unsplash.it/640/425?image=44"), linear-gradient(red, blue);
}
```

Es bastante plausible que las clases creadas por Modernizr puedan entrar en conflicto con una clase CSS preexistente que habria agregado a su hoja de estilo. Para evitar este escenario, es aconsejable agregar un `"classPrefix"` a todas sus clases Modernizr para que sean completamente unicas. Por ejemplo, es posible que ya este utilizando una clase llamada `'boxshadow'` que chocara con la clase de deteccion creada por Modernizr con el mismo nombre. Puede hacer uso de prefijos de clase para abordar facilmente este problema. Realice los siguientes cambios en su configuracion:

```html
{
  "classPrefix": "foo-",
  "feature-detects": ["dom/boxshadow"]
}
```

Ahora, en lugar de `<html class = "boxshadow">, modernizr agregara <html class = "foo-boxshadow">`.

Si desea que Modernizr no agregue ninguna de sus clases a su etiqueta HTML, configure `"enableClasses"` en falso en su archivo de configuracion. Esto todavia excluye la clase no-js. Para evitar incluso eso, establezca `"enableJSClass"` en falso tambien.

### Librerias Polyfills y el metodo Modernizr.load()

Modernizr dispone de un metodo que permite a los desarrolladores la carga bajo demanda de librerias o plugins que aumentan las funcionalidades de los navegadores menos modernos. La libreria se cargaria solo si el usuario visita una pagina web con algun estilo concreto no disponible en el navegador.

Esto se consigue con la carga de uno de estos plugins o polyfill mediante el metodo `Modernizr.load()`. Asi se mantiene la UX en navegadores antiguos.

El metodo `Modernizr.load()` es un cargador condicional basado en una biblioteca `yesnope.js` extremadamente popular que carga archivos JavaScript basados en el resultado de una prueba de deteccion de caracteristicas. Por ejemplo, podemos usar el metodo `Modernizr.load()` para probar la disponibilidad de soporte para flexbox y cargar un polyfill si el navegador no lo admite.

```html
Modernizr.load({
    test: Modernizr.flexbox,
    yep : 'flexlayout.css',
    nope: 'matchHeight.js' });
```

Si el navegador admite flexbox, se cargara el archivo `flexlayout.css`; de lo contrario, en caso de falta de compatibilidad, se cargara polyfill de `matchHeight.js`, que imita la funcion de flexbox en navegadores mas antiguos.

`Modernizr.load()` toma la propiedad que define una caracteristica como argumento y realiza una prueba para verificar su compatibilidad. Si la propiedad es compatible y la prueba se realiza correctamente, se carga la secuencia de comandos de caso `yep`. Si la propiedad no es compatible y la prueba falla, se carga el guion de caso `nope`. Si se va a cargar una secuencia de comandos, independientemente de si la prueba falla o no, `both` casos. Por ejemplo -

```html
Modernizr.load({
    test: Modernizr.canvas,
    yep:  'Canvasavailable.js',
    nope: 'FlashCanvas.js',
    both: 'CustomScript.js'
});
```

Los pasos a seguir:

- Con Modernizr se puede detectar si una funcionalidad esta o no disponible dentro del navegador utilizado por el usuario. En el caso de que esa propiedad no este disponible en el navegador, el metodo `Modernizr.load()` puede cargar el polyfill especifico para esa funcion.

- Como usar el metodo `Modernizr.load()` para incorporar librerias? El codigo necesario es sencillo, en este caso incorpora geolocalizacion:

```html
Modernizr.load({
  test: Modernizr.geolocation,
  yep : 'geo.js',
  nope: 'geo-polyfill.js'
});
```

En la sintaxis anterior hay tres elementos distintos:

- `test`: hace mencion a la funcionalidad que queremos que se ejecute dentro del navegador del usuario.

- `yep`: si la condicion cumple, cargamos la funcionalidad.

- `nope`: si la condicion no se cumple, cargamos la alternativa, el polyfill de geolocalizacion para navegadores antiguos.

Existen algunas caracteristicas añadidas que se pueden cargar tambien:

- `both`: se cumpla o no la condicion, se carga la funcionalidad.

- `load`: carga la funcionalidad independientemente del test que realice la libreria JavaScript Modernizr en el navegador.

- `callback`: carga la funcionalidad una vez esten los recursos.

- `complete`: carga la funcionalidad haya o no recursos. 

`Modernizr.load()`  tambien se puede utilizar en los casos en que desee crear un acceso por compatibilidad en caso de que no se pueda acceder a las redes CDN de Google o Microsoft, lo que puede arruinar toda su pagina web. Sin CDN, los scripts jquery o bootstrap no se cargaran si los incluye mediante enlaces CDN. El siguiente ejemplo muestra como crear una copia de seguridad para cargar jquery si falla CDN. Primero intentara descargar jQuery del CDN de Google, utilice la funcion correspondiente al caso `complete` para verificar si jQuery esta presente o no. Si jQuery esta ausente porque no se pudo descargar de Google CDN, el caso de `load` cargara la copia de seguridad jquery de su almacenamiento local

```html
Modernizr.load([
    {
        load: '//ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js',
        complete: function () {
            if (!window.jQuery) {
                Modernizr.load('js/libs/jquery/3.3.1/jquery.min.js');
            }
        }
    },
    {
        // execute this if jquery couldn't be loaded.
        load: 'backup-jquery.js'
    }
]);
```

`Modernizr.load()` y `yesnope.js` ahora han quedado en desuso y ya no son compatibles con la version actual de modernizr (v3.5). Todavia puedes usar esto en v2.8. Puede leer mas sobre el aviso de desaprobacion dirigido por el creador del modernizador Alex Sexton [aqui](https://github.com/SlexAxton/yepnope.js#deprecation-notice).

Una alternativa viable ahora es usar el metodo jquery `getScript()`. El siguiente ejemplo muestra como cargar un script de polyfill si un navegador no admite la deteccion de funciones:

```html
if (Modernizr.geolocation){
  //feature is supported by the browser
  console.log('geolocation supported');
} else {
  // feature not supported - load polyfill
  $.getScript('path/script.js')
  .done(function() {
    console.log('script loaded');
  })
  .fail(function() {
    console.log('script failed to load');
  });
}
```

Ha pasado casi una decada desde el lanzamiento de Modernizr en 2009, pero aun hoy no ha perdido su relevancia y proposito. Para cada desarrollador al que le guste construir sus sitios web y aplicaciones web con caracteristicas modernas de vanguardia HTML5 y CSS3, Modernizr es un activo indispensable. No solo ayuda a evitar los montones de codigo necesarios para las pruebas cruzadas del navegador, sino que tambien ayuda a proporcionar una alternativa a la deteccion poco confiable de User Agent. Al igual que las consultas de caracteristicas, Modernizr con deteccion de caracteristicas para compatibilidad cruzada entre navegadores ayuda a implementar todos los retrocesos necesarios para funcionalidades y caracteristicas no compatibles que garantizan una experiencia de usuario impecable independientemente del navegador que el usuario pueda estar utilizando. Aunque las consultas de caracteristicas de CSS @supports nativas se estan poniendo al dia rapidamente en terminos de popularidad y aceptacion generalizadas entre los desarrolladores, su falta de soporte en IE (incluido IE11) significa que Modernizr con mecanismo de deteccion de caracteristicas, sigue siendo la principal herramienta de eleccion para lograr la compatibilidad entre navegadores.

### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
