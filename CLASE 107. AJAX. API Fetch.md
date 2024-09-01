# 107. AJAX. API Fetch.

La ***API*** de ***Fetch*** es otra forma de poder ***ejecutar peticiones asíncronas*** del servidor.

En esta ***lección*** se presentara como utilizar ***fetch***, el cual fue diseñado primero a utilizar con ***promesas***, aunque puede utilizar otro ***método*** también.

La sintaxis de una ***petición fetch*** es la siguiente:

~~~
//Fetch
fetch("https://jsonplaceholder.typicode.com/users")
~~~

***Nota:*** Es una ***función*** que recibe como ***parámetro*** el ***string*** de la ***URL***.

También se permite recibir un ***segundo parámetro objeto*** con datos para la ***petición***.

Otro ejemplo:

~~~
//Fetch
fetch("https://jsonplaceholder.typicode.com/users", {
	method: "GET"
})
~~~

***Nota:*** Por ***default*** el ***método*** de la ***petición*** es ***GET***.

## Recibir respuesta

***Fetch*** funciona con ***promesas***, por lo que para recibir los datos (***respuesta*** o ***error***) tiene sus ***métodos*** (explicados en la ***lección 47. Promesas***) ***then*** y ***catch*** (también ***finally***, pero este no es necesario).

Un ***ejemplo*** de funcionamiento de ***then***:

~~~
//Fetch
fetch("https://jsonplaceholder.typicode.com/users", {
	method: "GET"
})

//Then de Fetch
.then(res => {
	//Impresion de response
	console.log(res);

	//Return de response como JSON
	return res.json();
})
~~~

	Otros tipos de datos para returns

	res.text(); (texto)
	res.blob(); (imagenes)

Donde el ***then*** retorna la ***respuesta*** en formato ***json***, listo para utilizarse en el siguiente ***then***, quedando el ***código*** de la siguiente manera:

~~~
//Fetch
fetch("https://jsonplaceholder.typicode.com/users", {
	method: "GET"
})

//Then de Fetch
.then(res => {
	//Impresion de response
	console.log(res);

	//Return de response como JSON
	return res.json();
})
//Segundo Then que recibe el respnse del primero ya como json
.then(json => {
	//Impresion de json
	console.log(json);
})
~~~

Y el ***catch*** y el ***Finally***:

~~~
//Fetch
fetch("https://jsonplaceholder.typicode.com/users", {
	method: "GET"
})

//Then de Fetch
.then(res => {
	//Impresion de response
	console.log(res);

	//Return de response como JSON
	return res.json();
})
//Segundo Then que recibe el respnse del primero ya como json
.then(json => {
	//Impresion de json
	console.log(json);
})
//Catch
.catch(err => {
	console.log(err);
})
//Finally
.finally(() => {
	//Codigo que siempre se ejecuta
	console.log("Codigo de ejecucion independiente")
});
~~~

	Todos los otros métodos explicados en las Promesas, se pueden utilizar.

Si ponemos el código en una ***función anónima autoejecutable***:

~~~
//Función anonima autoejecutable
(() => {
	//Fetch
	fetch("https://jsonplaceholder.typicode.com/users", {
		method: "GET"
	})

	//Then de Fetch
	.then(res => {
		//Impresion de response
		console.log(res);

		//Return de response como JSON
		return res.json();
	})
	//Segundo Then que recibe el respnse del primero ya como json
	.then(json => {
		//Impresion de json
		console.log(json);
	})
	//Catch
	.catch(err => {
		console.log(err);
	})
	//Finally
	.finally(() => {
		//Codigo que siempre se ejecuta
		console.log("Codigo de ejecucion independiente")
	});
})();
~~~

El ***código*** de una ***petición fetch*** utilizando ***promesas*** se vería de la anterior forma.
