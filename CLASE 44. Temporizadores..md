
# 44. Timers (setTimeout & setInterval).

Estos ***métodos*** permiten la ***ejecución de código*** mediante ***temporizadores*** y periodos controlados de ***tiempo*** y ***ejecuciones***.

Para ello, existen ***2 métodos***:

	- setTimeout
	- setInterval

## setTimeout

Este ***método*** permite la ejecución de un bloque de código con un ***tiempo configurado de salida***.

La sintaxis simple de esta ***función*** se escribe de la siguiente manera:

~~~
//Estructura basica de setTimeout
setTimeout();
~~~

Donde dentro de este ***método*** se coloca una ***arrow function*** y el ***tiempo*** de retraso que tendrá la ***función*** en ***milisegundos***.

Quedando de la siguiente manera:

~~~
//Estructura completa de setTimeout
setTimeout(() => {
	
}, 1000);
~~~

***Nota:*** Este ***setTimeout*** tiene un ***temporizador*** de ***1 segundo*** por lo que el bloque dentro tardara ***1 segundo*** para ser ejecutado.

Un ejemplo:

~~~
console.log("Inicio");

//setTimeout de 1 segundo
setTimeout(() => {
	console.log("setTimeout, se ejecuta una sola vez");
}, 1000);
~~~

	setTimeout solo se ejecuta una vez.

## setInterval

***setInterval*** es similar a ***setTimeout***, pero este se ejecuta de manera ***indefinida***, de manera infinita por si sola, tomando un ***temporizador*** para el ***intervalo*** de ***ejecución*** y ***repetición***.

Su sintaxis simple es similar:

~~~
setInterval();
~~~

Donde dentro de este se agrega una ***función*** acompañada de un ***tiempo*** en ***milisegundos***:

~~~
//setInterval cada 2 segundos
setInterval(() => {
	
}, 2000);
~~~

El ***código*** dentro de la ***arrow function*** se ejecutara cada ***tiempo*** establecido.

Un ejemplo:

~~~
//setInterval cada 2 segundos
setInterval(() => {
	console.log("setInterval, se ejecuta inifitamente cada 2 segundos");
}, 2000);
~~~

Podemos hacer un reloj que muestre el tiempo:

~~~
//setInterval reloj

setInterval(() => {
	//Impresion de hora
	console.log(new Date().toLocaleTimeString());
}, 1000);
~~~

	setInterval se ejecuta infinitamente cada cierto tiempo

## clear setTimeout y setInterval

Podemos usar un ***método*** especial para poder borrar un ***setTimeout*** y un ***setInterval***.

Los ***métodos*** son

	clearTimeout();
	clearInterval();

un ejemplo de cada ***método***:

$$ clearTimeout()$$

~~~
//Timeout reloj

let temporizador = setTimeout(() => {
	//Impresion de hora
	console.log(new Date().toLocaleTimeString());
}, 1000);

//Limpiar Timeout
clearTimeout(temporizador);
~~~

$$ clearInterval()$$

~~~
//setInterval reloj
let temporizador = setInterval(() => {
	//Impresion de hora
	console.log(new Date().toLocaleTimeString());
}, 1000);

//Limpiar Interval
clearInterval(temporizador);
~~~

***Nota:*** Para hacer esto, basta con ***expresar*** el ***método set*** en un ***identificador*** y enviarlo como ***parámetro*** al ***método clear*** correspondiente.

