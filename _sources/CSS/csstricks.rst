Trucos en CSS
===============

**BORRADOR** Este capítulo es un trabajo en progreso.

CSS se utiliza para todo tipo de efectos especiales que hacen que las páginas web se vean bien. En esta sección investigaremos algunos
de ellos.

Hover
-----

.. activecode:: hover1
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

            nav li:hover {
               background-color: lightblue;
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


* Agregue un enlace con una pseudoclase:hover al ejemplo anterior.
* Agregue un ``h2`` con el título más información. Debajo del h2, agregue un contenedor ``principal`` con un párrafo. El elemento de detalles debe estar inicialmente oculto y solo aparecerá cuando pase el cursor sobre el h2. Sugerencia: el carácter ``~`` le permite escribir un selector que coincida con un hermano.


La etiqueta details es una etiqueta semántica que tiene algunas propiedades muy buenas similares a nuestro experimento anterior.

.. activecode:: html_details
   :language: html

   <p>The details tag contains a summary tag and the details.  The summary is displayed with a triangle next to it.  The details are initially hidden but then displayed when the triangle is clicked on.</p>

   <details>
       <summary>Show me More</summary>
       <p>This text will only show when the triangle is clicked on</p>
   </details>



Animaciones
-------------

Usando la palabra clave ``@keyframes`` podemos crear una animación y luego aplicar esa animación a otros elementos CSS. Mira el siguiente ejemplo
eso anima el color de fondo. Con fotogramas clave podemos especificar una condición inicial y final utilizando
``from`` y ``to`` o podemos especificar varios puntos a lo largo de la animación usando ``xx%``.

La animación debería funcionar como se muestra en todos los navegadores modernos. Safari versión 8 y anteriores requerirán que se agregue el prefijo ``-webkit-``.


.. activecode:: animation1
   :language: html

   <html>
   <head>
     <style>
     @keyframes example {
            from {background-color: red;}
            to {background-color: yellow;}
     }

     div {
         width: 100px;
         height: 100px;
         background-color: red;
         animation-name: example;
         animation-duration: 4s;
     }
     </style>
   </head>
   <body>
   <div>
   <h1>Hello World</h1>
   </div>
   </body>
   </html>


Experimente con lo siguiente:

* ``animation-delay: 2s;``
* ``animation-iteration-count: infinite;``
* ``animation-direction: alternate;``

.. code-block:: css

    @keyframes spin {
        from {
            transform: rotate(0deg);
        } to {
            transform: rotate(360deg);
        }
    }


.. code-block:: css

   @keyframes moveit {
       from {
           top: 0px;
           left: 0px;
       }
       to {
           top: 300px;
           left: 300px;
       }
   }

* Agregue una imagen a la imagen y haga que gire infinitamente.
* intenta crear una animación a escala
* Use ``animation-fill-mode: forwards;`` para mantener el elemento en la posición final.

