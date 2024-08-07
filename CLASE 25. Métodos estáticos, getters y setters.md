
# 25. Static methods, getters and setters.

Existen ***diferentes características*** en ***JavaScript*** para los ***metodos*** y ***clases***.

En ***JS*** no existen los tipos de ***clases***:

	- Pulbica
	- Privada

Se podría decir que todas las ***clases*** en ***JS*** son ***publicas***.

Sin embargo, si existen características a usar entre los ***métodos***:

## Métodos estáticos

Se le llama ***método estático*** a un método definido dentro de una clase, cuando dicho ***método*** puede ser invocado ***directamente*** en la ***clase,  ***sin la necesidad*** de la ***creación*** de una ***instancia***.

Para ello, colocamos la palabra reservada ***static*** antes de una ***función*** común.

El siguiente ***ejemplo*** muestra la sintaxis.

~~~
//Clase
class Tortuga {

	//constructor
	constructor (nombre, genero, sonido, tipo) {

		//Declaracion de atributos
		this.nombre = nombre;
		this.genero = genero;
		this.sonido = sonido;
		this.tipo = tipo;
	}

	sonar () {
		console.log("¡Huug!");
	}

	gemir () {
	console.log(this.sonido);
	}

	//Funcion estatica
	static descripcion () {
		console.log("Reptil marino del orden de los quelonios, que llega a tener hasta dos metros y medio de largo y uno de ancho, con las extremidades torácicas más desarrolladas que las abdominales, unas y otras en forma de paletas, que no pueden ocultarse, y coraza, cuyas láminas, más fuertes en el espaldar que en el peto, tienen manchas verdosas y rojizas.");
	}
}
~~~

La ***función descripcion*** de la ***clase Tortuga*** esta definida como ***estática***, por lo que puede ser usada  directamente desde la clase.

~~~
Tortuga.descripcion()
~~~

Aun sin crear ***un objeto*** de la clase. Basta con colocar el ***nombre de la clase*** como si se tratase de una función de un ***objeto***.

## Métodos getters

Un método ***getter*** es un ***método*** que se define como ***función*** pero se ***comporta*** y ***llama*** de la misma manera como fuese un ***atributo***.

~~~
//Clase
class Animal {
	//Constructor
	constructor (nombre, genero, sonido) {
		//Declaracion de atributos
		this.nombre = nombre;
		this.genero = genero;
		this.sonido = sonido;
		this.edad = null;
	}

	get getEdad () {
		return this.edad;
	}
}

//Creacion de objeto
const firulais = new Animal ("Firulais", "Macho", "¡Guauu!");
~~~

Este tipo de ***método*** debe contener la ***palabra reservada*** de ***get*** al inicio.

***Nota:*** como ***estándar*** este tipo de ***métodos*** suelen llamarse con la palabra ***get*** al inicio del nombre.

Apesar, de ser un ***método***, ***NO*** suele ser invocada como una, sino como un ***atributo***.

~~~
//Error
firulais.getEdad();
~~~

***Nota:*** Esta sintaxis es ***incorrecta***.

En su lugar, la sintaxis correcta es:

~~~
//Llamado al getter
console.log(firulais.getEdad);
~~~

Al llamar al ***método*** no se envían con parámetros, sino como un ***atributo***.

Este ***tipo*** de ***métodos*** son utilizados en su mayoría para poder ***retornar*** valores.
## Métodos setters

Al igual que el ***getter*** el ***método setter*** se utiliza para para poder obtener datos útiles para los ***valores*** de los ***atributos*** del ***objeto***.

En este tipo de ***método*** se utiliza la ***palabra reservada set***.

Un ejemplo:

~~~
//Clase
class Animal {
	//Constructor
	constructor (nombre, genero, sonido) {
		//Declaracion de atributos
		this.nombre = nombre;
		this.genero = genero;
		this.sonido = sonido;
		this.edad = null;
	}

	get getEdad () {
		return this.edad;
	}

	set setEdad (edad) {
		this.edad = edad;
	}
}

//Creacion de objeto
const firulais = new Animal ("Firulais", "Macho", "¡Guauu!");
~~~

Este ***método*** recibe parámetros.

***Nota:*** Este tipo de ***métodos*** son utilizados para ***modificar*** o ***agregar*** valores en los ***atributos***.

Al igual que ***getter***, los ***métodos setters*** también, a pesar de ser ***métodos*** son ***invocados*** como si fueran ***atributos***.

***Nota:*** Como ***estándar***, a este tipo de ***métodos*** se les nombra al principio con ***set***.

Su ***invocación correcta*** es la siguiente:

~~~
//Llamado al setter
firulais.setEdad = 20;
~~~

Recibiendo un ***valor*** asignado, que sera recibido como ***parámetro*** en la ***función***.

Un ejemplo para visualizar es:

~~~
//Llamado al getter antes del setter
console.log(firulais.getEdad);

//Llamado al setter
firulais.setEdad = 20;

//Llamado al getter despues del setter
console.log(firulais.getEdad);
~~~





