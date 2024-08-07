
# 54. Generators.

Los ***generadores*** o ***funciones generadoras*** son ***funciones*** que permiten poder utilizar los ***iteradores*** de una manera mas simple y efectiva.

***Declarar*** una ***función generadora*** es muy simple, basta con declarar una funcion comun, acompañada de un * **.

Un ejemplo de la sintaxis:

~~~
//funcion generadora
function* iterable () {
}
~~~

Dentro de esta ***función*** se coloca una ***palabra reservada***:

	yield

***yield*** funciona como un ***return*** pero para ***funciones generadoras***.

Un ejemplo de como funcionan las ***funciones generadoras***.

Tenemos esta ***función generadora***.

~~~
//funcion generadora
function* iterable () {
	//Primera iteracion
	yield "Hola";
	console.log("Hola consola");

	//Segunda iteracion
	yield "Hola2";
	console.log("Seguimos con mas intrucciones de nuestro codigo");

	//tercera iteracion
	yield "Hola3";

	//Cuarta iteracion
	yield "Hola4";
}
~~~

La manera de poder ***generar*** una ***iteracion*** de su contenido es:

~~~
//Ejecucion de funcion generadora y guardar yield (return)
//Obtencion de iterador
let iterador = iterable();

//Impresion de iteraciones
console.log(iterador.next());
console.log(iterador.next());
console.log(iterador.next());
console.log(iterador.next());
~~~

***Nota:*** Los ***yield*** funcionan similar a los ***returns***, la iteracion en turno se detiene, hasta encontrar el siguiente ***yield***, o cuando ya no hay mas código en la función.

---
En los ***iteradores sin funciones generadoras*** era necesario la siguiente sintaxis:

~~~
//Acceder al iterador del iterable
const iterador = iterable[Symbol.iterator]();
~~~

En las ***funciones generadoras*** basta con:

~~~
let iterador = iterable();
~~~

acompañado del *.

Cumple la misma función.

Un código mas ***simplificado***:

~~~
//funcion generadora
function* iterable () {

	//Primera iteracion
	yield "Hola";
	console.log("Hola consola");

	//Segunda iteracion
	yield "Hola2";
	console.log("Seguimos con mas intrucciones de nuestro codigo");

	//tercera iteracion
	yield "Hola3";

	//Cuarta iteracion
	yield "Hola4";
}

//Ejecucion de funcion generadora y guardar yield (return)
//Obtencion de iterador
let iterador = iterable();

//for of para iterar el iterador
for (let y of iterador) {
	console.log(y);
}
~~~

Para poder guardar todos los ***datos*** de todas las iteraciones, basta con:

~~~
//Creacion de array y guardar cada iteracion de iterable en una posicion
const array = [...iterable()];

//Impresion del array
console.log(array);
~~~

En ***conclusión***:

	Un Generador es convertir un codigo de una funcion en iterable