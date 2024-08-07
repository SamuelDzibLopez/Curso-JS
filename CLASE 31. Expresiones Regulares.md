
# 31. Regular expressions.

Las ***expresiones regulares*** son una ***secuencia*** de ***símbolos*** delimitados por una ***regla*** en especifica.

Esta ***regla*** da las ordenes de ***continuidad***, ***aceptación*** o ***rechazo*** de los ***caracteres*** de una palabra, determinando si esta cumple con la ***expresión regular*** o no.

Gracias a estas ***expresiones*** podemos facilitarnos mucho las ***validaciones***.

Para mas detalle de esta ***clase***:

	https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Regular_expressions#crear_una_expresi%C3%B3n_regular

## Crear expresión regular

Para ***crear*** una ***expresión regular*** podemos hacer uso de su constructor propio:

~~~
let expresion = new RegExp ("lorem", "");
~~~

O directamente como un valor de  ***identificador***.

~~~
let exp = /lorem/;
~~~

***Nota:*** La ***expresión regular*** debe encontrarse dentro de ***//***.

También, existen las ***banderas***, que son las ***reglas*** que debe seguir el contenido de la ***expresión regular***.

***Nota:*** 

## Utilizar expresión regular

Para poder ***utlizar*** una ***expresion regular*** en una ***cadena de texto*** o ***identificador*** utilizamos el ***método test*** o el ***exec***, cada uno, tiene diferente función.

### test

El ***método test*** devuelve un ***boolean***, resultado de la revisión de la cadena de texto ***recibida*** como ***parámetro***.

Un ejemplo de sintaxis:

~~~
//Declaracion de cadenas de texto
let lorem = "lorema";
let cadena = "cadena";

//Prueba de metodo test
console.log(expresion.test(cadena));//false
console.log(expresion.test(lorem));//true
~~~

***Nota:*** Dependiendo de las ***reglas*** de la ***expresión regular***, se devolverá ***true*** o ***false***.

### exec

Este ***método*** nos brinda más información sobre la ***respuesta*** encontrada en ***cadena de texto***.

Su sintaxis es:

~~~
//Declaracion de cadenas de texto
let lorem = "lorema";
let cadena = "cadena";

//Prueba de metodo ecex
console.log(expresion.exec(cadena));//null
console.log(expresion.exec(lorem));//objet
~~~

Este ***método*** devuelve un ***objeto*** con más información de la ***subcadena encontrada***.

***Nota:*** Si no se encuentra la cadena devolverá ***null***.