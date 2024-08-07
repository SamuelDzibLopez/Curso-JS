# 56. Dynamic properties of Objects.

Generar ***propiedades dinámicas*** en los ***objetos*** puede ser útil para poder obtener datos o llenar datos en los ***atributos*** de estos de manera generada o pseudogenerada tomando como base otros ***datos***.

Un ejemplo simple:

~~~
//Un objeto vacio
const objUsuarios = {}

//Un array con usuarios
const usarios = ["Rodrigo", "Samuel", "Diego", "Andres"];

//Gereracion de atributos y sus valores de manera dinamica
usarios.forEach((usuario, index) => objUsuarios[`id_${index}`] = usuario);

//Impresion de objeto con atributos dinamicos
console.log(objUsuarios);
~~~

Donde generamos ***atributos*** y ***valores***. Podemos generarlos tanto, al momento de ***declarar el objeto*** como ***después***.

Un ejemplo:

~~~
//Un numero aleatorio redondeado
let aleatorio = Math.round(Math.random() * 100 + 5);

//Un objeto
const objUsuarios = {
	//Generacion de nombre atributo aleatrorio
	[`id_${aleatorio}`]: "valor aleatorio"
}

//Un array con usuarios
const usarios = ["Rodrigo", "Samuel", "Diego", "Andres"];

//Gereracion de atributos y sus valores de manera dinamica
usarios.forEach((usuario, index) => objUsuarios[`id_${index}`] = usuario);

//Impresion de objeto con atributos dinamicos
console.log(objUsuarios);
~~~

***Nota:*** Para declarar el ***nombre de un atributo*** utilizamos ***[]*** y los ***templates***.

Este método puede ayudarnos en diferentes formas, principalmente en ***frameworks*** de ***importación*** y ***propiedades*** en ***clases***.

