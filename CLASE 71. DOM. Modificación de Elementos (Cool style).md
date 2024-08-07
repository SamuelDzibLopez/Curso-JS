# 71. DOM: Element Modification (Cool style).

A partir de ***ES6*** también existen otros ***nuevos métodos*** diferentes:

Estos ***métodos*** tienen la ***misma funcionalidad*** que los vistos en la ***lección anterior***, pero con sintaxis diferente.

Los ***métodos*** son los siguientes:

	.insertAdjacentElement(posicion, elemento)
	.insertAdjacentHTML(posicion, elemento)
	insertAdjacentText(posicion, elemento)

Cada uno de ellos, se utiliza para poder agregar ***contenido diferente*** a un ***elemento*** en el ***DOM***:

	.insertAdjacentElement = Agregar un nodo elemento
	.insertAdjacentHTML = Agregar texto con sintaxis HTML (plantillas)
	insertAdjacentText = Agregar texto explicito

Un ejemplo de su sintaxis:

~~~
//Agregar $Elemento dentro del DOM como hermano anterior de $Padre
$Padre.insertAdjacentElement("beforebegin", $Element);
~~~

## Posiciones

Cada uno de estos ***métodos*** recibe como ***primer parámetro*** la ***posición*** del ***elemento*** a ***ingresar***:

Existen ***4 posibles posiciones***:

	beforebegin (hermano anterior)
	afterbegin (primer hijo)
	beforeend (ultimo hijo)
	afterend (hermano siguiente)

***Nota:*** La ***posición elegida*** es tomando como referencia el ***elemento*** desde donde se ejecuta el ***método***.

Conocidas estas, conozcamos los ***métodos***, para ello, utilizaremos la ***estructura HTML*** siguiente:

~~~
<div id="div">
	<p class="uno">Lorem.</p>
	<p class="dos">Lorem, ipsum.</p>
	<p class="tres">Lorem, ipsum dolor.</p>
	<p class="cuatro">Lorem ipsum dolor sit.</p>
</div>
~~~

 Y en el ***archivo JavaScript***:

~~~
//Captura de elemento con id "div" y asignacion en identificador en $div
const $div = document.getElementById("div");
~~~

Capturamos el ***elemento div*** y almacenamos en ***$div***.

## insertAdjacentElement

Este ***método*** permite poder ***agregar*** al ***DOM*** un ***nodo elemento*** tomando como referencia para ***su posición*** un ***elemento capturado***.

Un ejemplo:

~~~
//Creacion de Elemento de tipo p
const $newElement = document.createElement("p");

//Agregar texto a elemento $newElement
$newElement.textContent = "parrafo generado por JavaScript";

//Insertar nodo Elemento $newElement como hernano anterior de $div
$div.insertAdjacentElement("beforebegin", $newElement);
~~~

La ***posición*** asignada es tomada como ***referencia*** de ***$div***.

## insertAdjacentHTML

Con este ***método*** se puede ***agregar*** al ***DOM*** un ***elemento*** que sea ***variable*** de tipo ***string*** con ***sintaxis HTML***, tomando como referencia para ***su posición*** un ***elemento capturado***.

Un ejemplo:

~~~
//Variable con valor string con sintaxis HTML
let template = `<p>hola</p>`;

//Insertar texto template con sintaxis HTML como hijo primero de $div
$div.insertAdjacentHTML("afterbegin", template);
~~~

## insertAdjacentText

Este ***método*** permite agregar ***texto explicito*** en el ***DOM*** que sea una ***variable string***, tomando como referencia para ***su posición*** un ***elemento capturado***.

Un ejemplo:

~~~
//Variable con valor string
let text = "Hola";

//consulta de selector de elemento de clase "uno" y asignacion en identificador en $parrafo
const $parrafo = document.querySelector(".uno");

//Insertar texto explicito como hijo ultimo de $parrafo
$parrafo.insertAdjacentText("beforeend", text);
~~~

***Nota:*** Este ***método*** no ***elimina*** el ***texto contenido*** antes, sino que ***agrega*** como un nuevo ***nodo*** este ***string***.

## Métodos Jquery

Ademas de los ***3 métodos anteriores***, existen ***otros 3***, conocidos por ser utilizados por ***Jquery*** en su mayoría.

Estos métodos son:

	after (Hermano siguiente)
	before (Hermano anterior)
	prepend (Primer hijo)
	append (Ultimo hijo)

~~~
//Ejemplos Jquery (Solo aceptan nodos elementos)

//Agregar como hermano siguiente
$div.after($newElement);

//Agregar como hermano anterior
$div.before($newElement);

//Agregar como primer hijo
$div.prepend($newElement);

//Agregar como ultimo hijo
$div.append($newElement);
~~~

***Nota:*** Estos ***métodos*** solo pueden ser utilizados con ***elementos nodos***, como si fuera ***insertAdjacentElement***.

Este tipos de ***métodos*** solo reciben un ***parámetro***, el cual es el ***elemento*** a ***agregar***.

