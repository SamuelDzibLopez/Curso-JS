# 57. This.

	This es un "alias" para hacerse referencia un elemento a si mismo.
## this global.

En los ***navegadores*** el elemento ***this*** hace referencia máxima al ***elemento window***, en ***frameworks*** no existe el nombre ***window***, sino que es ***global***. 

~~~
//Impresion de window
console.log(this);
console.log(window);

//true
console.log(this === window);
~~~

***Nota:*** Todo depende del contexto y como se aplica; Si se aplica en un ***modulo*** sera diferente.

Eso ***significa*** que desde ***this*** (sea global o en un ámbito) podemos crear ***identificadores***, sin recurrir a los ***let***, ***var*** y ***const***.

~~~
//varaible global nombre
this.nombre = "contexto global";

//Imprimir window
console.log(window);
~~~

Y podremos acceder a el:

~~~
//Funcion
function Imprimir () {
	//Impresion de variable del this
	console.log(this.nombre);
}

//Llamado a funcion
Imprimir();
~~~

## this en ámbito.

Si el ***this*** se ejecuta dentro de un ***ámbito***, este hara referencia a su contexto.

Un ejemplo:

~~~
//Objeto
const objeto = {
	
	//Atributo
	nombre: "contexto objeto",
	
	//funcion
	Imprimir: function () {
		//impresion de this.nombre
		console.log(this.nombre);
	}
}

//Llamado a la funcion
objeto.Imprimir();
~~~

Donde ***this*** representa el ***contexto*** donde se encuentra, en este caso, en el contexto ***objeto***.

	AUN CUANDO ASIGNAMOS EN OTRO CONTEXTO

Un ejemplo:

~~~
//variable global
this.nombre = "contexto global"

//funcion
function Imprimir () {
	console.log(this.nombre);
}

//Llamado a la funcion
Imprimir();

//Objeto
const objeto2 = {
	//atributo
	nombre: "contexto objeto 2",

	//funcion asignada con sintaxis objeto literal
	Imprimir
}

//Llamado al metodo
objeto2.Imprimir();
~~~

Cuando el ***this*** es llamado con la ***funcion Imprimir*** el ***this*** que se ejecuta obtiene el contexto global, pero en el ***método Imprmir*** del ***objeto2*** toma como contexto este mismo.

## Arrow functions

Las ***arrow functions*** toman como contexto el ***contexto*** de su padre, en lugar de tomar el contexto de si mismas. a diferencia de las ***funciones comunes***.

Un ejemplo:

~~~
//variable global
this.nombre = "contexto global"

//funcion
function Imprimir () {
	console.log(this.nombre);
}

//Llamado a la funcion
Imprimir();

//Objeto
const objeto2 = {
	//atributo
	nombre: "contexto objeto 2",

	//funcion asignada con sintaxis objeto literal
	Imprimir
}

//Llamado al metodo
objeto2.Imprimir();

//Objeto con arrow function
const objeto3 = {
	//Atributo
	nombre: "contexto objeto 3",

	//Arrow function
	Imprimir: () => console.log(this.nombre)
}

//Llamado a metodo arrow function
objeto3.Imprimir();
~~~

Se podría decir que las ***arrow functions*** saltan su contexto y toman el contexto de su ***this*** padre.

