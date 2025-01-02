# 10 Configuración de una galería de fotos

Este capítulo cubre

* Uso de imágenes en una página web
* Trabajar con versiones en miniatura(thumbnail) de imágenes
* Visualización de imágenes en una lightbox
* Diseño de una página con Flexbox
* Elaboración de un prompt de ChatGPT para crear una página de galería de fotos
* Examinar y personalizar el código generado por ChatGPT

Después de aprender algunos conceptos básicos sobre imágenes en el capítulo 4, los proyectos de este libro han incluido principalmente una sola imagen: el logotipo de un sitio en el encabezado de la página. Es un buen comienzo, pero sin duda sabrá por sus propios viajes por Internet que las imágenes están por todas partes en la web. Una foto o ilustración bien ubicada y bien elegida puede animar una página y ofrecer un atractivo visual para los visitantes cansados ​​del texto.

En este capítulo, aprenderá un poco más sobre las imágenes y cómo funcionan en la web, lo que le permitirá incorporar imágenes adicionales en sus páginas. Como dice el dicho, “a lo grande o váyase a casa”, por eso, en este capítulo, las imágenes son importantes y no solo le mostrarán cómo crear una galería de fotos funcional que pueda usar para mostrar sus habilidades fotográficas, sino también cómo usar una técnica de diseño moderna para que su página se vea increíble. Luego, pondrá en práctica todo este conocimiento sobre imágenes y listas de diseño para crear un mensaje detallado para que ChatGPT genere el código para la galería de fotos.

Este capítulo también proporciona versiones comentadas del código HTML y CSS generados por ChatGPT para ayudarte a entender cómo funciona la galería de fotos. También recibirás algunos consejos útiles para personalizar el código.

## 10.1 Revisando el proyecto de este capítulo

Como mencioné en la introducción, el proyecto de este capítulo es una galería de fotos de una sola página. La página final incluirá los siguientes componentes:

* Un elemento de encabezado que incluye el logotipo y el título del sitio web.
* Un elemento principal que comienza con el título de la galería y las instrucciones para usar la galería.
* Nueve versiones de tamaño reducido de las fotografías, donde al hacer clic en una de estas imágenes se muestra una versión de tamaño más grande de la imagen.
* Un elemento de pie de página que incluye un aviso de derechos de autor

La figura 10.1 muestra un ejemplo de galería de fotos creada con el código proporcionado por ChatGPTPuedes utilizar este tipo de diseño para otros tipos de contenido, como un catálogo de productos, un portafolios de artistas, un muestrario de diseños o una galería de proyectos actuales o finalizados, miembros del equipo, próximos eventos, testimonios o clientes. El denominador común de todos estos proyectos es que consisten en una colección de imágenes (quizás también con algo de texto), por lo que necesitas saber un poco más sobre cómo funcionan las imágenes en la web.

![image](https://github.com/user-attachments/assets/dc6fb5c9-00fd-4df7-a7df-243688163ab2)

**Figura 10.1 Una galería de fotos generada por ChatGPT**

## 10.2 Una mirada más cercana a las imágenes

Si ha utilizado un procesador de textos o un programa de presentaciones, probablemente haya creado muchos documentos que incluyen imágenes. En cada caso, la aplicación ofrece algo así como un comando Insertar imagen que le permite elegir la imagen que desea, que se agrega directamente al documento en el lugar que elija.

Sorprendentemente, el código de una página web no funciona de la misma manera. No existe un equivalente en HTML del comando Insertar imagen que inserta una imagen directamente en la página. En su lugar, se carga la imagen en el sitio web como un archivo independiente y luego se inserta en el texto de la página una etiqueta HTML especial que le indica al navegador dónde ubicar la imagen. Cuando el navegador encuentra esta etiqueta, recupera el archivo de imagen del servidor y muestra la imagen en la página en la ubicación que se especificó.

### 10.2.1 Comprobación de la etiqueta `<img>`

La etiqueta especial que hace que el navegador agregue una imagen a una página web es la <img>etiqueta , que utiliza la sintaxis parcial que se muestra en la figura 10.2.

![image](https://github.com/user-attachments/assets/cebaa805-8a52-4f56-8e68-f28da259b37c)

**Figura 10.2 Inserta una imagen en una página web utilizando la etiqueta `<img>`.**

Esta versión del elemento `img` tiene dos atributos:

* `src="file"`: Para el atributo `src`(abreviatura de *source*), se reemplaza `file` con la ubicación del archivo de imagen. Para simplificar, solo voy a mostrar las dos posibilidades más comunes:

   * Si el archivo de imagen se encuentra en el mismo directorio que el archivo HTML, reemplácelo `file` con el nombre del archivo de imagen. Por ejemplo, si el archivo de imagen es `logo.png`, la etiqueta `<img>` se verá así:

   ```html
   <img src="logo.png" alt="">
   ```

   * Si la imagen está en un subdirectorio, reemplácela `file` con el nombre del directorio y el nombre del archivo de la imagen, separados por una barra invertida (`/`). Por ejemplo, si ha creado un subdirectorio llamado images y su archivo de imagen es `logo.png`, su etiqueta `<img>` se verá así:

   ```html
   <img src="images/logo.png" alt="">
   ```

* `alt="description"`: Para el atributo `alt`(abreviatura de *alternative - alternative*), se reemplaza `description` con una palabra o frase corta que describa la imagen; esto se puede usar en lugar de la imagen si no se puede mostrar el archivo de imagen. El texto alternativo (como se lo suele llamar) también lo usan los lectores de pantalla y las aplicaciones Braille para darles a sus usuarios una idea de qué es la imagen. Aquí hay un ejemplo:

```html
<img src="images/logo.png" alt="Ampersand Photography logo">
```

Técnicamente, su página web no es válida a menos que cada etiqueta `<img>` tenga un atributo `alt` presente. Tener una página no válida significa que su página puede no visualizarse correctamente en el navegador web, pero principalmente significa que su página será menos accesible para personas que usan tecnologías de asistencia como lectores de pantalla. Afortunadamente, las etiquetas `<img>` generadas por ChatGPT generalmente incluyen el atributo `alt`, pero la descripción casi siempre es trivial y poco útil. Por lo tanto, siempre debe incluir el texto `alt` que desea en su mensaje. Aquí hay un ejemplo de instrucción para ChatGPT:

```text
Add an image named "old-road-marker.jpg", which is stored in the "images" subdirectory. For the alt attribute, use the following: "A photo with a very old road marker in the foreground that reads 'Appleby 12 Miles'".
```

```text
Agregue una imagen llamada "old-road-marker.jpg", que se almacena en el subdirectorio "images". Para el atributo alt, utilice lo siguiente: "Una foto con un marcador de carretera muy antiguo en primer plano que dice 'Appleby 12 Miles'".
```

A continuación se muestra un ejemplo de etiqueta `<img>` generada por ChatGPT a partir de dicho mensaje:

```html
<img src="images/old-road-marker.jpg" 
     alt="A photo with a very old road marker in the 
     foreground that reads 'Appleby 12 Miles'">
```

**TIP**: Si tu página utiliza imágenes decorativas o no esenciales, establece el atributo `alt` como la cadena vacía (`""`). De esa manera, tu página seguirá siendo válida, pero no molestarás a las personas que usan tecnología de asistencia (como lectores de pantalla) y que no quieren escuchar descripciones de imágenes puramente decorativas.

Si aún no tiene la imagen que desea utilizar pero conoce las dimensiones finales de la imagen, puede insertar una imagen de marcador de posición para que ocupe el mismo espacio en la página hasta que la imagen esté lista para usarse. La sección de red proporciona los detalles.

### 10.2.2 Agregar placeholder images

Probablemente sepas que, en el mundo del texto, un placeholder es un texto que marca temporalmente un lugar donde aparecerá una palabra o frase permanente. En la sección anterior, por ejemplo, la sintaxis para la etiqueta `<img>` utilizó los placeholder(marcadores de posición) `file ` y `description` para los valores de los atributos `src` y `alt`, respectivamente.

También puedes usar placeholder con imágenes. En este caso, la imagen del marcador de posición ocupa la misma cantidad de espacio que la imagen permanente que se agregará eventualmente a la página, lo que resulta muy útil si quieres crear tu página pero no tienes la imagen (o imágenes) que necesitas.

Hay varias formas de agregar placeholder images, pero la más sencilla es usar un servidor de marcador de posición, como https://placehold.co . Aquí hay un ejemplo de instrucciones para que ChatGPT agregue una placeholder image:

```text
Insert a placeholder image from placehold.co. The image dimensions are width 300px and height 200px.
```

```text
Insertar una imagen de marcador de posición desde placehold.co. Las dimensiones de la imagen son 300 px de ancho y 200 px de alto.
```

A continuación se muestra un ejemplo de etiqueta `<img>` generada por ChatGPT a partir de este mensaje:

```html
<img src="https://placehold.co/300x200" alt="Placeholder image" width="300" height="200">
```

La figura 10.3 muestra cómo aparece este placeholder en una página web.

![image](https://github.com/user-attachments/assets/6f6fc9eb-3458-4067-9491-e048a778c976)

**Figura 10.3 Un ejemplo de placeholder image de placehold.co**

### 10.2.3 Trabajar con image thumbnails - miniaturas de imágenes

Para mostrar realmente sus fotografías, debe mostrarlas en un tamaño relativamente grande. Sin embargo, según el formato del archivo (consulte el capítulo 4) y otros factores, como la cámara que utilizó, el archivo de tamaño completo puede ser bastante grande, al menos varios megabytes. Eso es bastante malo para una sola imagen, pero su galería de fotos tendrá varias imágenes (nueve en este proyecto); es pedir demasiado que los visitantes de la galería descarguen una cantidad tan enorme de datos. (Esto es especialmente cierto para las personas que acceden a su página a través de una conexión a Internet lenta o un plan de datos móviles limitado).

En el caso de un proyecto como una galería de fotos, una mejor estrategia para todos los usuarios es mostrar inicialmente una versión reducida (conocida en el sector como *thumbnail-miniatura*) de cada foto. La idea es configurar la página de modo que al hacer clic en una miniatura se muestre temporalmente una versión de tamaño grande de la foto (el tamaño que ve el usuario depende de las dimensiones de la ventana del navegador).

**NOTA**: No existen reglas estrictas sobre el tamaño de las miniaturas. Una página diseñada para albergar docenas de imágenes puede utilizar miniaturas de solo 50 o 75 píxeles de ancho, mientras que para una galería de fotos como la que ChatGPT te ayudará a crear en este capítulo, las miniaturas de alrededor de 300 píxeles de ancho funcionan bien.

Antes de continuar, debes crear versiones en miniatura de tus fotos. En primer lugar, las instrucciones de Windows.

#### Cómo crear una miniatura con la aplicación Fotos de Windows

Si usa Windows 11, puede hacer una copia del archivo de la foto original y luego usar la aplicación Fotos para cambiar el tamaño de la copia a las dimensiones de miniatura que prefiera. En este proyecto, supongo que las versiones en miniatura incluyen el texto -thumbnail como parte del nombre del archivo. Por ejemplo, si la versión de tamaño completo se llama image01.jpg, su versión en miniatura se llamará `image01-thumbnail.jpg`.

Siga estos pasos para crear una versión en miniatura de una foto usando la aplicación Fotos:

   1. Utilice el Explorador de archivos para localizar la foto con la que desea trabajar.

   2. Haga clic en el archivo, haga clic en Copiar en la barra de herramientas y luego haga clic en Pegar para crear una copia de la foto.

   3. Haga clic en el archivo copiado, haga clic en Cambiar nombre (o presione F2) y luego edite el nombre del archivo para eliminar el texto -Copiar agregado por Windows y reemplazarlo por -thumbnail. (De esta manera, debería terminar con un nombre de archivo similar a `image01-thumbnail.jpg`).

   4. Haga doble clic en el archivo de imagen copiado y renombrado para cargar la imagen en la aplicación Fotos.

   5. Haga clic en Ver más (los tres puntos en la barra de herramientas) y luego haga clic en Cambiar tamaño de imagen para abrir el cuadro de diálogo Cambiar tamaño, que se muestra en la figura 10.4.

![image](https://github.com/user-attachments/assets/ad4f61bf-7368-4ff2-8fb4-1b41ecfdf2c3)

**Figura 10.4 Utilice el cuadro de diálogo Cambiar tamaño para crear una versión en miniatura de su foto.**

   6. Asegúrese de que la opción Píxeles esté seleccionada.

   7. Utilice el cuadro de texto Ancho para establecer el ancho de la miniatura en píxeles. (Tenga en cuenta que el valor de Altura cambia automáticamente para mantener la relación de aspecto, es decir, la relación entre el ancho de la imagen y su altura, que es lo que desea. Alternativamente, puede establecer el valor de Altura y el Ancho cambiará automáticamente).

   8. Haga clic en Guardar.

Si usa una Mac en lugar de una PC con Windows, su versión de los pasos es la siguiente.

#### Cómo crear una miniatura con la aplicación Vista previa de macOS

Si utiliza macOS, puede usar Finder para copiar el archivo de la foto original y luego usar Vista previa para cambiar el tamaño de la copia al ancho y alto de miniatura que prefiera. Este proyecto supone que las copias en miniatura incluyen el texto `-thumbnail` en el nombre del archivo. Por ejemplo, si el archivo de la foto de tamaño completo se llama `image01.jpg`, la versión en miniatura debe llamarse `image01-thumbnail.jpg`.

Siga estos pasos para crear una versión en miniatura de una foto en macOS:

   1. Utilice el Finder para localizar y hacer clic en la foto con la que desea trabajar.

   2. Seleccione Editar > Copiar y luego seleccione Editar > Pegar para crear una copia de la foto.

   3. Haga clic en el archivo copiado, presione Entrar y luego edite el nombre del archivo para eliminar el texto copiado agregado por Finder y reemplazarlo con `-thumbnail`. (De esta manera, debería terminar con un nombre de archivo como `image01-thumbnail.jpg`).

   4. Haga doble clic en el archivo de imagen copiado y renombrado para cargar la imagen en Vista previa.

   5. Elija Herramientas > Ajustar tamaño para abrir el cuadro de diálogo que se muestra en la figura 10.5.

![image](https://github.com/user-attachments/assets/e07664ad-faa3-4ffa-9267-71ee7fd17431)

Figura 10.5 Utilice este cuadro de diálogo para crear una versión en miniatura de su foto.

   6. Asegúrese de que el elemento Píxeles esté seleccionado en la lista a la derecha de los cuadros de texto Ancho y Alto.

   7. Utilice el cuadro de texto Ancho para establecer el ancho de la miniatura en píxeles. (Tenga en cuenta que el valor de Altura cambia automáticamente para mantener la relación de aspecto, es decir, la relación entre el ancho de la imagen y su altura, que es lo que desea. Alternativamente, puede establecer el valor de Altura y el Ancho cambiará automáticamente).

   8. Haga clic en Aceptar.

A continuación aprenderá cómo mejorar sus versiones en miniatura con algún texto explicativo.

### 10.2.4 Agregar subtítulos a imágenes

Es posible que prefieras que tu galería de fotos muestre solo las versiones en miniatura de cada imagen. Sin embargo, puedes hacer que la experiencia sea un poco más agradable para tus visitantes si proporcionas un breve título para cada imagen. El título no tiene que ser nada elaborado: solo un breve título o descripción de la foto.

Puedes agregar subtítulos de varias maneras, pero la más sencilla es pedirle a ChatGPT que convierta tu imagen en una figura y luego proporcione un subtítulo para la figura . Este es el HTML genérico que genera ChatGPT:

```html
<figure>
    <img src="file" alt="description">
    <figcaption>Caption text</figcaption>
</figure>
```

Aquí `Caption text` está el título, que aparece justo debajo de la imagen. Aquí hay un ejemplo de instrucciones para ChatGPT:

```text
Add an image named "old-road-marker.jpg", which is stored in the "images" subdirectory. Make it a figure with a caption. For the alt attribute, use the following: "A photo with a very old road marker in the foreground that reads 'Appleby 12 Miles'". For the caption, use the following: "An old road marker".
```

```text
Agregue una imagen llamada "old-road-marker.jpg", que se almacena en el subdirectorio "images". Conviértala en una figura con un título. Para el atributo alt, utilice lo siguiente: "Una foto con un marcador de carretera muy antiguo en primer plano que dice 'Appleby 12 Miles'". Para el título, utilice lo siguiente: "Un marcador de carretera antiguo".
```

A continuación se muestra un ejemplo de figura y título generados por ChatGPT a partir de dicho mensaje:

```html
<figure>
    <img src="images/old-road-marker.jpg" 
         alt="A photo with a very old road marker in the 
              foreground that reads 'Appleby 12 Miles'">
    <figcaption>An old road marker</figcaption>
</figure>
```

La figura 10.6 muestra cómo se ve en el navegador.

![image](https://github.com/user-attachments/assets/2c2d48f5-4b2d-43da-b796-73d6b560edf1)

**Figura 10.6 Una figura con un título**

Con sus versiones en miniatura creadas y sus títulos compuestos, está listo para ver cómo sus visitantes pueden ver la versión de tamaño grande de cada foto.

## 10.3 Implementación de una superposición de caja de luz - lightbox overlay

Como aprenderá en breve (consulte la sección 10.5), cuando alguien visita la galería de fotos, la página muestra al principio una cuadrícula de nueve imágenes en miniatura. ¿Cómo ve el usuario una versión de tamaño grande de una foto?

Hay muchas formas de resolver ese problema. Por ejemplo, puedes configurar cada imagen en miniatura como un enlace que, al hacer clic, carga la versión de tamaño grande de la foto. Ese enfoque funciona, pero al hacer clic en un enlace, el usuario sale de tu galería de fotos, por lo que debe volver a navegar para ver más fotos. Créeme, ¡nadie quiere tanto ver tus fotos!

Una mejor solución es pedirle a ChatGPT que cree un *lightbox*, que es un elemento especial que tiene las siguientes características:

* Se crea sobre la marcha.

* Ocupa todo el ancho y alto de la ventana del navegador.

* Es ligeramente transparente.

* Se muestra encima de la página web existente, por eso se llama "superposición".

Por ejemplo, la figura 10.7 muestra una versión simple de una galería de fotos con tres miniaturas. Cuando el usuario hace clic en una miniatura, sucede lo siguiente:

1. Se crea el elemento lightbox.

2. Al nuevo elemento lightbox se le asigna un elemento `img`.

3. Ese elemento `img` se rellena con la versión de gran tamaño de la foto.

4. La lightbox se muestra superponiéndola en la página.

![image](https://github.com/user-attachments/assets/0e6dc295-ab4d-4507-b605-39c8aec036a8)

**Figura 10.7 Una galería de fotos sencilla con tres miniaturas**

El resultado es que el usuario ahora ve la versión de tamaño grande de la foto, que llena toda o casi toda la ventana del navegador. Por ejemplo, si hago clic en la miniatura que está más a la derecha en la figura 10.7, el navegador muestra una versión más grande de la foto, como se muestra en la figura 10.8. Observe que la galería aparece tenuemente en los espacios a la izquierda y a la derecha del cuadro de luz. Esto permite que el usuario sepa que no ha abandonado la galería. Para volver a la galería, el usuario solo tiene que hacer clic en cualquier parte de la página, lo que elimina el cuadro de luz y vuelve a mostrar la galería de fotos.

![image](https://github.com/user-attachments/assets/9512a9f7-9d64-47ed-8f2e-e9e3b5794546)

**Figura 10.8 Al hacer clic en una miniatura se muestra el cuadro de luz, que contiene la versión más grande de la foto.**

Si todo esto parece terriblemente complejo de codificar, recuerda que no tienes que mover un dedo más allá de preparar las imágenes en miniatura. Puedes pedirle a ChatGPT que implemente toda la funcionalidad de la caja de luz con una instrucción similar a la siguiente:

```text
Please provide the HTML, CSS, and JavaScript code to implement a lightbox-style overlay for the images on this page. The thumbnails have names such as image01-thumbnail.png, image02-thumbnail.png, image03-thumbnail.png, and so on. Each full-size image uses the same name as its thumbnail but without "-thumbnail", as in image01.png, image02.png, image03.png, and so on. All the image files are stored in the "images" subdirectory.
```

```text
Proporcione el código HTML, CSS y JavaScript para implementar una superposición de estilo lightbox para las imágenes de esta página. Las miniaturas tienen nombres como image01-thumbnail.png, image02-thumbnail.png, image03-thumbnail.png, etc. Cada imagen de tamaño completo usa el mismo nombre que su miniatura pero sin "-thumbnail", como en image01.png, image02.png, image03.png, etc. Todos los archivos de imagen se almacenan en el subdirectorio "images".
```

El lector perspicaz habrá notado la instrucción de proporcionar “código JavaScript” en este mensaje. ¿De qué se trata? La siguiente sección resuelve el misterio.

## 10.4 La lightbox: Desarrollado con JavaScript

Hasta este punto del libro, has visto que puedes llegar bastante lejos con solo HTML y CSS. Se trata de tecnologías potentes que, cuando se generan correctamente mediante ChatGPT con indicaciones detalladas, pueden producir páginas web atractivas y útiles.

Sin embargo, hay muchas cosas que HTML y CSS, por muy potentes que sean, no pueden hacer. Un lightbox es un buen ejemplo. Sí, puedes usar HTML y CSS para crear y darle estilo al lightbox, pero una vez que haces clic en una miniatura, HTML y CSS dejan de funcionar:

* No pueden crear nuevos elementos.

* No pueden cargar la versión de tamaño completo de la miniatura en la que se hizo clic en el elemento `img` lightbox.

* No pueden mostrar la lightbox oculta.

* No pueden eliminar el lightbox cuando el usuario hace clic en él.

Afortunadamente, existe una tercera tecnología importante para páginas web que puede manejar este tipo de tareas y muchas más: JavaScript. Se trata de un lenguaje de programación integrado en el navegador web y diseñado para añadir interactividad y dinamismo a elementos de páginas web que de otro modo serían inertes. En este proyecto, JavaScript hace básicamente dos cosas:

* Agrega un controlador de evento de “clic” a cada imagen. Un controlador de evento es un código JavaScript que se ejecuta automáticamente cuando ocurre un evento específico. En este caso, el evento es el clic del usuario en una imagen de la galería de fotos.

* En el controlador de eventos, JavaScript crea y luego muestra el lightbox.

Afortunadamente para ti, eso es todo lo que necesitas saber. ChatGPT se encargará del resto.

## 10.5 Diseño de la galería con Flexbox

Cuando se añaden elementos a una página web, el comportamiento de diseño predeterminado para la mayoría de los elementos es que fluyan verticalmente hacia abajo en la página, un elemento tras otro. Esto ha funcionado bien para los proyectos que has visto hasta ahora en este libro, pero no funcionará para la galería de fotos. ¿Por qué no? Porque con las imágenes renderizadas como figuras, también fluirán verticalmente hacia abajo en la página, una tras otra.

No es el fin del mundo, sin duda, pero no es un buen aspecto y no resulta cómodo para quienes visitan tu página. La figura 10.9 muestra una versión de la galería de fotos en la que las fotos se muestran de esta manera.

Puede evitar este comportamiento predeterminado si le pide a ChatGPT que diseñe la galería de fotos utilizando una técnica de página web llamada *Flexbox*. Se trata de una tecnología compleja, pero todo lo que necesita saber por ahora es que cuando convierte un elemento de página web en un contenedor Flexbox, los elementos pierden su comportamiento de diseño predeterminado rígido y se adaptan a las dimensiones actuales del navegador. Para este proyecto, puede solicitarle a ChatGPT que use Flexbox con una instrucción simple:

```text
Make the gallery a Flexbox container. Center the content and enable it to wrap.
```

```text
Convierte la galería en un contenedor Flexbox. Centra el contenido y permite que se ajuste.
```

Para ver el resultado de esta instrucción, consulte el diseño final de la galería de fotos, que aparece más adelante, en la figura 10.10.

En este punto, ya sabes todo lo que se necesita para que ChatGPT cree una galería de fotos. La siguiente sección te guiará a través del proceso.

![image](https://github.com/user-attachments/assets/12a675b0-f4f9-4557-9883-5136a98072bf)

**Figura 10.9 De forma predeterminada, las figuras de sus fotografías se colocarán verticalmente en la página, una tras otra.**

## 10.6 Elaboración del prompt para la galería de fotos

El proyecto de este capítulo es una página de galería de fotos que muestra nueve miniaturas de fotos, cada una de las cuales, al hacer clic en ella, muestra una versión de tamaño grande de la foto. Supongo que ya tienes un logotipo y un título para el sitio, sabes qué fuentes quieres usar para los encabezados y el texto de la página y tienes un esquema de colores listo para aplicar. Vuelve al capítulo 3 para aprender cómo solicitarle a ChatGPT sugerencias de título, tipografía y color.

Para iniciar su prompt, dígale a ChatGPT que desea construir una página web y que desea que genere el código por usted:

```text
I want to build a web page for a photo gallery. I don't know how to code, so I need you to provide the code for me.
  
First, write the HTML code for a web page that includes the following:
```

```text
Quiero crear una página web para una galería de fotos. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
```

Ahora, esboce el contenido de la página, elemento por elemento, incluyendo lo siguiente (consulte la figura 10.10):

* Un header que incluya su logotipo y el título del sitio.

* Un elemento main que comienza con el título de la página y va seguido de algunas instrucciones.

* La galería de miniaturas de fotografías

* Un footer que incluye un aviso de derechos de autor

![image](https://github.com/user-attachments/assets/e88077c5-64dd-41b5-a76e-43055f9c1011)

**Figura 10.10 Los elementos de la página de la galería de fotos**

A continuación, solicite a ChatGPT que genere el CSS:

```text
Second, in a separate file please write the CSS code for the following:
```

```text
En segundo lugar, en un archivo separado, escriba el código CSS para lo siguiente:
```

A continuación, especifique el formato de la página, incluido lo siguiente:

* El color de fondo de la página y el color del texto.

* Los tamaños de fuente que desea utilizar para los encabezados y el texto de la página.

* Las fuentes que se deben utilizar para los encabezados y el texto normal de la página.

* ¿Qué elementos deben ser contenedores Flexbox (en este proyecto, estos serán el encabezado, la galería y la superposición de lightbox)?

Por último, le indica a ChatGPT que proporcione el código HTML, CSS y JavaScript para una superposición estilo lightbox para mostrar las fotos de gran tamaño.

A continuación se muestra un ejemplo de prompt para mi propia galería de fotos:

```text
I want to build a web page for a photo gallery. I don't know how to code, so I need you to provide the code for me.
  
First, write the HTML code for a web page that includes the following:
 * A header element that includes an image named logo.png, which is stored in the "images" subdirectory, and the title "Ampersand Photography".
 * A main section with the heading "Photo Gallery".
 * A paragraph with the text "Click each thumbnail to see the full version of the image. To return to the gallery, click anywhere on the page."
 * A gallery element that contains the following images, each of which is stored in the "images" subdirectory, and with each image rendered as a figure with the specified alt text and caption:
  * An image named "image01-thumbnail.jpg" with the alt text "Macro photograph of a cactus" and the caption "Cactus close-up".
  * An image named "image02-thumbnail.jpg" with the alt text "A blurry reflection of a passing streetcar and a person walking" and the caption "Street(car) scene".
  * An image named "image03-thumbnail.jpg" with the alt text "A photo with a very old road marker in the foreground that reads 'Appleby 12 Miles'" and the caption "An old road marker".
  * An image named "image04-thumbnail.jpg" with the alt text "A photo taken from the top of a Lake District fell looking down on a town and a lake" and the caption "Lake District scene".
  * An image named "image05-thumbnail.jpg" with the alt text "A Montreal tower shot from below through a hole" and the caption "Montreal architecture".
  * An image named "image06-thumbnail.jpg" with the alt text "The ornate ceiling of a church in Florence, Italy" and the caption "Church ceiling in Florence".
  * An image named "image07-thumbnail.jpg" with the alt text "A cheerful, bright, sky-blue umbrella sitting improbably on a dingy, dirty balcony." and the caption "A dash of color".
  * An image named "image08-thumbnail.jpg" with the alt text "A large, ornate, Zeus-like head over the words 'Brazen Head'" and the caption "Coffee shop sign".
  * An image named "image09-thumbnail.jpg" with the alt text "A metal bird sculpture with its head peeking out of a snow bank" and the caption "Peek-a-boo bird".
 * A footer element that includes the Copyright symbol, followed by "Ampersand Photography".
 * In the page head section, include the tag <meta charset="utf-8">.
 * In the page head section, include the tag <meta name="viewport" content="width=device-width, initial-scale=1">.
  
Second, in a separate file write the CSS code for the following:
 * The page has background color black and no margin.
 * The page text uses font size 20px, the color gold, and the Libre Baskerville font from Google Fonts.
 * The header has background color maroon and 24px padding.
 * Make the header a Flexbox container with centered content.
 * The title is 64px, centered, uses the generic "cursive" font, and has 16px padding on the left.
 * The main section has centered text and a 24px margin.
 * The main section heading has font size 30px and uses the Montserrat font from Google Fonts.
 * Make the gallery a Flexbox container. Center the content and enable it to wrap.
 * The footer has background color maroon, 24px padding, and centered text.
  
Third, provide the HTML, CSS, and JavaScript code to implement a lightbox-style overlay for the images in the gallery. Each full-size image uses the same name as its thumbnail, but without "-thumbnail". For example, for the image01-thumbnail.jpg thumbnail file, the full-size image filename is image01.jpg.
```

```text
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
```
  
En tercer lugar, proporcione el código HTML, CSS y JavaScript para implementar una superposición de estilo lightbox para las imágenes de la galería. Cada imagen de tamaño completo utiliza el mismo nombre que su miniatura, pero sin "-thumbnail". Por ejemplo, para el archivo de miniatura `image01-thumbnail.jpg`, el nombre del archivo de imagen de tamaño completo es `image01.jpg`.

En cada una de mis pruebas con este mensaje, ChatGPT generó este código en cuatro etapas:

1. ChatGPT generó una parte del código HTML (pero no todo, lo más importante). Cuando llegó el momento de generar los elementos `figure`, ChatGPT generó el código solo para la primera figura, seguido de un comentario similar a este:

   ```html
   <!-- repeat for each image -->
   ```

   ¡No lo creo! Más tarde, utilicé el siguiente mensaje para pedirle a ChatGPT que me proporcionara el código HTML completo:

   ```text
   Please provide the complete HTML code, including all the images specified in the original prompt.
   ```

   ```text
   Proporcione el código HTML completo, incluidas todas las imágenes especificadas en la solicitud original.
   ```

   Una vez hecho esto, guardé el código HTML completo como `index.html`. En ese archivo, deberías ver dos referencias a archivos externos:

   1. La primera referencia está en la sección `head` y es para el archivo CSS; la referencia es una etiqueta `<link>` que debería verse así:

   ```html
   <link rel="stylesheet" type="text/css" href="styles.css">
   ```

   2. La segunda referencia está cerca de la parte inferior del código HTML y es para el archivo JavaScript; la referencia es una etiqueta `<script>` que debería verse así:

   ```html
   <script src="script.js"></script>
   ```

2. ChatGPT generó el código para el CSS, que debes guardar con el mismo nombre de archivo que aparece en la etiqueta `<link>` (generalmente `styles.css`).

3. ChatGPT generó el código para JavaScript, que debes guardar con el mismo nombre de archivo que aparece en la etiqueta `<script>` (normalmente `script.js`)

4. ChatGPT generó más código CSS para la lightbox overlay. Debes copiar ese código y pegarlo en la parte inferior de tu archivo CSS.

Utilicé la aplicación ChatGPT de OpenAI para enviar mi mensaje a GPT-4. El código generado generó la página que se muestra en la figura 10.11. Al hacer clic en una miniatura, se genera una versión más grande de la imagen, como se muestra en la figura 10.12.

![image](https://github.com/user-attachments/assets/bb3aa8cf-086a-403c-8249-0f13609a4b04)

**Figura 10.11 Mi galería de fotos**

![image](https://github.com/user-attachments/assets/416ae5af-5f1c-4157-9d94-50268fcf9a40)

**Figura 10.12 Al hacer clic en una miniatura(thumbnail) se muestra una versión de mayor tamaño de la foto.**

Si está satisfecho con su página, puede omitir el resto de este capítulo e implementar el código en la web (consulte el apéndice B para saber cómo implementar su página). Sin embargo, si desea comprender el código de la página web generada, siga leyendo para obtener más información.

## 10.7 Examinar el código de la galería de fotos

Si desea tener al menos alguna idea de lo que ChatGPT generó en su nombre, las siguientes tres secciones le brindan una breve mirada al código HTML y CSS que sustenta la página de la galería de fotos mostrada anteriormente en la figura 10.11, así como el código JavaScript que habilita la superposición de caja de luz que se muestra en la figura 10.12.

**NOTA**: El código HTML y CSS generado para mi galería de fotos está disponible en el sitio web de este libro ( www.manning.com/books/build-a-website-with-chatgpt ) y en el repositorio de GitHub del libro: https://github.com/paulmcfe/websites-with-chatgpt .

Las anotaciones de código que siguen deberían ayudarle a comprender cómo funciona la galería de fotos y pueden facilitar la modificación o personalización de su propio código.

### 10.7.1 Examinar el HTML

Aquí hay una versión anotada del código HTML que ChatGPT produjo para mi galería de fotos:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <meta name="viewport" 
        content="width=device-width, initial-scale=1">                     ①
    <link href="https://fonts.googleapis.com/css?                          ②
        family=Montserrat|                                                 ②
        Libre+Baskerville&display=swap"                                    ②
        rel="stylesheet">                                                  ②
    <link rel="stylesheet" href="styles.css">                              ③
    <title>Ampersand Photography</title>
</head>
<body>
    <header>                                                               ⑥
        <img src="images/logo.png"                                         ⑥
             alt="Ampersand Photography Logo">                             ④⑥
        <h1>Ampersand Photography</h1>                                     ⑤⑥
    </header>                                                              ⑥
    <main>
        <h2>Photo Gallery</h2>                                             ⑦
        <p>                                                                ⑧
            Click each thumbnail to see the full version of the image.     ⑧
            To return to the gallery, click anywhere on the page.          ⑧
        </p>                                                               ⑧
        <div class="gallery">                                              ⑫
            <figure>                                                       ⑪⑫
                <img src="images/image01-thumbnail.jpg"                    ⑨⑪⑫
                     alt="Macro photograph of a cactus"                    ⑨⑪⑫
                     class="thumbnail">                                    ⑨⑪⑫
                <figcaption>Cactus close-up</figcaption>                   ⑩⑪⑫
            </figure>                                                      ⑪⑫
            <figure>                                                       ⑫
                <img src="images/image02-thumbnail.jpg"                    ⑫
                     alt="A blurry reflection of a passing streetcar       ⑫
                         and a person walking"                             ⑫
                     class="thumbnail">                                    ⑫
                <figcaption>Street(car) scene</figcaption>                 ⑫
            </figure>                                                      ⑫
            <figure>                                                       ⑫
                <img src="images/image03-thumbnail.jpg"                    ⑫
                     alt="A photo with a very old road marker in the       ⑫
                         foreground that reads 'Appleby 12 Miles'"         ⑫
                     class="thumbnail">                                    ⑫
                <figcaption>An old road marker</figcaption>                ⑫
            </figure>                                                      ⑫
            <figure>                                                       ⑫
                <img src="images/image04-thumbnail.jpg"                    ⑫
                     alt="A photo taken from the top of a Lake District    ⑫
                         fell looking down on a town and a lake"           ⑫
                     class="thumbnail">                                    ⑫
                <figcaption>Lake District scene</figcaption>               ⑫
            </figure>                                                      ⑫
            <figure>                                                       ⑫
                <img src="images/image05-thumbnail.jpg"                    ⑫
                     alt="A Montreal tower shot from below through a hole" ⑫
                     class="thumbnail">                                    ⑫
                <figcaption>Montreal architecture</figcaption>             ⑫
            </figure>                                                      ⑫
            <figure>                                                       ⑫
                <img src="images/image06-thumbnail.jpg"                    ⑫
                     alt="The ornate ceiling of a church in Florence,      ⑫
                         Italy"                                            ⑫
                     class="thumbnail">                                    ⑫
                <figcaption>Church ceiling in Florence</figcaption>        ⑫
            </figure>                                                      ⑫
            <figure>                                                       ⑫
                <img src="images/image07-thumbnail.jpg"                    ⑫
                     alt="A cheerful, bright, sky-blue umbrella sitting    ⑫
                         improbably on a dingy, dirty balcony."            ⑫
                     class="thumbnail">                                    ⑫
                <figcaption>A dash of color</figcaption>                   ⑫
            </figure>                                                      ⑫
            <figure>                                                       ⑫
                <img src="images/image08-thumbnail.jpg"                    ⑫
                     alt="A large, ornate, Zeus-like head over the words   ⑫
                         'Brazen Head'"                                    ⑫
                     class="thumbnail">                                    ⑫
                <figcaption>Coffee shop sign</figcaption>                  ⑫
            </figure>                                                      ⑫
            <figure>                                                       ⑫
                <img src="images/image09-thumbnail.jpg"                    ⑫
                     alt="A metal bird sculpture with its head peeking     ⑫
                         out of a snow bank"                               ⑫
                     class="thumbnail">                                    ⑫
                <figcaption>Peek-a-boo bird</figcaption>                   ⑫
            </figure>                                                      ⑫
        </div>                                                             ⑫
    </main>
    <footer>                                                               ⑬
        &copy; Ampersand Photography                                       ⑬
    </footer>                                                              ⑬
  
    <script src="script.js"></script>                                      ⑭
</body>
</html>
```

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

```html
<link rel="stylesheet" href="styles.css">
```

Esta etiqueta le dice al navegador web dónde encontrar el código CSS, que describo en la siguiente sección.

### 10.7.2 Examinar el CSS

Aquí hay una versión anotada del código CSS que ChatGPT produjo para mi galería de fotos:

```css
body {                                        ①
    background-color: black;                  ①
    margin: 0;                                ①
    font-size: 20px;                          ①
    color: gold;                              ①
    font-family: 'Libre Baskerville', serif;  ①
}                                             ①
  
header {
    background-color: maroon;                 ②
    padding: 24px;                            ②
    display: flex;                            ③
    justify-content: center;                  ③
    align-items: center;                      ③
}
  
h1 {
    font-size: 64px;                          ④
    font-family: cursive;                     ④
    padding-left: 16px;                       ④
}
 
h2 {
    font-size: 30px;                          ⑤
    font-family: 'Montserrat', sans-serif;    ⑤
}
  
main {
    margin: 24px;                             ⑥
    text-align: center;                       ⑥
}
  
.gallery {
    display: flex;                            ⑦
    flex-wrap: wrap;                          ⑦
    justify-content: center;                  ⑦
    align-items: center;                      ⑦
}
  
footer {
    background-color: maroon;                 ⑧
    padding: 24px;                            ⑧
    text-align: center;                       ⑧
}
.overlay {                                    ⑬
    position: fixed;                          ⑨⑬
    top: 0;                                   ⑨⑬
    left: 0;                                  ⑨⑬
    width: 100%;                              ⑩⑬
    height: 100%;                             ⑩⑬
    background-color: rgba(0, 0, 0, 0.8);     ⑪⑬
    display: flex;                            ⑫⑬
    justify-content: center;                  ⑫⑬
    align-items: center;                      ⑫⑬
}                                             ⑬
  
.overlay img {
    max-width: 90%;                           ⑭
    max-height: 90%;                          ⑭
}
```

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

```html
<script src="script.js"></script>
```

Esta etiqueta le dice al navegador web dónde encontrar el código JavaScript, que anoto en la siguiente sección.

### 10.7.3 Examinando el JavaScript

Si tienes cuidado, está bien hacer pequeños ajustes al código HTML y CSS. Sin embargo, te recomiendo encarecidamente que no toques el código JavaScript de ChatGPT. El código es complejo y una edición imprudente podría hacer que el lightbox quede inutilizable.

Sin embargo, si conoces un poco de JavaScript, quizás te interese saber cómo ChatGPT resolvió el problema del lightbox. Aquí tienes una versión comentada del código JavaScript que ChatGPT generó para mi galería de fotos:

```js
document.addEventListener('DOMContentLoaded', 
    function () {                                              ①
  
    const thumbnails = document.querySelectorAll(
        '.thumbnail');                                         ②
  
    thumbnails.forEach((thumbnail) => {                        ③
  
        thumbnail.addEventListener('click', 
            function (e) {                                     ④
  
            const imageName = e.target.src.split('/')
                .pop().replace('-thumbnail', '');              ⑤
  
            const overlay = document.createElement('div');     ⑥
  
            overlay.classList.add('overlay');                  ⑦
  
            const img = document.createElement('img');         ⑧
  
            img.src = `images/${imageName}`;                   ⑨
  
            overlay.appendChild(img);                          ⑩
  
            document.body.appendChild(overlay);                ⑪
  
            overlay.addEventListener('click', function () {    ⑫
                document.body.removeChild(overlay);            ⑫
            });                                                ⑫
        });
    });
});
```

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

## 10.8 Personalización de la galería de fotos

Utilizando las anotaciones de las secciones anteriores como guía, te mostraré algunas personalizaciones de código relativamente simples que puedes hacer abriendo los archivos HTML y CSS en tu editor de texto. Sin embargo, si tu página no se parece en nada a lo que quieres, es mejor que reescribas el mensaje y lo envíes a ChatGPT en una nueva sesión.

Para el código HTML, aquí hay algunas personalizaciones sugeridas:

* Puedes editar el poco texto que hay en la página, incluido el título, el encabezado y el texto de instrucciones. Solo asegúrate de editar solo el texto y no las etiquetas HTML que lo rodean (como las etiquetas `<figcaption>` y `</figcaption>` alrededor de cada título de figura).

* No dudes en cambiar el texto alternativo de cualquier imagen editando el valor del atributo `img` de esa etiqueta `alt`. Asegúrate de no eliminar por accidente las comillas dobles que rodean el valor `alt`.

* Si desea incluir un segundo párrafo introductorio, coloque el cursor de edición después de la etiqueta `</p>` que finaliza el párrafo introductorio existente. Presione Enter o Return para comenzar una nueva línea, escriba una etiqueta `<p>`, escriba el texto del párrafo y finalice con una etiqueta `</p>`.

* Es posible que desees desarrollar tu sitio creando varias galerías de fotos (o lo que sea), con cada página dedicada a un tema o categoría en particular. Pídele a ChatGPT que cree una página a la vez, modificando el mensaje según sea necesario. Si eliges esta opción, necesitarás un elemento de navegación que permita a los usuarios visitar cada página. Consulta el capítulo 6 para aprender a solicitarle a ChatGPT enlaces y una barra de navegación.

* En la sección de footer del código HTML, puedes agregar enlaces a tus cuentas de redes sociales, como describo en el capítulo 4.

A continuación se muestran algunas ideas de personalización para el código CSS:

* Para utilizar otro color de fondo de página, especifique una palabra clave de color diferente para la propiedad `background-color` del elemento `body`.

* Para utilizar otro color de fondo para el encabezado y el pie de página, especifique una nueva palabra clave de color para la propiedad `background-color` de los elementos `header` y `footer`.
  
* Para utilizar un color diferente para el texto de la página, especifique una palabra clave de color diferente para la propiedad `color` del elemento `body`.

* Para ajustar la transparencia de la lightbox overlay, edite la propiedad `background-color` de la clase `.overlay`. En concreto, modifique el valor final en la función `rgba()`, donde `1.0` es completamente opaco y `0.0` es completamente transparente.

* Para cualquier valor de tamaño de fuente, puede cambiar el número para aumentar o disminuir el tamaño de la fuente. Solo asegúrese de dejar la unidad `px` en su lugar.

* Para cualquier valor de margen o padding, puede cambiar el número para aumentar o disminuir el padding o los márgenes. En cada caso, asegúrese de dejar la unidad `px` en su lugar.

Para que el código de tu página sea más accesible, considera convertir todas las medidas en px a medidas en rem. 1 rem equivale de manera predeterminada a 16 px, por lo que 20 px son 1,25 rem, 24 px son 1,5 rem, 32 px son 2 rem, 48 px son 3 rem, y así sucesivamente. La unidad rem es más accesible porque mide los tamaños de fuente en relación con el tamaño de fuente predeterminado que el usuario del navegador ha definido en la configuración de su navegador.

## Resumen

* En HTML, se utiliza el elemento `img` para indicarle al navegador web que inserte un archivo de imagen externo en la página.

* En la etiqueta `<img>`, use el atributo `src` para indicarle al navegador dónde encontrar el archivo de imagen; use el atributo `alt` para agregar una frase corta que describa la imagen, particularmente para personas que usan lectores de pantalla y aplicaciones Braille.

* Al trabajar con miniaturas de imágenes, es mejor crear un archivo de miniatura separado que tenga las dimensiones más pequeñas que desea utilizar.

* Para incluir un título, rodee el elemento `img` con un elemento `figure` y agregue el título al elemento `figcaption`.

* Una lightbox overlay es un elemento de página web creado sobre la marcha para mostrar una versión de gran tamaño de una miniatura en la que se hizo clic.

* Cuando no desea que los elementos de la página estén dispuestos verticalmente en la página, convierta el elemento en un contenedor Flexbox.

* Para obtener mejores resultados, el mensaje de su página debe ser lo más específico posible, incluidos colores, tamaños de fuente y niveles de encabezado.

* Guarde el HTML generado en el archivo `index.html` y el CSS generado en el nombre de archivo sugerido por ChatGPT en el código HTML, generalmente `styles.css`.
