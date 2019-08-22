Objetos auxiliares
==================

Arreglo
-------

Una matriz se utiliza para contener una colección de elementos. Por ejemplo, si quisiéramos trabajar con todos los elementos ``li`` en una lista, haríamos un seguimiento de todos manteniéndolos en una matriz. Una matriz nos permite trabajar con cada elemento a su vez porque se puede acceder a cada elemento de la matriz por su número.


Considere la siguiente lista.

.. raw:: html

   <ul>
      <li>Luther</li>
      <li>Coe</li>
      <li>Simpson</li>
      <li>Central</li>
      <li>Wartburg</li>
   </ul>


Lo primero en nuestra lista es Luther, su posición en la lista es 0. Lo segundo en la lista es Coe, su posición es 1, lo último en la lista (apropiadamente) es Wartburg, su posición es 4.

Podemos obtener los elementos de la lista y ponerlos en una matriz usando la función ``querySelectorAll``.


.. activecode:: helper_array_1
   :language: html
   
   <html>
   <body>
     <ul>
        <li>Luther</li>
        <li>Coe</li>
        <li>Simpson</li>
        <li>Central</li>
        <li>Wartburg</li>
     </ul>
     <script>
         theList = document.querySelectorAll('li')
         alert(theList[0].innerText)
     </script>
   </body>
   </html>


Podemos combinar iteración y matrices para trabajar con cada elemento en una matriz de la siguiente manera:

.. activecode:: helper_array_2
   :language: html
   
   <html>
   <body>
     <ul>
        <li>Luther</li>
        <li>Coe</li>
        <li>Simpson</li>
        <li>Central</li>
        <li>Wartburg</li>
     </ul>
     <script>
         theList = document.querySelectorAll('li')
         for(i=0; i< theList.length; i++) {
           alert(theList[i].innerText)
         }
     </script>
   </body>
   </html>


String
------
