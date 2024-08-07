# 74. DOM: Flow of Events (Bubble and Capture).

En ***JavaScript*** los ***eventos*** tienen ***2 tipos*** de ***flujos*** de ***eventos***, los cuales son:

	- Burbuja (Los eventos se ejecutan de adentro hacia afuera).
	- Captura (Los eventos se ejecutan de afuera hacia adentro).

Es decir, cuando tenemos un ***mismo tipo de evento*** (click, etc.) anidado al ejecutarse, estos se ***ejecutaran*** de este ***flujo***.

Esta ***modalidad*** puede ser ***definida*** en el ***tercer parámetro*** de la invocación del ***addEventListener***.

Para esta ***lección*** se utilizará la ***estructura HTML***:

~~~
<section class="event-flow">
	<div class="uno">
		1
		<div class="dos">
			2
			<div class="tres">
				3
			</div>
		</div>
	</div>
</section>
~~~

Con unos ***estilos***, para poder visualizar ***mejor*** la ***estructura***:

~~~
.event-flow div {
	padding: 20px;
	font-size: 16px;
	text-align: center;
}

.uno {
	background-color: greenyellow;
}

.dos {
	background-color: crimson;
}

.tres {
	background-color: yellow;
}
~~~

En el ***archivo JavaScript*** capturaremos ***todos los divs***:

~~~
//Captura de todos los divs dentro de elemento con clase "event-flow" y almacenar en $divs
const $divs =document.querySelectorAll(".event-flow div");
~~~

Con estos ***recursos***, se explican los ***diferentes tipos*** de ***flujos***.

## Burbuja

Este es el ***flujo de eventos*** es el definido por ***default***. 

Podemos definirlo como un ***false*** como ***tercer parámetro***, o simplemente omitiendo el parámetro.

Un ejemplo:

~~~
//Funcion asignada para el evento
function funcionEvento (e) {
	console.log(`hola, te saluda ${this.className}, el click lo origino ${e.target.className}`);
}

//ForEach por cada elemento de $divs
$divs.forEach((div) => {

	//Definicion de flujo por default (burbuja)
	// div.addEventListener("click", funcionEvento);

	//Tercer parametro como false (burbuja)
	// div.addEventListener("click", funcionEvento, false);
});
~~~

Donde a cada ***div*** se le ***agrega*** la ***función funcionEvento*** al ***evento click***.

Este ***tipo de flujo*** recorre los ***eventos*** iniciando desde el ***elemento*** que genera el ***callback de eventos*** hasta el ***ultimo evento*** del ***elemento***.

	Click en el div 3
		
		- hola, te saluda tres, el click lo origino tres
		- hola, te saluda dos, el click lo origino tres
		- hola, te saluda uno, el click lo origino tres

		Click en el div 2
		
		- hola, te saluda dos, el click lo origino dos
		- hola, te saluda uno, el click lo origino dos


		Click en el div 1
		
		- hola, te saluda uno, el click lo origino uno

El ***flujo burbuja*** inicia el ***callback*** de ***eventos*** desde ***adentro*** hacia ***afuera***.

## Captura

El flujo ***captura***, al contrario del ***burbuja***, este inicia el ***callback*** de los ***eventos*** desde ***afuera*** hasta ***adentro***.

Un ejemplo:

~~~
//Funcion asignada para el evento
function funcionEvento (e) {
	console.log(`hola, te saluda ${this.className}, el click lo origino ${e.target.className}`);
}

//ForEach por cada elemento de $divs
$divs.forEach((div) => {

	// Tercer parametros como true (captura)
	div.addEventListener("click", funcionEvento, true);
});
~~~

El ***flujo*** tipo de ***captura*** se define colocando como ***3 parámetro*** el valor ***true***.


Este ***tipo de flujo*** recorre los ***eventos*** iniciando desde el ***ultimo elemento*** en el ***callback de eventos*** hasta el ***elemento*** que lo genera.

	Click en el div 3
		
		- hola, te saluda uno, el click lo origino tres
		- hola, te saluda dos, el click lo origino tres
		- hola, te saluda tres, el click lo origino tres

		Click en el div 2
		
		- hola, te saluda uno, el click lo origino dos
		- hola, te saluda dos, el click lo origino dos


		Click en el div 1
		
		- hola, te saluda uno, el click lo origino uno

El ***flujo captura*** inicia el ***callback*** de ***eventos*** desde ***afuera*** hacia ***adentro***.

## Objeto como 3 parámetro

También podemos pasar un ***objeto*** como ***3 parámetro***, el cual puede tener ciertos ***atributos*** para poder configurar el tipo de ***flujo*** y otra ***configuración***.

Un ejemplo:

~~~
//Funcion asignada para el evento
function funcionEvento (e) {
	console.log(`hola, te saluda ${this.className}, el click lo origino ${e.target.className}`);
}

//ForEach por cada elemento de $divs
$divs.forEach((div) => {

	//Tercer parametro como objeto
	div.addEventListener("click", funcionEvento, {

		//Tipo de captura (burbuja o captura)
		capture: false,
		
		//Ejecucion unica o no
		once: true
	});
});
~~~

El ***addEventListener*** recibe el ***objeto*** con los ***atributos capture*** y ***once***.

	- capture: Funciona como el parametro de flujo: false (burbuja) y true (captura).
	- once: true funciona para eliminar el evento cuando se ejecuta (para solo usarlo una vez), y false para siempre poder ser ejecutado (el evento puede ejecutarse infinitamente).



