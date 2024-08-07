# 59. JSON.

	JavaScript Object Notation

Los ***JSON*** son un la ***notación*** con la que escriben los ***objetos*** estandardizada por ***JavaScipt***. los cuales son una manera muy utilizada para el ***envió*** y ***recepción*** de ***datos*** e ***información***; Tales como el ***front-End*** con el ***Back-End*** o las ***APIs***.

Esto es debido a su ***sintaxis*** muy ***simple*** y ***entendible***.

Un ejemplo de un ***JSON*** y sus valores:

~~~
//JSON
const json = {
	cadena: "cadena",
	numero: 32,
	booleano: true,
	arreglo: [1, 2, 3, 4],
	objeto: {
		nombre: "nombre",
		email: "Email@gmail.com"
	},
	nulo: null
}
~~~

***Nota:*** Como te darás cuenta, los ***JSON***, son simples ***objetos***.

## Creación de archivo JSON

Para poder crear un ***archivo JSON*** basta con colocar la extension ***.json***, tal como cualquier archivo a crear.

~~~
Datos.json
~~~

Y su sintaxis interna en estos ***archivos***, seria la siguiente:

~~~
{
	"cadena": "cadena",
	"numero": "32",
	"booleano": "true",
	"arreglo": "[1, 2, 3, 4]",
	"objeto": {
		"nombre": "nombre",
		"email": "Email@gmail.com"
	},
	"nulo": "null"
}
~~~

Donde:

	-No tiene un identificador, solo un contenido dentro de las { }.
	- Todos los nombres de los atributos son colocados entre " ".
	- Se recomienda colocar tambien entre " ", los valores, aunque no sean Strings, pero no es necesario.

También podría ser:

~~~
{
	"cadena": "cadena",
	"numero": 32,
	"booleano": true,
	"arreglo": [1, 2, 3, 4],
	"objeto": {
		"nombre": "nombre",
		"email": "Email@gmail.com"
	},
	"nulo": null
}
~~~

## Métodos de los JSON

***JSON*** tiene ***2 métodos*** para poder ser utilizados, los cuales son:

	- Parse
	- Stringify

Podemos ver los ***métodos*** imprimiendo la clase ***JSON***.

~~~
console.log(JSON);
~~~

### Parse

El ***método parse*** se utiliza para poder convertir un ***string*** el cual tenga una ***sintaxis correcta*** a un ***objeto*** reconocible para ***JS***. El ***objeto*** no tiene que ser un ***objeto literal*** del ***JS***.

La ***sintaxis*** de ***parse*** es:

~~~
JSON.parse();
~~~

Unos ejemplos:

~~~
//Objetos
console.log(JSON.parse("{}"));

//Arreglos
console.log(JSON.parse("[]"));

//Boleanos
console.log(JSON.parse("true"));

//Numeros
console.log(JSON.parse("19"));
~~~

***Nota:*** Existe una pequeña ***excepción*** de las ***cadenas de texto*** en esta regla.

Los ***strings*** solo son aceptados si son ***objetos literales*** escritos de manera ***correcta***:

~~~
console.log(JSON.parse('{"cadena": "cadena","numero": "32","booleano": "true","arreglo": "[1, 2, 3, 4]","objeto": {"nombre": "nombre","email": "Email@gmail.com"},"nulo": "null"}'));
~~~

***Nota:*** Todo el ***string*** debe escribirse ***en una sola linea***, dentro de ***' '*** , ademas de escribirse de manera ***correcta*** sin errores de sintaxis.

## Stringify

Este ***método*** hace todo lo ***contrario*** a ***parse***, convirtiendo los ***objetos*** en ***strings***.

Su sintaxis simple es:

~~~
JSON.stringify();
~~~

Unos ejemplos:

~~~
//Arreglos
console.log(JSON.stringify([1, 2 , 3]));

//Boleanos
console.log(JSON.stringify(true));

//Numeros
console.log(JSON.stringify(19));
~~~

### Stringify con objetos literales:

Al usar el ***stringify*** con un ***objeto literal*** de ***JS***, este se convierte en ***formato JSON estandar***, colocando ***" "*** a los ***nombres*** de los ***atributos***.

Aquí un ejemplo:

~~~
//Objeto literal
const json = {
	cadena: "cadena",
	numero: 32,
	booleano: true,
	arreglo: [1, 2, 3, 4],
	objeto: {
		nombre: "nombre",
		email: "Email@gmail.com"
	},
	nulo: null
}

//Impresion de stringify de un objeto
console.log(JSON.stringify(json));
~~~

De esta manera, podrá entenderlo cualquier ***lenguaje*** externo.
