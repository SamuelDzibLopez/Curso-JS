
# 18. Restructuring

Si necesitamos desestructurar un elemento para poder utilizar sus elementos podemos usar lo que en **JavaScript** conocemos como **desctructuracion definida.**

El usar este método, permitimos el ahorro de codigo y escritura; A continuación, un ejemplo de sintaxis de definición de variables sin **destructauracion** y **con destructuracion.**

~~~
//Destructuracion

//sin destructuracion

const sindestructuracion = [1, 2, 3];

let uno = sindestructuracion[0];
let dos = sindestructuracion[1];
let tres = sindestructuracion[2];

console.log(uno, dos, tres);

// con destructuracion

const [one, two, three] = sindestructuracion;

console.log(one, two, three);
~~~

A diferencia de un código sin destructuracion, se necesita declarar y definir el valor de cada uno, pero con **destructuracion** necesitamos unas cuantas líneas codificadas.

## Destructuración con objetos

Cuando usamos **desestructuración** en un objeto es necesario declarar los identificadores creados, con el mismo nombre con los **atributos** del **objeto.**

De la siguiente manera:

~~~
const persona = {
	nombre: "Manuel",
	apellido: "López",
	edad: 21
}

//Destructuracion

let { nombre, apellido, edad } = persona;

console.log(nombre, apellido, edad);

/*
Para poder usar destructuracion en un objeto, debemos declarar los identificadores con el mismo nombre que los del objeto padre
*/
~~~

Si deseamos declarar los identificadores de un nombre diferente, la siguiente sintaxis ayuda.

~~~
let { nombre: name, apellido: apelli, edad: age } = persona;

console.log(name, apelli, age);

/*
Para poder usar destructuracion en un objeto, debemos declarar los identificadores con el mismo nombre que los del objeto padre
*/
~~~

