# 60. Web APIs.

	API singifica, en ingles, Application programming interface.

Una ***API web*** es el ***conjunto*** de funcionalidades desde las cuales podemos interactuar con la ***aplicación*** del navegador, de ***html***, ***css*** y ***JavaScript***.

Existen ***3 diferentes APIs webs*** disponibles en ***JavaScript***.

	- DOM -> Document Object Model
	- BOM -> Browser Object Model
	- CSSOM -> CSS Object Model.

Ademas de ***otras APIs*** menores.

Una de ellas ***speech*** (Chat de voz desde la web):

Un ejemplo:

~~~
let texto = "Hola";

const hablar = (texto) => speechSynthesis.speak(new SpeechSynthesisUtterance(texto));

hablar(texto);
~~~

## DOM

El ***DOM*** (Document Object Model) es la ***representacion estandarizada*** de la ***estructura HTML*** de un ***archivo .html*** como ***objeto literal*** en ***JS***.

## CSSOM

El ***CSSOM*** (CSS Object Model) es la ***representación*** de los ***estilos css*** en un archivo.

## BOM

El ***BOM*** es la ***representación*** del ***navegador*** e información de este y todos los ***métodos*** disponibles en relación al ***browser***.

---

***Nota:*** Todos estos ***elementos*** se encuentran en el ***elemento global window***.

---


