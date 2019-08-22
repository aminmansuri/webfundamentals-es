Cambiar la Disposición de tu Página
=====================================

Antes de continuar, es importante detenerse y pensar un poco sobre cómo el navegador representa el html en la ventana del navegador. A medida que el navegador lee cada etiqueta html, debe averiguar en qué parte de la página pertenece. En su mayor parte, el navegador fluye cada etiqueta de arriba a abajo y de izquierda a derecha. Como hemos mencionado, los elementos de bloque comienzan en una nueva línea, y los elementos en línea fluyen de izquierda a derecha, ajustándose al tamaño horizontal de la página o pasando a la siguiente línea. En esta sección consideraremos varias opciones CSS diferentes que tienen un impacto en el diseño de una página.

El Modelo de Caja de CSS
--------------------------

Todos los elementos HTML pueden considerarse simplemente como cuadros. De hecho, así es exactamente como el navegador piensa en ellos cuando comienza el proceso de renderizar la página. Al hacer el diseño y el diseño de la página web, es muy común escuchar a los diseñadores hablar sobre el modelo de caja CSS. La Figura 1 ilustra los diferentes componentes que entran en el modelo de caja.

.. figure:: Figures/box-model.gif

   Figura utilizada de acuerdo con la política de uso justo de w3schools

Las diferentes partes del modelo de caja se definen de la siguiente manera:

* Contenido: el contenido de texto o imagen real de una etiqueta html
* Relleno: el espacio entre el contenido y el borde.
* Borde: puede ser un borde real o invisible
* Margen: el espacio fuera del borde entre este cuadro y los cuadros al lado en cada dirección.

Probemos un ejemplo simple:

.. activecode:: css_boxmodel
   :language: html

   <html>
      <head>
         <style>
         section {
              width: 250px;
              background-color: green;
              padding: 25px;
              border: 10px solid blue;
              margin: 25px;
              }
         </style>
       </head>
   <body>

      <section>Hello World</section>
      <section id=b>Hello World</section>

   </body>
   </html>

Como un poco de revisión, agregue una regla al ejemplo anterior para que el margen para el segundo Hello world sea de 5px. ¿Qué te dice esto sobre cómo funcionan los márgenes?

El tamaño del área de contenido en sí también se puede controlar mediante las siguientes propiedades:

* altura
* Altura máxima
* altura mínima
* ancho
* anchura máxima
* ancho mínimo

Cada una de estas propiedades se puede especificar en términos de píxeles (px), puntos (pt) o como un porcentaje. Además, se puede usar la palabra clave auto, que es la predeterminada y permite al navegador determinar la altura y el ancho adecuados.


Cuando usa la altura y el ancho con un elemento **contenedor**, como uno de los elementos semánticos, es muy útil saber acerca de la propiedad de desbordamiento. ¿Qué sucede si establece una altura tan pequeña que el contenido no cabe? La propiedad `overflow <http://www.w3schools.com/cssref/pr_pos_overflow.asp>`_ le indica cómo manejar eso.

Aquí hay un ejemplo de activecode para que experimentes:

.. activecode:: css_overflow
   :language: html

   <html>
      <head>
         <style>
         section {
              width: 250px;
              background-color: green;
              padding: 25px;
              border: 10px solid blue;
              margin: 25px;
              height: 100px;
              }
         </style>
       </head>
   <body>

      <section>
      <p>Ea dolore do irure aliquip id qui dolor do in aliquip irure anim id. Adipisicing qui
       incididunt consectetur veniam cupidatat dolor. Aliquip irure labore elit ipsum officia non
       culpa consequat et voluptate. Officia nisi nostrud exercitation quis amet ipsum incididunt.
       Et incididunt eu laborum velit dolore laborum. Esse id mollit fugiat nostrud non ex occaecat
       culpa. Adipisicing quis excepteur voluptate commodo minim aliqua excepteur occaecat
       eu ipsum nisi duis amet. Duis proident fugiat velit elit esse cillum minim laborum elit.
      </p>

      </section>
   </body>
   </html>

Los valores posibles para la propiedad de desbordamiento son:

* visible
* oculto
* desplazamiento
* auto

Pruébelos en el ejemplo anterior y vea qué sucede.

.. admonition:: Greeking

   Quizás se esté preguntando sobre el uso de palabras latinas en el párrafo de ejemplo. Esta es una vieja tradición en la composición tipográfica, para usar un montón de palabras latinas, muchas de las oraciones comienzan con "Lorum Ipsum", por lo que a veces también se llama Lorum Ipusum. La idea es llenar el espacio con palabras que obviamente no tienen relación con la página web real. Esto ayuda a los revisores a centrarse en el estilo en lugar del contenido.


Display
-------

Con CSS puede tomar el control de cómo se presenta cada elemento en la página. Puede ocultar elementos, puede hacer que los elementos de bloque estén en línea y que los elementos en línea se bloqueen. Hay dos formas de controlar la visibilidad de un elemento. Puede ocultarlo por completo, como si no estuviera allí y no ocupara espacio en la página, o puede dejar el espacio en la página, pero no tendrá nada en él.

.. activecode:: css_disp1
   :language: html

   <html>
      <head>
         <style>
            h1.gone {
                background-color: #bbbbbb;
                display: none;
            }
         </style>
       </head>
   <body>

      <h1>Hello World One</h1>
      <h1 class="gone">Hello World Two</h1>
      <h1>Hello World Three</h1>
      <h1 class="gone">Hello World Four</h1>
      <h1>Hello World Five</h1>
   </body>
   </html>

Ahora cambie la regla y, en lugar de ``display:none`` cámbiela a ``visibility: hidden`` Observe que la visibilidad oculta reserva espacio en la página para el elemento pero no lo muestra. Mientras que la regla ``display: none`` eliminó cualquier rastro del elemento. Ahora cambie la regla a ``visibility: show`` para mostrar todos los elementos.

La propiedad de visualización también se puede utilizar para cambiar elementos de bloque en elementos en línea. Considere el siguiente ejemplo.

.. activecode:: css_disp2
   :language: html

   <html>
      <head>
         <style>
         </style>
       </head>
   <body>
      <p>There are 10 kinds of people in the world.
      <ol>
      <li>Those that know how to count in binary.</li>
      <li>Those that do not know how to count in binary</li>
      </ol>
      <p>When you have stopped laughing, add a CSS rule that changes the display
      property for the ``li`` element and sets its value to ``inline``. </p>
   </body>
   </html>


Esta técnica se usa a menudo en la barra de navegación para crear un "menú" de enlaces. Vea el ejercicio 5 en la sección de ejercicios para practicar con esto.

Floating
--------

La propiedad float de CSS nos permite empujar elementos HTML hacia la izquierda o hacia la derecha, para que otros elementos los envuelvan. Esto puede ser extremadamente útil para las imágenes, pero también será muy útil cuando comencemos a trabajar en diseños más complejos para nuestras páginas. Comencemos con un ejemplo simple.

.. activecode:: css_float1
   :language: html

   <html>
      <head>
         <style>
         </style>
       </head>
   <body>
   <p>the quick brown fox jumped over the lazy dog.  the quick brown fox jumped over the lazy dog.  the quick brown fox jumped over the lazy dog.  <img src="http://interactivepython.org/runestone/static/webfundamentals/_images/norse-logo.png" /> the quick brown fox jumped over the lazy dog. the quick brown fox jumped over the lazy dog. the quick brown fox jumped over the lazy dog.
   </body>
   </html>


Observe que el logotipo aparece justo en el medio del texto en su flujo en línea normal. Ahora, agregue una regla CSS para una etiqueta img que establezca la propiedad flotante a la izquierda. Luego cambie la regla para hacer flotar la imagen a la derecha.

A continuación, agreguemos una segunda copia del logotipo nórdico a la página copiando y pegando la imagen nuevamente.

A continuación, modifique el html y agregue una regla CSS para que un logotipo flote a la izquierda y el otro a la derecha.

La propiedad flotante también se puede aplicar a elementos de bloque. Esto hará que los elementos de bloque se comporten más como elementos en línea.

La propiedad clear se usa para deshacer los efectos del float.



Posicionamiento
----------------

Hay varias formas diferentes de afectar el posicionamiento de los elementos html dentro o fuera del flujo normal del diseño.

* estático
* fijo
* relativo
* absoluto

**Estático** es el valor de posicionamiento predeterminado para la propiedad de posición css. El valor estático simplemente le dice al navegador que coloque este elemento en el "flujo normal" del documento.

**Posicionamiento** fijo se mide contra el marco de la ventana del navegador. Los elementos con un valor de posición fijo no se mueven incluso cuando se desplaza el contenido de la ventana del navegador. La barra de navegación en la parte superior de esta página usa el valor de posición fija para que siempre esté visible. Debido a que los elementos fijos están fuera del flujo del documento, a veces pueden causar resultados inesperados con los que debe lidiar con cuidado.

Un elemento posicionado **relativamente** se mide con relación a su posición normal en el flujo. El uso de un valor de posición relativa le permite crear elementos que se superponen entre sí.

Un elemento **absoluto** se posiciona en relación con el primer elemento padre que tiene una posición que no es estática. Si no se encuentra dicho elemento, el bloque contenedor es la etiqueta ``html`` para todo el documento. Los elementos posicionados de manera absoluta se ubican fuera del flujo normal del documento.

Fixed
^^^^^

Veamos un ejemplo de cómo usar el posicionamiento fijo para crear un elemento que permanezca en la pantalla.

.. activecode:: css_pos1
   :language: html

   <html>
      <head>
         <style>
         #sticky {
            position: fixed;
            top: 0px;
            left: 5px
         }
         </style>
       </head>
   <body>
      <nav id="sticky">
          <p>There are 10 kinds of people in the world.</p>
      </nav>
      <ol>
      <li>Those that know how to count in binary.</li>
      <li>Those that do not know how to count in binary</li>
      <li>Those that know how to count in binary.</li>
      <li>Those that do not know how to count in binary</li>
      <li>Those that know how to count in binary.</li>
      <li>Those that do not know how to count in binary</li>
      <li>Those that know how to count in binary.</li>
      <li>Those that do not know how to count in binary</li>
      <li>Those that know how to count in binary.</li>
      <li>Those that do not know how to count in binary</li>
      <li>Those that know how to count in binary.</li>
      <li>Those that do not know how to count in binary</li>
      <li>Those that know how to count in binary.</li>
      <li>Those that do not know how to count in binary</li>
      <li>Those that know how to count in binary.</li>
      <li>Those that do not know how to count in binary</li>
      <li>Those that know how to count in binary.</li>
      <li>Those that do not know how to count in binary</li>
      <li>Those that know how to count in binary.</li>
      <li>Those that do not know how to count in binary</li>
      <li>Those that know how to count in binary.</li>
      <li>Those that do not know how to count in binary</li>
      </ol>
      <p>When you have stopped laughing, add a CSS rule that changes the display
      property for the ``li`` element and sets its value to ``inline``. </p>
   </body>
   </html>

Cuando ejecute el ejemplo anterior, notará que no está del todo bien. El texto se superpone y la página generalmente se ve fea. Los elementos se superponen porque el posicionamiento fijo saca el elemento de bloque de párrafo del flujo. Debido a que está fuera del flujo, el navegador muestra el ``ol`` como si fuera la primera cosa en la parte superior de la página.


Su desafío es arreglar el ejemplo para que la oración permanezca bien anclada en la parte superior, pero la lista ordenada comienza debajo de ella.

.. reveal:: css_pos_sol1

   Aquí hay una forma de resolver este problema. Agregue una regla para el ``ol`` que especifique un margen superior. Haga que el margen superior sea lo suficientemente grande como para que la lista comience debajo del primer párrafo. Es posible que deba experimentar un poco con algunos valores diferentes antes de encontrar uno que funcione bien. Ahora también debe agregar un poco de estilo a la navegación para darle un color de fondo y hacer que ocupe todo el ancho de la ventana.

Relative
^^^^^^^^

A continuación, veamos la posición relativa y cómo podemos usarla para hacer elementos superpuestos.

.. tome una imagen de una carta y haga un mazo de tres cartas apiladas.

Hagamos una pila de cartas usando la siguiente imagen:

.. image:: Figures/ace-of-hearts.gif

.. activecode:: css_pos2
   :language: html

   <html>
      <head>
         <style>
         img.card {
             height: 200px;
         }
         </style>
      </head>
   <body>
      <img id="a" class="card" src="http://interactivepython.org/runestone/static/webfundamentals/_images/ace-of-hearts.gif" />
      <img id="b" class="card" src="http://interactivepython.org/runestone/static/webfundamentals/_images/ace-of-hearts.gif" />
      <img id="c" class="card" src="http://interactivepython.org/runestone/static/webfundamentals/_images/ace-of-hearts.gif" />
   </body>
   </html>

Si ejecuta el ejemplo, verá las tres cartas alineadas una al lado de la otra. Como recordatorio, esto se debe a que:

1. las imágenes son elementos en línea y, por lo tanto, no crean un salto de línea.
2. El navegador presenta imágenes en línea de arriba a abajo y de izquierda a derecha.

Ahora usemos nuestras habilidades de posicionamiento para crear una pila. Modifique el ejemplo anterior para agregar la siguiente regla css:

.. code-block:: css

   img#b {
       position: relative;
       top: 20px;
       left: -100px;
   }

Genial, ahora hemos hecho que la segunda carta parezca estar encima de la primera. Tenga en cuenta que aunque hemos movido la segunda imagen, la posición de la tercera imagen no cambia. Esto se debe a que el espacio todavía está reservado para la segunda imagen en su posición media, lo estamos moviendo manualmente en relación con el lugar donde normalmente estaría en el flujo. Entonces, un posicionamiento relativo funciona dentro del flujo del documento. Agregue una regla para la tercera imagen para agregarla a la pila.

.. reveal:: css_stack

   .. code-block:: css

      img#c {
          position: relative;
          top: 40px;
          left: -200px;
      }

.. admonition:: Coordinates

   Sin duda ha notado que estamos utilizando los valores superior e izquierdo para posicionar nuestro cuadro. Este cuadro se coloca dentro de la ventana donde la coordenada 0,0 está en la esquina superior izquierda. La coordenada X o primera se agranda a medida que se mueve hacia la derecha a través de la ventana, y la coordenada segunda o Y se agranda al moverse hacia abajo de la pantalla. Esto requiere un pequeño ajuste, ya que es diferente de lo que aprendiste en la clase de matemáticas.

   
Ahora, ¿qué pasa con los elementos que vienen después de elementos relativamente posicionados? Si agrega un párrafo después de las imágenes, ¿espera que el texto se cubra o fluya debajo de todas las tarjetas?

Otra cosa importante a tener en cuenta es que la tarjeta 2 parece estar apilada encima de la tarjeta 1, y la tarjeta tres parece estar apilada encima de las tarjetas 1 y 2. Esto es porque los elementos que aparecen más adelante en el documento aparecen naturalmente encima de los elementos. que vienen antes que ellos

Si queremos cambiar eso y hacer que parezca que la tarjeta 1 está encima de la tarjeta 2 y la tarjeta 2 está encima de la tarjeta 3, podemos usar la propiedad css ``z-index`` para colocar los elementos. los elementos que tienen un índice z más grande aparecerán encima de los elementos con un índice z más bajo. Por defecto, todos los elementos tienen un z-idex de cero. Entonces, para cambiar el orden de la pila, necesitaremos modificar las reglas para las imágenes b y c. Agregue una propiedad z-image a las reglas ``img#b`` e ``img#c`` dando a b un z-index de -1 y c un índice z de -2.


.. admonition:: Advanced Topic: Transformation

   CSS nos brinda la capacidad de ser realmente elegantes y transformar cualquier elemento al rotar o escalar. Podemos hacer que nuestra pila de cartas se parezca mucho más a una mano de cartas explorando la propiedad `transform <http://www.w3schools.com/cssref/css3_pr_transform.asp>`_. De hecho, la propiedad de transformación aún es tan nueva que tiene diferentes nombres en diferentes navegadores. Para Chrome, Safari, querrá usar la propiedad ``-webkit-transform``, mientras que en Firefox puede usar ``transform``. Si usas Explorer, necesitarás usar ``-ms-transform``. De hecho, para escribir su página para trabajar en cualquier lugar, ¡debería especificar los tres!
   
Absolute
--------

¡Los elementos posicionados absolutamente son absolutos, pero relativos a su contenedor! La regla oficial es que los artículos absolutos se colocan utilizando la esquina superior izquierda del primer contenedor no estático como origen. Si no hay un contenedor no estático, se usará la etiqueta html y el origen será la esquina superior izquierda de la página.

.. activecode:: css_pos3
   :language: html

   <html>
      <head>
         <style>
             main {
                 position: relative;
             }
             img.card {
                 height: 200px;
             }
             img#a {
                 position: absolute;
                 top: 10px;
                 left: 50px;
             }
             img#b {
                 position: absolute;
                 top: 10px;
                 left: 50px;
             }
         </style>
      </head>
   <body>
   <main>
      <img id="a" class="card" src="http://interactivepython.org/runestone/static/webfundamentals/_images/ace-of-hearts.gif" />
      <img id="b" class="card" src="http://interactivepython.org/runestone/static/webfundamentals/_images/ace-of-hearts.gif" />
      
   </main>
   </body>
   </html>

OK, ¿qué pasó con la segunda carta? ¿Cómo puedes hacer una pila que se parezca a la pila de nuestro elemento relativamente posicionado? ¿Qué sucede si agrega un h1 frente a la etiqueta principal?






Disposicón de Página Completa
------------------------------


.. activecode:: css_layout1
   :language: html

    <html>
        <head>
            <title>Home</title>
            <style>
            header {
                position: fixed;
                background-color: #bbbbbb;
                top: 0px;
                left: 0px;
                width: 100%;
                height: 20px;
            }
            nav {
                margin-top: 20px;
                margin-bottom: 0px;
                background-color: green;
            }
            nav li {
               display: inline;
            }
            section {
                float: left;
                width: 20%;
                height: 500px;
                background-color: blue;
                color: white;
            }
            aside {
                float: left;
                width: 80%;
                height: 500px;
                background-color: red;
            }
            footer {
                clear: both;
                background-color: yellow;
            }
            body {
                background-color: black;
                margin: 0px;
            }
            </style>

        </head>
        <body>
            <header>
                A header that stays stuck to the top.
            </header>
            <nav>
                <ul>
                <li>About</li>
                <li>Papers</li>
                <li>Donate</li>
                </ul>
            </nav>
            <section>
                This would be a good place for a table of contents
            </section>
            <aside>
                This is the main content area
                <img src="http://interactivepython.org/runestone/static/webfundamentals/_images/img_sem_elements.gif" />
            </aside>
            <footer>
                Copyright Area, Contact Us.
            </footer>
        </body>
    </html>


Esto se ve bastante bien. Casi coincide con la imagen en el área lateral. Este es un diseño bastante típico para una página de buena calidad, y puede usarlo como plantilla para su propia página de inicio. Sin embargo, le falta el área del artículo, y hay una banda negra fea entre el navegador y la parte superior de la sección a un lado. Vea si puede hacer lo siguiente:

1. Retire la banda negra. Sugerencia: Una buena manera de averiguar por qué las cosas se ven como las ves puedes usar la función "Inspeccionar elemento" de su navegador. Si hace clic con el botón derecho en un área que le interesa, podrá ver todas las reglas CSS, incluidas las reglas de estilo predeterminadas que afectan a un elemento en particular.

2. Agregue un área de artículo como se muestra en la imagen. Dale un fondo morado. Mientras intenta hacer que esta área coincida con la imagen, piense en los efectos de las diversas cosas que puede probar.
