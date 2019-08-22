Iteración
=========


La iteración nos permite hacer cosas muchas veces, o procesar una **colección** de elementos. Examinaremos las colecciones en breve, por ahora, centrémonos en
conceptos básicos de iteración.


Ahora, esto no es muy emocionante, pero supongamos que queremos construir una tabla que tenga una fila para cada número del 0 al 9.


.. activecode:: js_iter1
   :language: javascript
   
   for(i = 0; i < 10; i++) {
       writeln("the number is " + i)
   }
   

Ahora eso fue bastante simple, pero ilustra un aspecto muy importante de la programación. Los aspectos clave del ejemplo son:

1. La declaración for, es la declaración que nos permite hacer cosas muchas veces.
2. El número de veces que hacemos algo está controlado por las tres declaraciones:
    1. ``i = 0`` este es nuestro valor inicial
    2. ``i < 10`` esta es nuestra condición de parada. Seguiremos haciendo lo que esté dentro de la declaración for hasta que ``i < 10`` ya no sea cierto.
    3.  ``i++`` esto es realmente importante ya que cambia el valor de i y nos permite avanzar hacia el final. Sin este tercer componente, nunca aumentaría y haríamos lo que sea que esté dentro del ciclo para siempre. Esto se llama un **bucle infinito**.

Ahora veamos cómo podemos usar el ciclo para agregar 10 filas a una tabla.


.. activecode:: js_iter2
   :language: html

   <html> 
   <table id="mytable"></table>   
   <script>  
   tbl = document.querySelector("#mytable")
   for(i = 0; i < 10; i++) {
       row = document.createElement("tr")
       cell = document.createElement("td")
       cell.innerText = i
       row.appendChild(cell)
       tbl.appendChild(row)
   }

   </script>
   </html>