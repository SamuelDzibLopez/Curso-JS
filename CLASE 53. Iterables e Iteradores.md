
# 53. Iterables & Iterators.

Los ***iterables*** son ***estructuras de datos*** que permiten poder recorrer su contenido de manera ***unitaria***, por ello, son ***estructuras lineales***.

Un ***iterador*** es el ***apuntador*** con el cual se puede recorrer el ***elemento iterable***.

Para estos ***elementos JavaScript*** tiene un ***método*** muy peculiar para recorrer por si mismos estos.

El ***iterator*** y el ***next***:

Un ejemplo simple y practico de la explicación:

~~~
//Iterable
const iterable = [1, 2, 3, 4, 5];

//Acceder al iterador del iterable
const iterador = iterable[Symbol.iterator]();

//Impresion de iterable
console.log(iterable);

//Impresion del iterador
console.log(iterador);

//Iteracion

//Impresion de elemento siguiente con next
console.log(iterador.next());
console.log(iterador.next());
console.log(iterador.next());
console.log(iterador.next());
console.log(iterador.next());
console.log(iterador.next());
~~~

Primero accedemos al ***método iterador*** del elemento ***iterable*** con ayuda de un ***symbol*** y el ***iterator***.

Despues podemos usar el ***método next*** para poder iterar el ***iterador*** con ayuda de su ***metodo iterador*** creado.

***Nota:*** esta manera funciona con cualquier tipo de dato ***iterable***.

El ***método next*** devuelve un ***objeto*** con ***2 atributos*** por iteracion:

	value
	done

El ***value*** devuelve el valor del ***elemento*** en turno de la ***iteración***.

El ***done*** devulve un ***boolean***, devolvera ***true*** si el ***iterable*** ha terminado, es decir, no hay elemento, y ***false*** cuando aun existen un ***elemento*** en el numero de iteracion presente.

Por los tanto, un codigo mas simplificado:

~~~
//Iterable
const iterable = [1, 2, 3, 4, 5];

//Acceder al iterador del iterable
const iterador = iterable[Symbol.iterator]();

//Ejecucion de primera iteracion
let next = iterador.next();

//Iteracion

//Mientras done de la iteracion sea false
while (!next.done) {

	//Impresion de value
	console.log(next.value);

	//Ejecucion de iteracion
	next = iterador.next();
}
~~~

De esta manera, este ***código*** puede funcionar con ***cualquier elemento iterable***.

Intente cambiar el tipo de dato de ***iterable***:

	set:
	
~~~
const iterable = new Set ([1, 1, 2, 3, 4, 4, 5]);
~~~

	string:

~~~
const iterable = "Hola mundo";
~~~

	map:

~~~
const iterable = new Map ([
	[true, 12],
	["nombre", [1, 2, 3 ,4]],
]);
~~~