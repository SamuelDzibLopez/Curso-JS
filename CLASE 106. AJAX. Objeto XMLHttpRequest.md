# 106. AJAX. XMLHttpRequest Object.

En esta ***sesión*** aprenderemos a utilizar ***AJAX*** por medio del ***método  XMLHttpRequest***, por medio de ejemplo y explicación.

Para ello, ***utilizaremos*** la ***API externa*** de ***JSONPlaceholder***:

	https://jsonplaceholder.typicode.com/

***Nota:*** El ***sitio web oficial*** explica más sobre su funcionamiento.

## Pasos de una petición XMLHttpRequest

Para poder realizar una ***peticion AJAX*** mediante ***XMLHttpRequest***, se necesitan ***seguir*** una ***serie de pasos*** con la ***intancia*** creada de ***XMLHttpRequest***.

### Paso 1. Inicialización de nueva Instancia XMLHttpRequest

Como ***primer paso*** se debe ***inicializar*** una ***nueva instancia*** tipo ***XMLHttpRequest***.

Ejemplo:

~~~
//1. Creacion de nueva instancia
const xhr = new XMLHttpRequest();
~~~

***Nota:*** La ***instancia creada*** debe ser almacenada en un ***identificador***, para poder ser ***utilizado***.

### Paso 2.  Asignación de evento a la petición XMLHttpRequest

Como ***segundo paso***, se debe asignar un evento a la ***petición***.

Por los general, este evento suele ser ***readystatechange***, que es cada que la ***petición*** cambia de sus ***estados***.

Ejemplo:

~~~
//2. Asignacion de eventos
xhr.addEventListener("readystatechange", e => {
	//Codigo
});
~~~

***Nota:*** Dentro de la ***función*** se logra obtener la ***respuesta de la petición***, pero aun faltan otros ***pasos*** para su funcionamiento.

### Paso 3. Declaración de end-point de la petición XMLHttpRequest

El ***tercer paso*** sera realizar el ***end-point*** de la ***petición***, es decir, hacia que ***API*** apuntamos para su ***utilización***. 

Para ello, se utiliza el ***método open***.

Ejemplo:

~~~
//3. Declaracion de end-point
xhr.open("GET", "https://jsonplaceholder.typicode.com/users");
~~~

***Nota:*** El ***método open*** recibe ***2 parámetros***, el ***primero*** sera el ***método*** por el cual se realizará la ***petición*** (***GET*** o ***POST***), y como ***segundo parámetro***, la ***URL*** de la ***API***.

En caso de tener un ***archivo JSON*** local a utilizar, se debe colocar la ***URL*** del archivo.

### Paso 4. Envío de petición XMLHttpRequest

Finalmente, el ***cuarto paso*** es ***enviar*** y ***realizar*** la ***petición***

Ejemplo:

~~~
//4. Envio de peticion
xhr.send();
~~~

Esto se realiza con el ***método send***.

## Propiedades y datos de una petición XMLHttpRequest

Una vez realizado los ***4 pasos***, se realizará la ***petición***, devolviendo (si se realizo de manera exitosa o no) una ***respuesta***.

Podemos acceder a estos ***datos***, para ello deberemos introducirnos en la ***función*** del evento asignado en el ***paso 2***.

Ejemplo:

~~~
//2. Asignacion de eventos
xhr.addEventListener("readystatechange", e => {

	//Si el estado de la peticion es 4 (Finalizado)
	if (xhr.readyState !== 4) return

	//Objeto XMLHttpRequest
	console.log(xhr);

	//Estado de la peticion
	console.log(xhr.readyState);

	//Respuesta de la peticion
	console.log(xhr.response);

	//Respuesta de la peticion en texto
	console.log(xhr.responseText);

	//Respuesta de la peticion en XML
	console.log(xhr.responseXML);

	//Status de la peticion
	console.log(xhr.status);

	//boolean para tipo de API (publica o privada)
	console.log(xhr.withCredentials);

});
~~~

Algunas de las ***principales propiedades*** son 

- ***readyState***: Devuelve un ***numero*** (1-4), dependiendo de en que ***estado*** se encuentra la ***petición***.
- ***response***: Devuelve la ***respuesta*** de los datos devueltos por la ***API***.
- ***responseText***: Devuelve la ***respuesta*** en tipo ***texto*** como ***JSON***.
- ***responseXML***: Devuelve la ***respuesta*** en tipo ***XML***.
- ***status***: Devuelve el ***status*** (diferente al ***estado***) de la ***petición***.
- ***withCredentials***: Devuelve un ***boolean***, dependiendo de si la ***petición*** requiere ***credenciales*** (true) o si no (false).

Gracias a estas ***propiedades*** podemos realizar ***validaciones*** en nuestra logica de programación a gusto.

Todo el ***código completo*** de la ***lección***:

~~~
//Funcion anonima autiejecutable
(() => {

	//1. Creacion de nueva instancia
	const xhr = new XMLHttpRequest();

	//2. Asignacion de eventos
	xhr.addEventListener("readystatechange", e => {

		//Si el estado de la peticion es 4 (Finalizado)
		if (xhr.readyState !== 4) return

		//Objeto XMLHttpRequest
		console.log(xhr);

		//Estado de la peticion
		console.log(xhr.readyState);

		//Respuesta de la peticion
		console.log(xhr.response);

		//Respuesta de la peticion en texto
		console.log(xhr.responseText);

		//Respuesta de la peticion en XML
		console.log(xhr.responseXML);

		//Status de la peticion
		console.log(xhr.status);

		//boolean para tipo de API (publica o privada)
		console.log(xhr.withCredentials);

	});

	//3. End-point
	xhr.open("GET", "https://jsonplaceholder.typicode.com/users");

	//4. Envio de peticion
	xhr.send();
}) ();
~~~

