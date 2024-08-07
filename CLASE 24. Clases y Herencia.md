
# 24. Classes and Inheritance.

En ***JavaScript*** las ***clases*** no son mas que ***sintaxis*** implementada desde ***ES6***, para poder escribir de una ***manera*** más fácil y rápida los ***prototipos***.

***JS*** utiliza en su ***interprete*** el concepto de ***prototipos*** y convierte las ***clases*** escritas a estos.

En la ***clase*** anterior teníamos una ***función constructora***  como la siguiente:

~~~
//Function Constructora del padre
function Animal (nombre, genero, sonido) {
	this.nombre = nombre;
	this.genero = genero;
	this.sonido = sonido;
}

//Definicion y asignacion de metodo a prototipo
Animal.prototype.sonar = function () {
	console.log(this.sonido);
}
~~~

Podemos transforma esta a una ***clase***:

Para ello, podemos aplicar las siguientes diferencias:

	- Cambio de function a class.
	- Eliminación de parametros (los datos se reciben por el constructor).
	- Creacion de constructor.
	- Declaraciónde atributos en el constructor.
	- Declaracion de funciones dentro de la clase.

Quedando de la siguiente manera: 

~~~
//Clase
class Animal {
	constructor (nombre, genero, sonido) {
		this.nombre = nombre;
		this.genero = genero;
		this.sonido = sonido;
	}
}
~~~

***Nota:*** La asignación de los ***atributos*** es idéntica, pero se colocan dentro del ***constructor***.

Para la definición de los ***métodos*** hacemos uso de la sintaxis de los ***objetos literales***.

***Nota:*** Los ***métodos*** se colocan dentro de la ***clase***, pero fuera del ***constructor.

Convirtiendo la ***función constructora*** en una ***clase***.

~~~
//Clase
class Animal {
	//Constructor
	constructor (nombre, genero, sonido) {
		//Declaracion de atributos
		this.nombre = nombre;
		this.genero = genero;
		this.sonido = sonido;
	}

	//Declaracion de metodos con sintaxis objeto literal
	sonar() {
		console.log(this.sonido);
	}
}

//Creacion de objeto de clase
const tommy = new Animal ("Tommy", "Macho", "¡Haaa!");

//impresion de objeto
console.log(tommy);

//Llamado al metodo
tommy.sonar();
~~~

## Herencia

Al igual que los ***prototipos***, poder ***generar clases hijas*** de otras ***clases*** que serán las ***padres***, con la finalidad de heredar sus ***atributos*** y ***métodos***, al momento que podemos agregarle más para la ***clase hijo***. 

Para ello, usamos la siguiente sintaxis:

~~~
//Clase hija
class Tortuga extends Animal {

	//construvtor
	constructor (nombre, genero, sonido, tipo) {

		//Metodo que llama al constructor de la clase padre
		super (nombre, genero, sonido);

		//Declaracion de atributos
		this.tipo = tipo;
	}

	//Modificacion de metodo
	sonar () {
		console.log("¡Huug!");
	}

	//Creacion de nuevo metodo
	gemir () {
		console.log(this.sonido)
	}
}

//Creacion de objeto de clase hijo
const tommy = new Tortuga ("Tommy", "Macho", "¡Haaa!", "Marina");

//impresion de objeto
console.log(tommy);

//Llamado al metodo modificado
tommy.sonar();

//Llamado al metodo exclusivo del hijo
tommy.gemir();
~~~

En el ***código*** creamos una ***clase hija*** llamada ***tortuga*** que ***hereda*** los ***atributos*** y ***métodos*** de su ***padre: Animal.***

***Nota:*** Para hacer una ***clase hija*** colocamos ***extends*** acompañado del nombre de la clase ***padre***.

El ***super*** es el llamado a la clase ***padre***, definida en el ***extends***.

Las ***clases*** También permite la ***modificación*** y ***sobreescritura*** de ***métodos*** heredados.

	AUN ASI, JAVASCRIPT SIGUE SIENDO UN LENGUAJE DE PROGRAMACION ORIENTADO A OBJETOS BASADO EN PROTOTIPOS.

