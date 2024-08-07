
# 26. Console Object.

***Console*** es un ***objeto*** que nos permite ***interactuar*** con la consola del ***interprete***, en caso de la web, la ***consola*** de nuestro ***browser***.

***Console*** también tiene sus propios ***métodos***:

## log

Uno de esos ***métodos*** más usados es el :

~~~
console.log();
~~~

Que no es más que un ***método*** el cual nos permite ***imprimir*** en consola, obteniendo un parámetro.

Funciona tanto en la impresión de ***texto*** y ***tipos de datos*** directos:

~~~
//Int
console.log(1);

//Float
console.log(2.3);

//String
console.log("Hola");

//Booleans
console.log(true);

//Objects
console.log({
	name: "Samuel",
	edad: 20
});

//Arrays
console.log([1, 2, 3, 4]);

//Null
console.log(null);

//Undefined
console.log(undefined);

//Operaciones
console.log(3 - 2 % 1);
~~~

Como con ***identificadores***, tengan el valor que tengan:

~~~
//Creacion de identificador
let variable = "1";

//Impresion
console.log(variable);
~~~

***Nota***: No olvidemos la ***concatenación*** y los ***templates***.

Existen otros ***métodos***, a continuación:

## error

Similar al ***log***; El ***método error*** imprime en ***consola*** un ***mensaje de error***.

Similar, es ***invocado*** de la siguiente manera, y recibe ***parámetros***.

~~~
console.error("Esto es un error");
~~~

Puede recibir incluso valor de ***identificadores***.

~~~
//Creacion de identificador
let variable = "Error";

//Impresion de error
console.error(variable);
~~~

## warn

***warn*** viene de la simplificación de la palabra ***warning*** o ***advertencia***. y permite imprimir una ***advertencia***, similar a ***error***.

Al igual, acepta ***tipos de datos*** directos e ***identificadores***.

Un ***ejemplo***:

~~~
//Impresion de warning con string directo 
console.warn("Esto es una Advertencia");

//Creacion de identificador
let variable = "Warning";

//Impresion de warning con identificador
console.warn(variable);
~~~

## clear

Este ***método*** permite limpiar la ***consola***.

~~~
console.clear();
~~~

Este ***método*** no recibe ***parámetros***, pero se invoca como un ***método*** común.

## dir

Este ***método*** permite la ***vista*** e ***impresión*** de elementos, dantoles un formato de ***objeto***.

Por ejemplo:

~~~
//Impresion de variable
console.log(document);
  
//Impresion como objeto
console.dir(document);
~~~

## group y groupCollapsed

Estos ***métodos*** imprimen grupos de ***impresiones***.

Como si fuese un ***acordión***, el ***group*** representa un ***grupo abierto***, mientras ***groupCollapsed*** representa un ***grupo cerrado***, pero en ***ocasiones*** esta diferencia depende del ***navegador***.

A continuación, un ejemplo de comparación de ***ambos***:

~~~
//Group
console.group("Tecnologias web")
console.log("HTML");
console.log("CSS");
console.log("JS");
console.groupEnd();

//GroupCollapsed
console.groupCollapsed("Tecnologias web")
console.log("HTML");
console.log("CSS");
console.log("JS");
console.groupEnd();
~~~

El ***grupo*** se ***cierra*** con el ***método groupEnd***.

## table

Este ***método*** permite la ***impresión*** de información en formato de ***tabla***.

Para ello, basta con enviar el ***parámetro***. Un ejemplo:

~~~
//Creacion de array
let array = [1, 2, 3, 4, 5];

//Tabla
console.table(array);
~~~

Funciona con diferentes ***tipos*** de ***datos***:

~~~
//Creacion de objeto
let objeto = {
	name: "Nombre",
	apellido: "Apellido",
	edad: "Edad"
}

//Tabla
console.table(objeto);
~~~

***Nota:*** Podemos agregar una ***columna*** de ***indices***, para ello, agregamos el método ***entries*** de ***objet***.

~~~
console.table(Object.entries(objeto));
~~~

Si queremos ***ordenar*** por ***alfabeto***. el ***método sort***.

~~~
console.table(Object.entries(objeto).sort());
~~~

## time y timeEnd

El ***método time*** se utiliza para poder capturar el ***cronometro*** de realización de un ***segmento*** de ***código***.

En su mayoría, es usado para la ***optimización*** y ***testeo*** cuando se trata de ***peticiones***.

Su ***sintaxis***:

~~~
//Inicio de cronometro time
console.time("tiempo");

//Creacion de arreglo
const arreglo = new Array (100);

//For con ingreso a valores
for (let i = 0; i < arreglo.length; i++) {
arreglo[i] = i;
}

//Finalizacion de cronometro time
console.timeEnd("tiempo");

//impresion de arreglo
console.log(arreglo);
~~~

***Nota:*** Los mensajes de los ***time*** deben ser los mismos, ya que funcionan como una especie de ***etiquetas***, para poder ***identificar*** el ***inicio*** y ***final*** del ***método.

## count

Permite ***guardar*** el numero de ***veces*** que se realiza un ***codigo***.

Para ello, utilizamos la sintaxis siguente:

~~~
console.count();
~~~

Dentro de un código, seria:

~~~
for (let i = 0; i <= 20; i++) {
	console.count("count");
	console.log(i);
}
~~~

***Nota:*** Al igual que el ***método time***, este ***método*** también recibe ***un parámetro*** que actúa como ***etiqueta*** o ***bandera***, pero su diferencia, es que no necesita la declaración de un final.

## assert

Este ***método*** se utiliza para poder evaluar ***condicionales*** y ***detectar errores*** de reglas en nuestro código.

Se utiliza por medio de ***booleans***, donde si la condición es ***true***, continua el código, pero si es false, muestra un ***error***.

Un ejemplo:

~~~
//Identificadores y datos

let x = 1;
let y = 2;
let mensaje = "X debe ser menor a Y";

//assert
console.assert(x < y, {x, y, mensaje});
~~~

el ***assert*** recibe como ***primer parámetro*** la condición que debe ser ***true***, seguido de un ***objeto*** con los ***identificadores*** y el ***mensaje*** que desea mostrar.

El ***orden de los datos*** dentro del ***objeto*** no afectan, siempre que se encuentren declarados, de manera y nombre correcto.