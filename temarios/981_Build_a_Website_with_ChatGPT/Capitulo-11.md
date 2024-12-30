# 11 Creación de una página de portafolio

Este capítulo cubre

* Creación de tarjetas de interfaz de usuario
* Añadir un efecto de sombra paralela
* Redondeo de las esquinas de las tarjetas
* Hacer que la página sea responsiva
* Elaboración de un mensaje de ChatGPT para crear una página de portafolio
* Examinar y personalizar el código generado por ChatGPT

Una de las mejores razones para crear una página web es mostrar el trabajo personal o el trabajo de un equipo, departamento o empresa. Muchos de los proyectos de este libro han servido para ese objetivo: la página personal (capítulo 3), el diario en línea (capítulo 5), el sitio web de intereses o aficiones (capítulo 7) y la galería de fotos (capítulo 10).

En este capítulo, aprenderá otra estructura de página para promocionar las actividades de una persona, un grupo o una organización: la página de portafolio. Esta página utiliza imágenes, encabezados y texto para crear un componente de página eficaz y popular diseñado para mostrar lo que desea que vean otras personas. También aprenderá varias formas de personalizar este componente y algunas técnicas que pueden hacer que su portafolio se vea lo mejor posible, no solo en un monitor grande, sino también en pantallas más pequeñas, incluso en teléfonos inteligentes. Luego, pondrá en práctica todo este nuevo conocimiento de HTML y CSS para crear un mensaje detallado que le permita a ChatGPT generar el código de página web para su página de portafolio.

En este capítulo se ofrecen versiones comentadas del código HTML y CSS generados por ChatGPT para ayudarle a comprender cómo funciona la página de portafolios. También obtendrá algunos consejos útiles para personalizar el código.

## 11.1 Conociendo el proyecto de este capítulo

El proyecto de este capítulo es una página de portafolio. La página final incluirá los siguientes componentes:

Un elemento de encabezado que incluye un logotipo y un título.

Un elemento principal que comienza con el título del portafolio

Seis tarjetas, cada una de las cuales muestra un elemento de la cartera.

Un elemento de pie de página que incluye un aviso de derechos de autor

La figura 11.1 muestra un ejemplo de página de cartera creada con el código proporcionado por ChatGPO.



**Figura 11.1 Una página de cartera generada por ChatGPT**

La página de ejemplo es un portafolio para un diseñador de libros, pero puedes usar este tipo de diseño para muchos otros tipos de contenido:

Arte —Pinturas, fotografías, ilustraciones, moda, arquitectura, diseño de interiores, escritura.

Trabajo —Proyectos, productos, eventos, noticias, métricas clave, cursos educativos

Personas : miembros del equipo, clientes, perfiles de usuarios, testimonios

En resumen, se trata de un diseño muy versátil y empezarás a aprender a construirlo en la siguiente sección.

## 11.2 Creación de la página de portafolio

Si te dedicas a la creación (ilustración, escritura, música, bellas artes), te debes a ti mismo y a tu carrera exponerte y decirle al mundo lo talentoso que eres. ¿Cómo lo haces? Las redes sociales son la forma habitual de alardear de ti mismo en estos días. Eso está bien, pero cuando usas la plataforma de otra persona para hablar de ti mismo, estás renunciando a mucho control sobre cómo te presentas. Siempre es mejor controlar tu propio mensaje, y la mejor forma de hacerlo es crear tu propia presencia en línea. Para los creativos, esa apuesta en línea debería incluir una página de portafolio que muestre tu mejor o más reciente trabajo.

Una página de portafolio es una página web diseñada para mostrar parte (o incluso todo) de su trabajo creativo. Es el equivalente en línea del portafolio impreso que los artistas hambrientos han estado cargando de mecenas en mecenas y de empleador en empleador durante décadas. La idea principal de una página de portafolio es mostrar su trabajo creativo a personas que podrían querer comprarlo o contratarlo para que haga su trabajo creativo.

Sin embargo, incluso si no eres un artista, una página de portafolios es un excelente diseño para mostrar distintos tipos de elementos, como productos, cursos y empleados. El componente principal de una página de portafolios es la tarjeta, sobre la que aprenderás a continuación.

### 11.2.1 Construir una tarjeta

Una tarjeta , a veces llamada tarjeta de interfaz de usuario o tarjeta UI , es una colección especial de etiquetas HTML y propiedades CSS destinadas a transmitir de manera sucinta y eficiente información sobre algo, que puede ser una obra de arte, un evento, un proyecto, una persona o cualquier elemento que se encuentre en su cartera. Una tarjeta típica incluye algunos o todos los elementos siguientes:

Imagen : una fotografía, ilustración u otra imagen que proporciona una vista previa o representación del artículo.

Encabezado : el título o nombre del artículo.

Texto : una breve descripción del artículo

Botón o enlace : un elemento que permite al lector obtener más información sobre el artículo o realizar una acción, como suscribirse o comprarlo.

Existen muchas formas de organizar la información de una tarjeta, pero hay dos diseños comunes. El primero tiene la imagen en la parte superior, seguida del encabezado, el texto y, luego, el botón o enlace. La figura 11.2 muestra un ejemplo.



**Figura 11.2 Un diseño de tarjeta típico con la información que va desde la parte superior de la tarjeta hasta la parte inferior.**

Para solicitarle a ChatGPT que cree una tarjeta que use este diseño, deberá utilizar una instrucción similar a la siguiente:

Genera el código para una tarjeta con un ancho máximo de 350 px. En la parte superior de la tarjeta, agrega la imagen portfolio01.jpg de la subcarpeta images. Debajo de la imagen, agrega el encabezado de segundo nivel "Me enamoré de ChatGPT", seguido del texto "Diseñé este libro para la nueva línea de libros románticos con temática de IA de Moughton-Hifflin", seguido de un enlace "Más información" al archivo portfolio01.html. Centra el texto en la tarjeta.
El segundo diseño común tiene la imagen en un lado (puede ser el izquierdo o el derecho), con el encabezado, el texto y el botón o enlace en el otro lado. La Figura 11.3 muestra un ejemplo.



**Figura 11.3 Un diseño de tarjeta típico con la imagen a la izquierda y el texto a la derecha**

Para solicitarle a ChatGPT que cree una tarjeta que use este diseño, deberá utilizar una instrucción como la siguiente:

Genera el código para una tarjeta con un ancho máximo de 500 px. En el lado izquierdo de la tarjeta, agrega la imagen portfolio01.jpg de la subcarpeta images. En el lado derecho de la tarjeta, agrega el encabezado de segundo nivel "Me enamoré de ChatGPT", seguido del texto "Diseñé este libro para la nueva línea de libros románticos con temática de IA de Moughton-Hifflin", seguido de un enlace "Más información" al archivo portfolio01.html.
Si el diseñador que hay en usted no está contento con el espacio en blanco alrededor de la imagen, aprenderá cómo solucionarlo en la siguiente sección.

### 11.2.2 Hacer que la imagen se extienda hasta los bordes de la tarjeta

Un ajuste común y atractivo de las tarjetas es hacer que la imagen se extienda hasta los bordes de la tarjeta:

Si la imagen está en la parte superior de la tarjeta , la imagen se extiende hasta los bordes superior, izquierdo y derecho.

Si la imagen está en el lado izquierdo de la tarjeta , la imagen se extiende hasta los bordes superior, izquierdo e inferior.

Si la imagen está en el lado derecho de la tarjeta , la imagen se extiende hasta los bordes superior, derecho e inferior.

Puedes pedirle a ChatGPT que configure la tarjeta de esta manera agregando algo como lo siguiente al mensaje de la tarjeta de la sección anterior:

Asegúrese de que no haya márgenes ni relleno alrededor de la imagen para que se extienda hasta los bordes superior, izquierdo y derecho de la tarjeta.
Esta instrucción es adecuada para una tarjeta con la imagen en la parte superior y da como resultado una tarjeta que se parece a la que se muestra en la figura 11.4.



**Figura 11.4 Un diseño de tarjeta donde la imagen se extiende hasta los bordes de la tarjeta.**

Otra personalización de tarjeta útil es la sombra proyectada, que se analiza en la siguiente sección.

### 11.2.3 Agregar una sombra

Observe que en las figuras 11.2, 11.3 y 11.4 cada carta tiene un sutil efecto de sombra. Esto se llama sombra proyectada porque hace que la carta parezca como si estuviera ligeramente levantada de la página y, por lo tanto, tiene una sombra que "cae" sobre el fondo. Hay dos cosas que se deben tener en cuenta sobre estos ejemplos de sombras proyectadas:

ChatGPT agrega automáticamente la sombra paralela incluso cuando el mensaje no la especifica. Si no desea una sombra paralela, debe incluir una instrucción como la siguiente en el mensaje:

No agregue una sombra proyectada a la tarjeta.

La sombra que crea ChatGPT es atractiva, pero puede que no sea de su agrado. Por ejemplo, puede que prefiera que la sombra se extienda hacia la derecha de la tarjeta en la misma medida que se extiende hacia abajo.

La propiedad CSS que crea el efecto de sombra se llama box-shadowy su sintaxis se muestra en la figura 11.5. Hay cuatro valores con los que puedes jugar:

x-offset—La cantidad (en píxeles) que la sombra se desplaza hacia la derecha (cualquier valor positivo) o hacia la izquierda (cualquier valor negativo) en relación con la tarjeta.

y-offset—La cantidad (en píxeles) en que la sombra se desplaza hacia abajo (cualquier valor positivo) o hacia arriba (cualquier valor negativo) en relación con la tarjeta.

blur—La cantidad (en píxeles) en que la sombra está borrosa, donde 0significa que no hay desenfoque y los valores más altos hacen que la sombra sea progresivamente más borrosa.

alpha—Un valor entre 0 y 1 que define la transparencia de la sombra, donde 0significa completamente transparente y 1significa completamente opaco



**Figura 11.5 La sintaxis de la propiedad `box-shadow`**

A continuación se muestra un ejemplo de instrucción para ChatGPT para agregar una sombra personalizada a una tarjeta:

Agregue un efecto de sombra a la tarjeta donde el desplazamiento x e y sean 8px, el desenfoque sea 4px y la transparencia sea 0,5.

**NOTA**: Aunque en este capítulo se aplica una sombra proyectada solo a las tarjetas del portafolios, en la práctica puede agregar una sombra proyectada a cualquier elemento de página que cree un bloque, incluido un párrafo, encabezado, divelemento o lista numerada o con viñetas.

Esta instrucción producirá una declaración box-shadow similar a la siguiente:

caja-sombra: 8px 8px 4px rgba(0, 0, 0, 0.5);

**NOTA**: En ocasiones, ChatGPT genera un box-shadowvalor que incluye un número adicional (normalmente 0) entre el blurnúmero y la rgba()función. Este parámetro adicional determina la extensión de la sombra, que es una medida del tamaño de la sombra en relación con la tarjeta (donde 0significa que la sombra tiene el mismo tamaño que la tarjeta y los valores de píxeles más altos amplían el tamaño de la sombra).

Otro efecto que puedes aplicar a tus tarjetas es redondear las esquinas, que es el tema de la siguiente sección.

### 11.2.4 Redondeo de las esquinas

Al examinar las figuras 11.2, 11.3 y 11.4, observe que las esquinas de cada tarjeta están redondeadas, lo que le da a la tarjeta una sensación más suave y accesible. Hay dos cosas que se deben tener en cuenta sobre estas esquinas redondeadas:

ChatGPT redondea automáticamente las esquinas de las tarjetas incluso cuando el mensaje no lo solicita. Si no desea esquinas redondeadas, debe incluir una instrucción como la siguiente en el mensaje:

No redondee las esquinas de la tarjeta.
La cantidad de curvatura es variable y también puedes aplicar la curvatura solo a esquinas específicas.

La propiedad CSS que redondea las esquinas se llama border-radius, y su sintaxis se muestra en la figura 11.6.



**Figura 11.6 La sintaxis de la propiedad `border-radius`**

Puede ajustar cuatro valores:

top-left—La cantidad (en píxeles o porcentaje) de curvatura que se aplicará a la esquina superior izquierda de la tarjeta.

top-right—La cantidad (en píxeles o porcentaje) de curvatura que se aplicará a la esquina superior derecha de la tarjeta.

bottom-right—La cantidad (en píxeles o porcentaje) de curvatura que se aplicará a la esquina inferior derecha de la tarjeta.

bottom-left—La cantidad (en píxeles o porcentaje) de curvatura que se aplicará a la esquina inferior izquierda de la tarjeta.

CONSEJO: Un formato corto que ChatGPT suele generar es border-radius: value, donde valuees la cantidad (en píxeles o porcentaje) de curvatura que se aplicará a las cuatro esquinas de la tarjeta.

A continuación se muestra un ejemplo de instrucción para ChatGPT para agregar esquinas redondeadas personalizadas a una tarjeta:

Redondea solo las esquinas superiores izquierda y derecha de la tarjeta en 10 px.
Esta instrucción producirá una box-shadowdeclaración similar a la siguiente:

radio del borde: 10px 10px 0 0;
La última idea de diseño que debes investigar para una página de portafolio es asegurar que la página se muestre bien en cualquier tamaño de pantalla, que es el tema de la siguiente sección.

### 11.2.5 Cómo hacer que su página sea responsiva

Como se describe en el capítulo 10, el comportamiento de diseño predeterminado para los elementos de páginas web con forma de caja, como encabezados, pies de página, áreas de navegación, encabezados y párrafos, es que fluyan verticalmente hacia abajo en la página: el segundo elemento debajo del primero, el tercer elemento debajo del segundo, y así sucesivamente. Cada elemento del ejemplo de portafolio también será uno de estos elementos con forma de caja: el divelemento . Esto significa que si se conforma con el diseño predeterminado, los elementos de su portafolio se mostrarán como una pila vertical, lo que no es el aspecto más atractivo ni eficiente.

La solución que propuse en el capítulo 10 fue utilizar Flexbox, que convierte un elemento de una página web en un contenedor Flexbox: los elementos de ese contenedor pierden su comportamiento de diseño predeterminado rígido y se adaptan a las dimensiones actuales del navegador. Para este proyecto, puede solicitarle a ChatGPT que utilice Flexbox con una instrucción simple:

Convierte el contenedor de la cartera en un contenedor Flexbox. Permite que el contenido se ajuste y dale a cada tarjeta un ancho mínimo de 250 px y un ancho máximo de 300 px.
Tenga en cuenta que este mensaje incluye instrucciones que establecen el ancho mínimo y máximo de las tarjetas porque no desea que sean demasiado grandes ni demasiado pequeñas.

Si permite que el contenido del contenedor Flexbox (es decir, las tarjetas de su portafolio) se adapte a las dimensiones actuales de la ventana del navegador, el diseño se adaptará automáticamente. Un diseño que hace eso se denomina responsivo y significa que su portafolio se verá bien en todo tipo de dispositivos, desde monitores grandes hasta pantallas pequeñas de teléfonos inteligentes.

Sin embargo, para que su página se vea mejor en las pantallas más pequeñas, su código HTML debe incluir la siguiente etiqueta entre las etiquetas <head>y </head>:

```html
```

Esta etiqueta hace dos cosas:

Al configurar width=device-width, le estás indicando al navegador que configure el ancho de la página para que sea el mismo que el ancho del dispositivo en el que se muestra la página.

Al configurar initial-scale=1, le estás indicando al navegador que muestre la página inicialmente sin acercar ni alejar la imagen.

Para garantizar que esta etiqueta esté incluida en el código, el mensaje de ChatGPT debe incluir una instrucción similar a la siguiente:

En la sección del encabezado de la página, incluya la etiqueta <meta name="viewport" content="width= device-width , initial-scale=1">
Más adelante, después de mostrarle el diseño final de la página del portafolio (consulte la figura 11.7), también le mostraré cómo se muestra la página tanto en una tableta (figura 11.8) como en un teléfono inteligente (figura 11.9) para verificar que la página sea correcta.s, de hecho, responde.

**NOTA**: También puede trabajar con una propiedad CSS especial denominada consulta de medios para que sus páginas respondan aún mejor a distintos tamaños de pantalla. Aprenderá a trabajar con consultas de medios en el capítulo 12.

Ahora ya sabes todo lo que necesitas para solicitarle a ChatGPT que cree una página de portafolio, como se describe en la siguiente sección.

## 11.3 Elaboración del mensaje para la página del portafolio

El proyecto de este capítulo es una página de portafolio que muestra seis tarjetas que presentan las obras de un diseñador de libros ficticio. Antes de continuar, supongo que tienes lo siguiente a mano:

Uno o más de los siguientes: un logotipo de página, un título y un eslogan

Los nombres de los tipos de letra que desea utilizar para los encabezados de página y el texto de la página.

Los nombres de los colores que desea aplicar a los fondos y al texto de la página.

Consulte el capítulo 3 para obtener más información sobre cada uno de estos elementos de diseño y cómo solicitar a ChatGPT sugerencias de título, tipo de letra y color.

Para iniciar su solicitud, dígale a ChatGPT que desea construir una página web y que desea que genere el código por usted:

Quiero crear una página web de portafolios. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
Ahora revise el contenido de la página, elemento por elemento, incluido lo siguiente (consulte la figura 11.7):

Un encabezado que incluye su logotipo y título.

Un elemento principal que comienza con el título de la página.

El contenedor de cartera

Las tarjetas de cartera

Un pie de página que incluyeIncluye un aviso de derechos de autor.



**Figura 11.7 Las secciones de la página de portafolio**

A continuación, solicite a ChatGPT que genere el CSS:

En segundo lugar, en un archivo separado, escriba el código CSS para lo siguiente:
A continuación, especifique el formato de la página, incluido lo siguiente:

El color de fondo de la página y el color del texto.

Los tamaños de fuente que desea utilizar para los encabezados y el texto de la página.

Las fuentes que se deben utilizar para los encabezados y el texto normal de la página.

¿Qué elementos deben ser contenedores Flexbox (en este proyecto, estos serán el encabezado y el contenedor de portafolio)?

A continuación se muestra un ejemplo de solicitud para mi propia página de portafolio:

```text
Quiero crear una página web para una galería de fotos. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
 * Un elemento de encabezado que incluye una imagen llamada logo.png, que se almacena en el subdirectorio "images", y el título "Cover Me Book Design".
 * Una sección principal con el encabezado "Mis últimos diseños de libros".
 * Un contenedor con seis tarjetas de interfaz de usuario, cada una de las cuales tiene una imagen en la parte superior, seguida de un encabezado de segundo nivel, seguido de un texto. A continuación, se muestran los detalles de cada una de las seis tarjetas:
   * Tarjeta 1: La imagen portfolio01.jpg en la subcarpeta de imágenes; el encabezado "Me enamoré de ChatGPT"; el texto "Diseñé este libro para la nueva línea de libros románticos con temática de IA de Moughton-Hifflin".
   * Tarjeta 2: La imagen portfolio02.jpg en la subcarpeta de imágenes; el encabezado "La máquina del tiempo de Shakespeare"; el texto "Maggie O'Farrell conoce a HG Wells en este libro de ficción histórica que diseñé para Juxtaposition Publishing".
   * Tarjeta 3: La imagen portfolio03.jpg en la subcarpeta de imágenes; el encabezado "Nuestros nuevos señores supremos de los ChatBot"; el texto "Un futuro distópico de IA nos espera a todos en este título de ciencia ficción que diseñé para HJ Simpson Press".
   * Tarjeta 4: La imagen portfolio04.jpg en la subcarpeta imágenes; el encabezado "¡Yo, Yossarian!"; el texto "Una biografía del personaje John Yossarian de la novela Catch-22 de Joseph Heller; diseñada para Hyperbole Editions".
   * Tarjeta 5: La imagen portfolio05.jpg en la subcarpeta de imágenes; el encabezado "El misterio del calcetín perdido"; el texto "Un misterio perenne se resuelve en esta novela policíaca que diseñé para The Butler Did It Publications".
   * Tarjeta 6: La imagen portfolio06.jpg en la subcarpeta de imágenes; el encabezado “Guía de TikTok para personas mayores”; el texto “Diseñé la portada de esta guía práctica de TikTok para Old People Are People, Too Press”.
 * Un elemento de pie de página que incluye el símbolo de Copyright, seguido de "Cover Me Book Design".
 * En la sección del encabezado de la página, incluya la etiqueta <meta charset="utf-8">.
 * En la sección del encabezado de la página, incluya la etiqueta <meta name="viewport" content="width=device-width, initial-scale=1">.
  
En segundo lugar, en un archivo separado escriba el código CSS para lo siguiente:
 *La página tiene color de fondo crema menta y no tiene margen.
 * El texto de la página utiliza un tamaño de fuente de 20px y la fuente Nunito de Google Fonts.
 * El encabezado tiene color de fondo coral y relleno de 24px.
 * Convierte el encabezado en un contenedor de filas Flexbox con contenido centrado y permite que el contenido se ajuste.
 * El título mide 64 px, utiliza la fuente Poppins de Google Fonts y tiene un relleno de 16 px a la izquierda.
 *La sección principal tiene texto centrado y un margen de 24px.
 * El encabezado de la sección principal tiene un tamaño de fuente de 30 px y utiliza la fuente Poppins de Google Fonts.
 * Convierte el portafolio en un contenedor Flexbox. Permite que el contenido se ajuste y agrega un espacio entre los elementos de 16 px.
 * Dale a cada tarjeta un ancho mínimo de 200 px y un ancho máximo de 350 px.
 * Para cada imagen de tarjeta, asegúrese de que no haya márgenes ni relleno alrededor de la imagen para que se extienda hasta los bordes superior, izquierdo y derecho de la tarjeta.
 * Agregue un relleno de 16px a la izquierda y a la derecha del texto de la tarjeta.
 * Diseñe las tarjetas con una sombra paralela donde los desplazamientos x e y sean de 8 px, el desenfoque sea de 4 px y la transparencia sea de 0,3.
 * Dale estilo a las tarjetas con un radio de borde de 20 px.
 * El pie de página tiene color de fondo coral, relleno de 16px y texto centrado.
```

Utilicé la aplicación ChatGPT de OpenAI para enviar mi mensaje a GPT-4. El código generado generó la página que se muestra en la figura 11.8.



**Figura 11.8 Mi página de portafolio**

La figura 11.8 muestra cómo se ve la página en un monitor de escritorio. Para asegurarse de que su página se comporta de manera responsiva, debe probarla con algunas pantallas más pequeñas. Por ejemplo, la figura 11.9 muestra la parte de la página correspondiente al portafolio en una pantalla del tamaño de una tableta: el portafolio se ha adaptado al tamaño de pantalla más pequeño al adoptar un diseño de dos columnas.



**Figura 11.9 La parte de cartera de la página utiliza un diseño de dos columnas en una pantalla de tableta.**

Por supuesto, también deberías probar tu página en la pantalla de un teléfono inteligente, como se muestra en la figura 11.10. En este caso, el portafolio se ha adaptado al tamaño de pantalla aún más pequeño al reducirse a un diseño de una sola columna.



**Figura 11.10 La parte de cartera de la página utiliza un diseño de una sola columna en la pantalla de un teléfono inteligente.**

Si el código generado por ChatGPT para usted funciona, puede omitir el resto de este capítulo e implementar el código en la web (como describo en el apéndice B). Sin embargo, si desea comprender el código de la página de portafolio, siga leyendo para analizarlo más de cerca.

## 11.4 Examinar el código de la página de portafolio

Si tiene curiosidad acerca del código generado por ChatGPT, o si desea comprenderlo un poco mejor para poder modificarlo, las siguientes dos secciones ofrecen guías comentadas sobre el código HTML y CSS que se encuentran detrás de la página de portafolio mostrada anteriormente en las figuras 11.8 a 11.10.

NOTA: El código HTML y CSS generado para mi página de portafolio está disponible en el sitio web de este libro ( www.manning.com/books/build-a-website-with-chatgpt ) y en el repositorio de GitHub del libro: https://github.com/paulmcfe/websites-with-chatgpt .

Comenzaré en la siguiente sección con el código HTML.

### 11.4.1 Examinar el HTML

Aquí hay una versión anotada del código HTML que ChatGPT generó para mi página de portafolio:

```html
```

① Ayuda a que la página se muestre correctamente en dispositivos móviles

② Le dice al navegador web dónde encontrar el código CSS

③ Encabezado de página

④ Logotipo del sitio

⑤ Título del sitio

⑥ Título de la página

⑦ Portafolio

⑧ Tarjeta de portafolio

⑨ Imagen de la tarjeta

⑩ Título de la tarjeta

⑪ Texto de la tarjeta

⑫ Pie de página

Tenga en cuenta que el código HTML incluye la siguiente línea:

```html
```

Esta etiqueta le dice al navegador web dónde encontrar el código CSS, que describo en la siguiente sección.

### 11.4.2 Examinar el CSS

Aquí hay una versión anotada del código CSS que ChatGPT generó para mi página de portafolio:

```css
```

① Importa las tipografías Nunito y Poppins de Google Fonts

② Diseña el color de fondo de la página, el margen, el tamaño del texto y la fuente.

③ Diseña el color de fondo y el relleno del encabezado

④ Establece el encabezado como un contenedor Flexbox con contenido centrado y ajustado

⑤ Diseña el tamaño de fuente del título de la página, la fuente y el relleno izquierdo.

⑥ Aplica estilo al elemento principal con un margen y centra el texto

⑦ Diseña el tamaño de fuente y la fuente del título de la página.

⑧ Establece la cartera como un contenedor Flexbox con envoltura, contenido centrado y un espacio entre los elementos

⑨ Estiliza cada tarjeta con un ancho mínimo y máximo

⑩ Aplica estilo a la tarjeta con una sombra proyectada.

⑪ Le da estilo a la tarjeta con esquinas redondeadas

⑫ Asegura que las esquinas de la imagen también estén redondeadas.

⑬ Aplica estilo a cada imagen de tarjeta para que se extienda hasta los bordes de la tarjeta.

⑭ Agrega 16 px de relleno izquierdo y derecho al texto de la tarjeta.

⑮ Aplica estilo al color de fondo y al relleno del pie de página y centra el texto.

Puede consultar las anotaciones HTML y CSS de las dos secciones anteriores para ayudar a personalizar el código de su página web, como describo en la siguiente sección.

## 11.5 Personalización de la página de portafolio

A continuación se ofrecen algunas sugerencias de personalización para el código HTML:

En el encabezado, puedes editar el título. Solo asegúrate de no editar ni eliminar las etiquetas HTML asociadas <h1>y </h1>.

Si está creando un sitio que incluye varios portafolios, necesitará un área de navegación para que los visitantes puedan encontrar fácilmente sus otras páginas. Consulte el capítulo 6 para aprender cómo solicitarle a ChatGPT enlaces y una barra de navegación.

En la sección principal, puedes editar el título de la página, pero no te metas con las etiquetas HTML asociadas <h1>y </h1>.

Si desea incluir uno o más párrafos introductorios adicionales, agréguelos justo debajo de la <h1>etiqueta en el mainelemento. Asegúrese de que cada párrafo se muestre correctamente rodeándolo con una <p>etiqueta al principio y </p>otra al final:

```html
```

En la sección de pie de página del código HTML, puedes agregar enlaces a tus cuentas de redes sociales, como describo en el capítulo 4.

A continuación se muestran algunas ideas de personalización para el código CSS:

Si no te gusta el efecto de sombra, puedes eliminarlo buscando el siguiente código y eliminando la box-shadowdeclaración:

```css
```

Si no utiliza la sombra paralela, necesitará alguna forma de hacer que su tarjeta se destaque del fondo de la página. La forma más fácil de hacerlo es agregar un borde (consulte el capítulo 5) alrededor de la tarjeta. En el mismo lugar del código CSS donde box-shadowapareció la declaración, agregue la borderdeclaración, como se muestra a continuación (con los valores ajustados para que se adapten a su propia cartera):

```css
```

Si prefiere que el texto de su tarjeta esté alineado a la izquierda, puede cambiarlo buscando el siguiente código en el CSS y cambiando el text-alignvalor de centera left:

```css
```

Para cualquier valor de color, puede cambiar el color existente a una palabra clave de color diferente.

Para cualquier valor de tamaño de fuente, puede cambiar el número para aumentar o disminuir el tamaño de la fuente. Solo asegúrese de dejar la pxunidad en su lugar.

Para cualquier valor de margen o relleno, puede cambiar el número para aumentar o disminuir el relleno o los márgenes. En cada caso, asegúrese de dejar la pxunidad en su lugar.

Para que el código de tu página sea más accesible, considera convertir todas las medidas en px a medidas en rem. 1 rem equivale de manera predeterminada a 16 px, por lo que 20 px son 1,25 rem, 24 px son 1,5 rem, 32 px son 2 rem, 48 px son 3 rem, y así sucesivamente. La unidad rem es más accesible porque mide los tamaños de fuente en relación con el tamaño de fuente predeterminado que el usuario del navegador ha definido en la configuración de su navegador.

## Resumen

* Una tarjeta es una colección especial de etiquetas HTML y propiedades CSS que tiene como objetivo transmitir de manera eficiente información sobre un elemento: una obra de arte, un evento, un proyecto, una persona, etc.

* La mayoría de las tarjetas incluyen una imagen del artículo, el título o nombre del artículo, una breve descripción del artículo y un botón o enlace que permite al lector obtener más información sobre el artículo o realizar una acción relacionada con el artículo.

* Los dos diseños de tarjetas más comunes son el vertical, donde los elementos de la tarjeta se disponen de arriba a abajo (imagen, título, texto, enlace), y el horizontal, donde los elementos de la tarjeta se disponen de izquierda a derecha (generalmente con la imagen a la izquierda y el texto a la derecha).

* Puede utilizar la box-shadowpropiedad para agregar una sombra a una tarjeta.

* Puede utilizar esta border-radiuspropiedad para redondear las esquinas de una tarjeta.

* Para obtener mejores resultados, el mensaje de su página debe ser lo más específico posible, incluidos colores, tamaños de fuente y niveles de encabezado.

* Guarde el HTML generado en el archivo index.html y el CSS generado en el nombre de archivo sugerido por ChatGPT en el código HTML, generalmente styles.css.
