# 2. Características y Gramática.

	JavaScript es el único lenguaje de programación que permite el ISOMORFISMO.

### Características:

Es un lenguaje:

	- De Alto nivel.
	- Interpretado y Dinámico.
	- Débilmente tipado.
	- Multiparadigma.
	- Sensible a MAYUSCULAS y minúsculas.
	- No necesita los puntos y comas al final de cada línea.

### Escritura de código

Los **Identificadores** deben comenzar con:

	- Una letra
	- Un signo de dólar $
	- Un guion bajo __
	- Nunca con números o caracteres especiales.

#### Uso de ***snake_case***

- archivos:

~~~
mi_archivo_javascript.js
~~~

#### Uso de ***UPPER_CASE***

- Constantes:

~~~
const UNA_CONSTANTE = "Soy una constante"

PI = 3.14.15.92653589793
~~~

#### Uso de ***UpperCamelCase***

- Clases:

~~~
class SerHumano {
	constructor {nombre, genero} {
		this.nombre = nombre
		this.genero = genero 
	}

	miNombreEs () {
		return `Mi nombre es ${this.nombre}`
	}
}
~~~

#### Uso de ***lowerCamelCase***

- Objetos:

~~~
const unObjeto = {
	nombre: "Luis"
	email: "Luis@gmail.com"
}
~~~

- Primitivos:

~~~
let unaCadena = "Hola mundo",
let	unNumero = 19,
let	unBoolean = true 
~~~

- Funciones:

~~~
function holaMundo (nombre) {
	alert (`Hola mundo ${nombre}`)
}

holaMundo ("Jonathan")
~~~

- Instancias:

~~~
const ajax = new XMLHttpRequest(),
json = new SerHumano("Jonathan", "Hombre")
~~~

### Palabras reservadas

~~~
1. abstract
2. boolean, break, byte
3. case, catch, char, class, const, continue
4. debugger, default, delete, do, double
5. else, enum, export, extends
6. false, final, finally, float, for, function
7. goto
8. if, implements, import, in, instanceof, int, interfacde
9. long
10. native, new, null
11. package, private, protected, public
12. return
13. short, static, super, switch, synchronized
14. this, thrwos, transient, true, try, typeof
15. var, volatile, void
16. while, with 
~~~

### Ordenamiento de código

	1. IMPORTACION DE MODULOS.
	2. DECLARACIÓN DE VARIABLES.
	3. DECLARACIÓN DE FUNCIONES.
	4. EJECUCION DE CÓDIGO.

### Tipos de datos en JavaScript

1. Datos **primitivos:** se accede directamente al valor.
	1. string
	2. number
	3. boolean
	4. null
	5. undefined
	6. NaN

2. Datos **Compuestos:** se accede a la referencia del valor
	1. Objet = {}
	2. array = []
	3. function = () {}
	4. class {}
	5. etc