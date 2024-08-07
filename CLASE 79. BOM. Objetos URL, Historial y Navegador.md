# 79. BOM: Objects URL, History and Browser.

Para poder ***manejar*** e ***interactuar*** de una mejor manera con las opciones que nos proporciona el ***browser***, existen ***3 objetos*** que proporcionan información y métodos útiles:

	1. Location
	2. History
	3. Navigator

Estos ***objetos*** contienen tanto ***atributos*** y ***métodos*** para interactuar y obtener datos de ***historial***, ***datos de la pagina*** y ***navegador***.

## Location

Este ***objeto*** (location) permite poder obtener información sobre la ***URL***:

~~~
//Location

//Impresion de objeto location
console.log(location);

//Impresion de URL completo (protocolo, URL, puerto)
console.log(location.origin);

//Impresion de protocolo
console.log(location.protocol);

//Impresion de host (URL, puerto)
console.log(location.host);

//Impresion de nombre del dominio
console.log(location.hostname);

//Impresion de numero de puerto
console.log(location.port);

//Impresion de localizacion completa de archivo (protocolo, URL, puerto, direccion de archivo)
console.log(location.href);

//Impresion de hash actual de la URL de la pagina
console.log(location.hash);

//Impresion de datos actuales de la URL de la pagina
console.log(location.search);

//Impresion de direccion de archivo
console.log(location.pathname);

//Asignacion de funcion de evento "click" a document
document.addEventListener("click", (e) => {

	//metodo reload

	//Recargar la pagina
	location.reload();
});
~~~

***Nota:*** Algunos de los ***atributos*** pueden ser definidos como ***nulos***, debido a que no tienen un valor.

el ***método reload*** permite poder ***recargar*** la pagina.

## History

El ***objeto history*** permite ***obtener información*** y ejecutar ***métodos*** relacionados con las paginas del ***historial***.

Para la explicación de este ***objeto***, utilizaremos la ***estructura HTML*** siguiente para los ejemplos:

~~~
<button id="atras">Atras</button>
<button id="adelante">Adelante</button>
~~~

Donde existen ***2 botones***.

En el ***código JS***:

~~~
//History

//Impresion de objeto history
console.log(history);

//Impresion de numero de URLs guardados dentro del historial de la pestaña del navegador (tamaño de history)
console.log(history.length);

//Captura de botones HTML con su id y almacenamiento en identificadores
const $btnAtras = document.getElementById("atras");
const $btnAdelante = document.getElementById("adelante");

//Asignacion de funcion de evento a boton de atras
$btnAtras.addEventListener("click", (e) => {

	//Ir hacia la pagina -1 en relacion a la actual
	history.go(-1);

	//Retroceder una pagina del historial
	//history.back(1);
});

//Asignacion de funcion de evento a boton de adelante
$btnAdelante.addEventListener("click", (e) => {

	//Ir hacia la pagina 1 en relacion a la actual
	history.go(1);

	//Avanzar una pagina del historial
	// history.forward(1);
});
~~~

***Nota:*** el ***objeto history*** obtiene las ***URLs anteriores*** y ***siguientes*** del ***historial***. 

## Navigator

El ***objeto navigator*** obtiene ***información*** y ***métodos útiles*** del ***navegador***:

~~~
//Navigator

console.log(navigator);

//Metodo para informacion de conexion
console.log(navigator.connection);

//Metodo para utilizar la geolocalizacion
console.log(navigator.geolocation);

//Compatibilidad con archivos media del navegador
console.log(navigator.mediaDevices);

//Compatibilidad con archivos de texto del navegador
console.log(navigator.mimeTypes);

//Impresion de valor boolean de conexion (true: conectado y false: no conectado)
console.log(navigator.onLine);


console.log(navigator.serviceWorker);
console.log(navigator.storage);

//Metodo para identificar USBs
console.log(navigator.usb);

//Impresion de informacion de version de navegador
console.log(navigator.userAgent);
~~~

***Nota:*** Algunos de estos pueden no ser compatibles, dependiendo del ***navegador***.
