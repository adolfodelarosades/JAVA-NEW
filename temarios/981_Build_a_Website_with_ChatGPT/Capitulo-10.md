# 10 Configuración de una galería de fotos
Este capítulo cubre

Uso de imágenes en una página web
Trabajar con versiones en miniatura de imágenes
Visualización de imágenes en una caja de luz
Diseño de una página con Flexbox
Elaboración de un mensaje de ChatGPT para crear una página de galería de fotos
Examinar y personalizar el código generado por ChatGPT
Después de aprender algunos conceptos básicos sobre imágenes en el capítulo 4, los proyectos de este libro han incluido principalmente una sola imagen: el logotipo de un sitio en el encabezado de la página. Es un buen comienzo, pero sin duda sabrá por sus propios viajes por Internet que las imágenes están por todas partes en la web. Una foto o ilustración bien ubicada y bien elegida puede animar una página y ofrecer un atractivo visual para los visitantes cansados ​​del texto.

En este capítulo, aprenderá un poco más sobre las imágenes y cómo funcionan en la web, lo que le permitirá incorporar imágenes adicionales en sus páginas. Como dice el dicho, “a lo grande o váyase a casa”, por eso, en este capítulo, las imágenes son importantes y no solo le mostrarán cómo crear una galería de fotos funcional que pueda usar para mostrar sus habilidades fotográficas, sino también cómo usar una técnica de diseño moderna para que su página se vea increíble. Luego, pondrá en práctica todo este conocimiento sobre imágenes y listas de diseño para crear un mensaje detallado para que ChatGPT genere el código para la galería de fotos.

Este capítulo también proporciona versiones comentadas del código HTML y CSS generados por ChatGPT para ayudarte a entender cómo funciona la galería de fotos. También recibirás algunos consejos útiles para personalizar el código.

10.1 Revisando el proyecto de este capítulo
Como mencioné en la introducción, el proyecto de este capítulo es una galería de fotos de una sola página. La página final incluirá los siguientes componentes:

Un elemento de encabezado que incluye el logotipo y el título del sitio web.

Un elemento principal que comienza con el título de la galería y las instrucciones para usar la galería.

Nueve versiones de tamaño reducido de las fotografías, donde al hacer clic en una de estas imágenes se muestra una versión de tamaño más grande de la imagen.

Un elemento de pie de página que incluye un aviso de derechos de autor

La figura 10.1 muestra un ejemplo de galería de fotos creada con el código proporcionado por ChatGPTPuedes utilizar este tipo de diseño para otros tipos de contenido, como un catálogo de productos, un portafolios de artistas, un muestrario de diseños o una galería de proyectos actuales o finalizados, miembros del equipo, próximos eventos, testimonios o clientes. El denominador común de todos estos proyectos es que consisten en una colección de imágenes (quizás también con algo de texto), por lo que necesitas saber un poco más sobre cómo funcionan las imágenes en la web.



Figura 10.1 Una galería de fotos generada por ChatGPT

10.2 Una mirada más cercana a las imágenes
Si ha utilizado un procesador de textos o un programa de presentaciones, probablemente haya creado muchos documentos que incluyen imágenes. En cada caso, la aplicación ofrece algo así como un comando Insertar imagen que le permite elegir la imagen que desea, que se agrega directamente al documento en el lugar que elija.

Sorprendentemente, el código de una página web no funciona de la misma manera. No existe un equivalente en HTML del comando Insertar imagen que inserta una imagen directamente en la página. En su lugar, se carga la imagen en el sitio web como un archivo independiente y luego se inserta en el texto de la página una etiqueta HTML especial que le indica al navegador dónde ubicar la imagen. Cuando el navegador encuentra esta etiqueta, recupera el archivo de imagen del servidor y muestra la imagen en la página en la ubicación que se especificó.

10.2.1 Comprobación de la etiqueta <img>
La etiqueta especial que hace que el navegador agregue una imagen a una página web es la <img>etiqueta , que utiliza la sintaxis parcial que se muestra en la figura 10.2.



Figura 10.2 Inserta una imagen en una página web utilizando la <img>etiqueta.

Esta versión del imgelemento tiene dos atributos:

src="file"—Para el atributo src(abreviatura de source ), se reemplaza filecon la ubicación del archivo de imagen. Para simplificar, solo voy a mostrar las dos posibilidades más comunes:

Si el archivo de imagen se encuentra en el mismo directorio que el archivo HTML, reemplácelo filecon el nombre del archivo de imagen. Por ejemplo, si el archivo de imagen es logo.png, la <img>etiqueta se verá así:

<img src="logotipo.png" alt="">
Si la imagen está en un subdirectorio, reemplácela filecon el nombre del directorio y el nombre del archivo de la imagen, separados por una barra invertida ( /). Por ejemplo, si ha creado un subdirectorio llamado images y su archivo de imagen es logo.png, su <img>etiqueta se verá así:

<img src="imágenes/logotipo.png" alt="">
alt="description"—Para el atributo alt(abreviatura de alternative ), se reemplaza descriptioncon una palabra o frase corta que describa la imagen; esto se puede usar en lugar de la imagen si no se puede mostrar el archivo de imagen. El texto alternativo (como se lo suele llamar) también lo usan los lectores de pantalla y las aplicaciones Braille para darles a sus usuarios una idea de qué es la imagen. Aquí hay un ejemplo:

<img src="images/logo.png" alt="Logotipo de Ampersand Photography">
Técnicamente, su página web no es válida a menos que cada <img>etiqueta tenga un altatributo presente. Tener una página no válida significa que su página puede no visualizarse correctamente en el navegador web, pero principalmente significa que su página será menos accesible para personas que usan tecnologías de asistencia como lectores de pantalla. Afortunadamente, <img>las etiquetas generadas por ChatGPT generalmente incluyen el altatributo, pero la descripción casi siempre es trivial y poco útil. Por lo tanto, siempre debe incluir el alttexto que desea en su mensaje. Aquí hay un ejemplo de instrucción para ChatGPT:

Agregue una imagen llamada "old-road-marker.jpg", que se almacena en el subdirectorio "images". Para el atributo alt, utilice lo siguiente: "Una foto con un marcador de carretera muy antiguo en primer plano que dice 'Appleby 12 Miles'".
A continuación se muestra un ejemplo <img>de etiqueta generada por ChatGPT a partir de dicho mensaje:

<img src="imagenes/marcador-de-carretera-antiguo.jpg"
     alt="Una foto con un marcador de carretera muy antiguo en el
     primer plano que dice 'Appleby 12 Miles'">
CONSEJO: si tu página utiliza imágenes decorativas o no esenciales, establece el altatributo como la cadena vacía ( ""). De esa manera, tu página seguirá siendo válida, pero no molestarás a las personas que usan tecnología de asistencia (como lectores de pantalla) y que no quieren escuchar descripciones de imágenes puramente decorativas.

Si aún no tiene la imagen que desea utilizar pero conoce las dimensiones finales de la imagen, puede insertar una imagen de marcador de posición para que ocupe el mismo espacio en la página hasta que la imagen esté lista para usarse. La sección de red proporciona los detalles.

10.2.2 Agregar imágenes de marcador de posición
Probablemente sepas que, en el mundo del texto, un marcador de posición es un texto que marca temporalmente un lugar donde aparecerá una palabra o frase permanente. En la sección anterior, por ejemplo, la sintaxis para la <img>etiqueta utilizó los marcadores de posición filey descriptionpara los valores de los atributos srcy alt, respectivamente.

También puedes usar marcadores de posición con imágenes. En este caso, la imagen del marcador de posición ocupa la misma cantidad de espacio que la imagen permanente que se agregará eventualmente a la página, lo que resulta muy útil si quieres crear tu página pero no tienes la imagen (o imágenes) que necesitas.

Hay varias formas de agregar imágenes de marcador de posición, pero la más sencilla es usar un servidor de marcador de posición, como https://placehold.co . Aquí hay un ejemplo de instrucciones para que ChatGPT agregue una imagen de marcador de posición:

Insertar una imagen de marcador de posición desde placehold.co. Las dimensiones de la imagen son 300 px de ancho y 200 px de alto.
A continuación se muestra un ejemplo <img>de etiqueta generada por ChatGPT a partir de este mensaje:

<img src="https://placehold.co/300x200" alt="Imagen de marcador de posición" width="300" height="200">
La figura 10.3 muestra cómo aparece este marcador de posición en una página web.



Figura 10.3 Un ejemplo de imagen de marcador de posición de placehold.co

10.2.3 Trabajar con miniaturas de imágenes
Para mostrar realmente sus fotografías, debe mostrarlas en un tamaño relativamente grande. Sin embargo, según el formato del archivo (consulte el capítulo 4) y otros factores, como la cámara que utilizó, el archivo de tamaño completo puede ser bastante grande, al menos varios megabytes. Eso es bastante malo para una sola imagen, pero su galería de fotos tendrá varias imágenes (nueve en este proyecto); es pedir demasiado que los visitantes de la galería descarguen una cantidad tan enorme de datos. (Esto es especialmente cierto para las personas que acceden a su página a través de una conexión a Internet lenta o un plan de datos móviles limitado).

En el caso de un proyecto como una galería de fotos, una mejor estrategia para todos los usuarios es mostrar inicialmente una versión reducida (conocida en el sector como miniatura ) de cada foto. La idea es configurar la página de modo que al hacer clic en una miniatura se muestre temporalmente una versión de tamaño grande de la foto (el tamaño que ve el usuario depende de las dimensiones de la ventana del navegador).

NOTA: No existen reglas estrictas sobre el tamaño de las miniaturas. Una página diseñada para albergar docenas de imágenes puede utilizar miniaturas de solo 50 o 75 píxeles de ancho, mientras que para una galería de fotos como la que ChatGPT te ayudará a crear en este capítulo, las miniaturas de alrededor de 300 píxeles de ancho funcionan bien.

Antes de continuar, debes crear versiones en miniatura de tus fotos. En primer lugar, las instrucciones de Windows.

Cómo crear una miniatura con la aplicación Fotos de Windows

Si usa Windows 11, puede hacer una copia del archivo de la foto original y luego usar la aplicación Fotos para cambiar el tamaño de la copia a las dimensiones de miniatura que prefiera. En este proyecto, supongo que las versiones en miniatura incluyen el texto -thumbnail como parte del nombre del archivo. Por ejemplo, si la versión de tamaño completo se llama image01.jpg, su versión en miniatura se llamará image01-thumbnail.jpg.

Siga estos pasos para crear una versión en miniatura de una foto usando la aplicación Fotos:

   1. Utilice el Explorador de archivos para localizar la foto con la que desea trabajar.

   2. Haga clic en el archivo, haga clic en Copiar en la barra de herramientas y luego haga clic en Pegar para crear una copia de la foto.

   3. Haga clic en el archivo copiado, haga clic en Cambiar nombre (o presione F2) y luego edite el nombre del archivo para eliminar el texto -Copiar agregado por Windows y reemplazarlo por -thumbnail. (De esta manera, debería terminar con un nombre de archivo similar a image01-thumbnail.jpg).

   4. Haga doble clic en el archivo de imagen copiado y renombrado para cargar la imagen en la aplicación Fotos.

   5. Haga clic en Ver más (los tres puntos en la barra de herramientas) y luego haga clic en Cambiar tamaño de imagen para abrir el cuadro de diálogo Cambiar tamaño, que se muestra en la figura 10.4.



Figura 10.4 Utilice el cuadro de diálogo Cambiar tamaño para crear una versión en miniatura de su foto.

   6. Asegúrese de que la opción Píxeles esté seleccionada.

   7. Utilice el cuadro de texto Ancho para establecer el ancho de la miniatura en píxeles. (Tenga en cuenta que el valor de Altura cambia automáticamente para mantener la relación de aspecto, es decir, la relación entre el ancho de la imagen y su altura, que es lo que desea. Alternativamente, puede establecer el valor de Altura y el Ancho cambiará automáticamente).

   8. Haga clic en Guardar.

Si usa una Mac en lugar de una PC con Windows, su versión de los pasos es la siguiente.

Cómo crear una miniatura con la aplicación Vista previa de macOS

Si utiliza macOS, puede usar Finder para copiar el archivo de la foto original y luego usar Vista previa para cambiar el tamaño de la copia al ancho y alto de miniatura que prefiera. Este proyecto supone que las copias en miniatura incluyen el texto -thumbnail en el nombre del archivo. Por ejemplo, si el archivo de la foto de tamaño completo se llama image01.jpg, la versión en miniatura debe llamarse image01-thumbnail.jpg.

Siga estos pasos para crear una versión en miniatura de una foto en macOS:

   1. Utilice el Finder para localizar y hacer clic en la foto con la que desea trabajar.

   2. Seleccione Editar > Copiar y luego seleccione Editar > Pegar para crear una copia de la foto.

   3. Haga clic en el archivo copiado, presione Entrar y luego edite el nombre del archivo para eliminar el texto copiado agregado por Finder y reemplazarlo con -thumbnail. (De esta manera, debería terminar con un nombre de archivo como image01-thumbnail.jpg).

   4. Haga doble clic en el archivo de imagen copiado y renombrado para cargar la imagen en Vista previa.

   5. Elija Herramientas > Ajustar tamaño para abrir el cuadro de diálogo que se muestra en la figura 10.5.



Figura 10.5 Utilice este cuadro de diálogo para crear una versión en miniatura de su foto.

   6. Asegúrese de que el elemento Píxeles esté seleccionado en la lista a la derecha de los cuadros de texto Ancho y Alto.

   7. Utilice el cuadro de texto Ancho para establecer el ancho de la miniatura en píxeles. (Tenga en cuenta que el valor de Altura cambia automáticamente para mantener la relación de aspecto, es decir, la relación entre el ancho de la imagen y su altura, que es lo que desea. Alternativamente, puede establecer el valor de Altura y el Ancho cambiará automáticamente).

   8. Haga clic en Aceptar.

A continuación aprenderá cómo mejorar sus versiones en miniatura con algún texto explicativo.

10.2.4 Agregar subtítulos a imágenes
Es posible que prefieras que tu galería de fotos muestre solo las versiones en miniatura de cada imagen. Sin embargo, puedes hacer que la experiencia sea un poco más agradable para tus visitantes si proporcionas un breve título para cada imagen. El título no tiene que ser nada elaborado: solo un breve título o descripción de la foto.

Puedes agregar subtítulos de varias maneras, pero la más sencilla es pedirle a ChatGPT que convierta tu imagen en una figura y luego proporcione un subtítulo para la figura . Este es el HTML genérico que genera ChatGPT:

<figura>
    <img src=" archivo " alt=" descripción ">
    <figcaption> Texto del título </figcaption>
</figura>
Aquí Caption textestá el título, que aparece justo debajo de la imagen. Aquí hay un ejemplo de instrucciones para ChatGPT:

Agregue una imagen llamada "old-road-marker.jpg", que se almacena en el subdirectorio "images". Conviértala en una figura con un título. Para el atributo alt, utilice lo siguiente: "Una foto con un marcador de carretera muy antiguo en primer plano que dice 'Appleby 12 Miles'". Para el título, utilice lo siguiente: "Un marcador de carretera antiguo".
A continuación se muestra un ejemplo de figura y título generados por ChatGPT a partir de dicho mensaje:

<figura>
    <img src="imagenes/marcador-de-carretera-antiguo.jpg"
         alt="Una foto con un marcador de carretera muy antiguo en el
              primer plano que dice 'Appleby 12 Miles'">
    <figcaption>Un antiguo marcador de carretera</figcaption>
</figura>
La figura 10.6 muestra cómo se ve en el navegador.



Figura 10.6 Una figura con un título

Con sus versiones en miniatura creadas y sus títulos compuestos, está listo para ver cómo sus visitantes pueden ver la versión de tamaño grande de cada foto.

10.3 Implementación de una superposición de caja de luz
Como aprenderá en breve (consulte la sección 10.5), cuando alguien visita la galería de fotos, la página muestra al principio una cuadrícula de nueve imágenes en miniatura. ¿Cómo ve el usuario una versión de tamaño grande de una foto?

Hay muchas formas de resolver ese problema. Por ejemplo, puedes configurar cada imagen en miniatura como un enlace que, al hacer clic, carga la versión de tamaño grande de la foto. Ese enfoque funciona, pero al hacer clic en un enlace, el usuario sale de tu galería de fotos, por lo que debe volver a navegar para ver más fotos. Créeme, ¡nadie quiere tanto ver tus fotos!

Una mejor solución es pedirle a ChatGPT que cree un lightbox , que es un elemento especial que tiene las siguientes características:

Se crea sobre la marcha.

Ocupa todo el ancho y alto de la ventana del navegador.

Es ligeramente transparente.

Se muestra encima de la página web existente, por eso se llama "superposición".

Por ejemplo, la figura 10.7 muestra una versión simple de una galería de fotos con tres miniaturas. Cuando el usuario hace clic en una miniatura, sucede lo siguiente:

Se crea el elemento lightbox.

Al nuevo elemento lightbox se le asigna un imgelemento.

Ese imgelemento se rellena con la versión de gran tamaño de la foto.

La caja de luz se muestra superponiéndola en la página.



Figura 10.7 Una galería de fotos sencilla con tres miniaturas

El resultado es que el usuario ahora ve la versión de tamaño grande de la foto, que llena toda o casi toda la ventana del navegador. Por ejemplo, si hago clic en la miniatura que está más a la derecha en la figura 10.7, el navegador muestra una versión más grande de la foto, como se muestra en la figura 10.8. Observe que la galería aparece tenuemente en los espacios a la izquierda y a la derecha del cuadro de luz. Esto permite que el usuario sepa que no ha abandonado la galería. Para volver a la galería, el usuario solo tiene que hacer clic en cualquier parte de la página, lo que elimina el cuadro de luz y vuelve a mostrar la galería de fotos.



Figura 10.8 Al hacer clic en una miniatura se muestra el cuadro de luz, que contiene la versión más grande de la foto.

Si todo esto parece terriblemente complejo de codificar, recuerda que no tienes que mover un dedo más allá de preparar las imágenes en miniatura. Puedes pedirle a ChatGPT que implemente toda la funcionalidad de la caja de luz con una instrucción similar a la siguiente:

Proporcione el código HTML, CSS y JavaScript para implementar una superposición de estilo lightbox para las imágenes de esta página. Las miniaturas tienen nombres como image01-thumbnail.png, image02-thumbnail.png, image03-thumbnail.png, etc. Cada imagen de tamaño completo usa el mismo nombre que su miniatura pero sin "-thumbnail", como en image01.png, image02.png, image03.png, etc. Todos los archivos de imagen se almacenan en el subdirectorio "images".
El lector perspicaz habrá notado la instrucción de proporcionar “código JavaScript” en este mensaje. ¿De qué se trata? La siguiente sección resuelve el misterio.

10.4 La caja de luz: Desarrollado con JavaScript
Hasta este punto del libro, has visto que puedes llegar bastante lejos con solo HTML y CSS. Se trata de tecnologías potentes que, cuando se generan correctamente mediante ChatGPT con indicaciones detalladas, pueden producir páginas web atractivas y útiles.

Sin embargo, hay muchas cosas que HTML y CSS, por muy potentes que sean, no pueden hacer. Un lightbox es un buen ejemplo. Sí, puedes usar HTML y CSS para crear y darle estilo al lightbox, pero una vez que haces clic en una miniatura, HTML y CSS dejan de funcionar:

No pueden crear nuevos elementos.

No pueden cargar la versión de tamaño completo de la miniatura en la que se hizo clic en el imgelemento lightbox.

No pueden mostrar la caja de luz oculta.

No pueden eliminar el cuadro de luz cuando el usuario hace clic en él.

Afortunadamente, existe una tercera tecnología importante para páginas web que puede manejar este tipo de tareas y muchas más: JavaScript. Se trata de un lenguaje de programación integrado en el navegador web y diseñado para añadir interactividad y dinamismo a elementos de páginas web que de otro modo serían inertes. En este proyecto, JavaScript hace básicamente dos cosas:

Agrega un controlador de evento de “clic” a cada imagen. Un controlador de evento es un código JavaScript que se ejecuta automáticamente cuando ocurre un evento específico. En este caso, el evento es el clic del usuario en una imagen de la galería de fotos.

En el controlador de eventos, JavaScript crea y luego muestra el lightbox.

Afortunadamente para ti, eso es todo lo que necesitas saber. ChatGPT se encargará del resto.

10.5 Diseño de la galería con Flexbox
Cuando se añaden elementos a una página web, el comportamiento de diseño predeterminado para la mayoría de los elementos es que fluyan verticalmente hacia abajo en la página, un elemento tras otro. Esto ha funcionado bien para los proyectos que has visto hasta ahora en este libro, pero no funcionará para la galería de fotos. ¿Por qué no? Porque con las imágenes renderizadas como figuras, también fluirán verticalmente hacia abajo en la página, una tras otra.

No es el fin del mundo, sin duda, pero no es un buen aspecto y no resulta cómodo para quienes visitan tu página. La figura 10.9 muestra una versión de la galería de fotos en la que las fotos se muestran de esta manera.

Puede evitar este comportamiento predeterminado si le pide a ChatGPT que diseñe la galería de fotos utilizando una técnica de página web llamada Flexbox . Se trata de una tecnología compleja, pero todo lo que necesita saber por ahora es que cuando convierte un elemento de página web en un contenedor Flexbox, los elementos pierden su comportamiento de diseño predeterminado rígido y se adaptan a las dimensiones actuales del navegador. Para este proyecto, puede solicitarle a ChatGPT que use Flexbox con una instrucción simple:

Convierte la galería en un contenedor Flexbox. Centra el contenido y permite que se ajuste.
Para ver el resultado de esta instrucción, consulte el diseño final de la galería de fotos, que aparece más adelante, en la figura 10.10.

En este punto, ya sabes todo lo que se necesita para que ChatGPT cree una galería de fotos. La siguiente sección te guiará a través del proceso.



Figura 10.9 De forma predeterminada, las figuras de sus fotografías se colocarán verticalmente en la página, una tras otra.

10.6 Elaboración del mensaje para la galería de fotos
El proyecto de este capítulo es una página de galería de fotos que muestra nueve miniaturas de fotos, cada una de las cuales, al hacer clic en ella, muestra una versión de tamaño grande de la foto. Supongo que ya tienes un logotipo y un título para el sitio, sabes qué fuentes quieres usar para los encabezados y el texto de la página y tienes un esquema de colores listo para aplicar. Vuelve al capítulo 3 para aprender cómo solicitarle a ChatGPT sugerencias de título, tipografía y color.

Para iniciar su solicitud, dígale a ChatGPT que desea construir una página web y que desea que genere el código por usted:

Quiero crear una página web para una galería de fotos. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
Ahora, esboce el contenido de la página, elemento por elemento, incluyendo lo siguiente (consulte la figura 10.10):

Un encabezado que incluya su logotipo y el título del sitio.

Un elemento principal que comienza con el título de la página y va seguido de algunas instrucciones.

La galería de miniaturas de fotografías

Un pie de página que incluye un aviso de derechos de autor



Figura 10.10 Los elementos de la página de la galería de fotos

A continuación, solicite a ChatGPT que genere el CSS:

En segundo lugar, en un archivo separado, escriba el código CSS para lo siguiente:
A continuación, especifique el formato de la página, incluido lo siguiente:

El color de fondo de la página y el color del texto.

Los tamaños de fuente que desea utilizar para los encabezados y el texto de la página.

Las fuentes que se deben utilizar para los encabezados y el texto normal de la página.

¿Qué elementos deben ser contenedores Flexbox (en este proyecto, estos serán el encabezado, la galería y la superposición de lightbox)?

Por último, le indica a ChatGPT que proporcione el código HTML, CSS y JavaScript para una superposición estilo lightbox para mostrar las fotos de gran tamaño.

A continuación se muestra un ejemplo de solicitud para mi propia galería de fotos:

Quiero crear una página web para una galería de fotos. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
 * Un elemento de encabezado que incluye una imagen llamada logo.png, que se almacena en el subdirectorio "images", y el título "Ampersand Photography".
 * Una sección principal con el encabezado “Galería de fotos”.
 * Un párrafo con el texto "Haga clic en cada miniatura para ver la versión completa de la imagen. Para volver a la galería, haga clic en cualquier parte de la página".
 * Un elemento de galería que contiene las siguientes imágenes, cada una de las cuales se almacena en el subdirectorio "imágenes" y cada imagen se representa como una figura con el texto alternativo y el título especificados:
  * Una imagen llamada "image01-thumbnail.jpg" con el texto alternativo "Fotografía macro de un cactus" y la leyenda "Primer plano de un cactus".
  * Una imagen llamada "image02-thumbnail.jpg" con el texto alternativo "Un reflejo borroso de un tranvía que pasa y una persona caminando" y la leyenda "Escena de calle (automóvil)".
  * Una imagen llamada "image03-thumbnail.jpg" con el texto alternativo "Una foto con un marcador de carretera muy antiguo en primer plano que dice 'Appleby 12 Miles'" y la leyenda "Un marcador de carretera antiguo".
  * Una imagen llamada "image04-thumbnail.jpg" con el texto alternativo "Una foto tomada desde la cima de una colina en el Distrito de los Lagos, mirando hacia abajo a una ciudad y un lago" y la leyenda "Escena del Distrito de los Lagos".
  * Una imagen llamada "image05-thumbnail.jpg" con el texto alternativo "Una torre de Montreal fotografiada desde abajo a través de un agujero" y la leyenda "Arquitectura de Montreal".
  * Una imagen llamada "image06-thumbnail.jpg" con el texto alternativo "El techo ornamentado de una iglesia en Florencia, Italia" y la leyenda "Techo de una iglesia en Florencia".
  * Una imagen llamada "image07-thumbnail.jpg" con el texto alternativo "Un paraguas alegre, brillante y azul cielo colocado de manera improbable sobre un balcón sucio y lúgubre" y la leyenda "Un toque de color".
  * Una imagen llamada "image08-thumbnail.jpg" con el texto alternativo "Una cabeza grande y ornamentada, similar a la de Zeus, sobre las palabras 'Cabeza de Bronce'" y la leyenda "Cartel de cafetería".
  * Una imagen llamada "image09-thumbnail.jpg" con el texto alternativo "Una escultura de un pájaro de metal con su cabeza asomando desde un banco de nieve" y la leyenda "Pájaro que se esconde tras la nieve".
 * Un elemento de pie de página que incluye el símbolo de Copyright, seguido de "Ampersand Photography".
 * En la sección del encabezado de la página, incluya la etiqueta <meta charset="utf-8">.
 * En la sección del encabezado de la página, incluya la etiqueta <meta name="viewport" content="width=device-width, initial-scale=1">.
  
En segundo lugar, en un archivo separado escriba el código CSS para lo siguiente:
 *La página tiene fondo de color negro y sin margen.
 * El texto de la página utiliza un tamaño de fuente de 20 px, el color dorado y la fuente Libre Baskerville de Google Fonts.
 * El encabezado tiene color de fondo granate y relleno de 24 px.
 * Convierte el encabezado en un contenedor Flexbox con contenido centrado.
 * El título mide 64 px, está centrado, utiliza la fuente "cursiva" genérica y tiene un relleno de 16 px a la izquierda.
 *La sección principal tiene texto centrado y un margen de 24px.
 * El encabezado de la sección principal tiene un tamaño de fuente de 30 px y utiliza la fuente Montserrat de Google Fonts.
 * Convierte la galería en un contenedor Flexbox. Centra el contenido y permite que se ajuste.
 * El pie de página tiene color de fondo granate, relleno de 24 px y texto centrado.
  
En tercer lugar, proporcione el código HTML, CSS y JavaScript para implementar una superposición de estilo lightbox para las imágenes de la galería. Cada imagen de tamaño completo utiliza el mismo nombre que su miniatura, pero sin "-thumbnail". Por ejemplo, para el archivo de miniatura image01-thumbnail.jpg, el nombre del archivo de imagen de tamaño completo es image01.jpg.
En cada una de mis pruebas con este mensaje, ChatGPT generó este código en cuatro etapas:

ChatGPT generó una parte del código HTML (pero no todo, lo más importante). Cuando llegó el momento de generar los figureelementos, ChatGPT generó el código solo para la primera figura, seguido de un comentario similar a este:

<!-- repetir para cada imagen -->
¡No lo creo! Más tarde, utilicé el siguiente mensaje para pedirle a ChatGPT que me proporcionara el código HTML completo:

Proporcione el código HTML completo, incluidas todas las imágenes especificadas en la solicitud original.
Una vez hecho esto, guardé el código HTML completo como index.html. En ese archivo, deberías ver dos referencias a archivos externos:

La primera referencia está en la headsección y es para el archivo CSS; la referencia es una <link>etiqueta que debería verse así:

<link rel="hoja de estilo" tipo="texto/css" href="estilos.css">
La segunda referencia está cerca de la parte inferior del código HTML y es para el archivo JavaScript; la referencia es una <script>etiqueta que debería verse así:

<script src="script.js"></script>
ChatGPT generó el código para el CSS, que debes guardar con el mismo nombre de archivo que aparece en la <link>etiqueta (generalmente styles.css).

ChatGPT generó el código para JavaScript, que debes guardar con el mismo nombre de archivo que aparece en la <script>etiqueta (normalmente script.js)

ChatGPT generó más código CSS para la superposición de la caja de luz. Debes copiar ese código y pegarlo en la parte inferior de tu archivo CSS.

Utilicé la aplicación ChatGPT de OpenAI para enviar mi mensaje a GPT-4. El código generado generó la página que se muestra en la figura 10.11. Al hacer clic en una miniatura, se genera una versión más grande de la imagen, como se muestra en la figura 10.12.



Figura 10.11 Mi galería de fotos



Figura 10.12 Al hacer clic en una miniatura se muestra una versión de mayor tamaño de la foto.

Si está satisfecho con su página, puede omitir el resto de este capítulo e implementar el código en la web (consulte el apéndice B para saber cómo implementar su página). Sin embargo, si desea comprender el código de la página web generada, siga leyendo para obtener más información.

10.7 Examinar el código de la galería de fotos
Si desea tener al menos alguna idea de lo que ChatGPT generó en su nombre, las siguientes tres secciones le brindan una breve mirada al código HTML y CSS que sustenta la página de la galería de fotos mostrada anteriormente en la figura 10.11, así como el código JavaScript que habilita la superposición de caja de luz que se muestra en la figura 10.12.

NOTA: El código HTML y CSS generado para mi galería de fotos está disponible en el sitio web de este libro ( www.manning.com/books/build-a-website-with-chatgpt ) y en el repositorio de GitHub del libro: https://github.com/paulmcfe/websites-with-chatgpt .

Las anotaciones de código que siguen deberían ayudarle a comprender cómo funciona la galería de fotos y pueden facilitar la modificación o personalización de su propio código.

10.7.1 Examinar el HTML
Aquí hay una versión anotada del código HTML que ChatGPT produjo para mi galería de fotos:

<!DOCTYPE html>
<html lang="es">
<cabeza>
    <meta conjunto de caracteres="utf-8">
    <meta name="ventana gráfica"
        content="width=ancho-del-dispositivo, escala-inicial=1">                      ① 
    <link href="https://fonts.googleapis.com/css?                           ② 
        family=Montserrat|                                                  ② 
        Libre+Baskerville&display=swap"                                     ② 
        rel="hoja-de-estilo">                                                   ② 
    <link rel="hoja-de-estilo" href="styles.css">                               ③
    <title>Fotografía con signo &</title>
</cabeza>
<cuerpo>
    <header>                                                                ⑥ 
        <img src="images/logo.png"                                          ⑥ 
             alt="Logotipo de Ampersand Photography">                              ④⑥ 
        <h1>Ampersand Photography</h1>                                      ⑤⑥ 
    </header>                                                               ⑥
    <principal>
        <h2>Galería de fotos</h2>                                              ⑦ 
        <p>                                                                 ⑧ 
            Haga clic en cada miniatura para ver la versión completa de la imagen.      ⑧ 
            Para volver a la galería, haga clic en cualquier parte de la página.           ⑧ 
        </p>                                                                ⑧ 
        <div class="gallery">                                               ⑫ 
            <figure>                                                        ⑪⑫
                <img src="images/image01-thumbnail.jpg"                     ⑨⑪⑫ 
                     alt="Fotografía macro de un cactus"                     ⑨⑪⑫ 
                     class="thumbnail">                                     ⑨⑪⑫ 
                <figcaption>Primer plano de un cactus</figcaption>                    ⑩⑪⑫ 
            </figure>                                                       ⑪⑫ 
            <figure>                                                        ⑫ 
                <img src="images/image02-thumbnail.jpg"                     ⑫ 
                     alt="Un reflejo borroso de un tranvía que pasa        ⑫ 
                         y una persona caminando"                              ⑫ 
                     class="thumbnail">                                     ⑫ 
                <figcaption>Escena de la calle (automóvil)</figcaption>                  ⑫ 
            </figure>                                                       ⑫ 
            <figure>                                                        ⑫ 
                <img src="images/image03-thumbnail.jpg"                     ⑫ 
                     alt="Una foto con una carretera muy antigua marcador en        primer plano ⑫ 
                         que dice 'Appleby 12 Miles'"          ⑫ 
                     class="thumbnail">                                     ⑫ 
                <figcaption>Un antiguo marcador de carretera</figcaption>                 ⑫ 
            </figure>                                                       ⑫ 
            <figure>                                                        ⑫ 
                <img src="images/image04-thumbnail.                    jpg" ⑫ 
                     alt="Una foto tomada desde lo alto de una colina en el Distrito de los Lagos,     mirando 
                         hacia abajo a una ciudad y un lago"            ⑫ 
                     class="thumbnail">                                     ⑫ 
                <figcaption>Escena del Distrito de los Lagos</figcaption>                ⑫ 
            </figure>                                                       ⑫ 
            <figure>                                                        ⑫ 
                <img src="images/image05-thumbnail.jpg"                     ⑫ 
                     alt="Una torre de Montreal tomada desde abajo a través de un agujero" ⑫
                     class="thumbnail">                                     ⑫ 
                <figcaption>Arquitectura de Montreal</figcaption>              ⑫ 
            </figure>                                                       ⑫ 
            <figure>                                                        ⑫ 
                <img src="images/image06-thumbnail.jpg"                     ⑫ 
                     alt="El techo ornamentado de una iglesia en Florencia,       ⑫ 
                         Italia"                                             ⑫ 
                     class="thumbnail">                                     ⑫ 
                <figcaption>Techo de una iglesia en Florencia</figcaption>         ⑫ 
            </figure>                                                       ⑫ 
            <figure>                                                        ⑫ 
                <img src="images/image07-thumbnail.jpg"                     ⑫ 
                     alt="Una alegre y brillante sombrilla azul cielo colocada     ⑫ 
                         improbablemente en un balcón sucio y lúgubre."             ⑫ 
                     class="thumbnail">                                     ⑫ 
                <figcaption>Un toque de color</figcaption>                    ⑫ 
            </figure>                                                       ⑫ 
            <figure>                                                        ⑫ 
                <img src="images/image08-thumbnail.jpg"                     ⑫ 
                     alt="Una cabeza grande y ornamentada, similar a la de Zeus, sobre las palabras    ⑫ 
                         'Cabeza de Bronce'"                                     ⑫ 
                     class="thumbnail">                                     ⑫ 
                <figcaption>Letrero de cafetería</figcaption>                   ⑫ 
            </figure>                                                       ⑫ 
            <figure>                                                        ⑫ 
                <img src="images/image09-thumbnail.                    jpg" ⑫ 
                     alt="Una escultura de pájaro de metal con su cabeza asomando      ⑫ 
                         de un banco de nieve"                                ⑫ 
                     class="thumbnail">                                     ⑫
                <figcaption>Pájaro que hace de cucú</figcaption>                    ⑫ 
            </figure>                                                       ⑫ 
        </div>                                                              ⑫
    </principal>
    <footer>                                                                ⑬ 
        © Fotografía comercial                                        ⑬ 
    </footer>                                                               ⑬
  
    <script src="script.js"></script>                                       ⑭
</cuerpo>
</html>
① Ayuda a que la página se muestre correctamente en dispositivos móviles

② Carga las fuentes Montserrat y Libre Baskerville desde Google Fonts

③ Le dice al navegador web dónde encontrar el código CSS

④ Logotipo del sitio

⑤ Título del sitio

⑥ Encabezado de página

⑦ Título de la página

⑧ Párrafo de instrucción

⑨ Imagen de la figura

⑩ Título de la figura

⑪ Figura de la galería de fotos

⑫ Galería de fotos

⑬ Pie de página

⑭ Le dice al navegador web dónde encontrar el código JavaScript

Tenga en cuenta que el código HTML incluye la siguiente línea:

<link rel="hoja de estilo" href="estilos.css">
Esta etiqueta le dice al navegador web dónde encontrar el código CSS, que describo en la siguiente sección.

10.7.2 Examinar el CSS
Aquí hay una versión anotada del código CSS que ChatGPT produjo para mi galería de fotos:

cuerpo {                                         ① 
    color de fondo: negro;                   ① 
    margen: 0;                                 ① 
    tamaño de fuente: 20px;                           ① 
    color: dorado;                               ① 
    familia de fuentes: 'Libre Baskerville', serif;   ① 
}                                              ①
  
encabezado {
    color de fondo: granate;                  ② 
    relleno: 24px;                             ② 
    pantalla: flex;                             ③ 
    justificar contenido: centrar;                   ③ 
    alinear elementos: centrar;                       ③
}
  
h1 {
    tamaño de fuente: 64px;                           ④ 
    familia de fuentes: cursiva;                      ④ 
    relleno izquierdo: 16px;                        ④
}
 
h2 {
    tamaño de fuente: 30px;                           ⑤ 
    familia de fuentes: 'Montserrat', sans-serif;     ⑤
}
  
principal {
    margen: 24px;                              ⑥ 
    alineación del texto: centro;                        ⑥
}
  
.galería {
    pantalla: flex;                             ⑦ 
    flex-wrap: ajustar;                           ⑦ 
    justificar-contenido: centrar;                   ⑦ 
    alinear-elementos: centrar;                       ⑦
}
  
pie de página {
    color de fondo: granate;                  ⑧ 
    relleno: 24px;                             ⑧ 
    alineación del texto: centro;                        ⑧
}
.overlay {                                     ⑬ 
    posición: fija;                           ⑨⑬ 
    superior: 0;                                    ⑨⑬ 
    izquierda: 0;                                   ⑨⑬ 
    ancho: 100%;                               ⑩⑬ 
    alto: 100%;                              ⑩⑬ 
    color de fondo: rgba(0, 0, 0, 0.8);      ⑪⑬ 
    visualización: flexible;                             ⑫⑬ 
    contenido justificado: centrado;                   ⑫⑬ 
    elementos alineados: centrado;                       ⑫⑬ 
}                                              ⑬
  
.superposición img {
    ancho máximo: 90%;                            ⑭ 
    alto máximo: 90%;                           ⑭ 
}
① Diseña el color de fondo de la página, el margen, el tamaño del texto, el color del texto y la fuente.

② Diseña el color de fondo y el relleno del encabezado

③ Establece el encabezado como un contenedor Flexbox con contenido centrado

④ Diseña el tamaño de fuente del título de la página, la fuente y el relleno izquierdo.

⑤ Diseña el tamaño de fuente y la fuente del título de la página.

⑥ Aplica estilo al elemento principal con un margen y centra el texto.

⑦ Establece la galería como un contenedor Flexbox con contenido centrado y envoltura.

⑧ Aplica estilo al color de fondo y al relleno del pie de página y centra el texto.

⑨ Ubicado en la esquina superior izquierda de la ventana.

⑩ Ocupa todo el ancho y la altura

⑪ Ligeramente transparente

⑫ Contenedor Flexbox con contenido centrado

⑬ Da estilo a la superposición de la caja de luz

⑭ Diseña la imagen más grande para utilizar el 90 % del ancho y la altura del lightbox

En la lista de códigos HTML de antes en este capítulo, observe la siguiente línea cerca de la parte inferior:

<script src="script.js"></script>
Esta etiqueta le dice al navegador web dónde encontrar el código JavaScript, que anoto en la siguiente sección.

10.7.3 Examinando el JavaScript
Si tienes cuidado, está bien hacer pequeños ajustes al código HTML y CSS. Sin embargo, te recomiendo encarecidamente que no toques el código JavaScript de ChatGPT. El código es complejo y una edición imprudente podría hacer que el lightbox quede inutilizable.

Sin embargo, si conoces un poco de JavaScript, quizás te interese saber cómo ChatGPT resolvió el problema del lightbox. Aquí tienes una versión comentada del código JavaScript que ChatGPT generó para mi galería de fotos:

documento.addEventListener('DOMContentLoaded',
    función() {                                               ①
  
    const miniaturas = document.querySelectorAll(
        ②                                         ​
  
    miniaturas.paraCada((miniatura) => {                         ③
  
        miniatura.addEventListener('clic',
            función (e) {                                      ④
  
            constante nombreImagen = e.target.src.split('/')
                .pop().replace('-miniatura', '');               ⑤
  
            const superposición = document.createElement('div');      ⑥
  
            superposición.classList.add('superposición');                   ⑦
  
            constante img = document.createElement('img');          ⑧
  
            img.src = `imágenes/${imageName}`;                    ⑨
  
            superposición.appendChild(img);                           ⑩
  
            documento.cuerpo.appendChild(superposición);                 ⑪
  
            superposición.addEventListener('click', función () {     ⑫ 
                document.body.removeChild(superposición);             ⑫ 
            });                                                 ⑫
        });
    });
});
① Ejecuta el código de función que sigue una vez que se ha cargado la página

② Almacena todas las miniaturas

③ Itera a través de las miniaturas

④ Agrega un controlador de evento de "clic" a la miniatura actual

⑤ Extrae el nombre del archivo de la imagen de tamaño completo

⑥ Crea un nuevo elemento para la superposición de la caja de luz

⑦ Agrega la clase de superposición al nuevo elemento

⑧ Crea un nuevo elemento img

⑨ Establece el nombre del archivo de imagen de tamaño completo como la fuente de la nueva imagen

⑩ Agrega la imagen a la superposición de la caja de luz.

⑪ Agrega la superposición de caja de luz a la página

⑫ Agrega un controlador de evento de "clic" al cuadro de luz que elimina el cuadro de luz de la página

Si lo desea, puede utilizar las anotaciones HTML y CSS de las dos secciones anteriores para ayudar a personalizar el código de su página web, como describo en la siguiente sección.

10.8 Personalización de la galería de fotos
Utilizando las anotaciones de las secciones anteriores como guía, te mostraré algunas personalizaciones de código relativamente simples que puedes hacer abriendo los archivos HTML y CSS en tu editor de texto. Sin embargo, si tu página no se parece en nada a lo que quieres, es mejor que reescribas el mensaje y lo envíes a ChatGPT en una nueva sesión.

Para el código HTML, aquí hay algunas personalizaciones sugeridas:

Puedes editar el poco texto que hay en la página, incluido el título, el encabezado y el texto de instrucciones. Solo asegúrate de editar solo el texto y no las etiquetas HTML que lo rodean (como las etiquetas <figcaption>y </figcaption>alrededor de cada título de figura).

No dudes en cambiar el texto alternativo de cualquier imagen editando el valor del atributo imgde esa etiqueta alt. Asegúrate de no eliminar por accidente las comillas dobles que rodean el altvalor.

Si desea incluir un segundo párrafo introductorio, coloque el cursor de edición después de la </p>etiqueta que finaliza el párrafo introductorio existente. Presione Enter o Return para comenzar una nueva línea, escriba una <p>etiqueta, escriba el texto del párrafo y finalice con una </p>etiqueta.

Es posible que desees desarrollar tu sitio creando varias galerías de fotos (o lo que sea), con cada página dedicada a un tema o categoría en particular. Pídele a ChatGPT que cree una página a la vez, modificando el mensaje según sea necesario. Si eliges esta opción, necesitarás un elemento de navegación que permita a los usuarios visitar cada página. Consulta el capítulo 6 para aprender a solicitarle a ChatGPT enlaces y una barra de navegación.

En la sección de pie de página del código HTML, puedes agregar enlaces a tus cuentas de redes sociales, como describo en el capítulo 4.

A continuación se muestran algunas ideas de personalización para el código CSS:

Para utilizar otro color de fondo de página, especifique una palabra clave de color diferente para la propiedad bodydel elemento background-color.

Para utilizar otro color de fondo para el encabezado y el pie de página, especifique una nueva palabra clave de color para la propiedad de los elementos headery .footerbackground-color

Para utilizar un color diferente para el texto de la página, especifique una palabra clave de color diferente para la propiedad bodydel elemento color.

Para ajustar la transparencia de la superposición de la caja de luz, edite la propiedad .overlayde la clase background-color. En concreto, modifique el valor final en la rgba()función, donde 1.0es completamente opaco y 0.0es completamente transparente.

Para cualquier valor de tamaño de fuente, puede cambiar el número para aumentar o disminuir el tamaño de la fuente. Solo asegúrese de dejar la pxunidad en su lugar.

Para cualquier valor de margen o relleno, puede cambiar el número para aumentar o disminuir el relleno o los márgenes. En cada caso, asegúrese de dejar la pxunidad en su lugar.

Para que el código de tu página sea más accesible, considera convertir todas las medidas en px a medidas en rem. 1 rem equivale de manera predeterminada a 16 px, por lo que 20 px son 1,25 rem, 24 px son 1,5 rem, 32 px son 2 rem, 48 px son 3 rem, y así sucesivamente. La unidad rem es más accesible porque mide los tamaños de fuente en relación con el tamaño de fuente predeterminado que el usuario del navegador ha definido en la configuración de su navegador.

Resumen
En HTML, se utiliza el imgelemento para indicarle al navegador web que inserte un archivo de imagen externo en la página.

En la <img>etiqueta, use el srcatributo para indicarle al navegador dónde encontrar el archivo de imagen; use el altatributo para agregar una frase corta que describa la imagen, particularmente para personas que usan lectores de pantalla y aplicaciones Braille.

Al trabajar con miniaturas de imágenes, es mejor crear un archivo de miniatura separado que tenga las dimensiones más pequeñas que desea utilizar.

Para incluir un título, rodee el imgelemento con un figureelemento y agregue el título al figcaptionelemento.

Una superposición de caja de luz es un elemento de página web creado sobre la marcha para mostrar una versión de gran tamaño de una miniatura en la que se hizo clic.

Cuando no desea que los elementos de la página estén dispuestos verticalmente en la página, convierta el elemento en un contenedor Flexbox.

Para obtener mejores resultados, el mensaje de su página debe ser lo más específico posible, incluidos colores, tamaños de fuente y niveles de encabezado.

Guarde el HTML generado en el archivo index.html y el CSS generado en el nombre de archivo sugerido por ChatGPT en el código HTML, generalmente styles.css.
