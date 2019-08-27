El lenguaje de marcado de hipertexto
=======================================

Como notamos en el capítulo anterior, HTML es el lenguaje de la web para expresar contenido. Pero antes de sumergirnos en los detalles de HTML, veamos qué entendemos por lenguaje de marcado en general. Un lenguaje de marcado es un lenguaje que **anota** el texto para que la computadora pueda manipularlo con algún propósito. La mayoría de los lenguajes de marcado son legibles por humanos y están diseñados para escribirse con un editor de texto sin formato en lugar de un procesador de textos elegante como Microsoft Word.

Este libro está escrito usando un lenguaje de marcado llamado `restructuredText <//http://sphinx-doc.org/rest.html>`_ restructuredText es similar a otro lenguaje de marcado muy popular llamado `Markdown <http://daringfireball.net/projects/markdown/syntax>`_.  Ambos lenguajes están diseñados para que los humanos puedan leerlos fácilmente y, sin embargo, se traducen fácilmente a nuestro lenguaje de elección para esta clase, HTML. Ahora conoce tres lenguajes de marcado:

* HTML
* Markdown
* restructuredText

El marcado de restructutedText para el contenido de este capítulo hasta ahora se ve así:

.. code-block:: rst

   El lenguaje de marcado de hipertexto
   =====================================

   Como notamos en el capítulo anterior, HTML es el lenguaje de la web para expresar contenido. Pero antes de sumergirnos en los detalles de HTML, veamos qué entendemos por lenguaje de marcado en general. Un lenguaje de marcado es un lenguaje que **anota** el texto para que la computadora pueda manipularlo con algún propósito. La mayoría de los lenguajes de marcado son legibles por humanos y están diseñados para escribirse con un editor de texto sin formato en lugar de un procesador de textos elegante como Microsoft Word.

   Este libro está escrito usando un lenguaje de marcado llamado `restructuredText <//http://sphinx-doc.org/rest.html>`_ restructuredText es similar a otro lenguaje de marcado muy popular llamado `Markdown <http://daringfireball.net/projects/markdown/syntax>`_.  Ambos lenguajes están diseñados para que los humanos puedan leerlos fácilmente y, sin embargo, se traducen fácilmente a nuestro lenguaje de elección para esta clase, HTML. Ahora conoce tres lenguajes de marcado:

   * HTML
   * Markdown
   * restructuredText

   El marcado de restructutedText para el contenido de este capítulo hasta ahora se ve así:
   

Las anotaciones en el restructuredText son bastante discretas, y en realidad se suman a la legibilidad del texto plano en la mayoría de los casos. Por ejemplo, el ``===`` debajo del título de este capítulo indica que es, de hecho, un título o encabezado. Los párrafos regulares no requieren anotaciones adicionales. Para hacer algo audaz, lo rodeas de dos asteriscos. Si desea hacer una lista de viñetas, simplemente comience la línea con un asterisco.

La mayoría de los documentos tienen un conjunto de elementos razonablemente limitado que incluye lo siguiente:

* Párrafos
* Título
* Encabezados y subtítulos y subtítulos
* listas de viñetas
* listas numeradas
* tablas de datos
* figuras o imágenes
* texto en negrita o cursiva
* encabezados de página
* pies de página

A medida que aprendemos HTML, es importante tener en cuenta que el trabajo de html es estructurar el documento y proporcionar contenido. Nos preocuparemos por hacer que las cosas se vean bonitas hasta que lleguemos a CSS.

HTML utiliza un conjunto de etiquetas para anotar (marcar) el documento. Todas las etiquetas tienen el siguiente aspecto: ``<nombre de etiqueta>`` y están equilibradas para que al final del contenido de esa etiqueta haya ``</ nombre de etiqueta>``. Observe que la etiqueta de cierre contiene una barra diagonal al principio para diferenciarse de una etiqueta de apertura.

Un documento HTML solo contiene una serie de estas etiquetas equilibradas. Veamos un pequeño documento que se ve así:

Mi Primer Encabezado
---------------------

Un simple párrafo de texto.

Otro párrafo de texto.


El HTML para este documento es el siguiente:

.. activecode:: html_1
   :language: html
   
   <html>
       <head>
           <title>Test Page</title>
       </head>
       <body>
           <h1>Mi Primer Encabezado</h1>
           <p>Un simple párrafo de texto.</p>
           <p>Otro párrafo de texto.</p>
       </body>
   </html>



Si haces clic en el botón Ejecutar, verás el HTML en el ejemplo anterior en una ventana de salida especial que imita su navegador. Intenta cambiar el texto de uno de los párrafos y haz clic en ejecutar nuevamente. Intenta cambiar la etiqueta ``h1`` a ``h2``. No olvides cambiar las etiquetas de apertura y cierre. He sangrado el HTML para que puedas ver las etiquetas de apertura y cierre más claramente. Un navegador web no se preocupa por la sangría ni un poco, puede deshacerse de toda la sangría o poner todo en una línea y la página se verá igual.


Antes de continuar para hablar más sobre etiquetas HTML específicas, es útil pensar sobre la página que se produce y la estructura de la página. Tienes una idea de la estructura de la sangría que he proporcionado, pero es útil mirar esto desde otra perspectiva. La Figura 2 ilustra una "vista de árbol" de una página HTML.

.. figure:: Figures/tree.svg

   Figura 2. Una vista de árbol de la página html

Este árbol está invertido con respecto a la forma en que generalmente pensamos en un árbol, pero en informática colocamos la "raíz" del árbol en la parte superior. Entonces, la raíz de este árbol es la etiqueta html. La etiqueta html tiene dos **hijos**, la cabeza y el cuerpo. La cabeza tiene un hijo, que es la etiqueta del título. La etiqueta html es el **padre** de la etiqueta principal. El cuerpo tiene tres hijos, la etiqueta h1 y dos etiquetas p. También puede resultarle útil pensar en esto como un esquema, aunque tendría que girar la imagen 90 grados en sentido antihorario para obtener la orientación en forma de esquema. Veremos cómo esta estructura de árbol de una página html es útil más adelante cuando comencemos a usar CSS y Javascript.




