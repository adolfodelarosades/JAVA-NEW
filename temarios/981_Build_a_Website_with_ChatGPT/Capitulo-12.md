# 12 Creación de una página de artículo
Este capítulo cubre

La estructura de una página de artículo
Diseño de la página usando CSS Grid
Cómo hacer que el artículo se vea bien en las pantallas de los teléfonos inteligentes
Elaboración de un mensaje de ChatGPT para crear una página de artículo
Examinar y personalizar el código generado por ChatGPT
Hay tantas razones para crear una página web como personas que desean establecer algún tipo de presencia en la red. Sin embargo, la mayoría de estas razones se pueden agrupar bajo dos grandes paraguas: la autoexpresión y el intercambio de información. Hasta ahora en este libro, has trabajado en varios proyectos relacionados con la autoexpresión: la página de inicio personal (capítulo 3), el diario en línea (capítulo 5), la galería de fotos (capítulo 10) y la página de portafolios (capítulo 11). También has trabajado en proyectos relacionados con el intercambio de información: la página del club de lectura (capítulo 4), el sitio web de información (capítulo 6), el sitio web de intereses o pasatiempos (capítulo 7), la página de inscripción a eventos (capítulo 8) y la página de recetas (capítulo 9).

Este capítulo le presenta otra estructura de página para compartir información: la página del artículo. Esta página utiliza estructuras HTML comunes, como un encabezado, una barra de navegación, una barra lateral y un pie de página, todas organizadas alrededor de la estrella de la página: un artículo largo que contiene varias secciones. Este capítulo será un poco más "práctico" que los proyectos anteriores porque es más fácil agregar secciones, encabezados y párrafos y marcar ese texto (es decir, agregar las etiquetas HTML adecuadas) para el lector a mano que confiar en ChatGPT para hacer todo. Sin embargo, no se preocupe: seguirá aprovechando los conocimientos de codificación de ChatGPT para crear la estructura básica de su página de artículo y agregar algunos detalles adicionales que harán que su artículo se destaque entre la multitud.

12.1 Conociendo el proyecto de este capítulo
El proyecto de este capítulo es una página de artículo. La página final incluirá los siguientes componentes:

Un elemento de encabezado que incluye un logotipo, un título y un eslogan.

Una barra de navegación con enlaces a otras secciones del sitio.

Un elemento principal que contiene un elemento de artículo con un título

Múltiples elementos de sección dentro del artículo, cada uno con su propio encabezado y párrafos.

Un elemento de barra lateral con información relacionada

Un elemento de pie de página que incluye un aviso de derechos de autor

La Figura 12.1 muestra una página de artículo de ejemplo (parcial) creada con código y texto proporcionados por ChatGPT.



Figura 12.1 Una página de artículo generada por ChatGPT

La página de ejemplo es un artículo de viajes ficticio sobre un lugar imaginario de una obra literaria (Narnia, el escenario principal de la serie de fantasía Las crónicas de Narnia de CS Lewis ), pero puedes usar el diseño del artículo para muchos otros tipos de contenido: noticias, ensayos, publicaciones de blogs, reseñas, biografías, relatos históricos, etc. En la siguiente sección, aprenderás a diseñar el diseño del artículo.

12.2 Creación de la página del artículo
¿Cómo saber si un artículo tiene el diseño de página que necesitas? Examina el contenido principal que quieres mostrar en la página y hazte las siguientes preguntas:

¿El escrito se centra en un único tema?

¿El escrito está dividido en múltiples subtemas?

Si la respuesta es “Sí” a ambas preguntas, el diseño del artículo que aprenderá en este capítulo será un excelente escaparate para su escritura.

Antes de aprender a diseñar una página como artículo, debería dar un paso atrás y revisar los elementos de diseño de páginas HTML que ha visto en los capítulos anteriores de este libro. Esto le ayudará a comprender el diseño general de la página del artículo.

12.2.1 Revisión de los elementos de diseño de la página HTML
En la mayoría de los proyectos de este libro, el HTML que ChatGPT ha generado ha diseñado la página utilizando algunos o todos los siguientes elementos:

header—Define un área de la página que contiene contenido introductorio. Este contenido suele ser el título del sitio (que debe estar marcado con un elemento de encabezado, como h1), pero también puede incluir elementos como el logotipo del sitio y un eslogan. A continuación, se incluye un ejemplo (del capítulo 9):

<encabezado>
    <img src="super-baker.png" alt="El logotipo de Super Baker">
    <h1>El Súper Panadero</h1>
    <p>La guía definitiva para hornear con superpoderes. Aprenda a
        Prepara deliciosas delicias que aumentarán tu energía,
        fuerza y ​​velocidad.</p>
</encabezado>
nav—Define un área de la página que contiene contenido de navegación, como enlaces a otras secciones del sitio. Este elemento puede estar en cualquier parte de la página, pero normalmente aparece justo después del headerelemento de la página. A continuación, se incluye un ejemplo (del capítulo 6):

<navegación>
    <a href="index.html">Inicio</a>
    <a href="blog.html">Blog</a>
    <a href="faq.html">Preguntas frecuentes</a>
    <a href="about.html">Acerca de</a>
    <a href="contacto.html">Contacto</a>
</nav>
main—Crea un contenedor para el contenido exclusivo de la página actual. Mientras que los headerelementos nav, y footersuelen ser comunes a todas o la mayoría de las páginas del sitio, el mainelemento está pensado para marcar el contenido exclusivo. Solo puede haber un mainelemento por página. Normalmente aparece después de los elementos headery nav, como se muestra aquí (del capítulo 6):

<encabezado>
    <h1>Sociedad para la preservación de la palabra antediluviana</h1>
    <p>Preservando palabras del pasado para el futuro</p>
</encabezado>
<navegación>
    <a href="index.html">Inicio</a>
    <a href="blog.html">Blog</a>
    <a href="faq.html">Preguntas frecuentes</a>
    <a href="about.html">Acerca de</a>
    <a href="contacto.html">Contacto</a>
</nav>
<principal>
    El contenido exclusivo de la página va aquí 
</main>
section—Contiene cualquier parte de una página que desee ver en un esquema de la página. Es decir, si parte de la página consta de un elemento de encabezado (como h2o h3) seguido de algún texto, rodeará el encabezado y su texto con las etiquetas <section>y </section>, de la siguiente manera (del capítulo 6):

    <sección>
      El desafío de esta semana
      <p>
          Tu desafío esta semana es usar la palabra tontería.
          — comportamiento tonto o tonto — al menos una vez en cada
          de los siguientes: en una conversación, en un mensaje de correo electrónico,
          en un mensaje de texto y en una reunión de negocios (virtual o
          mundo real) ¡Buena suerte y cuéntanos cómo te va!
      </p>
    </sección>
p—Marca un fragmento de texto como un párrafo. Un sectionelemento normalmente consta de uno o más párrafos, aunque también puedes agregar párrafos a cualquier otro elemento, en particular a los elementos header, mainy footer.

footer—Define un área de página que contiene contenido de cierre, como un aviso de derechos de autor, una dirección y la información de contacto. A continuación, se incluye un ejemplo (del capítulo 4):

<pie de página>
    <p>Copyright 2023 Código y prosa</p>
    <p>
        <a href="https://www.facebook.com/CodeAndProse">
        <i class="fab fa-facebook-square"></i></a>
        <a href="https://www.instagram.com/codeandprose">
        <i class="fab fa-instagram"></i></a>
        <a href="https://twitter.com/codenprose">
        <i class="fab fa-twitter-square"></i></a>
    </p>
</pie de página>
La figura 12.2 muestra un diseño de página abstracto que demuestra cómo aparecen estos elementos en una página. Observe que incluye dos elementos de diseño de página HTML que no cubrí en esta sección: articley aside. No es de sorprender que el articleelemento desempeñe un papel vital en el diseño de la página del artículo de este capítulo, por lo que lo cubriré en detalle a continuación.



Figura 12.2 Un diseño conceptual que incluye los elementos básicos del diseño HTML

12.2.2 Trabajar con el elemento de artículo
El elemento se utiliza articlepara marcar una composición completa e independiente. El modelo aquí es un artículo de periódico o revista, pero este elemento también se puede aplicar a una reseña, una entrada de blog, una publicación en un foro o un ensayo. La mayoría de las páginas tienen un solo articleelemento anidado dentro del mainelemento. Ese articleelemento generalmente contiene lo siguiente:

Un título, generalmente marcado como un encabezado de segundo nivel (es decir, un h2elemento)

Uno o más elementos introductorios p(párrafos)

Uno o más sectionelementos

Dentro de cada uno de esos sectionelementos, un encabezado de tercer nivel (es decir, un h3elemento) seguido de uno o más pelementos

Nada de esto está escrito en piedra. Por ejemplo, está perfectamente bien que un articleelemento contenga solo un título y uno o más párrafos. Sin embargo, para los fines de este capítulo, el diseño de la página del artículo utiliza estos elementos. Esta es la estructura genérica que utilizará:

<principal>
    <artículo>
        <h2>Título del artículo</h2>
        <p>Párrafo introductorio</p>
        <sección>
            <h3>Título de la sección 1</h3>
            <p>
                Artículo 1 párrafo 1
            </p>
            <p>
                Artículo 1 párrafo 2
            </p>
            <p>
                etc.
            </p>
        </sección>
        <sección>
            <h3>Título de la sección 2</h3>
            <p>
                Artículo 2 párrafo 1
            </p>
            <p>
                Artículo 2 párrafo 2
            </p>
            <p>
                etc.
            </p>
        </sección>
        <sección>
            <h3>Título de la sección 3</h3>
            <p>
                Artículo 3 párrafo 1
            </p>
            <p>
                Artículo 3 párrafo 2
            </p>
            <p>
                etc.
            </p>
        </sección>
    </artículo>
</principal>
En general, puedes lograr que ChatGPT genere el código para un articleelemento incluyendo una instrucción similar a la siguiente en tu mensaje:

En la sección principal, agregue un elemento de artículo donde el título del artículo sea "[ título ]" como encabezado de segundo nivel.
El segundo elemento nuevo de diseño de página HTML que se muestra anteriormente en la figura 12.2 es aside, sobre el que aprenderá a continuación.

12.2.3 Incluir una barra lateral en su página
Utilice el asideelemento para marcar un área de la barra lateral de una página que contenga contenido indirectamente relacionado con el contenido exclusivo de la página (en el diseño de este capítulo, ese contenido exclusivo se refiere a lo que aparece en el articleelemento). A continuación, se muestran algunos casos de uso para una barra lateral de este tipo:

Una lista de enlaces a páginas del sitio relacionadas con el contenido principal de la página.

Las últimas noticias del sitio

Un canal de redes sociales

Uno o más anuncios

Un asideelemento puede aparecer en cualquier parte dentro del mainelemento (y puede aparecer varias veces en la página). En el diseño de la página del artículo de este capítulo, el asideelemento aparece justo después del articleelemento de la página, como se muestra en el siguiente ejemplo:

<principal>
    <artículo>
        <h2>Título del artículo</h2>
        <p>Párrafo introductorio</p>
        <sección>
            <h3>Título de la sección 1</h3>
            <p>
                Artículo 1 párrafo 1
            </p>
            <p>
                Artículo 1 párrafo 2
            </p>
            <p>
                etc.
            </p>
        </sección>
        <sección>
            <h3>Título de la sección 2</h3>
            <p>
                Artículo 2 párrafo 1
            </p>
            <p>
                Artículo 2 párrafo 2
            </p>
            <p>
                etc.
            </p>
        </sección>
        <sección>
            <h3>Título de la sección 3</h3>
            <p>
                Artículo 3 párrafo 1
            </p>
            <p>
                Artículo 3 párrafo 2
            </p>
            <p>
                etc.
            </p>
        </sección>
    </artículo>
    <aparte>
        <h3>Título aparte</h3>
        <p>
            Apartado párrafo 1
        </p>
        <p>
            Párrafo aparte 2
        </p>
        <p>
            etc.
        </p>
    </aparte>
</principal>
En general, para que ChatGPT genere el código de un asideelemento, incluya una instrucción similar a la siguiente en su solicitud:

En la parte inferior de la sección principal, agregue un elemento aparte donde el título sea "[ título ]" como encabezado de tercer nivel.
Como parte del enfoque más práctico de este capítulo, en las siguientes secciones aprenderá cómo agregar nuevos elementos a su página en lugar de pedirle a ChatGPT que genere esos elementos.

12.2.4 Añadir nuevas secciones al artículo
Los artículos pueden ser breves o extensos. En el caso de un artículo breve, no es un problema incluir el texto y los encabezados en el mensaje de ChatGPT y dejar que el modelo haga el trabajo pesado por usted. Sin embargo, ese enfoque no funciona tan bien en el caso de artículos extensos, ya que los mensajes terminan siendo extremadamente extensos. Esa extensión puede causar dos problemas:

Es posible que exceda el número máximo de caracteres permitidos en un mensaje.

Cuanto más largo sea el mensaje, más probable será que ChatGPT pierda el rumbo al generar una respuesta.

Por estos motivos, en el proyecto de este capítulo, solo le pedirás a ChatGPT que cree un esqueleto del diseño de la página. Luego, le darás más cuerpo a ese esqueleto agregando el resto del contenido del artículo a mano.

El código HTML devuelto por ChatGPT se verá, en parte, así:

<principal>
    <artículo>
        <h2>Guía de viaje a Narnia</h2>
        <!-- El contenido del artículo va aquí -->
    </artículo>
</principal>
Estos son los pasos a seguir para agregar un nuevo sectionelemento al artículo:

   1. Abra el archivo HTML en un editor de texto.

   2. Coloque el cursor inmediatamente después del <!-- Article content goes here -->marcador de texto, como se muestra en la figura 12.3.



Figura 12.3 Coloque el cursor como se muestra aquí.

   3. Presione Enter o Retorno para comenzar una nueva línea.

   4. Escriba <section>. Si está utilizando un editor de código, debería agregar automáticamente la </section>etiqueta (aunque es posible que deba presionar la tecla Tab para que esto suceda). De lo contrario, escriba </section>y luego coloque el cursor entre las etiquetas <section>y .</section>

   5. Pulse Enter o Return. Ahora tendrá un nuevo sectionelemento listo para usar, como se muestra en la figura 12.4.



Figura 12.4 El nuevo sectionelemento, listo para ser rellenado

   6. Escribe <h3>. Si estás usando un editor de código, debería agregar la </h3>etiqueta automáticamente (aunque es posible que debas presionar la tecla Tab para que esto suceda). De lo contrario, escribe </h3>y luego coloca el cursor entre las etiquetas <h3>y .</h3>

   7. Escriba el encabezado o título de la sección, como se muestra en la figura 12.5. (Todavía no está agregando los párrafos. Lo abordaré en la siguiente sección).



Figura 12.5 Escriba un título o encabezado para la nueva sección.

   8. Para agregar más secciones, coloque el cursor inmediatamente después de la </section>etiqueta del sectionelemento que acaba de agregar y luego siga los pasos 3 a 7.

Los nuevos sectionelementos tienen encabezados pero no texto. A continuación, solucionará esa situación.

12.2.5 Agregar nuevos párrafos al artículo, sección o aparte
Ya sea que esté trabajando en articleel elemento de su página, en cualquier sectionelemento o en el asideelemento, a menudo necesitará agregar otro párrafo. Estos son los pasos para hacerlo:

   1. Abra el archivo HTML en un editor de texto.

   2. Coloque el cursor inmediatamente después de la etiqueta de cierre del elemento después del cual desea agregar el párrafo. Por ejemplo, si está trabajando en un sectionelemento que actualmente solo tiene un h3encabezado de elemento, colocará el cursor inmediatamente después de la </h3>etiqueta, como se muestra en la figura 12.6.



Figura 12.6 Coloque el cursor después de la etiqueta final del elemento después del cual desea agregar el párrafo.

   3. Presione Enter o Retorno para comenzar una nueva línea.

   4. Escriba <p>. Si está utilizando un editor de código, debería agregar automáticamente la </p>etiqueta (aunque es posible que deba presionar la tecla Tab para que esto suceda). De lo contrario, escriba </p>y luego coloque el cursor entre las etiquetas <p>y .</p>

   5. Pulse Enter o Return. Ahora tendrá un nuevo pelemento listo para texto, como se muestra en la figura 12.7.



Figura 12.7 El nuevo pelemento, listo para el texto

   6. Escriba el texto del párrafo, como se muestra en la figura 12.8.



Figura 12.8 Escriba un título o encabezado para la nueva sección.

   7. Para cada nuevo párrafo que desee agregar, coloque el cursor inmediatamente después de la </p>etiqueta del párrafo actual y luego siga los pasos 3 a 6.

Mientras escribe el texto de un párrafo, puede encontrar palabras o frases especiales que desea que el navegador web muestre en negrita o cursiva. Aprenderá a hacerlo en la siguiente sección.

12.2.6 Marcado de palabras y frases especiales
Algunas palabras o frases de tu texto son “especiales” en el sentido de que se distinguen de alguna manera del resto del texto. Por ejemplo, es posible que quieras enfatizar una palabra en particular, lo que normalmente harías formateándola con letra cursiva. De manera similar, una frase en particular puede ser importante, por lo que para asegurarte de que el lector no la pase por alto, normalmente formatearías la frase con letra negrita.

Si bien es posible indicarle a ChatGPT que agregue cursiva y negrita donde sea necesario, eso puede ser problemático en muchas circunstancias:

Es posible que su texto utilice una palabra o frase varias veces.

Es posible que desees marcar solo la primera instancia de una palabra o frase.

Su texto puede incluir muchas palabras o frases diferentes que desea marcar.

En cada caso, tendrías que encontrar una forma de asegurarte de que ChatGPT marcara lo que querías, una tarea que no es fácil de hacer en la práctica. En realidad, es muy sencillo hacer el marcado tú mismo manualmente a medida que ingresas el texto. Las siguientes secciones brindan los detalles.

Marcar texto importante

En su página web, es posible que desee asegurarse de que el lector vea una palabra, frase u oración en particular porque es importante. Este texto puede ser una instrucción vital, una condición crucial o un pasaje igualmente significativo que debe destacarse del texto normal porque no desea que el lector lo pase por alto. En HTML, se marca el texto como importante mediante el strongelemento:

<strong> El texto importante va aquí </strong>
Todos los navegadores muestran el texto entre las etiquetas <strong>y </strong>en negrita. El siguiente ejemplo muestra el código de una página web con un pasaje importante marcado con el strongelemento y la figura 12.9 muestra el texto que se muestra en negrita en el navegador web:

<p>
    Al entrar en la habitación, observe el gran botón rojo a su derecha.
    <strong>¡Nunca presiones ese botón!</strong>
</p>


Figura 12.9 El texto marcado con el strongelemento aparece en negrita en el navegador.

Un escenario de marcado similar es el de la palabra clave, que se analiza a continuación.

Marcar palabras clave

En algunos casos, desea llamar la atención sobre una palabra o frase no porque sea importante en sí, sino porque el texto en cuestión desempeña un papel que lo hace diferente del texto normal. Ese texto puede ser el nombre de un producto, el nombre de una empresa o un elemento de la interfaz, como el texto asociado con una casilla de verificación o un botón de comando. Nuevamente, el texto con el que está trabajando no es crucial, pero es diferente de alguna manera, por lo que desea que se vea diferente del texto de la página normal.

CONSEJO: Otros candidatos para palabras clave de una página web incluyen el nombre de una persona (como los infames “nombres en negrita” que aparecen en las columnas de chismes de celebridades) y las primeras palabras o la oración inicial de un artículo.

Cada uno de estos elementos indica una palabra clave (o frase clave ) que tiene un significado que va más allá del texto normal de la página. En HTML, este tipo de elemento se marca con el belemento:

<b> palabra clave </b>
Los navegadores web representan el texto entre las etiquetas <b>y </b>en negrita, como se muestra en el siguiente ejemplo y en la figura 12.10:

<p>
    Para guardar su trabajo, despliegue el menú <b>Archivo</b>
    y luego haga clic en <b>Guardar</b>.
</p>


Figura 12.10 Las palabras clave marcadas con el belemento aparecen en negrita en el navegador.

En este punto, imagino que te estarás rascando la cabeza y preguntándote cuál es la diferencia entre el strongelemento y el belemento, porque ambos se representan como texto en negrita. Es un buen punto, y admito que la diferencia es sutil. Debería decir que es semántica porque HTML usa estos dos elementos separados para diferenciar entre texto importante y palabras clave. ¿Por qué molestarse? Porque se espera que en el futuro, los lectores de pantalla y otros dispositivos de asistencia usen esta distinción semántica para ayudar a las personas con discapacidad visual a entender las páginas web.

Marcar texto resaltado

A menudo es importante enfatizar ciertas palabras o frases en una página. Este énfasis le indica al lector que lea o diga el texto con más énfasis. En HTML, se agrega énfasis a una palabra o frase marcándola con el emelemento (for ethics):

<em> texto </em>
Los navegadores web representan el texto entre las etiquetas <em>y </em>en cursiva, como se muestra en el siguiente ejemplo y en la figura 12.11:

<p>
    Al mezclar la masa para tarta, es <em>vital</em> que
    Tu mantequilla está lo más fría posible.
</p>


Figura 12.11 El texto marcado con el emelemento se muestra en cursiva en el navegador.

NOTA ¿Cuál es la diferencia entre el strongelemento y el emelemento? Se utiliza strongcuando el texto en cuestión es inherentemente crucial para el lector; se utiliza emcuando el texto en cuestión requiere un énfasis mayor para transmitir un mensaje.

Marcar texto alternativo

En prosa, es habitual que sea necesario marcar una palabra o frase para indicar que tiene una voz, un estado de ánimo o una función diferente a la del texto normal. Ejemplos habituales de texto alternativo son los títulos de libros y películas. En HTML, este tipo de texto semántico se marca con el ielemento (para cursiva):

<i> texto </i>
NOTA Otros ejemplos de texto alternativo incluyen nombres de publicaciones, términos técnicos, palabras y frases extranjeras y los pensamientos de una persona.

Los navegadores web muestran dicho texto en cursiva, como se muestra en el siguiente ejemplo y en la figura 12.12:

<p>
    Visitemos la tierra de Narnia, que nos fue presentada por primera vez por
    CS Lewis en <i>El león, la bruja y el armario</i> (1950).
</p>


Figura 12.12 El texto alternativo marcado con el ielemento se muestra en cursiva en el navegador.

Puede anidar estos elementos de nivel de texto dentro de otros elementos de nivel de texto para lograr un efecto adicional. Por ejemplo, puede marcar una oración como importante mediante el uso del strongelemento y, dentro de esa oración, puede marcar una palabra con énfasis mediante el uso del emelemento. El navegador mostrará esa palabra en negrita y cursiva.

12.2.7 Comenzar el artículo con letra capital
Puede hacer que sus artículos se destaquen entre la multitud al comenzarlos con una letra capital : la primera letra del primer párrafo, formateada para que parezca mucho más grande que el resto del texto del párrafo y ubicada de manera que se ubique debajo de la línea base del texto y “deje caer” algunas líneas en el párrafo. Para que ChatGPT cree una letra capital, incluya una instrucción similar a la siguiente en su mensaje:

Crea el código HTML y CSS que represente el siguiente texto como un párrafo con una letra capitular de color rojo oscuro: "¡Comenzar un artículo no tiene por qué ser aburrido! Haz que tu texto tenga un buen comienzo haciendo que el párrafo inicial luzca con una letra inicial gigante. Puedes usar una <i>letra capitular</i> (también llamada <i>letra capitular</i> o simplemente una <i>inicial</i>) que se ubique sobre la línea base, o puedes usar una <i>letra capitular</i> que se ubique debajo de la línea base y se integre en el texto".
Aquí está el HTML generado por ChatGPT:

<p>
    <span class="drop-cap">E</span>mpieza un artículo no tiene por qué ser
    ¡Aburrido! Haz que tu texto tenga un buen comienzo con una introducción genial.
    párrafo con una primera letra gigante. En particular, puedes usar una
    <i>letra capital</i> que se ubica debajo de la línea de base y se inserta en el texto.
</p>
Las claves son las <span>etiquetas </span>y que rodean la primera letra del párrafo. El spanelemento utiliza la drop-capclase, que se ve así en el código CSS:

.letra capital {
    flotante: izquierda;                  ① 
    tamaño de fuente: 4em;               ② 
    altura de línea: 0.8em;           ③ 
    relleno: 0.1em 0.1em 0 0;     ④ 
    color: rojo oscuro;               ⑤ 
}
① Saca la letra del flujo de página normal.

② Hace que la letra sea más grande

③ Ajusta la posición de la letra capital

④ Le da un poco de espacio a la letra capital

⑤ Estiliza el color de la letra capital

La figura 12.13 muestra cómo se ve la letra capital en el navegador.



Figura 12.13 Párrafo inicial de un artículo con letra capital

Las letras capitulares son una excelente manera de agregar un toque profesional a sus páginas web. Recuerde que solo debe usarlas para la primera letra del primer párrafo de un artículo.

12.2.8 Diseño del artículo con CSS Grid
Cuando presenté Flexbox en el capítulo 10, mencioné que la forma predeterminada en que el navegador web presenta los elementos HTML a nivel de bloque (incluidos los elementos header, nav, main, section, aside, footery p) es apilándolos uno sobre el otro. El primer bloque está arriba, el segundo debajo, el tercero debajo, y así sucesivamente. ¡No es un diseño muy inspirador!

Flexbox le permite romper con ese diseño predeterminado en una dimensión (horizontal o verticalmente), pero si desea diseñar su página en dos dimensiones (horizontal y verticalmente), debe recurrir a una técnica de diseño diferente llamada CSS Grid.

La buena noticia acerca de CSS Grid es que puedes pedirle a ChatGPT que genere todo el código requerido para ti incluyendo una instrucción simple en la parte CSS de tu mensaje:

El encabezado es un contenedor CSS Grid de dos columnas con el logotipo en la columna izquierda y el título del sitio y el lema en la columna derecha.
¡Eso es todo! Sin embargo, para los fines del proyecto de este capítulo, mencionaré un aspecto importante del código CSS Grid que genera ChatGPT. Si consulta la figura 12.2, observe estas dos cosas:

Dentro del mainelemento, el asideelemento se dispone a la derecha del articleelemento.

El articleelemento ocupa más espacio horizontal que el asideelemento.

Todo esto se hace con CSS Grid. Para entender cómo funciona, primero examine el HTML:

<principal>
    <artículo>
        El contenido del artículo va aquí
    </artículo>
   
    <aparte>
        El contenido aparte va aquí
    </aparte>
</principal>
Normalmente, el navegador web apilaría el articleelemento sobre el asideelemento anterior y ambos ocuparían todo el ancho del mainelemento. Puede salir de ese diseño predeterminado con una instrucción a ChatGPT similar a la siguiente:

El elemento principal es un contenedor de cuadrícula CSS de dos columnas donde la columna del elemento del artículo tiene el doble del ancho de la columna del elemento side.
En este caso, el código CSS Grid resultante coloca el asideelemento a la derecha del articleelemento y ajusta el ancho de los elementos definiendo una cuadrícula de dos columnas para el mainelemento:

principal {
    pantalla: cuadrícula;                      ① 
    columnas de plantilla de cuadrícula: 2fr 1fr;     ② 
}
① Configura el elemento principal como un contenedor de cuadrícula

② Divide el contenedor de la cuadrícula en dos columnas

El articleelemento aparece primero en el código HTML, por lo que se asigna a la columna izquierda y articlea la derecha. La clave aquí es el 2fr 1frvalor de la grid-template-columnspropiedad. Este valor de aspecto extraño define los anchos relativos de las dos columnas de la siguiente manera:

Aprovecha todo el espacio horizontal disponible para el mainelemento.

Divide ese espacio horizontal uniformemente en tres porciones.

Dale dos de esas porciones a la primera columna.

Entregue la porción restante a la segunda columna.

Esto le da un poco de libertad para ajustar estos anchos relativos para que se adapten a su propia página. Por ejemplo, si prefiere que el articleelemento tenga tres unidades del espacio disponible y el asideelemento solo una unidad, puede modificar la regla de la siguiente manera:

principal {
    pantalla: cuadrícula;
    columnas de plantilla de cuadrícula: 3fr 1fr;
}
Como aprenderá en la siguiente sección, aunque CSS Grid hace que su página responda a los cambios de tamaño de la ventana del navegador, no es suficiente para que la página del artículo se muestre bien en todas las pantallas.

12.2.9 Ajuste del diseño de la página del artículo para pantallas pequeñas
Las frunidades que presenté en la sección anterior se conocen como medidas relativas1fr porque el valor de, por ejemplo, depende del ancho disponible (suponiendo que estás trabajando con columnas de cuadrícula) en el contenedor de cuadrícula. Esto hace que tu página responda porque cuando el ancho del contenedor de cuadrícula cambia (quizás porque cambia el ancho de la ventana del navegador), el ancho de las columnas cambia automáticamente en relación con el nuevo ancho.

Esto funciona bien en pantallas relativamente grandes (por ejemplo, tabletas, portátiles y ordenadores de sobremesa), pero puede ser un problema en pantallas pequeñas, como la de un smartphone en modo vertical. Para entender lo que quiero decir, examine la figura 12.14, que es la página del artículo de este capítulo mostrada en un smartphone. Observe en particular que las dos columnas son estrechas, lo que dificulta la lectura del texto.



Figura 12.14 En la pantalla de un teléfono inteligente, las columnas de texto pueden volverse demasiado estrechas para una lectura cómoda.

Puede parecer un problema sin solución, pero con CSS se puede crear lo que se conoce como un diseño adaptable , que es un diseño que cambia sus propiedades en función de alguna característica de la pantalla del dispositivo, como su ancho. Con un diseño adaptable, se puede resolver el problema que se muestra en la figura 12.14 haciendo preguntas sobre el ancho de la ventana gráfica del navegador (la parte de la ventana del navegador que muestra la página web).

Por ejemplo, puede preguntar: "¿El ancho de la ventana gráfica es menor a 500 píxeles?" Si la respuesta es no, deja el diseño como está; si la respuesta es sí, puede indicarle al navegador que muestre el artículo como una sola columna, donde el asideelemento viene después del articleelemento pero ambos ocupan todo el ancho de la pantalla.

Puede hacer estas y muchas otras preguntas definiendo consultas de medios en su CSS. Una consulta de medios es una expresión acompañada de un bloque de código que consta de una o más reglas de estilo. La expresión interroga alguna característica de la pantalla, como su ancho. Si esa expresión es verdadera para el dispositivo actual, el navegador aplica las reglas de estilo de la consulta de medios; si la expresión es falsa, el navegador ignora las reglas de la consulta de medios.

Aquí está la sintaxis general para una consulta de medios:

@media ( expresión ) { 
     Las reglas a aplicar si la expresión es verdadera van aquí 
}
El expressionsuele min-widthir max-widthseguido de dos puntos y un valor. Por ejemplo, si desea aplicar estilos en una pantalla cuyo ancho no supere el valor especificado, utilice max-width. El código siguiente le indica al navegador que muestre el mainelemento como una cuadrícula de una columna siempre que el ancho de la pantalla sea menor o igual a 500 px:

@media (ancho máximo: 500px) {
    principal {
        pantalla: cuadrícula;
        columnas de plantilla de cuadrícula: 1fr;
    }
}
Para solicitarle a ChatGPT que incluya una consulta de medios en su código CSS, incluya una instrucción como la siguiente en su solicitud:

Para pantallas con un ancho menor o igual a 500 px, haga que el elemento principal sea una cuadrícula de una columna.
De manera similar, si desea aplicar estilos en una pantalla que tenga al menos el mismo ancho que un valor especificado, utilice min-width. El siguiente código establece el tamaño de fuente en el h1elemento siempre que el ancho de la pantalla sea mayor o igual a 1024 px:

@media (ancho mínimo: 1024px) {
    h1 {
        tamaño de fuente: 72px;
    }
}
Para solicitarle a ChatGPT que incluya esta consulta de medios en su código CSS, incluya una instrucción como la siguiente en su solicitud:

Para pantallas con un ancho mayor o igual a 1024 px, haga que el tamaño de fuente del elemento h1 sea 72 px.
Más adelante, después de mostrarle el diseño final de la página del artículo (consulte la figura 12.16), también le mostraré cómo se muestra la página en un teléfono inteligente (figura 12.17) para verificar que la página, de hecho, se ha adaptado a la pantalla más pequeña al cambiar a un diseño de una sola columna.

Ahora ya sabes todo lo que necesitas para pedirle a ChatGPT que cree una página de artículo, como se describe en la siguiente sección.

12.2.10 Elaboración del mensaje inicial para la página del artículo
El proyecto de este capítulo es una página de artículo que muestra una guía de viajes sobre un lugar de una obra literaria. Antes de continuar, supongo que tienes lo siguiente a mano:

El contenido del encabezado, como el logotipo, el título y el eslogan del sitio web.

Las fuentes de Google Fonts que desea utilizar para los títulos y el texto.

Las palabras clave de los colores que desea utilizar para los fondos y el texto de la página.

Consulte el capítulo 3 para obtener más información sobre cada uno de estos elementos de diseño y cómo solicitar a ChatGPT sugerencias de título, tipo de letra y color.

Para iniciar su solicitud, dígale a ChatGPT que desea construir una página web y que desea que genere el código por usted:

Quiero crear una página web para un artículo. No sé programar, así que necesito que me proporciones el código.
 
Primero, escriba el código HTML para una página web que incluya lo siguiente:
Ahora revise el contenido de la página, elemento por elemento, incluido lo siguiente (consulte la figura 12.15):

Un encabezado que incluye el logotipo, el título y el eslogan de su sitio web.

Un elemento de navegación con enlaces a otras áreas del sitio.

Un elemento principal que incluye un articleelemento y una asideorganización de elementos.ed en dos columnas

Un pie de página que incluye un aviso de derechos de autor



Figura 12.15 Las secciones de la página del artículo

Ten en cuenta que en este proyecto no vas a incluir el contenido de la página (es decir, las secciones y párrafos que forman el artículo y los párrafos que forman la barra lateral) en tu mensaje. En cambio, una vez que tengas el esqueleto de la página que se muestra en la figura 12.15, agregarás el contenido manualmente, como explico en la sección 12.3.

A continuación, solicite a ChatGPT que genere el CSS:

En segundo lugar, en un archivo separado, escriba el código CSS para lo siguiente:
A continuación, especifique el formato de la página, incluido lo siguiente:

El color de fondo de la página y el color del texto.

Los tamaños de fuente que desea utilizar para los encabezados y el texto de la página.

Las fuentes que se deben utilizar para los encabezados y el texto normal de la página.

Que el diseño debe utilizar CSS Grid

Que el diseño se adapte a pantallas más pequeñas.

A continuación se muestra un ejemplo de solicitud para mi propia página de artículo:

Quiero crear una página web para un artículo. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
 * Un elemento de encabezado que incluye una imagen llamada logo.png, que se almacena en el subdirectorio "imágenes", el título del sitio "Vacaciones de ensueño" y el lema del sitio "Guías de viaje a lugares imaginarios".
 * Un elemento de navegación que incluye los siguientes enlaces:
  * Inicio (enlaces a index.html)
  * Ciencia ficción (enlaces a sci-fi.html)
  * Fantasía (enlaces a fantasy.html)
  * Niños (enlaces a childrens.html)
  * Literario (enlaces a literary.html)
 * Una sección principal que contiene un elemento de artículo y un elemento aparte.
 * El título del elemento del artículo es el encabezado de segundo nivel "Guía de viaje a Narnia".
 * El título del elemento aparte es el encabezado de tercer nivel "Guías relacionadas".
 * Un elemento de pie de página que incluye el símbolo de Copyright, seguido de "Dream Vacations, LLC".
 * En la sección del encabezado de la página, incluya la etiqueta <meta charset="utf-8">.
 * En la sección del encabezado de la página, incluya la etiqueta <meta name="viewport" content="width=device-width, initial-scale=1">.
  
En segundo lugar, en un archivo separado escriba el código CSS para lo siguiente:
 * El texto de la página utiliza un tamaño de fuente de 20px y la fuente Baskerville de Google Fonts.
 * El encabezado tiene un color de fondo azul claro y un relleno de 24 px.
 * El título del sitio es de 64 px y utiliza la fuente Raleway de Google Fonts.
 * El lema del sitio es de 32 px y utiliza la fuente Raleway de Google Fonts.
 * El encabezado de segundo nivel mide 36 px y utiliza la fuente Raleway de Google Fonts.
 * Los encabezados de tercer nivel son de 24 px y utilizan la fuente Raleway de Google Fonts.
 * El título del artículo y el título aparte tienen un margen superior de 10 px.
 * El margen lateral tiene un borde sólido de color azul claro de 1 px.
 * Los elementos de navegación, artículo, apartado y pie de página tienen un relleno de 10 px.
 * El pie de página tiene un borde superior azul claro de 1 px y un margen superior de 10 px.
 * La página tiene un ancho máximo de 800px y está centrada dentro de la ventana del navegador.
 * Estilo a todos los enlaces con color azul medianoche y sin subrayado.
 * Distribuye la página de la siguiente manera:
  * El encabezado es un contenedor CSS Grid de dos columnas con el logotipo en la columna izquierda y el título del sitio y el lema en la columna derecha.
  *La barra de navegación es un contenedor de filas Flexbox.
  * El elemento principal es un contenedor CSS Grid de dos columnas; la columna del elemento article tiene el doble del ancho de la columna del elemento aside; hay un espacio de 10px entre las columnas.
 * Para pantallas con ancho menor o igual a 500px, haga lo siguiente:
  * Convierte cada cuadrícula de dos columnas en una cuadrícula de una columna.
  * Haga que el título del sitio tenga 40 px y el eslogan, 24 px.
  * Dale al logotipo del sitio un ancho máximo de 150 px.
  * Centrar el contenido del encabezado.
Utilicé Copilot en modo Precise para enviar mi mensaje. El código generado generó la página que se muestra en la figura 12.16.



Figura 12.16 Mi página de artículo antes de agregar el contenido

La figura 12.16 muestra cómo se ve la página en un monitor de escritorio. Para comprobar que la consulta de medios en el mensaje funciona correctamente, es necesario cargar la página mediante el navegador de un teléfono inteligente, como se muestra en la figura 12.17. En este caso, la consulta de medios ha adaptado la página de la siguiente manera:

El encabezado ahora es un contenedor de cuadrícula de una sola columna.

Se ha reducido el tamaño máximo del logotipo del sitio.

Se ha reducido el tamaño de fuente del título y del eslogan del sitio.

El elemento principal ahora es un contenedor de cuadrícula de una sola columna.



Figura 12.17 El esqueleto del artículo adaptado a la pantalla de un teléfono inteligente a través de una consulta de medios

Con el código de la página esqueleto del artículo copiado en su editor de texto, su próxima tarea es completar el contenido faltante.

12.3 Añadir contenido a la página
El código HTML generado por ChatGPT incluye las etiquetas y el texto básicos de la página, pero le faltan las partes más importantes: el contenido de los articleelementos asidey . Para completar la página, debe cargar index.html en su editor de texto y luego agregar el contenido manualmente.

Primero, para agregar el contenido de su artículo, examine el código HTML para buscar las siguientes etiquetas:

<artículo>
    <h2>Guía de viaje a Narnia</h2>
    <!-- El contenido del artículo va aquí -->
</artículo>
La línea clave aquí es <!-- Article content goes here -->, que es un marcador de posición para el contenido del artículo. (Las etiquetas <!--y -->crean un comentario , que es un texto que describe el código HTML pero que no aparece cuando se muestra la página en el navegador). Escribe tu contenido debajo de esa línea. En la mayoría de los casos, agregarás lo siguiente:

Un conjunto de etiquetas <p>y debajo del título del artículo (el elemento) y el texto de la introducción del artículo entre esas etiquetas. Siéntase libre de agregar dos o más párrafos de este tipo según sea necesario.</p>h2

Después del párrafo (o párrafos) introductorio, agregue uno o más sectionelementos, cada uno de los cuales tiene un encabezado de tercer nivel ( h3), seguido de uno o más párrafos (cada uno entre un conjunto de etiquetas <p>y ).</p>

Una vez que el artículo esté completo, agregue el contenido de la barra lateral. Para comenzar, examine el código HTML para buscar las siguientes etiquetas:

<aparte>
    <h3>Guías relacionadas</h3>
    <!-- Las guías relacionadas aparecen aquí -->
</aparte>
Nuevamente, la línea importante aquí es <!—Related guides go here -->(su texto será diferente según el encabezado que haya usado en su mensaje). Esta línea es un marcador de posición para el asidecontenido. Escriba su contenido debajo de esa línea, y su contenido puede ser un conjunto de párrafos, una lista de enlaces o algo más relacionado con el artículo. Siéntase libre de agregar nuevos h3elementos según lo necesite su contenido. La Figura 12.18 muestra la parte superior de la página de mi artículo con contenido.



Figura 12.18 Mi página de artículos, ahora con contenido agregado

Si está satisfecho con la página de su artículo, puede que prefiera omitir el resto de este capítulo e implementar su página en la web (como describo en el apéndice B). Si desea obtener más información sobre el código de la página del artículo, siga leyendo.

12.4 Examinar el código de la página del artículo
Las dos secciones siguientes ofrecen guías comentadas sobre el código HTML y CSS que se encuentra detrás de la página de esqueleto del artículo que se muestra anteriormente en las figuras 12.16 y 12.17. Comenzaré en la siguiente sección con el código HTML.

NOTA: El código HTML y CSS generado para la página de mi artículo están disponibles en el sitio web de este libro ( www.manning.com/books/build-a-website-with-chatgpt ) y en el repositorio de GitHub del libro: https://github.com/paulmcfe/websites-with-chatgpt .

12.4.1 Examinar el HTML
Aquí hay una versión anotada del código HTML que ChatGPT generó para la página de mi artículo:

<!DOCTYPE html>
<html>
<cabeza>
    <meta conjunto de caracteres="utf-8">
    <meta name="viewport"                                      ① 
          content="width=ancho-del-dispositivo, escala-inicial=1">       ①
    <title>Vacaciones de ensueño</title>
    <link rel="hoja de estilo" type="text/css" href="styles.css"> ②
</cabeza>
<cuerpo>
    <header>                                                   ③ 
        <img src="images/logo.png" alt="Logotipo">                 ③④ 
        <div>                                                  ③ 
            <h1>Vacaciones de ensueño</h1>                           ③⑤ 
            <p>Guías de viaje a lugares imaginarios</p>           ③⑥ 
        </div>                                                 ③ 
    </header>                                                  ③ 
    <nav>                                                      ⑦ 
        <a href="index.html">Inicio</a>                          ⑦ 
        <a href="sci-fi.html">Ciencia ficción                       </a> ⑦ 
        <a href="fantasy.html">Fantasía</a>                     ⑦ 
        <a href="childrens.html">Infantil</a>                ⑦ 
        <a href="literary.html">Literario</a>                   ⑦ 
    </nav>                                                     ⑦ 
    <main>                                                     ⑧ 
        <article>                                              ⑧⑨ 
            <h2>Guía de viaje a Narnia</h2>                    ⑧⑨⑩ 
            <!-- El contenido del artículo va aquí -->                 ⑧⑨⑪ 
        </article>                                             ⑧⑨ 
        <aside>                                                ⑧⑫ 
            <h3>Guías relacionadas</h3>                            ⑧⑫⑬ 
            <!-- Las guías relacionadas van aquí -->                    ⑧⑫⑭ 
        </aside>                                               ⑧⑫ 
    </main>                                                    ⑧ 
    <footer>                                                   ⑮ 
        © Dream Vacations, LLC                                 ⑮ 
    </footer>                                                  ⑮
</cuerpo>
</html>
① Ayuda a que la página se muestre correctamente en dispositivos móviles

② Le dice al navegador web dónde encontrar el código CSS

③ Encabezado de página

④ Logotipo del sitio

⑤ Título del sitio

⑥ Lema del sitio

⑦ Barra de navegación

⑧ Elemento principal

⑨ Elemento del artículo

⑩ Título del artículo

⑪ Marcador de posición para el contenido del artículo

⑫ Elemento aparte

⑬ Título aparte

⑭ Marcador de posición para el contenido aparte

⑮ Pie de página

Tenga en cuenta que el código HTML incluye la siguiente línea:

<link rel="hoja de estilo" href="estilos.css">
Esta etiqueta le dice al navegador web dónde encontrar el código CSS, que describo en la siguiente sección.

12.4.2 Examinar el CSS
Aquí hay una versión anotada del código CSS que ChatGPT generó para la página de mi artículo:

@import url('https://fonts.googleapis.com/css2?family=          ① 
➥ Baskerville:wght@400&family=Raleway:wght@400&display=swap'); ①
  
cuerpo {
    tamaño de fuente: 20px;                                            ② 
    familia de fuentes: 'Baskerville', serif;                          ② 
    ancho máximo: 960px;                                           ② 
    margen: 0 automático;                                             ②
}
  
encabezado {
    pantalla: cuadrícula;                                              ③ 
    columnas de plantilla de cuadrícula: auto 1fr;                            ③ 
    color de fondo: azul claro;                                ④ 
    relleno: 24px;                                              ④
}
 
encabezado h1 {
    tamaño de fuente: 64px;                                            ⑤ 
    familia de fuentes: 'Raleway', sans-serif;                         ⑤
}
  
encabezado p {
    tamaño de fuente: 32px;                                            ⑥ 
    familia de fuentes: 'Raleway', sans-serif;                         ⑥
}
  
navegación {
    pantalla: flex;                                              ⑦ 
    justificar-contenido: espacio entre;                             ⑦
}
  
a {
    color: azul medianoche;                                        ⑧ 
    decoración de texto: ninguna;                                      ⑧
}
  
principal {
    pantalla: cuadrícula;                                              ⑨ 
    columnas-de-plantilla-de-cuadrícula: 2fr 1fr;                             ⑨ 
    espacio: 10px;                                                  ⑨
}
  
artículo h2, aparte h3 {
    margen superior: 10px;                                           ⑩
}
  
aparte {
    borde: 1px azul claro sólido;                                ⑪
}
  
navegación, artículo, aparte, pie de página {
    relleno: 10px;                                              ⑫
}
  
h2 {
    tamaño de fuente: 36px;                                            ⑬ 
    familia de fuentes: 'Raleway', sans-serif;                         ⑬
}
  
h3 {
    tamaño de fuente: 24px;                                            ⑭ 
    familia de fuentes: 'Raleway', sans-serif;                         ⑭
}
 
pie de página {
    borde superior: 1px azul claro sólido;                            ⑮ 
    margen superior: 10px;                                           ⑮
}
  
@media (ancho máximo: 500px) {                                     ⑯ 
    encabezado {                                                    ⑯ 
        columnas de plantilla de cuadrícula: 1fr;                             ⑯ 
        alineación de texto: centro;                                     ⑯ 
    }                                                           ⑯ 
                                                               ⑯ 
    encabezado img {                                                ⑯ 
        ancho máximo: 150px;                                       ⑯ 
        margen izquierdo: automático;                                      ⑯ 
        margen derecho: automático;                                     ⑯ 
        visualización: bloque;                                         ⑯ 
    }                                                           ⑯ 
                                                               ⑯ 
    encabezado h1 {                                                 ⑯ 
        tamaño de fuente: 32px;                                        ⑯ 
    }                                                           ⑯ 
                                                               ⑯ 
    encabezado p {                                                  ⑯ 
        tamaño de fuente: 24px;                                        ⑯ 
    }                                                           ⑯ 
                                                               ⑯ 
    principal {                                                      ⑯ 
        columnas de plantilla de cuadrícula: 1fr;                             ⑯ 
}                                                               ⑯
① Importa las tipografías Baskerville y Raleway de Google Fonts

② Diseña el tamaño y la fuente del texto, establece el ancho máximo y centra la página.

③ Configura el encabezado como una cuadrícula de dos columnas

④ Diseña el color de fondo y el relleno del encabezado

⑤ Diseña el tamaño de fuente y la fuente del título del sitio.

⑥ Diseña el tamaño de fuente y la fuente del eslogan del sitio.

⑦ Establece el navegador como un contenedor Flexbox con los elementos espaciados uniformemente

⑧ Establece el color de los enlaces y elimina el subrayado.

⑨ Configura el elemento principal como una cuadrícula de dos columnas

⑩ Agrega un margen encima del artículo y al lado de los títulos.

⑪ Dale estilo al costado con un borde

⑫ Agrega relleno a los elementos de navegación, artículo, apartado y pie de página.

⑬ Diseña el tamaño de fuente h2 y la fuente

⑭ Diseña el tamaño de fuente h3 y la fuente

⑮ Aplica estilo al pie de página con un borde superior y un margen

⑯ La consulta de medios para pantallas de 500 px de ancho y menos

Puede consultar las anotaciones HTML y CSS de las dos secciones anteriores para ayudar a personalizar el código de su página web, como describo en la siguiente sección.

12.5 Personalización de la página del artículo
A continuación se ofrecen algunas sugerencias de personalización para el código HTML:

Si prefieres tener la barra lateral a la izquierda, debes cambiar tanto el código HTML como el CSS. Primero, en el código HTML, mueve el asideelemento para que aparezca justo antes del articleelemento:

<principal>
    <aparte>
        <h3>Guías relacionadas</h3>
        <!-- Las guías relacionadas aparecen aquí -->
    </aparte>
    <artículo>
        <h2>Guía de viaje a Narnia</h2>
        <!-- El contenido del artículo va aquí -->
    </artículo>
</principal>
En segundo lugar, en el CSS, cambie el valor maindel elemento de a , como se muestra aquí:grid-template-columns2fr 1fr1fr 2fr

principal {
    pantalla: cuadrícula;
    columnas de plantilla de cuadrícula: 1fr 2fr;
    espacio: 10px;
}
En el encabezado, puedes editar el título y el eslogan. Solo asegúrate de no editar ni eliminar las etiquetas HTML asociadas, <h1>y </h1>y <p>y </p>.

En la sección principal, puedes editar el título del artículo, pero no te metas con las etiquetas HTML asociadas <h2>y </h2>.

En la sección de pie de página del código HTML, puedes agregar enlaces a tus cuentas de redes sociales, como describo en el capítulo 4.

A continuación se muestran algunas ideas de personalización para el código CSS:

Para cualquier valor de color, puede cambiar el color existente a una palabra clave de color diferente.

Para cualquier valor de tamaño de fuente, puede cambiar el número para aumentar o disminuir el tamaño de la fuente. Solo asegúrese de dejar la pxunidad en su lugar.

Para cualquier valor de margen o relleno, puede cambiar el número para aumentar o disminuir el relleno o los márgenes. En cada caso, asegúrese de dejar la pxunidad en su lugar.

Para que el código de tu página sea más accesible, considera convertir todas las medidas en px a medidas en rem. 1 rem equivale de manera predeterminada a 16 px, por lo que 20 px son 1,25 rem, 24 px son 1,5 rem, 32 px son 2 rem, 48 px son 3 rem, y así sucesivamente. La unidad rem es más accesible porque mide los tamaños de fuente en relación con el tamaño de fuente predeterminado que el usuario del navegador ha definido en la configuración de su navegador.

Resumen
Utilice un diseño de artículo si el escrito se centra en un solo tema y puede dividirse en varios subtemas.

Los principales elementos de diseño de página HTML son header, nav, main, article, aside, footery p.

Utilice este articleelemento para marcar una composición completa e independiente, similar a un artículo de periódico o revista. Este elemento también se puede aplicar a una reseña, una entrada de blog, una publicación en un foro o un ensayo.

Utilice el asideelemento para marcar un área de la barra lateral de la página que contenga contenido relacionado indirectamente con el contenido único de la página, como una lista de enlaces a páginas del sitio relacionadas, las últimas noticias del sitio, un canal de redes sociales o anuncios.

Utilice el strongelemento para marcar texto importante, utilice el belemento para marcar palabras clave, utilice el emelemento para agregar énfasis al texto y utilice el ielemento para marcar texto alternativo.

Utilice CSS Grid para diseñar una página en dos dimensiones.

Para obtener mejores resultados, el mensaje de su página debe ser lo más específico posible, incluidos colores, tamaños de fuente y niveles de encabezado.

Guarde el HTML generado en el archivo index.html y el CSS generado en el nombre de archivo sugerido por ChatGPT en el código HTML, generalmente styles.css.
