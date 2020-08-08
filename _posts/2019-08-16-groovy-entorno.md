---
title: Groovy - Entorno
description: Instalacion de Groovy y configuracion de variables de entorno
categories: 
  - Blog
  - Groovy
comments: true
---

Hay una variedad de formas de obtener la configuracion del entorno Groovy.

**Descarga e instalacion binarias**: vaya al enlace www.groovy-lang.org/download.html para obtener el instalador binario `apache-groovy-binary-2.5.8.zip`. Haga clic en esta opcion para iniciar la descarga del instalador Groovy.

Despues de descargar la distribucion comprimida, debe descomprimir el archivo en un directorio de su eleccion y llevar a cabo los siguientes pasos para instalar Groovy en Windows:

1.Por simplicidad, asumiremos que la ruta del directorio es `C:\Applications\groovy-2.0`. 

2.Para tener el comando groovy disponible en su linea de comando, debe agregarlo a la ruta de su sistema configurando la variable de entorno llamada `PATH`. Tambien le recomendamos que cree una variable de entorno`GROOVY_HOME`.

3.Para acceder a las variables de entorno de Windows, debe presionar la combinacion de teclas Windows + Break. En Windows Vista, Windows 7 o posterior, abrira la pagina del Panel de control para la configuracion del sistema.

4.Haga clic en Configuracion avanzada del sistema para abrir la ventana Propiedades del sistema.

5.Luego debe hacer clic en el boton Variables de entorno... para llegar finalmente a la lista de variables del sistema.

6.Haga clic en el boton Nuevo ... y agregue la variable `GROOVY_HOME` que apunta a su ruta de instalacion Groovy, `C:\Applications\groovy-2.0`:

7.Luego busque la variable `PATH` en la lista de variables del sistema y agregue o inserte `%GROOVY_HOME%\bin;` al final

8.Ahora puede abrir la linea de comandos de Windows y verificar que Groovy este instalado correctamente digitando el comando `groovy --version`:

Si desea incluir los binarios groovy como parte de su construccion maven o gradle, puede agregar las siguientes lineas

##### Gradle

```xml
'org.codehaus.groovy: groovy: 2.4.5'
````

##### Maven

```xml
<groupId> org.codehaus.groovy </groupId>
<artifactId> maravilloso </artifactId>
<version> 2.4.5 </version>
```

### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
