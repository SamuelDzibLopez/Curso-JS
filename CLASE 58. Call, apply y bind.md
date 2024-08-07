# 58. Call, apply and bind.

Los ***métodos call, apply y bind*** funcionan para poder ***manipular*** de manera mas ***sencilla*** y ***atendible***.

## Call

El ***método call*** permite ejecutar nuestro código con el ***contexto*** del ***elemento this*** que deseemos; Para ello recibimos en este ***método*** el ***elemento*** como un ***parámetro***.

Para ello es ***necesario*** ejecutarse en una ***función***:

La sintaxis del ***call*** es:

~~~
//Metodo call
saludar.call(contexto);
~~~

Tomando de ejemplo el siguiente ***código***:

~~~
//Declaracion de identificador lugar en this global
this.lugar = "Contexto Global";

//Funcion saludar
function saludar () {
	//Impresion de this.lugar (Dependiendo del contexto)
	console.log(`${this.lugar}`);1
}

//Ejecucion comun de funcion (tomando como this el contexto default)
saludar();

//Declaracion de obj
const obj = {
	lugar: "Contexto Objeto"
}

//Ejecucion de funcion saludar, pero con el this como obj
saludar.call(obj);
~~~

De este ***modo*** se define dentro de la ***función saludar*** que el ***this*** sera referente a ***obj***, que fue enviado como parámetro.

### Call con parámetros extra

Si al ejecutar la ***función*** debemos enviar ***mas parámetros***, ademas del ***contexto*** (con el ***método call***), deben ser enviados después del ***this***.

Un ejemplo:

~~~
//Declaracion de identificador lugar en this global
this.lugar = "Contexto Global";

//Funcion saludar
function saludar (saludo, persona) {
	console.log(`${saludo} ${persona}, ${this.lugar}`);1
}

//Invocacion a la funcion saludar de manera comun
saludar("Buenos Dias", "Juan");

//Objeto
const obj = {
	lugar: "Contexto Objeto"
}

//Invocacion de funcion saludar con call y 2 parametros extra
saludar.call(obj, "Hola", "Pedro");
~~~

***Nota:*** Si colocamos ***null*** como contexto de ***this*** en el ***call***, tomaremos el contexto desde donde se ejecuta la ***invocación***, tal como lo haría una común.

~~~
//Call con null
saludar.call(null, "Buenas noches", "Pablo");
~~~

## Apply

***Apply*** es muy similar a ***call*** pero este ***método*** recibe los ***parámetros extra*** ordenados en un ***array***.

Un ejemplo:

~~~
//Funcion saludar
function saludar (saludo, persona) {
	console.log(`${saludo} ${persona}, ${this.lugar}`);1
}

//Invocacion a la funcion saludar de manera comun
saludar("Buenos Dias", "Juan");

//Objeto
const obj = {
	lugar: "Contexto Objeto"
}

//Invocacion de funcion saludar con call y 2 parametros extra
saludar.call(obj, "Hola", "Pedro");

//Invocacion de funcion saludar con apply y 2 parametros extra
saludar.apply(obj, ["Bunas tardes", "Allison"]);
~~~

El ***único parámetro*** que no se envía dentro del ***array*** es el ***this*** al que queremos hacer contexto.

Si la ***función*** no requiere otros ***parámetros***, no se envía ***array***.

Al igual que ***call*** si enviamos como contexto ***null***, haremos referencia al contexto defualt.

~~~
//Apply con null
saludar.apply(null, ["Bunas noches", "Jorge"]);
~~~

## bind

Es un ***enlace*** que se realiza para poder comunicar el ***contexto*** de la ***función*** y la ***ejecución***.

Tomemos el siguiente ejemplo y su problemática:

~~~
//Objeto 1
const persona = {

	//Atributo nombre
	nombre: "Jose",
	
	//Funcion saludar
	saludar: function () {
		console.log(`Hola ${this.nombre}`);
	}
}

//Invocacion de método saludar de persona
persona.saludar();
//Jose

//Objeto 2
const persona_2 = {
	//Metodo saludar de persona_2 es el metodo saludar de persona
	saludar: persona.saludar
}

//Invocacion de método saludar de persona_2
persona_2.saludar();
//Undefined
~~~

Donde al ejecutarse el ***método saludar*** de ***persona***, toma como ***.nombre*** de ***persona***, pero al ***saludar*** de ***persona***, como ***undefined***, al este no tener un ***atributo nombre***.

---

*Entienda el porque sucede esto*:

***El this toma como contexto a cada objeto desde donde se ejecuta***.

---

Para resolver este problema usamos el ***método bind***, corrigiendo el código de la ***función*** al siguiente:

~~~
//Objeto 2
const persona_2 = {
	//Metodo saludar de persona_2 es el metodo saludar de persona y enlazando con bind a persona
	saludar: persona.saludar.bind(persona)
}
~~~

El ***codigo completo*** es:

~~~
//Objeto 1
const persona = {
	//Atributo nombre
	nombre: "Jose",

	//Funcion saludar
	saludar: function () {
		console.log(`Hola ${this.nombre}`);
	}
}

//Invocacion de método saludar de persona
persona.saludar();
//Jose

//Objeto 2
const persona_2 = {
	//Metodo saludar de persona_2 es el metodo saludar de persona y enlazando con bind a persona
	saludar: persona.saludar.bind(persona)
}

//Invocacion de método saludar de persona_2
persona_2.saludar();
//Jose
~~~

El ***bindeo*** puede enlazarse a cualquier contexto, incluso al ***global***.

