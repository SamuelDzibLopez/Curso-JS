# 67. DOM: DOM Tour.

***JavaScript*** permite poder ***obtener elementos*** del ***DOM*** mediante el ***posicionamiento*** y ***relación*** de estos, tomando como referencia un ***elemento*** como base.

Gracias a esta manera y a los ***atributos reservados***, podemos obtener otros ***elementos***, tales como ***elementos padre***, ***hijos***, ***hermanos*** y ***antecedentes***.

Para ejemplos de esta lección tomaremos el siguiente código ***HTML***:

~~~
<h1>Curso JS</h1>
<ul id="lista">
	<li id="1">1</li>
	<li id="2">2</li>
	<li id="3">3</li>
	<li id="4">4</li>
	<li id="5">5</li>
</ul>
<p>parrafo</p>
~~~

Tenemos ***3 elementos HTML***, entre los que se encuentran un ***ul*** con un ***id***, usado para poder obtener los otros ***elementos*** desde este.

Obtendremos el ***elemento*** desde ***JS***, para ser usado como ***identificador***:

~~~
//Obtencion de elemento con id "lista" en identificador $elementist 
const $elementList = document.getElementById("lista");

//Impresion de $elementist
console.log($elementList);
~~~

## Contenido de Nodo.

Es importante conocer que las ***listas*** de ***nodos*** contienen ***2 diferentes*** elementos:

Los cuales son:

	- Texto
	- Elementos

Los ***textos*** en su mayoría no son mas que las ***identaciones*** y ***espaciados*** del ***codigo HTML*** entre ***elementos*** interpretados por ***JS***, ocupando un ***nodo*** entre la ***lista de nodo.

Por su parte, los ***elementos*** son las ***etiquetas HTML*** reales que contiene dentro la captura del ***nodo***.

Existen ***varios atributos*** explicados en las siguientes ***acciones***, los cuales permiten obtener, tanto todo el ***contenido*** de un ***nodo***, como únicamente los ***elementos*** que se encuentran dentro de este.

## Obtener hijos de un Elemento

Para ***obtener*** los ***elementos hijos*** de un ***elemento capturado*** podemos usar la sintaxis ***child***.

### Atributo childNodes

El ***atributo childNodes*** devolverá una ***colección*** de todos los ***nodos hijos*** del ***elemento***, sin importar si son ***text*** o ***element***.

~~~
//Impresion de coleccion de todos los nodos, tanto texto como elementos
console.log($elementList.childNodes);
~~~

	El contenido dependera de la identacion del codigo HTML.
### Atributo childNodes

Para obtener una ***colección*** de ***UNICAMENTE*** los ***elementos hijos***, utilizamos el ***atributo children***.

~~~
//Impresion de coleccion de elementos HTML hijos
console.log($elementList.children);
~~~

	Este atributo, solo devolvera los elementos hijos, sin nodos text.
### Obtener hijo en especifico

Podemos utilizar la ***notación de []*** para ***obtener*** un ***hijo*** en ***especifico***.

~~~
//Impresion de 3er elemento de la coleccion de elementos nodos
console.log($elementList.children[2]);
~~~

	Esto funciona tanto en childNodes, como en children.

### Obtener primer nodo hijo

Podemos ***obtener*** el ***primer nodo hijo*** de un ***elemento***.

Para podemos utilizar ***2 atributos***:

~~~
//Primer nodo (text o element)
console.log($elementList.firstChild);

//Primer elemento nodo
console.log($elementList.firstElementChild);
~~~

***Nota:*** El ***atributo firstChild*** obtiene el ***primer nodo hijo*** tomando en cuenta los ***nodos*** de tipo ***texto***, mientras que ***firstElementChild*** devolvera el ***primer elemento nodo hijo***, sin contar los ***nodos text***.

### Obtener ultimo nodo hijo

También podemos ***obtener*** el ***ultimo nodo hijo*** de un ***elemento***.

Similar, tenemos ***2 atributos***:

~~~
//ultimo nodo (text o element)
console.log($elementList.lastChild);

//Ultimo elemento nodo
console.log($elementList.lastElementChild);
~~~

***Nota:*** Estos funcionan siguiendo las mismas reglas que ***firstChild*** y ***firstElementChild***, pero tomando el ***ultimo nodo***.

## Obtener elemento padre de un Elemento

No solo podemos obtener los ***elementos*** que a su vez, se encuentran dentro de un ***elemento***, sino que también, podemos obtener su ***elemento padre directo***.

Es decir, la ***etiqueta*** que encierra a este.

Para ello se utiliza el ***atributo parentElement***:

~~~
//Impresion de elemento Padre del elemento
console.log($elementList.parentElement);
~~~

	Esto devolvera el Elemento padre.

## Obtener hermano de un Elemento

También ***JavaScript*** permite obtener los ***nodos directos*** que se encuentren en la misma jerarquía que un ***elemento capturado***.

Estos ***atributos*** solo permiten obtener los ***hermanos vecinos***.
### Obtener hermano anterior

Para ***obtener*** el ***nodo hermano anterior*** (tanto si es un ***texto*** como un ***elemento***), tenemos ***2 atributos***:

	- previousSibling
	- previousElementSibling

***previousSibling*** permite obtener el ***nodo hermano anterior*** tomando en cuenta tanto ***nodos*** de tipo ***texto***, como ***elementos***.

***previousElementSibling*** devolverá el ***ultimo nodo hermano anterior*** contando ÚNICAMENTE los ***nodos*** de tipo ***elementos***.

Su sintaxis de ejemplo:

~~~
//Nodo Previo
console.log($elementList.previousSibling);

//Nodo elemento previo
console.log($elementList.previousElementSibling);
~~~

### Obtener hermano siguiente

Para obtener el ***nodo hermano siguiente*** también existen ***2 atributos***:

	- nextSibling
	- nextElementSibling

~~~
//Nodo siguiente
console.log($elementList.nextSibling);

//Nodo elemento siguiente
console.log($elementList.nextElementSibling);
~~~

***Nota:*** ***nextSibling*** devuelve el ***primer nodo hermano siguiente*** tomando en cuenta tanto ***nodos*** de tipo ***texto***, como ***elementos***, mientras ***nextElementSibling*** solo tomará en cuenta los ***nodos*** de tipo ***elemento***.

## Método closest

El ***método closest*** permite obtener un ***nodo padre indirecto*** de un ***elemento*** especificando el tipo.

Por ejemplo:

~~~
//Impresion de elemento superpadre de $elementList que sea de tipo body
console.log($elementList.closest("body"));
~~~

Este ***método*** permite obtener ***elementos padre*** que tienen una jerarquía de aun mas arriba.