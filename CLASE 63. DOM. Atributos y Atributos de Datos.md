# 63. DOM: Attributes and Data-Attributes.

Los ***atributos*** son los datos que las ***etiquetas HTML*** conservan en su interior y que ayuda a su funcionamiento correcto al ser mostrados en el ***navegador***.

***JavaScript*** permite poder acceder a ellos y realizar acciones útiles.

***ES6*** permite poder crear ***atributos*** personalizados para nuestras ***etiquetas***, para ello basta con seguir la sintaxis ***data-***.

En ***HTML***:

~~~
<li class="lista" data-description="Element-One">Uno</li>
~~~

***Nota:*** El nombre del ***atributo*** debe comenzar con ***data-***.

## Acceder a un atributo

Para acceder a uno ***atributo*** de un ***elemento*** existen ***2 maneras diferentes***, pero primero vamos paso a paso:

Tenemos el siguiente ***elemento HTML***.

~~~
<a href="#" class="link" data-description="Document Object Model">Enlace</a>
~~~

Y queremos obtener el valor de su ***atributo href***.

	1. Capturar el elemento

~~~
//Impresion de elemento con una consulta de selector de su clase
console.log(document.querySelector(".link"));
~~~

Para obtener el ***valor del atributo*** tenemos ***2 maneras*** y cada una tiene sus diferencias:

### Notación de punto

Podemos acceder al ***valor*** como si fuese un ***objeto*** común de ***JS***, por medio de la ***notación de punto***.
~~~
//impresion de valor de href interpretado
console.log(document.querySelector(".link").href);
~~~

Sin embargo, al acceder de esta ****manera***, el valor que recibimos no es exactamente igual ***explicitamente*** al escrito en el ***elemento***.

	http://127.0.0.1:5500/index.html#

Esto es debido a que con esta notación obtenemos la información ***interpretada*** por el ***navegador***.

***Nota:*** Al acceder a un ***atributo*** con la ***notación de punto*** pasamos por la ***interpretación del navegador*** y este devolverá el valor asignado en un contexto.

Esto ***NO*** suele ocurrir en ***todos los atributos***, sino mayormente en los que sean ***enlaces relativos*** u otros con esta misma aplicación.

Para evitar esto existe el otro ***método***.

### Método getAttribute

Podemos acceder al ***valor*** de un ***atributo*** por medio del ***método getAttribute***.

Este ***método*** devuelve ***explicitamente*** el dato escrito dentro del ***atributo*** del ***elemento HTML***.

~~~
//Impresion de valor de href explicito
console.log(document.querySelector(".link").getAttribute("href"));
~~~

***Nota:*** el ***método getAttribute*** recibe como ***parámetro*** el nombre del ***atributo*** en formato de ***string***.

## Modificar un atributo

Similar a ***acceder a un atributo***, para ***modificar*** el valor de un ***atributo*** existen ***2 diferentes maneras***.

### Notación de punto

Para esta forma, basta con asignar un ***valor*** a la dirección del ***atributo***, tal como lo si fuese una asignación a un identificador.

~~~
//Modificacion de meta lenguaje a Ingles 
document.documentElement.lang = "en";
~~~

***Nota:*** En el ejemplo anterior no usamos una ***consulta de selector*** debido a que para acceder a el ***meta*** de ***lang*** no es necesario.

### Método setAttribute

Otra ***manera*** de poder realizar el ***cambio de valor*** a un ***atributo*** es por medio del ***método setAttribute***.

~~~
document.documentElement.setAttribute("lang", "es-MX");
~~~
Para ello, se ***identifica el elemento*** donde se encuentra el ***atributo*** y se ejecuta el ***método setAttribute***.

Este ***método*** recibe ***2 parámetros***, el primero es el ***nombre del atributo*** al que deseamos cambiar el valor, y el segundo el ***valor*** que se desea colocar.

## Agregar un atributo

También podemos ***agregar atributos*** a un ***elemento HTML***, que este no posea, para ello utilizamos el   

Tenemos el ***elemento*** en el ***HTML***:

~~~
<a href="https://www.youtube.com" class="link" data-description="Document Object Model">Enlace</a>
~~~

Y deseamos agregar un ***atributo***:

~~~
//Agregar atributo "target" con valor "_blank"
document.querySelector(".link").setAttribute("target", "_blank");
~~~

Debemos ***capturar*** el ***elemento*** al que se desea ***agregar*** el ***atributo***; Seguido ejecutar el ***método setAttribute***.

El ***setAttribute*** recibe ***2 parámetros***, el primero es del ***nombre del atributo*** y el segundo el ***valor***, ambos en formato ***string***.

## Eliminar un atributo

Así como existen los ***métodos  getAttribute*** y ***setAttribute***, tambien existe un ***método*** para poder ***eliminar atributos*** de un ***elemento***.

Este se llama ***removeAttribute***.

~~~
//Eliminacion de atributo href
document.querySelector(".link").removeAttribute("href");
~~~

Para usar este ***método*** debemos ubicar el ***elemento*** al que se desea eliminar el ***atributo***, seguido, se utiliza el ***método***.

***removeAttribute*** recibe un ***1 parámetro*** en formato ***string***, el cual es el ***nombre del atributo*** que se eliminara.

## Consultar si existe un atributo

Podemos utilizar el ***método hasAttribute*** para consultar si dentro de un ***elemento*** se encuentra un atributo.

Su sintaxis y un ejemplo:

~~~
//Impresion de resultado si existe el atributo "href"
console.log(document.querySelector(".link").hasAttribute("href"));
~~~

Similar a los anteriores, para usar este ***método*** debemos ubicarnos en el ***elemento*** donde queremos consultar su ***atributo***, esto puede hacerse con un ***querySelector*** u otro ***método similar***.

Este ***método*** recibe ***1 parámetro***, el cual es el ***nombre del atributo*** a consultar y devuelve un ***boolean***, dependiendo si se encuentra o no el ***atributo***.

## data-attributes

Podemos obtener los ***data-attributes*** de las maneras iguales a los ***atributos*** comunes, pero también de un modo especial.

Con el ***atributo especial*** llamado ***dataset***.

Tenemos el ***elemento***:

~~~
<a href="https://www.youtube.com" class="link" data-id="1" data-description="Document Object Model">Enlace</a>
~~~

Que tiene ***2 data-attributes***, gracias a ***ES6*** podemos obtenerlos de la siguiente manera:

~~~
//Impresion de Map de data-attributes
console.log(document.querySelector(".link").dataset);
~~~

Este devuelve un ***map*** con los ***nombres*** y sus ***valores***.

***Nota:*** Al ser obtenidos ***JavaScript*** elimina de su ***nombre*** la sintaxis ***"data-"***.

Desde el ***atributo dataset*** podemos utilizar la ***notación de punto*** en todas sus aplicaciones.

~~~
//Obtener un data-attribute
console.log(document.querySelector(".link").dataset.id);


//Modificar un data-attribute
document.querySelector(".link").dataset.id = "2";

//Impresion
console.log(document.querySelector(".link").dataset.id);


//Agregar un data-attribute
document.querySelector(".link").dataset.value = "Dos";

//Impresion
console.log(document.querySelector(".link").dataset.value);
~~~

***Nota:*** De esta manera no es necesario especificar la sintaxis ***"data-"***.
