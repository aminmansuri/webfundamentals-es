Introducción a CSS
===================

CSS viene de Cascading Style Sheets que significa hojas de estilo en cascada. Las hojas de estilo definen cómo mostrar su código html. Este no fue siempre el caso. En HTML 3, los diseñadores del lenguaje agregaron etiquetas como fuente y color. Esto fue excelente para empresas como Microsoft, donde se podía exportar su documento de Word como html, pero creó una pesadilla para los desarrolladores de sitios grandes que no se desarrollaron utilizando herramientas WYSIWYG, e hizo que el html fuera completamente ilegible. Entonces, en HTML 4.0 se introdujo CSS para solucionar el problema que creamos para nosotros mismos.

CSS define cómo debería verse el html, y lo hace usando un conjunto de reglas. Todos estamos acostumbrados a seguir ciertas reglas en la vida diaria: **Si** está lloviendo, **entonces** tome su paraguas. **Si** la luz es roja, **entonces** deténgase en el semáforo. En términos html podríamos decir, **si** la etiqueta es un ``h1``, **entonces **colorea de azul y establece el tamaño de la fuente en 28 puntos**.

Sintaxis CSS
-------------

Para informarle a la computadora sobre estas reglas if/then, necesitamos una sintaxis consistente. La sintaxis para CSS tiene dos partes, un selector y una declaración.

.. code-block:: css

   selector {
       declaration;
       declaration;
       }

La declaración en sí consta de dos partes: una propiedad y un valor. Hay muchísimas propiedades en CSS y veremos muchas de ellas, pero por ahora, solo piense en la propiedad como algo así como color, tamaño de fuente, familia de fuentes, etc.

Los selectores pueden ser tan simples como un nombre de etiqueta o un patrón muy complejo para que coincida. Comenzaremos con algunos selectores muy simples y avanzaremos hasta los más complejos.

Sin más complicaciones, veamos una regla CSS para colorear las etiquetas h1 de azul y cambiar su fuente a 28 puntos.

.. code-block:: css

   h1 {
       color: blue;
       font-size: 28pt;
   }


Incluyendo CSS en su página
-----------------------------

Hay tres formas de incluir CSS en su documento html.

* Puede agregar un atributo de estilo a una etiqueta. ¡Esto no debe usarse muy a menudo, o más bien nunca!
* Puede incrustar su CSS en su archivo dentro de una etiqueta de ``style``. Utilizaremos este método en este libro por conveniencia.
* Puede poner todo su CSS en un archivo de estilo separado e incluir el archivo de estilo en su HTML. Esta es la forma preferida de hacerlo porque logra la mayor cantidad de separación entre el contenido y cómo se ve el contenido.

Veamos ahora un ejemplo completo:

.. activecode:: css_rule_1
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


Hay varias cosas a tener en cuenta sobre el ejemplo anterior. Primero, el selector ``h1`` coincide con todas las etiquetas h1 en el documento. Pero no coincide con las etiquetas ``h2`` o ``p``. Si desea cambiar el estilo del párrafo, debe agregar otra regla. Probémoslo: agregue una regla a la etiqueta de estilo que colorea de verde el texto del párrafo. Luego haga otra regla que haga que el tamaño de la etiqueta h2 sea de 16 puntos y amarillo.

Una cosa a tener cuidado es recordar los punto y coma después de los valores. Si olvida un punto y coma, su regla no funcionará.


Usar un archivo css separado es la forma más preferida de organizar tu CSS. Esto le permite usar el mismo estilo en varias páginas web, y en una configuración grupal facilita que una persona trabaje en el estilo mientras que otra se enfoca en el contenido. Las hojas de estilo CSS se incluyen en una página web mediante el uso de la etiqueta ``link`` en la sección ``head`` de su página de la siguiente manera:

.. code-block:: html

   <link rel="stylesheet" href="mystyle.css" type="text/css">

Cascada
---------

Dado que puede agregar información de estilo sobre una etiqueta en cualquiera de los tres lugares, ¿cómo se resuelve el estilo si diferentes fuentes proporcionan información contradictoria?

Las reglas predeterminadas del navegador se combinan con las reglas de una hoja de estilo externa y las reglas contenidas en las etiquetas de estilo de la página. Si hay un conflicto, entonces gana la etiqueta de estilo interno. Estas reglas se combinan con cualquier información de estilo contenida en un atributo de estilo. Si el atributo de estilo entra en conflicto con cualquier información anterior, gana.
