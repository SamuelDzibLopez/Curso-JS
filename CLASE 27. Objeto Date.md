
# 27. Date Object.

El ***objeto Date*** nos permite ***obtener*** y crear ***valores*** de tipo ***fechas.

Se puede visualizar:

~~~
console.log(Date);
~~~

Podemos obtener los ***datos*** de la ***fecha***, basta con:

~~~
console.log(Date());
~~~

***Nota:*** Podemos ver la ***captura*** recargando la ***pagina***, ya que siempre nos mostrara la fecha de captura del ***método***.

Para obtener un ***date*** basta con almacenar el contenido en un ***identificador***.

Como el siguiente ejemplo: 

~~~
//Captura de fecha acutal en un identificador
let fecha = new Date();

//impresion
console.log(fecha);
~~~

Dentro de este ***identificador*** podremos almacenar una fecha ***exacta*** y utilizarla en cualquier momento.

Si deseamos obtener el dato en ***formato string***, podemos utilizar el ***método toString***.

~~~
console.log(fecha.toString());
~~~

También para otro formato, que sea ***string***.

~~~
console.log(fecha.toLocaleString());
~~~

O...

~~~
//Solo fecha y horas
console.log(fecha.toDateString());

//Otro formato de fechas y horas
console.log(fecha.toLocaleDateString());
~~~

***Nota:*** Estos últimos ***métodos Date*** solo devolverá el ***día,  mes, ***fecha*** y ***año***.

También podemos obtener de ***date*** los datos ***individuales***.

### Obtener datos específicos

Podemos ***obtener*** datos de una ***fecha*** de manera ***separada***, para ello, ***JavaScript*** maneja diferentes ***métodos***, donde obtenerlos.

Los ***datos*** que podemos obtener, van desde ***año, mes, día del mes, día de la semana, hora, minutos, segundos, milisegundos*** hasta un único numero ***general*** para identificar en formato de ***navegadores***.

A continuación, los ***métodos***:

Supongamos que tenemos el ***date*** almacenado en un ***identificador*** siguiente:

~~~
//Captura de fecha acutal en un identificador
let fecha = new Date();
~~~

Con base a este ***identificador***, usaremos los ***métodos***:

### obtener año

~~~
//Impresion de año
console.log(fecha.getFullYear());
~~~

Este ***método*** nos devuelve un ***numero***, que sera el ***año de la fecha***.

### obtener mes

~~~
//Impresion de mes
console.log(fecha.getMonth());
~~~

Este ***método*** devuelve el ***mes*** en formato de ***numero*** de ***array***, es decir, donde:

	0 --> Enero
	1 --> Febrero
	2 --> Marzo
	3 --> Abrir
	4 --> Mayo
	5 --> Junio
	6 --> Julio
	7 --> Agosto
	8 --> Septiembre
	9 --> Octubre
	10 --> Noviembre
	11 --> Diciembre

El primer mes ***enero*** es contado con el ***0***, y el ultimo, ***diciembre*** es ***11***.

### obtener fecha de día

~~~
//Impresion de fecha de dia
console.log(fecha.getDate());
~~~

Este ***método*** devuelve la ***fecha del día del mes***, en formato de ***numero***.

***Nota:*** Este número es preciso, a diferencia del ***més***, donde el primer dato es 0.

### obtener día de la semana

~~~
//Impresion de dia de la semana
console.log(fecha.getDay());
~~~

Este ***método*** devuelve el dato en formato ***númerico***, donde:

	0 --> Domingo
	1 --> Lunes
	2 --> Martes
	3 --> Miercoles
	4 --> Jueves
	5 -->Viernes
	6 --> Sabado

El ***primer día*** es ***domingo***, con dato ***0***, mientras el ultimo día es ***sábado*** con dato ***6***.

### obtener hora

~~~
//Impresion de hora
console.log(fecha.getHours());
~~~

El ***formato*** de este ***método*** devuelve la ***hora*** en un formato de ***número*** de ***24 hrs***.

Si deseamos el formato en ***string***, podemos usar el ***método***:


~~~
//Impresion de hora en string
console.log(fecha.toLocaleTimeString());
~~~

Este ***formato*** devuelve en ***string*** la ***hora: minuto:segundo***.

### obtener minutos

~~~
//Impresion de minutos
console.log(fecha.getMinutes());
~~~

Este ***método*** devolverá los ***minutos*** en formato de ***números***.

### obtener segundos

Similar al ***método*** para obtener ***minutos***, este devuelve de la misma manera los ***segundos***, en un formato de ***numeros***.

~~~
//Impresion de segundos
console.log(fecha.getSeconds());
~~~

### obtener milisegundos

~~~
//Impresion de milisegundos
console.log(fecha.getMilliseconds());
~~~

Igual a los últimos dos métodos, este ***método*** devolverá los ***milisegundos*** de la fecha en formato ***números***.

## obtener fecha timestamp

Este ***método*** permite obtener el ***formato*** exacto de la marca de ***tiempo***.

Dentro de un ***date*** almacenado, lo podemos obtener de la siguiente manera:

~~~
//Impresion  de marca de tiempo timestamp
console.log(fecha.getTime());
~~~

Y desde el ***objeto date***:

~~~
//Impresion  de marca de tiempo timestamp
console.log(Date.now());
~~~

Este contador inicia desde ***1 de enero de 1970***.

	Libreria util: moment.js

## Obtener datos de una fecha NO ACTUAL

Para poder obtener los ***datos*** mostrados anteriormente, de una ***fecha*** que no sea la del ***navegador*** del momento exacto atrás, es muy simple.

Basta con ***enviar la fecha*** en los ***parámetros*** de la creación de un nuevo ***Date***.

Como en el siguiente ***ejemplo:***

~~~
//Captura de fecha en un identificador
let cumpleaños = new Date(2002, 10, 21);

//Impresion de fecha
console.log(cumpleaños);

//Impresion de timestamp
console.log(cumpleaños.getTime());
~~~

***Nota:*** En el anterior, ejemplo, se pasaron únicamente de ***parámetros*** el ***año***, ***mes***, y ***fecha de mes***, (En respectivo orden), los cuales son los más indispensables.

También podemos ser mas específicos, colocando ***hora***, ***minuto*** y ***segundos***, incluso ***milisegundos***.

Como el siguiente ejemplo:

~~~
let cumpleaños = new Date(2002, 10, 21, 23, 59, 59, 0);
~~~

Siguiendo el ***orden de jerarquía***.