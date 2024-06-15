
# 7. Numbers.

En múltiples lenguajes de programación los números se dividen en diferentes tipos (int, float, double, etc), pero **JavaScript** nos permite poder declarar un identificador tipo número independientemente del tipo o futuro tipo de dato que este almacené al principio.

Para poder declarar un tipo de dato **number,** basta hacerlo de la siguiente manera:

~~~
let numero_1 = 2.1; //manera 1

let numero_2 = new Number(1); //manera 2
~~~

## método ***toFixed***

La función **toFixed** permite poder redondear el valor de un tipo de dato **number** a un determinado número de decimales.

~~~
let numero_3 = 7.19; //Declaracion de identificador y valor

console.log(numero_3.toFixed(1)); //Redondeo a 1 decimal

console.log(numero_3.toFixed(6)); //Redondeo a 6 decimales
~~~

Solo necesitamos definir la cantidad de decimales a redondear, tanto a menos, como a más.

## Atributo typeof

Si por casualidad, necesitamos saber el tipo de dato de identificador, podemos obtenerla por medio del atributo **typeof.**

Solo necesitamos escribir la siguiente sintaxis:

~~~
let a = 7.19; //number
let b = "5.6"; //string
let c = true; //boolean

console.log(typeof a); //tipo number
console.log(typeof b); //tipo string
console.log(typeof c); //tipo boolean
~~~

## método ***parseint***

Existe un pequeño detalle, cuando deseamos sumar un dato **string** a un **number** lo único que lograremos es la concatenación de estos dos datos.

~~~
let dato_1 = 1;
let dato_2 = "2.2";

console.log(dato_1 + dato_2); //Concatenamiento (12.2)
~~~

Para este tipo de ocasiones, la función **parseInt** nos permite convertir el dato **string** en un dato **number.**

La siguiente sintaxis muestra el ejemplo:

~~~
console.log(dato_1 + parseInt(dato_2)); //Respuesta 3
~~~

**_Nota:_** La función **parseInt** solo convierte el dato entero del identificador, ignorando los decimales existentes.

## método ***parseFloat***

Si lo que necesitamos es convertir un **string** a un **number** sin ignorar sus decimales (lo que sucede con **parseInt**), podemos usar **parseFloat.**

~~~
console.log(dato_1 + parseFloat(dato_2)); //Respuesta 3.2
~~~

En esta función el numero **string** se convierte por completo sin ignorar ninguna parte.