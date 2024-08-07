
# 33. Modules (Import and Export).

La ***importación*** y ***exportación*** de ***módulos*** en ***JavaScript*** nos permite la separación de código y llamado dentro de otros ***archivos .js** para ser ejecutados, ya sean ***funciones*** o código ***estructural***.

	Para que un ARCHIVO .js puede importar o exportar necesita ser un módulo.

Anteriormente en el ***html*** colocábamos el enlace de nuestro ***script*** de la siguiente manera:

~~~
<script src="script.js"></script>
~~~

Si deseamos que este ***archivo*** pueda ***importar*** o ***exportar módulos***, necesitamos colocar el ***atributo type*** con valor ***module***.

Quedando de la manera:

~~~
<script src="script.js" type="module"></script>
~~~

Definiendo que es de tipo ***módulo***.


	Dentro del ordenamiento de codigo, siempre debe ir primero la importación de módulos.

## Exportación de un dato

Si deseamos ***exportar*** un ***dato*** de un archivo, este debe tener una sintaxis de inicio.

Supongamos que tenemos el archivo. ***modulo.js***, este archivo tiene una ***const*** a ***exportar***, y su sintaxis debe ser:

~~~
//Contenido de modulo
export const PI = 3.1416;
~~~

***Nota:*** Debe colocarse la ***palabra reservada export*** antes del ***identificador***.

## Importación de un dato

Ahora, para el ***archivo*** donde ***importamos*** el dato, debe tener la siguiente sintaxis:

~~~
//Archivo padre

//importacion de dato del modulo
import {PI} from "./modulo.js";

//Uso del dato
console.log(PI);
~~~

Usamos la ***palabra reservada import*** dentro de ***{}*** el nombre de ***dato importado***, la ***palabra reservada from*** y dentro de ***""*** la ***ruta*** del ***archivo*** donde esta la ***exportación***.   

***Nota:*** Tomemos como ejemplo, que ***modulo.js*** se encuentra en la misma ***jerarquia*** que nuestro ***archivo padre***, por lo que en estos caso es ***NECESARIO SIEMPRE COLOCAR ./***.

## Exportación de varios datos

Si deseamos exportar varios ***datos*** podemos hacer un pequeño cambio a nuestro modulo ***modulo.js***.

De la siguiente manera:

~~~
//Contenido de modulo
export const PI = 3.1416;

export let usuario = "usuario"
export let contrasena = "12345"
~~~

Esta manera permite ***enviar datos*** que únicamente necesitemos, sin la necesidad de ***exportar*** todo el ***archivo***.

## Importación de varios datos

Y para ***importalos***, basta con añadirlos dentro de los ***datos a importar*** en la declaración del ***archivo padre***.

~~~
//Archivo padre

//importacion de datos del modulo
import {PI, usuario, contrasena} from "./modulo.js";

//Uso de los datos
console.log(PI);
console.log(usuario);
console.log(contrasena);
~~~

De esta manera, podemos ***obtener*** los datos que necesitemos y definirlos en nuestro ***archivo padre***.

## Exportación de funciones

La ***exportación*** de ***funciones*** se aplica de la misma manera que los ***identificadores***, para ello utilizamos la palabra ***export*** antes de la declaración de la ***función***.

Un ejemplo, tenemos dentro del archivo ***modulo.js*** 2 ***funciones*** a ***exportar***:

~~~
//Funcion sumar exportada
export function sumar (a, b) {
	return a + b;
}

//Funcion restar exportada
export function restar (a, b) {
	return a - b;
}
~~~

Colocamos ***export*** en ambas ***funciones***, esto hará que  podamos utilizarlas al exportarlas en otro archivo.

## Importación de funciones

Para ***importar*** hacemos los mismo que los ***identificadores***, tomando en cuenta como ejemplo las ***2 funciones anteriores***, importamos de la siguiente manera:

~~~
//Importacion de funciones sumar y restar
import { sumar , restar } from "./modulo.js";

//Uso de funciones
console.log(sumar(1, 2));
console.log(restar(1, 2));
~~~

Para poder ser ***utilizadas***.

	Para la IMPORTACION se utiliza la DESESTRUCTURACIÓN.

## Exportación por default

Podemos elegir un ***dato*** (sea un ***valor*** o ***función***) para ser ***exportado*** como predeterminado en un archivo.

Para ello. simplemente hacemos uso de una ***palabra reservada***, llamada ***default***. colocando después de ***export***.

Pongamos el siguiente ejemplo, dentro de un archivo ***modulo.js***:

~~~
//Funcion sumar exportada
export function sumar (a, b) {
	return a + b;
} 

//Funcion restar exportada
export function restar (a, b) {
	return a - b;
}

//Funcion saludar exportada por default 
export default function saludar () {
	console.log("Hola, export default");
}
~~~

***Nota:*** Solo podemos ***exportar un dato default*** por modulo como máximo.

Esto es muy útil en ***librerías*** como ***Rect***, que se basan en componentes que solo tienen ***una función*** por ***modulo***.

***Nota:*** Esta forma solo aplica en ***funciones declaradas*** o ***clases***, no en ***expresiones*** (***identificadores*** o ***funciones expresadas***).

## Importación por default

Al ***importar*** un dato enviado por ***default***, no necesitamos ***desestructurarlo***, por lo que nos facilita la escritura de sintaxis.

Tomando como ejemplo las ***3 funciones anteriores***, supongamos que solo queremos utilizar ***saludar***, escribiríamos:

~~~
//Importacion de funcion saludar exportada como default
import saludar from "./modulo.js";

//Uso de la importacion default
saludar();
~~~

***Nota:*** No necesitamos los ***{}***.

Pero si necesitamos utilizar también las ***otras funciones***, escribiríamos la sintaxis:

~~~
//Importacion de funciones saludar, sumar y restar
import saludar, {sumar, restar} from "./modulo.js";

//Uso de importaciones desestructuradas
console.log(sumar(1, 2));
console.log(restar(1, 2));

//Uso de la importacion default
saludar();
~~~

La ***importación*** por ***default*** no se coloca dentro de la ***desestructuración***.

## Exportación por default con declaraciones

Si deseamos ***exportar*** por defecto una ***declaración***, la ***exportamos*** aparte.

Un ejemplo en una variable:

~~~
//Declaracion de identificador
const IPv4 = "192.168.200.1";

//Exportacion por default de identificador
export default IPv4;
~~~

***Nota:*** Lo mismo aplica, para ***funciones expresadas***.

## Importación por default con declaraciones

Para la  ***importación*** de este tipo de ***declaraciones*** no cambia.

Tomando como ejemplo el anterior código, que existe dentro de ***modulo.js***:

~~~
//Importacion de declaracion default
import IPv4 from "./modulo.js";

//Uso de declaracion default
console.log(IPv4);
~~~

Sin ***necesidad*** de la ***desestructuración***.

## Colocar alias a importaciones

Podemos ***nombrar*** a nuestras ***importaciones***, es decir, colocar ***alias*** para ser utilizados con ese ***nombre*** en el ***archivo*** donde fueron ***importados***.

Para ello en la ***importación*** colocamos ***as***.

Ejemplo:

~~~
//Importacion de funciones con alias
import saludo, {restar as resta} from "./modulo.js";

//Uso de alias de exportacion comun
console.log(resta(1, 2));

//Uso de alias de exportacion default
saludo();
~~~

Por si deseamos ***cambiar nombres*** a gusto.

En nuestra ***exportación*** el nombre de la ***export default*** es ***saludar***, pero hacemos directamente el ***alias***.

Para los ***export default*** se hace directamente el ***alias***.

Para los ***exports*** de ***desestructuración***, es necesario el ***as***.


	Los modulos son muy utiles, y pueden ser utilizados para ordenar codigo de diferentes fines

	- Importar funciones para obtener datos.
	- Importar clases o funciones constructoras para crear objetos.
	- Importar otros moudulos de alguna libreria.

