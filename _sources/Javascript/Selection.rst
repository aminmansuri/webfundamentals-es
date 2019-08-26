Selección
=========

La selección nos permite hacer preguntas y tomar diferentes acciones dependiendo de las respuestas. Usamos la selección todos los días a medida que avanzamos en nuestras tareas. Si hace frío, nos ponemos algo de ropa extra. Si está lloviendo, agarramos nuestro paraguas antes de salir de la casa. Estos son ejemplos de los tipos de decisiones que tomamos. Más formalmente podemos poner esto en una declaración de ``if``. ``si`` está lloviendo, ``entonces`` tomamos nuestro paraguas.

Javascript nos permite hacer preguntas como esta usando una declaración ``if`` también. Una declaración if se usa a menudo en Javascript para verificar un valor de entrada de
un cuadro de texto para asegurarse de que sea un buen valor. Por ejemplo, si los colores solo pueden estar en el rango de 0 a 255, podríamos verificar el valor de un cuadro de entrada de la siguiente manera:


.. activecode:: select_1
   :language: html
   
   <html>
      <label for="red">Red:</label>
      <input id="red" type="text" onchange="checkme(this)" />
      <label for="green">Green:</label>
      <input id="green" type="text" onchange="checkme(this)" />
      <label for="blue">Blue:</label>
      <input id="blue" type="text" onchange="checkme(this)" />

      <script type="text/javascript">
      checkme = function(textbox) {
         if (textbox.value > 255) {
            alert("Value is too large, must be less than 256");
            textbox.value = 255;
         }
      }
      </script>
   </html>


En este ejemplo, tenemos una función que puede verificar los valores de cualquiera de nuestros cuadros de entrada de texto en color. Una vez más tenemos el interesante tema de cómo la función checkme sabe qué cuadro de texto se supone que debe verificar. Cuando estamos configurando una llamada desde html, podemos pasar ``this`` como un parámetro especial que se refiere al objeto al que está conectado el onchange.


Si desea practicar un poco, agregue otra instrucción if a ``checkme`` que garantice que el valor ingresado por el usuario sea mayor o igual a cero.


Juego de adivinanzas
=====================

Aquí hay una aplicación simple que usa la selección para permitirte jugar al viejo juego de adivinanzas.

La computadora seleccionará un número entre 1 y 100. Puede escribir su suposición en el cuadro y la computadora le dirá cuándo tiene razón, o si su suposición es demasiado alta o demasiado baja.

Para seleccionar nuestro número, utilizaremos otro método de Javascripts para crear un número aleatorio. Esto se llama ``Math.random()`` Genera un número aleatorio entre 0 y 1, por lo que tendremos que hacer un poco de trabajo para convertirlo en un número aleatorio entre 1 y 100.


.. activecode:: select_2
   :language: html

   <html>
   
   <body>   
      <label for="red">Guess:</label>
      <input id="guess" type="text" />
      <button onclick="check()">Check</button>
      <script type="text/javascript">
      theNumber = Math.floor(Math.random()*100)
      check = function() {
          guess = document.querySelector("#guess").value;
          if (guess == theNumber) {
              alert("you are right!")
          } else {
              if (guess < theNumber) {
                  alert("you are too low")
              } else {
                  alert("you are too high")
              }
          }
      }
      </script>
   </body>
   </html>
   
Cosas para hacer:

* Cambie esto para no usar una alerta. Actualice el innerHTML de un párrafo para decirle al usuario si es demasiado alto o demasiado bajo.
* Agregue una lista creada dinámicamente para realizar un seguimiento de las conjeturas, colorear las conjeturas que son demasiado altas en rojo y las conjeturas que son demasiado bajas.
* Mantenga un registro del número de conjeturas y diga al usuario al final cuántas conjeturas necesitaban.
* Para jugar un juego nuevo, ahora debes volver a cargar la página. ¿Puedes agregar un botón de reinicio que forme un nuevo número y borre todo lo demás?
