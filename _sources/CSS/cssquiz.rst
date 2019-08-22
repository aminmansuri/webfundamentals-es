Prueba dos
------------



.. timed:: css_quiz_1
   :timelimit: 20

   .. mchoice:: q1_1
      :multiple_answers:
      :answer_a: &lt;h1&gt;
      :answer_b: &lt;p&gt;
      :answer_c: &lt;img&gt;
      :answer_d: &lt;li&gt;
      :correct: a,b,d
      :feedback_a: Sí
      :feedback_b: Sí
      :feedback_c: No, una etiqueta img es un elemento en línea
      :feedback_d: Sí

      ¿Cuáles de los siguientes son elementos de bloque HTML? Seleccione todas las que correspondan.

   .. mchoice:: q1_2
      :answer_a: File Transfer Protocol
      :answer_b: HyperText Markup Language
      :answer_c: Secure Sockets Layer
      :answer_d: HyperText Transfer Protocol
      :correct: d
      :feedback_a: No, FTP no está relacionado con esta clase.
      :feedback_b: No, HTML es el lenguaje de marcado, no el protocolo
      :feedback_c: No, no se usa SSL
      :feedback_d: Sí

      ¿Cuál es el protocolo utilizado en la URL? ``http://interactivepython.org/index.html``


   En la siguiente pregunta, seleccione todas las respuestas correctas para cada pregunta.

   .. mchoice:: q1_3
      :multiple_answers:
      :answer_a: &lt;h1 class="low"&gt;Hello World&lt;/h1&gt;
      :answer_b: &lt;p class="high"&gt;some text&lt;/p&gt;
      :answer_c: &lt;p&gt;some text&lt;/p&gt;
      :answer_d: &lt;li class="high"&gt;do my homework&lt;/li&gt;
      :answer_e: &lt;p id="high"&gt;some text&lt;/p&gt;
      :correct: b,d
      :feedback_a: Este h1 tiene clase baja
      :feedback_b: Sí
      :feedback_c: No, la etiqueta de párrafo es solo un párrafo simple sin clase
      :feedback_d: Yes
      :feedback_e: No, el selector coincide con la clase, no con el id.

      ¿Cuál de las siguientes opciones coincidirá con el selector CSS ``.high``

   .. mchoice:: q1_4
      :multiple_answers:
      :answer_a: &lt;h1 class="low"&gt;Hello World&lt;/h1&gt;
      :answer_b: &lt;p class="high"&gt;some text&lt;/p&gt;
      :answer_c: &lt;p&gt;some text&lt;/p&gt;
      :answer_d: &lt;li class="high"&gt;do my homework&lt;/li&gt;
      :answer_e: &lt;p id="high"&gt;some text&lt;/p&gt;
      :correct: b
      :feedback_a: Este h1 tiene clase baja
      :feedback_b: Yes
      :feedback_c: No, la etiqueta de párrafo es solo un párrafo simple sin clase
      :feedback_d: No, esta es una etiqueta li
      :feedback_e: No, este selector está buscando un párrafo con una clase de alta

      ¿Cuál de los siguientes coincidirá con el selector CSS? ``p.high``


   .. mchoice:: q1_5
      :multiple_answers:
      :answer_a: &lt;h1 class="low"&gt;Hello World&lt;/h1&gt;
      :answer_b: &lt;p class="high"&gt;some text&lt;/p&gt;
      :answer_c: &lt;p&gt;some text&lt;/p&gt;
      :answer_d: &lt;li class="high"&gt;do my homework&lt;/li&gt;
      :answer_e: &lt;p id="high"&gt;some text&lt;/p&gt;
      :correct: b,c,e
      :feedback_a: No, esta es una etiqueta h1
      :feedback_b: Sí
      :feedback_c: Sí
      :feedback_d: No, esta es una etiqueta li
      :feedback_e: Sí

      ¿Cuál de los siguientes coincidirá con el selector CSS? ``p``

   .. mchoice:: q1_6
      :multiple_answers:
      :answer_a: &lt;h1 class="low"&gt;Hello World&lt;/h1&gt;
      :answer_b: &lt;p class="high"&gt;some text&lt;/p&gt;
      :answer_c: &lt;p&gt;some text&lt;/p&gt;
      :answer_d: &lt;li class="high"&gt;do my homework&lt;/li&gt;
      :answer_e: &lt;p id="high"&gt;some text&lt;/p&gt;
      :correct: e
      :feedback_a: No this is an h1 tag
      :feedback_b: No, this selector is matching the id attribute
      :feedback_c: No, this selector is looking for an id
      :feedback_d: No, this selector is matching on the id not the class
      :feedback_e: Yes

      ¿Cuál de los siguientes coincidirá con el selector CSS? ``#high``


   .. mchoice:: q1_7
      :multiple_answers:
      :answer_a: height
      :answer_b: padding
      :answer_c: border
      :answer_d: margin
      :answer_e: background-color
      :correct: b,c,d
      :feedback_a: No, height es un atributo del contenido
      :feedback_b: Sí
      :feedback_c: Sí
      :feedback_d: Sí
      :feedback_e: No, background-color no es parte del modelo de caja

      ¿Cuáles de las siguientes son propiedades del modelo de caja CSS?


Cuando haya terminado la pregunta anterior, haga clic en el botón Mostrar a continuación para mostrar dos ejercicios adicionales.

Para las siguientes preguntas, utilizaré su resultado final. Puede presionar el botón Ejecutar tantos
veces como quieras sin penalización. También debe guardar su versión final.

.. reveal:: css_qs
   :showtitle: Show Final Questions

   Complete el HTML adicional necesario para hacer una lista ordenada de 3 elementos. Los artículos deben estar numerados A, B y C.

   .. actex:: q1_8
      :language: html

      <html>

      </html>

   Dado el HTML en el código activo a continuación, agregue el CSS apropiado para diseñar el h1 con una fuente de 28pt y un color rgb que consiste en rojo: 128, azul: 200, verde: 99 y el *último* párrafo con un color naranja.

   .. actex:: q1_9
      :language: html

      <html>
         <body>
            <h1>Learning about HTML</h1>
            <p>HTML is a fun and easy language to learn</p>
            <h2>Learning about CSS</h2>
            <p class="css"> CSS is fun too, but more challenging than HTML</p>
         </body>
      </html>
