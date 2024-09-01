# 108. AJAX. API Fetch + Async-Await.

Como se presento en la ***lección anterior***, la ***API*** de ***fetch*** sirve para poder ejecutar ***peticiones asíncronas***.

***Fetch*** suele utilizarse con ***promesas***, pero también permite poder ejecutarse con ***funciones async*** y ***await***, lo cual se enseñará a continuación.

***Nota: Async*** y ***await*** fue explicado en la ***lección 48. Async y Await***.

A continuación, se presenta la forma en que se realiza una ***petición fetch*** por medio de una ***función async*** y ***await***.

## Función asíncrona

Primeramente se necesita ***definir*** una ***función*** de modo ***async***.

~~~
//Funcion asincrona getData
async function getData () {
	//Contenido
}
~~~

De esta manera, dentro de esta ***función***, la cual es ***asíncrona***, podremos utilizar el ***await*** dentro, para poder realizar el ***fetch***.

Dentro de esta ***función*** podremos definir la ***petición fetch***.

***Nota:*** Se recomienda utilizar ***try*** y ***catch*** (y ***finally***) para estos métodos. explicado en la ***lección 16. Manejo de errores***.

~~~
//Funcion asincrona getData
async function getData () {

	//try del codigo a ejecutar
	try {

	//catch para atrapar el error
	} catch (error) {

	//finally para ejecutar codigo independientemente del resultado
	} finally {

	}
}  
~~~

Dentro de ***try***, podremos ejecutar el ***código*** de la ***petición***.

~~~
//Funcion asincrona getData
async function getData () {

	//try del codigo a ejecutar
	try {

		//Peticion fetch cuya respuesta sera almacenada en un identificador resp, colocando el await
		let resp = await fetch("https://jsonplaceholder.typicode.com/users", { method: "GET" });

		//Conversion de la respuesta en JSON y almacenamiento en json, colocando el await
		let json = await resp.json();

		//Impresion de respuesta
		console.log(resp);

		//Impresion de json
		console.log(json);

	//catch para atrapar el error
	} catch (error) {

	//finally para ejecutar codigo independientemente del resultado
	} finally {

	}
}  
~~~

La ***petición fetch*** debe ser ***almacenado*** en un ***identificador*** (en el ejemplo anterior: ***resp***) y utilizar ***await***, para obligar al ***flujo de código*** a ***esperar*** que se termine la ***petición***.

De igual manera, la conversión de la ***respuesta*** a ***json*** (o ***blob*** o ***text***), debe ser definida con ***await***.

De esta manera, podremos utilizar el ***data*** de la ***petición***.

Finalmente, invocar la ***función asíncrona***.

~~~
//Ejecucion de funcion getData
getData();
~~~

	Se puede utilizar todos los metodos y funciones de los try-catch y los async-await explicados en anteriores clases.

## Función asíncrona  devolviendo un return

En ***ocasiones*** es recomendable realizar ***funciones asíncronas*** que retornen la ***respuesta*** que realizará la ***petición fetch*** dentro de esta.

~~~
//Función anonima autoejecutable, declarada como asincrona con el async
(async () => {

	//Funcion asincrona getData
	async function getData () {

		//try del codigo a ejecutar
		try {

			//Peticion fetch cuya respuesta sera almacenada en un identificador resp, colocando el await
			let resp = await fetch("https://jsonplaceholder.typicode.com/users", { method: "GET" });

			//Conversion de la respuesta en JSON y almacenamiento en json, colocando el await
			let json = await resp.json();

			//Impresion de respuesta
			console.log(resp);

			//retunr de json
			return json;

		//catch para atrapar el error
		} catch (error) {

		//finally para ejecutar codigo independientemente del resultado
		} finally {

		}
	}

	//Ejecucion de funcion getData y obtencion de dato return en identificador respuesta. colocando el await
	const respuesta = await getData();

	//Impresion de respuesta
	console.log(respuesta);

})();
~~~