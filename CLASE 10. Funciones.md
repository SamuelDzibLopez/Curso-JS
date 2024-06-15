
# 10. Funciones.

El uso de funciones es la programación que nos permite poder tener nuestro código de forma más ordenada y tener código que puede ser utilizado nuevamente sin la repetición de estos; También permite la programación a bloques.

Una función es un segmento de código que se dedica a realizar una cantidad de acciones específicas con datos enviados a ella y que puede o no devolver un resultado.

~~~
//Funcion declarada
function estoEsUnaFuncion () {
	console.log("Uno");
	console.log("Dos");
	console.log("Tres");
}

//Invocacion
estoEsUnaFuncion();

//se llama a una funcion con su nombre y (); con sus parametros a enviar;
~~~

Una **función** debe ser invocada para poder ser ejecutada, por si sola no se ejecuta en el orden codificado.

## Funciones con return

En varias ocasiones necesitaremos recuperar un resultado de una funcion para poder ser utilizada más adelante fuera de la misma función, para ello se hace uso del **return.**

Para poder devolver un resultado en una función se realiza la siguiente sintaxis:

~~~
function unaFuncionQueDevuelvevalor () {
	return "la Funcion ha retornado una cadena de texto";
}

//Las funciones pueden devolver un resultado
//Ya sea una variable o un valor solo
~~~

**_Nota:_** El recorrido y lectura de la consola leerá hasta encontrar la línea **return**, el sistema ignorara toda línea después de esta, como si terminara la función.

## Guardar el resultado de la función

Si deseamos guardar el valor del **return** para ser usado después podemos guardarlo en un identificador dentro.

~~~
let valorDeFuncion = unaFuncionQueDevuelvevalor(); //El resultado de la funcion se guarda en la variable
~~~

## Funciones con parametros

Las funciones también pueden recibir datos para poder realizar sus acciones y ejecutarse, para ello se declaran en la función y se envían de la siguiente manera.

~~~
//Creacion de funcion
function saludar (nombre = "Desconocido", edad = "0") {
	console.log(`hola mi nombre es ${nombre} y tengo ${edad} años`);
}

//Creacion y asignacion de variable
let edadmia = 21;

//Invocacion a la funcion con envio de parametros 
saludar("Felix", edadmia);
~~~

Para poder enviar los datos a una función se colocan dentro de los () cuando se invoca, y para recibirlos los colocamos dentro de los () de la función.

Los nombres de la función declarada no tienen que coincidir con los nombrados al nombre de los enviados al momento de la invocación; Estos se llaman de otra manera dentro de la función.

**_Nota:_** Podemos inicializar los parámetros declarados dentro de la función, esto servirá si al momento de llamar a la función no se envían los parámetros, pero si se envían, utilizará los enviados e ignorará los definidos anteriormente.

**_Nota:_** Debemos enviar los parámetros en el orden correcto definido en la función para evitar errores.

## Funciones declaradas

Existen diferentes tipos de funciones, las más importantes son las **funciones declaradas.**

Las **funciones declaradas** tienen las ventajas, tales como, poder ser llamadas en todo momento del código, incluso arriba de la función declarada en nuestro código.

~~~
functionDeclarada(); //una funcion se puede ejecutar antes de declararse

//Funcion
function functionDeclarada() {
	console.log(`Esto es una funcion declarada, puede invocarse en cualquier parte del codigo, incluso antes de que la funcion sea declarada`);
}

functionDeclarada(); //Se ejecuta despues
~~~

## Funciones expresadas

A diferencia de las **funciones declaradas**, las funciones expresadas nos permiten poder declarar una función dentro de un identificador; La desventaja, no permite la invocación antes del orden del código donde se encuentra su declaración.


~~~
functionExpresada();//Marca error cuando la funcion se ejecuta antes de ser declarada

//Funcion
const functionExpresada = function () {
	console.log(`Esto es una funcion declarada, puede invocarse en cualquier parte del codigo, incluso antes de que la funcion sea declarada`);
}

functionExpresada(); //Se ejecuta bien
~~~