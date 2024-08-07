
# 20. REST and Spread.

## Parámetro REST

El parámetro REST es una forma virtual en la que se puede ir agregando parámetros infinitos, ya sea a una función o a una variable.

Para ello usamos una sintaxis sencilla de los:

	...

A continuación, un ejemplo.

~~~
//Parametro REST (...)

function sumar (a, b, ...c) {
	let resultado = a + b;

	c.forEach(function (n) {
		resultado += n;
	});
	
	return resultado;
}

//Pruebas con diferente cantidad de parametros

console.log(sumar(1, 2));
console.log(sumar(1, 2, 3));
console.log(sumar(1, 2, 3, 4));

//Permite recibir una cantidad de parametros variable de una función 
~~~

***Nota:*** El código se entiende como todo lo que se escriba después del parámetro ***b*** sera un arreglo (es decir ***c***).

Debido a ello, ***c*** es tratado como un ***Array***, motivo por el que podemos usar método el ***forEach***.
## Spread Opeador o Operador de propagación

Cuando una expresión tenga que expandirse, como cuando tengamos que almacenar múltiples elementos, lo podamos hacer de manera sencilla.

Un ejemplo; Como cuando se ***necesite almacenar los elementos*** de dos o mas Arrays en un nuevo Array de una sola posicion.

A continuación, un ejemplo codificado:

~~~
//Spread Opeador (...)

//Declaracion de arrays

const array1 = [1, 2, 3, 4, 5];
const array2 = [6, 7, 8, 9, 0];
~~~

Tenemos ***2 Arrays***; Y deseamos crear uno nuevo, que almacené únicamente los elementos de ambos.

~~~
//Conversion de un nuevo array

//Error:
const array3 = [array1, array2];

//array3 es un propio array que tiene dentro array1 y array2
console.log(array3);

//Correcto
const array4 = [...array1, ...array2];

//array4 es un array que une los elementos de los 2 arrays
console.log(array4);
~~~

Utilizamos de la misma manera los (...).


