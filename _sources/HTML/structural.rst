Etiquetas HTML semánticas
===========================

Algunas etiquetas en HTML están diseñadas para que las use al crear una estructura lógica para su página. Como probablemente hayas notado, muchos sitios tienen una barra de navegación en el encabezado y tienen información sobre la página en un pie de página. Muchas páginas web tienen barras laterales y, por supuesto, los blogs y muchos sitios de noticias están divididos en artículos. Los sitios web académicos se dividen en partes y secciones.

Probablemente también hayas notado que es bastante fácil distinguir las diferentes partes de una página web porque tienen un aspecto distinto. Para dar a diferentes secciones diferentes miradas, necesitamos proporcionar alguna estructura dentro de nuestro marcado. Esto se realiza mediante el uso de etiquetas estructurales de la siguiente manera:


* article
* aside
* details
* figcaption
* figure
* footer
* header
* main
* mark
* nav
* section
* summary
* time

¡Estas etiquetas son todas etiquetas de nivel de bloque, pero aparte de eso, no tienen impacto en el aspecto de la página sin el uso de CSS! La Figura 1 ilustra cuántas de estas etiquetas se usan para crear estructura en una página.

.. figure:: Figures/img_sem_elements.gif

   Figura utilizada de acuerdo con la política educativa de uso justo de w3schools.com

Veamos un ejemplo que usa algunas de estas etiquetas:

.. activecode:: sem_tags
   :language: html
   
   <html>
   <body>
   <header>
   <p>Este es el texto en el encabezado</p>
   </header>
   <aside>
   <p>Este es un comentario secundario</p>
   </aside>
   <article>
   <p>Este es un texto para un artículo.</p>
   </article>
   <p>Tenga en cuenta que no hay nada especial sobre la ubicación de ninguno de estos textos. Sin CSS, las etiquetas semánticas simplemente dividen el documento lógicamente</p>
   </body>
   </html>


.. admonition:: Nota histórica

    Todas las etiquetas mencionadas anteriormente se agregaron al estándar HTML5. Antes de HTML5 solo había dos de estas etiquetas estructurales invisibles. Verá muchos ejemplos del uso de estas etiquetas:
   
   * div
   * span
   
   Estas etiquetas sirvieron para el mismo propósito, generalmente mediante el uso de un atributo de identificación o clase para indicar su propósito semántico.
   
   
