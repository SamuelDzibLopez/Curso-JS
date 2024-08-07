# 70. DOM: Element Modification (Old style).

Existen ***diferentes métodos*** para poder interactuar (***modificar***, ***agregar***, ***eliminar***, ***clonar***) con los ***elementos*** del ***DOM***.

En esta ***clase*** veremos algunos:

tendremos el siguiente ***código HTML***:

~~~
<div id="div">
	<p id="uno">Lorem.</p>
	<p id="dos">Lorem, ipsum.</p>
	<p id="tres">Lorem, ipsum dolor.</p>
	<p id="cuatro">Lorem ipsum dolor sit.</p>
</div>
~~~

Y en el ***archivo JavaScript***:

~~~
//Captura elemento con id "div" y asignacion en el identificador $div
const $div = document.getElementById("div");
~~~

## Clonar un Elemento

El ***método cloneNode*** permite poder ***clonar*** o ***copiar*** un ***elemento***.

Un ejemplo de sintaxis:

~~~
//Clonar un elemento
const $cloneElement = $div.cloneNode(true);
~~~

El ***parámetro true*** que recibe significa:

	- true: clonar el elemento con su contenido.
	- false: clonar el elemento sin su contenido.

Para luego poder utilizarlo como se desee:

~~~
//Agregar nuevo nodo hijo an body
document.body.appendChild($cloneElement);
~~~

## Reemplazar un Elemento

Para poder ***reemplazar*** un ***nodo elemento*** por otro, se utiliza el ***método replaceChild***:

Ejemplo de sintaxis:

~~~
//Creacion de nuevo elemento de tipo p y asignacion en el identificador $newElement
const $newElement = document.createElement("p");

//Asignacion de texto a $newElement
$newElement.textContent = "parrafo generado por JavaScript";

// Remplazar un nodo elemento en posicion [0] de $div por $newElement
$div.replaceChild($newElement, $div.children[0]);
~~~

***Nota:*** ***replaceChild*** recibe ***2 parametros***, el ***primero*** es el ***elemento nuevo***, mientras que el ***segundo*** es el ***elemento*** a ser ***reemplazado***, dentro del elemento especificado.

## Agregar un Elemento antes que otro

Para ***agregar*** un nuevo ***nodo*** antes que un ***nodo especificado***, utilizamos ***insertBefore***.

Ejemplo de sintaxis:

~~~
//Imgresar el elemento $newElement antes que el primer nodo elemento de $div
$div.insertBefore($newElement, $div.firstElementChild);
~~~

***Nota:*** Al igual que ***replaceChild***, el ***método insertBefore*** recibe ***2 parametros***, el ***primero*** es el ***elemento a ingresar*** y el ***segundo***, la referencia del ***elemento*** que deseamos que se coloque el nuevo antes.

## Eliminar un Elemento

Para ***eliminar*** un ***nodo*** dentro de una ***lista de nodo*** de un ***elemento***, para ello, se utiliza ***removeChild***:

~~~
//Eliminar el ultimo nodo elemento de $div
$div.removeChild($div.lastElementChild);
~~~

Recibiendo como ***parámetro*** el ***elemento*** a ***remover*** dentro del mismo ***elemento***.


