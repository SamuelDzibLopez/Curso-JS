
# 9.  Undefined, null y NaN.

Además de los tipos de datos ya abordados con anterioridad en el documento, existen otros tipos de datos.

## Undefined

~~~
//Undefined

let indefinido; //Un dato undefined

console.log(indefinido); //Resultado: undefined
~~~

Podemos decir que un dato **undefined** es el valor definido por el sistema si no definimos nosotros el valor (muy diferente a null).

**_Nota:_** En otras palabras, un valor **undefined** es el valor que significa que no se sabe el valor dentro del identificador.

## Null

Otro valor que existe es el valor null.

~~~
let nulo = null; //Un dato null

console.log(nulo); //null
~~~

A diferencia de un valor **undefined**, un valor **null** es cuando definimos que un identificador carece de un valor.

**_Nota:_** Podemos decir que **null** es la definición por el programador a una variable como careciente de valor alguno.

## NaN

La definición **NaN (Not at Number)** se encuentra cuando intentamos realizar cualquier acción con un dato que no sea un **number.**

El sistema detecta este tipo de error y nos lanza un resultado de tipo **NaN.**

~~~
let noEsUnNumero = "hola" * 3.5; //multiplicar un string

console.log(noEsUnNumero); //NaN
~~~