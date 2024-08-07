
# 30. Alert, Confirm y Prompt.

Estos son ***métodos*** del objeto ***window***, útiles para poder interactuar con el ***usuario*** de una forma muy rápida.

Estos ***métodos*** permiten al ***usuario***, ***visualizar*** datos, ingresar ***datos***, y ***tomar*** decisiones, para el manejo de las ***acciones*** del ***programa***. 

Como parte de una sintaxis más simple, pueden ser llamados de manera ***directa*** sin ***invocar***a ***window***.

## alert

Este ***método*** activa una ventana con un ***mensaje*** visible en el ***browser***, acompañada de un ***botón*** de ***confirmación***.

La sintaxis:

~~~
//alert
window.alert("Esto es una alerta");
~~~

De forma ***directa*** podemos escribir:

~~~
//alert
alert("Esto es una alerta");
~~~

***Nota:*** Este método es útil para mostrar ***mensajes*** de ***confirmación*** y ***avisos*** de sucesos al ***cliente***.

La ***única acción disponible*** para el ***usuario*** es la ***confirmación***, si deseamos poder dar a elegir al usuario podemos usar el ***método*** siguiente:

## confirm

Este ***método*** activa una ventana con un ***mensaje*** visible en el ***browser***, pero, a diferencia del ***alert*** esta va acompañada de  ***2 botones***, uno de ***aceptar***, y otro de ***cancelar*** o ***denegar***.

Esto permite la ***elección*** del ***usuario*** a dos ***opciones***. que dependiendo de la elección podremos programar.

La sintaxis es la siguiente:

~~~
//confirm
window.confirm("Esto es una confirmacion, ¿Desea continuar?");
~~~

O de manera mas corta:

~~~
//confirm
confirm("Esto es una confirmacion, ¿Desea continuar?");
~~~

Dependiendo de la ***opción*** elegida por el ***usuario***, podremos obtener un dato.

Para ***obtener*** el ***resultado*** de la ***elección***, basta ***asignar*** el resultado del ***método*** a un ***identificador***.

Como el siguiente ejemplo:

~~~
//confirm y almacenamiento de resultado
let confirmacion = confirm("Esto es una confirmacion, ¿Desea continuar?");
~~~

Para luego poder ***obtener*** el ***resultado***:

~~~
//Impresion de confirmacion
console.log(confirmacion);
~~~

***Nota:*** El resultado siempre sera un ***boolean***, ***true*** o ***false***, dependiendo de la elección del ***cliente***.

## prompt

Este ***método*** despliega en el ***navegador*** una ***ventana***, acompañada de un ***texto***, un ***campo de ingreso*** para ***datos*** y ***2 botones***, uno de ***confirmar*** y otro de ***cancelar***.

Este ***método*** tiene la siguiente sintaxis:

~~~
//prompt
window.prompt("Esto es un prompt, Ingrese su dato:");
~~~

Y de manera corta:

~~~
//prompt
prompt("Esto es un prompt, Ingrese su dato:");
~~~

Al igual que el ***confirm***, este permite ***almacenar*** su ***resultado*** ingresado en el ***campo de texto*** en una variable.

Para ello, asignamos su resultado a un ***identificador***:

~~~
//prompt y almacenamiento de resultado  
let aviso = prompt("Esto es un prompt, Ingrese su dato:");
~~~

Para poder ser utilizado:

~~~
//Impresion de aviso
console.log(aviso);
~~~

***Nota:*** El valor que se ingrese en el ***campo***, se almacenara en el identificador.

***Nota:*** Si el ***campo*** es enviado ***vacío***, se recibirá una ***cadena vacía***.

***Nota:*** Si se ***cancela*** el ***prompt***, se recibirá el valor ***null***.


	EL DISEÑO DE LAS VENTANAS DE ESTOS METODOS NO PUEDEN SER MODIFICADOS, PERO SU TEXTO PUEDE SER PERSONALIZADO.



