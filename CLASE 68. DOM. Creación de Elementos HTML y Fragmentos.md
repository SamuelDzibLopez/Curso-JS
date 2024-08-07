# 68. DOM: Creating HTML Elements and Fragments.

Ademas de ***manipular*** los ***elementos HTML*** ya existentes den el ***DOM***. ***JavaScript*** permite la creación e implementación de ***nuevos elementos***.

Para los ejemplos de esta ***lección*** utilizaremos el código ***HTML***:

~~~
<div id="div"></div>
~~~

Un ***div*** con un ***id*** para poder ser ***capturado*** por ***JS*** y ser ***utilizado***.

Y en el archivo ***.js***:

~~~
//Asignacion de elemnto HTML con id "div" a identificador $div
const $div = document.getElementById("div");
~~~

Antes, definamos ***mejor*** que es un ***nodo***:

	Tanto un ELEMENTO como un TEXTO son un NODO, y son utilizados para poder implementarse dentro de un elemento, tanto creado como capturado.

## Creación de nodo Elemento HTML

Para crear un ***elemento HTML*** que podría ser ***implementado*** en el ***árbol del DOM***, utilizamos el ***método createElement*** de ***document***:

Un ejemplo:

~~~
//Creacion de nodo elemento HTML de etiqueta "p"
const $element = document.createElement("p");
~~~

Este ***método*** recibe como ***parámetro*** el nombre de la ***etiqueta HTML*** que creara el ***elemento***, en formato ***string***.

	De esta manera, AUN NO se ha implementado en el DOM, UNICAMENTE a sido declarado.

## Creación de nodo Texto HTML

También podemos crear un ***nodo*** de tipo ***texto***, para poder ser implementado en un ***nodo*** de tipo ***elemento***.

Para ello, utilizamos el ***método createTextNode***:

~~~
//Creacion de nodo texto con valor "lorem"
const $elementText = document.createTextNode("lorem");
~~~

Este ***método*** recibe un ***parámetro*** en formato ***string***, definiendo el ***texto***.

## Agregar nodo a Elemento

Después de haber ***creado*** o ***capturado*** un ***nodo***, tanto ***elemento*** como ***texto***, podemos ***agregarlo*** a un ***elemento***.

	Podemos agregar un Nodo Elemento a un Nodo 
	Elemento
	Podemos agregar un Nodo Texto a un Nodo Elemento

Un ejemplo de la primera situación:

~~~
//Implementacion de nodo text a elemento 
$element.appendChild($elementText);
~~~

***Nota:*** Agregamos el ***texto*** dentro del ***elemento*** que es una ***etiqueta p***.

De la segunda situación:

~~~
//Implementacion de nodo Elemento a elemento capturado 
$div.appendChild($element);
~~~

***Nota:*** Agregamos el ***elemento creado $element*** que es un ***p*** en el ***div***.

	Tambien podemos agregar un nodo Elmento o texto, a un Nodo creado, no necesariamente solo a un elemento capturado.

***Nota:*** También podemos agregar ***texto*** con los ***atributos vistos*** en la ***CLASE 66*** .

## Creación de Elementos con ForEach

Tomando en cuenta lo ***enseñado***, podemos utilizar un ***arreglo*** y un ***forEach*** para generar ***elementos***.

Tenemos un ***array***:

~~~
//Creacion de array
let arreglo = ["uno", "dos", "tres", "cuatro"];
~~~

Y deseamos crear un ***ol*** que cada ***li*** se agrege dentro del ***elemento $div***.

~~~
//Asignacion de elemento HTML con id "div" a identificador $div
const $div = document.getElementById("div");

//Creacion de nuevo Elemento HTML "ol" y asignacion a identificador $element
const $element = document.createElement("ol");

//ForEach del arreglo
arreglo.forEach((el) => {

	//Creacion de nuevo elemento HTML "li" y asignacion a identificador $li
	const $li = document.createElement("li");

	//Asignacion de texto con textContet con valor del el iterable en turno
	$li.textContent = el;

	//Agrega el elemento HTML $li en el nodo a elemento $element 
	$element.appendChild($li);
});

//Agrega el elemento HTML $$element en el nodo a elemento $div 
$div.appendChild($element);
~~~

***Nota:*** Existen otras maneras diferentes para ***realizarlo*** (templates, etc).

Otra solución:

~~~
const $div = document.getElementById("div");

const $element = document.createElement("ol");

$element.innerHTML = ""

arreglo.forEach((el) => {
	$element.innerHTML += `<li>${el}</li>`;
});

$div.appendChild($element);
~~~

Intenta entender el código.

## Creación de fragmento

Los ***fragmentos*** son un ***contenedor*** que permite poder ***almacenar nodos*** para luego poder ser utilizados como un conjunto.

Para crear un ***fragmento***, utilizamos la sintaxis:

~~~
//Creacion de fragmento y asignacion de valor a identificador $fragment 
const $fragment = document.createDocumentFragment();
~~~

Para luego poder ***ingresar nodos***.

## Insertar nodo dentro de fragmento

Al igual que los ***nodos*** comunes, para ingresar un ***elemento*** dentro del ***fragment*** utilizamos el ***método appendChild***.

Su sintaxis:

~~~
$fragment.appendChild($elemento);
~~~

## Agregar fragmento a Elemento

Igual, para agregar un ***fragment*** se utiliza ***appendChild***.

Ejemplo de sintaxis:

~~~
$elemento.appendChild($fragment);
~~~

Idéntico a cualquier agrego de ***nodo***.

***Nota:*** Los ***fragment*** no son renderizados en el ***DOM*** de la ***interfaz***.

***Nota:*** Los ***fragment*** permiten poder ejecutar una sola ***inserción*** en el ***DOM***, mejorando el ***rendimiento*** de el código.

Un ejemplo de ***implementación*** de ***fragmentos***:

~~~
//Arreglo
let arreglo = ["uno", "dos", "tres", "cuatro"];

//Asignacion de elemnto HTML con id "div" a identificador $div
const $div = document.getElementById("div");

//Creacion de elemento de tipo "ol" y asignacion en identificador $element
const $element = document.createElement("ol");

//Creacion de fragmento y asignacion en identificador $fragment
const $fragment = document.createDocumentFragment();

//ForEach de arreglo
arreglo.forEach((el) => {

	//Creacion de elemento de tipo "li" y asignacion en identificador $li
	const $li = document.createElement("li");

	//Asignacion de valor de atributo textContent de $li como el el en turno del forEach
	$li.textContent = el;

	//Insercion de nodo elemento $li en $fragment
	$fragment.appendChild($li);

});

//Insercion de nodo elemento $fragment en $element
$element.appendChild($fragment);

//Insercion de nodo elemento $element en $div
$div.appendChild($element);
~~~