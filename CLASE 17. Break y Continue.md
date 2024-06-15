
# 17. Break and Continue.

Para un mejor uso y manejo de código, el lenguaje nos permite el uso de **break** y **continue.**

Estos elementos son mas usados para excepciones dentro de los **loops** o **bucles.**

## Break

El uso del elemento **break,** funciona para poder terminar un bloque de código y salir de este si se ejecuta en **loop.**

Para una mejor comprensión, se presenta el siguiente código.

~~~
let arreglo = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]

//break
//Termina el bloque o ciclo y sale

for (let i = 0; i < arreglo.length; i++) {
	//for para el array arreglo

	if (i === 5) { //Si i es igual a 5
		break; //Salir de la estructura
	}

	console.log("break " + arreglo[i]);
}
~~~

## Continue

A diferencia del elemento **break, continue** tiene la función de terminar un bloque de código, pero sin salir de este, si se trata de un **loop.**

Si se tratara de un **bucle, continue** terminará la iteración del **loop** pero a continuación, seguirá la iteración siguiente.

A continuación, un ejemplo del elemento **continue.**

~~~
let arreglo = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]

//cotinue
//Termina el bloque o ciclo pero no sale

for (let i = 0; i < arreglo.length; i++) {
	//for para el array arreglo

	if (i === 5) { //Si i es igual a 5
		continue; //Salir del loop actual
	}

	console.log("continue " + arreglo[i]);
}
~~~

