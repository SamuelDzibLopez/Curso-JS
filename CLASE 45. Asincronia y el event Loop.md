
# 45. Asynchrony and the Loop event.

La ***asincronia*** es uno de los pilares principales de ***JvaScript***.

	JavaScript es un lenguaje de un solo subporceso.

	"Solo puede ejecutar una sola cosa a la vez".

La ***asincronia*** permite realizar ***largas solicitudes*** de red sin bloquear el ***hilo principal***.

Un ***hilo*** es el conteo mínimo en la computación para la realización de ***procesos***.

	Procesamiento single thread y multi thread.
	Operaciones de CPU y péraciones de I/O.
	Operaciones concurrentes y paralelas.
	Operaciones bloqueantes y No bloqueantes.
	Operaciones Sincronas y Asincronas.

En ***JavaScript*** existen ***2 tipos de código***:

	Codigo sincrono Bloqueante.
	Codigo Asincrono No bloqueante.

Con ***ayuda*** de la ***herramienta***:

	http://latentflip.com/loupe/

Puedes probar los ***ejemplos siguientes*** para entender mejor la clase.

## Sincrono bloqueante

Un ejemplo de un código ***sincrono bloqueante***:

~~~
console.log("Codigo sincrono");

console.log("Inicio");

function dos () {
	console.log("Dos");
}

function uno () {
	console.log("Uno");
	dos();
	console.log("Tres");
}

uno();

console.log("fin");
~~~

El ***orden*** de impresión es:

	Inicio
	Uno
	Dos
	Tres
	Fin

Donde cada ***proceso*** se ejecuta de manera ***sincrona*** y no pasa a la siguiente hasta ***terminar*** todos sus ***subprocesos*** de manera ***total***.

## Asincrono no bloqueante

Un ejemplo de un código ***asincrono no bloqueante***:

~~~
console.log("Inicio");

function dos() {
	setTimeout(function () {
	    console.log("Dos");
	}, 1000);
}

function uno() {
	setTimeout(function () {
		console.log("Uno");
	}, 0);
	dos();
	console.log("Tres");
}

	uno();
	console.log("Fin");
~~~

El ***orden*** de impresión es:


	Inicio
	Tres
	Fin
	Uno
	Dos

Los ***procesos asincronos*** terminan aun cuando no ha recibido la ***respuesta*** del servidor, y dejan paso a los ***sincronos***, para al final ***regresarlos.

No bloquean el ***hilo principal*** del código.


***JavaScript*** usa un modelo ***asincrono no bloqueante*** con un loop de eventos implementado en un ***solo hilo*** (single thread) para operaciones de entrada y salida (input y output).