
# 16. Try and Catch.

JavaScript permite poder ejecutar instrucciones de manejo de errores, cuando la consola detecta un error en nuestro código, podemos personalizar instrucciones.

Para ello hacemos uso del **try, catch** y **finally.**

La sintaxis es la siguiente.

~~~
//Manejo de errores

try {
	//Aqui se escribe el codigo a ejecutar
} catch (error) {
	//Aqui na el codifo a ejecutar para un error
} finally {
	//Aqui va codigo que se ejecuta, tanto si el try o el catch se activan
}
~~~

**Try:** Dentro del apartado, se escribirá el código que queremos ejecutar con manejo de errores, si dentro de este, JavaScript encuentra un error, se ejecutará el **catch.**

**Catch:** Aquí escribimos el código ejecutado si la consola encuentra un error dentro de bloque **try.**

**Finally:** Este código se ejecuta al final de todos los bloques, tanto si se ejecuta el **try** como el **catch.**

Un ejemplo de un **manejo de errores try-catch**:

~~~
//Ejemplo de try-catch

try {
	//En el try se agrega el codigo a evaluar
	console.log("Mensaje 1");
	noexiste // Error de variable no declarada
	console.log("Mensaje 2"); //Codigo
} catch (error) {
	//Captura cualquier error surgido en el try
	//Se ejecuta si hay un error en el try
	console.log("Error en el try");
	console.log(error); //Impresion de descripcion de error
} finally {
	//Se ejecutara independientemente si se ejecuta el try o el catch, al final de todo
	//console.log("Finally");
}
~~~

## Manejo avanzado de errores

El **try-catch** permite la creación de **errores personalizados,** a continuación, un ejemplo más amplio.

~~~
//Manejo de errores avanzados

try {
	let numero = "Sam";
	//Declaracion de numero

	if (isNaN(numero)) {
		//Si numero no es un numero
		
		throw new Error ("El caracter introducido no es un numero");
		//Creacion de un nuevo error y mensaje de error
	}

	console.log(numero * numero);
	//Multiplicacion de numero

} catch (error) {
	//Captura de error
	console.log(`Se produjo el siguiente error: ${error}`);
	//Impresion del manejo de error recibido
	
} finally {
	//console.log("Gracias por usar el programa");
	//Final del programa
}
~~~