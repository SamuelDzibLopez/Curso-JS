
# 5. Strings.

JavaScript, al igual que la gran mayoría de lenguajes de programación, nos permite guardar dentro de variables y constantes diferentes tipos de datos, los **strings** son uno de esos tipos de datos, los cuales nos permiten almacenar cadenas de texto.

Los **strings** permiten el almacenamiento de palabras en forma de texto, aun si guardamos números, si utilizamos la sintaxis, será una cadena de texto.

La sintaxis para un **string** es la siguiente:

~~~
let cadena = "Hola";
~~~

De esta manera almacenamos texto para utilizar en nuestro futuro código.

Si deseamos almacenar **strings** dentro de variables o constantes, debemos usar comillas, para que el lenguaje entienda que es texto almacenado.

## Atributo ***length***

Gracias a la propiedad (atributo de objeto) de los objetos de tipo **string** llamada **lenght (largo)**, podremos saber el tamaño de un texto almacenado dentro de un identificador tipo cadena de texto.

Para ello podemos escribir la sintaxis siguiente:

~~~
cadena.length
~~~

Podemos declarar una nueva variable con este atributo, o imprimirlo en consola

~~~
let lengthCadena = cadena.length; //Declaracion de la variable el valor del length de cadena (4)

console.log(cadena.length); //Impresion del length de cadena (4)
~~~

## Concatenamiento de cadenas de texto

También podemos unir/concatenar dos o más cadenas de texto, tanto para imprimir como para almacenar dentro de un nuevo identificador.

~~~
let concatenamiento = cadena + texto; //concatenamiento tiene el valor de cadena  y texto junto 
~~~

De esta manera, la variable **concatenamiento** tendrá el valor **string** almacenado de cadena unida a texto.

***Nota:*** Si eres principiante en el ámbito, debes tomar en cuenta que al concatenar no existen espacios no deseados, si deseamos debemos colocarlas nosotros mismos.