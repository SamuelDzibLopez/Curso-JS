# 72. DOM: Event Handlers.

Los ***eventos*** se conocen como aquellos ***mecanismos***, los cuales permiten poder ejecutar código y desplegar acciones en el documento, tomando en cuenta las ***acciones*** del usuario.

Para más información:

	https://developer.mozilla.org/es/docs/Learn/JavaScript/Building_blocks/Events

Podemos ***describir*** los ***eventos*** a un ***elemento*** de ***3 diferentes formas***:

	- Eventos como Atributo HTML.
	- Eventos con Manejadores Semanticos.
	- Eventos con Manejadores Multiples.

A continuación, se explica cada uno y sus diferencias.
## Eventos como Atributo HTML

Se puede ***asignar*** un ***evento*** a un ***elemento*** de manera directa en nuestro ***archivo HTML***.

Para ello, se asigna el ***nombre del evento*** como si se tratase de un ***atributo*** común de una ***etiqueta***:

Un ejemplo:

~~~
<!--Boton con evento onlclick-->
<button onclick="alert('Hola mundo')">Evento con Atributo HTML</button>
~~~

***Nota:*** El ***código*** del ***evento***, puede ser definido, dentro del ***valor*** del ***atributo***, o llamado desde una ***función***  

~~~
<!--Boton con evento onlclick-->
<button onclick="alert('Hola mundo'); console.log(event);">Evento con
~~~

Código ***JavaScript***:

~~~
//Funcion
function holaMundo () {
	//Despliegue de alert
	alert("Hola mundo");

	//Impresion de objeto evento definido como defualt
	console.log(event);
}
~~~

	Todos los Eventos como Atributos empiezan con "on".

***Nota:*** Al ***ejecutar*** un ***evento***, se crea un ***objeto*** definido como ***event***, el cual contiene toda la ***información*** (tipo de evento, elemento que lo ocasiona, posición, etc.) sobre el ***evento***.

## Eventos como Manejadores Semánticos

También existe una forma en que se pueden ***asignar eventos*** conociéndose como ***manejadores semanticos***.

Esta ***manera*** se realiza ***asignando*** un ***valor*** a un ***atributo*** de un ***elemento capturado***, tal como lo haríamos como un ***objeto común:

Tenemos el ***elemento HTML***:

~~~
<!--Boton para evento con manejador semantico-->
<button id="btn-semantico">Evento con manejador Semantico</button>
~~~

Que contiene un ***id***, mediante el cual podremos ***capturar*** el ***elemento***.

Para luego, poder asignarle mediante un ***manejador semántico*** un ***valor*** al ***atributo*** del ***evento***:
 
~~~
//Captura de elemento con id "btn-semantico" y asignacion a identificador $btnSemantico
const $btnSemantico = document.getElementById("btn-semantico");

//Funcion
function holaMundo () {
	//Despliegue de alert
	alert("Hola mundo");

	//Impresion de objeto evento definido como defualt
	console.log(event);
}

//Manejador semantico con asignacion a evento onclick la funcion holaMundo
$btnSemantico.onclick = holaMundo;

//Manejador semantico con cambio de valor a evento onclick una funcion anonima
//Definicion de parametro event como e
$btnSemantico.onclick = function (e) {

	//Despliegue de alert
	alert("Hola mundo con manejador semantico");

	//Impresion de parametro e (event)
	console.log(e);

	//Impresion de objeto event
	console.log(event);
}
~~~

***Nota:*** Cuando se utilizan los ***manejadores semánticos*** solo se podrá ***asignar UNA función*** por ***tipo de evento***, si se asigna otro, cambiara el valor de ejecución de ***evento***.

	Las funciones asignadas a eventos, solo pueden recibir un solo parametro, el cual es en si mismo el objeto event de si mismo por estandar y buenas practicas, definido como e.

## Eventos como Manejadores Múltiples

Por ultimo, existen los ***eventos*** como ***manejadores múltiples***, los cuales, permiten poder ***agregar*** una nueva ***función de evento*** al tipo de ***evento***.

De esta manera, permiten ***ejecutar diferentes funciones*** asignadas a un solo ***tipo*** de ***evento***, cosa que los ***manejadores semánticos*** no pueden hacer.

Este ***método*** se llama:

	addEventListener

Entendiéndose como:

	Agregar detector de eventos.

Para el ejemplo, tendremos un ***elemento HTML***:

~~~
<!--Boton para evento con manejador multiple-->
<button id="btn-multiple">Evento con manejador Multiple</button>
~~~

Y nuestro ***codigo JavaScript***:

~~~
//Captura de elemento con id "btn-multiple" y asignacion a identificador $btnMultiple
const $btnMultiple = document.getElementById("btn-multiple");

//Funcion
function holaMundo () {
	//Despliegue de alert
	alert("Hola mundo");

	//Impresion de objeto evento definido como defualt
	console.log(event);
}

//Asignacion de nuevo detector de evento, de evento click y la funcion a ejecutar holaMundo
$btnMultiple.addEventListener("click", holaMundo);

//Asignacion de nuevo detector de evento, de evento click y una arrow function a ejecutar
//Definicion de objeto event como parametro e
$btnMultiple.addEventListener("click", (e) => {

	//Despliegue de alert 
	alert("Funcion de manejador de eventos multiples");

	//Impresion de tipo de evento, asignado dentro de parametro e(objeto event)
	console.log(e.type);
	
	//Impresion de elemento desencadenante del evento, asignado dentro de parametro e(objeto event)
	console.log(e.target);
});
~~~

El ***método addEventListener*** recibe ***2 parámetros***, el ***tipo de evento*** en formato ***string*** (sin la semántica ***on***), y la ***función*** (***definida*** o ***arrow function***) a ***agregar*** al ***detector*** de ***evento***.

***Nota:*** El ***atributo type*** de ***event*** permite obtener el ***tipo de evento*** que se ***desencadena***, mientras que el ***tarjet*** revuelve el ***elemento*** que ***desencadena*** dicho ***evento***.

## Eventos

Otros ***eventos***:

	- onclick (Al hacer click en el elemento) (botones y otros elementos).
	- onblur (Al dejar de interactuar con el elemento) (inputs y otros elementos).
	- onchange (Despues de cambiar el valor de el elemento) (inputs)
	- oninput (Al intentar cambiar el valor de el elemento) (inputs)
	- onabort (Al abortar el cargado de un elemento) (imagenes, videos y otros elementos).
	- oncanplay (Cuando el cargado de un elemento es lo suficiente para poder empezar) (imagenes, videos y otros elementos).
	- oncanplaythrough (Cuando finaliza todo el cargado de un elemento para poder mostrarse completo) (imagenes, videos y otros elementos).
	- oncontextmenu (Al intentar abrir el menu contextual, en su mayoria, "click derecho") (elementos)
	- ondblclick (Al hacer doble click en el elemento) (botones y otros elementos).
	- ondrag (Mientras se arrastre un elemento (debe tener el atributo draggable="true", para poder ejecutarse)) (elementos).
	- ondragend (Cuando se deje de arrastrar un elemento (debe tener el atributo draggable="true", para poder ejecutarse)) (elementos).
	- ondragstart (Cuando se intenta arrastrar un elemento (debe tener el atributo draggable="true", para poder ejecutarse)) (elementos).
	- onerror (Cuando existe un Error al cargar u obtener un elemento, ya sea por su fuente, ruta u otro error) (Imagenes, videos y otros elementos).
	- onfocus (Al intentar enfocar a un elemento) (inputs y otros elementos).
	- oninvalid (Al detectar (Al intentar enviar) un valor invalido) (inputs y otros elementos).
	- onkeydown (Al enfocar el elemento y presionar cualquier tecla (Algunos elementos es hacer click para enfocarlos)) (inputs y otros elementos).
	- onkeydown (Al enfocar el elemento y presionar una tecla con caracter imprimible (Algunos elementos es hacer click para enfocarlos)) (inputs y otros elementos).
	- onkeyup (Al enfocar el elemento y dejar de presionar cualquier tecla (Algunos elementos es hacer click para enfocarlos)) (inputs y otros elementos).
	- onload (Cuando un recurso (script, pagina (body) o estilo) se ha terminado de cargar) (recursos).
	- onmousedown (Al presionar cualquier boton del raton en el elemento) (Elemetos).
	- onmouseenter (Al pasar el cursor sobre el elemento) (Elementos).
	- onmouseleave (Al quitar el cursor sobre el elemento) (Elementos).
	- onsubmit (Cuando se envia un formulario) (formularios).
	- onreset (Cuando se resetea un formulario) (formularios).
	- onresize (Cuando el tamaño de el elemento cambia) (Elementos).
	- onscroll (Cuando se escrollea dentro del elemento) (Elementos).

Los ***eventos*** de los***manejadores múltiples*** se nombran igual, ***UNICAMENTE*** eliminando la palabra ***on***.

Ejemplos:

	onclick -> click
	onblur -> blur

Con los ***eventos*** en ***atributos*** y ***métodos semánticos*** inician con ***on***.

---

