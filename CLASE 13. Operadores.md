
# 13. Operadores.

Los operadores son símbolos que permiten realizar acciones dentro de la programación, los cuales son indispensables para realizar acciones y dar resultados para futuras acciones.

	Operadores: +, -, *, /, %, ()

## Operador de suma

El operador de suma nos permite poder realizar sumas aritméticas, tal como conocemos en la vida común

Para ellos usamos el símbolo de +;

~~~
let suma = 5 + 5; //Operador de suma
//Resultado: 10
~~~

**_Nota:_** Estas operaciones solo funcionan en tipos de datos **numbers,** para **strings** estos se vuelven concatenaciones, ya explicadas antes en este documento.

## Operador de resta

Asi como tenemos el operador de suma, el operador de resta, cuya función es contraria a la función de adición.

~~~
let suma = 5 - 5; //Operador de resta
//Resultado: 0
~~~

## Operador de multiplicación

El operador multiplicativo permite realizar sumas idénticas cierta cantidad de veces, tal como conocemos.

A diferencia de la aritmética común, en la programación el operador de multiplicación se realiza con ******* en lugar de **x**.

~~~
let suma = 5 ** 5; //Operador de multiplicacion
//Resultado: 25
~~~

## Operador de división/modulo

Tal cual lo conocemos, nos permite obtener el resultado de poder hacer divisiones con **numbers,** este operador puede devolvernos decimales.

~~~
let suma = 5 / 2; //Operador de division
//Resultado: 2.5
~~~

## Operador de cociente

Este operador permite obtener el residuo de una división con resultados enteros

Es decir, dar un resultado de dividir con números enteros y devolver el resto.

~~~
console.log(5 % 2); //Operador de cociente
//Resultado: 1
~~~

## Operador de orden aritmético

Tal como en la aritmética común, existe el orden y privilegio de operaciones, para priorizar y fragmentar las operaciones, utilizamos los ().

~~~
let num_1 = (5- 10) * 3; //Operacion con orden aritmetico

let num_2 = 5- 10 * 3; //Operacion sin orden aritmetico
~~~

## Operadores relacionales

Los operadores relacionales permiten comparar datos, por lo que este tipo de operadores nos devolverán un tipo de dato **boolean.** Es decir, **true** o **false.**

	Operadores: **>, <, >=, <=, ==, ===, !=, !==**

### Operador de asignación

El símbolo = es usado con suma repetición en la programación; Como ya vimos JavaScript nos permite asignar un valor a un identificador con el símbolo =, únicamente codificando un signo.

~~~
let asignacion = "Asignacion"; // = es usado para asignar un valor a los identificadores
~~~

### Operador de comparación

El operador de comparación == sirve para poder comparar los valores de dos identificadores.

Este operador, solo toma en cuenta el valor bruto de los identificadores como tal, (más adelante entenderás mejor).

~~~
console.log("7" == 7); //true
console.log("5" == 4); //false

// El == solo compara valores brutos de los identificadores
~~~

El operador == no toma en cuenta si los valores son de diferente tipo de dato, únicamente compara el valor.

### Operador de comparacion completa

A diferencia del operador 
	==
El operador 
	=== 
también compara el tipo de dato entre los dos datos a comparar, para poder devolver un **true,** el valor de los identificadores deberá ser no solo el mismo, sino del mismo valor también.

Cualquier otra excepción dará como resultado **false.**

~~~
console.log("7" === 7); //false
console.log(4 === 4); //true

// El === compara valor y tipo de los identificadores
~~~

**_Nota:_** Podemos usar los **valores que tienden a true o false,** comparando ambos para obtener un resultado.

### Operador ***mayor que***

Podemos hacer operaciones para poder identificar resultados **booleans** si las condiciones son correctas.

Dependiendo del sentido de la operación será **true** o **false.**

~~~
console.log(9 > 8); //true
//9 es mayor a 8

console.log(8 > 9); //false
//8 no es mayor a 9

console.log(9 > 9); //false
//9 no es mayor a 9
~~~

**_Nota:_** Ten en cuenta, que el valor del resultado solo será **true,** si el primer dato es mayor al segundo, si es inverso o son idénticos el resultado será **false.**

### Operador ***menor que***

El operador de **menor que (<)**, es inverso al **mayor que (>)**, si realizamos una operación cuyo primer dato sea menor que el segundo, el resultado será **true.**

~~~
console.log(9 < 8); //false
//9 no es menor a 8

console.log(8 < 9); //true
//8 es menor a 9

console.log(9 < 9); //false
//9 no es menor a 9
~~~

**_Nota:_** Si los datos son iguales, el resultado será **false.**

### Operador ***mayor o igual que***

El operador de **mayor o igual que (>=)** tiene la misma función que el operador **mayor que (>)**, con la excepción de contar como **true** cuando el valor de ambos es igual.

~~~
console.log(9 >= 8); //true
//9 es mayor o igual a 8

console.log(8 >= 9); //false
//8 no es mayor o igual a 9

console.log(9 >= 9); //true
//9 es mayor o igual a 9
~~~

### Operador ***menor o igual que***

Funciona de manera similar al **menor que** contando como **true** cuando los datos son iguales.

~~~
console.log(9 <= 8); //false
//9 no es menor o igual a 8

console.log(8 <= 9); //true
//8 es menor o igual a 9

console.log(9 <= 9); //true
//9 es menor o igual a 9
~~~

### Operador ***no es igual que***

El operador de **no es igual que (!=)** es el operador inverso del **es igual que 
	==
El cual solo compara valores, sin tipos de datos.

~~~
console.log(4 != "5"); //true
//4 es no igual a "5"
  
console.log("65" != 65); //false
//"65" no es no igual a 65
~~~

**_Nota:_** Usar este operador puede causar problemas si no se entiende.

Si los datos son iguales (sin importar el tipo) será **false.**

Si los datos son diferentes (sin importar el tipo) será **true.**

### Operador ***no es igual que completo***

Este ultimo operador es igual al operador de **comparación completa 
	===
Invirtiendo el resultado.

A diferencia del **operador no es igual simple (!=),** este si compara también el tipo de dato.

~~~
console.log(4 !== "5"); //true
//4 es no igual a "5" en valor no en tipo
  
console.log("65" !== 65); //true
//"65" de diferente en tipo a 65, pero es igual en valor

console.log(10 !== 10); //false
//10 es igual a 10, en valor y tipo
~~~

**_Nota:_** En términos simples, este operador devolverá **true** cuando el valor o el tipo de dato sea diferente al otro.

Sera **false** solo, y solo si los valores son idénticos de forma completa.

## Operadores incrementales

Los **operadores incrementales** permiten, como su nombre indica, poder incrementar el valor de un identificador **number,** con un parámetro según desee.

	Estos operadores son: ++, +=, --, -=, *=, /=.

### Operador incremental positivo

Si queremos incrementar el valor de un identificador de tipo number, lo lógico seria hacer la siguiente operación.

~~~
let incremento = 1; //Declaracion de identificador y valor
incremento = incremento + 1; //Incremento el valor en 1
~~~

Sin embargo, una manera más fácil y corta, seria con el operador ++.

~~~
let incremento = 1; //Declaracion de identificador y valor
incremento++; //Incremento del valor en 1
//Resultado: 2
~~~

El valor del incremento se almacena en el identificador sin necesidad de codificarlo expresamente.

### Operador incremental positivo mayor a 1

Si queremos incrementar nuestro valor a un número que sea mayor que 1 (incrementar en 2, 3, 4, …), podemos cambiar la sintaxis un poco:

~~~
let incremento = 1; //Declaracion de identificador y valor
incremento += 2; //Incremento del valor en 2 (hacemos una suma de 2)
//Resultado: 3
~~~

### Operador incremental negativo

Si deseamos incrementar el valor number de manera negativa (decrementar), podemos hacer uso del operador --,

~~~
let decremento = 1; //Declaracion de identificador y valor
decremento--; //Decremento del valor en 1
//Resultado: 0
~~~

De esta forma ahorramos codificación, como fue el caso del incremento positivo.

### Operador incremental negativo mayor a 1

De igual forma, si queremos decrementar el valor de nuestro identificador en un número que sea mayor que 1 (2, 3, 4, …), podemos usar el operador:

~~~
let decremento = 1; //Declaracion de identificador y valor
decremento -= 2; //Decremento del valor en 2 (hacemos una resta de 2)
//Resultado: -1
~~~

Funciona de manera idéntica al operador positivo, diferenciando que decrementa el valor, en lugar de incrementarlo.

### Operador incremental multiplicativo

Si deseamos incrementar el valor de nuestro identificador multiplicándolo, el operador incremental multiplicativo sirve de mucha ayuda.

~~~
let dato = 1; //Declaracion de identificador y valor
dato *= 2; //Multiplicamos el valor por 2
//Resultado: 2
~~~

En este operador, necesitamos declarar el dato del multiplicador.

### Operador incremental divisivo

También podemos incrementar el valor de un identificador dividiéndolo.

~~~
let dato = 4; //Declaracion de identificador y valor
dato /= 2; //Division del valor por 2
//Resultado: 2
~~~

Para la multiplicación y división, deben declararse los parámetros.

## Operadores lógicos

Los operadores lógicos nos permiten obtener un resultado **boolean** cuando realizan una comparación o múltiples comparaciones de valores.

	Existen diferentes tipos de operadores lógicos: !, ||, &&.

### Operador lógico de negación

El **operador de negación (!)**, permite poder negar el resultado **boolean** de un identificador, un ejemplo simple es el siguiente:

~~~
console.log(true); //True
console.log(!true); //False

console.log(false); //False
console.log(!false); //True
~~~

### Operador lógico OR

El operador lógico OR (||) permite hacer comparaciones anidadas y devolver un **boolean**, si por lo menos alguna de las condiciones es **true,** el resultado general será true.

Si ninguna de las comparaciones es **true,** el resultado será **false.**

~~~
console.log(("9" === 9) || (9 === 9)); // true

// Si se cumple 
~~~

### Operador lógico AND

Igual al operador OR (||), el operador lógico AND (&&) también nos devuelve un **boolean,** pero para devolver un valor **true,** todas las operaciones deberán dar como resultado individual **true,** de modo que si solo algún resultado es **false**, el resultado final también será **false.**

~~~
console.log("(9" === 9) && (9 === 9)); // false

console.log((9 === 9) && (6 === 6)); // true

// Para que el resultado sea true las operaciones deben ser true
~~~

