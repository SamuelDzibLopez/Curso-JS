
# 28. Math Object.

***Math*** es un ***objeto*** que nos permite poder realizar ***múltiples*** operaciones y generarlos resultados de estas, contiene múltiples ***métodos matemáticas*** y ***atributos*** valores a utilizar.

Podemos ver imprimiendo en pantalla el ***objeto***:

~~~
console.log(Math);
~~~

Dentro de sus ***atributos*** y ***valores*** esta el famoso ***PI***:

~~~
console.log(Math.PI);
~~~

***Nota:*** Los ***atributos*** que ***Math*** nos brinda están escritos en ***mayúsculas***, debido a que son consideradas ***constantes*** matemáticas.

Algunos ***métodos*** más importantes de ***Math*** son:

## abs

Este ***método*** permite obtener el ***valor absoluto*** de un numero pasándolo como ***parámetro***.

Un ejemplo:

~~~
console.log(Math.abs(5.3));
console.log(Math.abs(-5.3));

//Valor absoluto: 5.3
~~~

Este ***método*** permite ***strings***, siempre y cuando, el valor de este pueda ser considerado ***numero***.

~~~
console.log(Math.abs("-5.3"));
~~~

De lo contrario...

~~~
console.log(Math.abs("numero"));
~~~

También se permiten ***operaciones***, este devolverá el ***valor absoluto*** del ***resultado***.

~~~
console.log(Math.abs(4-5));
console.log(Math.abs(4-3));

//Valor absoluto: 1
~~~

***Nota:*** Podemos pasar un ***identificador*** como parámetro.
## ceil

Este ***método*** permite ***redondear*** hacia ***arriba*** un numero con decimal.

Un ejemplo:

~~~
//Decimal en un identificador
let decimal = 3.2;

//Metodo ceil
console.log(Math.ceil(decimal));
~~~

Tambien permite operaciones:

~~~
//Decimal en un identificador
let decimal = 3.2;

//Metodo ceil
console.log(Math.ceil(decimal - 1));
~~~


***Nota:*** Siempre redondeara al ***numero proximo mayor***.

## floor

Este es el ***método*** es lo contrario al ***ceil***, este redondeara hacia ***abajo*** el numero.

~~~
//Decimal en un identificador
let decimal = 3.2;

//Metodo floor
console.log(Math.floor(decimal));
~~~

También permite ***operaciones***:

~~~
//Decimal en un identificador
let decimal = 3.2;

//Metodo floor
console.log(Math.floor(decimal - 1));
~~~

## round

Redondea de forma ***automática*** el número, dependiendo el ***numero entero mas cercano***, dependiendo de sus decimales:

	.0 --> Anterior
	.1 --> Anterior
	.2 --> Anterior
	.3 --> Anterior
	.4 --> Anterior
	.5 --> Siguiente
	.6 --> Siguiente
	.7 --> Siguiente
	.8 --> Siguiente
	.9 --> Siguiente

Un ejemplo:

~~~
//Metodo round

//Abajo
console.log(Math.round(3.4));

//Arriba
console.log(Math.round(6.5));
~~~

***Nota:*** A partir del ***.5***, el numero ***redondea*** hacia ***arriba***.

Este método, es idéntico al ***ceil*** y ***floor***, por lo que permite ***operaciones***.

~~~
console.log(Math.round(6.5 - .1));
~~~


## sqrt

También podemos sacar la ***raiz cuadrada*** de un numero.

Con el ***método sqrt***:

~~~
console.log(Math.sqrt(81));

//Raiz cuadrada: 9
~~~

***Nota:*** Podemos enviar ***operaciones*** e ***identificadores***.

## pow

Este ***método*** permite obtener una ***n potencia*** de un ***número***.

La sintaxis es la siguiente:

~~~
//Metodo pow
console.log(Math.pow(2, 4));
~~~

***pow*** recibe ***2 parámetros.

	Primer parametro  -->  Numero a potenciar.
	Segundo parametro -->  Potencia

## random

Este ***método*** devuelve un ***numero aleatorio*** entre ***0-1.

Su sintaxis en un ejemplo:

~~~
console.log(Math.random());
~~~

Supongamos que queremos un numero del ***0-1000***, basta con multiplicar.

~~~
console.log(Math.random() * 1000);
~~~

