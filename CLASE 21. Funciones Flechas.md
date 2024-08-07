
# 21. Arrow Functions.

Las ***Arrow Functions (Funciones Flechas)*** son una mejora que **ES6** implementó para poder escribir nuestra sintaxis de ***funciones*** de una manera mas expresiva.

Ademas, también las ***Arrow Functions*** tienen una serie de características para las que pueden ser utilizadas de manera de ventaja sobre las ***funciones comunes***.

Algunas de las ***Ventajas*** o ***Características*** son: 

	- Permiten la definir funciones anonimas.
	- Permiten declarar funciones expresadas (asignación de funcion a una variable).
	- Permiten return implicitos.
	- Tiene un contexto del scope.

Para convertir una ***función expresada común*** a una ***arrow function*** simplemente hacemos unos cambios en la sintaxis.

Supongamos que tenemos la siguiente función expresada:

~~~
//Funcion expresada

const saludar = function () {
	console.log("Saludar");
}

saludar();
~~~

Donde a la constante ***saludar*** contiene a la función.

Construyamos una ***Arrow Function*** con una nueva constante, basándonos en la anterior función.

Para ello, seguiremos unos simples pasos:

	- Eliminar la palabra reservada "function"
	- Colocar entre los parentesis de los parametros y las llaves una =>

Quedando de la siguiente forma:

~~~
//Arrow Function

const saludo = () => {
	console.log("Saludo");
}

saludo();
~~~

## Arrow functions de una sola linea

***Nota:*** Cuando nuestra ***Arrow Function*** solo tiene una sola linea de código dentro, (Como en el caso del **console.log** o alguna otra instrucción), Podemos sustituir aun mas la función.

	Eliminando las {} de la función.

Quedando similar a la función de a continuación.

~~~
//Arrow Function

const saludo = () => console.log("Saludo");

saludo();
~~~

De esta manera, el código de la función parece mas legible. 

## Arrow Functions de un solo parámetro

Cuando nuestra ***Arrow Function*** solo recibe un parámetro, podemos simplificar aun más nuestra función

	- Eliminando los parentesis de parametros

Quedando como ejemplo la siguiente sintaxis:

~~~
//Arrow Function

const saludo = nombre => console.log(`Hola ${nombre}`);

saludo("Samuel");
~~~

***Notas:*** Si la función no recibe parámetros, o recibe mas de uno, los paréntesis tienen que colocarse.

## Arrow Functions y Returns Implícitos

Otra característica de las ***Arrow Functions*** es la de **retornar de manera implícita** un valor o identificador.

Si no tuviéramos una ***Arrow function***, tendríamos que escribir como el siguiente ejemplo:

~~~
//Funcion sumar

const sumar = function (a ,b) {
	return a + b;
}

console.log(sumar(1, 2));
~~~

Pero, podríamos ahorrar código, si utilizáramos una ***Arrow Function***, aprovechando su característica de ***return implícito***.

~~~
//Arrow function

const suma = (A, B) => A + B;

console.log(suma(2, 3));
~~~

## Arrow Functions en datos Compuestos

Las ***Arrow Functions*** tambien pueden ser utilizadas dentro de metodos para elementos compuestos, tales como ***objetos*** o ***arrays***.

Un ejemplo, es el siguiente código, basado en un ***forEach*** de un ***array***.

~~~
//Arrow Function en arrays

const numeros = [1, 2, 3, 4, 5];

numeros.forEach((el, index) => console.log(`${el} esta en la pocision ${index}`));
~~~

***Nota:*** Esta función puede utilizarse en cualquier método que sea compatible.

## Arrow Functions y .this

Otra de las características de las ***Arrow Functions*** son la capacidad de poder obtener el contexto del objeto donde se encuentran.

Es decir, cuando obtenemos el ***.this*** dentro de una ***arrow function***, podemos obtener el contexto del elemento padre donde se encuentran, el vez de obtener el contexto de si mismo, como sucedería en una función expresada comúnmente.

Para una mejor comprensión, el siguiente código hace un ejemplo:

~~~
// Funcion expresada comun

const gato = {
	nombre : "Misho",
	maullar : function () {
		console.log(this);
	}
}

gato.maullar();
~~~

En una ***función comun***, el elemento ***.this*** es en si, el mismo elemento; En el ejemplo anterior seria por si mismo ***gato***.

Pero observemos la diferencia entre una ***arrow function***.

~~~
//Arrow Function

const perro = {
	nombre : "Firulais",
	ladrar: () => {
		console.log(this);
	}
}
perro.ladrar();
~~~

En el anterior, el elemento ***.this*** no sera en si el elemento superior, si el objeto ***perro*** esta en el cuerpo principal, entonces el ***.this*** sera el elemento ***window***.

De esta manera, podemos subir sobre el contexto de nuestro codigo y facilitar la lectura datos superiores.







