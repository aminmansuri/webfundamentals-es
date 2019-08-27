Etiquetas HTML avanzadas
========================


Listas desordenadas
-------------------

.. activecode:: advhtml_ul
   :language: html

   <ul>
   <li>Esta es una lista desordenada</li>
   <li> <code>li</code> tags come between two <code>ul</code> tags
   </ul>


Listas ordenadas
----------------

.. activecode:: advhtml_ol
   :language: html

   <ol>
   <li>This is an ordered list</li>
   <li>The <code>li</code> tags come between two <code>ol</code> tags
   <li>Notice that the <code>li</code> tags are used for both.
   </ol>

La etiqueta ``ol`` también puede tener un atributo de tipo. El atributo type puede ser uno de los siguientes valores

* 1 Esto hará que la lista se numere con números
* A Esto hará que la lista se ordene con letras mayúsculas
* a Esto hará que la lista se ordene con letras minúsculas
* I Esto hará que la lista se ordene con números romanos en mayúscula
* i Esto hará que la lista se ordene con números romanos en minúscula

Inténtalo tú mismo.

Descripción Listas
--------------------

.. activecode:: advhtml_dl
   :language: html

   <dl>
   <dt>Description list</dt><dd>A list for defining terms</dd>
   <dt>dt</dt><dd>The <code>dt</code> tags are for the term</dd>
   <dt>dd</dt><dd>The <code>dd</code> tags are for the description</dd>
   </dl>

Listas de anidamiento
-------------------------

Las listas pueden estar dentro de otras listas. También. Esto es muy cierto para la mayoría de las etiquetas HTML.

.. activecode:: advhtml_nested
   :language: html

   <ol>
   <li>Esta es una lista ordenada</li>
   <li>Las etiquetas <code>li</code> se encuentran entre dos etiquetas <code>ol</code>
   <li>Observe que las etiquetas <code>li</code> se usan para ambos.
   <ul>
   <li>Esta es una lista desordenada</li>
   <li>Las etiquetas <code>li</code> se encuentran entre dos <code>ul</code> etiquetas</li>
   </ul>
   <li>Puede mezclar y combinar listas como esta tan profundamente como desee.</li>
   </ol>


Tablas
------

Las tablas tienen muchos usos, puede usarlas para organizar datos como lo haría normalmente en un informe donde tiene filas y columnas de números u otra información, pero también puede usar tablas de forma invisible para influir en cómo se muestra su página. En los primeros días de html, era común usar una tabla para crear un diseño de página de dos columnas. Todavía podemos hacer eso, pero ahora es **mucho más aceptable** usar CSS para ese propósito.

Aquí hay un ejemplo completo que ilustra el uso de las siguientes etiquetas específicas de la tabla

* table  -- esta es la etiqueta principal para una tabla
* tr  -- cada fila de una tabla comienza con una etiqueta tr
* td -- cada columna de una fila está delineada por una etiqueta ``td``
* th -- Puede usar la etiqueta ``th`` en lugar de la etiqueta ``td`` en la primera fila para hacer encabezados


.. activecode:: advhtml_table
   :language: html

    <table width='100%' border=1px cellspacing=0>
    <caption>Table of Scores</caption>
    <tr>
    	<th>Number</th>
    	<th>First Name</th>
    	<th>Last Name</th>
    	<th>Points</th>
    </tr>
    <tr>
    	<td>1</td>
    	<td>Russell</td>
    	<td>Jackson</td>
    	<td>94</td>
    </tr>
    <tr>
    	<td>2</td>
    	<td>John</td>
    	<td>Deere</td>
    	<td>80</td>
    </tr>
    <tr>
    	<td>3</td>
    	<td>Nikola</td>
    	<td>Tesla</td>
    	<td>100</td>
    </tr>
    <tr>
    	<td>4</td>
    	<td>Richard</td>
    	<td>Smith</td>
    	<td>50</td>
    </tr>
    </table>

Hay muchos atributos que puede usar con las diversas etiquetas de tabla.

* ``table``
    * width - puede especificar un ancho como porcentaje o como número de píxeles. Este atributo es útil en este momento, pero no se recomienda su uso, ya que es mejor usar CSS para controlar el aspecto de su tabla. Decimos que este atributo está **en desuso**
    * border - puede agregar bordes a sus tablas como en el ejemplo anterior, pero esta etiqueta también está en desuso.
    * El espacio entre las celdas de la tabla. También en desuso.

* ``td``
    * colspan  -- si tiene una tabla en particular donde necesita una columna extra ancha en algunas filas, puede hacer que una celda de su tabla abarque más de una columna usando el atributo colspan. Su valor es el número de columnas.

* ``tr``
    * rowspan -- si tiene una tabla en particular donde necesita una columna para abarcar varias filas, puede hacer que una celda de su tabla abarque más de una fila utilizando el atributo rowspan. Su valor es el número de filas.


Experimenta con table. ¿Qué tipo de etiquetas puedes incluir dentro de cada ``td``? ¿Puedes hacer una table de otro table?

.. Ejercicio haga una tabla de dos columnas con una lista en cada columna

.. Ejercicio hacer una tabla que se parece a Nombre | nombre luego dos filas llamadas Teléfono con dos columnas después de la celda y el número seguidos en la siguiente línea por oficina y el número. esto combinará rowpan y colspan en un proyecto.


Audio
-----

Incrustar audio en su página web le permite vincular a varios archivos que contienen música o voz. La etiqueta de audio tiene el siguiente aspecto:

.. code-block:: html

    <audio controls>
        <source src="horse.ogg" type="audio/ogg">
        <source src="horse.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>

El atributo ``controls`` proporciona botones de inicio/parada/avance rápido/rebobinado para el oyente. Las etiquetas ``source`` dentro de la etiqueta ``audio`` le permiten proporcionar varios formatos de audio diferentes. Esto se debe a que diferentes navegadores admiten diferentes tipos de audio. El navegador recorrerá la lista, en orden, hasta que encuentre un formato que comprenda, o de lo contrario, reemplazará el controlador con el mensaje al final.

Video
-----

Incrustar un video en su página web le permite vincular a varios archivos que contienen películas.

.. code-block:: html

    <video height=312 width= 540 controls>
        <source src="movie.mp4" type="video/mp4">
        <source src="movie.ogg" type="video/ogg">
        Your browser does not support the video element.
    </video>

El atributo ``controls`` proporciona botones de inicio/parada/avance rápido/rebobinado para el oyente. Las etiquetas ``source`` dentro de la etiqueta ``video`` le permiten proporcionar varios formatos de video diferentes. Esto se debe a que diferentes navegadores admiten diferentes tipos de video. El navegador recorrerá la lista, en orden, hasta que encuentre un formato que comprenda, o de lo contrario, reemplazará el controlador con el mensaje al final.



IFrames
-------

IFrames le permite incrustar una página web dentro de otra página web. Los ejemplos de active code en este libro usan un iframe para permitirle experimentar con el html, creando una página dentro de una página.
