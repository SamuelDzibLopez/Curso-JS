
# 14. Condicionales.

Hasta el momento, todo el código enseñado ha sido para programación lineal, pero existirán ocasiones, donde deberemos elegir dependiendo de un resultado, si se ejecutara cierta parte del código o no.

Básicamente, ejecutar cierta parte de código, dependiendo de si se cumplen o no condiciones declaradas.

## Condicional **if**

Para hacer la sintaxis de una condicional, lo expresamos:

~~~
let edad = 18 //Declaracion de identificador y su valor

//Condicional
if (edad >= 18) { //Sintaxis de una condicional
	console.log("Eres mayor de edad");

	/*El codigo que se encuentra dentro de los {},
	Se ejecutara. si la condicion declarada es true*/
}

/*Despues continua el codigo*/
~~~

La condición se coloca dentro de los paréntesis, podemos usar cualquier operador enseñado con anterioridad. Siempre y cual devuelva un valor **boolean.**

## Condicional con **else**

En ocasiones también querremos ejecutar cierto código si la condición es **false,** para ello podemos usar la otra parte de la condicional: **else.**

~~~
let edad = 18 //Declaracion de identificador y su valor

//Condicional
if (edad >= 18) { //Sintaxis de una condicional

	console.log("Eres mayor de edad");

	/*El codigo que se encuentra dentro de los {},
	Se ejecutara. si la condicion declarada es true*/

} else { //Sintaxis del else

	console.log("Eres menor de edad");
	
	/*El codigo dentro de los {}, se ejecutara,
	Si el resultado es false*/
}

/*Despues continua el codigo*/
~~~

En una condicional solo puede ejecutarse la parte de **true** o el **false,** después de ejecutarse la parte, el flujo de la programación continuará.

## Condicional **else if**

Podemos anidar ciertas condiciones a un **if,** para eso, necesitamos el uso del **else if**

A diferencia del uso de **else,** el **else if** tiene una condición propia, la cual no depende del **if.**

~~~
let hora = 24; //Declaracion de identificador y valor

if (hora >= 6 && hora < 12) { //Condicion 1

	console.log("Buenos dias");
	//Si la condicion 1 es true, se ejecuta

} else if (hora >= 12 && hora < 18) { //Condicion 2

	console.log("Buenas tardes");
	//Si la condicion 2 es true, se ejecuta

} else if (hora >= 18 && hora < 24) || (hora >= 0 && hora < 6) { //Condicion 3

	console.log("Buenas noches");
	//Si la condicion 3 es true, se ejecuta

} else { //Si ninguna de las condiciones no se cumple

	console.log("Dato de hora no valido");
	//Si ninguna de las condiciones if o else if se cumplen, se ejecuta

}
~~~

Un ejemplo de cómo usar el **else if**

**_Nota:_** Podemos usar el **else** dentro de una condicional general que no cumple con ninguna de las condiciones planeadas.

## Operador ternario

Podemos expresar una condicional simple dentro de un identificador y ser llamado en cualquier momento después de ser declarado. A esto llamamos **operador ternario.**

Para poder declarar un operador de este tipo, se necesita ser una condicional de **una sola línea** y retorna un dato de forma implícita.

~~~
let Edad = 18; //Declaraci0n de la variable Edad

let EresMayor = (Edad >= 18) //Condicional expresada
? "Eres mayor de edad" //return, si es true
: "Eres menor de edad"; //return si es false

console.log(EresMayor); //Llamado a la condicional
~~~

Gracias a estos operadores, podemos realizar una condicional simple con return varias veces, solo con llamar a la expresión

**_Nota:_** Es importante recalcar que para poder funcionar las condicionales, deben ser de **una sola línea por caso de condición.**

## **Switch** case

Los **Switch case** ayudan a poder crear situaciones donde existan muchas condiciones, tal como funcionarían los **if, else if y else.**

La diferencia entre **else if** y un **swich case,** el **switch** se permite visualizar mas expresivo y sencillo

A continuación, un ejemplo de un **switch case:**

~~~
let dia = 0;

switch (dia) { //Sintaxis de switch

	case 0: //Si es 0
		console.log("Domingo");
		break; //Salida
	case 1: //Si es 1
		console.log("Lunes");
		break; //Salida
	case 2: //Si es 2
		console.log("Martes");
		break; //Salida
	case 3: //Si es 3
		console.log("Miercoles");
		break; //Salida
	case 4: //Si es 4
		console.log("Jueves");
		break; //Salida
	case 5: //Si es 5
		console.log("Viernes");
		break; //Salida
	case 6: //Si es 6
		console.log("Sabado");
		break; //Salida
	default: //Si no es ningun caso
		console.log("Día no definido");
		break; //Salida

}
~~~

Si necesitamos verificar condiciones múltiples, es más optimo y legible utilizar **switch case** en lugar de **else if.**

**_Nota:_** Al acabar cada **case,** no olvidemos colocar el **break,** lo que permite salir del **switch** si se cumple.

**_Nota:_** El caso **default,** funciona si ninguno de los casos declarados se cumple, un funcionamiento similar al **else** en una condicional **if.**