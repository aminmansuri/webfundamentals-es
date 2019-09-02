.. This work is licensed under a Creative Commons Attribution 4.0 License
   Brad Miller, Luther College

La tecnología de la Web
=========================

Ahora volvemos a la pregunta de cómo una página llega del servidor a su navegador. Usemos la idea de un URI como nuestro punto de partida para esta sección. De hecho, comencemos abordando un punto de confusión muy común. Qué es un URI y qué es una URL, probablemente piense más comúnmente en las URL.

* URL - Localizador uniforme de recursos
* URI - Identificador uniforme de recursos

Todos los localizadores también son identificadores, por lo que todas las URL son URI. Piénselo de esta manera, Bradley Miller es un identificador, me identifica, pero no le dice cómo localizarme o cómo contactarme. 321 Olin Hall, Luther College, Decorah IA, es un localizador e identificador de un lugar específico en el mundo. En la URL de la web tenemos tres piezas principales, veamos una e identifiquemos las partes:

::

    http://interactivepython.org/runestone/static/webfundamentals/index.html

Esta es una URL común con tres partes:

* ``http`` Esta parte identifica el protocolo que se utilizará para la comunicación. Parece un poco redundante cuando siempre estamos pensando en la web, pero de hecho hay varios protocolos comunes que se usan en las URL, incluidos ``https`` para una comunicación http segura, ``mailto`` para indicar que vamos a usar un protocolo de correo, ``ftp``, el protocolo de transferencia de archivos.

* ``interactivepython.org`` Este es el nombre de un host en la web. Los nombres de host deben ser únicos, solo hay un interactivepython.org en todo Internet. Si profundiza más, puede descubrir que este nombre se traduce en una dirección numérica. Si alguna vez ha intentado configurar su enrutador doméstico, o ha mirado la configuración en su computadora o teléfono, indudablemente se ha encontrado con estas direcciones numéricas antes. En el caso de interactivepython.org la dirección numérica es 108.168.242.153. Esta dirección numérica también es única en todo Internet e identifica un servidor específico que se ejecuta en una sala de servidores en Dallas TX.

* ``runestone/static/webfundamentals/index.html`` identifica un archivo en particular en el servidor. El servidor tiene una carpeta runestone, y dentro de esa carpeta hay otra carpeta llamada static, que contiene otra carpeta llamada webfundamentals que finalmente contiene un archivo llamado index.html. Esto no es diferente de cómo probablemente organice sus propios archivos en su propia computadora.

Esta URL contiene **mucha** información. Cuando escribe esto en la barra de direcciones de su navegador, le ha brindado suficiente información para obtener la página específica que desea. Un diagrama ayudará con la siguiente parte de esta discusión.

.. image:: Figures/SimpleRequest.png

Supongamos que continuamos con la URL anterior. Usted, el usuario, ingrese la URL de su navegador. El navegador sabe que el nombre de host es la parte que viene después de las dos primeras barras, pero antes de la siguiente barra. Entonces puede extraer esa parte de la URL. El uso de patrones como este ocurre con frecuencia en informática. El nombre se pasa a otro servidor llamado Servicio de nombres de dominio (DNS) en el diagrama anterior. El DNS es en realidad una red de servidores muy grande y compleja, pero daremos por sentado que funciona y nos devuelve la dirección IP correctamente. Con la dirección en mano, el navegador establece una conexión con el servidor a través de un mechansim conocido como **socket**. Este socket permite que el navegador y el servidor se comuniquen de manera confiable a través de Internet.

Una solicitud HTTP
-------------------

Con la conexión establecida, el navegador envía el siguiente mensaje:

     GET runestone/static/webfundamentals/index.html HTTP/1.1
     Host: myname.luther.edu
     User-Agent: Mozilla/6.0
     Accept-Language: en
     _

El formato de este mensaje está definido por HTTP. Recuerde que un protocolo es un conjunto bien definido de reglas sobre cómo un programa se comunica con otro. Desglosemos este mensaje en sus partes componentes.

* ``GET``  -- HTTP define varios comandos, pero los más comunes son GET y POST. Como puede imaginar, GET es una solicitud para recuperar algunos recursos del servidor.
* ``runestone/static/webfundamentals/index.html`` Este es el URI para el recurso que queremos obtener. Recuerde que esto corresponderá a un archivo en la unidad de disco del servidor.
* ``HTTP/1.1`` le dice al servidor que el navegador está "hablando" la versión 1.1 del protocolo HTTP.

Esta es toda la información que puede estar contenida en la primera línea del mensaje. Si hay algo más en la línea, puede confundir al servidor, o el servidor puede simplemente ignorarlo. Esta línea se llama **línea de solicitud**.

Lo que sigue a la línea de solicitud son una serie de líneas llamadas **encabezados** Puede haber solo un encabezado o puede haber muchos. Sin embargo, solo puede haber un encabezado por línea y todos siguen el patrón de ``nombre: valor``. Entonces, la primera línea, el nombre es ``host`` y el valor es ``myname.luther.edu``, esto le permite al servidor saber el nombre de la máquina que lo está contactando. El encabezado ``User-Agent`` le dice al servidor que el usuario está ejecutando la versión 6.0 del navegador mozilla.

Finalmente la última línea está en blanco. El servidor sabe que no hay más encabezados cuando aparece una línea en blanco.

Una respuesta HTTP
------------------

El servidor extrae el URI de la línea de solicitud y sale a su disco para localizar el archivo. Suponiendo que el archivo esté allí, hará la siguiente respuesta a través del socket al navegador::

    HTTP/1.1 200 OK
    Date: Tues, 2 Sept 2014 15:39:21
    Server: Apache/1.4.1
    Content-Type: text/html

    <html>
    <head>
    </head>
    <body>
    <h1>Hello World</h1>
    </body>
    </html>


Al igual que la solicitud, el formato de la respuesta se detalla mediante HTTP. La primera línea nuevamente tiene tres partes ``HTTP/1.1`` le dice al navegador que el servidor está siguiendo el protocolo HTTP 1.1. el ``200`` es el código de respuesta que le dice al navegador que todo está bien y que OK es un mensaje descriptivo: algunas otras líneas de respuesta comunes son:

* HTTP/1.1 404 Not Found   -- es posible que haya visto un 404 si ha escrito mal una URL
* HTTP/1.1 500 Internal Server Error  -- el servidor se ha bloqueado por algún motivo
* HTTP/1.1 302 Recurso movido

Siguiendo la línea de respuesta están los encabezados del servidor. La mayoría de estos se explican por sí mismos, pero el encabezado ``Content-Type`` es particularmente importante. Esto le dice al navegador que lo que sigue será algo de HTML. Otro ``Content-type`` común es ``image/jpg``, esto le dice al navegador que lo que viene a continuación será una imagen. Tenga en cuenta que cada imagen en una página requerirá su propia solicitud/respuesta del navegador al servidor.

Finalmente, observe la línea en blanco seguida de los contenidos de la página web expresada en HTML, que es el tema del próximo capítulo.
