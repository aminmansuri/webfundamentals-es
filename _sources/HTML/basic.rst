Etiquetas HTML básicas
=========================

Encabezados
-------------

Como cualquier documento, los documentos HTML pueden tener varias capas de encabezados. De hecho, puede tener niveles de encabezado del 1 al 6 en un documento HTML.

.. activecode:: html_headings
   :language: html

   <h1>Level one</h1>
   <h2>Level two</h2>
   <h3>Level three</h3>


Ahora modifica el ejemplo anterior para agregar los siguientes tres niveles de encabezados. ¿Que notaste? ¿Qué sucede si agrega un título de nivel 7? ¿Qué sucede si cierra una etiqueta h2 con un h1 o un h3?

.. reveal:: reveal_heading

   Como es de esperar, los títulos continúan disminuyendo a medida que avanza del 1 al 6. Pero cuando pasa al nivel 7, el texto se hace más grande. Esto se debe a que el navegador web está escrito de modo que simplemente ignora cualquier etiqueta que no conozca. Esto es una desventaja, ya que no recibe ningún mensaje de error, las cosas simplemente se ven mal y tiene que descubrir por qué.



Otro aspecto de la etiqueta de encabezado es que es lo que llamamos una etiqueta **block**. Observe que cada encabezado aparece en su propia línea. Eso es más o menos lo que esperaríamos para un encabezado. Pero no necesariamente para otras etiquetas. En breve, veremos algunas etiquetas **en línea** que no aparecen en su propia línea.


Los párrafos
-------------

Los párrafos son otro elemento fundamental de los documentos. Los párrafos también son otro ejemplo de un elemento de bloque en el que cada párrafo tiene su propio espacio y está separado de otros elementos html por líneas en blanco en el documento.


.. activecode:: html_paragraph
   :language: html

   <p>This is a short sentence.</p>
   <p>This is a paragraph.  What happens when we have a really really really long line that takes up more than one line of the browser? </p>
   <p>Level this is a short sentence</p>


¿Qué sucede cuando pones un párrafo dentro de otro párrafo? ¿Qué pasa con un encabezado dentro de un párrafo?


Imágenes
----------

Las imágenes son otro elemento común de un documento o una página web. Para incluir una imagen en un documento, debe usar una etiqueta ``img``. Las etiquetas de imagen son un ejemplo de un elemento **en línea** porque simplemente fluyen con el texto circundante. No obligan a crear un nuevo bloque en la representación del html. Aquí hay un par de imágenes:

.. figure:: Figures/LutherBellPic.jpg

   Luther Bell:  ``http://interactivepython.org/runestone/static/webfundamentals/_images/LutherBellPic.jpg``

.. figure:: Figures/norse-logo.png

   Norse Logo:  ``http://interactivepython.org/runestone/static/webfundamentals/_images/norse-logo.png``


La etiqueta de imagen tiene un nuevo componente llamado atributo. En general, las etiquetas pueden tener muchos atributos en el caso de una imagen, podemos incluirla utilizando un atributo ``src`` que contiene la URL de la imagen que queremos incrustar. Podemos incrustar cualquier imagen en Internet en nuestro propio documento al referirnos a él por su URL en el atributo ``src``.

.. activecode:: html_img
   :language: html

   <h1>Imágenes incrustadas</h1>
   <p>Las imágenes son elementos en línea que encajan en el flujo
   <img src="http://interactivepython.org/runestone/static/webfundamentals/_images/LutherBellPic.jpg">
   de un párrafo sin causar saltos de línea adicionales.</p>


Intenta modificar el ejemplo anterior para que incluya el logotipo nórdico en lugar de la campana.
También puedes cambiar el alto y el ancho de una imagen utilizando un atributo ``height=`` o un atributo ``width=``. Intenta cambiar el tamaño de la imagen en el ejemplo anterior. Observa lo que le hace al flujo. Intenta cambiar solo uno de alto o ancho y luego intenta cambiar ambos al mismo tiempo. Puedes estirar tu imagen, hacer de todo tipo de locuras.

También hay varios otros atributos de la etiqueta de imagen. Puede leer sobre ellos `here <http://www.w3schools.com/tags/tag_img.asp>`_.


Links
-----

El último enlace básico para cubrir en esta sección es la etiqueta de enlace ``a``. De hecho, la última oración de la sección anterior utilizaba un enlace para enviarlo al sitio web de w3schools para obtener más información sobre los atributos de una etiqueta ``img``. Los enlaces son lo que hizo que la web fuera tan popular en primer lugar. Hoy los llamamos enlaces, pero en años anteriores generalmente se los denominaba hipervínculos. Puede proporcionar un enlace a cualquier URL en la web utilizando el atributo ``href`` en la etiqueta ``a``. El texto en el que hará clic va entre la etiqueta de apertura ``a`` y la etiqueta de cierre ``a``.


.. activecode:: html_link
   :language: html

   <h1>Los enlaces hacen la web!</h1>
   <p>Los enlaces son otro elemento en línea. Puedes leer sobre enlaces y sus atributos
   <a href="http://www.w3schools.com/tags/tag_a.asp">aquí</a> en el sitio web de w3schools</p>


Intenta hacer clic en el enlace del ejemplo anterior. ¿Lo que pasa? ¿Cómo vuelves? No te preocupes, siempre puedes volver a cargar esta página.

Los enlaces también se pueden usar para navegar dentro de la misma página, para hacer esto, usa una etiqueta ``a`` para crear
un punto de anclaje en la página usando el atributo de nombre como este:  ``<a name="target">Soy un objetivo</a>`` Puede crear
un enlace que saltará al objetivo en cualquier otro lugar de la página usando ``<a href="#target">Ir al objetivo</a>``


Formato de texto simple
--------------------------

Hacer texto en negrita o cursiva y otros formatos también es fácil en HTML. El siguiente ejemplo ilustra las etiquetas básicas de formato de texto.

.. activecode:: html_fmt
   :language: html

   <html>
   <body>

   <p><b>Este texto está en negrita</b></p>
   <p><strong>Este texto es fuerte</strong></p>
   <p><i>Este texto está en cursiva</i></p>
   <p><em>Este texto es enfatizado</em></p>
   <p><code>Esta es la salida de la computadora</code></p>
   <p>Este es<sub> subíndice</sub> y <sup>superíndice</sup></p>
   <p>Esto <br /> fuerza <br /> un <br /> salto de línea </p>
   </body>
   </html>

Puedes mezclar y combinar estos estilos en todo tipo de formas. Intenta hacer un superíndice dentro de un superíndice. Intenta poner el subíndice en negrita o cursiva.


**Revisa tu entendimiendo**

.. clickablearea:: blockelem
   :question: Haga clic en la etiqueta de inicio para todos los elementos de bloque en el ejemplo.
   :iscode:
   :feedback: Los elementos de bloque comienzan en una nueva línea y ocupan todo el ancho disponible.

   &lt;html&gt;
   :click-incorrect:&lt;body&gt;:endclick:

   :click-correct:&lt;h1&gt;:endclick:Welcome to my Page&lt;/h1&gt;
   :click-correct:&lt;p&gt;:endclick:Hello World!   This is :click-incorrect:&lt;b&gt;:endclick:me&lt;/b&gt; :click-incorrect:&lt;img src="me.jpg"&gt;:endclick: &lt;/p&gt;
   :click-correct:&lt;p&gt;:endclick:This is my second paragraph
   :click-incorrect:&lt;a href="home.html"&gt;:endclick:Click here for my homepage&lt;/a&gt;
   :click-incorrect:&lt;/p&gt;:endclick:
   &lt;/body&gt;
   &lt;/html&gt;


.. clickablearea:: inlineelem
   :question: Haga clic en la etiqueta de inicio para todos los elementos en línea en el ejemplo.
   :iscode:
   :feedback: Los elementos en línea no comienzan en una nueva línea y solo toman el ancho que sea necesario.

    &lt;html&gt;
    &lt;body&gt;
    :click-incorrect:&lt;h1&gt;:endclick:Welcome to my Page&lt;/h1&gt;
    &lt;p&gt;Hello World!  This is :click-correct:&lt;b&gt;:endclick:me&lt;/b&gt; :click-correct:&lt;img src="me.jpg"&gt;:endclick: &lt;/p&gt;

    :click-incorrect:&lt;p&gt;:endclick:This is my second paragraph
    :click-correct:&lt;a href="home.html"&gt;:endclick:Click here for my homepage&lt;/a&gt;
    &lt;/p&gt;
    &lt;/body&gt;
    &lt;/html&gt;