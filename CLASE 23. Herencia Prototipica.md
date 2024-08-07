 
# 23. Prototypical Inheritance.

La ***herencia*** es la capacidad de poder ***obtener*** atributos (ya sea ***datos*** o ***funciones***) gracias a la relación entre ***elementos padre*** a sus ***elementos hijos***.

Por medio de los ***prototipos*** podemos lograr eso:

Con base al ***ejemplo*** de la clase ***anterior***:

~~~
//Function Constructora
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

Donde tenemos la ***función constructora*** para crear ***objetos*** de tipo ***animal***, Supongamos que queremos crear una ***sub-prototipo*** inferior a este ***prototipo*** que sera el ***padre***.

Llamaremos a este ***prototipo hijo*** como ***Perro***:

Hacemos algo similar a crear una ***función constructora***:

~~~
function Perro (nombre, genero, sonido, tamano) {
	//Creacion atributo que sera el prototipo padre
	this.super = Animal;
	//Asigna como prototipo padre

	//Llamado al prototipo padre
	this.super (nombre, genero, sonido)

	//Asignacion de atributos unicos del prototipo
	this.tamano = tamano;
}

//Herencia de Padre a hijo
Perro.prototype = new Animal();

//Creacion de contructor
Perro.prototype.constructor = Perro;
~~~

***Nota:*** No olvidemos colocar la herencia en el ***prototipo*** y no en la creación del ***objeto***. PAra ello, se hace fuera de la ***función constructora***.

***Nota:*** La ***función*** debe recibir ***todos los parametros*** que necesite, tanto los ***propios*** como los necesarios para el ***padre***, los cuales serán enviados.

También podemos crear los ***métodos*** exclusivos para este ***prototipo*** y sus ***objetos***.

~~~
//Creacion de metodo
Perro.prototype.ladrar = function () {
	console.log("¡Guau!, ¡Guau!");
}
~~~

***Nota:*** No olvidemos colocar estos ***métodos*** fuera de la ***función*** constructora.
## Sobrescritura de funciones padre

Podemos ***sobrescribir*** o ***modificar*** los ***metodos*** heredados, para ello basta con usar la sintaxis.

Tomando como ejemplo, los ***métodos*** anteriores, ***modificamos*** el ***método sonar*** en ***Perro*** heredado del padre ***Animal***:

~~~
//Sobreescritura de metodo padre
Perro.prototype.sonar = function () {
	console.log("¡Grrr!");
}
~~~

De esta manera, solo los ***objetos*** de este ***prototipo*** serán afectados.

Para visualizar basta con ***imprimir*** el ***objeto*** y ***llamar*** a las ***funciones***.

~~~
//Creacion de objeto de prototipo hijo
const snoopy = new Perro ("Snnopy", "Macho", "¡Guauuu!", "Mediano");

//Impresion de objeto hijo
console.log(snoopy);

//Llamado a funcion exclusiva
snoopy.ladrar();

//Llamado a funcion modificada
snoopy.sonar();
~~~

***Nota:*** Ya no creamos un ***prototipo*** del ***padre***, sino directamente el ***hijo***.

A diferencia de crear un ***objeto*** que sea del ***prototipo padre***.

~~~
//Creacion de un objeto padre
const misho = new Animal ("Misho", "Macho", "¡Miauu!");

//Impresion de objeto
console.log(misho);

//Llamado a funcion
misho.sonar();
~~~

De manera ***final***, la ***codificación completa***:

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

//Funcion constructora del hijo
function Perro (nombre, genero, sonido, tamano) {
	//Creacion atributo que sera el prototipo padre
	this.super = Animal;
	//Asigna como prototipo padre

	//Llamado al prototipo padre
	this.super (nombre, genero, sonido)

	//Asignacion de atributos unicos del prototipo
	this.tamano = tamano;
}

//Herencia de Padre a hijo
Perro.prototype = new Animal();

//Creacion de contructor
Perro.prototype.constructor = Perro;

//Sobreescritura de metodo padre
Perro.prototype.sonar = function () {
	console.log("¡Grrr!");
}

Perro.prototype.ladrar = function () {
	console.log("¡Guau!, ¡Guau!");
}

//Creacion de objeto de prototipo hijo
const snoopy = new Perro ("Snnopy", "Macho", "¡Guauuu!", "Mediano");

//Impresion de objeto hijo
console.log(snoopy);

//Llamado a funcion exclusiva
snoopy.ladrar();

//Llamado a funcion modificada
snoopy.sonar();


//Creacion de un objeto padre
const misho = new Animal ("Misho", "Macho", "¡Miauu!");

//Impresion de objeto
console.log(misho);

//Llamado a funcion
misho.sonar();
~~~

***Nota:*** Podemos crear múltiples ***prototipos hijos***, incluso, de otros ***prototipos hijos***.

