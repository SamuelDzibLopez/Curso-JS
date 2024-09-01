# 47. Promises.

Cuando tenemos una cola de ***callbacks*** que es muy difícil de controlar. podemos usar el mecanismo de ***JavaScript*** llamado ***promesa***.

La sintaxis de una ***promesa*** es:

~~~
//funcion
function cuadradoPromise (value) {

	//Validacion para return negativo
	if (typeof value !== "number") {
		//Return negativo de promesa
		return Promise.reject(`Error, el valor ${value} no es un numero`);
	}

	//Creacion de promesa
	return new Promise((resolve, reject) => {
		//contenido de la promesa

		//setTimeout con temporizador de 0-10 segundos
		setTimeout(()=> {

			//Ejecucion de asincronia

			//Return positivo (si se cumple)
			resolve(
				//Objeto a return
				{
					value,
					result: value * value
				}
			);
		}, 0 || Math.random()*1000);
	});
}
~~~

Una ***promesa*** puede devolver un ***return*** ***positivo*** o ***negativo***.

Y para obtener los datos de la ***promesa***:

~~~
//Llamado a funcion con promesa
cuadradoPromise(0)

//Obtencion de return positivo
.then(obj => {
	console.log(obj);
})

//Obtencion de return negativo
.catch(err => {
	console.error(err);
});
~~~

***reject*** es el ***método*** para obtener el ***return negativo***, obtenido con el ***catch***.

***resolve*** es el ***método*** para obtener el ***return positivo***, obtenido con el ***then***.

Las ***promesas*** son útiles cuando necesitamos despejar una ***concatenación*** de codigo ***asincrono***.

De este modo podemos generar concatenaciones de ***asincronia*** de una forma mas ***lejible***

~~~
//funcion
function cuadradoPromise (value) {

	if (typeof value !== "number") {
		return Promise.reject(`Error, el valor ${value} no es un numero`);
	}

	//Creacion de promesa
	return new Promise((resolve, reject) => {
		//contenido de la promesa

		//setTimeout con temporizador de 0-10 segundos
		setTimeout(()=> {

			//Ejecucion de asincronia

			//Return positivo (si se cumple)
			resolve(
				//Objeto a return
				{
					value,
					result: value * value
				}
			);
		}, 0 || Math.random()*1000);
	});
}
~~~

Podemos tener una concatenación de ***promesas***, las cuales tienen la ***misma gerarquia*** en el código.

~~~
//Creacion de promesa 1
cuadradoPromise(0)

//Obtencion de return positivo
.then(obj => {
	console.log(`Inicio promise ${obj.value+1}`);
	console.log(obj);
	console.log(`Promise: ${obj.value}, ${obj.result}`);
	//Creacion de promesa 2
	return new cuadradoPromise(1)
})

//Obtencion de return positivo de promesa 2
.then(obj => {
	console.log(`Inicio promise ${obj.value+1}`);
	console.log(obj);
	console.log(`Promise: ${obj.value}, ${obj.result}`);
	//Creacion de promesa 3
	return new cuadradoPromise(2)
})

//Obtencion de return positivo de promesa 3
.then(obj => {
	console.log(`Inicio promise ${obj.value+1}`);
	console.log(obj);
	console.log(`Promise: ${obj.value}, ${obj.result}`);
	//Creacion de promesa 4
	return new cuadradoPromise(3)
})

//Obtencion de return positivo de promesa 4
.then(obj => {
	console.log(`Inicio promise ${obj.value+1}`);
	console.log(obj);
	console.log(`Promise: ${obj.value}, ${obj.result}`);
	console.log(`Fin promises`);
})

//Obtencion de return negativo de cualquier promesa
.catch(err => {
	console.error(err);
});
~~~

El ***método .catch*** obtiene los ***reject*** de todas las ***promesas*** por lo que solo necesitamos un solo ***catch***.

