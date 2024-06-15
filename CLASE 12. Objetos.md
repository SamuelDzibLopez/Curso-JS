
# 12. Objects.

Los objetos son otro tipo de dato un poco similar a los arrays, pero con notables diferencias.

La regla de los identificadores **const** se aplica de igual forma a los objetos, como lo es a los arrays, permitiendo cambiar los datos de sus elementos creados, ingresar nuevos o eliminarlos en un futuro.

Para poder definir un objeto se hace de la siguiente forma:

~~~
const objeto = {

}

//un objeto puede ser un const vacio y ser definido mas adelante
~~~

**_Nota:_** Los elementos dentro de los objetos se definen dentro de { }, a diferencia de los arrays, que son con [ ].

Los elementos dentro de un **objeto** se definen con 2 tipos de datos llamados **atributo** y **valor.**

~~~
const alumno = {
	nombre: "Roberto",
	edad: 21,
	sexo: "hombre",
	//Array
	pasatiempos: ["jugar", "estudiar", "escribir"],
	soltero: true,
	//Objeto
	constacto: {
		email: "correo@gmail.com",
		whatsapp: 9999999999,
		faceboock: "Roberto Fabian"
    },
	//Funcion
	saludar: function () {
		console.log("Hola soy la funcion de saludar del objeto");
	}
}

//Un objeto puede tener varios tipos de datos dentro, incluso otro objeto o funcion
~~~

A diferencia de los **arrays,** los elementos de los **objetos** vienen representados por un nombre y un valor, gracias a esto, podemos obtener una mejor descripción de los elementos de este, cosa que los arrays no tenían, solo nos daban valores sin contexto.

Los elementos de un objeto pueden ser variados aun dentro de el mismo, tal como en la imagen anterior, donde se encuentran tanto identificadores declarados como **strings, numbers, arrays, boolens,** otros **objetos,** incluso **funciones.**

Si queremos obtener el objeto la sintaxis es simple:

~~~
console.log(alumno);
//impresion de objeto alumno
~~~

## Acceder a un valor de un atributo de un objeto

También podemos obtener el valor de un único atributo (elemento) del **objeto**; Con los **arrays** teníamos que acceder por medio de la posición del valor que queríamos, pues con los **objetos** únicamente necesitamos el nombre del atributo para obtener su valor; Esto es muy útil y practico al momento de querer acceder al valor que almacena un objeto, aun si no conocemos a detalle el objeto con el que trabajamos.

~~~
console.log(alumno["nombre"]);
//Acceder al valor del atributo nombre del objeto alumno
~~~

Para ello bastara con definir el atributo, cuyo valor deseamos, colocado entre “ ” y   [ ], algo parecido a los arrays, pero en vez de la posición, declaramos el atributo.

Otra opción más sencilla es con la **notación de punto:**

~~~
console.log(alumno.edad);
//Notacion de punto, no necesitamos los "" y []
~~~

Ahorramos tiempo.
## Acceder a un array dentro de un objeto

Dentro de los **objetos** también pueden almacenarse arrays, para acceder a un elemento de este, es muy sencillo.

~~~
console.log(alumno.pasatiempos[1]);
//Acceder a un elemento de un array de un objeto
~~~

Siempre seguimos la misma lógica de las posiciones

## Acceder a un objeto dentro de un objeto

Al igual que el ejemplo anterior, podemos acceder a objetos anidados y a sus atributos.

La sintaxis codificada es:

~~~
console.log(alumno.contacto.email);
//Acceder a un atributo de un objeto de un objeto
~~~

## Invocar una función expresada en un objeto

Como JavaScript es un lenguaje de bajo nivel tipado, nos permite declarar el atributo de un objeto como una función; Si deseamos invocar una función similar, lo haríamos de la siguiente manera, siguiendo las reglas de **funciones** explicadas en este documento anteriormente.

~~~
//Invocacion de la funcion/metodo declarada en un objeto
alumno.saludar();
//Ejecutamos la funcion (metodo si es un dato de un objeto) que esta dentro del objeto
~~~

**_Nota:_** Recordemos que esta es una **función expresada**, lo que significa que solo puede ser invocada después de ser expresada, también hay que tomar en cuenta que si el objeto esta declarado con un identificador **let** el objeto solo será declarado en un bloque de código.

## Elemento ***this***

El elemento **this** es usado para obtener el elemento padre de un elemento

~~~
objeto_2 = {
	nombre: "Samuel",
	apellido: "Dzib",
	edad: 21,
	saludar_2: function () {
		console.log(`Hola ${this.nombre} ${this.apellido}, tienes ${this.edad} años`);
    }
    //Elemento this para obtener el elemento padre
}

//Llamado a la funcion
objeto_2.saludar_2();
~~~

Este elemento nos ayuda a poder declarar u obtener el elemento padre de un atributo o elemento

This funciona como **_alias_** del elemento padre.

## Función ***Object.key***

Si tenemos un objeto que queremos saber los nombres de los atributos que este tiene definidos, la función **object.keys** es útil para ello.

La función nos listara por orden definido los nombres de los atributos del objeto, todos estos en forma de **array.**

~~~
console.log(Object.keys(alumno));
//Listado de nombres de los atributos en un objeto, entregando un array
~~~

**_Nota:_** Recuerda que esta función, solo devuelve los nombres de los atributos, no sus valores.

## Función ***Object.values***

Ahora, si queremos obtener no los nombres de los atributos de un objeto, sino sus valores, la función **Object.values** es la útil.

Esta función nos devuelve un arrays con todos los valores de los atributos por orden declarado.

~~~
console.log(Object.values(alumno));
//Listado de valores de los atributos en un objeto, entregando un array
~~~

**_Nota:_** Los elementos del arrays solo devolverán los valores de los atributos, sin nombre, **_muy útil si queremos convertir un objeto a un array, de forma fácil._**

## método ***hasOwnProperty***

Si tenemos dudas si algun atributo existe dentro de un objeto, podemos usar la función **hosOwnProperty.**

~~~
console.log(alumno.hasOwnProperty("nombre")); //true
console.log(alumno.hasOwnProperty("fecha")); //false
~~~

El resultado de esta función nos devolverá un valor **boolean,** dependiendo del resultado de la función.

