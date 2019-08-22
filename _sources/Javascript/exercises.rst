Ejercicios Javascript
======================


1. Haga una página web simple que contenga un h2 con la palabra "Hello", un cuadro de entrada de texto y un botón. Cuando el usuario escribe una palabra o frase en el cuadro de entrada y presiona el botón, reemplace el antiguo h2 con la palabra ingresada. Usando animación, haz girar la palabra.

  .. actex:: ex_js_4
     :language: html

     <html>
     <style>
     </style>
     <body>
     <h2>Hello</h2>
     </body>
     </html>


2. Cree una página web simple que contenga un botón y un párrafo con la identificación de ``count``. Cuando se presione este botón, incremente el recuento en 1 y actualice el texto del párrafo. También actualice el tamaño de la fuente para que a medida que el número se agrande, también lo haga la fuente.

  .. actex:: ex_js_1
     :language: html

     <html>



     </html>


3. Repita el ejercicio anterior pero haga una lista de números. En este caso, no podrá actualizar simplemente el innerHTML del párrafo, deberá usar las funciones ``document.createElement()`` y ``document.appendChild()`` para agregar un nuevo elemento de lista.

  .. actex:: ex_js_2
    :language: html

    <html>



    </html>


4. Dado el siguiente html. Cada vez que se presiona el botón, debe agregar una fila a la tabla, donde la nueva fila de la tabla contiene la suma de las dos filas anteriores. Debe hacer uso de los atributos lastChild, previousSibling e innerText en este ejercicio.

  .. actex:: ex_js_3
     :language: html
     
     <html>
         <body>
            <button onclick="addrow()">Next</button>
            <ul id="mytable"><li id=0>1</li><li id=1>1</li></ul>
         </body>
     </html>
     

5. Cree una página html con dos cuadros de entrada de texto y cuatro botones. Los botones deben etiquetarse como ``+``, ``-``, ``*``, y ``/``. Cuando uno
   presiona estos botones, debe obtener el `valor` de ambos cuadros de entrada de texto y sumar, restar, multiplicar o dividir los
   números ingresados en los cuadros de entrada de texto. El resultado debe mostrarse debajo de los botones. **Nota** Para hacer matemáticas
   en los valores que lee de los cuadros de entrada de texto, deberá usar ``Number.parseInt`` en el valor. Por ejemplo
   supongamos que obtiene una referencia al cuadro de entrada 1 usando ``myIn1 = document.querySelector("#in1id");`` entonces la instrucción ``value1 = Number.parseInt(myIn1.value)`` convierte la cadena de la entrada de texto caja a un entero. De hecho
   la mayoría de las veces, Javascript realizará la conversión automáticamente, excepto por la adición.

  .. actex:: ex_js_5
    :language: html

    <html>



    </html>


6.  Comenzando con el código proporcionado, cree una página similar a la siguiente imagen: El resto de la página debe crearse.
    usando javascript. Debe usar ``document.createElement`` y las funciones ``appendChild``.

    .. image:: Figures/cePage.png
       :width: 350px

    .. actex:: ex_js_6
       :language: html

       <html>
       <body>
       <button onclick="makePage();">Click Here</button>
       </body>

       </html>
