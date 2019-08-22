Elementos HTML para interacción
===============================

La creación de páginas web interactivas requiere una variedad de elementos que permiten que su aplicación interactúe con el usuario. El estándar HTML5 nos proporciona muchos elementos diferentes a partir de los cuales podemos construir una aplicación.


Botón
------

.. code-block:: html

   <button>Click Me</button>

.. raw:: html

   <div style="display: block;">
   <button>Click Me</button>
   </div>


La etiqueta de entrada
----------------------

Muchos de los elementos utilizados en la construcción de una interfaz de usuario usan la etiqueta ``input``. Todos los elementos de ``input`` tienen un conjunto común de atributos, el más importante es el atributo de ``type``, ya que eso es lo que determina cómo se verá el elemento de entrada.

* type
* name
* id
* value


Entrada de texto
----------------

.. code-block:: html

   <input type="text" value="changeme" size="40">

.. raw:: html

   <div style="display: block;">
   <input type="text" size="20" value="change me">
   </div>


Contraseña
----------

.. code-block:: html

   <input type="password" value="secret" size="40">

.. raw:: html

   <div style="display: block;">
   <input type="password" size="40" value="change me">
   </div>



Caja
-----

.. code-block:: html

   <input type="checkbox" name="group1" value="audi">Audi<br />
   <input type="checkbox" name="group1" value="bmw">BMW<br />
   <input type="checkbox" name="group1" value="mercedes">Mercedes<br />

.. raw:: html

   <div style="display: block">
   <input type="checkbox" name="group1" value="audi">Audi<br />
   <input type="checkbox" name="group1" value="bmw">BMW<br />
   <input type="checkbox" name="group1" value="mercedes">Mercedes<br />
   </div>


Radio
-----

.. code-block:: html

   <input type="radio" name="group1" value="audi">Audi<br />
   <input type="radio" name="group1" value="bmw">BMW<br />
   <input type="radio" name="group1" value="mercedes">Mercedes<br />

.. raw:: html

   <div style="display: block">
   <input type="radio" name="group1" value="audi">Audi<br />
   <input type="radio" name="group1" value="bmw">BMW<br />
   <input type="radio" name="group1" value="mercedes">Mercedes<br />
   </div>

Color
-----

Dependiendo del navegador que esté utilizando, esto se verá como un cuadro de texto genérico o aparecerá como un bloque de color que al hacer clic en él aparecerá un selector de color.

.. code-block:: html

   <input type="color">

.. raw:: html

   <div style="display: block">
   <input type="color">
   </div>

Rango
-----

.. code-block:: html

   <input type="range" min=0 max=255 value=125>

.. raw:: html

   <div style="display: block;">
   <input type="range" min=0 max=255 value=125>
   </div>

Cosas de fecha
--------------

* month
* datetime-local
* week
* time


Menús desplegables
------------------

.. code-block:: html

   <select id="priority">
       <option>High</option>
       <option>Medium</option>
       <option>low</option>
   </select>
   
.. raw:: html

    <div style="display: block;">
        <select id="priority">
            <option>High</option>
            <option>Medium</option>
            <option>low</option>
        </select>
    </div>