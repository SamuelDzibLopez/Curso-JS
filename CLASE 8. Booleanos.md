
# 8. Booleans.

Los tipos de datos **booleans** son los identificadores que guardan en su interior datos que se identifican como **verdadero** o **falso.**

Para ello la declaración es de la siguiente manera.

~~~
let verdadero = true; //Verdadero
let falso = false; //Falso

console.log(verdadero, false);
~~~

## Tipos de datos que "tienden a ***true*** o ***false***"

Algunos datos pueden ser considerados por JS como **true** o **false,** dependiendo del valor.

Algunos de estos son los siguientes:

~~~
//Algunos valores que tienden a false o true

//true
console.log(Boolean(1)); //Un numero positivo
console.log(Boolean(-4)); //Un numero negativo
console.log(Boolean("Hola")); //Un string

//false
console.log(Boolean(0)); //Un numero 0
console.log(Boolean("")); //Cadena vacia
console.log(Boolean('')); //Cadena vacia

//otros false: null, undefined y NaN
~~~

Gracias a esto podemos hacer comparaciones de tipo booleans entre diferentes tipos de datos.
