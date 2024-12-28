# 4 Cómo añadir estructura a una página

Este capítulo cubre:

* El papel del header y footer - encabezado y pie de página
* Insertar una imagen en una página web
* Agregar links - enlaces a sitios de redes sociales
* Prompting ChatGPT para crear una página de club de lectura
* Examinar y personalizar el código de la página web ChatGPT

En el capítulo 3, aprendiste a usar ChatGPT para crear una personal home page. Una de las principales conclusiones de ese proceso es que cuanto más específico sea el prompt, más reflejará el código resultante tus requisitos y más se acercará la página resultante a tu visión original.

Dos aspectos que pueden haberle sorprendido sobre el proceso del capítulo 3 fueron la longitud del prompt final y la cantidad de detalles que contenía. Sin embargo, los prompt largos y detallados son la única forma de garantizar que ChatGPT genere código que cumpla con sus objetivos de diseño. En este capítulo, proporcionará a ChatGPT un poco más de detalle agregando un par de elementos estructurales (el encabezado y el pie de página - page header and the page footer) que son comunes a casi todas las páginas web. También aprenderá a incluir un par de elementos de contenido útiles: una o más imágenes y uno o más links-enlaces a redes sociales. Toda esta información luego se incluye en un prompt detallado que le pasará a ChatGPT para producir el código para una página de club de lectura que le brinde a usted y a otros miembros del club un hogar en la web.

Este capítulo también ofrece una explicación detallada del código generado por ChatGPT. Incluso ofrece algunos consejos para personalizar el código manualmente y lograr que todo funcione exactamente como lo desea.

## 4.1 Comprender el proyecto de este capítulo

En este capítulo, utilizará ChatGPT para crear una página web sencilla para un club de lectura. La página resultante incluirá los siguientes componentes:

* Un elemento header que incluye lo siguiente:
   * El logotipo del club de lectura
   * El nombre del club de lectura
   * Un eslogan que describa o resuma de alguna manera el club.
* Un elemento principal que incluye lo siguiente:
   * Una sección introductoria que describe el club de lectura.
   * Una sección "What We’re Reading - Lo que estamos leyendo" que muestra información sobre la selección actual del club de lectura, incluida la portada, el título y el resumen.
   * Una sección de “Next Meetup - Próxima reunión” que muestra información sobre la próxima reunión del club, incluida la fecha, la hora, la ubicación y algunas preguntas relacionadas con los libros para considerar.

* Un elemento footer que incluye lo siguiente:
   * Un aviso de derechos de autor
   * Enlaces a las cuentas de redes sociales del club

La figura 4.1 muestra un ejemplo del tipo de página que creará con la ayuda de ChatGPT.

Para tu propia página, es posible que quieras hablar sobre el diseño de la página con los miembros de tu grupo para ver si falta algún contenido. También puedes modificar esta página ligeramente para convertirla en la página de inicio de un grupo de lectura, un grupo de debate, una sociedad literaria o cualquier tipo de reunión.

<img width="577" alt="image" src="https://github.com/user-attachments/assets/ac6ab4fd-3cc1-49f1-870e-f2869513ea76" />

**Figura 4.1 Una página de club de lectura creada con código generado por ChatGPT**

## 4.2 Creación de la página del club de lectura

El objetivo de este capítulo es utilizar la ayuda de ChatGPT para construir una página de club de lectura sencilla que muestre los siguientes elementos fundamentales de una página web: header, footer e images - el encabezado, el pie de página y las imágenes. También aprenderá a agregar links a una o más cuentas de redes sociales. Al final de esta sección, reunirá todo esto en un prompt completo para construir la página del club de lectura.

### 4.2.1 Presentación del header - encabezado de página

El encabezado de página es una sección que aparece en la parte superior de la página. En casi todos los casos, el encabezado se extiende por todo el ancho de la página. Sin embargo, vale la pena señalar aquí que esto no significa que el encabezado se extenderá necesariamente por todo el ancho de la ventana del navegador. ¿Por qué? Porque, como verá en el proyecto de este capítulo y en la mayoría de las páginas de ejemplo de este libro, generalmente es mejor restringir el ancho de la página web para que las líneas de texto no se vuelvan demasiado anchas y, por lo tanto, demasiado difíciles de leer.

El encabezado actúa como una especie de introducción a la página, lo que significa que generalmente incluye uno o más de los siguientes elementos:

* El icono o logotipo de la página
* El título de la página y un eslogan o subtítulo opcional
* Enlaces a cuentas de redes sociales

Es común (aunque de ningún modo necesario) diferenciar el header del resto de la página al diseñarlo con un background color diferente.

Al solicitar ChatGPT(prompting ChatGPT), puede especificar un header y su contenido incluyendo una instrucción con el siguiente formato:

```text
Add a header element that includes an image named logo.png, the title "Code & Prose", and the tagline "Diving deep into the narrative side of code".
```

```text
Agregue un elemento de encabezado que incluya una imagen llamada logo.png, el título "Código y prosa" y el lema "Sumergiéndonos profundamente en el lado narrativo del código".
```

**Nota**: Todas las indicaciones de este capítulo están disponibles en el sitio web de este libro ( www.manning.com/books/build-a-website-with-chatgpt ) y en el repositorio de GitHub del libro ( https://github.com/paulmcfe/websites-with-chatgpt ).

A continuación se muestra un ejemplo de código HTML que ChatGPT podría generar según esta instrucción:

```html
<header>
    <img src="logo.png" alt="Code & Prose logo">
    <h1>Code & Prose</h1>
    <p>Diving deep into the narrative side of code</p>
</header>
```

Tenga en cuenta que el encabezado está marcado con el elemento header, lo que significa que el contenido del encabezado aparece entre las etiquetas `<header>` y `</header>`, como se muestra en este ejemplo. (Hablaré de la etiqueta `<img>` un poco más adelante en este capítulo; para la etiqueta `<h1>`, consulte el capítulo 3; para la etiqueta `<p>`, consulte el capítulo 5). La Figura 4.2 muestra cómo puede aparecer este código después de que se le haya aplicado algo de CSS. La contraparte inferior de la página del encabezado es el pie de página, que analizo a continuación.

<img width="828" alt="image" src="https://github.com/user-attachments/assets/843f4148-959a-4632-9c69-b5e3f332be89" />

**Figura 4.2 Un encabezado de página**

### 4.2.2 Presentación del footer - pie de página

El footer es una sección que aparece en la parte inferior de la página. Al igual que el header, el pie de página casi siempre se extiende por todo el ancho de la página y la altura del footer depende de su contenido. Los footer suelen ser elementos bastante simples que incluyen uno o ambos de los siguientes elementos:

* Un aviso de derechos de autor
* Links a cuentas de redes sociales

Tenga en cuenta que, si bien es posible que los links a las redes sociales aparezcan tanto en el header como en el footer, no deberían aparecer en ambos. En el proyecto de este capítulo, los enlaces a las redes sociales aparecerán en el footer.

Nuevamente, es común distinguir el pie de página del resto de la página al diseñarlo con un color de fondo diferente. También es común llenar el footer con links a otras páginas principales del sitio, un tema que abordo en el capítulo 7.

Como parte del prompt de ChatGPT, puede especificar un footer y su contenido incluyendo una instrucción similar a la siguiente:

```text
Add a footer element that includes the text "Copyright" (spelled out, do not include the Copyright symbol), followed by the current year, followed by "Code & Prose".
```

```text
Agregue un elemento de pie de página que incluya el texto "Copyright" (escrito con todas las letras, no incluya el símbolo de Copyright), seguido del año actual, seguido de "Código y prosa".
```

ChatGPT podría generar el siguiente código basándose en esta instrucción:

```html
<footer>
    <p>
        Copyright 2023 Code & Prose
    </p>
</footer>
```

Tenga en cuenta que el pie de página está marcado con el elemento `footer`, lo que significa que el contenido del pie de página aparece entre las etiquetas `<footer>` y `</footer>`, como se muestra en este ejemplo. La Figura 4.3 demuestra cómo el navegador muestra este código después de aplicar algunos CSS. A continuación, aprenderá un aspecto vital de los elementos que ve en una página web: el box model.


<img width="1153" alt="image" src="https://github.com/user-attachments/assets/63fb42bb-a81c-4f2c-a59a-b3f7413add6e" />

**Figura 4.3 Pie de página**

### 4.2.3 Introducción padding, borders y margins

Un concepto HTML importante que hay que tener en cuenta es que cada elemento de la página está rodeado por un recuadro(box) invisible. ¿Por qué es tan importante? Porque puedes hacer que ChatGPT genere código para controlar muchos aspectos de ese recuadro(box), incluido el espaciado interior, los bordes y el espaciado exterior. Para lograrlo, debes familiarizarte con las distintas partes del box.

La figura 4.4 ofrece una visión abstracta de las partes básicas del cuadro, y la figura 4.5 muestra cómo estas mismas partes afectan el contenido real de una página. Hay cuatro partes para cada box:

* ***Content***: Esta área es el rectángulo interior del box y consiste en el contenido (como texto o imagen) incluido en el box.

* ***Padding***: Esta área entre el contenido y el borde representa un espacio en blanco adicional agregado fuera de los bordes superior, derecho, inferior e izquierdo(top, right, bottom, and left) del área de contenido.

* ***Border***: Esta parte corre a lo largo de los bordes exteriores del área padding y rodea el contenido y el padding con líneas.

* ***Margin***: Esta área es el rectángulo exterior del box, que representa el espacio en blanco adicional agregado fuera de los bordes superior, derecho, inferior e izquierdo(top, right, bottom, and left).

<img width="809" alt="image" src="https://github.com/user-attachments/assets/a101c40b-7a71-4baf-a350-18723b4f278f" />

**Figura 4.4 Las partes principales de un elemento box**

<img width="1050" alt="image" src="https://github.com/user-attachments/assets/7334d69d-1fe8-4f3e-97e7-ddc64a1839da" />

**Figura 4.5 Las partes del elemento box tal como aparecen con el contenido real de la página**

La combinación del área content, el padding, el border y el margin se conoce en los círculos CSS como el **box model - modelo de caja**. Teniendo todo esto en cuenta lo mejor que pueda, es hora de centrar su atención en las propiedades CSS útiles y potentes que le permiten manipular cualquier elemento box. En primer lugar, cambie el box padding.

#### AÑADIENDO PADDING

En el elemento box, el padding es el espacio en blanco que se agrega arriba, abajo, a la izquierda y a la derecha del contenido. Si agrega un borde a su elemento, como se describe en la siguiente sección, el padding es el espacio entre el contenido y el borde. El padding le da al elemento un poco de espacio para respirar en su cuadro, lo que garantiza que el contenido no esté abarrotado por su propio borde o por elementos cercanos.

Para configurar el padding, aplique un valor a uno o más de los cuatro lados:

```css
element {
    padding-top: top-value;
    padding-right: right-value;
    padding-bottom: bottom-value;
    padding-left: left-value;
}
```

Cada valor es una medida en píxeles (px). A continuación, se muestra un ejemplo:

```css
header {
    padding-top: 16px;
    padding-right: 24px;
    padding-bottom: 12px;
    padding-left: 20px;
}
```

También puede utilizar una propiedad `padding` abreviada para establecer todos los valores de padding con una única declaración. Puede duplicar la regla del ejemplo anterior utilizando la sintaxis abreviada de la siguiente manera:

```css
header {
    padding: 16px 24px 12px 20px;
}
```

Si proporciona un solo valor, el navegador web aplicará esa cantidad de padding a los cuatro lados.

Para solicitarle a ChatGPT que establezca el padding en un elemento, incluya una instrucción similar a la siguiente en la parte CSS de su prompt:

```text
Style the footer with 10px padding all around.
```

```text
Dale estilo al pie de página con un relleno de 10px alrededor.
```

Basándose en esta instrucción, ChatGPT generará un código como este:

```css
header {
    padding: 10px;
}
```

La siguiente parte del box model - modelo de caja es el border - borde.

#### RODEAR UN ELEMENTO CON UN BORDER

En el elemento box, el border es la línea que define el borde exterior del padding en los cuatro lados: superior, derecho, inferior e izquierdo(top, right, bottom, and left). De esta manera, el border se sitúa entre el padding del elemento y su margin. El borde es opcional, pero suele ser útil para proporcionar al lector un indicador visual de que el contenido incluido está separado de cualquier contenido cercano. Para crear un borde básico alrededor de un elemento, utilice la propiedad `border`, como se muestra en la figura 4.6.

<img width="624" alt="image" src="https://github.com/user-attachments/assets/e1440f1c-7dc8-4774-8d04-8b0012da2075" />

**Figura 4.6 La sintaxis de la propiedad `border`**

El valor `width` es una medida en `px`. También puedes establecer el valor en cualquiera de las siguientes palabras clave: `thin`, `medium` o `thick`. Para el valor `style`, puedes usar cualquiera de las siguientes palabras clave: `dotted`, `dashed`, `solid`, `double`, `groove`, `ridge`, `inset`, `outset`, `hidden` o `none`. Para el parámetro `color` puedes usar cualquiera de los nombres de colores que aprendiste en el capítulo 3.

Para solicitarle a ChatGPT que agregue un borde alrededor de un elemento, incluya una instrucción similar a la siguiente en la parte CSS de su prompt:

```text
Style the nav element with a 1px, solid, black border.
```

```text
Dale estilo al elemento de navegación con un borde negro sólido de 1 px.
```

Basándose en esta instrucción, ChatGPT generará un código como este:

```css
nav {
    border: 1px solid black;
}
```

El aspecto final del modelo de caja - box model que discutiré aquí es el margin - margen.

#### TRABAJAR CON MARGINS

En el elemento box, el margen es el espacio en blanco que se agrega arriba, abajo, a la izquierda y a la derecha del borde. El margen le permite controlar el espacio entre los elementos. ***Los valores de margen positivos, por ejemplo, evitan que los elementos de la página choquen entre sí o se superpongan y también evitan que los elementos rocen los bordes de la ventana gráfica del navegador***. Por otro lado, ***si su diseño requiere que los elementos se superpongan, puede lograr este efecto utilizando valores de margen negativos***.

El margen se aplica estableciendo un valor en uno o más de los cuatro lados de un elemento:

```css
element {
    margin-top: top-value;
    margin-right: right-value;
    margin-bottom: bottom-value;
    margin-left: left-value;
}
```

Cada valor de margen es una medida en píxeles. A continuación, se muestra un ejemplo:

```css
footer {
    margin-top: 24px;
    margin-right: 40px;
    margin-bottom: 32px;
    margin-left: 48px;
}
```

Al igual que con el padding, una propiedad abreviada de margen le permite aplicar los márgenes mediante una única declaración. Puede reescribir la regla del ejemplo anterior utilizando la sintaxis abreviada de la siguiente manera:

```css
footer {
    margin: 24px 40px 32px 48px;
}
```

Si proporciona un solo valor, el navegador web aplicará ese valor de margen a los cuatro lados del elemento.

Para solicitarle a ChatGPT que establezca el margen de un elemento, incluya una instrucción similar a la siguiente en la parte CSS de su solicitud:

```text
Style the body with 16px padding all around.
```

```text
Dale estilo al cuerpo con un relleno de 16px alrededor.
```

Basándose en esta instrucción, ChatGPT generará un código como este:

```css
body {
    padding: 16px;
}
```

Anteriormente, viste un ejemplo de un header que incluía una imagen. En la siguiente sección, se explica cómo trabajar con imágenes de páginas web.

### 4.2.4 Trabajar con imágenes

Aunque la mayoría de las páginas web transmiten información (por más vaga que sea la definición de ese término) mediante palabras, las páginas que no son más que texto resultan un poco intimidantes y, a menudo, ¡muy aburridas! Por supuesto, puedes (y debes) utilizar tipos de letra, colores y estilos de texto para embellecer la página (como describí en el capítulo 3). Sin embargo, una forma relativamente fácil de animar una pared de texto que de otro modo sería aburrida es ofrecer a tus lectores un atractivo visual insertando una o dos imágenes. Esto no quiere decir que las imágenes de tu página web deban ser meramente decorativas. Las imágenes son una excelente forma de complementar el texto de tu página, mostrar la información de forma concisa y ayudar a tus lectores a retener lo que leen en tus páginas.

Una imagen es un archivo independiente que puedes indicarle a ChatGPT que haga referencia en el código HTML de tu página. (Consulta el capítulo 10 para obtener un tratamiento más detallado de las imágenes y cómo se insertan en una página web). La web se ha estandarizado en cuatro formatos que representan casi todas las imágenes web, como se resume en la tabla 4.1.

En este capítulo, supongo que ya tienes las imágenes que quieres incluir en tu página. Para el proyecto del club de lectura, necesitas dos imágenes:

* Un logotipo para el club de lectura; esta imagen irá en el encabezado de la página.
* La portada del libro que el club está leyendo actualmente; esta imagen irá en la sección principal de la página.

Debes saber los nombres de todos los archivos de imagen que deseas incluir en tu página porque incluirás esos nombres en tu prompt.

**Tabla 4.1 Formatos de archivos de imagen**

<img width="663" alt="image" src="https://github.com/user-attachments/assets/14f3cc6a-5630-4875-845c-0d7928fc9641" />

<img width="664" alt="image" src="https://github.com/user-attachments/assets/9090c5c1-12d1-4ead-b2c0-7b7d3e954544" />

<img width="656" alt="image" src="https://github.com/user-attachments/assets/1aa2cc81-c322-4427-b7a7-49c338807b0b" />

<img width="663" alt="image" src="https://github.com/user-attachments/assets/96f32754-c3c4-4f88-9670-50dad15aa709" />

<img width="666" alt="image" src="https://github.com/user-attachments/assets/179881ca-3181-49f5-8d36-a23087dc4ae7" />

<img width="660" alt="image" src="https://github.com/user-attachments/assets/b024cabc-b068-4495-9edc-d08020afc06b" />

<img width="651" alt="image" src="https://github.com/user-attachments/assets/3a2a9378-5fe7-41be-8132-8d4ad7544533" />

<img width="663" alt="image" src="https://github.com/user-attachments/assets/a1c68045-d116-4ade-ae9c-f1858d1ac985" />

**Nota**: Uno de los aspectos más divertidos de trabajar con modelos de IA generativos es lograr que creen imágenes completamente nuevas a partir de indicaciones de texto. Hablo sobre la generación de nuevas imágenes a partir de texto utilizando el modelo DALL-E de OpenAI en el capítulo 5.

Es posible que también desees obtener íconos para cada cuenta de redes sociales asociada con tu club de lectura, lo cual se analiza a continuación.

### 4.2.5 Agregar links a redes sociales

En esta era moderna, ninguna página web parece completa sin al menos algunos enlaces a sitios de redes sociales. El proyecto de este capítulo supone que desea vincular cuentas en Facebook, X (Twitter) e Instagram. Para cada enlace, necesitará lo siguiente:

* El nombre de usuario de la cuenta
* Un icono para el sitio de redes sociales.

Para esto último, no es necesario descargar un archivo de imagen independiente de la web (a menos que prefieras hacerlo). En su lugar, deberás solicitarle a ChatGPT que te vincule con un conjunto de herramientas de íconos llamado Font Awesome, que incluye íconos para todos los sitios de redes sociales más importantes. (La única excepción, mientras escribo esto, es el sitio de redes sociales Threads, cuyo ícono aún no se había agregado a Font Awesome).

### 4.2.6 Elaboración del prompt

Si has seguido las indicaciones de ChatGPT en la sección anterior, ahora tienes lo que necesitas para que ChatGPT genere el código para la página de tu club de lectura. La indicación debería comenzar así:

```text
I want to build a web page for a book club. I don't know how to code, so I need you to provide the code for me.
  
First, write the HTML code for a web page that includes the following:
```

```text
Quiero crear una página web para un club de lectura. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
```

A continuación, especifique el contenido de su página, incluido lo siguiente (consulte la figura 4.7):

* Un header que incluye el logotipo de su club, el título de la página y el eslogan.
* Un elemento main que comienza con una sección que presenta a los visitantes a su club de lectura.
* Una sección que muestra información sobre el libro que el club está leyendo actualmente, incluida la portada, el título, el resumen y el número de páginas.
* Una sección que muestra información sobre la próxima reunión del club, incluida la fecha, la hora, la ubicación y algunas preguntas que los miembros deben considerar con anticipación.
* Un footer que incluye un aviso de derechos de autor y enlaces a las cuentas de sus redes sociales del club.

A continuación, le pides a ChatGPT que genere el CSS según el formato que deseas para tu página:


```text
Second, in a separate file please write the CSS code for the following:
```

```text
En segundo lugar, en un archivo separado, escriba el código CSS para lo siguiente:
```

A continuación, especifique el formato, incluido lo siguiente:

* El color de fondo del encabezado (debe ser el color principal de su esquema de colores).
* El tamaño de fuente y el color que desea utilizar para el título y el eslogan de la página (el color debe ser el más claro de su combinación de colores).
* El tamaño de fuente y el color de los títulos de segundo nivel (el color debe ser el color principal de su esquema de colores).
* El tamaño de fuente del texto de la página normal.
* Las fuentes a utilizar para los encabezados y el texto de la página normal.
* Un ancho máximo para la página. Esto evita que las líneas de texto sean demasiado largas. Una longitud máxima de 800px es adecuada para la mayoría de las páginas.

<img width="591" alt="image" src="https://github.com/user-attachments/assets/7b9a6ece-ac8b-4f1e-97fb-35f3a97bbbf6" />

**Figura 4.7 Las secciones de la página del club de lectura**

A continuación se muestra un ejemplo de prompt para mi propia página de club de lectura:

```text
I want to build a web page for a book club. I don't know how to code, so I need you to provide the code for me.
  
First, write the HTML code for a web page that includes the following:
 * A header element that includes an image named logo.png, the title "Code & Prose", and the tagline "Diving deep into the narrative side of code".
 * A main element that contains three sections.
 * The first section contains the second-level heading "Welcome!", followed by a paragraph that contains the text between the triple quotation marks: 
"""Welcome to Code & Prose, the only book club in the world that (we think) reads fiction related to web development.""".
 * A second section that begins with the second-level heading "What We're Reading".
 * In the second section, include the image named book-cover.png, followed by the text between the triple quotation marks, where each word or phrase before a colon is bold:
"""
Title: The Web Designer
Author: Paul McFedries
Pages: 1,576
Summary: At High Falutin High, [etc.]
"""
 * A third section that begins with the second-level heading "Next Meetup".
 * In the third section, include the text between the triple quotation marks, where each word or phrase before a colon is bold:
 """
 Date: August 23
 Time: 6:00pm
 Location: The Coder Cafe
 Questions to ponder: Can Daisy code, or what? Does the book contain too much HTML, or not enough? Why is it so hard for nerds to date?
 """
 * A footer element that includes the text "Copyright" (spelled out, do not include the Copyright symbol), followed by the current year, followed by "Code & Prose". In a separate paragraph, the footer also includes three links to social media accounts: one for Facebook (username: CodeAndProse), Instagram (username: codeandprose), and Twitter (username: codenprose).
  
Second, in a separate file write the CSS code for the following:
 * The header background color is darkorchid with 10px padding all around. Float the logo to the left and right-align the title and tagline.
 * The title font size is 48px with color lightsteelblue.
 * The tagline font size is 24px with color lightsteelblue and formatted as italic.
 * The second-level heading font size is 30px with color darkorchid and a top margin of 15px.
 * The main element font size is 20px.
 * In the second and third sections, the bold text should use the color mediumseagreen.
 * The image named book-cover.png should be floated to the right.
 * For the title and headings, use the Fira Sans Extra Condensed Bold font from Google Fonts. For the rest of the text, use the Source Code Pro font from Google Fonts.
 * The footer background color is darkorchid with 5px padding all around and a 10px top margin. The text color is lightsteelblue. Center the text and social media links.
 * For the social media links, use the corresponding Font Awesome icons.
 * The entire page is centered in the browser window.
 * The page is responsive with a maximum width of 800px.
```

```text
Quiero crear una página web para un club de lectura. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
 * Un elemento de encabezado que incluye una imagen llamada logo.png, el título "Código y prosa" y el lema "Sumergiéndonos profundamente en el lado narrativo del código".
 * Un elemento principal que contiene tres secciones.
 * La primera sección contiene el encabezado de segundo nivel "¡Bienvenido!", seguido de un párrafo que contiene el texto entre comillas triples:
"""Bienvenido a Code & Prose, el único club de lectura en el mundo que (creemos) lee ficción relacionada con el desarrollo web.""".
 * Una segunda sección que comienza con el encabezado de segundo nivel “Qué estamos leyendo”.
 * En la segunda sección, incluya la imagen llamada book-cover.png, seguida del texto entre comillas triples, donde cada palabra o frase antes de dos puntos aparece en negrita:
"""
Título: El diseñador web
Autor: Paul McFedries
Páginas: 1,576
Resumen: En la preparatoria High Falutin, [etc.]
"""
 * Una tercera sección que comienza con el encabezado de segundo nivel “Próxima reunión”.
 * En la tercera sección, incluya el texto entre comillas triples, donde cada palabra o frase antes de dos puntos aparece en negrita:
 """
 Fecha: 23 de agosto
 Hora: 6:00pm
 Ubicación: The Coder Café
 Preguntas para reflexionar: ¿Puede Daisy codificar, o qué? ¿El libro contiene demasiado HTML, o no lo suficiente? ¿Por qué es tan difícil para los nerds tener citas?
 """
 * Un elemento de pie de página que incluye el texto "Copyright" (escrito con todas las letras, sin incluir el símbolo de Copyright), seguido del año actual y, a continuación, "Code & Prose". En un párrafo aparte, el pie de página también incluye tres enlaces a cuentas de redes sociales: una para Facebook (nombre de usuario: CodeAndProse), Instagram (nombre de usuario: codeandprose) y Twitter (nombre de usuario: codenprose).
  
En segundo lugar, en un archivo separado escriba el código CSS para lo siguiente:
 * El color de fondo del encabezado es orquídea oscuro con un margen de 10 píxeles alrededor. Coloca el logotipo a la izquierda y alinea el título y el eslogan a la derecha.
 * El tamaño de fuente del título es 48px con color azul acero claro.
 * El tamaño de fuente del lema es 24 px con color azul acero claro y formateado en cursiva.
 * El tamaño de fuente del encabezado de segundo nivel es de 30 px con color darkorchid y un margen superior de 15 px.
 * El tamaño de fuente del elemento principal es 20px.
 * En la segunda y tercera sección, el texto en negrita debe utilizar el color verde mar medio.
 * La imagen llamada book-cover.png debe flotar hacia la derecha.
 * Para el título y los encabezados, utilice la fuente Fira Sans Extra Condensed Bold de Google Fonts. Para el resto del texto, utilice la fuente Source Code Pro de Google Fonts.
 * El color de fondo del pie de página es orquídea oscuro con un relleno de 5 px alrededor y un margen superior de 10 px. El color del texto es azul acero claro. Centre el texto y los enlaces a las redes sociales.
 * Para los enlaces de redes sociales, utilice los íconos Font Awesome correspondientes.
 *La página entera está centrada en la ventana del navegador.
 *La página es responsiva con un ancho máximo de 800px.
```

**Nota**: Dada la longitud de este mensaje, si utiliza Bing Copilot o Microsoft Copilot, asegúrese de utilizar el modo Preciso, que tiene un límite de 4000 caracteres.

ChatGPT debe crear primero el código HTML, que puedes copiar y pegar y guardar en un archivo llamado `index.html`. En ese código, deberías ver una línea cerca de la parte superior similar a la siguiente:

```css
<link rel="stylesheet" type="text/css" href="styles.css">
```

Este código le indica al navegador web que busque el código CSS en un archivo llamado `styles.css`, por lo que su próxima tarea es copiar el código CSS generado, luego pegarlo y guardarlo en un archivo llamado `styles.css` (o cualquier nombre que vea en la etiqueta `<link>`). Asegúrese de guardar `styles.css` en la misma carpeta que su archivo `index.html`. También debe copiar sus archivos de imagen en la misma carpeta. Consulte el apéndice A para obtener más información sobre cómo trabajar con archivos de páginas web. Envié este mensaje a GPT-4 usando la aplicación ChatGPT de OpenAI, y el código que generó dio como resultado la página que se muestra en la figura 4.8.

Si está satisfecho con la página del club de lectura que ChatGPT generó para usted, puede omitir el resto de este capítulo e implementar el código como describo en el apéndice B. Sin embargo, si desea saber un poco más sobre el código que ChatGPT generó, la siguiente sección le brinda una mirada más cercana.

<img width="585" alt="image" src="https://github.com/user-attachments/assets/f8263f70-7df3-447d-9f5a-7b62ff095cb1" />

**Figura 4.8 Mi página del club de lectura generada por ChatGPT**

## 4.3 Examinando el código

Voy a darte una descripción general breve y razonablemente no técnica del código de la página del club de lectura que ChatGPT generó según mi mensaje de la sección anterior (esa página se muestra en la figura 4.8). Tu código generado por ChatGPT será diferente al mío no solo porque tu texto e imágenes serán diferentes, sino también porque los algoritmos de ChatGPT incluyen cierta aleatoriedad incorporada, por lo que el mismo mensaje a menudo generará un código ligeramente diferente cada vez que lo ejecutes.

El resultado de ChatGPT varía según el modelo (GPT-3.5 frente a GPT-4) y la aplicación (OpenAI frente a Bing Copilot). En el caso de Bing Copilot, el resultado también depende del estilo de conversación (creativo, equilibrado o preciso).

**Nota**: El código HTML y CSS generado para mi club de lectura están disponibles en el sitio web del libro (www.manning.com/books/build-a-website-with-chatgpt) y en el repositorio de GitHub ( https://github.com/paulmcfe/websites-with-chatgpt ).

Sin embargo, cada versión de ChatGPT debería generar código HTML y CSS que sea al menos similar a lo que se muestra en las siguientes dos secciones, por lo que mis anotaciones de código deberían ayudarlo a comprender lo que sucede bajo el capó.

### 4.3.1 Examinar el HTML

El código HTML que ChatGPT generó para mi club de lectura se muestra aquí:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Code & Prose</title>
    <link rel="stylesheet" href="styles.css">                   ①
    <link rel="preconnect" href="https://fonts.gstatic.com">    ②
    <link href="https://fonts.googleapis.com/css2
          ?family=  Fira+Sans+Extra+Condensed:wght@700
          &family=Source+Code+Pro&display=swap" 
          rel="stylesheet">                                     ②
    <link rel="stylesheet" 
          href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2
          /css/all.min.css">
</head>
<body>
    <header>                                                    ③
        <img src="logo.png" alt="Code & Prose logo" id="logo">  ④
        <h1>Code & Prose</h1>                                   ⑤
        <p>Diving deep into the narrative side of code</p>      ⑥
    </header>                                                   ③
    <main>
        <section>                                               ⑦
            <h2>Welcome!</h2>
            <p>Welcome to Code & Prose, the only book 
               club in the world that (we think) 
               reads fiction related to web 
               development.</p>
        </section>                                              ⑧
        <section>                                               ⑨
            <h2>What We're Reading</h2>
            <img src="book-cover.png"                           ⑩
                 alt="Book cover"                               ⑩
                 id="book-cover">                               ⑩
            <p><b>Title:</b> The Web Designer<br>               ⑪
            <b>Author:</b> Paul McFedries<br>                   ⑪
            <b>Pages:</b> 1,576<br>                             ⑪
            <b>Summary:</b> At High Falutin High, [etc.]</p>    ⑪  
        </section>                                              ⑨
        <section>                                               ⑫
            <h2>Next Meetup</h2>
            <p><b>Date:</b> August 23<br>                       ⑬
            <b>Time:</b> 6:00pm<br>                             ⑬
            <b>Location:</b> The Coder Cafe<br>                 ⑬
            <b>Questions to ponder:</b> Can Daisy 
               code, or what? Does the book contain 
               too much HTML, or not enough? Why is 
               it so hard for nerds to date?</p>                ⑬
        </section>                                              ⑫
    </main>
    <footer>                                                    ⑭
        <p>Copyright 2023 Code & Prose</p>                      ⑮
        <p>                                                     ⑯
        <a href=https://www.facebook.com/CodeAndProse
        target="_blank">
        <i class="fab fa-facebook-square"></i></a>              ⑯
        <a href=https://www.instagram.com/codeandprose
        target="_blank">
        <i class="fab fa-instagram"></i></a>
        <i class="fab fa-x-twitter"></i></a>                    ⑯
        </p>                                                    ⑯
    </footer>                                                   ⑭
</body>
</html>
```

① Le dice al navegador web dónde encontrar el código CSS

② Carga las fuentes de la página desde Google Fonts

③ Encabezado de página

④ Logotipo de la página

⑤ Título de la página

⑥ Lema de la página

⑦ Primera sección de la página

⑧ Primera sección de la página

⑨ Segunda sección de la página

⑩ Imagen de la portada del libro

⑪ Información del libro

⑫ Tercera sección de la página

⑬ Información de la reunión del club

⑭ Pie de página

⑮ Aviso de derechos de autor

⑯ Enlaces de redes sociales

**Nota**: En mis propios experimentos, ChatGPT ocasionalmente generó código que agregó caracteres inusuales a la página. Si ve caracteres inusuales, casi siempre puede solucionar el problema agregando el código `<meta charset="utf-8">` inmediatamente después de la etiqueta `<head>` en el archivo HTML. Esta etiqueta le indica al navegador web cómo manejar ciertos caracteres, como las comillas tipográficas (“ y ”).

A continuación se muestran algunas notas a tener en cuenta al leer el código HTML:

* Las dos imágenes de la página se referencian mediante la etiqueta `<img>`, donde el valor `src` es el nombre del archivo de imagen. Si cambia el nombre de su archivo de imagen, asegúrese de cambiar también el valor `src` correspondiente.

* En la información del libro y de la reunión, la etiqueta `<br>` le indica al navegador web que comience el siguiente elemento en la siguiente línea, sin espacio adicional entre las dos líneas. Si su página tiene espacio adicional entre estas líneas, significa que ChatGPT ha utilizado etiquetas `<p>` (para párrafos) en lugar de etiquetas `<br>` (para saltos de línea). Elimine la etiqueta `<p>` al comienzo de cada línea y reemplace la etiqueta `</p>` al final de cada línea con `<br>`.

* En los enlaces de redes sociales, el código `target="_blank"` indica al navegador web que abra el enlace en una nueva pestaña. Para abrir el enlace en la misma pestaña (que es el método preferido), puedes eliminar el código `target="_blank"` de cada enlace.

* En los enlaces a redes sociales, los valores `class` hacen referencia a un icono de **Font Awesome** en particular que se mostrará como texto del enlace. Por ejemplo, `class="fab fa-instagram"` muestra el icono de Instagram.

Por último, tenga en cuenta que el código HTML incluye la siguiente línea:

```css
<link rel="stylesheet" href="styles.css">
```

Esta etiqueta le dice al navegador web dónde encontrar el código CSS, que describo en la siguiente sección.

### 4.3.2 Examinando el CSS

El código CSS generado por ChatGPT para mi página del club de lectura se muestra aquí:

```css
body {
    font-family: 'Source Code Pro', monospace;            ①
    color: black;
    max-width: 800px;                                     ②
    margin: auto;                                         ③
}
header {
    background-color: darkorchid;                         ④
    padding: 10px;                                        ⑤
}
header img {
    float: left;                                          ⑥
}
header h1 {
    font-family: 'Fira Sans Extra Condensed', sans-serif; ⑦
    font-size: 48px;                                      ⑧
    color: lightsteelblue;                                ⑧
    text-align: right;    
}
header p {
    font-size: 24px;                                      ⑨
    color: lightsteelblue;                                ⑨
    font-style: italic;                                   ⑨
    text-align: right;                                    ⑨
    clear: right;
}
main {
    font-size: 20px;                                      ⑩
}
h2 {
    font-family: 'Fira Sans Extra Condensed', sans-serif; ⑪
    font-size: 30px;                                      ⑪
    color: darkorchid;                                    ⑪
    margin-top: 15px;                                     ⑪
}
section:nth-child(2) img {
    float: right;                                         ⑫
}
section:nth-child(2) p b,
section:nth-child(3) p b {
    color: mediumseagreen;                                ⑬
}
footer {
    background-color: darkorchid;                         ⑭
    color: lightsteelblue;                                ⑭
    padding: 5px;                                         ⑭
    margin-top: 10px;                                     ⑭
    text-align: center;                                   ⑭
}
footer a {
    margin: 0 10px;                                       ⑮
    color: lightsteelblue;                                ⑮
    text-decoration: none;                                ⑮
}
```

① Aplica Source Code Pro al texto de la página

② Establece el ancho máximo de página en 800px

③ Centra la página

④ Establece el header background a darkorchid

⑤ Agrega 10px de espacio alrededor del texto del encabezado

⑥ Flota el logotipo hacia la izquierda.

⑦ Aplica Fira Sans Extra Condensed al título

⑧ Estilos del título: tamaño de fuente 48px, color azul acero claro, alineado a la derecha

⑨ Estilos del eslogan: tamaño de fuente 24 px, color azul acero claro, cursiva, alineado a la derecha

⑩ Establece el tamaño de fuente de la página normal en 20px

⑪ Aplica estilo a los encabezados de segundo nivel: fuente Fira Sans Extra Condensed, tamaño de fuente 30px, color darkorchid, margen superior 15px

⑫ Flota la portada del libro hacia la derecha.

⑬ Aplica el color verde mar medio al texto en negrita.

⑭ Estilos del pie de página: color de fondo darkorchid, color de texto lightsteelblue, relleno 5px, margen superior 10px y texto centrado

⑮ Aplica estilo a los enlaces del pie de página: márgenes izquierdo y derecho de 10 px, color del texto azul acero claro, sin subrayado

Si lo desea, puede utilizar estas anotaciones para modificar el código de su página web, como describo en la siguiente sección.

## 4.4 Personalización de la página

Si el código de la página del club de lectura de ChatGPT no es correcto por algún motivo, tienes dos formas de solucionarlo:

* Si la página está lejos de lo que quieres, reescribe tu mensaje, inicia una nueva sesión de chat y vuelve a intentarlo.

* Si la página se parece a lo que desea, solicite a ChatGPT que realice los ajustes necesarios. Asegúrese de enviar esta solicitud en la misma sesión que la solicitud original.

En el segundo caso, si el código producido por ChatGPT realmente solo necesita algunos pequeños retoques, considere modificar el código manualmente según las anotaciones que proporcioné en la sección anterior. Como no conoce el código de las páginas web, es mejor no intentar realizar cambios importantes. Sin embargo, aún quedan algunas formas de alterar el código para obtener la página que desea.

Primero, aquí hay algunas sugerencias de personalización para el código HTML:

* En el encabezado, puedes editar el título o el eslogan. Solo asegúrate de no editar ni eliminar las etiquetas HTML asociadas: `<h1>` y `</h1>` para el título; `<p>` y `</p>` para el eslogan.

* En la sección principal del código HTML, puede agregar, eliminar o editar el texto de cada encabezado de segundo nivel (es decir, el texto entre las etiquetas `<h2>` y `</h2>`; asegúrese de no editar ni eliminar estas etiquetas).

* En la sección principal del código HTML, puede agregar, eliminar o editar el texto de cada párrafo (es decir, el texto entre las etiquetas `<p>` y `</p>`; asegúrese de no editar ni eliminar estas etiquetas).

En la sección principal del código HTML, puedes agregar una nueva sección escribiendo una etiqueta `<section>` seguida de la etiqueta `</section>`. Entre estas etiquetas, puedes agregar un encabezado (un texto entre las etiquetas `<h2>` y `</h2>`) y un párrafo (un texto entre las etiquetas `<p>` y `</p>`).

A continuación se muestran algunas ideas de personalización para el código CSS:

* Si desea que su página tenga un ancho máximo diferente, cambie el valor `max- width` por algo distinto de `800px`. Por ejemplo, si aumenta el tamaño de la fuente (como describiré en un momento), es posible que desee aumentar el ancho de la página; disminuir el tamaño de la fuente significa que puede disminuir el ancho de la página. Pruebe diferentes anchos (generalmente dentro del rango de `600px` en el lado bajo y `1000px` en el lado alto) hasta que encuentre uno que se adapte a su página.

* Para cualquier valor de color, puedes cambiar el color existente por una palabra clave de color diferente. Sin embargo, ten en cuenta que cambiar un solo color puede alterar el esquema de colores de tu página. Si no te gustan los colores de tu página, elige un nuevo color primario y luego vuelve a solicitar a ChatGPT que cree un esquema de colores a partir de ese tono.

* Para cualquier valor de tamaño de fuente, puedes cambiar el número para aumentar o disminuir el tamaño de la fuente. Por ejemplo, si el texto parece apretado y difícil de leer, intenta aumentar el valor del tamaño de fuente en uno o dos píxeles. Solo asegúrate de dejar la unidad `px` en su lugar.

* Para cualquier valor de margen o padding, puedes cambiar el número para aumentar o disminuir el padding o los márgenes. Por ejemplo, si el contenido de tu página parece estar abarrotado, puedes abrirlo aumentando el padding o los márgenes. De manera similar, si los elementos de tu página parecen desconectados entre sí, intenta disminuir los márgenes. En cada caso, asegúrate de dejar la unidad `px` en su lugar.

* Para que el código de su página sea más accesible, considere convertir todas las medidas en `px` a medidas en `rem`. 1 rem es, de manera predeterminada, equivalente a 16px, por lo que 20px es 1,25 rem; 24px es 1,5rem; 32px es 2rem; 48px es 3rem; y así sucesivamente. La unidad rem es más accesible porque mide los tamaños de fuente en relación con el tamaño de fuente predeterminado que el usuario del navegador ha definido en la configuración de su navegador.

## Resumen

* Casi todas las páginas web comienzan con un encabezado que incluye al menos un logotipo, el título de la página y el lema o subtítulo de la página.

* La mayoría de las páginas web terminan con un pie de página que incluye al menos un aviso de derechos de autor y algunos enlaces a redes sociales.

* Cada elemento de la página está rodeado por un cuadro invisible que consta de cuatro partes: el contenido, que es el texto o la imagen contenida en el cuadro; el padding, que es el espacio en blanco entre el contenido y el borde; el borde, que corre a lo largo de los bordes externos del área de padding y rodea el contenido y el padding con líneas; y el margen, que es el espacio en blanco adicional agregado fuera de los bordes superior, derecho, inferior e izquierdo.

* Para incluir una imagen en su página, necesita saber el nombre del archivo de imagen y debe almacenar el archivo de imagen en la misma carpeta que los archivos de código de su página web.

* Para incluir enlaces de redes sociales en su página, necesita conocer el nombre de usuario de cada cuenta de redes sociales.

* Para obtener mejores resultados, el mensaje de su página debe ser lo más específico posible, incluidos colores, tamaños de fuente y niveles de encabezado.

* Guarde el HTML generado en el archivo `index.html` y el CSS generado en el nombre de archivo sugerido por ChatGPT en el código HTML, generalmente `styles.css`.

