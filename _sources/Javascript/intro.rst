El lenguaje de programación Javascript
======================================

Hemos hecho un excelente progreso para aprender sobre programación web. Has aprendido algo sobre dos de los tres lenguajes de programación web principales. Continuaremos explorando HTML y CSS con más detalle, pero ahora es el momento de centrar nuestra atención en Javascript.

Aunque hemos estado llamando a los lenguajes de programación HTML y CSS, no tienen casi el poder de Javascript. Una vez que aprenda Javascript, puede escribir cualquier programa que se pueda escribir.

Javascript es un lenguaje de procedimiento. Con HTML y especialmente CSS, el orden de las cosas no siempre es importante, pero con Javascript, el orden en el que haces las cosas es muy importante. Javascript también se llama lenguaje **orientado a objetos**. Eso significa que trabajaremos con objetos en nuestro mundo imaginario del navegador. Los objetos pueden decirnos cosas que queremos saber, y los objetos saben cómo hacer muchas cosas. Solo necesitamos escribir un programa javascript para preguntar o contar.

Pero, no nos dejemos atrapar por un montón de charlas formales sobre ciencias de la computación y teoría del lenguaje de programación, comencemos con un ejemplo simple de una de las cosas en las que Javascript es bueno, es decir, hacer que los botones hagan cosas interesantes. Para nuestro primer programa, hagamos un botón que cambie el color de fondo de nuestra ventana.

.. activecode:: js_first
   :language: html
   
   <html>
      <body>
         <h1>Hello World!!</h1>
         <button onclick="changeThisPageFunc();">Click Me!</button>
         <script type="text/javascript">
            changeThisPageFunc = function() {
               document.body.style.backgroundColor = "lightblue";
               document.body.innerHTML = "<h1>I am a little blue today</h1>";
            }
         </script>
      </body>
   </html>
   
Ahora ese ejemplo puede parecerle muy complejo, y de hecho demuestra **MUCHOS** aspectos importantes de la programación. Pero no se preocupe, analizaremos este ejemplo cuidadosamente para que comprenda completamente lo que está sucediendo.

Aquí hay algunas preguntas que deberíamos responder sobre el ejemplo anterior:

#. ¿Button? No hemos hablado antes de una etiqueta de ``button``, ¿cuál es el problema con eso?
#. ¿Para qué sirve el atributo ``onclick``?
#. Etiqueta de script? Nuevamente, esta es una nueva ¿por qué una etiqueta ``script``?
#. ¿Qué significa todo eso dentro de la etiqueta del script?
#. ¿Qué le pasó a mi botón!?

Esas son todas muy buenas preguntas, me alegra que hayas preguntado. Tomemos uno a la vez en este momento, y luego ampliaremos las ideas en las próximas secciones.

La etiqueta del botón es parte del HTML que nos permitirá crear sitios web interactivos. Además de los botones, hay otras cosas como casillas de verificación y entrada de texto, de las que hablaremos en la siguiente sección. Por ahora usaremos el botón como un ejemplo simple, de algo que todos estamos acostumbrados a usar todos los días.

El atributo ``onclick`` es la forma en que respondemos a la pregunta, "¿qué debe hacer este botón cuando alguien hace clic en él". La respuesta en este caso puede llevar a confusión, pero esperamos que al menos tenga la idea de que cuando se hace clic en el botón queremos "cambiar esta página". La forma en que haremos esto es a través de una **llamada de función**. Has usado funciones en la clase de matemáticas muchas veces, y estas no son tan diferentes. Lo importante para recordar es que las funciones son **abstracciones** de cosas que deben hacerse. Todos usamos abstracciones todo el tiempo en nuestra vida cotidiana.

Por ejemplo, puede decirle a su amigo: "Voy a la informática ahora". Esta es una abstracción de los siguientes pasos hipotéticos:

#. Levantarse de la cama.
#. Vestirse
#. Sal de tu habitación, baja por el pasillo y espera el ascensor.
#. Toma el ascensor hasta el cuarto piso.
#. Salga del elevador, salga por la puerta y cruce el campus hacia el salón Olin.
#. Entra por la puerta y sube las escaleras hasta el segundo piso, entra en la habitación 202 y encuentra tu lugar favorito para sentarte.

Sería una conversación larga y aburrida si respondieras con los 6 pasos cada vez que un amigo te preguntara qué estabas haciendo. Pero tu amigo entiende que esos pasos son necesarios cuando dices que vas a clase. Más aún, incluso el paso 1 es una abstracción de varios pasos más pequeños: sentarme, quitar las sábanas, deslizar mis piernas por el costado de la cama, levantarme (o bajar por la escalera).

Esto nos lleva a la siguiente pregunta, la etiqueta ``script`` es una forma en que podemos incluir Javascript en nuestro HTML. Pero al igual que CSS, veremos que podemos y debemos también incluir Javascript al ponerlo en su propio archivo e incluirlo. Más sobre eso más tarde.

Lo que hay dentro de la etiqueta del script es el código Javascript. Este código contiene una **definición de función**, que es cómo creamos nuestras propias abstracciones. A diferencia de tu amigo que entiende naturalmente lo que significa ir a clase, las computadoras son muy tontas y muy literales, solo hacen lo que tú les dices. En este caso hay dos pasos para nuestra abstracción. Uno cambia el color de fondo del cuerpo, y el segundo cambia nuestro mensaje. Estas líneas también son abstracciones de un conjunto de pasos muy complicado del que nosotros, como programadores, no necesitamos conocer los detalles en este momento. Solo necesitamos saber qué abstracciones comprende el navegador.

Vamos a diferir la pregunta de qué pasó con el botón por un momento. Mientras tanto, experimente con el código Javascript probando lo siguiente:

#. Haz el fondo verde claro
#. Experimente con diferentes elementos de estilo que hemos aprendido a través de CSS. Vea si puede agregar una línea que haga que el texto sea rojo.
#. ¿Se puede cambiar el tamaño de fuente a 48pt?
#. ¿Qué te dice eso sobre ``document.body.style``?
#. Cambie la redacción dentro de la etiqueta ``<h1>`` en el Javascript.
#. ¿Qué sucede si agrega ``<button>Click Me</button>`` después del cierre ``</h1>``?


Veamos un pequeño ejemplo diferente que logra lo mismo, pero ilustra cómo CSS, Javascript y HTML funcionan juntos.
En este ejemplo, en lugar de establecer el color del fondo directamente, haremos que el cuerpo tenga el atributo de clase "myclass" cuando se haga clic en el botón.

Ahora,

.. activecode:: js_second
   :language: html
   
   <html>
      <head>
         <style>
         .myclass {
            background-color: lightblue;
         }
         </style>
      </head>
      <body>
         <h1>Hello World!!</h1>
         
         <button onclick="changeThisPageFunc();">Click Me!</button>
         <script type="text/javascript">
            changeThisPageFunc = function() {
               alert("body has class = "+document.body.className);
               document.body.className = "myclass";
               alert("body has class = "+document.body.className);
               document.body.innerHTML = "<h1>I am a little blue today</h1>";
            }
         </script>
      </body>
   </html>
