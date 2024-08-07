
# 32. Anonymous Auto Executable Functions.


Estas ***funciones*** permiten la ejecución de bloques de código sin ser ***definidos*** al momento de ser ***creadas***. para una mejor forma.

Para definir una ***función anónima*** basta con incluirla dentro de de una ***encapsulación***:

~~~
//Funcion anonima autoejecutable
(function () {
//Codigo de funcion
}) ();
~~~

***Nota:*** La ***función anónima*** se encuentra dentro de unos primeros ***()***, y los segundos ***()***, indican la ejecución inmediata.

***Nota:*** Es indispensable la declaración de el ***;*** al final de la ejecución.

Un ejemplo de funciones ***anónimas autoejecutables***:

~~~
//Funciones anonima autoejecutable

(function () {
	//Codigo de funcion
	console.log("Primer funcion");
}) ();

(function () {
	//Codigo de funcion
	console.log("Segunda funcion");
}) ();
~~~

Estas ***funciones*** no tienen un nombre y no necesitan ser ***invocadas***, si no que se ***ejecutan*** de manera ***automática*** en la interpretación.

## funciones anónimas autoejecutables con parámetros

Para enviar y recibir ***parámetros*** en este tipo de ***funciones***, es muy simple.

Un ejemplo con su ***explicación:***

~~~
//Funcion anonima autoejecutable con parametros
(function (a, b, c) { //Recibo de parametros con identificadores personales
	//Codigo de funcion
	console.log(a);
	console.log(b);
	console.log(c);

	//uso de parametros
	c.log("uso de console como parametro");
}) (document, window, console); //envio de parametros externos
~~~

Para ***enviar parámetros*** basta con definiros dentro de los ***()*** de la ***ejecución***.

Para recibirlos, simplemente se ***declaran*** en los ***()*** de la ***función anónima***; al igual que cualquier otra, su declaración de nombre es indiferente. 

En el ***anterior ejemplo***, se envían los ***objetos globales document, window*** y ***console***, así como el uso de un ***método*** con el ***nombre de parámetro declarado*** en la función.

## Otras maneras de escribir funciones anonimas autoejecutables

Existen otras maneras de ***codificar*** este tipo de ***funciones***, creadas y estandarizadas por varias personas y empresas.

A pesar de tener diferente ***sintaxis***, su funcionamiento es el mismo.

Algunas de ellas son las siguientes:

La manera ***clásica***:

~~~
//Funcion anonima clasica

(function () {
	//Codigo de funcion
	console.log("Clasica");
}) ();
~~~

La ***Crockford***:

~~~
//Funcion anonima Crockford

((function () {
	//Codigo de funcion
	console.log("Crockford");
}) ());
~~~

La versión ***unaria***: 

~~~

//Funcion anonima unaria

+function () {
	//Codigo de funcion
	console.log("unaria");
} ();
~~~

Y una nueva forma creada por ***facebook***:

~~~

//Funcion anonima de Facebook

!function () {
	//Codigo de funcion
	console.log("Facebook");
} ();
~~~

Cada una de estas, tiene un cambio mínimo de sintaxis, pero funcionan de manera idéntica.
