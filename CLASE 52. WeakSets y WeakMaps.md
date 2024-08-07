
# 52. WeakSets and WeakMaps.

Los ***WeakSets*** y ***WeakMaps*** son una ***variante*** de los ***sets*** y los ***Maps***, con restricciones:

	- No se puede iterar en estos tipos de elementos.
	- No se puede vaciar por completo estos elementos.
	- No puede verificar su tamaño.

## WeakSets

A diferencia de los ***sets***, para declarar un ***WeakSets***:

~~~
//Set

//Declaracion de Set
let set = new Set([0, 1, 1, 2, [], [], {}, {},"Hola"]);

//Impresion de set
console.log(set);


//Weakset (Error)

//Declaracion de Weakset
let Wset = new WeakSet([0, 1, 1, 2, [], [], {}, {},"Hola"]);

//Impresion de Weakset
console.log(Wset);
~~~

Los ***Weakset*** solo aceptan ***objetos*** a ingresar.

~~~
//Declaracion de Wheakset
let Wset = new WeakSet();

//Objeto
let objeto = {
	nombre: "Roberto"
}

//Valor primitivo
let cadena = "Roberto";

//Agregar un objeto al Weakset
Wset.add(objeto);

//Impresion de Weakset
console.log(Wset);

//Agregar un valor primitivo (Error)
Wset.add(cadena);

//Impresion de Weakset
console.log(Wset);
~~~

## Weakmap

Similar a los ***weakset***, los ***weakmap*** solo aceptan ***objetos*** dentro de ellos, diferente a los ***map***.

Un ejemplo de comparación con los ***map***:

~~~
//Map

//Declaracion de Map
let Mapa = new Map([
	["nombre", 1],
	[true, "verdadero"]
]);

//Impresion de map
console.log(Mapa);


//Weakmap (Error)

//Declaracion de Weakmap
let WMapa = new WeakMap([
	["nombre", 1],
	[true, "verdadero"]
]);

//Impresion de Weakmap
console.log(WMapa);
~~~

Un ***ejemplo*** de como debería realizarse:

~~~
//Declaracion de Weakmap
let WMapa = new WeakMap([
	[{ nombre : "roberto"}, true],
	[{ edad : 19}, true],
]);

//Impresion de Weakmap
console.log(WMapa);

//Objeto
let objeto = {
	apellido: "Perez"
}

//Agregar un atributo (un objeto como clave y true como valor)
WMapa.set(objeto, true);

//Impresion de Weakmap
console.log(WMapa);
~~~

Al igual que los ***weakset*** no pueden consultarse su ***size***, y ***NO son iterables*** de manera directa.

***Nota:*** Todos los ***métodos*** no especificados en los ***weaks*** funcionan igual que los ***sets*** y ***maps***.