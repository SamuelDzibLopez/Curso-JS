# 73. DOM: Events with Parameters and Remove Events.

Recordemos que ***toda función*** asignada a un ***evento***, ***SOLO*** puede recibir un ***parámetro***, el cual es en si, el ***evento*** mismo.

Para esta ***lección*** tendremos el siguiente ***código HTML***:

~~~
<button id="btn-parametros">Evento con Parametros</button>

<button id="btn-remover">Evento para Remover</button>
~~~

Dos ***botones***, uno para la explicación de ***eventos con parámetros***, y otra para ***remover eventos***.

## Eventos con parámetros

Como ya se ***explicó***, una ***función*** asignada a un ***evento*** solo podrá tener un ***parámetro***, el ***event***.

Por lo tanto tenemos el siguiente código:

~~~
//Captura de elemento con id "btn-parametros" y almacenar en $btn
const $btn = document.getElementById("btn-parametros");

//Funcion comun para ser invocada dentro de funcion de evento
function saludar (nombre = "Desconocid@") {
	alert(`Hola ${nombre}`);
	console.log(event);
}

//ERROR
//Agregar funcion saludar con el evento de click
$btn.addEventListener("click", saludar);
//ERROR (La funcion de evento no acepta parametros mas que event)
~~~

Si se ***asigna*** la ***función saludar*** (La cual recibe un parámetro) como ***función de evento click***, funcionara de manera ***ERRONEA***.

***Nota:*** Para ejecutar ***funciones*** con ***parametros*** en un ***evento*** debemos ***llamarlos dentro*** de la ***función de evento*** y ***NO ser asignados como tales*** (NO asignarlos como funciones de eventos).

Por ejemplo:

~~~
//Captura de elemento con id "btn-parametros" y almacenar en $btn
const $btn = document.getElementById("btn-parametros");

//Funcion comun para ser invocada dentro de funcion de evento
function saludar (nombre = "Desconocid@") {
	alert(`Hola ${nombre}`);
	console.log(event);
}

//Agregar arrow funcion con el evento de click (La funcion saludar se ejecuta dentro de la arrow function)
$btn.addEventListener("click", () => saludar("Luis"));
//CORRECTO

//Para mas de una linea de codigo
$btn.addEventListener("click", () => {
	saludar("Jorge");
	saludar("Jose");
});
//Correcto
~~~

Donde la ***función saludar*** es ***invocada*** dentro de la ***arrow function*** la cual es la ***asignada*** como ***función de evento***.

	Para EJECUTAR una FUNCIÓN COMO PARAMETROS debemos llamarla dentro de la funcion asignada del evento.

## Remover eventos

***JavaScript*** permite también poder ***remover*** los ***eventos*** al ***realizar acciones***.

Para ello, se utiliza el ***método removeEventListener***:

Este ***método*** recibe ***2 parámetros***, los cuales son:

	tipo de evento
	funcion a eleminar

El ***primer parámetro*** es el ***tipo de evento*** y el ***segundo***, la ***función de evento*** asignada a un ***identificador***.

POR LO QUE ESTO SIGNIFICA, que solo se pueden ***remover funciones de eventos*** asignados en ***identificadores***.

Un ejemplo:

~~~
//Remover eventos

//Captura de elemento con id "btn-remover" y almacenar en $btnRemover
const $btnRemover = document.getElementById("btn-remover");

//Arrow function expresada para ser asignada a un evento (Recibe un parametro (event))
const removerEvento = (e) => {

	alert(`Removiendo evento ${e.type}`);

	//Remover en $btnRemover la funcion "removerEvento" de evento dblclick
	$btnRemover.removeEventListener("dblclick", removerEvento);

	//Cambio de atributo disable(desabilitado) a true
	$btnRemover.disabled = true;
}

//Agregar en $btnRemover la funcion "removerEvento" de evento dblclick
$btnRemover.addEventListener("dblclick", removerEvento);
~~~

***Nota:*** Por obvias razones, el ***removeEventListener*** se invoca dentro de la ***función removerEvento*** asignada como ***addEventListener*** y se remueve a si misma.


	Para poder remover el evento (la funcion asignada al evento), debemos haber almacenado ese evento (funcion).








