Cambiar el Estilo de un Elemento HTML
======================================

Hay muchas maneras en que podemos cambiar el estilo de lo que vemos en el navegador. En esta sección veremos ejemplos de lo siguiente:

* fondo
* texto
* fuente

Pero antes de hablar sobre esto, debemos pensar en los colores. Hay tres formas diferentes de especificar el color.

* por nombre, como azul, rojo, verde. Puede ver una lista completa de `nombres de colores <http://www.w3schools.com/cssref/css_colors.asp>`_ en el sitio web de w3schools.
* usando un valor RGB como ``rgb(255,0,0)``
* utilizando un valor HEX como ``#ff0000``

El uso del valor RGB o HEX le brinda un control total para especificar cualquiera de los 16 millones de colores diferentes. Hay un poco de informática interesante detrás de los valores RGB y HEX. La función rgb le permite especificar un valor entre 0 y 255 para cada componente de rojo, verde y azul. Al mezclar una cierta cantidad de rojo, verde y azul puede crear: matemática:`255 \cdot 255 \cdot 255` colores diferentes, que es un poco más de 16.5 millones. ¿De dónde viene el número 255? Es uno menos que: matemáticas:`2^8`. A los informáticos les gustan los poderes de dos porque cuando entras profundamente en el funcionamiento interno de la computadora, ves que todo está en binario (unos o ceros) que llamamos bits. Con ocho bits podemos especificar 256 valores diferentes o 0 - 255. Llamamos ocho bits a un byte.

Ahora la especificación HEX del número está directamente relacionada con el binario de la siguiente manera:

======  ===  =======
binary  hex  decimal
======  ===  =======
0000     0   0
0001     1   1
0010     2   2
0011     3   3
0100     4   4
0101     5   5
0110     6   6
0111     7   7
1000     8   8
1001     9   9
1010     a   10
1011     b   11
1100     c   12
1101     d   13
1110     e   14
1111     f   15
======  ===  =======

Al especificar un color usando el sistema HEX, los dos primeros caracteres son para el rojo, los dos últimos para el verde y los últimos para el azul. Hay muchas herramientas de selección de color que puede usar que le permitirán elegir el color que desee y luego le indicará el valor hexadecimal apropiado.


Fondo
-------

CSS tiene las siguientes propiedades que podemos usar para cambiar el fondo.

* color de fondo
* imagen de fondo
* repetición de fondo
* fondo adjunto
* posición de fondo

.. activecode:: css_bkgrd_1
   :language: html

   <html>
      <head>
         <style>
         h1 {
            color: blue;
            font-size: 28pt;
         }
         body {
             background-image: url("http://m.99wallpaper.com/images/7_1306/Black%20Background%20Wood%20-%202560x1600%20by%20Freeman.jpg")
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


Texto
------

* color de texto
* texto alineado
* decoración de texto
* transformación de texto

Fuente
-------

* familia tipográfica
* estilo de fuente
* tamaño de fuente
