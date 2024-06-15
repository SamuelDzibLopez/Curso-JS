
# 3. Variables.

Las variables son espacios de memoria que nos permiten almacenar información o datos.

## Declaración de variables

Para poder declarar una variable en **JavaScript**, usamos la palabra reservada: **var**.

~~~
var hola = "Hola mundo"
~~~

## Ámbito de variables

El **ámbito de variable** es el tamaño de bloque donde se conoce la existencia de la variable.

Anteriormente, JavaScript solo tenia **ámbito global** para sus variables (var), lo que ocasionaba confusiones y errores al momento de codificar.

### var

Usamos **var** como una variable global dentro de todo nuestro contenido.

Antes de la actualización a ES6 JS se programaba solo programación estructural, lo que implicaba que JS detectaba todas las variables, elevando a nivel superior su creación global dentro de todo el documento.

Esto presenta dificultades y problemas para al POO, lo que impulso la creación de un nuevo tipo de variable.

La creación de una **var** es mediante la sintaxis:

~~~
var variableGlobal = "Variable global"
~~~

### let

Una de las nuevas funciones que ES6 nos trajo en su implementación a la web en 2015 fue la creación del nuevo tipo de variable de declaración por bloques

**Let,** a diferencia de **var,** solamente respeta su existencia dentro de un contenedor, al cual se le denomina, bloque, de alli la programación en bloques.

Para hacer la creación de una variable **let,** utilizamos la sintaxis similar a la **var.**

~~~
let variableDeBloque = "Variable de bloque"
~~~

## Elemento window

Podemos usar el elemento **window** que nos permite ver las propiedades y elementos de la ventana global dentro de la página.

Si declaramos una variable global (**var**), podremos buscarla como propiedad dentro del window, mientras que las **let** no serán reconocidas.

~~~
var Hola = "Hola mundo"; //varaible global
let Hello = "Hello world"; //variable de bloque

console.log(window); //impresion del elemento window

console.log(window.Hola); //impresión de Hola
console.log(window.Hello); //Hello no se conoce en el elemento window (undefined)
~~~