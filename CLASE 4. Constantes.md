
# 4. Const.

JavaScript nos permite crear también constantes declaradas, a diferencia de las variables, (**var y let**) estas no pueden ser cambiadas de valor (para los valores primitivos) y tipo de dato,

Otra diferencia para las const, es que al momento de su creación, se necesita asignar un valor definido, algo que las variables nos daban como opcional.

~~~
const PI; //Error
~~~

La sintaxis para crear una constante se permite con la palabra reservada: 

~~~
const PI = 3.1416 //una const de tipo primitivo number
~~~

Sin embargo, si declaramos una **const** de tipo **compuesto**, el interior del dato puede ser modificado mas adelante.

~~~
const ARREGLO_CONST = [1, 2]; //Una const de tipo objeto

ARREGLO_CONST.push(3); //Ingresamos un nuevo dato en el array

console.log(ARREGLO_CONST); //Impresion de ARREGLO_CONST
~~~

***Nota:*** Recuerda cuales son los tipos de datos **compuestos**.










