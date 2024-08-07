# 61. DOM: Introduction.

El ***DOM*** (Document Object Model) nos permite poder ***acceder*** al contenido ***html*** de un ***documento*** desde ***JavaScript***.

Para ello, utilizamos el ***document*** de ***window***.

~~~
//DOM
console.log(window.document);
~~~

Podemos colocar:

~~~
console.log(document);
~~~

***Nota:*** ***Document*** devuelve ***todo*** el contenido ***html***, entre ellos, información como ***URL*** y otros.

El ***document*** cuenta de ***2 partes***:

	- doctype
	- documentElement

## Acceder a estructura HTML

Para ***acceder*** a la ***estructura HTML*** de un ***documento***, accedemos el ***documentElement*** de ***document***.

~~~
//Impresion de Estructura HTML
console.log(document.documentElement);
~~~

También podemos acceder al ***head*** o ***body***.

~~~
//Impresion de head HTML
console.log(document.head);

//Impresion de body HTML
console.log(document.body);
~~~

## Acceder a información HTML

Por otro lado, ***doctype*** permite poder ***obtener información*** de la pagina.

~~~
//Impresion de informacion HTML
console.log(document.doctype);
~~~

## Acceder a información extra HTML

Tambien, podemos ***acceder*** a diferentes elementos ***HTML***, tanto del ***contenido*** como a ***colecciones*** de estos.

Ejemplos de algunos:

~~~
//Impresion de Charset del documento
console.log(document.charset);

//Impresion de tirulo del documento
console.log(document.title);

//Colecciones

//Impresion de coleccion de links
console.log(document.links);

//Impresion de coleccion de imagenes
console.log(document.images);

//Impresion de coleccion de formularios
console.log(document.forms);

//Impresion de coleccion de hojas de estilos
console.log(document.styleSheets);

//Impresion de coleccion de scripts
console.log(document.scripts);

//Tiempo para seleccionar algo en la pagina
setTimeout(() => {
//Impresion de texto seleccionado
console.log(document.getSelection().toString());
}, 4000);

//Impresion de codigo HTML en el documento
document.write("<h2>Hola mundo</h2>");
~~~

Las ***colecciones*** no son ***arrays*** por lo que algunos ***métodos*** de estos no estas disponibles.

