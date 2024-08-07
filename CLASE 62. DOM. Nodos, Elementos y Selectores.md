# 62. DOM: Nodes, Elements and Selectors.

	https://developer.mozilla.org/es/docs/Web/API/Node

Los ***Nodos*** son ***clases abstractas*** por las que se logra ***dividir*** por ***diferentes grupos*** los elementos HTML de un documento, y poder obtenerlos.

Algunos ***nodos*** pueden ser:

	- Etiquetas
	- Clases
	- Nombres
	- Ids

Para poder acceder a estos ***nodos*** y sus ***elementos*** existen diferentes sintaxis, dependiendo de cada uno:

## Obtener elementos por etiqueta

Podemos obtener una ***colección HTML*** de todos los ***elementos existentes*** un tipo de ***etiqueta*** de un documento.
 
Para ello usamos el ***método getElementsByTagName*** de ***document.

~~~
//Impresion de Coleccion por tipo de etiqueta
console.log(document.getElementsByTagName("nombre de etiqueta"));
~~~

Esta ***función*** recibe como ***parámetro*** un ***nombre de etiqueta HTML*** en forma de ***string***.

Un ejemplo de su uso:

~~~
//Impresion de Coleccion de etiquetas li HTML en el documento
console.log(document.getElementsByTagName("li"));
~~~

## Obtener elementos por clase CSS

Existe otra sintaxis para poder obtener una ***colección HTML***, pero en esta ocasion, por ***clase designada***.

Para ello usamos el ***metodo getElementsByClassName***.

~~~
//Impresion de Coleccion por clase CSS
console.log(document.getElementsByClassName("nombre de clase"));
~~~

Al igual que ***getElementsByTagName***, este recibe como ***parámetro*** el nombre de la ***clase CSS*** en formato de ***string***.

Un ejemplo de uso de este ***método***:

~~~
//Impresion de Coleccion de elementos con clase CSS lista en el documento
console.log(document.getElementsByClassName("lista"));
~~~

***Nota:*** En este ***método*** no se especifica el ***.*** como selector de clase, sino únicamente el ***nombre de la clase***.

## Obtener elementos por name

Gracias al ***método getElementsByName*** podemos obtener una ***lista de nodo***, donde dentro de ella, se encontraran los ***elementos HTML (etiquetas)*** que cumplan con la condición de tener como atributo ***name*** el valor designado.

La sintaxis es la siguiente:

~~~
//Impresion de Nodo de elementos por name
console.log(document.getElementsByName("name"));
~~~

Un ejemplo de su uso:

~~~
//Impresion de Nodo de elementos HTML con name de valor "Dos"
console.log(document.getElementsByName("Dos"));
~~~

## Obtener elemento por id

Podemos obtener un ***elemento HTML*** por medio del ***método getElementById***.

Su sintaxis:

~~~
//Impresion de Elemento por id
console.log(document.getElementById("nombre de id"));
~~~

Este ***método*** devuelve un ***solo elemento***, debido a que solo debe existir un ***elemento*** con el mismo ***id*** por documento, debido a esto, no devuelve una ***colección HTML*** ni una ***lista de nodo***, sino un ***elemento*** directamente.

Un ejemplo:

~~~
//Impresion de Elemento con id de valor "boton"
console.log(document.getElementById("boton"));
~~~

## consultas por selector

Existe un ***método*** el cual permite poder obtener un ***elemento*** con  un ***selector*** especificandolo.

Este es ***querySelector***.

~~~
//Impresion de Elemento con regla
console.log(document.querySelector("selector y nombre"));
~~~

Los ***querySelector*** permiten poder obtener un ***elemento*** con selector de ***etiqueta***, ***clase***, ***name*** y ***id***.

Aquí los ejemplos de uso:

~~~
//Id
console.log(document.querySelector("#boton"));

//Clase
console.log(document.querySelector(".lista"));

//Name
console.log(document.querySelector('[name="Dos"]'));

//Clase
console.log(document.querySelector("li"));
~~~


	Query selector, devuelve el primer elemento de una seleccion especificada (etiqueta, nombre, clase, id).

***Nota:*** El ***querySelector*** devolverá el ***primer elemento encontrado*** que cumpla con las ***reglas*** del ***selector***, si deseamos ***devolver TODOS***, usamos el siguiente método:

El ***método querySelectorAll***.

Este devuelve una ***lista de nodo*** con todos los ***elementos*** que cumplan con la regla.

Su sintaxis es:

~~~
//Impresion de lista de nodo que cumpla la regla
console.log(document.querySelectorAll("selector y nombre"));
~~~

Un ejemplo de uso:

~~~
//Impresion de lista de nodos de elementos que cumplan con la regla de ser etiquetas "li"
console.log(document.querySelectorAll("li"));
~~~

	Query selector All, devuelve todos los elementos de una seleccion especificada (etiqueta, nombre, clase, id).

***Nota:*** todas las ***reglas*** de ***querySelector*** son aplicables para ***querySelectorAll***.

## Length en consultas por selector

Las ***listas de nodo*** tienen la ***propiedad length***, que podemos consultar.

Un ejemplo:

~~~
//Impresion de tamaño de lista de nodo de consulta por selector
console.log(document.querySelectorAll("li").length);
~~~

## Recorrer elementos de consultas por selector

Para poder ***recorrer*** una ***lista de nodo*** se utiliza el ***método  forEach***:

~~~
//Impresion de recorrido de elememtos de lista de nodo con ForEach
document.querySelectorAll("li").forEach((el) => console.log(el));
~~~

Podemos acceder a un ***elemento*** de una ***lista de nodo*** con su ***posición*** y con la notación de ***[]***.

Un ejemplo:

~~~
//Impresion de elemento en la posicion 3 de una lista de nodo
console.log(document.querySelectorAll("li")[3]);
~~~