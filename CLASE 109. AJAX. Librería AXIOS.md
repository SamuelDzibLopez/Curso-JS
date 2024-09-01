# 109. AJAX: Library AXIOS.

Otra ***forma*** de poder realizar ***peticiones asíncronas*** sin utilizar el ***método XMLHTTPRequest*** o ***API Fetch*** es por medio de librería. En esta ***lección*** se enseñara la ***librería AXIOS***. 

***AXIOS*** es una ***librería*** que trabaja tanto con ***promesas*** como con ***funciones asíncronas***. En esta ***lección*** se enseñara su manejo con ***promesas***.

Para mas información:

	https://axios-http.com

## Importación de librería AXIOS

Primeramente, es necesario ***importar*** la ***librería*** en nuestro proyecto. Para ello podemos utilizar ***npm***.

O de una manera mas sencilla, añadiendo la ***etiqueta script*** para enlazar la librería:

~~~
<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
~~~

***Nota:*** No olvidemos colocar primeramente el ***script*** de la librería, antes que el ***script*** de nuestro código.

## Utilizar AXIOS

Para realizar una ***petición AXIOS*** debemos seguir la sintaxis.

Un ejemplo:

~~~
//Peticion axios con URL a la API
axios.get("https://jsonplaceholder.typicode.com/users")
~~~

***Nota:*** Existe tanto el ***método get*** como el ***post***, dependiendo la situación.

Como una ***petición AXIOS*** utiliza ***promesas***, significa que tiene los ***métodos then, catch*** y ***finally***.

~~~
//Peticion axios con URL a la API
axios.get("https://jsonplaceholder.typicode.com/users")

//Then
.then(resp => {

	//Respuesta asincrona
	console.log(resp);

	//.data es donde se encuentra la data de la respuesta asincrona
	console.log(resp.data);
})
//Catch
.catch(error => {

	//Impresion de error
	console.log(error);

	//Impresion de informacion de error
	console.log(error.response)

	//Impresion de texto de error
	console.log(`Error en el catch ${error.response.status}`);
})
//Finally
.finally(
	console.log("Método finally")
)
~~~

Para la ***respuesta*** los datos se encuentran dentro de ***.data***, sin necesidad de convertir esta, como sucedía como en ***fetch*** o ***XMLHTTPRequest***.

En caso de error, podemos obtener mas información en ***.response***, incluyendo el ***status*** y otros datos importantes.

