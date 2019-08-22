Javascript: Prueba final
==========================

Para las siguientes preguntas, puede usar el libro de texto o sus notas. No puede googlear otras referencias. Tienes 30 minutos para completar ambas partes del cuestionario. Asegúrese de completar las
preguntas de opción múltiple primero, y haga clic en "Finalizar examen" antes de continuar con la pregunta de codificación.

.. qnum::
   :prefix: Q-
   :start: 1


.. timed:: js2timed

   .. mchoice:: q4_1
      :answer_a: &lt;script&gt;
      :answer_b: &lt;scripting&gt;
      :answer_c: &lt;style&gt;
      :answer_d: &lt;javascript&gt;
      :correct: a
      :feedback_a: Sí
      :feedback_b: Cerca
      :feedback_c: El estilo es para CSS
      :feedback_d: No


      ¿Dentro de qué etiqueta HTML ponemos el código Javascript?

   .. mchoice:: q4_2
      :answer_a: #demo.innerHTML = "Hello World!";
      :answer_b: document.appendChild("p").innerHTML = "Hello World!";
      :answer_c: document.getElement("p").innerHTML = "Hello World!";
      :answer_d: document.querySelector("#demo").innerHTML = "Hello World!";
      :correct: d
      :feedback_a: No, esto es un error
      :feedback_b: No
      :feedback_c: No
      :feedback_d: Sí!

      Cuál es la declaración correcta para cambiar lo siguiente: ``<p id="demo"> Esta es una demostración.</p>``

   .. mchoice:: q4_3
      :answer_a: onchange
      :answer_b: onclick
      :answer_c: onmouseover
      :answer_d: onmouseclick
      :correct: b
      :feedback_a: No, esto funcionaría solo con elementos de entrada
      :feedback_b: Sí
      :feedback_c: No, este evento no requiere un click
      :feedback_d: No, esto no es un evento

      ¿Qué evento ocurre cuando el usuario hace click en un elemento HTML?


   .. mchoice:: q4_4
      :answer_a: document.body.ol.innerHTML = "&lt;li&gt;"
      :answer_b: myLi = "#newli"
      :answer_c: document.createElement("li")
      :answer_d: myOl.appendChild("li")
      :correct: c
      :feedback_a: No, no hay document.body.ol
      :feedback_b: Esto solo asigna un string a una variable
      :feedback_c: Sí
      :feedback_d: No, appendChild no crea un elemento

      ¿Qué declaración de JavaScript crea correctamente una nueva entrada para una lista?


   .. mchoice:: q4_5
      :answer_a: True
      :answer_b: False
      :correct: b
      :feedback_a: Sin realimentación
      :feedback_b: Sin realimentación

      Un archivo JavaScript externo debe contener la etiqueta ``<script>``.

   .. mchoice:: q4_6
      :answer_a: msg("Hello World");
      :answer_b: console.log("Hello World");
      :answer_c: alertBox("Hello World");
      :answer_d: alert("Hello World");
      :correct: d
      :feedback_a: No, no hay función de mensaje
      :feedback_b: Esto agrega un mensaje a la consola javascript
      :feedback_c: No hay función alertBox
      :feedback_d: ¡Sí!

      ¿Cómo se escribe "Hola mundo" en un cuadro de alerta?


   .. mchoice:: q4_7
      :answer_a: myFunction = function()
      :answer_b: myFunction()
      :answer_c: function:myFunction()
      :answer_d: &lt;script&gt;function = {}&lt;/script&gt;
      :correct: a
      :feedback_a: Sí
      :feedback_b: No, esto llama myFunction
      :feedback_c: No, the : está mal
      :feedback_d: No, esto está sintácticamente todo mal

      ¿Cómo se crea una función en JavaScript?


   .. mchoice:: q4_8
      :answer_a: myTr.addParent(myRow);
      :answer_b: document.body.innerHTML = "&lt;tr&gt;&lt;tr&gt;&lt;/tr&gt;&lt;/td&gt;"
      :answer_c: myRow.appendChild(myTr);
      :answer_d: myTr.appendChild(myRow);
      :correct: c
      :feedback_a: No hay función addParent
      :feedback_b: No, esto cambia todo el cuerpo
      :feedback_c: Sí
      :feedback_d: No, tienes padre e hijo hacia atrás

      ¿Qué enunciado agrega correctamente un elemento tr llamado myTr al árbol DOM?


   .. mchoice:: q4_9
      :answer_a: &lt;script name="xxx.js"&gt;
      :answer_b: &lt;script src="xxx.js"&gt;
      :answer_c: &lt;script href="xxx.js"&gt;
      :answer_d: &lt;link href="xxx.js"&gt;
      :correct: b
      :feedback_a: No, el nombre se usa principalmente con etiquetas de entrada
      :feedback_b: Sí
      :feedback_c: href se usa con la etiqueta de enlace
      :feedback_d: No, el enlace se usa para incluir css

      ¿Cuál es la sintaxis correcta para referirse a un script externo llamado "xxx.js"?

   
   .. mchoice:: q4_10
      :answer_a: a1
      :answer_b: a2
      :answer_c: a3
      :answer_d: a5
      :correct: b
      :feedback_a: No, a1 es el abuelo
      :feedback_b: Sí
      :feedback_c: No, a3 es un hermano
      :feedback_d: No, a5 es hijo de a4

      Dada la siguiente fuente HTML, ¿cuál es el elemento primario del elemento con el selector "#a4"

      .. code-block:: html

         <body>
         <table id="a1">
         <tr id="a2">
            <td id="a3">Hello</td>
            <td id="a4"><img id="a5" src="hello.jpg"></td>
         </tr>
         </table>
         </body>



Pregunta de programación
------------------------

    Escriba una función que * cada vez que se haga clic en ella * haga lo siguiente:

    1. Convierta el fondo de la página en azul claro.
    2. Agregue otro H1 a la página que dice "So Long 130"
    3. Cambia el color de fuente para el H1 a rojo

    Por cada vez, quiero decir que si se hace clic en el botón 10 veces, debería haber 10 H1 en la página.


.. activecode:: q4_11
   :language: html

   <html>
   <body>
       <button onclick="finalquiz();">Click Me</button>
       <script type="text/javascript">

       </script>
   </body>
   </html>
