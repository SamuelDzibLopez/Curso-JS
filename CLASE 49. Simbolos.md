
# 49. Symbols.

Los ***symbols*** son un tipo de dato ***primitivo***, ingresado por ***ES6***.

Estos crean un ***identificador único*** en un ***dato***.

Por ejemplo, tenemos 2 ***identificadores***:

~~~
//Declaracion de identificadores tipo number

let numero = 20;
let edad = 20;
~~~

Y los queremos comparar:

~~~
//comparacion
console.log(numero === edad);
~~~

Esto dará como ***resultado***:

	true

Pero si declaramos los ***identificadores*** como ***symbols***, esto cambiara:

~~~
//Declaracion de identificadores de tipo Symbol
let numero = Symbol(20);
let edad = Symbol(20);

console.log(numero === edad);
~~~

Esto ***imprime***:

	false

Aunque:

~~~
console.log(typeof numero === typeof edad);
~~~

Sea:

	true

Al crear un ***Symbol  NO SE COLOCA*** la ***palabra  reservada new***.

## Symbols en atributos de objetos

Si deseamos ingresar un ***Symbol***, debemos declararlo de la siguiente manera:

~~~
//Declaracion de identificador Symbol
const NAME = Symbol();

//Creacion de objeto
const persona = {

	//Declaracion de symbol
	[NAME]: "Juan",

	//Declaracion de atributos
	NAME: "Juan"
}

//Impresion
console.log(persona);
~~~

***Nota:*** Podemos declarar un ***atributo*** con el nombre del ***Symbol***, ya que no afecta.

Para llamar un ***Symbol*** usamos la notación de ***[]***.

~~~
console.log(persona[NAME]);
~~~

Podemos declarar mas de un ***Symbol*** en un ***objeto***.

~~~
//Declaracion de identificadores Symbol
const NAME = Symbol();
const ID = Symbol();

//Creacion de objeto
const persona = {

	//Declaracion de symbols
	[NAME]: "Juan",
	[ID]: 12345,

	//Declaracion de atributos
	NAME: "Juan"
}

//Impresion
console.log(persona);
~~~

Para ver los valores:

~~~
console.log(persona[NAME]);
console.log(persona[ID]);
~~~

## Symbols en métodos de objetos

También podemos declarar ***métodos*** como ***Symbols***.

Para ello hacemos lo siguiente:

~~~
//Declaracion de Symbol SALUDAR
const SALUDAR = Symbol();

//objeto
const persona = {
	NAME: "juan"
}

  
//Declaracion de funcion en el objeto persona como simbolo SALUDAR
persona[SALUDAR] = function () {
	console.log("Hola");
}

//Impresion
console.log(persona);
~~~

Podemos usar este ***método Symbol*** con la ***notación []***.

~~~
//Invocacion de metodo Symbol

persona[SALUDAR]();
~~~

## Symbols como atributos ocultos

Los ***Symbols*** son una manera de poder ocultar ***atributos*** que no deseamos que se conozcan (se oculta su nombre de atributo).

Estos ***atributos ocultos*** no son mostrados como los ***atributos comunes***

Ejemplo:

~~~
//Declaracion de Symbols
const ID = Symbol();
const SALUDAR = Symbol();

//Objeto
const persona = {
	EDAD: 22,
}

//Declaracion de atributo
persona.NOMBRE = "Juan"

//Declaracion de atributo Symbol
persona[ID] = 12345;

//Declaracion de metodo Symbol
persona[SALUDAR] = function () {
	console.log("Hola");
}

//For in para ver propiedades del objeto
for (let propiedad in persona) {

	//Propiedad
	console.log(propiedad);

	//Valor de propiedad
	console.log(persona[propiedad]);
}
~~~

Un ejemplo, como en los ***for in***.

De esta manera, se dice que los ***Symbols*** en ***objetos*** son ***atributos privados***.

Para poder ver necesitamos el ***método getOwnPropertySymbols*** de ***Objet***.

~~~
console.log(Object.getOwnPropertySymbols(persona));
~~~

Este ***metodo*** solo devuelve un ***array*** con los ***Symbols*** y su ***descripción***.

## Descripción

El ***valor*** que recibe el ***Symbol*** se llama ***descripción***, y sirve para poder ingresar un valor o texto representativo del ***Symbol***.

Por ejemplo, en el siguiente código, le agregamos ***descripciones*** a los ***Symbols***.

~~~
//Declaracion de Symbols con descripcion
const ID = Symbol("Clave");
const SALUDAR = Symbol("F. saludar");

//Objeto
const persona = {
	EDAD: 22,
}

//Declaracion de atributo
persona.NOMBRE = "Juan"

//Declaracion de atributo Symbol
persona[ID] = 12345;

//Declaracion de metodo Symbol
persona[SALUDAR] = function () {
	console.log("Hola");
}

//Impresion de objeto
console.log(persona);
~~~

Esta ***descripcion*** no afecta el valor del ***Symbol***, solo es un texto (***number*** o ***string***) que describe al ***atributo Symbol***.

