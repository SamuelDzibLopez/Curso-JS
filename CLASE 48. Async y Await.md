
# 48. Async and Await.

Las ***funciones asíncronas*** permiten una ***mejor sintaxis*** que acompaña a las ***promesas***, para ello, basta utilizar estas en lugar de los ***then*** y ***catch***.

Las ***funciones asíncronas*** trabajan con las ***promesas*** pero las reciben diferente a ***then*** y ***catch***.

Podemos tener ***funciones asíncronas declaradas*** y ***funciones asíncronas expresadas***:

## Funciones asíncronas declaradas

La sintaxis simple de una ***función asíncrona declarada*** es la siguiente:

~~~
//Funcion asincrona declarada
async function funcionAsincronaDeclarada () {

	//Metodo try
	try {

		//Llamado a la promesa y obtencion de return
		let objeto = await promesa ();

		//Uso de return de promesa
		console.log(objeto);

	//Metodo catch (recibe como parametro el error)
	} catch (error) {
		//Uso de error
		console.error(error);
	}
}

//Llamado a funcion asincrona declarada
funcionAsincronaDeclarada();
~~~

Antes de declarar la ***función*** se coloca la ***palabra reservada async***.

Para llamar a la función ***promesa***, usamos ***await***.

## Funciones asíncronas expresadas

La sintaxis simple de una ***función asíncrona expresada*** es la siguiente:

~~~
//Funcion asincrona expresada
const funcionAsincronaExpresada = async () => {
	try {

		//Llamado a la promesa y obtencion de return
		let objeto = await promesa ();

		//Uso de return de promesa
		console.log(objeto);

	//Metodo catch (recibe como parametro el error)
	} catch (error) {

		//Uso de error
		console.error(error);
	}
}

//Llamado a funcion asincrona expresada
funcionAsincronaExpresada ();
~~~

El ***async*** se coloca antes de los ***parametros***.

---
$$Observaciones:$$

Los ***returns*** de la ***promesa*** se manejan por medio de un ***try*** (para el ***resolve***) y ***catch*** (para el ***reject***), a diferencia de ***then*** y ***catch***.

Al llamar al la ***función*** que devolverá los datos ***asíncronos*** utilizamos la ***palabra reservada await***, que significa:

	Esperar hasta que el resultado asincrono sea obtenido, para poder continuar.

No olvidemos ***llamar a la función asíncrona***.

---

Para una ***mejor compresión***, el siguiente ejemplo:

Tenemos la misma función para obtener ***datos*** de una ***promesa***:

~~~
//funcion
function cuadradoPromise (value) {

	//Validacion para return negativo
	if (typeof value !== "number") {
		//Return negativo de promesa
		return Promise.reject(`Error, el valor ${value} no es un numero`);
	}

	//Creacion de promesa
	return new Promise((resolve, reject) => {
		//contenido de la promesa

		//setTimeout con temporizador de 0-10 segundos
		setTimeout(()=> {

			//Ejecucion de asincronia

			//Return positivo (si se cumple)
			resolve(
				//Objeto a return
				{
					value,
					result: value * value
				}
			);
		}, 0 || Math.random()*1000);
	});
}
~~~

***Nota:*** Esta función es una ***promesa*** que devuelve un ***dato asincrono***, un ***objeto*** si el parámetro es un numero o un ***mensaje de error*** si no lo es.

***Nota:*** En la clase anterior, recibimos sus datos con ***then*** y ***catch***

Pero esta ocasión, obtendremos los valores con una ***función Async***, de la siguiente manera:

~~~
//Declaracion de funcion asincrona declarada
async function funcionAsincronaDeclarada () {

	try {
		console.log("Inicio de Async function");

		//Llamado a la funcion promesa y obtencion de return
		let objeto = await cuadradoPromise (0);

		//Uso de los datos del return
		console.log(`Async Function: ${objeto.value}, ${objeto.result}`);
		
		//Segundo llamado a la funcion promesa y obtencion de return
		let objeto2 = await cuadradoPromise ("1");

		//Uso de los datos del segundo return
		console.log(`Async Function: ${objeto2.value}, ${objeto2.result}`);

		console.log("Fin de Async function");

	} catch (error) {
		//Uso de error
		console.error(error);
	}
}

//Invocacion de la funcion declarada
funcionAsincronaDeclarada();
~~~

O si queremos una ***función asíncrona expresada***:

~~~
//Expresion de funcion asincrona expresada
const funcionAsincronaExpresada = async () => {

	try {

		console.log("Inicio de Async function");

		//Llamado a la funcion promesa y obtencion de return
		let objeto = await cuadradoPromise (0);

		//Uso de los datos del return
		console.log(`Async Function: ${objeto.value}, ${objeto.result}`);

		//Llamado a la segunda funcion promesa y obtencion de return
		let objeto2 = await cuadradoPromise ("1");

		//Uso de los datos del segundo return
		console.log(`Async Function: ${objeto2.value}, ${objeto2.result}`);

	} catch (error) {
		//Uso de error
		console.error(error);
	}
}

//Invocacion de funcion expresada
funcionAsincronaExpresada ();
~~~

Estas formas permiten una ***sintaxis aun más legible***.

