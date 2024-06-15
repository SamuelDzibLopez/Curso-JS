
# 19. Literals Objets.

Los objetos literales nos permiten el ahorro de código y declaración de prototipos al momento de ser declaradas. A continuación, se presentan unos ejemplos para una mejor comprensión.

~~~
//Objeto comun
const perro = {
	nombrePerro: nombrePerro,
	//El valor del objeto nombre es igual al valor de nombrePerro
	edadPerro: edadPerro,
	//El valor del objeto edad es igual al valor de edadPerro
	ladrar: function () {
		console.log("Guauu, Guauu");
	}
}

console.log(perro);
perro.ladrar();

//Objeto literal

const dog = {
	nombrePerro,
	/*Si nuestro identificador se llama igual que el atributo, podemos simplificarlo de esta manera*/
	edadPerro,
	raza: "Callejero",
	ladrar() { //Una manera mas facil de declarar una funcion
		console.log("Guauu, Guauu, Guauu");
	}
}

console.log(dog);
dog.ladrar();
~~~

El funcionamiento de un **objeto literal** tiene el mismo funcionamiento que un **objeto común.**

