Sockets: los componentes básicos de la programación de redes
================================================================


¿Cómo es que dos programas que se ejecutan en su propia computadora pueden comunicarse entre sí? Esto es, por supuesto, lo que sucede muchas veces al día cuando su navegador le muestra una página web. Su navegador es un programa y debe comunicarse con un servidor web para obtener HTML, CSS, imágenes y Javascript que conforman una página web. Los detalles de cómo ocurre esta comunicación simple pueden tomar un semestre completo en un curso de Networking. Vamos a abordar solo la capa superior de este problema mirando la capa de aplicación de la pila de Redes.

El bloque de construcción de la capa de aplicación es el socket. Los sockets proporcionan una comunicación bidireccional fácil entre dos programas que se ejecutan en dos computadoras (o hosts) diferentes. Un socket se identifica de forma exclusiva por cuatro valores:

* Dirección IP origen
* Puerto de origen
* Dirección IP de destino
* Puerto de destino

Estos valores necesitan alguna definición. Primero, ¿qué queremos decir con una dirección IP? Usted ya sabe que las computadoras en Internet tienen buenos nombres memorables como www.google.com o knuth.luther.edu. Cada nombre se puede traducir a una dirección IP numérica IP única, como 192.203.196.71, solo 1 máquina en Internet puede tener la dirección IP  192.203.196.71  (sin embargo, esa dirección puede ser conocida por varios nombres). Las direcciones numéricas son necesarias para que la maquinaria de Internet haga el trabajo de enviar un mensaje de una máquina a otra.

El número de puerto es importante porque una computadora puede tener muchos programas ejecutándose, cada uno correspondiente a un servicio de red diferente. Por ejemplo, el servidor web se ejecuta en el puerto 80 mientras que el servidor de correo se ejecuta en el puerto 25 y el servidor ssh se ejecuta en el puerto 22. Por lo tanto, el puerto identifica a qué programa de la computadora está conectado el socket. En su computadora portátil, la situación es similar, puede tener un navegador web conectado a muchos servidores web diferentes en diferentes pestañas, tiene un cliente de correo conectado a un servidor de correo y probablemente tenga un cliente de mensaje conectado a un servidor de chat, etc.
