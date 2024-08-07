# 55. Proxies.

son un ***nuevo mecanismo*** que permite la creación de un ***objeto*** basándonos de un objeto literal inicial.

El ***proxie*** recibe un objeto literal y generara una copia.

Los ***proxies*** permiten validación de tipos de datos basado en el ***objeto literal obtenido***.

La sintaxis para crear un ***proxie*** es:

~~~
const proxie = new Proxy(objeto, manejador);
~~~

***Nota:*** Para crear un ***proxie***, es necesario recibir ***2 parámetros***, el ***objeto base***, al cual queremos tomar como referencia del nuevo ***objeto proxie*** a crear; Y el ***manejador***  y utilizado para poder realizar las ***validaciones*** para los ***tipos de datos*** de ***valores*** de los ***atributos***.

Ambos ***parámetros*** enviados deben cumplir con la notación ***objeto***.

Un ejemplo de ***creación*** de un ***proxie***:

Tenemos un ***objeto*** del cual deseamos generar ***proxies***:

~~~
//objeto base

	const persona = {
	nombre: "",
	apellido: "",
	edad: 0
}
~~~

Generamos el ***manejador***:

~~~
//Manejador

const manejador = {
	//Metodo para validar
	set(obj, prop, valor) {
	
	//Asignamos a cada atributo del objeto su valor
	obj[prop] = valor;

	//retornamos un true
	return true;
	}
}
~~~

Ahora tomamos el ***objeto base*** y el ***manejador*** para generar un ***proxie***:

~~~
//Declaracion de proxie como parametros el objeto case y el manejador
const diego = new Proxy(persona, manejador);

//Asignacion de valores de los atributos
diego.nombre = "Diego";
diego.apellido = "López";
diego.edad = 35;

//Impresion de objeto proxie
console.log(diego);
~~~

De esta manera, podemos generar ***objetos*** tomando como ***modelos*** otros ***objetos***, sin la necesidad de definir clases, basta con ***declarar*** un ***manejador*** para poder controlar la lógica.

---

***Nota:*** Al declarar valores de los ***atributos*** a un ***proxie*** estos valores también se asignaran al ***proxie***. debido a su ***vinculación bidireccional***.

Tomando como ejemplo el ***codigo anterior***, si imprimimos:

~~~
console.log(persona);
~~~

El ***objeto base*** tendrá los mismos ***valores*** en sus ***atributos*** que los ***proxies*** que ***creemos*** como hijos de ellos.

Lo mismo sucede cuando ***declaramos*** un ***NUEVO atributo*** a un ***proxie*** que no tenia el ***objeto base***:

~~~
//Declaracion de nuevo atributo al proxie
diego.email = "diego@gmai.com"

//Impresion de objeto base con nuevo atributo con valor igual al asignado al proxie
console.log(persona);
~~~

Generando un ***atributo*** con el mismo valor en el ***objeto base***.

---

Todo el ***código completo***:

~~~
//objeto base
const persona = {
	nombre: "",
	apellido: "",
	edad: 0
}

//objeto base vacio
console.log(persona);

//Manejador
const manejador = {

//Metodo para validar
	set(obj, prop, valor) {

		//Asignamos a cada atributo del objeto su valor
		obj[prop] = valor;

		//retornamos un true
		return true;
	}
}

//Declaracion de proxie como parametros el objeto case y el manejador
const diego = new Proxy(persona, manejador);

//Asignacion de valores de los atributos
diego.nombre = "Diego";
diego.apellido = "López";
diego.edad = 35;

//Impresion de objeto proxie
console.log(diego);

//Impresion de objeto base con valores del atributo proxie
console.log(persona);

//Declaracion de nuevo atributo al proxie
diego.email = "diego@gmai.com"

//Impresion de proxie con nuevo atributo
console.log(diego);

//Impresion de objeto base con nuevo atributo con valor igual al asignado al proxie
console.log(persona);
~~~

## Validaciones

Podemos ***validar*** los ***valores*** y los ***atributos*** al momento de ***crear un ***proxie***.

Para ello debemos utilizar el ***método set***, donde dentro de este, colocaremos el codigo:

~~~
//Manejador
const manejador = {

	//Metodo para validar
	set(obj, prop, valor) {

		//Validacion
		if (Object.keys(obj).indexOf(prop) === -1) {
			return console.error(`La propiedad "${prop}" no existe en el objeto persona`);
		}

		//Asignamos a cada atributo del objeto su valor
		obj[prop] = valor;

		//retornamos un true
		return true;
	}
}
~~~

Se ***puede validar*** cualquier ***situación***.

En ***conclusión*** un ***proxie*** es un ***tipo de dato*** similar a un objeto que es creado, utilizando como base un ***objeto común***, usando como ayuda un ***manejador***, el cual permite asignar los valores al ***objeto base*** y ***obtener una copia*** en el nuevo ***proxie***.

