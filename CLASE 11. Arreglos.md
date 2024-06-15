
# 11. Arrays.

Los **arrays** son tipos de valores que permiten almacenar varios datos dentro de un mismo identificador usando espacios.

A diferencia de otros lenguajes, JavaScript no limita los datos almacenados a un **array** a un solo tipo de dato, lo que permite la mejor y mayor utilidad de estos.

Para definir un array podemos hacerlo de las siguientes maneras:

~~~
//Arrays
const arreglo_1 = [];
const arreglo_2 = [1, true, "Hola", ["A", "B", "C"]];

//Los arrays en JS pueden tener multiples tipos de datos
~~~

Incluso dentro de un array, JS nos permite guardar otro array, entre otras cosas que veremos a más adelante.

**_Nota:_** Para los **arrays**, podemos usar de manera más optima el identificador **const** al momento de crearlo, ya que, al no ser un tipo de dato primitivo, nos permitira ingresar nuevos datos a este, incluso modificar los datos creados y eliminarlos;

## Atributo ***length***

Podemos usar el atributo length en un array, lo cual nos permitira saber el número de los espacios declarados, a diferencia de los datos primitivos, donde nos devolvía el tamaño del identificador.

~~~
console.log(arreglo_2.length); //El tamaño del array principal

//Resultado:4
~~~

## Acceder a un elemento dentro del array

Existirán ocasiones donde querremos obtener únicamente un solo dato dentro del array, cambiarlo o hacer cualquier cosa con él; Para ello accederemos a ellos por medio de su posicionamiento.

~~~
console.log(arreglo[2]); //Impresion del elemento de posicion 2 del array padre

//Resultado: "Hola"
~~~

Recordemos, los arrays empiezan su cuenta de espacios desde el 0, por lo tanto, el elemento 2, es el de la posición 3.

## Acceder a arrays dentro de arrays

También podemos acceder a un elemento de un array que está dentro de otro array, si seguimos la misma manera, seria:

~~~
console.log(arreglo_2[3][1]); //Impresion solo de un elemento del array hijo

//Resultado: B
~~~

## método ***fill***

La funcion fill en un array permite declarar los elementos de un array con un valor que podemos definir.

~~~
const array_4 = Array(10).fill(false);

//Creamos un array de los 10 de length y le asignamos a todos el valor de false
~~~

## método ***push***

Este método permite ingresar un nuevo elemento en un array, colocándolo al final de todos los elementos.

~~~
const colores = ["Rojo", "Verde", "Azul"];
//Declaracion de array

colores.push("Negro");
//Agregacion de un nuevo elemento al array
~~~

## método ***pop***

JavaScript también permite eliminar el último elemento de un array.

La función pop elimina el elemento que se encuentra en la posición final del array definido.

~~~
colores.pop();
//El ultimo elemento se elimina del array 
~~~

Este método no requiere parámetros, por lo que solo necesitamos declararla vacia.

## método ***forEach***

Otro método muy utilizado para los arrays en el ámbito de la programación es el método **forEach,** el cual hace un bucle que se repite una vez por cada elemento dentro del array declarado.

~~~
colores.forEach(function (e, index) {
	//e es el parametro del elemento en forma del forEach
	console.log(`<li id="${index}">${e}</li>`);
});
~~~

El elemento **e** como parámetro declarado en los parámetro del método se refiere al elemento en turno dentro del array.

El parámetro **index** o **i** se refiere a un elemento que va en aumento en 1, sumándose por cada ciclo (empezando en 0).


