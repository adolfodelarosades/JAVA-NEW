# 6 Agregar links y navegación

Este capítulo cubre:

* Creación de links a otros sitios y páginas
* Creando una barra de navegación para tu sitio
* Pídele a ChatGPT que te ayude a diseñar tus páginas
* Prompting ChatGPT a crear un sitio web de información para una organización
* Examinar y personalizar el código de la página web de ChatGPT

En cada uno de los proyectos web que ha visto hasta ahora en este libro, ha convencido a ChatGPT para que le proporcione el código para una sola página web. Los sitios web de una sola página son legión en la web, pero es más común que un sitio tenga dos o más páginas. Sin embargo, una vez que agrega esa segunda página, surgen preguntas rápidamente: ¿Cómo lleva a un visitante del sitio desde su página de inicio a la otra página? Y una vez que alguien llega a esa otra página, ¿cómo lo lleva de regreso a la página de inicio? ¿Cómo resuelve todo esto con un sitio que tiene tres, cuatro o incluso más páginas?

Responder a estas y otras preguntas similares es el tema de este capítulo. En las páginas siguientes, aprenderá a permitir que un visitante de su sitio salte de una página a otra pidiéndole a ChatGPT que cree un código de página web que cree un vínculo a otra página en el que se pueda hacer clic. También aprenderá a pedirle a ChatGPT que cree un elemento especial de página web llamado barra de navegación que reúne vínculos a todas las páginas de su sitio en una única ubicación práctica para facilitar el acceso.

Toda esta información se incluye en un prompt detallado que deberá enviar a ChatGPT para generar el código de un patrón de proyecto muy común: un sitio web que proporciona información sobre una organización. Este capítulo también proporciona una explicación detallada del código generado por ChatGPT y sugerencias para personalizar el código manualmente para que todo quede exactamente como lo desea.

## 6.1 Comprender el proyecto de este capítulo

En este capítulo, utilizará ChatGPT para crear un sitio web de información simple para una organización. La página final incluirá los siguientes componentes:

* Un elemento de header que incluye el título y el eslogan del sitio.
* Un elemento de navegación con enlaces a otras páginas del sitio.
* Un elemento main que incluye una introducción al sitio, así como contenido atractivo para el lector.
* Un elemento footer que incluye un aviso de derechos de autor

La figura 6.1 muestra un ejemplo de la página de inicio de un sitio web de información creada a partir del código generado por ChatGPT. Este tipo de sitio web se puede modificar fácilmente para que funcione como sitio de información para una comunidad, una organización benéfica, un evento, un equipo o una banda, o incluso para una película o un programa de televisión favoritos.

![image](https://github.com/user-attachments/assets/51745a48-a15f-4532-a1bd-5b5c16c9b899)

**Figura 6.1 Página de inicio de un sitio web de información generada por ChatGPT**

## 6.2 Creación de la página de inicio del sitio de información

Un sitio web de información contiene varias páginas web, por lo que es una buena idea crear el sitio en etapas. El proceso que recomiendo se resume aquí:

Solicite a ChatGPT que genere el código HTML para la página de inicio del sitio web.

Indique a ChatGPT que genere el código CSS para el estilo del sitio web. Tenga en cuenta que es mejor combinar estos dos primeros pasos en un solo mensaje.

Para cada una de las demás páginas de su sitio, solicite a ChatGPT que genere el código HTML para esa página. En particular, la solicitud para cada una de las demás páginas del sitio debe incluir lo siguiente:

Una instrucción para utilizar el mismo archivo CSS en el que guardó el CSS generado en el paso 2.

Una instrucción para no generar estilos adicionales, en particular estilos en línea (es decir, código CSS insertado directamente en las etiquetas HTML). ChatGPT siempre desea incluir estilos CSS con su salida HTML, por lo que sin esta instrucción, ChatGPT casi con certeza agregará estilos adicionales, que podrían entrar en conflicto con los estilos en el archivo CSS o anularlos.

Antes de llegar a todo eso, tómese un minuto para familiarizarse con la nueva tecnología de página web presentada en este capítulo.

6.2.1 Creación de enlaces
Una de las características distintivas de HTML (de hecho, es la H en HTML ) es el hipertexto , que es simplemente una palabra elegante para los enlaces que lo llevan a otras páginas, ya sea que esas páginas existan en otra parte de su sitio web o en cualquier lugar de la web. Un enlace suele ser una palabra o frase configurada de modo que cuando alguien hace clic en ese texto, el navegador web navega a cualquier página web especificada por la configuración del enlace.

Si está creando un vínculo a una página de su sitio que se encuentra en el mismo directorio que el archivo HTML actual, puede solicitarle a ChatGPT un vínculo a ese nombre de archivo. A continuación, se muestra un código que solicita un vínculo a una página llamada about.html:

Proporcione el código HTML para un enlace a una página web llamada about.html.
La figura 6.2 muestra el resultado de la aplicación ChatGPT. Este es el código HTML que devuelve ChatGPT:

<a href="about.html">Acerca de</a>


Figura 6.2 Código de ChatGPT para un enlace a la página about.html

Como muestra el código, las etiquetas HTML que se utilizan para crear un enlace son <a>y su </a>etiqueta de cierre correspondiente. En el aelemento, se utiliza el hrefatributo para insertar la dirección (a menudo denominada URL , abreviatura de localizador uniforme de recursos ) del enlace. La figura 6.3 muestra cómo funciona este elemento.



Figura 6.3 La sintaxis a utilizar para la <a>etiqueta

Si el archivo de su sitio al que desea vincular reside en un directorio diferente, debe incluir el nombre de ese directorio en su solicitud:

Proporcione el código HTML para un enlace a una página web llamada index.html en el directorio /faq.
La figura 6.4 muestra el resultado de la aplicación ChatGPT. Este es el código HTML que devuelve ChatGPT:

<a href="/faq/index.html">Preguntas frecuentes</a>


Figura 6.4 Código de ChatGPT para un enlace a la página index.html en el directorio /faq

Tenga en cuenta que antepuse una barra diagonal ( /) al nombre del directorio, lo que indica a la IA que el directorio especificado se ejecuta desde el directorio raíz de mi sitio. Si, en cambio, la ubicación es un subdirectorio del directorio donde se encuentra su archivo HTML, omita la barra diagonal en el mensaje.

En el caso de una página web externa, suele ser más fácil crear un enlace vacío (es decir, <a href="">link text</a>navegar a la página, copiar la dirección y luego pegar esa dirección entre las comillas del hrefvalor del atributo). Sin embargo, si la página se puede describir (por ejemplo, conoce el nombre del sitio y puede describir el contenido de la página de forma única en pocas palabras), ¿por qué no dejar que su asistente de inteligencia artificial haga el trabajo sucio por usted? Aquí hay un ejemplo:

Proporcione el código HTML para un enlace a la página de Wikipedia sobre colinabos.
La figura 6.5 muestra el resultado de la aplicación ChatGPT. Este es el código HTML que devuelve ChatGPT:

<a href="https://en.wikipedia.org/wiki/Rutabaga">Rutabaga</a>


Figura 6.5 Código de ChatGPT para un enlace a la página de rutabagas en Wikipedia

6.2.2 Creación de la barra de navegación
Un patrón muy común en los sitios web es la barra de navegación , que es una colección de enlaces a otras páginas del sitio web (o, si el sitio es grande, a las páginas más importantes del sitio). La barra de navegación puede ser horizontal o vertical, pero la configuración más común es una franja horizontal que recorre la página, justo debajo del encabezado. La Figura 6.6 muestra un ejemplo.



Figura 6.6 Un ejemplo de una barra de navegación

En HTML, se crea una barra de navegación utilizando las etiquetas <nav>y </nav>. Entre estas etiquetas, se agregan los enlaces a cada página del sitio. Puede solicitar a ChatGPT que genere una barra de navegación similar incluyendo la siguiente instrucción en su mensaje:

Crea un elemento de navegación que incluya cinco enlaces:
* El texto “Inicio” que enlaza al archivo “index.html”.
* El texto "Blog" que enlaza al archivo "blog.html".
* El texto "FAQ" que enlaza al archivo "faq.html".
* El texto "Acerca de" que enlaza al archivo "about.html".
* El texto “Contacto” que enlaza al archivo “contact.html”.
Basándose en esta instrucción, ChatGPT generará un código HTML similar al siguiente (que es el código que creó la barra de navegación que se muestra en la figura 6.6):

<navegación>
    <a href="index.html">Inicio</a>
    <a href="blog.html">Blog</a>
    <a href="faq.html">Preguntas frecuentes</a>
    <a href="about.html">Acerca de</a>
    <a href="contacto.html">Contacto</a>
</nav>
Es posible que notes dos cosas extrañas sobre cómo el navegador representa la lista en la figura 6.6:

La lista se ejecuta horizontalmente en lugar de verticalmente.

Los elementos de la lista están espaciados uniformemente a lo largo de la página.

El navegador muestra la barra de navegación de esa manera debido al siguiente código CSS, que aplica algunas propiedades al navelemento:

navegación {
    borde superior: 1px azul medianoche sólido;         ① 
    borde inferior: 1px azul medianoche sólido;      ① 
    pantalla: flexible;                              ② 
    justificar contenido: espacio entre;             ③ 
    margen: 20px 0;                             ④ 
    relleno: 10px 0;                            ④ 
}
① Agrega un borde arriba y debajo del elemento de navegación

② Convierte el elemento de navegación en un contenedor Flexbox

③ Le indica al navegador que espacie los elementos de manera uniforme

④ Aplica estilo a los márgenes y al relleno del elemento de navegación.

Lo más importante que hay que tener en cuenta aquí es la display: flexdeclaración, que convierte el navelemento en un contenedor Flexbox. De forma predeterminada, muestra sus elementos de forma horizontal en lugar de vertical. (Aprenderá más sobre Flexbox en el capítulo 10).

NOTA: Según la cantidad de elementos de la barra de navegación, es posible que ese elemento sea demasiado ancho para visualizarse bien en pantallas pequeñas, en particular en pantallas de teléfonos inteligentes en modo vertical. La solución habitual es convertir el elemento de navegación en un ícono que muestra un menú cuando se hace clic o se toca. Para saber cómo solicitarle a ChatGPT que genere el código para un menú como este, consulte el capítulo 12.

Ahora tienes todo lo que necesitas saber para crear el mensaje de tu página de inicio para ChatGPT.

6.2.3 Elaboración del mensaje de la página de inicio
El proyecto de este capítulo es un sitio web informativo. Antes de pasar a la parte de presentación del programa, asegúrese de tener estos elementos:

Algunos o todos los siguientes: un logotipo de página, un título y un eslogan.

Los nombres de los tipos de letra que desea utilizar para los encabezados de página y el texto de la página.

Las palabras clave de los colores que desea aplicar a los fondos y textos de las páginas.

Consulta el capítulo 3 para obtener más información sobre estos elementos de diseño y cómo solicitar a ChatGPT sugerencias de título, tipo de letra y color.

Ahora está listo para solicitar a ChatGPT que lo ayude a generar el código para la página de inicio de su sitio web de información. El mensaje debería comenzar así:

Quiero crear una página web para un sitio web de información. No sé programar, así que necesito que me proporciones el código.
Primero, escriba el código HTML para una página web que incluya lo siguiente:
A continuación, especifique el contenido de su página, incluido lo siguiente (consulte la figura 6.7):

Un encabezado que incluye el título y el eslogan de su sitio

Un elemento de navegación que incluye enlaces a otras páginas del sitio (o a las páginas principales del sitio)

Un elemento principal con un párrafo introductorio que da la bienvenida a los visitantes al sitio.

Uno o más elementos de sección que muestran contenido atractivo para el lector.

Un pie de página que incluye un aviso de derechos de autor



Figura 6.7 Los elementos de la página de inicio del sitio web de información

A continuación, le pides a ChatGPT que genere el CSS según el formato que deseas para tu página:

En segundo lugar, en un archivo separado, escriba el código CSS para lo siguiente:
A continuación, especifique el formato, incluido lo siguiente:

El color de fondo de la página y el color del texto.

Los tamaños de fuente que desea utilizar para el título y el eslogan de la página.

El tamaño de letra de los encabezados y del texto de la página.

Las fuentes que se deben utilizar para los encabezados y el texto normal de la página.

Un ancho máximo para la página. Esto evita que las líneas de texto sean demasiado largas. Una longitud máxima de 800 px es adecuada para este tipo de sitio.

A continuación se muestra un ejemplo de solicitud para mi propia página de información:

Quiero crear una página de inicio para un sitio web informativo. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
 * El título de la página es "Sociedad para la Preservación de Palabras Antediluvianas".
 * Un encabezado que incluye el título "Sociedad de Preservación de Palabras Antediluvianas" y el lema "Preservando palabras del pasado, para el futuro".
 * Después del encabezado, un elemento de navegación que incluye cinco enlaces:
   * El texto “Inicio” que enlaza al archivo “index.html”.
   * El texto "Blog" que enlaza al archivo "blog.html".
   * El texto "FAQ" que enlaza al archivo "faq.html".
   * El texto "Acerca de" que enlaza al archivo "about.html".
   * El texto “Contacto” que enlaza al archivo “contact.html”.
 * Un elemento principal que incluye lo siguiente:
   * Un párrafo introductorio que incluya el texto "Bienvenidos a la Sociedad para la Preservación de Palabras Antediluvianas, donde nuestro objetivo es proteger, preservar y promover palabras antiguas que corren el riesgo de quedar olvidadas, pasadas de moda y obsoletas. Quédense un rato, miren a su alrededor y disfruten del brillo bruñido de estas antiguas y hermosas palabras".
  * Un elemento de sección con el encabezado de segundo nivel "Palabra más reciente", seguido de un encabezado de tercer nivel con el texto "*hullaballoo* (hul·uh·buh·LOO, sustantivo)", seguido de un párrafo que incluye el texto "Un gran ruido o conmoción; un alboroto. (Ejemplo: "Después de escuchar el **alboroto** que ocho niños drogados con azúcar podían armar, Rupert decidió no volver a ofrecerse como voluntario para ayudar en una fiesta de Halloween"). [etc.]".
  * Otro elemento de sección con el encabezado de segundo nivel "El desafío de esta semana" seguido de un párrafo que incluye el texto "Tu desafío esta semana es usar la palabra *tomfoolery* (comportamiento tonto o absurdo) al menos una vez en cada uno de los siguientes casos: en una conversación, en un mensaje de correo electrónico, en un mensaje de texto y en una reunión de negocios (virtual o real). ¡Buena suerte y cuéntanos cómo te va!"
  * En el texto anterior, haga que cada palabra que esté rodeada por asteriscos dobles esté en negrita, y cada palabra que esté rodeada por asteriscos simples esté en cursiva.
 * Un elemento de pie de página que incluye el símbolo de Copyright, seguido del año actual, seguido de "Antediluvian Word Preservation Society".
 * En la sección del encabezado de la página, incluya la etiqueta <meta charset="utf-8">.
 
En segundo lugar, en un archivo separado escriba el código CSS para lo siguiente:
 * El elemento del cuerpo tiene un relleno de 25 px y un color de fondo de oldlace.
 * Establezca el título en 64 px, la altura de línea en 1, el color azul medianoche, el margen inferior en 20 px y la tipografía Playfair Display de Google Fonts.
 * El tamaño de fuente del eslogan debe ser de 30 px.
 * El elemento de navegación tiene un borde superior e inferior de color azul medianoche.
 * El elemento de navegación tiene un borde superior e inferior de 20 px y un relleno superior e inferior de 10 px.
 * Diseña los enlaces de navegación con un tamaño de fuente de 24 px;
 * Espacie los enlaces de navegación de modo que abarquen todo el ancho del cuerpo.
 * Diseñe los encabezados de segundo nivel con un tamaño de 48 px, un margen superior de 30 px, un margen inferior de 10 px, el color azul medianoche y la tipografía Playfair Display de Google Fonts.
 * Dale estilo al resto del texto de la página con un tamaño de 24 px, el color darkslategray y la tipografía Lora de Google Fonts.
 * Dale estilo a los enlaces con el color azul acero y sin subrayado.
 * El pie de página tiene un relleno superior e inferior de 10 px, un margen superior de 50 px y un borde superior e inferior de color azul medianoche.
 * La página tiene un ancho máximo de 800px y está centrada dentro de la ventana del navegador.
ChatGPT debe crear primero el código HTML, que puedes copiar y pegar y guardar en un archivo llamado index.html. En ese código, deberías ver una línea cerca de la parte superior similar a la siguiente:

<link rel="hoja de estilo" tipo="texto/css" href="estilos.css">
Este código le indica al navegador web que busque el código CSS en un archivo llamado styles.css, por lo que la siguiente tarea es copiar el código CSS generado, pegarlo en un archivo y guardarlo como styles.css (o cualquier nombre que vea en la <link>etiqueta). Asegúrese de guardar styles.css en la misma carpeta que su archivo index.html. También debe copiar su archivo de imagen en la misma carpeta. Consulte el apéndice A para obtener más información sobre cómo trabajar con archivos de páginas web.

Envié este mensaje a GPT-4 mediante la aplicación ChatGPT de OpenAI. El código generado generó la página que se muestra en la figura 6.8.



Figura 6.8 Página de inicio del sitio web Mi información generada por ChatGPT

Si le gusta el sitio web de información que ChatGPT creó para usted, puede omitir el resto de este capítulo e implementar el código como describo en el apéndice B. Sin embargo, si desea saber más sobre el código que generó ChatGPT, la siguiente sección le brinda una mirada más cercana.

6.3 Examinar el código de la página de inicio
Si tiene curiosidad acerca del código que genera ChatGPT, en esta sección le brindaré una descripción general breve y no demasiado técnica del código del sitio web de información que resultó de mi solicitud de la sección anterior (la página de inicio del sitio web de información se muestra en la figura 6.8).

NOTA El código HTML y CSS generado para la página de inicio de mi sitio web de informaciónLas edades están disponibles en el sitio web de este libro ( www.manning.com/books/build-a-website-with-chatgpt ) y en el repositorio de GitHub del libro: https://github.com/paulmcfe/websites-with-chatgpt .

Cada versión de ChatGPT debe generar código HTML y CSS que sea al menos similar a lo que se muestra en las siguientes dos secciones, por lo que mis anotaciones de código deberían ayudarlo a comprender lo que sucede bajo el capó.

6.3.1 Examinar el HTML
El código HTML que ChatGPT generó para la página de inicio de mi sitio de información se muestra aquí:

<!DOCTYPE html>
<html>
<cabeza>
  <title>Sociedad para la preservación de las palabras antediluvianas</title>
  <meta charset="utf-8">                                                     ①
  <link href="https://fonts.googleapis.com/css2?
  familia= Playfair+Pantalla:wght@400;700&display=swap"
  rel="hoja de estilo">                                                          ②
  <link href="https://fonts.googleapis.com/css2?
  familia=Lora:ital,peso@0,400;0,700;1,400&display=swap"
  rel="hoja de estilo">                                                          ② 
  <link rel="hoja de estilo" href="estilos.css">                                  ③
</cabeza>
<cuerpo>
  <header>                                                                   ⑥ 
    <h1>Sociedad para la Preservación de Palabras Antediluvianas</h1>                          ④⑥ 
    <p>Preservando palabras del pasado, para el futuro</p>                    ⑤⑥ 
  </header>                                                                  ⑥ 
  <nav>                                                                      ⑦ 
    <a href="index.html">Inicio</a>                                            ⑦ 
    <a href="blog.html">Blog</a>                                             ⑦ 
    <a href="faq.html">Preguntas frecuentes</a>                                               ⑦ 
    <a href="about.html">Acerca de</a>                                           ⑦ 
    <a href="contact.html">Contacto</a>                                       ⑦ 
  </nav>                                                                     ⑦ 
  <main>                                                                     ⑧ 
    <p>Bienvenido a la Sociedad para la Preservación de Palabras Antediluvianas,                ⑧ 
       donde nuestro objetivo es proteger, preservar y promover palabras antiguas               ⑧ 
       que están en peligro de pasar desapercibidas, quedar obsoletas            ⑧ 
       y pasar de moda. Quédate un rato, echa un vistazo alrededor y disfruta              ⑧ 
       del brillo bruñido de estas antiguas y hermosas palabras.</p>          ⑧ 
    <section>                                                                ⑧ 
      <h2>Palabra más reciente</h2>                                              ⑧ 
      <h3><em>alboroto</em> (hul·uh·buh·LOO, sustantivo)</h3>                   ⑧ 
      <p>Un gran ruido o conmoción; un alboroto. (Ejemplo: "Después de escuchar     ⑧ 
         el <strong>alboroto</strong> que ocho niños drogados con       ⑧ 
         azúcar podían hacer, Rupert decidió no ofrecerse nunca más como voluntario para ayudar   ⑧ 
         en una fiesta de Halloween"). Esta es una palabra divertida para usar en            ⑧ 
         una conversación, y es perfecta si necesitas un sinónimo inusual para   ⑧ 
         <em>ruido</em> o <em>conmoción</em>. Es lo suficientemente oscura      ⑧ 
         como para que no se use demasiado,    pero no es tan oscuro como para que la mayoría de las 
         personas no lo reconozcan y se rían para sí mismas.               
         <em>Hullabaloo</em> comenzó como la palabra <em>halloo</em>,     ⑧ 
         que significa "instar o incitar con gritos". Luego, a través del proceso de   ⑧ 
         reduplicación de la rima, se agregó la parte <em>balloo</em> para formar   ⑧ 
         <em>halloo-balloo</em>, que finalmente se transformó en                 ⑧ 
         <em>hullabaloo</em>. Algunos sinónimos que se registran de manera similar en ⑧ 
         el medidor de diversión son <em>brouhaha</em>, <em>hubbub</em> y           ⑧ 
         <em>hurly-burly</em>.</p>                                           ⑧ 
    </section>                                                               ⑧ 
    <section>                                                                ⑧ 
      <h2>El desafío de esta semana</h2>                                         ⑧ 
         <p>Tu desafío esta semana es usar la palabra <em>tomfoolery</em> ⑧ 
         -- comportamiento tonto o estúpido -- al menos una vez en cada uno de los        ⑧ 
         siguientes: en una conversación, en un mensaje de correo electrónico, en un          ⑧ 
         mensaje de texto y en una reunión de negocios (virtual o del mundo real).         ⑧ 
         ¡Buena suerte y cuéntanos cómo te va!</p>                     ⑧ 
    </section>                                                               ⑧ 
  </main>                                                                    ⑧ 
  <footer>                                                                   ⑨ 
    © 2023 Antediluvian Word Preservation Society                       ⑨ 
  </footer>                                                                  ⑨
</cuerpo>
</html>
① Especifica el conjunto de caracteres de la página

② Carga las fuentes de la página desde Google Fonts

③ Le dice al navegador web dónde encontrar el código CSS

④ Título de la página

⑤ Lema de la página

⑥ Encabezado de página

⑦ Elemento de navegación

⑧ Elemento principal

⑨ Pie de página

A continuación se muestran algunas notas a tener en cuenta al leer el código HTML:

El código <meta charset="utf-8">de la <head>etiqueta del archivo HTML le indica al navegador el conjunto de caracteres que se utiliza en la página. No es necesario que sepas qué significa esto, solo que esta etiqueta es necesaria para que el símbolo de copyright se muestre correctamente. También ayudará a que caracteres como los guiones largos (—) y las comillas tipográficas (“ y ”) se muestren correctamente si utilizas esos y otros caracteres similares en el texto de tu página.

Por alguna razón, ChatGPT hizo referencia a las dos fuentes de Google Fonts mediante dos <link>etiquetas independientes. No tengo idea de por qué, pero funciona, así que lo usé.

En el mensaje, le pedí a ChatGPT que buscara palabras rodeadas de asteriscos dobles (por ejemplo, **hullaballoo**) y que las pusiera en negrita. En el HTML, ChatGPT reemplazó los asteriscos dobles con las etiquetas <strong>y </strong>, que hacen que el texto entre ellos aparezca en negrita.

De manera similar, le pedí a ChatGPT que buscara palabras rodeadas de asteriscos simples (por ejemplo, *noise*) y las pusiera en cursiva. En el HTML, ChatGPT reemplazó los asteriscos con las etiquetas <em>y </em>, que hacen que el texto entre ellos esté en cursiva.

Tenga en cuenta que el código HTML incluye la siguiente línea:

<link rel="hoja de estilo" href="estilos.css">
Esta etiqueta le dice al navegador web dónde encontrar el código CSS, que describo en la siguiente sección.

6.3.2 Examinando el CSS
El código CSS generado por ChatGPT para la página de inicio de mi sitio web de información se muestra aquí:

cuerpo {
  color de fondo: oldlace;               ① 
  ancho máximo: 800px;                        ② 
  margen: 0 automático;                          ③
  relleno: 25px;
}
encabezado h1 {                                ④ 
  tamaño de fuente: 64px;                         ④ 
  altura de línea: 1;                          ④ 
  color: azul medianoche;                     ④ 
  familia de fuentes: 'Playfair Display', serif; ④ 
  margen inferior: 20px;                     ④ 
}                                          ④
encabezado p {
  tamaño de fuente: 30px;                         ⑤
}
nav {                                      ⑥ 
  borde superior: 1px azul medianoche sólido;      ⑥ 
  borde inferior: 1px azul medianoche sólido;   ⑥ 
  margen: 20px 0;                          ⑥ 
  relleno: 10px 0;                         ⑥ 
  visualización: flexible;                           ⑥ 
  justificar contenido: espacio entre;          ⑥ 
}                                          ⑥
navegar a {
    tamaño de fuente: 24px;                       ⑦
}
a {
  color: azul acero;                        ⑧ 
  decoración de texto: ninguna;                   ⑧
}
h2 {
  tamaño de fuente: 48px;                         ⑨ 
  color: azul medianoche;                     ⑨ 
  familia de fuentes: 'Playfair Display', serif; ⑨ 
  margen: 30px 0 0;                        ⑨
}
h3, p, principal p {
  tamaño de fuente: 24px;                         ⑩ 
  color: gris pizarra oscuro;                    ⑩ 
  familia de fuentes: 'Lora', serif;              ⑩
  margen superior: 8px;
}
pie de página {                                   ⑪ 
  borde superior: 1px azul medianoche sólido;      ⑪ 
  borde inferior: 1px azul medianoche sólido;   ⑪ 
  relleno: 10px 0;                         ⑪ 
  margen superior: 50px;                        ⑪ 
}                                          ⑪
① Establece el color de fondo de la página

② Establece el ancho máximo de página en 800 px

③ Centra la página

④ Cambia el tamaño de fuente del título de la página a 64 px, con el color azul medianoche y la fuente Playfair Display.

⑤ Aplica estilo al eslogan con un tamaño de fuente de 30 px

⑥ Da estilo al elemento de navegación (como se describió anteriormente)

⑦ Cambia el tamaño de los enlaces de navegación a 24 px

⑧ Aplica estilo a los enlaces de la página con color azul acero y sin subrayado.

⑨ Aplica estilo a los encabezados de segundo nivel con un tamaño de fuente de 48 px, color azul medianoche y la fuente Playfair Display.

⑩ Aplica estilo al texto de la página normal con un tamaño de fuente de 24 px, color gris pizarra oscuro y la fuente Lora.

⑪ Da estilo al pie de página

Si lo desea, puede utilizar estas anotaciones para modificar el código de su página web, como describo en la siguiente sección.

6.4 Personalización de la página de inicio
Si el código del sitio web de información de ChatGPT está deshabilitado por algún motivo, tienes dos formas de solucionarlo:

Si la página está lejos de lo que quieres, reescribe tu mensaje, inicia una nueva sesión de chat y vuelve a intentarlo.

Si la página se parece a lo que desea, solicite a ChatGPT que realice los ajustes necesarios. Asegúrese de enviar esta solicitud en la misma sesión que la solicitud original.

En el segundo caso, si el código producido por ChatGPT realmente solo necesita algunos pequeños retoques, considere modificar el código manualmente según las anotaciones que proporcioné en la sección anterior. Como no conoce el código de las páginas web, es mejor no intentar realizar cambios importantes. Sin embargo, eso deja bastantes formas de alterar el código para obtener la página que desea.

Primero, aquí hay algunas sugerencias de personalización para el código HTML:

En el encabezado, puedes editar el título o el eslogan. Solo asegúrate de no editar ni eliminar las etiquetas HTML asociadas: <h1>y </h1>para el título, y <p>y </p>para el eslogan.

Edita los sectionelementos según necesites, ajustando el encabezado y el texto.

Para agregar una nueva sección, siga estos pasos:

   a) Abra el archivo HTML en un editor de texto.

   b) Seleccione una sección existente. Es decir, seleccione todo lo que esté entre un único par de etiquetas <section>y </section>, tal como se muestra en la figura 6.9.



Figura 6.9 Seleccionar un elemento de sección existente.

   c) Copie la entrada (por ejemplo, presionando Ctrl-C o Cmd-C).

   d) Cree una nueva línea en el punto donde desea que aparezca la nueva sección. Por ejemplo, si desea que la nueva sección aparezca sobre la primera sección de la página, coloque el cursor inmediatamente antes de la primera <section>etiqueta y luego presione Enter o Return.

   e) Coloque el cursor en la nueva línea que acaba de crear, como se muestra en la figura 6.10.



Figura 6.10 Coloque el cursor donde desea pegar el código que ha copiado.

   f) Pegue el código copiado (por ejemplo, presionando Ctrl-C o Cmd-C).

   g) Editar el título y el texto de la sección.

Si el texto de su entrada incluye varios párrafos, puede asegurarse de que cada párrafo se muestre correctamente rodeándolo con una <p>etiqueta al principio y </p>otra al final:

<sección>
    <h2>Título de sección</h2>
    <p>
        Primer párrafo
    </p>
    <p>
        Segundo párrafo
    </p>
    <p>
        Tercer párrafo
    </p>
</sección>
En la sección de pie de página del código HTML, puedes agregar enlaces a tus cuentas de redes sociales, como describo en el capítulo 4.

A continuación se muestran algunas ideas de personalización para el código CSS:

Si desea que su página tenga un ancho máximo diferente, cambie el max-widthvalor a algo distinto de 800px.

Para cualquier valor de color, puede cambiar el color existente a una palabra clave de color diferente.

Para cualquier valor de tamaño de fuente, puede cambiar el número para aumentar o disminuir el tamaño de la fuente. Solo asegúrese de dejar la pxunidad en su lugar.

Para cualquier valor de margen o relleno, puede cambiar el número para aumentar o disminuir el relleno o los márgenes. En cada caso, asegúrese de dejar la pxunidad en su lugar.

Para darle más espacio a tu texto, crea un espacio extra entre cada línea agregando la declaración line-height: 1.5;en algún lugar de la regla del código CSS body:

cuerpo {
    color de fondo: oldlace;
    ancho máximo: 800px;
    margen: 0 automático;
    rellenotamaño: 25px;
    altura de línea: 1,5;
}
Para que el código de tu página sea más accesible, considera convertir todas las medidas en px a medidas en rem. 1 rem equivale de manera predeterminada a 16 px, por lo que 20 px son 1,25 rem, 24 px son 1,5 rem, 32 px son 2 rem, 48 px son 3 rem, y así sucesivamente. La unidad rem es más accesible porque mide los tamaños de fuente en relación con el tamaño de fuente predeterminado que el usuario del navegador ha definido en la configuración de su navegador.

6.5 Creación de indicaciones para las demás páginas del sitio
Aunque algunos sitios web de información constan de una sola página, la mayoría tienen varias páginas y muchos tienen bastantes. Si ese es el caso de su sitio, su próxima tarea es solicitarle a ChatGPT el código para crear las demás páginas.

Afortunadamente, estas otras páginas tendrán una estructura muy similar a la de tu página de inicio, con la única diferencia de que el mainelemento almacenará los encabezados y el texto de cada página. Todo esto significa que el mensaje para cada página de subtema será muy similar al mensaje para tu página de inicio. Ten en cuenta también que no necesitas ningún CSS nuevo para estas páginas de subtemas, por lo que puedes omitir la parte CSS del mensaje.

A continuación se muestra un mensaje genérico que puedes utilizar:

Quiero crear una página para un sitio web de información. No sé programar, así que necesito que me proporciones el código.
  
Escriba el código HTML para una página web que incluya lo siguiente:
 * El título de la página es "[título de la página]".
 * Un elemento de encabezado que incluye el título "[título del sitio]" y el eslogan "[eslogan del sitio]".
* Después del encabezado, un elemento de navegación que incluye los siguientes enlaces:
[Copia tus enlaces de navegación aquí]
*Un elemento principal que incluye el texto entre comillas triples.
 """
[el contenido de la página va aquí]
 """
 * Un elemento de pie de página que incluye el símbolo de Copyright seguido del año actual, seguido de "[título del sitio]".
 * En la sección del encabezado de la página, incluya la etiqueta <meta charset="utf-8">.
 * En la sección del encabezado de la página, incluya una referencia a un archivo de hoja de estilo llamado "styles.css".
 * En la sección del encabezado de la página, incluya una referencia a las fuentes de Google X e Y.
 * No agregue ningún estilo en línea.
Tenga en cuenta la instrucción final a ChatGPT de no agregar estilos en línea, que se refiere al código CSS agregado directamente a una etiqueta HTML. En ausencia de instrucciones relacionadas con CSS, ChatGPT tiene una tendencia a insertar algunas sugerencias de formato en forma de estilos en línea. Debido a que todo el estilo que necesita ya está en su archivo styles.css, debe indicarle a ChatGPT que no agregue ningún estilo nuevo que pueda estropear sus páginas. La Figura 6.11 muestra una página de ejemplo generada por ChatGPT para mi sitio de información.



Figura 6.11 Otra página de información del sitio generada por ChatGPT

Sea cual sea el tipo de entidad que desee destacar (una organización, una comunidad, un evento, una organización benéfica, un equipo o un proyecto), un sitio web informativo es una excelente manera de informar al mundo sobre ella y ayudar a las personas a obtener más información. Ahora, con ChatGPT como su socio de codificación, puede poner en funcionamiento un sitio web completo con solo unas pocas indicaciones.

Resumen
Un enlace es una etiqueta HTML especial que, al hacer clic, lleva al usuario a una página web específica.

Una barra de navegación es una colección de enlaces a otras páginas del sitio web (o, si el sitio es grande, a las páginas más importantes del sitio).

Para obtener mejores resultados, el mensaje de su página debe ser lo más específico posible, incluidos colores, tamaños de fuente y niveles de encabezado.

Guarde el HTML generado en el archivo index.html y el CSS generado en el nombre de archivo sugerido por ChatGPT en el código HTML, generalmente styles.css.
