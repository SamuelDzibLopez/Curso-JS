# 78. BOM: Methods.

En ***clases anteriores*** se enseñaron los ***metodos alert,*** ***confirm*** y ***prompt***, estos ***métodos*** en realidad, pertenecen al ***BOM***.

Pero ademas de ellas, existen otros ***métodos*** útiles para poder ***interactuar*** con el ***browser***.

Para esta ***lección*** se utilizará la siguiente ***estructura HTML***:

~~~
<button id="open">Abrir Ventana</button>

<button id="close">Cerrar Ventana</button>

<button id="print">Imprimir Ventana</button>
~~~

***3 botones***, para poder ejemplificar los ***métodos***.

Y en nuestro ***archivo JS***:

~~~
//Captura de elemento con id "open" y almacenar en $btnOpen
const $btnOpen = document.getElementById("open");

//Captura de elemento con id "close" y almacenar en $btnClose
const $btnClose = document.getElementById("close");

//Captura de elemento con id "print" y almacenar en $btnPrint
const $btnPrint = document.getElementById("print");
~~~

Se ***capturan*** los ***3 elementos*** para ser utilizados.
## open

El ***método open*** se utiliza para poder ***interactuar*** con el ***navegador*** para poder abrir una nueva ***pestaña*** del ***navegador*** con una ***URL*** personalizada.

Para ello utilizamos:

~~~
//Abrir pestaña emergente
window.open("URL");
~~~

Un ejemplo:

~~~
let ventana;

//Asignacion de funcion de evento click al boton de open
$btnOpen.addEventListener("click", (e) => {

	//Abrir ventana emergente
	ventana = window.open("https://www.youtube.com");
	//Podemos omitir el window
	//Alamacenar en una variable es para poder cerrarla con el metodo close

});
~~~

Al igual que explicado con ***alert***, podemos omitir el ***window***.

Al ***almacenar*** el ***método open*** en un ***identificador***, permite poder utilizar el ***próximo método*** llamado ***close***.

## close

El ***método close*** se el ***método contrario*** a ***open***, el cual permite cerrar la ***ventana emergente***.

Su sintaxis:

~~~
const ventana;

ventana = window.open("https://www.youtube.com");

//Cerrar pestaña emergente alamacenada en identificador
ventana.close();
~~~

***Nota:*** Para poder ***utilizar*** este ***método***, se necesita almacenar el ***método open*** en un ***identificador***, para poder ser utilizado en el ***close***.

	Este método no es un estandar, por lo que en ciertos Navegadores, este no funciona.

Un ejemplo:

~~~
//Asignacion de funcion de evento click al boton de close
$btnClose.addEventListener("click", (e) => {

	//cerrar ventana emergente almacenada en ventana 
	ventana.close();
});
~~~

## print

Este ***método*** permite poder ***abrir la interfaz*** de ***impresión*** para la ***pagina web***.

Su sintaxis:

~~~
//Abrir la interfaz de impresion
window.print();
~~~

***Nota:*** Esta interfaz permite tanto ***imprimir*** el documento, como ***guardar*** como ***PDF***.

Un ejemplo:

~~~
//Asignacion de funcion de evento click al boton de print
$btnPrint.addEventListener("click", (e) => {

	//Abrir la interfaz de impresion
	window.print();
});
~~~