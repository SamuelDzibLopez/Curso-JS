
# 22. Prototypes.

	"En Javascript, todo es un Objeto".

***JavaScript*** es un lenguaje multiparadigma, gracias a ello, la **POO** (Programación Orientada a Objetos) es muy importante en su codificación.

A pesar de que gracias a ***ES6***, ya podemos escribir código basado en ***clases***, en realidad, no es mas que sintaxis, ya que al interpretar, el lenguaje convierte estos en ***prototipos***.

Empecemos entendiendo que es la ***POO***:

## POO (Programación Orientada a Objetos)

La Programación Orientada a Objetos o POO, por sus siglas, es el paradigma de programación que se conoce por el cual los datos o funciones son estructurados mediante diferentes tipos de modelos, a los cuales se les llama ***clases***.

Dependiendo de cada contexto y funcionamiento, cada dato dentro de nuestro código estará dentro dentro de uno de los diferentes modelos.
## ¿Qué es una Clase?

Una ***Clase*** es una representación abstracta de un modelo a poder usar para los datos, con base en este modelo, se crearan los ***objetos***, teniendo las propiedades establecidas en este modelo codificado.

La definición de una ***clase***, se realiza dando un nombre que represente a todos los futuros ***objetos*** creados como base de esta.

También se hace la creación de las ***propiedades*** y ***métodos*** que serán heredados (tanto los nombres, como sus valores).

## ¿Qué es un Objeto?

 Un ***Objeto*** es un dato representado por medio de la notación de su clase ***definida***, es decir, es la creación de física (una instancia) creada por medio del modelo al que llamamos ***clase***.
 
## ¿Que es un atributo?

Un ***atributo*** o ***atributos*** son el conjunto de datos, propiedades o y características que representan a la ***clase***, y por lo tanto al ***objeto***.

Son las variables dentro de un ***objeto***.

Un ejemplo de estos son los datos que ingresamos siempre, dentro de los ***JSONs***.

A continuación, un ejemplo de un ***Objeto*** con sus ***Atributos***:

~~~
let Firulais = {
	Raza: "Chihuahua",
	Edad: 4
}
~~~

Los ***atributos*** pueden ser diferentes tipos de datos, incluso pueden llegar a ser otros objetos dentro.

Otro de los atributos que solemos utilizar muy frecuentemente aun sin darnos cuenta, es el ***.length***.

Cuando accedemos a este atributo de un identificador, estamos accediendo realmente a su atributo ***tamaño***, debido a que este es un ***objeto*** de la clase ***identificador***.

~~~
let nombre = "Samuel";

console.log(nombre.length);
~~~

Existen otros atributos generados de forma automática por el lenguaje, gracias a las clases de cada uno.

## ¿Que es un método?

Un ***método*** es la acción que se le define a cierta ***clase*** para poder ser heredada a un ***objeto*** al momento de ser creado.

En el ámbito de programación, los ***métodos*** son ***funciones*** que se encuentran dentro de un ***objeto*** o ***clase***. 

Estas suelen ser llamadas en forma de verbos, ya sea por el usuario, o incluso por el lenguaje, tales como las ***funciones comunes***

Una vez, definido que es una ***clase*** y un ***objeto***, podemos practicar la estructuración prototipica.

Aqui, un ejemplo de una funcion dentro de un objeto (A lo que se le llama ***metodo***):

~~~
let Firulais = {
	Raza: "Chihuahua",
	Edad: 4,
	sonido: "Guauu",
	sonar () {
		console.log(this.sonido);
	}
}

Firulais.sonar();
~~~

La ***Función*** sonar esta dentro del ***objeto***, por lo tanto, podemos decir, que ***sonar*** es un ***método de Firulais***. 

## Estructuración prototipica

Los ***prototipos*** eran la forma de generar modelos para nuestros ***objetos*** antes de la llegada de ***ES6***; Después de esta, empezó a usarse las ***clases***, una de las lecciones siguientes de este curso.

La ***Clase*** mas primitiva en ***JS***, definida por el lenguaje de manera ***default*** es la clase ***Objet***, de forma que si, nosotros definimos un objeto (O algún otra estructura de dato) de forma manual, este sera heredero de la clase ***Objet***

Podemos comprobar esto asiendo el siguiente ejercicio

~~~
let Firulais = {
	Raza: "Chihuahua",
	Edad: 4,
	sonido: "Guauu",
	sonar () {
		console.log(this.sonido);
	}
}

console.log(Firulais);
~~~

Definiendo un ***identificador*** que no salga de una clase, ***JS*** lo interpreta como un objeto de la clase ***Objet***.

Pero para poder crear ***objetos*** sin necesidad de definirlos así, podemos crear un ***modelo***, que sera un ***prototipo***, de ese modo, podremos crear infinitos objetos de manera mas facil y controlada.

### Creación de función constructora

Para ello, crearemos una función, que sera la ***función constructora***, como suele llamarse, debido a que gracias a ella, podremos construir ***n*** cantidad de ***objetos***.

~~~
//Function Constructora

function Animal (nombre, genero, sonido) {
	this.nombre = nombre;
	this.genero = genero;
	this.sonido = sonido;

	//Definicion de metodo
	this.sonar = function () {
		console.log(this.sonido);
	}
}

//Hay que bindear los atributos
~~~

***Nota:*** No olvidemos las ***características y gramática*** con la que deben escribirse los diferentes tipos de datos.

La ***función constructora*** recibe los parámetros que serán los ***atributos***.

La función genera primeramente la creación del atributo dentro del mismo mediante el elemento ***.this*** y nombre del atributo, para luego asignarle el valor recibido como parámetro.

A este método se le llama ***bindeo***.

La llamada a al ***función constructora*** se realiza de la siguiente manera:

~~~
//Creacion de objetos

const snoopy = new Animal("Snoopy", "Macho", "¡Guaau!");
~~~

Creamos una ***constante*** o un ***identificador cualquiera*** y creamos un nuevo objeto de ***prototipo Animal***.

Para verificar, podemos imprimir el objeto:

~~~
console.log(snoopy);
~~~

## Optimización de funciones

El espacio en memoria de los ***identificadores*** presenta un ***problema*** cuando comenzamos a crear ***multiples*** objetos por medio de los ***prototipos***, debido a que estas funciones de crean también en cada uno de los ***objetos*** existentes.

Esto ocupa ***memoria*** y presenta problemas de ***rendimiento***.

Una mejora al código es ***asignar*** al ***prototipo*** las funciones, en vez de crearlas dentro de cada ***objeto***.

	Los atributos deben encontrarse dentro de la funcion constructora, y los metodos, asignarlos al prototipo.

Un ejemplo del ***prototipo*** explicado con anterioridad:

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

//Creacion de objetos
const snoopy = new Animal("Snoopy", "Macho", "¡Guaau!");

// Impresion y llamado
console.log(snoopy);
snoopy.sonar();
~~~

Las funciones se encuentran ***afuera*** de la ***función constructora*** y hacemos unos cambios.

	- Colocar la función fuera del constructor
	- cambiamos el .this por .(nombredelprototupo).prototype

De esta manera ***mejoramos*** la ***optimización*** y reducción de ***espacio*** requerido.
















