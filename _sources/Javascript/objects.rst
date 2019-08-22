Objetos Atributos y Métodos
==============================


En la sección anterior tuvimos el siguiente ejemplo:

.. activecode:: js_hello2
   :language: html
   
   <html>
      <body>
         <h1>Hello World!!</h1>
         <button onclick="changeThisPageFunc();">Click Me!</button>
         <script type="text/javascript">
            changeThisPageFunc = function() {
               document.body.style.backgroundColor = "lightblue";
               document.body.innerHTML = "<h1>I am a little blue today</h1>";
            }
         </script>
      </body>
   </html>
   
   
Si solo piensa en el HTML, y qué tipo de árbol obtiene del documento, obtendrá algo como esto:

.. image:: Figures/simpledom.svg


En el ejemplo anterior tenemos un nombre ``document``, ya que puede haber adivinado que este nombre de documento se refiere a todo el documento HTML (o página). Más técnicamente, documento es un nombre que se refiere a un **objeto**. Ese objeto es la representación de la página.

Anteriormente dijimos que los objetos saben cosas y saben cómo hacer las cosas, la terminología de las cosas que los objetos saben es que los objetos tienen **atributos** atributos en los objetos tienen el mismo propósito que los atributos de las etiquetas, contienen alguna propiedad de objeto. Por ejemplo, ``document.height`` nos dice cuántos píxeles de altura tiene toda la página. Nuestro ejemplo ilustra varios otros atributos:

* document.body
* document.body.style
* o más específicamente document.body.style.backgroundColor   (y los otros que probablemente descubriste)
* document.body.innerHTML

Podemos usar estos atributos de dos maneras. Primero, podemos usar atributos para hacer una pregunta al objeto. Por ejemplo, ``document.body.style.backgroudColor`` podría interpretarse como preguntando al documento "dime tu color de fondo".
Por otro lado, ``document.body.style.backgroundColor = "lightblue"`` debe interpretarse como "establecer el color de fondo en azul claro".

La diferencia clave entre las dos interpretaciones en el párrafo anterior es donde se utiliza el atributo en relación con el signo igual. De hecho, la declaración ``document.body.style.backgroundColor = "lightblue"`` es una declaración de programación especial y muy común llamada **declaración de asignación**.

Ahora, también puede estar preguntándose sobre el ``.`` entre los diversos atributos en la declaración. Debe leer los puntos entre los atributos como: objeto de documento (punto) devuelve su objeto de cuerpo (punto) devuelve su objeto de estilo (punto) devuelve su objeto backgroundColor.

El atributo innerHTML nos permite cambiar el html de cualquier elemento en nuestro documento. Por supuesto, como notó antes de cambiar el valor HTML del cuerpo, borra todas las etiquetas antiguas y las reemplaza por lo que está entre comillas. Veamos otro ejemplo que ilustra otra función de JavaScript muy importante y nos permitirá cambiar solo una pequeña parte de la página web.

Nuestro objetivo es cambiar el ``h1`` sin cambiar el resto de la página. Probemos un enfoque que pueda parecerle claro ahora, que **no funcionará**

.. activecode:: js_hello3
   :language: html
   
   <html>
      <body>
         <h1>Hello World!!</h1>
         <button onclick="changeThisPageFunc();">Click Me!</button>
         <script type="text/javascript">
            changeThisPageFunc = function() {
               // this will not work
               document.body.h1.style.backgroundColor = "lightblue";
            }
         </script>
      </body>
   </html>

La razón por la que esto no funcionará es porque el cuerpo puede contener muchas etiquetas ``h1``. Por lo tanto, necesitamos una forma de identificar y "controlar" el h1 exacto que queremos cambiar.

Veamos la forma correcta de hacer esto. En el siguiente ejemplo tenemos una etiqueta semántica llamada ``main``, queremos cambiar el contenido de main sin modificar el resto del documento.

.. activecode:: js_selector
   :language: html
   
   <html>
      <body>
         <h1>Hello World!!</h1>
         <button onclick="changeThisPageFunc();">Click Me!</button>
         <main>
            <h1>Hello Main</h2>
            <p>The quick brown fox jumped over the lazy dog.</p>
         </main>
         <script type="text/javascript">
            changeThisPageFunc = function() {
               var myMain;
               document.body.style.backgroundColor = "lightblue";
               myMain = document.querySelector('main');
               myMain.innerHTML = "<h3>Where have all the flowers gone?<h3>";
               myMain.style.height = "50px";
               myMain.style.width = "50%";
               myMain.style.backgroundColor = "lightgreen";
            }
         </script>
      </body>
   </html>


¡Nuestra función ha crecido! Pero no dejes que eso te preocupe, hemos agregado más elementos de asignación que solo cambian la etiqueta ``main``. Sin embargo, hemos introducido una nueva característica de programación muy importante en este ejemplo.  ``myMain`` es una **variable**. Las variables son nombres que le damos a los objetos Javascript, en este caso es la etiqueta ``main``. Ahora, dado lo que sabe hasta ahora, puede preguntarse por qué no solo usar ``document.body.main``. Porque no existe El objeto de documento tiene un atributo ``body`` porque todos los documentos tienen un ``body``, pero no todos los documentos tienen un ``main``.

Por lo tanto, necesitamos encontrar el principal en nuestro documento y darle un nombre para que podamos hacer cosas con él. Esto es lo que está sucediendo en la declaración: ``myMain = document.querySelector('main');`` Las declaraciones de asignación funcionan de la siguiente manera:

1. evalúe lo que esté al lado derecho del operador de asignación ``=``.
2. Haga que el nombre en el lado izquierdo de la tarea se refiera al resultado de 1.

Ahora, el lado derecho de la instrucción de asignación contiene un **método**. Esta es una palabra elegante para nosotros diciéndole a un objeto que haga algo por nosotros. De hecho, un método es solo un nombre elegante para una función adjunta a un objeto, por lo que también es una abstracción. Ahora, aquí están las buenas noticias sobre este método. ¡Todo lo que aprendiste sobre los selectores en el capítulo anterior sobre CSS se puede usar para decirle a este método lo que quieres que encuentre! ``'main`` es un parámetro para el método querySelector, y podría contener cualquier selector que aprendimos en el capítulo anterior.

De hecho, ``document.head`` y ``document.body`` son las únicas etiquetas a las que podemos acceder directamente. Se debe acceder a todas las demás etiquetas usando ``querySelector``

Tomemos un respiro aquí y pruebe algunas cosas:

1. Regrese y modifique el primer ejemplo para que pueda cambiar el color del h1.
1. Cambie el HTML para que main tenga una identificación de ``"a"``. También agregue una segunda etiqueta ``main`` que contenga un h1. La vista inicial de su página no debe cambiar. ¿Qué sucede cuando haces clic en el botón?
2. Ahora cambie el parámetro al método querySelector para que encuentre main por su ID en lugar de por su etiqueta. ¿Qué sucede si elimina el atributo id del primer main y lo mueve al segundo?