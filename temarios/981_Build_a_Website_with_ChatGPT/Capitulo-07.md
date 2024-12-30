# 7 Creación de contenido del sitio

Este capítulo cubre

* Colaborar con ChatGPT para crear y editar contenido
* Cómo hacer que ChatGPT escriba con tu propio estilo
* Cómo obtener ayuda de IA para editar tus textos
* Agregar una imagen de héroe
* Prompting ChatGPT para crear una página sobre un interés o pasatiempo
* Examinar y personalizar el código de la página web ChatGPT

Como expliqué en el capítulo 1, la G de GPT significa generativo, y significa que puedes usar ChatGPT no solo para tener conversaciones, sino también para crear cosas nuevas. Como has visto hasta ahora en este libro, ese contenido generado puede ser ideas para el título y el eslogan de la página, sugerencias de tipografías que coincidan con el tema de tu página, recomendaciones de esquemas de colores, enlaces, barras de navegación y, por supuesto, el código HTML y CSS para crear la página web final.

Sin embargo, tus ambiciones de generar contenido no tienen por qué limitarse a pequeños fragmentos de texto y código. Si tienes ganas de mostrar tu verdadero yo en la web para que todo el mundo lo vea, una de las mejores formas de hacerlo es escribir sobre un interés o pasatiempo que te fascine o te atraiga. Si no estás seguro de qué escribir o tienes problemas para empezar, este capítulo te muestra cómo incorporar a ChatGPT como colaborador para ayudarte a empezar. Aprenderás a obtener ideas de contenido y sugerencias de redacción generadas por IA, a utilizar la IA para la investigación e incluso a utilizar ChatGPT para escribir con tu voz.

También aprenderá a crear un mensaje detallado que le enviará a ChatGPT para que produzca el código de una página dedicada a un interés o pasatiempo, donde podrá publicar cualquier contenido que usted y ChatGPT hayan creado juntos. Este capítulo también proporciona una explicación detallada del código generado por ChatGPT e incluso brinda algunos consejos para personalizar el código manualmente para que todo quede exactamente como lo desea.

## 7.1 Comprender el proyecto de este capítulo

En este capítulo, creará un sitio web sencillo dedicado a un interés o pasatiempo. Contratará a ChatGPT como asistente de redacción para que lo ayude a generar ideas, investigar y crear los primeros borradores del contenido del sitio. La página de inicio incluirá los siguientes componentes:

Un elemento de encabezado que incluye lo siguiente:

* Una imagen que ocupa todo el ancho y la altura de la ventana del navegador.
* El título del sitio web
* El lema del sitio web
* Un elemento de navegación con enlaces a otras páginas del sitio.
* Un elemento principal con algún texto introductorio y enlaces a otras páginas del sitio.
* Un elemento de pie de página que incluye un aviso de derechos de autor

La figura 7.1 muestra un ejemplo de la página de inicio de un sitio web de interés creada con código generado por ChatGPT.



**Figura 7.1 Página de inicio de un sitio web de interés generada por ChatGPT**

Las demás páginas del sitio utilizarán una estructura similar:

* Un elemento de encabezado que incluye lo siguiente:
* Una imagen de héroe
* El título de la página
* El subtítulo de la página
* Un elemento de navegación con enlaces a otras páginas del sitio.
* Un elemento principal con el texto de la página.
* Un elemento de pie de página con un aviso de derechos de autor

La figura 7.2 muestra un ejemplo de una página de este tipo. La simplicidad de estas páginas significa que puedes personalizarlas fácilmente para usarlas con cualquier interés, pasatiempo u obsesión que quieras compartir con el mundo.



**Figura 7.2 Una página de subtemas**

## 7.2 Generación y edición de texto con ChatGPT

Si no solo tiene ganas de escribir, sino también de compartir lo que escribe con otras personas publicándolo en la web, es posible que le resulte un poco receloso utilizar ChatGPT como asistente de escritura o incluso como una especie de escritor fantasma (en la máquina). Si escribir es importante para usted, también es importante que sea su escritura, no algo creado por una IA.

Sin embargo, nada de eso significa que no puedas usar ChatGPT para parte del trabajo pesado asociado con la escritura. ¿Necesitas algunas ideas para el contenido? ChatGPT puede ayudarte. ¿Necesitas investigar para una publicación? ChatGPT es ideal para eso. ¿Te quedaste frente a una pantalla en blanco? Haz que ChatGPT genere algo, cualquier cosa, y tal vez una oración o incluso una frase de ese texto sea suficiente para despertar tu imaginación. ¿No estás satisfecho con algo que escribiste? Pídele a ChatGPT que lo revise y sugiera mejoras.

En realidad, no hay límite para las formas en que ChatGPT puede actuar como tu asistente personal de escritura. Y, por supuesto, si lo deseas, incluso puedes hacer que ChatGPT escriba todo por ti. Si puedes hacer eso y aún así dormir bien por las noches, bueno, no voy a intentar persuadirte de lo contrario.

### 7.2.1 Cómo hacer que ChatGPT sugiera ideas de escritura

ChatGPT se destaca en muchas tareas, pero una de sus mayores virtudes es sugerir ideas para escribir sobre casi cualquier tema, sin importar lo oscuro o misterioso que sea. Es decir, si tienes una idea general del tema que quieres abordar en tu escritura, ChatGPT puede generar ideas de contenido desde múltiples ángulos.

Debes comenzar tu mensaje asignando un rol a ChatGPT:

Eres un experto en [ tema ] y puedes generar ideas interesantes y creativas sobre [ tema ] basándose en la siguiente pregunta.
Reemplazar con una palabra o frase que describa el tema o asunto sobre el que desea escribir.[topic]

Ahora, agrega una pregunta que hará que ChatGPT genere algunas ideas para una publicación. Aquí tienes algunos ejemplos para empezar:

¿Cuáles son los pros y contras de [ tema ]?
¿Cuáles son las diez características principales de [ tema ]?
¿Cuáles son las cinco cosas que todo el mundo necesita saber sobre [ tema ]?
¿Cuáles son algunos mitos comunes sobre [ tema ]?
¿Cómo puede un principiante empezar con [ tema ]?
¿Cuáles son media docena de consejos y trucos para aprovechar al máximo [ tema ]?
Nuevamente, en cada caso, reemplaza con una palabra o frase que describa el tema o asunto sobre el que quieres escribir. Por ejemplo, la figura 7.3 muestra las ideas que Copilot (en modo Creativo) generó para mí en base a la siguiente indicación:[topic]

Eres un experto en la elaboración de pan y puedes generar ideas interesantes y creativas sobre la elaboración de pan basándose en la siguiente pregunta.
  
¿Cómo puede un principiante iniciarse en la elaboración de pan?


Figura 7.3 Ideas de ChatGPT para comenzar a hornear pan

Estas son sugerencias excelentes y servirían como punto de partida para una publicación que interese a los principiantes en la elaboración de pan. Tenga en cuenta que es importante considerar las ideas de contenido de ChatGPT como solo el comienzo. Depende de usted desarrollar los detalles para crear una publicación increíble.

### 7.2.2 Generar ideas sobre cómo escribir sobre un tema

En la sección anterior, aprendiste a usar ChatGPT para generar ideas para escribir. Un uso similar de ChatGPT es preguntarle cómo escribir sobre un tema en particular o un enfoque particular sobre un tema.

Como de costumbre, comience su mensaje asignando un rol a ChatGPT:

Eres un coach de escritura y un experto en [ tema ] y puedes generar consejos prácticos y creativos sobre cómo escribir sobre [ tema ] basándose en la siguiente pregunta.
Reemplazar con una palabra o frase que describa el tema o asunto que desea explorar a través de la escritura.[topic]

A continuación, agrega una pregunta que le pedirá a ChatGPT que sugiera ideas sobre cómo escribir sobre tu tema. A continuación, se muestran algunos ejemplos:

¿Cuáles son las mejores formas de introducir a un principiante en [ tema ]?
Una vez que alguien ha aprendido los conceptos básicos de [ tema ], ¿qué debo enseñarle a continuación?
¿Cómo puedo lograr que alguien que no sabe nada sobre [ tema ] se entusiasme con el tema?
¿Cuáles son algunas formas de escribir de manera atractiva sobre [ tema ]?
¿Qué tipos de publicaciones son más adecuadas para escribir sobre [ tema ]?
Nuevamente, reemplaza cada ejemplo con texto que describa el tema o asunto de tu escrito. Por ejemplo, la figura 7.4 muestra las ideas de escritura que Copilot (en modo Creativo) generó a partir de la siguiente indicación:[topic]

Eres un coach de escritura y un experto en panadería y puedes generar consejos prácticos y creativos sobre cómo escribir sobre panadería basándose en la siguiente pregunta.
  
¿Cuáles son algunas formas de escribir de manera atractiva?¿Qué opinas sobre la elaboración del pan?
¡Éstas son excelentes sugerencias no sólo para escribir sobre cómo hornear pan, sino también para escribir sobre casi cualquier otra cosa!



**Figura 7.4 Consejos de ChatGPT para escribir de forma atractiva sobre la elaboración de pan**

### 7.2.3 Cómo obtener ayuda de ChatGPT para investigar un tema

Los modelos GPT que sustentan ChatGPT se entrenaron con una cantidad de datos imposible de imaginar, lo que significa que saben bastante sobre casi cualquier tema que se te ocurra. Eso hace que ChatGPT sea el asistente de investigación perfecto, ya que puedes pedirle ayuda para explorar cualquier tema sobre el que quieras escribir y recibirás muchos consejos útiles.

A continuación se muestra un mensaje que puede utilizar para solicitar asistencia a ChatGPT para su investigación:

Ayúdame a investigar [ tema ] para un público general. Estoy interesado en A , B y C. Proporciona X , Y y Z. Además, incluye datos curiosos o anécdotas interesantes que puedan resultar interesantes para los lectores. El objetivo es proporcionar una gran cantidad de información que sea precisa y detallada, pero que también sea fácil de entender para un público amplio. Proporciona enlaces a tus fuentes.
Como es habitual, se trata de una breve descripción del tema que desea investigar. Esto es lo que representan los demás marcadores de posición:[topic]

A, B, y C—Temas generales relacionados con el tema general.

X, Y, y Z—Aspectos específicos del tema general.

Consejo La última oración del mensaje asume que estás usando una versión de ChatGPT que está conectada a la web. Recomiendo encarecidamente una versión conectada a la web para esto porque los enlaces generados te permiten verificar los resultados de ChatGPT y también te brindan más material para tu investigación.

He aquí un ejemplo:

Ayúdame a investigar la historia del café para un público general. Me interesa el descubrimiento del café, su difusión por todo el mundo y su impacto cultural en diferentes sociedades. Proporciona figuras y eventos históricos clave, variedades notables de café y la evolución de los hábitos de consumo de café a lo largo del tiempo. Además, incluye cualquier dato curioso o anécdota interesante que pueda resultar interesante para los lectores. El objetivo es proporcionar una gran cantidad de información que sea precisa y detallada, pero también fácil de entender para un público amplio. Proporciona enlaces a tus fuentes.
La figura 7.5 muestra la última parte de una respuesta excepcionalmente larga a la pregunta anterior de Copilot (en modo creativo). La pregunta asume que estás escribiendo para un público general, pero, por supuesto, debes modificarla según el lector al que te dirijas.



**Figura 7.5 La última parte de la respuesta de ChatGPT a una solicitud de ayuda para investigar la historia del café.**

### 7.2.4 Cómo hacer que ChatGPT escriba con tu propia voz

Un objetivo difícil de alcanzar de la escritura generada por ChatGPT es lograr que el modelo produzca una prosa que suene como la tuya. Seguro, ChatGPT puede generar fácilmente (y, a menudo, de manera divertida) prosa al estilo de escritores famosos como James Joyce, Emily Dickinson y Dr. Seuss. Esto se debe a que ChatGPT fue entrenado (casi con certeza) con grandes muestras de los escritos de esos autores. Sin embargo, es poco probable que ChatGPT tenga la menor idea de cómo escribes .

Sin embargo, esto no es un problema, ya que puedes "entrenar" a ChatGPT para que escriba como tú. ¿Cómo? Dándole a ChatGPT varias muestras de tu escritura, pidiéndole que analice el tono y el estilo de esas muestras y luego pidiéndole que escriba algo nuevo con la misma voz.

Aquí está el mensaje:

Eres un escritor fantasma experimentado. Con varios ejemplos de la escritura de un autor, eres hábil para detectar el tono y el estilo de la escritura y emular la voz de ese escritor para generar nuevos textos.
  
A continuación se presentan varios ejemplos de escritura, cada uno de ellos entre comillas triples.
  
Examine las muestras para determinar la voz única del escritor.
  
Emular la voz del escritor para generar X.
  
"""
Ejemplo de escritura n.° 1
"""
  
"""
Ejemplo de escritura n.° 2
"""
  
"""
Ejemplo de escritura n.° 3
"""
  
"""
Ejemplo de escritura n.° 4
"""
  
"""
Ejemplo de escritura n.° 5 
"""
Reemplace cada instancia de Writing sample #ncon una muestra de su escritura.

**Nota**: Lo ideal es que sus muestras de escritura utilicen el mismo estilo y tono que desea utilizar para el texto que desea crear.

No es necesario que incluyas las cinco muestras. Puedes usar solo dos o tres o incluso una sola muestra larga, pero recuerda que cuanto más texto proporciones, más preciso será el análisis que proporcione ChatGPT y más acertado será el mensaje.

Consejo: si tienes un autor favorito cuyo estilo de escritura admiras y te gustaría emular hasta cierto punto, inclúyelo en tu mensaje. Por ejemplo, para pedirle a ChatGPT que incluya un poco del estilo y el tono de Eudora Welty, agrega lo siguiente a tu mensaje: Please also include about 10 percent of the tone and style of Eudora Welty.

En el mensaje, reemplaza X por una breve descripción del texto que quieres que ChatGPT genere. A continuación, se muestra un ejemplo:

Eres un escritor fantasma experimentado. Con varios ejemplos de la escritura de un autor, eres hábil para detectar el tono y el estilo de la escritura y emular la voz de ese escritor para generar nuevos textos.
  
A continuación se presentan varios ejemplos de escritura, cada uno de ellos entre comillas triples.
  
Examine las muestras para determinar la voz única del escritor.
  
Emular la voz del escritor para generar una noticia satírica basada en las múltiples pronunciaciones de las letras "ough".
  
"""
Investigadores de la Universidad de Aalborg anunciaron hoy que finalmente han descubierto el tan ansiado Continuum Sopa-Nueces. Científicos de todo el mundo han estado buscando este esquivo elemento desde que la suegra de Albert Einstein propuso su existencia en 1922. "Hoy es un día increíble para la comunidad de físicos y para la humanidad en su conjunto", dijo el investigador principal Lars Grüntwerk. "Hoy, por primera vez en la historia, estamos a punto de saberlo todo, desde la sopa hasta, bueno, los frutos secos".
"""
  
"""
SCHECHENECTADY, ​​NY--Después de un matrimonio largo y tempestuoso, los dos sentidos de la palabra "supervisión" han solicitado el divorcio. Aduciendo diferencias irreconciliables, el sentido "responsable" de la palabra ("cuidado o gestión vigilante") y el sentido "irresponsable" ("una omisión o un error") se han separado. "Después de un tiempo, se volvió demasiado", dijo la supervisión responsable. "No se puede confiar en la otra supervisión ni siquiera para la tarea más pequeña. Es '¡Ups!' esto y '¡Lo siento!' aquello. Creo en ser cuidadoso y en asegurarme de que las cosas se hagan bien, así que simplemente no puedo soportar vivir con tal negligencia".
"""
  
"""
AIEA, Hawaii--El ex Secretario General de las Naciones Unidas Boutros-Boutros Ghali y el actual Subsecretario de las Naciones Unidas para la Movilización Alfabética Yada-Yada Yada anunciaron hoy la formación del Comité Internacional de Asistencia Vocal de las Naciones Unidas. El mandato de UNIVAC es "ayudar a las personas privadas de vocales dondequiera que vivan y financiar los esfuerzos de socorro en las zonas más afectadas". "Tenemos una buena reserva de a, e y o", dijo Ng Ng, Oficial de Distribución de Cartas de UNIVAC. "Esperamos tener un suministro adecuado de i y u en los próximos seis meses. Mientras tanto, podemos utilizar nuestras y adicionales en caso de necesidad".
"""
  
"""
KALAMAZOO, Michigan—Un grupo de gramáticos descontentos que se autodenominan "Estamos locos como el infierno" ha presentado una serie de demandas civiles en las últimas semanas. Los destinatarios de estas demandas son escritores, narradores y entrevistados profesionales de la calle que, según afirman, son inveterados violadores de las reglas de la gramática. La portavoz del grupo, Millicent Peevish, directora de la biblioteca del distrito de Kalamazoo, dijo que los gramáticos ya no podían quedarse de brazos cruzados y permitir "la división de infinitivos inocentes y el final de oraciones con preposiciones malvadas, muy malvadas". Una campaña anterior, llamada Shock and Appalled (Conmoción y consternación), que se centró en escribir cartas irritadas a los editores de varias publicaciones locales, no tuvo ningún efecto perceptible.
"""
  
"""
En un informe publicado hoy, los expertos en comunicación han declarado que los mensajes instantáneos que intercambian los adolescentes no son en realidad más que un galimatías. El director general de chat de Estados Unidos, Todd Dood, con la ayuda técnica de la Agencia de Seguridad Nacional, examinó miles de mensajes instantáneos. Durante mucho tiempo se ha creído que los mensajes instantáneos de los adolescentes contenían abreviaturas (como LOL, por "me estoy riendo a carcajadas" y MAIBARP, por "mi acné se está convirtiendo en un verdadero problema"), formas cortas (como L8R, por "más tarde", y R2D2, por "R2D2") y jerga (como whassup, por "qué pasa" y yo, por "Hola, me alegro de conocerte. ¿Quieres tener una conversación?").
"""
La Figura 7.6 muestra la historia que GPT-4 (Copiloto en modo creativo) generó basándose en mis muestras de escritura.



**Figura 7.6 La historia generada por Copilot en modo Creativo**

Este es un primer intento bastante bueno: coincide con el tono y el estilo de los ejemplos de escritura, es una idea narrativa decente y tiene un humor genuino. Sin embargo, está lejos de ser perfecto:

Contiene algunos errores, como incluir “Pittsburgh” como ejemplo de una palabra que utiliza las letras “ough”.

Algunos textos son torpes y será necesario reescribirlos considerablemente para ponerlos a punto.

El uso de nombres reales (como el de la jueza Sonia Sotomayer) en una pieza satírica como ésta es una mala elección. Una mejor opción sería utilizar nombres inventados que jueguen con las letras “ough”.

Este tipo de problemas son comunes con los textos generados por IA, por lo que siempre debes revisar cuidadosamente todo lo creado por ChatGPT y estar preparado para reescribir bastante.

### 7.2.5 Reescritura del texto de la publicación

Después de haber escrito un texto, es posible que se pregunte si su prosa podría mejorarse de alguna manera para que sea más divertida, más concisa, más detallada, más fácil de entender, más académica, etc. Afortunadamente, siempre que su texto esté en línea o en un formato que pueda cargar en un navegador web (como un archivo HTML, un archivo de texto o un archivo PDF), ChatGPT (en concreto, la aplicación Microsoft Copilot) estará encantado de ayudarle. A continuación, le indicamos cómo:

   1. En el navegador Microsoft Edge, abra la barra lateral de Copilot.

   2. Navegue hasta la página o abra el archivo que contiene el texto que desea reescribir.

   3. Seleccione el texto que desea reescribir.

   4. En la barra lateral, verá el mensaje Send selected or copied text to chat?, como se muestra en la figura 7.7.



Figura 7.7 Seleccione algún texto en la página actual y Copilot le preguntará si desea enviarlo a la IA.

   5. Haga clic en Enviar. Copilot le preguntará qué desea hacer con el texto.

   6. Escriba sus instrucciones. A continuación, se muestran algunos ejemplos:

   — Hazlo más divertido

   —Hazlo más conciso

   — Hazlo más fácil de entender

   —Hazlo más académico

   —Reescríbalo para un niño de 10 años.

   7. Pulse Enter o Return. Copilot revisará el texto seleccionado según las instrucciones que proporcionó en el paso 6.

La figura 7.8 muestra el resultado cuando le pedí a Copilot que reescribiera el texto seleccionado que se muestra en la figura 7.7 para un niño de 10 años.



**Figura 7.8 El texto seleccionado de la figura 7.7, reescrito para un niño de 10 años.**

Es posible que hayas notado algo en todos los ejemplos de texto que he generado con ChatGPT hasta ahora. Así es: ¡no hay etiquetas HTML! Son importantes, así que aprenderás a incluirlas en tu texto generado con ChatGPT en la siguiente sección.

### 7.2.6 No olvides las etiquetas HTML

Independientemente del texto que crees en colaboración con ChatGPT, al final el texto se encontrará en una página web. Esto significa que el texto debe estar estructurado con las etiquetas HTML adecuadas, en particular para los encabezados y párrafos del texto. Para que ChatGPT haga esto por ti, agrega lo siguiente al final de tu mensaje de redacción:

Agregue etiquetas HTML al texto, pero no genere el código para una página web completa.
Una vez que el texto de su sitio esté listo para publicar, es momento de que ChatGPT lo ayude a crear su página de inicio. Aprenderá cómo hacerlo en la siguiente sección.

## 7.3 Creación de la página de inicio

Como este proyecto es un sitio web de varias páginas, es mejor crear los componentes del sitio en etapas. El proceso básico se resume aquí:

Solicite a ChatGPT que genere el código HTML para la página de inicio del sitio web.

Indique a ChatGPT que genere el código CSS para el estilo del sitio web. Tenga en cuenta que es mejor combinar estos dos primeros pasos en un solo mensaje.

Para cada una de las demás páginas de su sitio, solicite a ChatGPT que genere el código HTML para esa página. En particular, la solicitud para cada una de las demás páginas del sitio debe incluir lo siguiente:

Una instrucción para utilizar el mismo archivo CSS en el que guardó el CSS generado en el paso 2

Una instrucción para no generar estilos adicionales, particularmente estilos en línea (es decir, código CSS insertado directamente en etiquetas HTML)

Antes de llegar a todo eso, tómese un minuto para familiarizarse con la nueva tecnología de página web presentada en este capítulo.

### 7.3.1 Trabajar con imágenes de héroe

La única tecnología nueva para páginas web que aprenderá en este capítulo es la imagen principal : una foto o ilustración llamativa que ocupa todo el ancho (y normalmente todo el alto) de la ventana del navegador cuando accede por primera vez a una página. La figura 7.9 muestra un ejemplo de página web que incluye una imagen principal.

Un primer plano de un pan Descripción generada automáticamente

**Figura 7.9 Una página web con una imagen de héroe**

A continuación se muestran algunos consejos a tener en cuenta al utilizar una imagen destacada:

El asunto de la imagen debe ser relevante al tema de tu página.

La imagen debe ser dramática o llamativa de alguna manera.

Utilice una imagen de alta calidad y sin distorsiones como la pixelación. Si utiliza una fotografía, debe estar bien compuesta y bien iluminada.

No utilice un archivo de imagen que sea demasiado pequeño, ya que se distorsionará cuando el navegador lo amplíe para que se ajuste a la ventana. Una imagen de 1200 píxeles de ancho con una relación de aspecto (es decir, la relación entre el ancho y la altura) de 16:9 es el tamaño ideal para la mayoría de las pantallas más grandes (y para las pantallas de dispositivos más pequeños en modo horizontal).

Utilice una imagen que no sea tan recargada que el texto se pierda o sea ilegible.

Como verás un poco más adelante, puedes indicarle a ChatGPT que oscurezca un poco la imagen, así que no te preocupes si tu imagen aparece demasiado clara para tu texto.

Si no tiene una imagen adecuada, puede pedirle a DALL-E o al Creador de imágenes de Copilot que genere una para usted (como describí en el capítulo 5).

Para que ChatGPT agregue una imagen de héroe a una página, el mensaje debe incluir una instrucción similar a la siguiente:

Incluya un encabezado que utilice el archivo hero.jpg como imagen principal.
Curiosamente, cuando examinas el código HTML, no verás ninguna referencia al archivo de imagen. Por ejemplo, aquí está el código HTML que crea el encabezado que se muestra en la figura 7.9:

```html
```

La imagen del héroe está incrustada en el headerelemento en el CSS, como lo muestra esta lista parcial de la headerregla utilizada para el headerelemento en la figura 7.9:

```html
```

Este código le indica al navegador web que muestre el archivo de imagen hero.jpg como fondo del headerelemento y que la imagen debe cubrir todo el elemento. El uso de una imagen de héroe es una excelente manera de captar la atención de un visitante desde el principio, por lo que ha sido una de las tendencias de diseño web más populares en los últimos años.

### 7.3.2 Elaboración del mensaje de la página de inicio

El proyecto de este capítulo es un sitio web dedicado a un interés o pasatiempo. Ya casi está listo para construir la página de inicio de ChatGPT, pero primero debe asegurarse de tener estos elementos:

Algunos o todos los siguientes: un logotipo de página, un título y un eslogan.

Los nombres de los tipos de letra que desea utilizar para los encabezados de página y el texto de la página.

Las palabras clave de los colores que desea aplicar a los fondos y textos de las páginas.

Consulta el capítulo 3 para obtener más información sobre estos elementos de diseño y cómo solicitar a ChatGPT sugerencias de título, tipo de letra y color.

El punto de partida para el sitio web de su interés o pasatiempo es la página de inicio, para cuya creación puede contar con la ayuda de ChatGPT. Su mensaje debe comenzar así:

Quiero crear una página web para la página de inicio de un sitio web. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
A continuación, especifique el contenido de su página, incluyendo lo siguiente (consulte la figura 7.10):

Un encabezado que incluye su imagen principal, título de página, lema y una barra de navegación con enlaces a otras páginas de su sitio.

Un elemento principal que comienza con un párrafo introductorio que da la bienvenida a los visitantes de su sitio.

Para cada uno de los subtemas de su sitio, un elemento de sección que incluye un encabezado con el título del subtema, una descripción del subtema y un enlace al subtema.

Un pie de página que incluye un aviso de derechos de autor

A continuación, solicite a ChatGPT que genere el CSS según el formato que desea para su página:

En segundo lugar, en un archivo separado, escriba el código CSS para lo siguiente:
Especifique el formato, incluido lo siguiente:

El color de fondo de la página y el color del texto.

Los tamaños de fuente y colores que desea utilizar para el título de la página, el lema y los enlaces de navegación.

Las fuentes a utilizar para los encabezados y el texto de la página normal.

Un ancho máximo para el elemento principal. Esto evita que las líneas de texto sean demasiado largas. Una longitud máxima de 800 px es adecuada para la mayoría de las páginas.



**Figura 7.10 Las secciones de la página de inicio del sitio de interés**

A continuación se muestra un ejemplo de mensaje para mi propia página de inicio:

Quiero crear una página de inicio para un sitio web. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
 * Un encabezado que utiliza el archivo hero.jpg como imagen de héroe.
 * El encabezado también incluye el título “Pan en el hueso” y el lema “Una mirada a medias a la historia y la cultura del pan”.
 * El encabezado también debe incluir cuatro enlaces en la esquina superior derecha:
   * El texto “Inicio” que enlaza al archivo “index.html”.
   * El texto "Historial" que enlaza al archivo "history.html".
   * El texto “Cultura” que enlaza al archivo “cultura.html”.
   * El texto "Idioma" que enlaza al archivo "idioma.html".
 * Un elemento principal que incluye los siguientes cinco elementos:
   * Un párrafo introductorio que incluya el texto "Bienvenidos a Bread in the Bone, donde yo, panadero, comedor de pan y un nerd del pan, trato de darle sentido al significado histórico, cultural y lingüístico del más humilde de los alimentos básicos del hogar: la hogaza de pan. Es lo mejor desde, bueno, ya saben..."
  * Un segundo párrafo que consta del texto "Este sitio está dividido en tres secciones:"
  * El encabezado de segundo nivel "Historia" seguido de un párrafo que incluye el texto "Una breve y probablemente no muy precisa historia del pan, desde sus orígenes antiguos hasta los granos antiguos de la actualidad". Luego el texto "Échale un vistazo" como un enlace a "history.html".
  * El encabezado de segundo nivel “Cultura” seguido de un párrafo que incluye el texto “Un análisis notablemente superficial del significado cultural del pan, desde sus significados religiosos hasta sus usos sociales”. Luego el texto “Léalo” como un enlace a “culture.html”.
  * El encabezado de segundo nivel "Lenguaje" seguido de un párrafo que incluya el texto "Una inmersión no tan profunda en las raíces lingüísticas y los usos de la palabra pan, desde su etimología hasta sus variadas metáforas". Coloque la palabra "pan" en cursiva. Luego agregue el texto "Ir allí" como un enlace a "language.html".
 * Un elemento de pie de página que incluye el símbolo de Copyright, seguido del año actual, seguido de "Paul McFedries".
  * En la sección del encabezado de la página, incluya la etiqueta <meta charset="utf-8">.
  
En segundo lugar, en un archivo separado escriba el código CSS para lo siguiente:
 *El color de fondo de la página es trigo.
 *La imagen del héroe cubre toda la ventana del navegador.
 * Agregue un degradado lineal al fondo del encabezado para oscurecer ligeramente la imagen principal.
 * Hacer que todo el texto del encabezado sea blanco.
 * Centrar el título y el eslogan tanto horizontal como verticalmente.
 * Hacer que el título tenga 72px.
 * Haz que el eslogan tenga 36 px.
 * Hacer que los enlaces del encabezado tengan un tamaño de 24 px.
 * Dale estilo a los encabezados con un tamaño de 48 px, sin margen inferior, el color marrón oscuro y la tipografía Raleway de Google Fonts.
 * Diseña el resto del texto de la página con un tamaño de 24 px, un margen inferior de 20 px y la tipografía Lato de Google Fonts.
 * Dale estilo a los enlaces del elemento principal con el color marrón silla de montar.
 * La sección principal tiene un relleno de 25 px alrededor y un ancho máximo de 800 px.
 *El pie de página tiene un borde superior.
ChatGPT debe crear primero el código HTML, que puedes copiar y pegar y guardar en un archivo llamado index.html. En ese código, deberías ver una línea cerca de la parte superior similar a la siguiente:

```html
```

Este código le indica al navegador web que busque el código CSS en un archivo llamado styles.css, por lo que tu próxima tarea es copiar el código CSS generado, pegarlo en un archivo y guardarlo como styles.css (o cualquier nombre que veas en la <link>etiqueta). Asegúrate de guardar styles.css en la misma carpeta que tu archivo index.html. También debes copiar tu archivo de imagen principal en la misma carpeta. Consulta el apéndice A para obtener más información sobre cómo trabajar con archivos de páginas web.

Envié este mensaje a GPT-4 mediante la aplicación ChatGPT de OpenAI. El código generado generó la página que se muestra en la figura 7.11.



**Figura 7.11 La página de inicio generada por ChatGPT**

Si te gusta la página de inicio que ChatGPT creó para ti, puedes saltarte el resto de esta sección y pasar a las otras páginas (consulta “Creación de indicaciones para las otras páginas del sitio”). Sin embargo, si quieres saber un poco más sobre el código que ChatGPT generó, la siguiente sección te ofrece una visión más detallada.

## 7.4 Examinar el código de la página de inicio

Voy a darles una descripción general breve y no demasiado técnica del código de la página de inicio que resultó de mi solicitud de la sección anterior (esa página de inicio se muestra en la figura 7.11).

**Nota**: El código HTML y CSS generado para mi página de diario en línea están disponibles en el sitio web de este libro ( www.manning.com/books/build-a-website-with-chatgpt ) y en el repositorio de GitHub del libro: https://github.com/paulmcfe/websites-with-chatgpt .

Cada versión de ChatGPT debe generar código HTML y CSS que sea al menos similar a lo que se muestra en las siguientes dos secciones, por lo que mis anotaciones de código deberían ayudarlo a comprender lo que sucede bajo el capó.

### 7.4.1 Examinar el HTML

El código HTML que ChatGPT generó para la página de inicio del sitio web de mi interés se muestra aquí:

```html
```

① Especifica el conjunto de caracteres de la página

② Carga las fuentes de la página desde Google Fonts

③ Le dice al navegador web dónde encontrar el código CSS

④ Encabezado de página

⑤ Elemento de navegación

⑥ Título de la página

⑦ Lema de la página

⑧ Encabezado de página

⑨ Elemento principal

⑩ Introducción de la página

⑪ Cada elemento de sección tiene un encabezado, una descripción y un enlace.

⑫ Elemento principal

⑬ Pie de página

Tenga en cuenta que el código HTML incluye la siguiente línea:

```html
```

Esta etiqueta le dice al navegador web dónde encontrar el código CSS, que describo en la siguiente sección.

### 7.4.2 Examinando el CSS

El código CSS generado por ChatGPT para la página de inicio del sitio web de mi interés se muestra aquí:

```css
```

① Restablece algunos estilos

② Diseña el color de fondo de la página, la fuente, el tamaño de fuente y el color del texto.

③ Configura la imagen del héroe para que llene la ventana del navegador

④ Centra el texto del encabezado

⑤ Oscurece la imagen del héroe para que el texto sea más fácil de leer.

⑥ Da estilo al elemento de navegación

⑦ Da estilo a los enlaces de navegación

⑧ Agrega un subrayado a cada enlace de navegación cuando se pasa el cursor sobre él.

⑨ Establece el tamaño de fuente del título de la página a 72 px y aplica la fuente Raleway

⑩ Aplica estilo al eslogan con un tamaño de fuente de 36 px

⑪ Aplica estilo a los encabezados de página con color marrón, tamaño de fuente 48 px y la fuente Raleway.

⑫ Agrega un margen de 20 px debajo de cada párrafo del elemento principal

⑬ Aplica estilo al elemento principal con un relleno de 25 px, un ancho máximo de 800 px y centrado.

⑭ Aplica estilo a los enlaces de la página con color marrón oscuro y sin subrayado.

⑮ Agrega un subrayado a cada enlace cuando se pasa el cursor sobre él.

⑯ Da estilo al pie de página

Si lo desea, puede utilizar estas anotaciones para modificar el código de su página web, como describo en la siguiente sección.

### 7.4.3 Personalización de la página de inicio

Si no te gusta la página de inicio que resulta del código generado por ChatGPT, puedes modificar el mensaje y volver a intentarlo. Sin embargo, si solo quieres hacer algunos pequeños cambios, considera editar el código manualmente.

Primero, aquí hay algunas sugerencias de personalización para el código HTML:

En el encabezado, puedes editar el título o el eslogan. Solo asegúrate de no editar ni eliminar las etiquetas HTML asociadas: <h1>y </h1>para el título, y <p>y </p>para el eslogan.

En el encabezado, edite el texto del enlace y el nombre del archivo del enlace según sea necesario para los archivos de su sitio web.

Edite los sectionelementos, ajustando el encabezado, la descripción y el enlace según sea necesario.

Para agregar una nueva sección, copie una sección existente (es decir, todo lo que se encuentre entre y incluyendo un solo par de etiquetas <section>y </section>), pegue el código donde lo desee en el mainelemento (es decir, entre las etiquetas <main>y </main>) y luego ajuste el encabezado, la descripción y el enlace. (Consulte el capítulo 6 para obtener instrucciones más detalladas sobre cómo agregar un nuevo sectionelemento).

En la sección de pie de página del código HTML, puedes agregar enlaces a tus cuentas de redes sociales, como describí en el capítulo 4.

A continuación se muestran algunas ideas de personalización para el código CSS:

Para establecer la oscuridad de la imagen del héroe, ChatGPT usa el siguiente código:

gradiente lineal(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5))
Puedes controlar la oscuridad ajustando los números finales en las dos rgbafunciones (los 0.5valores en este código). La primera rgbafunción controla la oscuridad de la mitad superior de la imagen y la segunda rgbafunción controla la oscuridad de la mitad inferior. Utiliza valores más cercanos a 0para una imagen más clara y más cercanos a 1para una imagen más oscura. Aquí tienes un ejemplo más oscuro:

      gradiente lineal(rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0.75))
Para darle más espacio a tu texto, crea un espacio extra entre cada línea agregando la declaración line-height: 1.5;en algún lugar de la regla del código CSS body:

```css
```

Si desea que su página tenga un ancho máximo diferente, busque la mainregla en el código CSS y cambie el max-widthvalor a algo distinto de 800px. En el siguiente ejemplo, he cambiado el ancho máximo a 960px:

```css
```

Para cualquier valor de color, puede cambiar el color existente a una palabra clave de color diferente.

Para cualquier valor de tamaño de fuente, puede cambiar el número para aumentar o disminuir el tamaño de la fuente. Solo asegúrese de dejar la pxunidad en su lugar.

Para cualquier valor de margen o relleno, puede cambiar el número para aumentar o disminuir el relleno o los márgenes. En cada caso, asegúrese de dejar la pxunidad en su lugar.

Para que el código de tu página sea más accesible, considera convertir todas las medidas en px a medidas en rem. 1 rem equivale de manera predeterminada a 16 px, por lo que 20 px son 1,25 rem, 24 px son 1,5 rem, 32 px son 2 rem, 48 px son 3 rem, y así sucesivamente. La unidad rem es más accesible porque mide los tamaños de fuente en relación con el tamaño de fuente predeterminado que el usuario del navegador ha definido en la configuración de su navegador.

## 7.5 Creación de indicaciones para las demás páginas del sitio

Si bien es posible que el sitio web de tu interés o pasatiempo conste de una sola página, es mucho más probable que tengas varias páginas, una para cada subtema del tema principal de tu sitio. Si ese es el caso, tu siguiente tarea es solicitarle a ChatGPT el código para crear las demás páginas.

Afortunadamente, estas otras páginas tendrán una estructura muy similar a la de tu página de inicio, con la única diferencia de que el mainelemento almacenará los encabezados y el texto de cada página. Todo esto significa que el mensaje para cada página de subtema será muy similar al mensaje para tu página de inicio. Ten en cuenta también que no necesitas ningún CSS nuevo para estas páginas de subtemas, por lo que puedes omitir la parte CSS del mensaje.

A continuación se muestra un mensaje genérico que puedes utilizar:

Quiero crear una página web. No sé programar, así que necesito que me proporciones el código.
  
Escriba el código HTML para una página web que incluya lo siguiente:
 * Un elemento de encabezado que incluye el título "[título de la página]" y el eslogan "[eslogan de la página]".
 * El encabezado también debe incluir los siguientes enlaces en la esquina superior derecha:
[Copia los enlaces de tu página de inicio aquí]
*Un elemento principal que incluye el texto entre comillas triples.
 """
[el contenido de la página va aquí]
 """
 * Un elemento de pie de página que incluye el símbolo de Copyright, seguido del año actual, seguido de "[su nombre]".
 * En la sección del encabezado de la página, incluya la etiqueta <meta charset="utf-8">.
 * En la sección del encabezado de la página, incluya una referencia a un archivo de hoja de estilo llamado "styles.css".
 * En la sección del encabezado de la página, incluya una referencia a las fuentes de Google X e Y.
 * No agregue ningún estilo en línea.
Tenga en cuenta la instrucción final a ChatGPT de no agregar estilos en línea, que se refiere al código CSS agregado directamente a una etiqueta HTML. En ausencia de instrucciones relacionadas con CSS, ChatGPT tiene una tendencia a insertar algunas sugerencias de formato en forma de estilos en línea. Debido a que todo el estilo que necesita ya está presente en su archivo styles.css, debe indicarle a ChatGPT que no agregue ningún estilo nuevo que pueda estropear sus páginas.

La figura 7.12 muestra una página de ejemplo generada por ChatGPT para el sitio de mis intereses. Cualquiera sea su interés o pasatiempo, ¿por qué no solicitar la ayuda de ChatGPT para compartir su entusiasmo con amigos, familiares y cualquier persona que visite su nuevo sitio web? ¡Nunca ha sido tan fácil mostrarle al mundo lo que le interesa!



**Figura 7.12 Una página de subtemas generada por ChatGPT**

## Resumen

* Una imagen de héroe es una foto o ilustración llamativa que ocupa todo el ancho (y generalmente todo el alto) de la ventana del navegador cuando ingresas por primera vez a una página.

* Puede utilizar ChatGPT para sugerir ideas de escritura, ofrecer consejos para escribir sobre temas específicos y ayudar a investigar temas.

* Para que ChatGPT escriba con su propia voz, proporciónele varios ejemplos de su escritura, pídale que analice las muestras en busca de tono y estilo, y luego pídale que escriba algo que emule su voz al escribir.

* Para obtener mejores resultados, el mensaje de su página debe ser lo más específico posible, incluidos colores, tamaños de fuente y niveles de encabezado.

* Para la página de inicio del sitio web, guarde el HTML generado en el archivo index.html y el CSS generado en el nombre de archivo sugerido por ChatGPT en el código HTML, generalmente styles.css.

* Para cada página de subtema del sitio web, solicite a ChatGPT que cree solo el código HTML y lo guarde en el nombre de archivo que esté usando para la página.

