# 5 Publicación de publicaciones en la página

Este capítulo cubre

* Colaborando con ChatGPT para publicar posts como acordeones
* Generación de nuevas imágenes mediante DALL-E
* Prompting ChatGPT para crear una página de diario en línea
* Examinar y personalizar el código de la página web ChatGPT

Aunque a muchas personas no les gusta escribir, a muchos de nosotros realmente nos gusta el acto de poner la pluma sobre el papel o los dedos sobre el teclado. A muchos de nosotros nos encanta escribir tanto que, además de escribir de forma más “seria”, mantenemos un hábito de escritura regular en forma de un diario o bitácora que actualizamos con frecuencia. Y una cantidad sorprendente de esas personas tienen el deseo de publicar sus reflexiones en línea. De hecho, siempre que hablo con gente sobre cómo crear páginas web, la pregunta más común es, con diferencia, “¿Cómo empiezo un diario/blog en línea?”.

Afortunadamente, si ya tienes algo escrito, es muy fácil conseguir que ChatGPT te ayude a crear una página web en la que puedas publicar tu prosa para que todo el mundo la lea. También puedes usar IA para generar nuevas imágenes para cosas como logotipos de sitios, íconos e ilustraciones de páginas. Este capítulo también te muestra cómo usar la combinación de ChatGPT y el modelo de creación de imágenes DALL-E de OpenAI para generar las imágenes que necesites para tu página.

Toda esta información se incluye en un mensaje detallado que deberás enviar a ChatGPT para que produzca el código de una página de diario en línea donde puedas publicar cualquier texto que quieras compartir. Este capítulo también ofrece una explicación detallada del código generado por ChatGPT e incluso ofrece algunos consejos para personalizar el código manualmente para que todo quede exactamente como lo deseas.

## 5.1 Comprender el proyecto de este capítulo

En este capítulo, vas a contar con ChatGPT para que te ayude a crear una página web sencilla para un diario en línea. La página final incluirá los siguientes componentes:

* Un elemento header que incluye lo siguiente:
   * El logotipo de la revista (generado por Dall-E)
   * El título de la revista
   * El lema de la revista
* Elemento main donde aparecen las entradas del diario. Cada entrada muestra solo su título al principio, pero al hacer clic en ella, se muestra el contenido de la entrada.
* Un elemento footer que incluye un aviso de derechos de autor.

La Figura 5.1 muestra un ejemplo del tipo de página que creará con la ayuda de ChatGPT en este capítulo. La simplicidad de esta página significa que puede modificarla fácilmente para almacenar entradas para un blog o diario de viaje, ensayos, reseñas de libros o películas, historias de fan fiction o cualquier tipo de escritura periódica.

<img width="685" alt="image" src="https://github.com/user-attachments/assets/1db8a9d6-878d-4bc6-9da6-f6e0616b2daa" />

**Figura 5.1 Una página de diario en línea generada por ChatGPT**

## 5.2 Creación de la página del diario en línea

Antes de crear el prompt que generará el código para la página de tu diario en línea, necesitas algunos antecedentes sobre un elemento de la página web llamado accordion - acordeón, así como también sobre cómo lograr que la IA cree nuevas imágenes a partir de prompts de texto. Las siguientes secciones brindan los detalles.

### 5.2.1 Trabajar con accordions-acordeones

La única tecnología nueva de páginas web que aprenderá en este capítulo es el acordeón , que es un elemento HTML interactivo que permite a los usuarios alternar entre mostrar solo el título de un elemento y el título y el contenido del elemento. Un acordeón consta de dos elementos:

* ***Summary-Resumen***: Un elemento que actúa como título o descripción del acordeón.

* ***Details-Detalles***: Un elemento que contiene la totalidad del contenido del acordeón, incluido el elemento de resumen y cualquier otro contenido que proporcione (como uno o más artículos, encabezados, párrafos, imágenes, etc.)

La idea detrás de un acordeón es que, de manera predeterminada, todo lo que se ve al principio es el elemento de resumen-summary. Por ejemplo, la figura 5.2 muestra parte de una página web con cuatro acordeones. Cada uno muestra actualmente solo su elemento de resumen, como “¡Hola mundo!” en la parte superior, que es el texto de resumen del primer acordeón.

<img width="863" alt="image" src="https://github.com/user-attachments/assets/ec4a12fa-f017-4516-bef0-779fdb4566a0" />

**Figura 5.2 Una página web con cuatro acordeones, cada uno de los cuales muestra solo su texto de resumen**

Observe también la flecha que apunta hacia la derecha a la izquierda del texto de cada elemento de resumen. Esta flecha indica que hay más contenido disponible. Cuando hace clic en un resumen (o en su flecha), el acordeón se expande para mostrar todo el contenido en el elemento de detalles del acordeón. Por ejemplo, al hacer clic en el resumen “¡Hola mundo!” se expande el primer acordeón, como se muestra en la figura 5.3. Observe que la flecha del acordeón ahora apunta hacia abajo para indicar que se muestra el contenido completo del acordeón. Al hacer clic nuevamente en el texto del resumen (o en la flecha), se oculta el contenido detallado.

<img width="877" alt="image" src="https://github.com/user-attachments/assets/86c177ca-fc9e-4230-8ce1-fdd6adf2413f" />

**Figura 5.3 Al hacer clic en el primer elemento de resumen, se abre el acordeón para mostrar su contenido completo.**

Para solicitarle a ChatGPT que use acordeones en tu página, puedes incluir una instrucción similar a la siguiente:

```text
Include a main section where each entry is an accordion using the HTML summary and details elements. For each entry, the summary text is the entry title and the details include the entry date, followed by the entry text. Please provide four sample entries going back four days from today.
```

```text
Incluya una sección principal en la que cada entrada sea un acordeón que utilice los elementos HTML de resumen y detalles. Para cada entrada, el texto de resumen es el título de la entrada y los detalles incluyen la fecha de la entrada, seguida del texto de la entrada. Proporcione cuatro entradas de muestra que se remonten a cuatro días de la fecha actual.
```

El objetivo de usar acordeones es que puedas incluir una gran cantidad de publicaciones en tu página sin abrumar a los visitantes con una gran cantidad de contenido. ¿La mejor noticia? Solo tienes que decirle a ChatGPT que quieres usar acordeones en tu página y se encargará de todos los detalles de HTML y CSS por ti.

### 5.2.2 Generación de imágenes con GPT-4 y DALL-E

Es sorprendente que GPT-4 pueda generar ensayos, poemas, correos electrónicos y, por supuesto, código de páginas web a partir de indicaciones relativamente simples. Sin embargo, si hay una característica que hace que GPT-4 sea “indistinguible de la magia” (en palabras de Arthur C. Clarke), es la capacidad del modelo para convertir el lenguaje natural en imágenes. Es decir, dada una indicación de texto que describe algo (una escena, un objeto, una persona, etc.), GPT-4 puede usar esa descripción para generar una imagen que coincida.

La herramienta detrás de esta hazaña aparentemente mágica es DALL-E (una mezcla del título de la película WALL-E y el apellido del artista Salvador Dalí), un modelo OpenAI optimizado para convertir descripciones de texto en lenguaje natural en imágenes.

**WARNING** Como aprenderá en las secciones siguientes, DALL-E es bastante bueno para convertir texto en imágenes, pero sólo es bastante bueno. Sólo en raras ocasiones generará imágenes que pueda utilizar directamente. Tendrá que modificar las imágenes usted mismo en un programa de gráficos o solicitar la ayuda de un profesional de gráficos para modificar una imagen DALL-E o utilizar una imagen generada como prototipo para el diseño final.

#### ACCEDIENDO A DALL-E

Tienes dos formas de acceder a DALL-E:

* **Aplicación OpenAI DALL-E**: esta aplicación le brinda acceso directo a DALL-E a través de su cuenta OpenAI. Hay un par de formas de acceder a la aplicación (que se muestran en la figura 5.4):

   * Vaya a https://openai.com, haga clic en Menu, haga clic en Log In y, a continuación, inicie sesión en su cuenta de OpenAI. En la selección de herramientas de OpenAI que aparecen, haga clic en DALL-E.

   * Vaya a https://openai.com/dall-e-2, haga clic en Try DALL-E y luego inicie sesión en su cuenta OpenAI.

<img width="832" alt="image" src="https://github.com/user-attachments/assets/bbe229ea-2d8b-4acb-a3fa-f917318752e8" />

**Figura 5.4 La aplicación OpenAI DALL-E**

* ***Copilot Image Creator***: con Microsoft Edge, vaya a https://www.bing.com/images/create (consulte la figura 5.5) o https://copilot.microsoft.com/images/create; o, en Copilot, dirija su mensaje a Image Creator (por ejemplo, `Ask Image Creator for an image of a dog running on the moon`).

<img width="910" alt="image" src="https://github.com/user-attachments/assets/50486ab4-80f6-4778-a521-6a7b20f1e4a2" />

**Figura 5.5 Creador de imágenes de Copilot**

**Nota**: El uso de DALL-E a través de la aplicación Open AI no es gratuito. Para usarlo, debe comprar créditos, donde un crédito es válido para una sola solicitud de DALL-E. Mientras escribo esto, puede comprar **115 créditos por USD 15** a través de su cuenta OpenAI. Tenga en cuenta que ***el uso de DALL-E a través de Microsoft Copilot es gratuito***.

#### PROMPTING DALL-E

Conseguir que DALL-E produzca imágenes satisfactorias es un arte en sí mismo. El mayor error que cometen los novatos de DALL-E es tratar la aplicación como un chatbot y darle instrucciones sobre lo que quieres que haga. En lugar de eso, suponen que tu imagen ya existe y que lo que estás escribiendo es una descripción detallada para una persona ciega o con alguna otra discapacidad visual que le impide ver la imagen.

En la descripción, incluya no solo los elementos que desea ver en la imagen, sino también una o más palabras clave (cuanto más, mejor) que especifiquen el estilo exacto de la imagen. A continuación, se ofrecen algunas ideas:

* ***The mood - El estado de ánimo***: utilice palabras clave que evoquen un estado de ánimo positivo ( *brillante, ligero, vibrante, pacífico - bright, light, vibrant, peaceful* ) o un estado de ánimo negativo ( *sombrío, oscuro, apagado, melancólico, tormentoso - gloomy, dark, muted, melancholic, stormy*).

* ***The overall aesthetic - La estética general***: por ejemplo, *gótico, steampunk, ciberpunk, postapocalíptico, afrofuturismo - Gothic, steampunk, cyberpunk, post-apocalyptic, Afro-futurism*.

* ***The medium - El medio***: Por ejemplo, *fotografía, ilustración, pintura, caricatura - photograph, illustration, painting, cartoon*.

* ***Las particularidades del medio - The specifics of the medium***: Algunos ejemplos:

   * ***Photograph - Fotografía***: Tipo de película ( *color, blanco y negro - color, black and white* ), contexto( *interior, exterior - indoors, outdoors* ), iluminación, ángulo ( *largo , medio , primer plano - long, medium, close-up* ), profundidad de campo ( *superficial, profunda - shallow, deep* ).

   * ***Illustration - Ilustración***: Medio ( *lápiz, tinta, carboncillo, plantilla, crayón, etc. - pencil, ink, charcoal, stencil, crayon, and so on*) y estilo ( *arte digital, collage, anime, Art Deco, Bauhaus, etc. - digital art, collage, anime, Art Deco, Bauhaus, and so on*).

   * ***Painting - Pintura***: Medio ( *acuarela, óleo, etc. - watercolor, oil, and so on*) y estilo ( *impresionista, manierista, simbolista, Art Nouveau, etc. - Impressionist, Mannerist, Symbolist, Art Nouveau, and so on*).

**Nota**: La última versión de DALL-E (DALL-E 3) debería estar disponible para el público en general cuando lea esto. Es una buena noticia porque, a diferencia de las versiones anteriores de DALL-E, esta última versión es mucho mejor en la representación de texto. Si su imagen requiere texto, inclúyalo en su descripción. Sin embargo, verifique cuidadosamente el texto de la imagen resultante porque DALL-E 3 a menudo omite una letra o agrega una letra adicional.

Para que te hagas una idea de cómo funciona la estimulación DALL-E, te resultará útil ver algunos ejemplos. Para mi página de diario en línea, inscribí a Copilot de la siguiente manera:

```text
Please ask image creator to create a cartoon of a cow standing on two legs with a text bubble over the cow's head that says "Moo".
```

```text
Pídale al creador de la imagen que cree una caricatura de una vaca parada sobre dos patas con una burbuja de texto sobre la cabeza de la vaca que diga "Muu".
```

La figura 5.6 muestra las imágenes que recibí. ¡La que está en la parte superior izquierda es bastante buena!

<img width="707" alt="image" src="https://github.com/user-attachments/assets/f7f87a5a-bcf1-4641-bf70-08f0517e32d5" />

**Figura 5.6 Dibujos animados generados por Image Creator basados ​​en mi mensaje**

A continuación se muestra un ejemplo de prompt para una fotografía que incluye las palabras clave `medium shot` y `fluorescent lighting`:

```text
A photograph of a golden retriever browsing in a library, medium shot, fluorescent lighting.
```

```text
Una fotografía de un golden retriever curioseando en una biblioteca, plano medio, iluminación fluorescente.
```

La figura 5.7 muestra una imagen que DALL-E generó a partir de este mensaje.

<img width="912" alt="image" src="https://github.com/user-attachments/assets/82793d94-e5d0-41ca-8f70-7ef190757518" />

**Figura 5.7 Una imagen fotográfica generada por DALL-E**

A continuación se muestra una sugerencia para una ilustración de arte digital que utiliza las palabras clave `post-apocalyptic` y `desolate`:

```text
A digital art illustration of an old-fashioned diner in a post-apocalyptic, desolate street scene.
```

```text
Una ilustración de arte digital de un restaurante antiguo en una escena callejera desolada y postapocalíptica.
```

La figura 5.8 muestra un ejemplo de imagen DALL-E generada a partir de este mensaje.

<img width="924" alt="image" src="https://github.com/user-attachments/assets/e87a280c-d993-4714-9675-98e0914cb5c8" />

**Figura 5.8 Una ilustración generada por DALL-E**

A continuación se muestra un mensaje para una página de manuscrito iluminado que utiliza las palabras clave `bright` y `lavish`:

```text
A bright, lavish, illuminated manuscript page that includes "Lorem ipsum" text and drawings of cats in the margins.
```

```text
Una página manuscrita brillante, lujosa e iluminada que incluye texto "Lorem ipsum" y dibujos de gatos en los márgenes.
```

La figura 5.9 muestra una imagen que DALL-E creó a partir de este mensaje.

<img width="926" alt="image" src="https://github.com/user-attachments/assets/a18fe1f3-4666-43cb-975f-654c26c14318" />

**Figura 5.9 Una página de manuscrito iluminado generado por DALL-E con gatos**

Si DALL-E genera una imagen que desea utilizar (ya sea para editarla o para que sirva como prototipo), el siguiente paso es guardar esa imagen en su computadora.

#### GUARDAR UNA IMAGEN GENERADA

Una vez que tenga una imagen que desee utilizar en su página web, deberá guardar la imagen en su computadora:

* ***OpenAI DALL-E app***: Haga clic en la imagen, haga clic en el botón de tres puntos (...) que aparece en la esquina superior derecha de la imagen y luego haga clic en Download.

* ***Copilot Image Creator***: Haga clic en la imagen y luego en Download.

De cualquier manera, la imagen se almacena en la carpeta Downloads de tu computadora. 
Mueve el archivo de imagen a la misma carpeta que contiene tus archivos HTML y CSS (que crearás en la siguiente sección) y luego cambia el nombre de la imagen por el nombre de archivo que prefieras.

Ahora que sabe cómo hacer que ChatGPT lo ayude a escribir y editar texto y generar imágenes, está listo para crear el prompt que genera el código de la página web para un diario en línea.

### 5.2.3 Elaboración del prompt

El proyecto de este capítulo es una página de diario en línea. Antes de continuar, debe tener a mano lo siguiente:

* Un logotipo, un título y un eslogan para la página.

* Los nombres de los tipos de letra que desea utilizar para los encabezados de página y el texto de la página.

* Los nombres de los colores que desea aplicar a los fondos y al texto de la página.

Consulta el capítulo 3 para obtener más información sobre estos elementos de diseño y cómo solicitar a ChatGPT sugerencias de título, tipo de letra y color.

Incluso si no tienes nada escrito para publicar, puedes seguir el proceso de solicitar a ChatGPT el código HTML y CSS de tu diario en línea, ya que el código incluirá marcadores de posición para tu texto. Debes hacerle saber a ChatGPT de inmediato que quieres que te ayude a crear una página web y que no sabes cómo codificar, por lo que tendrá que generar el código por ti. Todo esto se hace iniciando tu solicitud de la siguiente manera:

```text
I want to build a web page for an online journal. I don't know how to code, so I need you to provide the code for me.
  
First, write the HTML code for a web page that includes the following:
```

```text
Quiero crear una página web para una revista en línea. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
```

A continuación, especifique el contenido de su página, incluido lo siguiente (consulte la figura 5.10):

* Un header que incluye su logotipo, título de página y eslogan.

* Un elemento main donde cada entrada es un accordion que utiliza HTML elementos `summary` y `details`.

* Para cada entrada, el texto `summary` ves el título de la entrada y el elemento `details` incluye la fecha de entrada seguida del texto de la entrada.

* Un footer que incluye un aviso de derechos de autor.

<img width="863" alt="image" src="https://github.com/user-attachments/assets/bbef970a-551c-41bc-87e3-c2ee998bd2cf" />

**Figura 5.10 Las secciones de la página del diario en línea**

A continuación, le pides a ChatGPT que genere el CSS según el formato que deseas para tu página:

```text
Second, in a separate file please write the CSS code for the following:
```

```text
En segundo lugar, en un archivo separado, escriba el código CSS para lo siguiente:
```

A continuación, especifique el formato, incluido lo siguiente:

* El color de fondo(background) de la página y el color del texto.

* Los tamaños de fuente que desea utilizar para el título y el eslogan de la página.

* El tamaño de letra de los elementos `summary`.

* Las fuentes a utilizar para los headings, resúmenes y texto de página normal.

* Un ancho máximo para la página. Esto evita que las líneas de texto sean demasiado largas. Una longitud máxima de 850px es adecuada para la mayoría de las páginas.

A continuación se muestra un ejemplo de solicitud para mi propia página de diario en línea:

```text
I want to build a web page for an online journal. I don't know how to code, so I need you to provide the code for me.
  
First, write the HTML code for a web page that includes the following:
 * A header element that includes an image named logo.png, the title "The Moo Point", and the tagline "It's like a cow's opinion, you know, it just doesn't matter. It's moo."
 * A main section where each entry is an accordion using the HTML summary and details elements.
 * For each entry, the summary text is the entry title and the details include the entry date, followed by the entry text.
 * Please provide four sample entries going back four days from today.
 * A footer element that includes the Copyright symbol, followed by the current year, followed by "Paul McFedries".
 * In the page head section, include the tag <meta charset="utf-8">.
  
Second, in a separate file write the CSS code for the following:
 * The page background color is mintcream.
 * The page text color is slategray.
 * Make the image a maximum width of 150px and floated to the left.
 * The title font size is 48px.
 * The tagline font size is 22px and formatted as italic.
 * The summary font size is 30px.
 * The main section font size is 20px with a top margin of 48px.
 * Make the date of each entry dark blue with font size 18px.
 * For the headings and summary text, use the Lato font from Google Fonts. For the rest of the text, use the Merriweather font from Google Fonts.
 * The footer has 5px padding all around and a 10px top margin.
 * Make the page responsive with a maximum width of 850px.
 * Style the accordions to make them look nicer, including a powderblue background color.
```

```text
Quiero crear una página web para una revista en línea. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
 * Un elemento de encabezado que incluye una imagen llamada logo.png, el título "The Moo Point" y el eslogan "Es como la opinión de una vaca, ya sabes, simplemente no importa. Es muuuuu".
 * Una sección principal donde cada entrada es un acordeón que utiliza los elementos de resumen y detalles HTML.
 * Para cada entrada, el texto del resumen es el título de la entrada y los detalles incluyen la fecha de la entrada, seguida del texto de la entrada.
 * Proporcione cuatro entradas de muestra que se remonten a cuatro días a partir de hoy.
 * Un elemento de pie de página que incluye el símbolo de Copyright, seguido del año actual, seguido de "Paul McFedries".
 * En la sección del encabezado de la página, incluya la etiqueta <meta charset="utf-8">.
  
En segundo lugar, en un archivo separado escriba el código CSS para lo siguiente:
 *El color de fondo de la página es crema menta.
 *El color del texto de la página es gris pizarra.
 * Hacer que la imagen tenga un ancho máximo de 150px y flote hacia la izquierda.
 *El tamaño de fuente del título es 48px.
 * El tamaño de fuente del lema es 22px y está formateado en cursiva.
 *El tamaño de fuente del resumen es 30px.
 * El tamaño de fuente de la sección principal es de 20 px con un margen superior de 48 px.
 * Hacer que la fecha de cada entrada sea de color azul oscuro con un tamaño de fuente de 18px.
 * Para los títulos y el texto del resumen, utilice la fuente Lato de Google Fonts. Para el resto del texto, utilice la fuente Merriweather de Google Fonts.
 * El pie de página tiene un relleno de 5 px alrededor y un margen superior de 10 px.
 * Hacer que la página sea responsiva con un ancho máximo de 850px.
 * Dale estilo a los acordeones para que se vean mejor, incluyendo un color de fondo azul pálido.
```

ChatGPT debe crear primero el código HTML, que puedes copiar y pegar y guardar en un archivo llamado `index.html`. En ese código, deberías ver una línea cerca de la parte superior similar a la siguiente:

```html
<link rel="stylesheet" type="text/css" href="styles.css">
```

Este código le indica al navegador web que busque el código CSS en un archivo llamado `styles.css`, por lo que tu próxima tarea es copiar el código CSS generado, pegarlo en un archivo y guardarlo como `styles.css` (o cualquier nombre que veas en el tag `<link>`). Asegúrate de guardar `styles.css` en la misma carpeta que tu archivo `index.html`. También debes copiar tu archivo de imagen en la misma carpeta. Consulta el apéndice A para obtener más información sobre cómo trabajar con archivos de páginas web.

Envié este mensaje a GPT-4 mediante la aplicación ChatGPT de OpenAI. El código generado generó la página que se muestra en la figura 5.11.

<img width="683" alt="image" src="https://github.com/user-attachments/assets/729ad066-81e2-444b-96b1-8fd1fffad709" />

**Figura 5.11 Mi página de diario en línea generada por ChatGPT**

**Nota**: Para obtener la página que se muestra en la figura 5.11, tuve que corregir un error que cometió ChatGPT en el código CSS. Hablo de este error en la siguiente sección.

Si le gusta el diario en línea que ChatGPT creó para usted, puede omitir el resto de este capítulo e implementar el código como describo en el apéndice B. Sin embargo, si desea saber más sobre el código que ChatGPT generó, la siguiente sección le brinda una mirada más cercana.

## 5.3 Examinando el código

Si tiene curiosidad sobre el código que genera ChatGPT, en esta sección le brindaré una descripción general breve y no demasiado técnica del código de diario en línea que resultó de mi prompt de la sección anterior (esa página de diario se muestra en la figura 5.11). Su código generado por ChatGPT será diferente al mío no solo porque su texto e imágenes serán diferentes, sino también porque:

* Los algoritmos de ChatGPT incluyen cierta aleatoriedad incorporada, por lo que el mismo mensaje a menudo generará un código ligeramente diferente cada vez que lo ejecutes.

* El resultado de ChatGPT varía según el modelo (GPT-3.5 frente a GPT-4) y la aplicación (OpenAI frente a Copilot). En el caso de Copilot, el resultado también depende del estilo de conversación (creative, balanced, o precise).

**Nota**: El código HTML y CSS generado para mi página de diario en línea están disponibles en el sitio web de este libro ( www.manning.com/books/build-a-website-with-chatgpt ) y en el repositorio de GitHub del libro: https://github.com/paulmcfe/websites-with-chatgpt .

Sin embargo, cada versión de ChatGPT debería generar código HTML y CSS que sea al menos similar a lo que se muestra en las siguientes dos secciones, por lo que mis anotaciones de código deberían ayudarlo a comprender lo que sucede bajo el capó.

### 5.3.1 Examinar el HTML

El código HTML que ChatGPT generó para mi página de diario en línea se muestra aquí:

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">                                   ①
        <title>The Moo Point</title>
        <link rel="stylesheet" 
              href="styles.css">                                 ②
        <link rel="preconnect" 
              href="https://fonts.googleapis.com">               ③
        <link rel="preconnect"                                   ③
              href=https://fonts.gstatic.com                     ③
              crossorigin>                                       ③
        <link href="https://fonts.googleapis.com/css2?           ③
        family=Lato:wght@400;700&family=Merriweather:            ③
        ital,wght@0,400;0,700;1,400&                             ③
        display=swap" rel="stylesheet">                          ③
    </head>
    <body>
        <header>                                                 ⑦
            <img src="logo.png" alt="Logo">                      ④⑤
            <h1 class="title">The Moo Point</h1>                 ⑤⑦
            <p class="tagline">                                  ⑥⑦
                It's like a cow's opinion, you know, it          ⑦
                just doesn't matter. It's moo.                   ⑦
            </p>                                                 ⑥⑦
        </header>                                                ⑦
        
        <main>
            <details>                                            ⑪
                <summary class="entry-title">                    ⑧⑪
                    Title of Entry 1                             ⑪
                </summary>                                       ⑧⑪
                <p class="entry-date">24 July 2023</p>           ⑨⑪
                <p class="entry-text">Entry text goes here.</p>  ⑩⑪
            </details>                                           ⑪
  
            <details>
                <summary class="entry-title">Title of Entry 2</summary>
                <p class="entry-date">25 July 2023</p>
                <p class="entry-text">Entry text goes here.</p>
            </details>
  
            <details>
                <summary class="entry-title">Title of Entry 3</summary>
                <p class="entry-date">26 July 2023</p>
                <p class="entry-text">Entry text goes here.</p>
            </details>
  
            <details>
                <summary class="entry-title">Title of Entry 4</summary>
                <p class="entry-date">27 July 2023</p>
                <p class="entry-text">Entry text goes here.</p>
            </details>
        </main>
  
        <footer>                                                 ⑫
            <p>&copy; 2023 Paul McFedries</p>                    ⑫
        </footer>                                                ⑫
    </body>
</html>
```

① Especifica el conjunto de caracteres de la página

② Le dice al navegador web dónde encontrar el código CSS

③ Carga las fuentes de la página desde Google Fonts

④ Logotipo de la página

⑤ Título de la página

⑥ Lema de la página

⑦ Encabezado de página

⑧ Resumen de la entrada (título)

⑨ Fecha de entrada

⑩ Texto de entrada

⑪ Elemento de detalles

⑫ Pie de página

A continuación se muestran algunas notas a tener en cuenta al leer el código HTML:

* El código `<meta charset="utf-8">` que aparece inmediatamente después de la etiqueta `<head>` en el archivo HTML le indica al navegador el conjunto de caracteres que se utiliza en la página. No es necesario que sepas qué significa esto, solo que esta etiqueta es necesaria para que el símbolo de copyright se muestre correctamente. También ayudará a que caracteres como los guiones largos (`—`) y las comillas tipográficas (`“` y `”`) se muestren correctamente si utilizas esos y otros caracteres similares en las entradas de tu diario.

* Este código utiliza texto de marcador de posición(placeholder) para las entradas, por lo que deberá agregar su propio título, fecha y texto para cada entrada.

* Si el lema de la página te suena familiar, es una línea tomada del personaje Joey del antiguo programa de televisión *Friends*.

Por último, tenga en cuenta que el código HTML incluye la siguiente línea:

```html
<link rel="stylesheet" href="styles.css">
```

Esta etiqueta le dice al navegador web dónde encontrar el código CSS, que describo en la siguiente sección.

### 5.3.2 Examinando el CSS

El código CSS generado por ChatGPT para mi página de diario en línea se muestra aquí:

```css
body {
    background-color: mintcream;               ①
    color: slategray;                          ①
    font-family: 'Merriweather', serif;        ①
    max-width: 850px;                          ②
    margin: 0 auto;                            ③
}
img {
    max-width: 150px;                          ④
    float: left;                               ④
}
h1 {
    font-size: 48px;                           ⑤
    font-family: 'Lato', sans-serif;           ⑤
}
p.tagline {
    font-size: 22px;                           ⑥
    font-style: italic;                        ⑥
}
main {
    margin-top: 48px;
}
.summary, .entry-title {
    font-size: 30px;                           ⑦
    font-family: 'Lato', sans-serif;           ⑦
}
.date {
    color: darkblue;                           ⑧
    font-size: 18px;                           ⑧
}
footer {
    padding: 5px;
    margin-top: 10px;
}
details {                                      ⑨
    background: powderblue;
    margin: 5px 0;
    border: 1px solid #aaa;
    border-radius: 4px;
    padding: .625em .625em .625em .625em;
    width: 100%;
}
summary {
    font-weight: bold;
    margin: -.625em -.625em 0;
    padding: .625em;
}
details[open] {
    padding: .625em;
    border: 1px solid #aaa;
}
details[open] summary {
    border-bottom: 1px solid #aaa;
    margin-bottom: .625em;
}    #I
```

① Establece el color de fondo de la página, el color del texto y la fuente.

② Establece el ancho máximo de página en 850 px

③ Centra la página

④ Establece un ancho máximo para el logotipo y lo desplaza hacia la izquierda.

⑤ Establece el tamaño de fuente del título de la página a 48 px y aplica la fuente Lato

⑥ Aplica estilo al eslogan con un tamaño de fuente de 22 px y cursiva.

⑦ Aplica estilo a los títulos de las entradas con un tamaño de fuente de 30 px y la fuente Lato

⑧ Aplica estilo a la fecha de entrada con color azul oscuro y tamaño de fuente 18 px

⑨ Aplica estilos especiales a los acordeones.

Afortunadamente, ChatGPT rara vez comete errores al generar código HTML y CSS, pero en este caso sí lo hizo. Para ver el error, primero vuelva a mirar la siguiente línea del código HTML (hay líneas similares para cada entrada):

```html
<p class="entry-date">24 July 2023</p>
```

En esta etiqueta `<p>`, el atributo `class` hace referencia a un conjunto de estilos CSS aplicados al párrafo. En este ejemplo, el nombre de la clase es `entry-date`. En el código CSS, los estilos de clase se designan añadiendo un punto (`.`) antes del nombre de la clase. Sin embargo, puedes buscar en el código CSS todo el día y no encontrarás ninguna regla CSS que comience con `.entry-date`. La más cercana es `.date`, lo que significa que ChatGPT cometió un error. (¿Cómo lo sabrías? En este caso, lo sabrías mirando la página y notando que las fechas de entrada no están formateadas con el color `darkblue` especificado en el prompt). En el CSS, solucionas el problema cambiando `.date` a `.entry-date`.

Si lo desea, puede utilizar las anotaciones anteriores en esta sección para modificar el código de su página web, como describo a continuación.

## 5.4 Personalización de la página

Si no está satisfecho con la página que ChatGPT generó para usted, una posible solución es modificar el prompt y volver a enviarlo. Sin embargo, para personalizaciones relativamente pequeñas, suele ser más fácil editar el código manualmente.

Primero, aquí hay algunas sugerencias de personalización para el código HTML:

* En el header, puedes editar el título o el eslogan. Solo asegúrate de no editar ni eliminar las etiquetas HTML asociadas: `<h1>` y `</h1>` para el título, y `<p>` y `</p>` para el eslogan.

* Para agregar una nueva entrada (es decir, un nuevo acordeón), siga estos pasos:

   a) Abra el archivo HTML en un editor de texto.

   b) Seleccione una entrada existente. Es decir, seleccione todo lo que esté entre un único par de tags: `<details>` y `</details>`, tal como se muestra en la figura 5.12.

<img width="930" alt="image" src="https://github.com/user-attachments/assets/ca60c57e-9f3b-4016-800b-34a73215388c" />

**Figura 5.12 Seleccionar una entrada de acordeón existente.**

   c) Copie la entrada (por ejemplo, presionando Ctrl-C o Cmd-C).

   d) Cree una nueva línea en el punto donde desea que aparezca la nueva entrada. Por ejemplo, si desea que la nueva entrada aparezca encima de las entradas existentes, coloque el cursor inmediatamente antes de la primera etiqueta `<details>` y luego presione Enter o Return.

   e) Coloque el cursor en la nueva línea que acaba de crear, como se muestra en la figura 5.13.

<img width="786" alt="image" src="https://github.com/user-attachments/assets/8fced6e6-a1b7-493c-ba2c-bd6b1795fdd8" />

**Figura 5.13 Coloque el cursor donde desea pegar el código que ha copiado.**

   f) Pegue el código copiado (por ejemplo, presionando Ctrl-C o Cmd-C).

   g) Editar el título, la fecha y el texto de la entrada.

Si el texto de su entrada incluye varios párrafos, puede asegurarse de que cada párrafo se muestre correctamente rodeándolo con una etiqueta `<p class="entry-text">` al principio y otra al final `</p>`:

```html
<main>
    <details>
        <summary class="entry-title">Title of Entry 1</summary>
        <p class="entry-date">24 July 2023</p>
        <p class="entry-text">Entry text goes here.</p>
        <p class="entry-text">Another paragraph goes here.</p>
        <p class="entry-text">You can keep going if you want.</p>
    </details> 
```

* En la sección de footer del código HTML, puedes agregar links a tus cuentas de redes sociales, como describo en el capítulo 4.

A continuación se muestran algunas ideas de personalización para el código CSS:

* Para dar formato al texto de cada entrada, agréguelo `.entry-text { }` al final del código CSS y complételo con el formato que desee. Por ejemplo, el siguiente código ajusta el tamaño de fuente de la entrada:

```css
.entry-text {
    font-size: 20px;
}
```

* Si desea que su página tenga un ancho máximo diferente, cambie el valor `max-width` a algo distinto de 850px.

* Para cualquier valor de color, puede cambiar el color existente a una palabra clave de color diferente.

* Para cualquier valor de tamaño de fuente, puede cambiar el número para aumentar o disminuir el tamaño de la fuente. Solo asegúrese de dejar la unidad `px` en su lugar.

* Para cualquier valor de margen o padding, puede cambiar el número para aumentar o disminuir el padding o los márgenes. En este caso, asegúrese de dejar la unidad `px` en su lugar.

* Para que el código de tu página sea más accesible, considera convertir todas las medidas en px a medidas en rem. 1 rem equivale de manera predeterminada a 16 px, por lo que 20 px son 1,25 rem, 24 px son 1,5 rem, 32 px son 2 rem, 48 px son 3 rem, y así sucesivamente. La unidad rem es más accesible porque mide los tamaños de fuente en relación con el tamaño de fuente predeterminado que el usuario del navegador ha definido en la configuración de su navegador.

## Resumen

* Un accordion es una característica HTML especial que consta de un summary - resumen (el título o la descripción del acordeón) y details - detalles (la totalidad del contenido del acordeón).

* Al hacer clic en el resumen del acordeón, el contenido completo del acordeón alterna entre oculto y visible.

* Para que la IA genere una imagen a partir de un mensaje de texto, utilice la aplicación DALL-E de OpenAI o el Creador de imágenes de Copilot.

* Al solicitar una imagen, utilice palabras clave para evocar el estado de ánimo y la estética general, el medio y las características específicas del medio.

* Para obtener mejores resultados, el mensaje de su página debe ser lo más específico posible, incluidos colores, tamaños de fuente y niveles de encabezado.

* Guarde el HTML generado en el archivo `index.html` y el CSS generado en el nombre de archivo sugerido por ChatGPT en el código HTML, generalmente `styles.css`.
