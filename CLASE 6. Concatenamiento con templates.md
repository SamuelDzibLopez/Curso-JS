
# 6. templates.

Existe una forma más sencilla, practica y beneficiosa para poder concatenar texto.

Gracias a los **templates** podemos almacenar texto en un identificador con múltiples espacios y saltos de línea, siendo visualmente más fácil.

También nos permite eliminar los símbolos de + y los espacios en el concatenamiento.

~~~
let nombre = "Roberto"; //variable de nombre
let apellido = "Lopez"; //variable de apellido

let saludo = `Hola mi nombre es ${nombre} ${apellido}`; //concatenamiento de valor con templates

console.log(saludo); //impresion de valor de saludo
~~~

## Concatenamiento con +=

También podemos concatenar texto con el símbolo +=, de la siguiente manera:
~~~
let ejemplo = "hola"; //Declaracion de ejemplo
console.log(ejemplo); //Impresion de valor actual de ejemplo 

ejemplo += " mundo"; //concatenamiento de nuevo valor al valor anterior 
console.log(ejemplo); //Impresion de valor actual de ejemplo 
~~~

## método ***toUpperCase*** 

La función **toUpperCase** nos permite poder convertir una cadena de texto a letras mayúsculas, lo único que necesitamos para poder utilizarla es la cadena string o el identificador que contiene dicho valor:

~~~
console.log(cadena.toUpperCase()); //conversion de contenido string a mayusculas
~~~

## método ***toLowerCase***

Existe la función inversa del **toUpperCas,** la cual nos permite convertir un texto en mayúsculas a caracteres en minúsculas: **toLowerCase**.

Para utilizarla, podemos escribir la sintaxis:

~~~
console.log(cadena.toLowerCase()); //conversion de contenido string a minusculas
~~~

## método ***includes*** 

Podemos hacer uso de esta función si necesitamos saber si una cadena de texto contiene dentro de si una subcadena la cual nos interesa:

Para ello escribimos la función de la manera siguiente:

~~~
console.log(texto.includes("mundo")) 
/*Esta funcion nos devolvera un boolean.
(true o faolse)
Dependiendo si dentro de la cadena de texto se logra encontrar una subcadena que coincida con la declaracion*/
~~~

Para poder escribir la sintaxis necesitamos escribir la cadena que deseamos observar y la subcadena que queremos observar ira dentro de paréntesis, declarada como un parámetro.

La función nos devuelve un valor **boolean,** dependiendo del resultado obtenido.

## método ***split***

También tenemos una función declarada a los strings, con la función **split** podemos obtener de una cadena de texto un **array**, donde dentro de los espacios, se almacenan cadenas de texto del **string.**

~~~
let texto_2 = "Roberto Luis Lopez"; //variable de ejemplo

console.log(texto_2.split(" ")); //desestructurar texto_2 a elementos de array
~~~

***Nota:*** Para poder dividir cada sección del array a las cadenas, es necesario un carácter común entre las divisiones que deseamos hacer.

Aquí existe otro ejemplo.

~~~
let texto_3 = "Roberto, Luis, Lopez, Perez, 6SA, Ingenieria de software"; //variable de ejemplo

console.log(texto_2.split(", ")); //desestructurar texto_3 a elementos de array
~~~

## método [ ]

La función [ ], es útil para poder obtener un dato de la cadena de texto que deseamos.

~~~
let cadenaDeTexto = "Hola";

console.log(cadenaDeTexto[0]); //H
console.log(cadenaDeTexto[1]); //o
console.log(cadenaDeTexto[2]); //l
console.log(cadenaDeTexto[3]); //a
console.log(cadenaDeTexto[4]); //undefined
~~~

Solo basta colocar el nombre del identificador y el numero de la posición del carácter que deseamos dentro de unos [ ].

**_Nota:_** Para ordenar la posición, JavaScript comienza el conteo desde el numero 0, lo que significa que, si queremos obtener un dato según su número de posición, debemos hacer una resta de -1.

## método ***indexOf***

Gracias a la función **indexOf** podemos obtener el inicio de la posición de una subcadena de texto dentro de un **string.**

El valor que nos devuelve empieza tomando en cuenta la regla del inicio de posición desde 0.

La función **indexOf** es usado de la siguiente manera:

~~~
console.log(cadenaDeTexto.indexOf("ola")); //Respuesta : 1

/*con indexOf podemos encontrar en que posicion empieza una subcadena de texto*/
~~~

## método ***slice***

La función **slice** ayuda a obtener un parámetro de caracteres de una cadena de texto.

~~~
console.log(cadenaDeTexto.slice(0, 4)); //Respuesta: Hola

//Obtencion de los datos de cada posicion 

//En el ejemplo es del 0 hasta el 3 (en el 4 se detiene)
~~~

Definimos dos parámetros dentro de la función, el inicio (la posición donde inicia el recorrido) y el final (la posición donde termina).

**_Nota:_** Si deseamos obtener los primeros 4 caracteres de un string, empezaremos desde la posición 0 (el primero) y como final colocaremos el (4), la posición 4 no se obtendrá dentro del resultado de la función; sino que, será el parámetro que indique cuando se acaba la obtención de los caracteres.

### método ***slice*** con un parametro

Cuando definimos únicamente un solo parámetro en la función, se imprimirá toda la cadena de texto, empezando desde la posición declarada por el valor de único parámetro.

~~~
console.log(cadenaDeTexto.slice(0)); //Respuesta: Hola

//Se detiene hasta terminar el string
~~~

## método ***replace***

También podemos hacer cambios a nuestra cadena de texto con una función declarada, sin la necesidad de volver a declarar el valor completo del identificador.

~~~
let ejemplo_1 = "mozilla"; //Creacion de la variable

console.log(ejemplo_1.replace("moz", "van")); //Impresion del valor con cambio (sin guardar)

ejemplo_1 = ejemplo_1.replace("moz", "van"); //Cambio de valor en la variable

console.log(ejemplo_1); //impresion de la variable (con cambio guardado)
~~~

***Nota:*** Hay que tomar en cuenta que esta función no cambia el valor del identificador al que hacemos el cambio, sino solamente ejecuta la acción momentánea de cambiar la subcadena. Si deseamos guardar el nuevo valor remplazado, debemos hacer la operación.