El Proyecto del Menú Desplegable
=================================

En esta sección, realizaremos un proyecto completo para crear algunos menús desplegables de navegación con submenús. Este no es un proyecto simple, por lo que seguiremos las buenas prácticas de programación y desarrollaremos nuestra solución de forma iterativa.

Primer Paso
------------

Antes de agregar cualquier regla CSS, vamos a tener la estructura del menú y algunos contenidos de la página en su lugar. Esto no se verá bonito, pero nos dará un punto de partida. Esto es casi siempre una buena práctica en el desarrollo web. Primero, coloque la estructura básica en su lugar, luego realice progresivamente algunas mejoras. La razón para hacerlo de esta manera es simple: si agrega pequeñas cosas de una en una, es fácil saber cuándo hace algo mal, y automáticamente sabe que fue lo último que hizo que causó el problema.

Tenemos dos áreas semánticas principales en nuestra página, el contenido principal del menú de navegación. Los separaremos colocando el menú de navegación dentro de una etiqueta de navegación y los contenidos principales dentro de una etiqueta principal.

.. activecode:: menu_1
   :language: html
   
   <html>
   <head>
   <title>SubMenus</title>
   <style type='text/css'>

   </style>
   </head>
   <body>

   <h1>Fundamentals of Web Programming</h1>

   <nav>
   <ul >
    <li><a href='/'>Home</a></li>
    <li><a href='#'>Syllabus</a>
     <ul>
      <li><a href='#'>Text Book</a></li>
      <li><a href='#'>Office Hours</a></li>
      <li><a href='#'>Grading Policy</a></li>
      <li><a href='#'>Learning Goals</a></li>
     </ul>
    </li>
    <li><a href='#'>Resources</a></li>
    <li><a href='#'>Publications</a>
     <ul>
      <li><a href='#'>Articles</a></li>
      <li><a href='#'>Tutorials</a>
       <ul>
        <li><a href='#'>HTML</a></li>
        <li><a href='#'>CSS</a></li>
        <li><a href='#'>SVG</a></li>
        <li><a href='#'>XML</a></li>
       </ul>
      </li>
      <li><a href='#'>Assignments</a></li>
     </ul>
    </li>
    <li><a href='#'>Contact</a></li>
   </ul>
   </nav>

   <main>
   <p>
   Lorem ipsum, dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.
    Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.
   Lorem ipsum, dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.
   Lorem ipsum, dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.
   </p>
   </main>
   </body>
   </html>



Segundo Paso
--------------

Ahora que el contenido está en su lugar, establezcamos algunos colores de fondo para las cosas y ubiquemos nuestros elementos semánticos. En este caso, queremos que nuestro menú de navegación esté en el lado izquierdo de la página, con el contenido principal a la derecha.

Podemos posicionarnos en el navegador a la izquierda y tener el principal justo a la derecha usando la propiedad ``float: left``. Tenga en cuenta que establecemos nuestro ancho para que el elemento de navegación sea ``7em``, usar un ``em`` como unidad de medida en este caso es una buena idea porque escalará el ancho de nuestra barra de navegación si cambiamos El tamaño de nuestra fuente. Intente configurar el tamaño de fuente en la etiqueta del cuerpo y observe que todo crece proporcionalmente.

Por ahora, le damos al navegador su propio color de fondo, solo para facilitar la diferenciación entre el área que pertenece al navegador y el área que pertenece al principal.

.. activecode:: menu_2
   :language: html
   
   <html>
   <head>
   <title>SubMenus</title>
   <style type='text/css'>
   body {
       background: #EEE; 
       color: #000;
   }

   h1 {
       color: #AAA; 
       border-bottom: 1px solid; 
       margin-bottom: 0;
   }

   main {
       color: #CCC; 
       margin-left: 7em; 
       padding: 1px 0 1px 5%;
       border-left: 1px solid;
   }

   nav {
       float: left;
       width: 7em;
       background: #FDD;
   }
   </style>
   </head>
   <body>

   <h1>Fundamentals of Web Programming</h1>

   <nav>
   <ul>
    <li><a href='/'>Home</a></li>
    <li><a href='#'>Syllabus</a>
     <ul>
      <li><a href='#'>Text Book</a></li>
      <li><a href='#'>Office Hours</a></li>
      <li><a href='#'>Grading Policy</a></li>
      <li><a href='#'>Learning Goals</a></li>
     </ul>
    </li>
    <li><a href='#'>Resources</a></li>
    <li><a href='#'>Publications</a>
     <ul>
      <li><a href='#'>Articles</a></li>
      <li><a href='#'>Tutorials</a>
       <ul>
        <li><a href='#'>HTML</a></li>
        <li><a href='#'>CSS</a></li>
        <li><a href='#'>SVG</a></li>
        <li><a href='#'>XML</a></li>
       </ul>
      </li>
      <li><a href='#'>Assignments</a></li>
     </ul>
    </li>
    <li><a href='#'>Contact</a></li>
   </ul>
   </nav>

   <main>
   <p>
   Lorem ipsum, dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.
    Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.
   Lorem ipsum, dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.
   Lorem ipsum, dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.

   </p>
   </main>
   </body>
   </html>
   

Tercer Paso
-------------

A continuación, cambiemos nuestra sangría de las sublistas usando las siguientes tres reglas:

.. code-block:: css

   nav ul {
        margin: 0; 
        padding: 0; 
        width: 7em; 
        background: white;
        border: 1px solid;
   }

   nav li {
        position: relative;
        list-style: none; 
        margin: 0;
        border-bottom: 1px solid #CCC;
   }

   nav ul ul {
       position: absolute;
       top: 0;
       left: 7em;
       display: block;
   }
   
Establecemos el margen de los uls dentro del elemento de navegación (nav ul) para que tenga un margen de 0 porque por defecto tienen un margen distinto de cero, lo que hará que nuestro posicionamiento sea más difícil más adelante. Lo mismo ocurre con el relleno. También establecemos el fondo en blanco, y le damos al borde un pequeño borde. Establecer la lista sytle en none elimina las viñetas.

Observe que agregamos dos propiedades de posición. Los elementos ``nav li`` están posicionados relativamente, pero no cambiamos la propiedad superior o izquierda. Esto es simplemente en preparación para la siguiente regla ``nav ul ul`` que posiciona los submenús usando mediciones absolutas. Podemos usar absoluto aquí porque los ul en cuestión serán todos hijos de li que se han posicionado relativamente. Recuerde que la regla para usar la posición absoluta es que la posición absoluta es relativa al primer contenedor que no está posicionado estáticamente. O bien, la etiqueta html si no se encuentra una etiqueta no estática.

.. activecode:: menu_3
   :language: html
   
   <html>
   <head>
   <title>SubMenus</title>
   <style type='text/css'>
   body {
       background: #EEE; 
       color: #000;
   }

   h1 {
       color: #AAA; 
       border-bottom: 1px solid; 
       margin-bottom: 0;
   }

   main {
       color: #CCC; 
       margin-left: 7em; 
       padding: 1px 0 1px 5%;
       border-left: 1px solid;
   }

   nav {
       float: left;
       width: 7em;
       background: #FDD;
   }

   nav ul {
        margin: 0; 
        padding: 0; 
        width: 7em; 
        background: white;
        border: 1px solid;
   }

   nav li {
        position: relative;
        list-style: none; 
        margin: 0;
        border-bottom: 1px solid #CCC;
   }

   nav ul ul {
       position: absolute;
       top: 0;
       left: 7em;
       display: block;
   }
   
   </style>
   </head>
   <body>

   <h1>Fundamentals of Web Programming</h1>

   <nav>
   <ul >
    <li><a href='/'>Home</a></li>
    <li><a href='#'>Syllabus</a>
     <ul>
      <li><a href='#'>Text Book</a></li>
      <li><a href='#'>Office Hours</a></li>
      <li><a href='#'>Grading Policy</a></li>
      <li><a href='#'>Learning Goals</a></li>
     </ul>
    </li>
    <li><a href='#'>Resources</a></li>
    <li><a href='#'>Publications</a>
     <ul>
      <li><a href='#'>Articles</a></li>
      <li><a href='#'>Tutorials</a>
       <ul>
        <li><a href='#'>HTML</a></li>
        <li><a href='#'>CSS</a></li>
        <li><a href='#'>SVG</a></li>
        <li><a href='#'>XML</a></li>
       </ul>
      </li>
      <li><a href='#'>Assignments</a></li>
     </ul>
    </li>
    <li><a href='#'>Contact</a></li>
   </ul>
   </nav>

   <main>
   <p>
   Lorem ipsum, dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.
    Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.
   Lorem ipsum, dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.
   Lorem ipsum, dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.

   </p>

   </main>

   </body>
   </html>
   

Cuarto Paso
-------------

En este paso agregamos una sola regla para lidiar con un pequeño problema. El problema es que solo puede hacer clic en un enlace cuando el mouse se encuentra sobre un enlace. Queremos poder hacer clic en cualquier lugar del cuadro que contenga una etiqueta. Cambiar la propiedad de visualización de una etiqueta le permitirá llenar el contenedor que lo encierra

.. code-block:: css

   nav li a {
       display: block; 
       padding: 0.25em 0 0.25em 0.5em;
       text-decoration: none; 
   }
   

.. activecode:: menu_4
   :language: html
   
   <html>
   <head>
   <title>SubMenus</title>
   <style type='text/css'>
   body {
       background: #EEE; 
       color: #000;
   }

   h1 {
       color: #AAA; 
       border-bottom: 1px solid; 
       margin-bottom: 0;
   }

   main {
       color: #CCC; 
       margin-left: 7em; 
       padding: 1px 0 1px 5%;
       border-left: 1px solid;
   }

   nav {
       float: left;
       width: 7em;
       background: #FDD;
   }

   nav ul {
        margin: 0; 
        padding: 0; 
        width: 7em; 
        background: white;
        border: 1px solid;
   }

   nav li {
        position: relative; 
        list-style: none; 
        margin: 0;
        border-bottom: 1px solid #CCC;
   }
   
   nav ul ul {
       position: absolute; 
       top: 0; 
       left: 7em;
       display: block;
   }
   
   nav li a {
       display: block; 
       padding: 0.25em 0 0.25em 0.5em;
       text-decoration: none; 
   }
   
   </style>
   </head>
   <body>

   <h1>Fundamentals of Web Programming</h1>

   <nav>
   <ul class='level1'>
    <li><a href='/'>Home</a></li>
    <li class='submenuu'><a href='#'>Syllabus</a>
     <ul class='level2'>
      <li><a href='#'>Text Book</a></li>
      <li><a href='#'>Office Hours</a></li>
      <li><a href='#'>Grading Policy</a></li>
      <li><a href='#'>Learning Goals</a></li>
     </ul>
    </li>
    <li><a href='#'>Resources</a></li>
    <li class='submenuu'><a href='#'>Publications</a>
     <ul class='level2'>
      <li><a href='#'>Articles</a></li>
      <li class='submenuu'><a href='#'>Tutorials</a>
       <ul class='level3'>
        <li><a href='#'>HTML</a></li>
        <li><a href='#'>CSS</a></li>
        <li><a href='#'>SVG</a></li>
        <li><a href='#'>XML</a></li>
       </ul>
      </li>
      <li><a href='#'>Assignments</a></li>
     </ul>
    </li>
    <li><a href='#'>Contact</a></li>
   </ul>
   </nav>

   <main>
   <p>
   Lorem ipsum, dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.
    Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.
   Lorem ipsum, dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.
   Lorem ipsum, dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.

   </p>

   </main>

   </body>
   </html>


Quinto Paso
------------

Antes de pasar al conjunto final de nuevas reglas, modifique el código anterior y simplemente cambie la propiedad de visualización en la regla ``nav ul ul`` a ninguna; Cuando vuelva a mostrar nuestra página, verá que esto hace que todos los submenús sean invisibles. He hecho este cambio a esa regla en el siguiente paso, pero es bueno ver cómo funciona por sí solo.
   
Finalmente, juntaremos todo, con unas pocas reglas pequeñas.

Cambiemos el color de fondo cuando pasemos el cursor sobre cualquier elemento de la lista.

También agreguemos una imagen de fondo para indicar que algo es un submenú.

¡La última regla hace visible un submenú! ``display: block;`` Pero queremos distinguir entre los distintos niveles añadiéndoles clases. Por lo tanto, también debemos modificar nuestro html para agregar clases a las ul y las li.

.. code-block:: css

   nav li:hover {
       background: #EBB;
   }

   nav li.submenu {
       background: url(http://...submenu.gif) 95% 50% no-repeat;
   }

   nav li.submenu:hover {
       background-color: #EDD;
   }

   nav ul.level1 li.submenu:hover ul.level2, 
   nav ul.level2 li.submenu:hover ul.level3 {
       display:block;
   }

El cambio que necesitamos hacer es

.. activecode:: menu_5
   :language: html
   
   <html>
   <head>
   <title>SubMenus</title>
   <style type='text/css'>
   body {
       background: #EEEEEE; 
       color: #000000;
   }

   h1 {
       color: #AAA; 
       border-bottom: 1px solid; 
       margin-bottom: 0;
   }

   main {
       color: #CCC; 
       margin-left: 7em; 
       padding: 1px 0 1px 5%;
       border-left: 1px solid;
   }

   nav {
       float: left;
       width: 7em;
       background: #FDD;
   }

   nav ul {
        margin: 0; 
        padding: 0; 
        width: 7em; 
        background: white;
        border: 1px solid;
   }

   nav li {
        position: relative; 
        list-style: none; 
        margin: 0;
        border-bottom: 1px solid #CCC;
   }
   
   nav ul ul {
       position: absolute; 
       top: 0; 
       left: 7em;
       display: none;
   }
   
   nav li a {
       display: block; 
       padding: 0.25em 0 0.25em 0.5em;
       text-decoration: none; 
   }
   
   nav li:hover {
       background: #6F99F2;
   }

   nav li.submenu {
       background: url(http://interactivepython.org/runestone/static/webfundamentals/_static/submenu.gif) 95% 50% no-repeat;
   }

   nav li.submenu:hover {
       background-color: #EDD;
   }



   nav ul.level1 li.submenu:hover ul.level2, 
   nav ul.level2 li.submenu:hover ul.level3 {
       display:block;
   }
   </style>
   </head>
   <body>

   <h1>Fundamentals of Web Programming</h1>

   <nav>
   <ul class='level1'>
    <li><a href='/'>Home</a></li>
    <li class='submenuu'><a href='#'>Syllabus</a>
     <ul class='level2'>
      <li><a href='#'>Text Book</a></li>
      <li><a href='#'>Office Hours</a></li>
      <li><a href='#'>Grading Policy</a></li>
      <li><a href='#'>Learning Goals</a></li>
     </ul>
    </li>
    <li><a href='#'>Resources</a></li>
    <li class='submenuu'><a href='#'>Publications</a>
     <ul class='level2'>
      <li><a href='#'>Articles</a></li>
      <li class='submenuu'><a href='#'>Tutorials</a>
       <ul class='level3'>
        <li><a href='#'>HTML</a></li>
        <li><a href='#'>CSS</a></li>
        <li><a href='#'>SVG</a></li>
        <li><a href='#'>XML</a></li>
       </ul>
      </li>
      <li><a href='#'>Assignments</a></li>
     </ul>
    </li>
    <li><a href='#'>Contact</a></li>
   </ul>
   </nav>

   <main>
   <p>
   Lorem ipsum, dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.
    Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.
   Lorem ipsum, dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.
   Lorem ipsum, dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.

   </p>

   </main>

   </body>
   </html>
   
  