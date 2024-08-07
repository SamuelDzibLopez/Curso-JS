
# 51. Maps.

***Map*** es un tipo de dato ***compuesto*** ingresado por ***ES6***, este dato es una mejora a los ***objetos***.

	Un Map es un Objeto que permite como atributos y nombre de atributos, deferentes tipos de datos primitivos, llamados de forma unica.

Su sintaxis es:

~~~
//Creacion de map 
let mapa = new Map();
~~~

Si deseamos crear un ***map*** con contenido:

~~~
//Declaracion de map
let mapaContenido = new Map ([

	//Agrego de atributos
	["nombre", "Juan"],
	[true, 19],
	[[1, 2, 3], "Arreglo"]
])

console.log(mapaContenido);
~~~

un ***map*** es un conjunto de ***datos*** que pueden ***llamarse*** y ***obtener*** como valores como ***tipos de datos***, a diferencia de los ***objetos*** que solo pueden ser ***llamados*** como ***strings***.

## set

El ***método set*** permite ingresar datos dentro de un ***map***, a diferencia de los ***objetos*** donde usamos el ***push***.

~~~
//Objeto

//Creacion de objeto
let objeto = {
}

//Agregar atributo edad con valor 20
objeto.edad = 20

//Impresion de objeto
console.log(objeto);

//Map

//Creacion de map
let mapa = new Map();

//Agregar atributo con clave "nombre" y valor "juan"
mapa.set("nombre", "Juan");

//Agregar atributo con clave true y valor 19
mapa.set(true, 19);

//Agregar atributo con clave [1, 2, 3]  y valor "Hombre"
mapa.set([1, 2, 3], "Hombre");

console.log(mapa);
~~~

***Nota:*** El primer ***parámetro*** que recibe el ***método*** es la ***clave***, mientras que el ***segundo*** es el ***valor***.

La ***clave*** y ***valor*** puede ser cualquier ***tipo de dato***.

## size

Al igual que los ***sets***, para obtener el ***tamaño*** de un ***map*** usamos el ***atributo size***.

~~~
//Impresion de tamaño de map
console.log(mapa.size);
~~~

## has

Con el ***método has*** podemos obtener si existe ***una clave***

~~~
//false
console.log(mapa.has("correo"));

//true
console.log(mapa.has("nombre"));
~~~

Este ***método*** devuelve un ***boolean***, ***true*** si se encuentra la ***clave*** y ***false*** si no se encuentra.

## get

Para ***obtener*** el ***valor*** relacionado a una ***clave***, se usa el ***método get***.

Como en el ejemplo anterior:

~~~
//Impresion de valor relacionado a la clave "nombre"
console.log(mapa.get("nombre"));
~~~

Hay que tomar en cuenta que algunos ***tipos de datos*** no tienden a relacionarse como ***false***.

## delete

Para ***eliminar*** un ***atributo*** (clave y valor) podemos usar el ***método delete***. 

~~~
mapa.delete("sexo");
~~~

***Nota:*** a diferencia de los ***arrays***, donde eliminamos por orden, el ***delete*** en los ***maps*** permite ***eliminar cualquier atributo***, independientemente de su posición.

## Recorrer un map

Al igual que los ***sets***, los ***maps*** pueden recorrerse por los ***loops***, como los ***for of***.

Un ejemplo:

~~~
//ciclo for of
for (let [key, value] of mapa) {
	//Impresion de clave y valor de cada atributo del map
	console.log(`Llave: ${key}, Valor: ${value}`);
}
~~~

***Nota:*** se obtienen ***2 valores*** por ciclo, la ***clave*** y el ***valor***.

## Almacenar keys y values

Podemos almacenar los ***datos*** de un ***map*** separandolos en ***arrays***. para ello se utilizan los métodos ***keys*** y ***values***, dependiendo el tipo de datos que se desee obtener.

~~~
//Almacenar keys del map en un array
let keysMapa = [...mapa.keys()];

//Almacenar values del map en un array
let valuesMapa = [...mapa.values()];

//Impresion de array de keys
console.log(keysMapa);

//Impresion de array de values
console.log(valuesMapa);
~~~

***Nota:*** El ***método*** va acompañado del ***Operador Spread***.