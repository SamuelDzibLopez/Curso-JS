# 66. DOM: Text and HTML.

***JavaScript*** también permite poder ***interactuar*** con el ***contenido*** y ***texto*** de un ***elemento HTML***.

Existen al menos ***4 maneras*** diferentes para esto. ***propiedades*** de un ***elemento***.

Para los ***ejemplos*** de esta clase, utilizaremos el ***elemento HTML*** siguiente:

~~~
<p id="parrafo">Lorem ipsum dolor sit amet.</p>
~~~

Con un ***id*** de valor ***párrafo*** para ser capturado por ***JavaScript***, y un texto.

Para obtenerlo y almacenarlo en un ***identificador***:

~~~
//Almacenamiento en identificador $parrafo el elemento HTML con id "parrafo"
const $parrafo = document.getElementById("parrafo");

//identificador con valor de template string con etiquetas HTML
let text = `
	<p id="parrafo">Lorem ipsum dolor sit amet.</p>
	<p id="parrafo">Lorem ipsum dolor sit amet.</p>
	<p id="parrafo">Lorem ipsum dolor sit amet.</p>
`;

//Impresion de elemento $parrafo
console.log($parrafo);
~~~

## Atributo innerText

El ***atributo innerText*** permite ***interactuar*** con el ***contenido textual*** de un ***elemento***.

Un ejemplo

~~~
//Asigancion de valor de identificador text como valor innerText de $parrafo
$parrafo.innerText = text;
~~~

Este ***atributo innerText*** se encuentra ***DESESTANDARIZADA***, gracias a los ***3 nuevos atributos***, siguientes.

	Este atributo NO acepta texto HTML solo texto explicito.

## Atributo textContent

El ***atributo textContent*** realiza la misma ***acción*** que el ***método innerText***.

Un ejemplo:

~~~
//Asigancion de valor de identificador text como valor textContent de $parrafo
$parrafo.textContent = text;
~~~

***textContent*** reemplazo a ***innerText***, debido a su mejor interpretación de ***codigo HTML***.

	Este atributo NO acepta texto HTML solo texto explicito.

## Atributo innerHTML

A diferencia de ***textContent*** que solo interpreta ***texto explicito***, ***innerHTML*** logra interpretar ***etiquetas HTML*** para ser renderizadas en la interfaz de manera interpretada.

Un ejemplo:

~~~
//Asigancion de valor de identificador text como valor innerHTML de $parrafo, interpretando HTML
$parrafo.innerHTML = text;
~~~

	Este atributo SI acepta texto HTML interpretado.

## Atributo outerHTML

El ***atributo outerHTML*** es una mejora del ***innerHTML*** donde el ***elemento*** donde se colocará el ***contenido***.

Este ***elemento "padre"*** se convertirá en un ***fragment*** y renderizará el ***contenido HTML*** del contenido, sin mostrar el ***elemento padre***.

Un ejemplo:

~~~
//Asigancion de valor de identificador text como valor outerHTML de $parrafo, interpretando HTML y volviendo $parrafo como fragment
$parrafo.outerHTML = text;
~~~

	Este atributo SI acepta texto HTML interpretado.