# 77. BOM: Properties and Events.

El ***BOM*** (Browser Object Model) nos permite poder ***acceder*** al contenido ***disponible*** de nuestro ***navegador*** desde ***JavaScript***, tales como ***tamaño de ventana***, ***Tamaño de pestaña***, etc.

Los ***datos*** que podemos ***obtener*** del ***browser*** se ejecutan desde ***window***, a diferencia del ***DOM***, que se obtienen desde ***window.document***.

## Obtener tamaño de contenido del navegador

Para poder ***obtener*** los ***tamaños*** (***px***) del ***contenido*** (el ***body***) que se muestra desde la ***pantalla*** en el ***browser***, se utilizan los ***atributos inner***.

### Para el width

Para obtener el ***width*** que se muestra en ***pantalla*** del ***contenido*** del ***navegador***, se utiliza ***innerWidth***.

~~~
//Impresion de width de contenido del navegador
console.log(window.innerWidth);
~~~

***Nota:*** El ***innerWidth*** muestra en tamaño en ***px*** del contenido, por lo que depende del ***tamaño*** de la ***pestaña*** y ***%*** de ***zoom***.

### Para el height

Para obtener el ***height*** que se muestra en ***pantalla*** del ***contenido*** del ***navegador***, se utiliza ***innerHeight***.

~~~
//Impresion de height de contenido del navegador
console.log(window.innerHeight);
~~~

***Nota:*** ***inner*** se utiliza para mostrar en ***tamaño SOLO*** del espacio ***disponible*** para mostrar ***contenido***.

## Obtener tamaño de pestaña del navegador

También se puede ***obtener*** el ***tamaño*** de la ***pestaña*** del ***navegador***, para ello se utiliza ***outer***.

### Para el width

Para ***obtener*** el ***width*** de la ***pestaña*** del ***navegador***, se utiliza ***outerWidth***.

~~~
//Impresion de width de pestaña del navegador
console.log(window.outerWidth);
~~~

Similar a ***inner***, estos ***atributos***, son susceptibles al ***tamaño*** de la ***pestaña*** y ***%*** de ***zoom***.

### Para el height

Para ***obtener*** el ***height*** de la **pestaña*** del ***navegador***, se utiliza ***outerHeight***.

~~~
//Impresion de height de pestaña del navegador
console.log(window.outerHeight);
~~~

A continuación, un ejemplo de ***código*** para visualizar los ***inner*** y ***outer***:

~~~
//Asignacion de funcion de evento rezise al window
window.addEventListener("resize", (e) => {

	console.clear();
	console.log("--- Evento resize ---");

	//Impresion de tamaño de contenido del navegador
	console.log("---Tamaño de contenido---");
	console.log(window.innerWidth);
	console.log(window.innerHeight);

	//Impresion de tamaño de ventana de navegador
	console.log("---Tamaño de browser---");
	console.log(window.outerWidth);
	console.log(window.outerHeight);
});
~~~

Donde si de detecta un ***cambio de tamaño*** en el ***window*** se limpia la consola e imprimen los datos.

## Obtener distancia en Scrolls

Se puede ***obtener*** la ***distancia*** que existe entre los ***scrolls*** y el ***lado base***. con los ***atributos scroll***.

### Para Scrolls horizontales

Para obtener la ***distancia*** en los ***scrolls horizontales*** (eje ***x***) se utiliza ***scrollX***.

El ***lado base*** de los ***scrolls horizontales*** es ***left*** (izquierda).

~~~
//Impresion de distancia entre el scroll horizontal actual y left 0
console.log(window.scrollX);
~~~

***Nota:*** los ***scroolls*** dependerá del ***tamaño*** de la ***pestaña*** y ***%*** de ***zoom***.

### Para Scrolls verticales

Para obtener la ***distancia*** de los ***scrolls verticales*** (eje ***y***) se utiliza el ***atributo scrollY***.

El ***lado base*** de los ***scrolls verticales*** es ***top*** (arriba).

~~~
//Impresion de distancia entre el scroll vertical actual y top 0
console.log(window.scrollY);
~~~

A continuación, un ***código*** para visualizar la información de los datos de los ***scrolls***:

~~~
//Asignacion de funcion de evento scroll al window
window.addEventListener("scroll", (e) => {

	console.clear();
	console.log("--- Evento scrooll ---");

	//Impresion de distancia entre el scroll horizontal actual y left 0
	console.log(window.scrollX);

	//Impresion de distancia entre el scroll vertical actual y top 0
	console.log(window.scrollY);
});
~~~

El ***evento scroll*** se realiza, cada que se hace un ***scroll*** en el ***elemento asignado***; Por los tanto, cada que se haga ***scroll*** en el ***documento***, se ejecutara la ***función*** de ***evento***.

## Obtener posición de Ventana en Pantalla

Desde ***JavaScript***, también se puede obtener, la ***posición*** (px), de la ***pestaña*** de nuestro ***browser*** en relación a la ***pantalla***.

Para ello, se utilizan los atributos ***screen***.

### Para posición x

Para la ***posición x*** que es la ***horizontal***, se utiliza el ***atributo screenX***.

~~~
//Impresion de distancia horizontal de inicio de pestaña de navegador
console.log(window.screenX);
~~~

El ***resultado*** es la ***distancia*** que existe entre el ***left 0*** de la ***pantalla*** y el inicio de la ***pestaña*** del ***navegador***.

### Para posición y

Para la ***posición y*** que es la ***vertical***, se utiliza el ***atributo screenY***.

~~~
//Impresion de distancia vertical de inicio de pestaña de navegador
console.log(window.screenY);
~~~

El ***resultado*** es la ***distancia*** que existe entre el ***top 0*** de la ***pantalla*** y el inicio de la ***pestaña*** del ***navegador***.

Un ejemplo de código para visualizar los ***atributos screen***:

~~~
//EVento load
window.addEventListener("load", (e) => {

	console.log("--- Evento load ---");

	//Posicionamiento de ventana en pantalla
	console.log(window.screenX);
	console.log(window.screenY);

	//Tiempo que tarda en ejecutarse el evento
	console.log(e.timeStamp);
	//Menos eficiencia
});

//Evento DOMContentLoaded
document.addEventListener("DOMContentLoaded", (e) => {

	console.log("--- Evento DOMContentLoaded ---");

	//Posicionamiento de ventana en pantalla
	console.log(window.screenX);
	console.log(window.screenY);

	//Tiempo que tarda en ejecutarse el evento
	console.log(e.timeStamp);
	//Mas eficiencia
});
~~~

***Nota:*** Los tipos de ***eventos DOMContentLoaded*** y ***load*** son similares a simple vista, pero funciona de manera ***diferente***.

	- DOMContentLoaded: Se ejecuta al cargarse la pagina, pero NO necesitan cargarse todos los elementos secundarios (imagenes, estilos, etc.).
	- load: Se ejecuta al cargarse la pagina, incluyendo todos los elementos secundarios (imagenes, estilos, etc.).

Por lo tanto, es mas ***eficiente*** utilizar el ***evento DOMContentLoaded***.

