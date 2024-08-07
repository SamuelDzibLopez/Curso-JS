
# 50. Sets.

***Set*** es un ***tipo de dato*** ingresado por ***ES6*** al igual que ***Symbol***, pero este, es una mejora de los ***Arrays***.

	Un Set es un Array que solo permite datos primitivos unicos.

La sintaxis es:

~~~
//Creacion de Set
const set = new Set ();
~~~

Dentro de un ***set*** solo se guardaran ***una sola vez*** valores ***primitivos únicos***. 

Un ***ejemplo***:

~~~
//Ejemplo

//Array comun con valores repetidos
let Arreglo = [0, 1, 1, 2, 3, 0, false, "Hola", "Hola", "HOLA", [1], [1], {}, {}, true, false];

//Creacion de set y paso de array comun
const set = new Set (Arreglo);

//Impresion
console.log(set);
~~~

Todo ***elemento primitivo*** (***strung, number, boolean***) es almacenado una vez, mientras que los ***elementos compuestos*** permanecen.

## size

Para consultar el ***tamaño*** de un ***set NO*** utilizamos ***length***, sino ***size***.

~~~
//Consultar tamaño de set
console.log(set.size);
~~~

## add

Para ***añadir*** elementos a un ***set***. utilizamos el ***método add***. a igual que con un ***array normal***, donde  se usaba push.

~~~
//Creacion del set
const set = new Set ();

//Impresion de set antes de ingreso de datos
console.log(set);

//Impresion de tamaño de set antes de ingreso de datos
console.log(set.size);

//Agrego de datos al set

set.add(1);
set.add(1);

set.add("Hola");
set.add("HOLA");
set.add(2);
set.add(true);
set.add(false);

//Impresion de set despues de ingreso de datos
console.log(set);

//Impresion de tamaño de set despues de ingreso de datos
console.log(set.size);
~~~

Al igual, si se agregan ***datos repetidos*** no se tomaran en cuenta.

***Nota:*** Al igual que los ***arrays***, los ***sets*** pueden ser recorridos por los ciclos, tales como ***for of***, ***for in*** y ***forEach***.

## delete

Para ***eliminar*** un dato de un ***set***, usamos el método ***delete***.

~~~
//Eliminar elemento de valor "HOLA"
set.delete("HOLA");

//Impresion de set
console.log(set);
~~~

A diferencia de los ***arrays***, que elimina el ***ultimo elemento*** en cola con el ***pull***, el ***delete*** permite eliminar un dato de ***cualquier posición***.

## Ingresar a un dato de un set

Para ***ingresar*** a un ***dato*** de un ***set*** debemos convertirlo en un ***array***, para ello usamos el ***método from*** de ***Array***.

Como en el ejemplo:

~~~
//Error
console.log(set[0]);

//Convertir set a array y almacenar en un identificador
let setArray = Array.from(set)

//Impresion de dato en la posicion 0
console.log(setArray[0]);
~~~

***Nota:*** No podemos acceder directamente a un ***dato*** de un ***set*** sin ser convertido antes en ***array***.

## has

El ***método has*** se utiliza en los ***sets*** para poder identificar si ***existe*** un ***dato*** dentro de este.

Este ***método*** devuelve un ***boolean***.

La sintaxis y ejemplo tomando como ***set*** los códigos anteriores:

~~~
//true
console.log(set.has("Hola"));

//false
console.log(set.has(10));
~~~

## clear

Podemos ***vaciar por completo*** un ***set***.

Para ello, utilizamos el ***método clear***.

como el siguiente ejemplo:

~~~
//Vacio de set
set.clear();

//Impresion de set
console.log(set);
~~~