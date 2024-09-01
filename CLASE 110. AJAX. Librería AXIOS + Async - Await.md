# 110. AJAX: Library AXIOS + Async - Await.

La librería ***AXIOS*** también permite poder ejecutar ***peticiones asíncronas*** utilizando ***funciones asíncronas***.

Este ***método*** es muy similar a la ***lección 108. AJAX. API Fetch + Async-Await***.

## Creación de función asíncrona

Primeramente, se debe crear la ***función asíncrona***, dentro de la cual colocaremos un ***try-catch***, y donde se colocara el código y la ***petición asíncrona AXIOS***.

~~~
//Funcion asincrona getData
async function getData() {

	//try
	try {

	//catch
	} catch (error) {

	//Finally
	} finally {

		//Impresion de mensaje dentro del finally
		console.log("finally");
	}
}

//Invocacion de funcion asincrona getData
getData();
~~~

## Declaración de función asíncrona con AXIOS

Dentro de ***try*** colocaremos la ***petición AXIOS***, acompañado de ***await***.

De la siguiente manera:

~~~
//Peticion axios con URL a la API y almacenamiento en identificador await
let res = await axios.get("https://jsonplaceholder.typicode.com/users");
~~~

Quedando de la siguiente manera el ***código***:

~~~
//Funcion asincrona getData
async function getData() {

	//try
	try {

		//Peticion axios con URL a la API y almacenamiento en identificador await
		let res = await axios.get("https://jsonplaceholder.typicode.com/users");

		//Impresion de respuesta
		console.log(res);

		//Impresion de data dentro de respuesta
		console.log(res.data);

	//catch
	} catch (error) {

		//Impresion de error
		console.log(error);

		//Impresion de mensaje dentro de error
		console.log(error.message);

		//Impresion de objeto response dentro de error, el cual tiene mas informacion
		console.log(error.response);

		//Impresion de status
		console.log(error.response.status);

		//Impresion de texto de status
		console.log(error.response.statusText);

	//Finally
	} finally {

		//Impresion de mensaje dentro del finally
		console.log("finally");
	}
}

//Invocacion de funcion asincrona getData
getData();
~~~

***Nota:*** Recordemos que las respuesta de ***AXIOS*** tienen un ***.data*** donde se almacena la ***data*** de la petición y un ***.response***, donde se obtiene información.

