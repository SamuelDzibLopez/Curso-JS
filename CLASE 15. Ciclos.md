
# 15. loops.

A diferencia de las condicionales (**if, else if, else, switch**), los cuales una vez realizados una sola vez siguen con las líneas siguientes, los **loops** permiten hacer ciclos a determinadas líneas de código, repitiéndose hasta cumplir una condición especifica.

Los **loops** permiten ejecutar código sin detenerse, hasta cumplir una condición declarada.

Existen varios **loops.**

## Ciclo **while**

Un **ciclo while** es uno de los **loops** más sencillos, este permite ejecutar cierto código mientras el resultado de una condición sea **true.**

La sintaxis de un **ciclo while** es la siguiente:

~~~
let contador = 0;
//Variable para controlar el while

//ciclo while
while (contador < 10) { //Condicion

	//Codigo en loop
	console.log(contador);
	contador++; //Aumento del valor de contador

}
~~~

Todas las líneas de código que se encuentren dentro de los { } del **ciclo while** se repetirán hasta que la condición sea **false.**

**_Nota:_** Si la condición se evalúa por medio de un contador, para evitar un **loop infinito** se deberá sumar al dato un valor por cada iteración.

## Ciclo **do while** 

Un ciclo **do while** es muy similar al ciclo anterior (**while**), con la diferencia que, en esta variación del ciclo, primero se realiza la acción y luego se evaluara la condición. Por ello, en un ciclo **do while**, el código se repetirá por lo menos, una ocasión.

La sintaxis es la siguiente:

~~~
let cont = 0;
//Declaracion del contador

//Ciclo do while
do {
	console.log("do while " + cont);
	cont++;
	//Codigo en loop
	/*Primero se realiza el loop
	y luego se evalua la condicion*/

} while (cont < 10); //Condicion
~~~

## Ciclo **for**

El **ciclo for** es un **loop** que funciona por medio de la evaluación de un contador, a diferencia de los ciclos **while** y **do while,** que evaluaban por medio de una **condición**, el **for** utiliza un contador creado dentro de su cabecera.

~~~
//Ciclo for
for (let i = 0; i < 10; i++) { //Cabecera del for
	console.log("for " + i);
	//Codigo en loop
}
~~~

Dentro de la **cabecera** del ciclo, se encuentran los 3 datos importantes que hacen lo funcionar.

1.    **Declaración del** **iterador (i).**
2.    **Condición máxima del iterador**
3.     **Decremento o incremento del iterador**

**_Nota:_** Gracias a todos los datos de la cabecera, no tendremos que colocar un decremento dentro del del loop del código.

### Ciclo for con ***Arrays***

El **ciclo for** nos permite poder recorrer con facilidad un **array** por medio de su iterador declarado.

Para ello hacemos un pequeño cambio en la condición máxima del iterador y el atributo **length.**

~~~
let numeros = [10, 20, 30, 40, 50, 60, 70, 80, 90];
//Array

//Ciclo for
for (let i = 0; i < numeros.length; i++) { //Cabecera del for
	console.log(numeros[i]);
	//Elemento del array en loop
}
~~~

De este modo, podemos recorrer todo el array, aun si modificamos el largo del **array.**

### Ciclo **forin** (for para recorrer objetos)

El ciclo **forin** es una variación del ciclo **for,** este nos ayuda con el recorrido dentro de **objetos.**

~~~
//Objeto
const alumno = {
	nombre: "Roberto",
	apellido: "López",
	edad: 30
}

//Forin
for (const propiedad in alumno) { //sntaxis
	console.log(propiedad);
	//inpresion de los nombres de loss atributos
	
	console.log()`Atributo: ${propiedad} Valor: ${alumno.propiedad}`;
	//La notacion punto no funciona en un forin

	console.log()`Atributo: ${propiedad} Valor: ${alumno[propiedad]}`;
	//La notacion de los [] si funciona
}
~~~

**Forin** utiliza **in** en la **cabecera**

En la cabecera del **for** de este tipo, se debe declarar un identificador y el **array,** de esta manera podremos recorrer un **atributo** del **objeto** por cada iteración.  

**_Nota:_** La **notación de punto** no funciona para este ciclo, si queremos acceder a uno de los **atributos** necesitamos la **notación [ ].**

### Ciclo **forof** (for para recorrer elementos iterables)

El **ciclo forof** no solo permite recorrer objetos, como **forin,** sino que permite recorrer cualquien elemento iterable. Tanto como cadenas, arrays, entre otros.

~~~
let numeros = [10, 20, 30, 40, 50, 60, 70, 80, 90];
//Elemento iterable

//forof 
for (const elemento of numeros) {
	console.log("forof " + elemento);
	//Elemento en loop
}
~~~

**Foriof** utiliza **of** en la **cabecera**

Otro ejemplo puede hacerse con **strings.**

~~~
let cadena = "Hola mundo";
//Elemento iterable

//forof 
for (const caracter of cadena) {
	console.log("for de cadena " + elemento);
	//Elemento en loop
}
~~~

De esta manera, se imprimirá un **carácter** por iteración hasta terminar la cadena de texto.