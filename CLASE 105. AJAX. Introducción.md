# 105. AJAX. Introduction.

	AJAX: Asynchronous JavaScript & XML.

***AJAX*** es un ***mecanismo*** que posee ***JavaScript*** para poder manejar la ***asincronia*** y ***peticiones***.

## Metodos:

***AJAX*** tiene funcionamiento de diferentes ***métodos***, ante las diferentes versiones antes de la ***estandarización*** de la ***web***.

	1. ActiveXObject (IE8 e inferiores)
	2. XMLHttpRequest
	3. API Fetch

Todas se ***utilizan*** o se ***utilizaron*** para el ***manejo de peticiones asíncronas***.

## Librerias externas

También ***existen librerías externas*** fuera de ***JS vanila***, útiles, que facilitan las funciones de las ***peticiones***.

	1. JQuery
	2. Axios
	3. etc.

## Otros datos

Las ***peticiones*** tienen diferentes ***estados***, los cuales son numerados y nos ayudan a poder identificarlos de mejor manera.

	READY_STATE_UNINITIALIZED = 0
	READY_STATE_LOADING = 1
	READY_STATE_LOADED = 2
	READY_STATE_INTERACTIVE = 3
	READY_STATE_COMPLETE = 4

***Todos*** estos ***estados*** nos permiten identificar en que parte del ***cliclo de vida*** se encuentra la ***petición***.

## Status de peticiones

Para la ***mejor comprensión*** de las ***peticiones*** es importante, entender los ***diferentes status*** de una ***petición HTTP***.

Más ***información***:

	https://developer.mozilla.org/es/docs/Web/HTTP/Status


Ejemplo:

~~~
https://api.github.com/users/[usuariodegithub]
~~~

Un ***ejemplo*** de uso de ***API*** de ***github*** que devuelve un ***JSON***.

