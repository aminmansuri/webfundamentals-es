Crear elementos sobre la marcha
================================

El patrón en el ejemplo anterior es común en el desarrollo web. Crea una plantilla usando HTML y luego modifica la plantilla en respuesta a eventos, obteniendo acceso a esos elementos usando el método ``querySelector``.

Modificar una plantilla solo nos lleva muy lejos. En muchos otros casos, desea agregar contenido a su página de forma dinámica. Por ejemplo, hagamos una aplicación de tiempo simple que registre la fecha y la hora cada vez que presione el botón.

.. activecode:: create_1
   :language: html
   
   <html>
      <body>
          <button onclick="savetime()">Time</button>
          <table id="timetable">
          </table>
          <script type="text/javascript">
             savetime = function() {
                t = document.querySelector("#timetable")
                trow = document.createElement("tr")
                td = document.createElement("td")
                contents = document.createTextNode(Date())
                td.appendChild(contents)
                trow.appendChild(td)
                t.appendChild(trow)
             }
          </script>
      </body>
   </html>

Aunque no es una aplicación muy útil, ilustra cómo podemos crear elementos HTML en respuesta a eventos. La Figura 1 muestra el árbol DOM antes de hacer clic en el botón.

.. figure:: Figures/tree1.svg

   Figura 1, árbol DOM antes de hacer click

**Creación de un elemento** La función ``document.createElement`` se puede usar para crear cualquier elemento HTML. Puede crear un h1, una tabla, un párrafo, una entrada, incluso un botón. Una vez creado, el nuevo elemento aún no forma parte de nuestro árbol de documentos. Es por eso que necesitamos asignar un nombre a este elemento recién creado. En el ejemplo anterior, creamos un ``tr`` y lo llamamos trow y un ``td`` al que llamamos td. Podemos asignar valores a cualquiera de los atributos del elemento en este momento.

**Creación de texto** También utilizamos la función ``document.createTextNode`` para crear el texto que vamos a poner en la tabla. También podríamos haber usado ``td.innerHTML`` para lograr lo mismo, pero crear un ``textNode`` es otra forma de hacer el trabajo.

**Agregar al árbol** Ahora que tenemos nuestras nuevas piezas para nuestra página, necesitamos volver a armar las cosas. La función ``appendChild`` nos permite agregar al árbol agregando hijos uno a la vez. La Figura 2 muestra el nuevo árbol DOM y muestra el orden en que los nodos están conectados entre sí.

.. figure:: Figures/tree2.svg

   Figura 2, árbol DOM después de hacer click


Que botón?
----------

Considere el siguiente código. Tenemos dos botones, nos gustaría adjuntar la misma función a
ambos botones, pero cuando hacemos clic también nos gustaría que nuestra función sepa en qué botón se hizo clic.


.. activecode:: button_context_1
   :language: html

   <html>
      <body>
          <button onclick="hello()">Button1</button>
          <button onclick="hello()">Button2</button>
          <script type="text/javascript">
             hello = function() {
                 alert("Hello, who am I?");
             }
          </script>
      </body>
   </html>

¿Cómo podemos modificar el ejemplo para que sepa en qué botón se hizo clic? Podemos usar un parámetro.

¿Qué es ``this``?
~~~~~~~~~~~~~~~~~

El parámetro que podemos usar en nuestro ejemplo anterior es ``this``, que es un nombre de variable muy usado en Javascript,
pero también bastante confuso Puedes pensar en ``this`` como una referencia propia. Esto responde a "¿quién soy yo?" pregunta
para un objeto. Desde HTML podemos pasar esto como un parámetro a una función onclick, y porque el onclick
es parte de la etiqueta ``this`` se refiere a la etiqueta. Nota importante: en la mayoría de los casos hemos dicho que el
el nombre de una variable no importa; ¡``this`` es la excepción a esa regla!

Modifique el ejemplo anterior para que en cada caso llame a ``hello(this)``. Ahora en tu cambio de javascript
la alerta a ``alert("Hello I am " + me.innerHTML)``

A modo de comparación, creemos la misma página que la anterior pero en Javascript.

.. activecode:: button_context_2
   :language: html

   <html>
      <body>
          <script type="text/javascript">
             var b1 = document.createElement("button");
             b1.innerHTML = "Button1";
             var b2 = document.createElement("button");
             b2.innerHTML = "Button2";

             hello = function() {
                 alert("Hello, who am I?");
             }

             document.body.appendChild(b1);
             document.body.appendChild(b2);
             b1.onclick = hello;
             b2.onclick = hello;
          </script>
      </body>
   </html>

Cuando estamos creando elementos en Javascript, nuestra tarea es un poco más fácil. Porque la variable ``this``
se configura automáticamente para nosotros dentro de la función en función del objeto al que está adjunto.

Adjuntar eventos
----------------

¿Qué sucede si queremos adjuntar un evento a uno de los objetos que hemos creado? ¿Qué sucede si queremos usar una función pero adjuntarla a muchos elementos diferentes y hacer que nuestra función haga algo diferente según el elemento en el que se haga clic? Este es el tema final de esta sección. Es complicado, así que presta mucha atención. Comencemos adjuntando un controlador onclick a cada fila de la tabla.

.. activecode:: create_2
   :language: html
   
   <html>
      <body>
          <button onclick="savetime()">Time</button>
          <table id="timetable">
          </table>
          <script type="text/javascript">
             clickon = function() {
                 alert("Hello!");
             }
             savetime = function() {
                t = document.querySelector("#timetable");
                trow = document.createElement("tr");
                td = document.createElement("td");
                contents = document.createTextNode(Date());
                td.appendChild(contents);
                td.onclick = clickon;
                trow.appendChild(td);
                t.appendChild(trow);
             }
          </script>
      </body>
   </html>


Este ejemplo tiene una nueva función llamada clickon, en este momento, todo lo que hace es abrir un cuadro de diálogo de alerta que dice Hello cada vez que hace clic en una fila de la tabla. La línea que une esta función a la fila es ``td.onclick = clickon;`` Eso no es un error tipográfico, esa línea es correcta.  clickon es solo un nombre para una función, por lo que podemos usar ese nombre para asignar a otros atributos. Es solo cuando los paréntesis se ponen después del nombre que llamamos a la función.

.. admonition:: Punto clave

  Cuando se llama a un controlador de eventos, se llama dentro del contexto del elemento en el que se hizo clic. Entonces, el identificador ``this`` se referirá al elemento DOM en el que hizo clic. Luego puede acceder a los atributos del elemento utilizando ``this`` como identificador. Por ejemplo, ``this.className`` le dará la clase del elemento en el que hace clic.

Usando el punto clave desde arriba, podemos cambiar nuestra función de clic de la siguiente manera:

.. code-block:: javascript

   clickon = function() {
       message = this.innerText;
       alert("the time is " + message);
       alert("my parent is a " + this.parentNode.tagName)
   }  
   
Modifique el código en el ejemplo para que coincida con el anterior y luego ejecútelo. Tenga en cuenta que cuando hace clic en diferentes filas de la tabla, obtiene diferentes mensajes en el cuadro de diálogo de alerta. Tenga en cuenta que también sabe dónde vive en el árbol DOM y puede obtener su padre o incluso sus hermanos.
