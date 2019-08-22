Eventos Javascript
===================

En lugar de simplemente enumerar una serie de posibles eventos, veamos un ejemplo que ilustra el uso de muchos eventos.

Considere la siguiente página:


.. activecode:: js_event_1
   :language: html

    <html>
      <head>
        <title>Colors</title>
      </head>
      <body>
        <label for="redi">Red:</label>
        <input type="text" id="redi" min="0" value="255" /> <br>
        <label for="greeni">Green:</label>
        <input type="text" id="greeni"  value="255" /><br>
        <label for="bluei">Blue:</label>
        <input type="text" id="bluei" value="255" />
        <br>
        <button onclick="changeColor();">Change Color</button>

        <script>
          changeColor = function() {
              red = document.querySelector('#redi').value;
              green = document.querySelector('#greeni').value;
              blue = document.querySelector('#bluei').value;
              colorStr = "rgb("+red+","+green+","+blue+")";
              document.body.style.backgroundColor = colorStr;
          }
        </script>
      </body>
    </html>


Ahora, este primer ejemplo es similar en muchos aspectos a nuestros ejemplos anteriores, estamos utilizando el método ``querySelector`` para obtener una referencia al elemento de entrada de texto y leer su valor. El método ``onclick`` en nuestro botón adjunta el método changeColor a nuestro botón.

Sin embargo, esto es un poco insatisfactorio, sería bueno si pudiéramos escribir un nuevo valor en uno de los cuadros de entrada de texto y hacer que el color cambie. Otro tipo de evento que se usa comúnmente con entrada es el evento ``onchange``. Vamos a agregar un evento onchange a los elementos de entrada de texto y adjuntarlo a nuestra función changeColor. Ahora, cuando realiza un cambio en un color y toca la tecla de retorno en su teclado, el color cambiará. El color también cambiará si hace clic fuera del cuadro de entrada de texto. Darle una oportunidad.

.. activecode:: js_event_2
   :language: html

    <html>
      <head>
        <title>Colors</title>
      </head>
      <body>
        <label for="redi">Red:</label>
        <input type="text" id="redi" onchange="changeColor()" value="255" /> <br>
        <label for="greeni">Green:</label>
        <input type="text" id="greeni" onchange="changeColor()" value="255" /><br>
        <label for="bluei">Blue:</label>
        <input type="text" id="bluei" onchange="changeColor()" value="255" />
        <br>
        <button onclick="changeColor();">Change Color</button>

        <script>
          changeColor = function() {
              red = document.querySelector('#redi').value;
              green = document.querySelector('#greeni').value;
              blue = document.querySelector('#bluei').value;
              colorStr = "rgb("+red+","+green+","+blue+")";
              document.body.style.backgroundColor = colorStr;
          }
        </script>
      </body>
    </html>

Escribir return o hacer clic con el mouse todavía no es tan bueno como podríamos hacer. Hay algunos otros eventos específicos del teclado que podemos adjuntar a nuestro cuadro de entrada de texto. Intente cambiar el atributo ``onchange`` en el ejemplo anterior a ``onkeyup``. Este evento ocurre después de que el usuario ha escrito una tecla y la tecla ha vuelto a su posición superior. De hecho, hay tres eventos con los que puede experimentar para las teclas del teclado:

* onkeydown  -- se dispara cuando se presiona la tecla
* onkeypress  -- dispara después de onkeydown pero no para control, shift, alt
* onkeyup --se dispara cuando la tecla sube

Puede notar aquí un comportamiento poco confiable. El problema es que hay un pequeño problema de tiempo entre el momento en que ocurre el evento clave y el momento en que ocurre la actualización del valor de los cuadros de entrada de texto. Puede ser que el valor se actualice antes de leerlo, o puede que no se actualice hasta después de leerlo. Hay maneras de evitar esto, pero eso agregaría más dificultad al ejemplo de lo que queremos entrar ahora.

Ahora, para explorar algunos eventos adicionales, usemos un elemento de interfaz de usuario más agradable para ajustar el color de nuestro fondo. Vamos a usar un control deslizante. Podemos obtener un control deslizante cambiando el tipo de entrada a ``range``.

.. activecode:: js_event_3
   :language: html

    <html>
      <head>
        <title>Colors</title>
      </head>
      <body>
        <label for="redi">Red:</label>
        <input type="range" min=0 max=255 id="redi" onchange="changeColor()" value="255" /> <br>
        <label for="greeni">Green:</label>
        <input type="range" min=0 max=255 id="greeni" onchange="changeColor()" value="255" /><br>
        <label for="bluei">Blue:</label>
        <input type="range" min=0 max=255 id="bluei" onchange="changeColor()" value="255" />
        <br>
        <script>
          changeColor = function() {
              red = document.querySelector('#redi').value;
              green = document.querySelector('#greeni').value;
              blue = document.querySelector('#bluei').value;
              colorStr = "rgb(" + red + "," + green + "," + blue + ")";
              document.body.style.backgroundColor = colorStr;
          }
        </script>
      </body>
    </html>

Ok, eso es realmente agradable, ahora podemos mover el control deslizante, y cada vez que lo dejamos ir, solo actualiza el color. ¡Pero podemos ir un paso más allá y cambiar el color a medida que se mueve la barra! Cambie el evento de `` onchange`` a `` onmousemove`` para ver los resultados.


Antes de abandonar esta sección, agreguemos dos mejoras más a este ejemplo:

1. Permite mostrar los valores de rojo, verde y azul.
2. Comencemos con un valor predeterminado diferente para nuestros colores rgb y haga que la página cambie automáticamente su color de fondo cuando se cargue la página.

No *necesitamos* que los valores cambien continuamente, así que vamos a actualizar los valores cuando el usuario deja de presionar la tecla del mouse. Para hacer esto, agregaremos un segundo atributo de evento a cada uno de nuestros elementos de entrada. El evento que necesitamos es ``onmouseup``. Cuando recibamos un evento onmouseup, llamaremos a otra función para mostrar los valores actuales de rojo, verde y azul.

.. activecode:: js_event_4
   :language: html

    <html>
      <head>
        <title>Colors</title>
      </head>
      <body>
        <label for="redi">Red:</label>
        <input type="range" min=0 max=255 id="redi" onmousemove="changeColor()"
              onmouseup="showValues()" value="125" /> <span id="redv"></span><br>
        <label for="greeni">Green:</label>
        <input type="range" min=0 max=255 id="greeni" onmousemove="changeColor()"
              onmouseup="showValues()" value="125" /><span id="greenv"></span><br>
        <label for="bluei">Blue:</label>
        <input type="range" min=0 max=255 id="bluei" onmousemove="changeColor()"
              onmouseup="showValues()" value="200" /><span id="bluev"></span>

        <br>
        <script>
          changeColor = function() {
              red = document.querySelector('#redi').value;
              green = document.querySelector('#greeni').value;
              blue = document.querySelector('#bluei').value;
              colorStr = "rgb(" + red + "," + green + "," + blue + ")";
              document.body.style.backgroundColor = colorStr;
          }
          showValues = function() {
            document.querySelector('#redv').innerHTML = document.querySelector("#redi").value;
            document.querySelector('#greenv').innerHTML = document.querySelector("#greeni").value;
            document.querySelector('#bluev').innerHTML = document.querySelector("#bluei").value;
          }
          window.onload = function() { changeColor(); showValues(); }
        </script>
      </body>
    </html>


Este es un buen ejemplo pulido ahora. Así que echemos un vistazo a algunos de los nuevos artículos. Primero, hemos adjuntado diferentes eventos al elemento de entrada. En general, puede adjuntar tantos eventos como tenga sentido a un elemento. En este caso tenemos uno para el movimiento del mouse y otro para el mouse hacia arriba.

En segundo lugar, la función showValues contiene una declaración de asignación que es muy compacta para escribir, pero puede ser complicada para seguir, así que veamos una de esas declaraciones y luego la reescribamos de una manera que probablemente sea más fácil de entender.

.. code-block:: javascript

   document.querySelector('#redv').innerHTML = document.querySelector("#redi").value;

Comenzando con el lado derecho de la declaración de asignación, lo anterior es obtener el valor del control deslizante para el valor rojo. Luego está configurando el innerHTML del elemento ``span`` que viene después del control deslizante para mantener ese valor. Podríamos reescribir esta declaración para que sea más fácil de entender de la siguiente manera:

.. code-block:: javascript

  theSpan = document.querySelector('#redv');
  theSlider = document.querySelector("#redi");
  sliderVal = theSlider.value;
  theSpan.innerHTML = sliderVal;

El segundo ejemplo divide nuestro trabajo en partes mucho más manejables:

#. Obtenga una referencia al elemento span que sigue al control deslizante. Aquí es donde se mostrará el valor del control deslizante.
#. Obtenga una referencia al nodo del control deslizante de entrada en el modelo de objeto del documento.
#. Obtenga el valor del control deslizante del atributo de valor
#. Almacene el valor del control deslizante en el atributo innerHTML del intervalo.

Finalmente, cuando se carga la página, queremos establecer el color de fondo y mostrar cada valor del control deslizante en la página. Para hacer esto, necesitamos adjuntar dos funciones al evento ``window.onload``. Esto no es posible sin una magia sofisticada de Javascript, pero esto ilustra una forma de programación de Javascript que es bastante común. Aquí está la línea importante:

.. code-block:: javascript

   window.onload = function() { changeColor(); showValues(); }

Cuando la página está completamente cargada, ocurre el evento ``window.onload``. Como queremos que se invoquen nuestras dos funciones, creamos una función (¡sin nombre!) Para que se invoque, y esta función llama a nuestras dos funciones. Esto es un poco diferente de cómo adjuntamos funciones a elementos HTML, pero no se preocupe demasiado por ahora. Simplemente pruebe el ejemplo para ver que realmente funciona tal como lo queremos.


.. activecode:: js_event_6
   :language: html
   
   <html>
   <body>
   <button onclick="stop();">Stop</button>
   <script>
     changeColor = function() {
         red = Math.floor(Math.random()*255);
         green = Math.floor(Math.random()*255);
         blue = Math.floor(Math.random()*255);
         colorStr = "rgb(" + red + "," + green + "," + blue + ")";
         document.body.style.backgroundColor = colorStr;
         //window.setInterval(changeColor, 1000);
     }
     stop = function() {
         window.clearInterval(intId);
     }
     intId = window.setInterval(changeColor, 1000);
   </script>
   </body>
   </html>
   

Eventos utilizados en esta sección
------------------------------------

* onclick
* onchange
* onkeyup
* onkeypress
* onmouseup
* onmousedown
* onmousemove
* window.onload
* window.setInterval
* window.clearInterval

