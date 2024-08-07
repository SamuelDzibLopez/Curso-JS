# 64. DOM: Styles and CSS Variables.

Con ***JavaScript*** podemos agregar ***estilos y variables CSS*** a un elemento deseado.

Para los ***ejemplos*** de esta clase, tendremos el siguiente ***elemento***.

~~~
<a href="https://www.youtube.com" id="enlace" target="_blank" style="background-color: yellow; color: black;">Enlace</a>
~~~

Un ***enlace*** con ***estilos CSS*** desde el ***HTML***.

## Capturar elementos HTML en identificadores

Como ***primer paso*** aprendemos a almacenar ***elementos HTML*** en ***identificadores***, esto permite ahorrar código que podría ser ***repetitivo***, al momento de utilizarse en diferentes ocasiones.

Tomemos por ***ejemplo*** el ***enlace***.

Almacenar el ***elemento*** en un ***identificador***, permite poder ser utilizada de manera ***más practica***.

~~~
//Almacenar el elemento con id "enlace" en identificador
const $linkDOM = document.getElementById("enlace");

//Impresion de identificador con valor del elemento
console.log($linkDOM);
~~~

***Nota:*** Podemos almacenar los ***elementos*** en identificadores ***const***, y poder modificarse sin preocuparse sin problemas.

***Nota:*** Es una ***buena practica recomendable*** identificar los ***identificadores*** para ***elementos*** colocándoles un signo ***$*** al inicio del ***nombre***.

## Acceder a estilos CSS

Al igual que los ***atributos*** en un ***elemento***, existen ***3 maneras*** de acceder a los ***estilos CSS***.

### Notación de punto

Podemos acceder a las ***propiedades CSS*** de un ***elemento HTML*** desde ***JS***, para ello, accedemos como si fuese una ***propiedad*** común llamada ***style***.

~~~
//Almacenar el elemento con id "enlace" en identificador
const $linkDOM = document.getElementById("enlace");

//Impresion de propiedades CSS
console.log($linkDOM.style);
~~~

Esta ***propiedad*** devuelve una ***lista*** de ***TODAS*** las ***propiedades CSS existentes***, ya sean definidas o no definidas.

También podemos especificar mejor a una ***propiedad de estilo***.

~~~
//Impresion de valor de propiedad CSS color
console.log($linkDOM.style.color);
//black

//Impresion de valor de propiedad CSS background-color
console.log($linkDOM.style.backgroundColor);background
//Yellow
~~~

***Nota:*** Las ***propiedades CSS*** en dentro de ***.style*** se encuentran escritas con el formato de ***lowerCamelCase***.

### Método getAttribute

Podemos usar el mismo ***método*** que para obtener un atributo, pero usando el ***parámetro style***.

~~~
//Almacenar el elemento con id "enlace" en identificador
const $linkDOM = document.getElementById("enlace");

//Impresion de propiedades CSS espeficicadas
console.log($linkDOM.getAttribute("style"));
~~~

### Método getComputedStyle de window

Existe un ***tercer método*** para poder obtener los ***estilos CSS*** de un ***elemento***, para ello utilizamos ***getComputedStyle***.

Este ***método*** es utilizado desde el ***window*** y recibe como ***parametro*** el ***elemento*** al que se desea obtener sus ***estilos***.

Un ejemplo de sintaxis:

~~~
//Almacenar el elemento con id "enlace" en identificador
const $linkDOM = document.getElementById("enlace");

//Impresion de propiedades CSS interpretadas por el navegador
console.log(window.getComputedStyle($linkDOM));
~~~

***getComputedStyle*** tiene un cambio en comparación con los anteriores ***2 métodos***, en este se devuelven los ***valores*** de las ***propiedades CSS*** ya interpretadas por el ***navegador***, ya sean, ***definidas*** o ***default***.

Ademas de una ***colección*** de todos los ***nombres*** de las ***propiedades*** existentes y soportadas por el ***browser***.

Para acceder a una ***propiedad*** en especifico, podemos usar la ***notación de punto***:

~~~
//Almacenar el elemento con id "enlace" en identificador
const $linkDOM = document.getElementById("enlace");

//Almacenamiento de estilos del elemento guardado en $linkDOM
let estilos = window.getComputedStyle($linkDOM);

//Impresion de propiedad CSS "color" con notacion de punto
console.log(estilos.color);
~~~

O por el ***método getPropertyValue***:

~~~
//Almacenar el elemento con id "enlace" en identificador
const $linkDOM = document.getElementById("enlace");

//Almacenamiento de estilos del elemento guardado en $linkDOM
let estilos = window.getComputedStyle($linkDOM);

//Impresion de propiedad CSS "color" con metodo getPropertyValue
console.log(estilos.getPropertyValue("background-color"));
~~~

***Nota:*** con ***getPropertyValue*** utilizamos la ***sintaxis*** de ***CSS*** (utilizando los ***-*** entre palabras), mientras que con la ***notación de punto*** seguimos con el ***lowerCamelCase***.

## Modificar y agregar estilos CSS

Para ***modificar*** y ***agregar estilos CSS*** a un ***elemento***, existen igualmente ***2 maneras diferentes***.

### Método setProperty

Para este primera forma basta con usar el ***método setProperty*** de ***style***.

Por ejemplo, ***modificar*** el ***subrayado*** de un ***elemento***:

~~~
//Almacenar el elemento con id "enlace" en identificador
const $linkDOM = document.getElementById("enlace");

//Modificar la propiedad "text-decoration" de un elemento
$linkDOM.style.setProperty("text-decoration", "none");
~~~

***Nota:*** ***Modificar*** y ***agregar*** son los mismo, ***únicamente cambiando*** los valores ***default*** de una ***propiedad***.

Este ***método*** recibe ***2 parámetros***, el ***nombre*** de la ***propiedad CSS*** y el ***valor*** de dicha ***propiedad***, ambos en ***formato string***.

### Notación de punto

De manera mas sencilla, y como los ejemplos de aplicación de esta misma notación, basta con especificar la ***propiedad CSS*** y su valor de manera expresiva.

Un ejemplo:

~~~
//Almacenar el elemento con id "enlace" en identificador
const $linkDOM = document.getElementById("enlace");

//Modificar propiedad "border" de un elemento
$linkDOM.style.border = "1px solid red";
~~~

***Nota:*** No olvidemos el ***lowerCamelCase*** al nombrar las ***propiedades CSS*** y escribir el valor en ***string***.

## Variables CSS

Si tenemos ***variables CSS*** (Ya sea declaradas en nuestro archivo ***.html*** o ***.css***), podemos acceder a ellas, de la siguiente manera:

Supongamos que tenemos las siguientes ***variables CSS***:

~~~
:root {
	--white-color: yellow;
	--dark-color: green;
}
~~~

### Acceder a variables CSS

Para acceder a ellas:

	- Nos ubicamos en el document.documentElement
	- Utilizamos el método getComputedStyle para obtener los estilos CSS del HTML completo
	  - Y utilizamos el método getPropertyValue para obtener el valor de la variable

Como el siguiente ejemplo:

~~~
//Asignacion de contenido HTML a identificador
const $HTML = document.documentElement;

//Asignacion de estilos CSS HTML de $HTML a identificador
const $HTMLstyle = getComputedStyle($HTML);

//Asignacion de valor de variable CSS
let whiteColor = $HTMLstyle.getPropertyValue("--white-color");

//Asignacion de valor de variable CSS
let blackColor = $HTMLstyle.getPropertyValue("--dark-color");

//Impresion de whiteColor
console.log(whiteColor);

//Impresion de darkColor
console.log(blackColor);
~~~

### Utilizar variables CSS en elementos

Para ***utilizarlas*** en una ***propiedad CSS*** de algún ***elemento***, aplicamos lo aprendido con las ***propiedades*** comunes:

~~~
//Asignacion a propiedad "color" de $body la variable CSS
$body.style.color = whiteColor;

//Asignacion a propiedad "backgroundColor" de $body la variable CSS
$body.style.backgroundColor = blackColor;
~~~

	- Nos ubicamos en la propiedad de los estilos de el elemento que deseamos cambiar y declaramos 

También puede hacerse con el ***método correspondiente*** explicado con anterioridad.

### Modificar variables CSS y actualizar vista

Para ***modificar*** el valor de una ***variable CSS***, podemos utilizar el ***método setProperty*** y declarar un nuevo valor.

~~~
//Cambiar el valor del valor de la variable CSS
$HTML.style.setProperty("--white-color", "pink");
~~~

En ocasiones, en especial, cuando la ***asignación de valores*** de las ***variables CSS*** han sido asignadas o modificadas con ***JS*** con anterioridad, es necesario, actualizar en el ***documento*** el valor nuevo.

Para ello:

~~~
//Asginacion de nuevo valor de valiable CSS
whiteColor = getComputedStyle($HTML).getPropertyValue("--white-color");

//Actualizacion de neuvo valor de variable CSS en el body 
$body.style.setProperty("color", whiteColor);
~~~