# 75. DOM: stopPropagation and preventDefault.

Los ***eventos*** tienen ***2 métodos*** importantes que influyen en su ***callback*** de ***eventos*** y ***funcionamiento***.

Estos son:

	- stopPropagation: Detiene el flujo de la desencadenacion de eventos.
	- preventDefault: Detiene el funcionamiento default del evento.

Para los ejemplos de esta lección utilizaremos la misma ***estructura HTML***, que la anterior:

~~~
<section class="event-flow">
	<div class="uno">
		1
		<div class="dos">
			2
			<div class="tres">
				3
				<a href="https://www.youtube.com" target="_blank">Enlace</a>
			</div>
		</div>
	</div>
</section>
~~~

Con un ***enlace*** en el ultimo ***div***.

Con los mismos ***estilos CSS***:

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

Para el ***JavaScript*** capturaremos los ***elementos*** y ***asignación*** de ***eventos*** en cada ***div***:

~~~
//Captura de todos los divs dentro de elemento con clase "event-flow" y almacenar en $divs
const $divs =document.querySelectorAll(".event-flow div");

//Captura del elemento a dentro de elemento con clase "event-flow" y almacenar en $enlace
const $enlace =document.querySelector(".event-flow a");

//Funcion asignada para el evento
function funcionEvento (e) {
	console.log(`hola, te saluda ${this.className}, el click lo origino ${e.target.className}`);
}

//ForEach por cada elemento de $divs
$divs.forEach((div) => {

	//Definicion de flujo por default (burbuja)
	// div.addEventListener("click", funcionEvento);
});
~~~

Justo como se enseño en la ***lección anterior***.

	Al hacer click se ejecuta el callback de eventos en flujo burbuja

## stopPropagation

El ***método stopPropagation*** elimina la ***desencadenación*** del ***callback*** de ***eventos*** que se ejecutan, sea el flujo que fuera (burbuja o captura).

***stopPropagation*** solo ejecuta el ***primer evento*** del ***callback***, dependiendo si es flujo ***burbuja*** (El mas interno) o ***captura*** (El más externo).

Con base en esto, modifiquemos nuestra ***función*** asignada a los ***eventos*** para aplicar este ***método***:

~~~
//Funcion asignada para el evento con metodo stopPropagation
function funcionEvento (e) {

	console.log(`hola, te saluda ${this.className}, el click lo origino ${e.target.className}`);

	//metodo stopPropagation (Solo se ejecuta el primer método del callback de eventos)
	e.stopPropagation();
}
~~~

***Nota:*** Con este ***método***, al hacer ***click*** en un ***elemento div*** solo se ***desencadenara*** el ***evento*** de ese ***elemento***.

## preventDefault

El ***método preventDefault*** en un ***evento*** permite poder invalidar el ***comportamiento*** por ***defecto*** de un ***elemento*** en el ***browser***.

Por ejemplo, ***evitar*** redirigir a pestañas, ***evitar*** recargos de ***pagina***, etc.

Para el ejemplo:

~~~
$enlace.addEventListener("click", (e) => {

	alert("Click en enlace");

	//metodo preventDefault
	e.preventDefault();

	//metodo stopPropagation
	e.stopPropagation();
});
~~~

Si se ***agrega*** el ***método preventDefault*** al ***evento click*** de un ***enlace***.
