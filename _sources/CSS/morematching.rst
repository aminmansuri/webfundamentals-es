Más Sobre Emparejamiento
=========================

Ahora que sabemos cómo cambiar algunos elementos de estilo en las etiquetas, podemos seguir adelante y aprender más sobre los selectores y cómo usar los selectores junto con dos nuevos atributos html que nos dan mucha más flexibilidad para diseñar un documento html.


Emparejamiento de Múltiples Etiquetas
---------------------------------------

supongamos que queremos tener encabezados h1, h2 y h3 en azul, pero los encabezados h4, h5 y h6 en verde. No tenemos que escribir una regla separada para cada etiqueta de encabezado, podemos escribir una regla que se vea así:

.. code-block:: css

   h1,h2,h3 {
       color: blue;
   }

   h4,h5,h6 {
       color: green;
   }


Puede leer las comas entre las etiquetas como "or". Entonces, la primera de las reglas anteriores se lee como Si la etiqueta es h1 o h2 o h3, cambie el color a azul.

En el ejemplo a continuación, agregue una regla para que h2 y el párrafo tengan el color rojo.

.. activecode:: css_or
   :language: html

   <html>
      <head>
         <style>
         h1 {
            color: blue;
            font-size: 28pt;
         }
         </style>
      </head>
      <body>
         <h1>Hello World!!</h1>
         <p>The paragraph text should be unchanged</p>
         <h2>I am not blue!</h2>
         <h1>Hello Again</h1>
      </body>
   </html>


Usar un Atributo id en una Regla
----------------------------------

Otra situación común es que tiene un párrafo en particular que desea tener en un color diferente. No puede simplemente usar un selector que coincida con la etiqueta p, ya que coincidirá con todas las etiquetas p. Entonces, en este caso, debemos marcar de alguna manera un párrafo en particular para que podamos tener un selector que seleccione ese párrafo y solo ese párrafo. Aquí es donde se usa el atributo ``id``. Cualquier etiqueta html puede tener un atributo id, que sirve como un **identificador único** para esa etiqueta. De hecho, el valor del atributo id debe ser único en todo el archivo.


En el siguiente ejemplo tenemos dos reglas. Uno que cambia el texto a azul en todos los párrafos. La segunda regla cambia el tamaño de fuente a 18 puntos para el párrafo que tiene el identificador de "abc456". El hashtag ``#`` es muy importante para esta regla, ya que le dice al css matcher que lo que viene después de ese hashtag debe coincidir con la identificación atributo de algún elemento. Entonces, de hecho, la p es redundante en este ejemplo, y podría eliminar la p desde el comienzo del selector y la regla aún funcionaría. De hecho, deberías probar eso ahora.

.. activecode:: css_ids
   :language: html

   <html>
      <head>
         <style>
         p {
            color: blue;
         }
         p#abc456 {
            font-size: 18pt;
         }
         </style>
      </head>
      <body>
         <h1>Hello World!!</h1>
         <p id="xyz123">The paragraph text should be unchanged</p>
         <h2>I am not blue!</h2>
         <h1>Hello Again</h1>
         <p id="abc456">This is another paragraph with a different identifier.</p>
      </body>
   </html>


¿Qué crees que sucederá si cambias la segunda regla para que establezca el color en rojo? Si dijiste que mantendrá el color azul del primer párrafo pero cambiará el segundo a rojo, estás en lo correcto. ¿Por qué la segunda regla prevalece sobre la primera? Porque la segunda regla es más específica. Es posible que haya pensado que fue debido al orden de las reglas, pero de hecho puede cambiar el orden de las dos reglas y probarlo, y verá que aún obtiene el mismo resultado.

Usar un Atributo de Clase en una Regla
----------------------------------------

A veces, desea hacer coincidir algunos elementos que son la misma etiqueta pero no otros. Un ejemplo de esto es cuando desea tener una tabla de "rayas de cebra", donde cualquier otra línea tiene un color de fondo ligeramente diferente, entonces querrá usar un atributo de ``clase``. Las clases y CSS pueden ser la combinación más útil para diseñar sus páginas web.

A diferencia del atributo ``id``, muchas etiquetas diferentes pueden tener el mismo valor para una clase. Algunos ejemplos:

Tiene párrafos o encabezados y desea algo normal, algunos son "advertencias", algunos son "errores" y otros son "precauciones". O tal vez tenga una lista de cosas, algunas de las cuales son de alta prioridad, algunas son bajas y otras son medianas. Al usar una clase, puede aplicar un estilo consistente a todas las cosas que pertenecen a esa clase (tienen el mismo valor para su atributo de clase).

Para seleccionar cualquier elemento que coincida con una clase en particular, use el `` .`` antes del nombre de la clase. Entonces ``.high`` coincidirá con cualquier etiqueta que tenga el atributo ``class=high``.

Volviendo a nuestro ejemplo de tabla HTML, tenemos algunas filas que son "impares" y algunas que son "pares". Hagamos una tabla corta y estilo las filas pares e impares de manera diferente.

.. activecode:: css_classes
   :language: html

   <html>
      <head>
         <style>
         .odd {
            background-color: #9999ee;
         }
         .even {
            background-color: pink;
         }
         </style>
      </head>
      <body>
           <table>
           <tr class="odd"><td>aapl</td><td>$101.23</td></tr>
           <tr class="even"><td>goog</td><td>$583.10</td></tr>
           <tr class="odd"><td>tsla</td><td>$281.10</td></tr>
           <tr class="even"><td>amzn</td><td>$331.33</td></tr>
           </table>
      </body>
   </html>



Ahora, para practicar un poco más, hagamos que la mesa se vea realmente agradable. Agregue un encabezado y haga que el fondo del encabezado sea gris claro. Haga el texto del encabezado en negrita y ligeramente más grande. En general, cambie la tabla para que su ancho sea el 50% de la página y elimine la página. `Esta página <http://www.w3schools.com/css/css_table.asp>`_ le ofrece un resumen completo sobre cómo diseñar tablas.


Emparejando Hijos
------------------

Cuando se utilizan los elementos html semánticos, a veces es muy deseable hacer coincidir una etiqueta en particular, pero solo si esa etiqueta está en la sección del artículo. CSS nos permite hacer coincidir las etiquetas que son descendientes de otras etiquetas mediante el uso de un espacio después de la etiqueta principal. Por ejemplo:

.. code-block:: css

   article h1 {
       color:  purple;
   }


Cambiará el color de la h1 pero solo si son descendientes de la etiqueta del article.


.. activecode:: css_descendant
   :language: html

   <html>
      <head>
         <style>
         article h1 {
             color: purple;
         }
         </style>
      </head>
      <body>
      <h1>This is outside the article</h1>
      <article>
          <h1>This is inside the article</h1>
          <section>
              <h1>This is in a section of an article</h1>
          </section>
      </article>
      </body>
   </html>


En el ejemplo anterior, los dos h1 dentro del article se cambiaron porque ambos son descendientes del article. Si solo quisiéramos cambiar el h1 que es un hijo directo de article, podemos reemplazar el espacio con un ``>`` dándonos ``article>h1`` que indica que solo el hijo inmediato debe cambiar su estilo.
