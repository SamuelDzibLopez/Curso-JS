
# 46. Callbacks.

	JavaScript es un lenguaje single thread.
	Las tareas de I/O son Asincronas- No bloqueantes.

Las ***Callbacks*** son las ***llamadas de vueltas***  de funciones que se ejecutan después que otra lo haga.

Es una manera para poder ***controlar*** la ***asincronia*** y datos que se devuelven para ser utilizados.

	Las Callbacks son el mecanismo por defecto en JS para invocar algiunas de sus funciones o métodos.

Un ejemplo, de ejecución de un ***callback***:

~~~
//Funcion que recibe un valor y una callback
function cuadradoCallback (value, callback) {

	//setTimeout con ttemporizador de 0-10 segundos
	setTimeout(()=> {
	//Ejecucion del callback
	callback(value, value * value);
	}, 0 || Math.random()*1000);
}

//Invocacion de funcion, enviando como parametros un valor y una arrow function
cuadradoCallback(0, (value, result) => {
console.log("Inicia ballback");
console.log(`Callback: ${value}, ${result}`);
});
~~~

Esto esta bien, pero que sucede cuando necesitamos mas de un ***callback*** en una ***función***.

~~~
//Funcion que recibe un valor y una callback
function cuadradoCallback (value, callback) {

//setTimeout con ttemporizador de 0-1 segundo
setTimeout(()=> {

		//Ejecucion del callback
		callback(value, value * value);
	}, 0 || Math.random()*1000);
}

  

//Invocacion de funcion, enviando como parametros un valor y una arrow function

//Primera callback
cuadradoCallback(0, (value, result) => {

	console.log("Inicia ballback");
	console.log(`Callback: ${value}, ${result}`);

	//Segunda callback
	cuadradoCallback(1, (value, result) => {
		console.log(`Callback: ${value}, ${result}`);

		//Tercara callback
		cuadradoCallback(2, (value, result) => {
			console.log(`Callback: ${value}, ${result}`);

			//Cuarta callback
			cuadradoCallback(3, (value, result) => {
				console.log(`Callback: ${value}, ${result}`);
			});
		});
	});
});
~~~

Este problema se conoce como ***callback hell*** y presenta problemas como:

	Problemas de legibilidad
	Gran cantidad de codigo
	Repeticion de validaciones de respuestas

Podemos ver mas información en la pagina:

	http://callbackhell.com/

Para estos ***problemas*** se utiliza la ***modularizacion***, las ***promesas***, ***generadores*** y las ***funciones asincronas***.

