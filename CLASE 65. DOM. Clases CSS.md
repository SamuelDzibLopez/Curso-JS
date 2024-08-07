# 65. DOM: CSS Class.

En ***JavaScript*** podemos acceder a las ***clases CSS*** de un ***elemento HTML***. el cual es diferente a los ***atributos CSS*** vistos en la clase anterior.

Para los ejemplos de esta clase, usaremos el siguiente ***elemento HTML*** como referencia:

~~~
<a href="https://www.youtube.com" id="enlace" class="link bold">Enlace</a>
~~~

Un ***enlace*** que tiene un ***id*** para poder ser capturado por ***JS*** y una ***clase CSS*** para las referencias.

Para obtener el ***elemento*** en ***JavaScript*** usaremos:

~~~
//Asigancion de elemento HTML con id "enalce" a identificador $enlace
const $enlace = document.getElementById("enlace");

//Impresion de identificador $enlace con elemento HTML
console.log($enlace);
~~~

## Obtener clase CSS de un Elemento HTML

Para obtener las ***clases CSS*** de un ***elemento HTML*** existen ***2 atributos*** diferentes:

	- className
	- classList

### Atributo className
 
 El uso de este ***atributo*** se utiliza para poder obtener el valor en formato ***string*** de la o las ***clases***.

Su sintaxis:

~~~
//Impresion de clases CSS de $enlace en formato string
console.log($enlace.className);
~~~

***Nota:*** Tanto si el ***elemento*** tiene una ***clase*** o más se impriman separados por un espacio.

### Atributo classList

Este ***atributo*** devuelve una ***lista*** de las ***clases CSS*** del ***elemento***, en formato parecido a un ***array***.

Su sintaxis:

~~~
//Impresion de clases CSS de $enlace en formato lista o array
console.log($enlace.classList);
~~~

***Nota:*** Este ***atributo*** se utiliza para poder realizar más acciones, tales como ***agregar***, ***remover*** y ***remplazar clases***.

## Verificar existencia de clase CSS de un elemento HTML

Podemos verificar si un ***elemento HTML*** tiene una ***clase CSS***, para ello se utiliza el ***método contains***.

Su sintaxis y ejemplo

~~~
//Impresion de verificacion de existencia de clase CSS "link" en elemento $enlace
console.log($enlace.classList.contains("link"));
//true

//Impresion de verificacion de existencia de clase CSS "enlace" en elemento $enlace
console.log($enlace.classList.contains("enlace"));
//false
~~~

Este ***método contains*** devuelve como valor un ***boolean***.

Donde ***true*** significa que la ***clase CSS*** se encontró en el ***elemento***, y ***false*** si no se encontró.

## Agregar clase CSS a un Elemento HTML

Para ***agregar*** una ***clase CSS*** a un ***elemento*** usamos el ***método add*** dentro del atributo ***classList***.

Su sintaxis:

~~~
//Agregar clase "extra" a elemento $enlace
$enlace.classList.add("extra");
~~~

Este ***método*** también permite ***agregar más*** de una ***clase***.

~~~
//Agregar clases "extra" y "border" a elemento $enlace
$enlace.classList.add("extra", "border");
~~~

Las ***clases*** son ingresadas como parámetros en formato de ***string***.

## Remover clase CSS de un Elemento HTML

También se puede ***remover*** una ***clase CSS*** en un ***elemento***, para ello, se utiliza el ***método remove***.

Un ejemplo de sintaxis:

~~~
//Eliminar clase CSS "link" de elemento $enlace
$enlace.classList.remove("link");
~~~

Al igual que ***add***, también podemos asignar varios ***parámetros*** a este ***método***.

Esto ***removerá*** las ***clases especificadas***.

~~~
//Eliminar clases CSS "link" y "border" de elemento $enlace
$enlace.classList.remove("link", "border");
~~~

## Switchear clase CSS de un Elemento HTML

Existe un ***método especial*** que permite ***activar*** y ***desactivar*** una ***clase CSS*** de un ***elemento***, dependiendo de si se encuentra o no.

El ***método toggle*** funciona como un ***interruptor***, si la ***clase CSS*** se encuentra en el ***elemento*** esta se ***remueve***, en cambio, si no se encuentra, se ***agrega***.

Su sintaxis y ejemplo es la siguiente:

~~~
//Switcheo de clase CSS "link" en elemento $enlace
$enlace.classList.toggle("link");
~~~

## Remplazar clase CSS de un Elemento HTML

También podemos ***remplazar*** una ***clase CSS*** de un ***elemento*** por ***otra***.

Para ello, se utiliza el ***método replace***.

Un ejemplo:

~~~
//Remplazar clase CSS "bold" por la clase "extra" de elemento $enlace
$enlace.classList.replace("bold", "extra");
~~~

***Nota:*** Podría decirse que el ***método replace*** realiza un ***remove*** y ***add*** en un sola acción.


