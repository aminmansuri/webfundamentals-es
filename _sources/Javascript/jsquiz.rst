Prueba de Javascript
====================

Para la siguiente pregunta, puede usar el libro de texto o sus notas. No puede googlear otras referencias. Tiene 30 minutos para completar esto y puede probarlo tantas veces como sea necesario.

.. qnum::
   :prefix: Q-
   :start: 1


.. timed:: js1timed

   .. mchoice:: q3_5
      :multiple_answers:
      :answer_a: document.body.h1
      :answer_b: document.h1
      :answer_c: document.body
      :answer_d: document.body.style
      :correct: c,d
      :feedback_a: ¿Qué pasa si hay más de un h1?
      :feedback_b: No, como mínimo, el h1 estaría dentro del cuerpo
      :feedback_c: Sí
      :feedback_d: correcto


      ¿Cuál de los siguientes es legal?


   .. mchoice:: q3_3
      :answer_a: dragon
      :answer_b: wizard
      :answer_c: castle
      :answer_d: dungeon
      :correct: b
      :feedback_a: No lo suficientemente lejos
      :feedback_b: Buen trabajo
      :feedback_c: No del todo, verifique el orden de los identificadores
      :feedback_d: No, revise los identificadores cuidadosamente


      Dado el siguiente fragmento de Javascript, ¿qué dirá el cuadro de alerta?

          .. code-block:: html

              <html>
              <ul>
                 <li id="d">dragon</li>
                 <li id="c">wizard</li>
                 <li id="b">castle</li>
                 <li id="a">dungeon</li>
              </ul>
              <script type="text/javascript">
                  myLi = document.querySelector('#c')
                  alert(myLi.innerHTML)
              </script>
              </html>

   .. mchoice:: q3_4
      :answer_a: un string
      :answer_b: el string wizard
      :answer_c: un elemento HTML li en el árbol
      :answer_d: una regla CSS
      :correct: c
      :feedback_a: No, el atributo innerText es una cadena
      :feedback_b: No, el atributo innerText sería el asistente de cadena
      :feedback_c: Buen trabajo
      :feedback_d: No, esto no tiene nada que ver con CSS todavía.

      Refiriéndose al código en la pregunta anterior, ¿a qué tipo de cosas se refiere ``myLi``?


.. reveal:: jquiz1prog

   1.  Dado el siguiente HTML, agregue un botón con una función de devolución de llamada que cambie el ``h1`` de "Hello World" a "So Long CS130". Cuando cambie el mensaje, también debe organizarlo para que el color del texto se vuelva azul. El resto de su página debe permanecer sin cambios.

   .. actex:: jsquiz_1
      :language: html

      <html>
      <body>
      <h1 id="hello">Hello World</h1>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
      </body>
      </html>
