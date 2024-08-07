
# 29. Short Circuit Operators.

Los ***operadores de corto circuito*** sirven para poder ***asignar valores*** a los parámetros de un ***método*** o ***función***, cuando estos no reciben un ***valor***.

Existen ***2 tipos*** de ***operadores de corto circuito***.

	Operador corto circuito con OR (||)
	Operador corto circuito con AND (&&)

## Operador corto circuito con OR (||)

Este ***operador*** cambia el valor de la ***parámetro*** si se encuentra como un valor que tiende a ***false***, por medio de un ***operador boolean***.

No necesariamente para una ***función***.

Un ejemplo:

~~~
//Declaracion de funcion
function saludar (nombre) {
	//Operador de corto circuito
	nombre = nombre || "Desconocido";
	console.log(`Hola ${nombre}`);
}

//Llamado a funcion con parametro
saludar("Alberto");

//Llamado a la funcion sin parametro
saludar();
~~~

Cuando el ***valor*** del ***parámetro*** tiende a ***true*** tomará el valor de la ***izquierda***, si tiende a ***false*** tomará el de la ***derecha***.

Un ejemplo mejor:

~~~
//true
console.log(true || "Hola");
console.log(1 || "Hola");

//false
console.log(false || "Hola");
console.log(0 || "Hola");
~~~

## Operador corto circuito con AND (&&)

A diferencia del operador ***||*** el ***&&*** tomara el ***primer valor*** (de la ***izquierda***)  cuando este tienda a ***true***.

Si el ***primer valor*** tiende a ***false*** tomara ese como ***defecto***.

Con el mismo ***ejemplo***, pero con ***&&***:

~~~
//Declaracion de funcion
function saludar (nombre) {
	//Operador de corto circuito
	nombre = nombre && "Desconocido";
	
	console.log(`Hola ${nombre}`);
}

//Llamado a funcion sin parametro
saludar();
~~~

A ***nombre*** tender a ***false*** (***undefined***), se toma ese ***valor***.

Lo mismo sucede con otros ejemplos:

~~~
//true
console.log(true && "Hola");
console.log("Hola" && false);
console.log([1] && [2]);

//false
console.log(false && "Hola");
console.log("" && [1]);
console.log(null && 2);
~~~

***Nota:*** Estos ***operadores*** eran muy útiles antes de poder utilizar ***inicialización de parámetros***.