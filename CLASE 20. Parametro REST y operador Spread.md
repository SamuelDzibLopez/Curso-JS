
# REST and Spread

## Parametro REST

~~~
//Parametro REST (...)

function sumar (a, b, ...c) {
	let resultado = a + b;

	c.forEach(function (n) {
		resultado += n;
	});
	
	return resultado;
}

console.log(sumar(1, 2));
console.log(sumar(1, 2, 3));
console.log(sumar(1, 2, 3, 4));

//Permite recibir una cantidad de parametros variable de una función 
~~~

