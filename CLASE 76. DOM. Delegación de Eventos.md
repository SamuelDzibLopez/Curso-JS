# 76. DOM: Events Delegation.

La ***delegación*** de los ***eventos*** se llama a la ***forma*** en la cual se ***detectan*** los ***eventos*** y despliega la ***programación*** agregando un solo ***tipo*** de ***evento*** al ***elemento document*** (document se encuentra dentro de window).

En la ***delegación de eventos*** solo se ***asigna*** un solo ***evento*** de ***tipo***, y con ayuda de ***condicionales*** se detecta el ***elemento*** y despliega la ***programación***.

Para esta ***lección*** utilizaremos la misma ***estructura HTML***:

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

Con los ***estilos CSS***:

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

En la ***clase anterior*** se asigno una ***función*** de ***evento*** a cada ***elemento***, en la ***delegación de eventos*** solo se asigna al ***document***.

Ejemplo de delegación de eventos:

~~~
//Funcion para divs (parametro event)
function funcionEvento (e) {

	console.log(`hola, te saluda ${e.target.className} (realmente ${this}), el click lo origino ${e.target.className}`);
}

//Asignacion de evento click al document con funcion con condicionales y parametro event
document.addEventListener("click", (e) => {

	console.log("Clik en el", e.target);

	//Si el evento se origina en el elemento
	if (e.target.matches(".event-flow a")) {

		alert ("Click al Enlace");
		//Metodo preventDefault
		e.preventDefault();

	//Si el evento se origina en el elemento
	} else if (e.target.matches(".event-flow div")) {

		//Ejecucion de funcion funcionEvento con parametro event
		funcionEvento(e);
	}

});
~~~

***Nota:*** Cada vez que se ejecuta el ***evento click*** en el ***document***, se condiciona si el ***elemento*** que lo origino es alguno, con los condicionales, y si es el caso, se ejecuta su respectivo código.

Este tipo de ***asignación*** de ***eventos*** es muy ***útil*** al momento de ***renderizar elementos*** dinámicos, sin contar la carga baja que influye.

	Este metodo no necesariamente debe ser utilizado en document, puede ser utilizado en forms (para delegar eventos de los inputs) o en secciones especificas, para generalizar codigo.



