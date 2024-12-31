# 7 Creación de contenido del sitio

Este capítulo cubre

* Colaborar con ChatGPT para crear y editar contenido
* Cómo hacer que ChatGPT escriba con tu propio estilo
* Cómo obtener ayuda de IA para editar tus textos
* Agregar una imagen hero
* Prompting ChatGPT para crear una página sobre un interés o pasatiempo
* Examinar y personalizar el código de la página web ChatGPT

Como expliqué en el capítulo 1, la G de GPT significa generativo, y significa que puedes usar ChatGPT no solo para tener conversaciones, sino también para crear cosas nuevas. Como has visto hasta ahora en este libro, ese contenido generado puede ser ideas para el título y el eslogan de la página, sugerencias de tipografías que coincidan con el tema de tu página, recomendaciones de esquemas de colores, enlaces, barras de navegación y, por supuesto, el código HTML y CSS para crear la página web final.

Sin embargo, tus ambiciones de generar contenido no tienen por qué limitarse a pequeños fragmentos de texto y código. Si tienes ganas de mostrar tu verdadero yo en la web para que todo el mundo lo vea, una de las mejores formas de hacerlo es escribir sobre un interés o pasatiempo que te fascine o te atraiga. Si no estás seguro de qué escribir o tienes problemas para empezar, este capítulo te muestra cómo incorporar a ChatGPT como colaborador para ayudarte a empezar. Aprenderás a obtener ideas de contenido y sugerencias de redacción generadas por IA, a utilizar la IA para la investigación e incluso a utilizar ChatGPT para escribir con tu voz.

También aprenderá a crear un mensaje detallado que le enviará a ChatGPT para que produzca el código de una página dedicada a un interés o pasatiempo, donde podrá publicar cualquier contenido que usted y ChatGPT hayan creado juntos. Este capítulo también proporciona una explicación detallada del código generado por ChatGPT e incluso brinda algunos consejos para personalizar el código manualmente para que todo quede exactamente como lo desea.

## 7.1 Comprender el proyecto de este capítulo

En este capítulo, creará un sitio web sencillo dedicado a un interés o pasatiempo. Contratará a ChatGPT como asistente de redacción para que lo ayude a generar ideas, investigar y crear los primeros borradores del contenido del sitio. La página de inicio incluirá los siguientes componentes:

* Un elemento de header que incluye lo siguiente:
   * Una imagen que ocupa todo el ancho y la altura de la ventana del navegador.
   * El título del sitio web
   * El lema del sitio web
   * Un elemento de navegación con links a otras páginas del sitio.
* Un elemento main con algún texto introductorio y enlaces a otras páginas del sitio.
* Un elemento footer que incluye un aviso de derechos de autor

La figura 7.1 muestra un ejemplo de la página de inicio de un sitio web de interés creada con código generado por ChatGPT.

![image](https://github.com/user-attachments/assets/df72d84e-f1e7-42c6-9833-18a4c6ed718c)

![image](https://github.com/user-attachments/assets/7d3e0f14-58d8-43ca-8878-882670e53cb2)

![image](https://github.com/user-attachments/assets/cb3a0770-ca3d-4d1e-b707-559b4ceb7fef)


**Figura 7.1 Página de inicio de un sitio web de interés generada por ChatGPT**

Las demás páginas del sitio utilizarán una estructura similar:

* Un elemento de header que incluye lo siguiente:
   * Una imagen hero
   * El título de la página
   * El subtítulo de la página
   * Un elemento de navegación con enlaces a otras páginas del sitio.
* Un elemento main con el texto de la página.
* Un elemento de footer con un aviso de derechos de autor

La figura 7.2 muestra un ejemplo de una página de este tipo. La simplicidad de estas páginas significa que puedes personalizarlas fácilmente para usarlas con cualquier interés, pasatiempo u obsesión que quieras compartir con el mundo.

![image](https://github.com/user-attachments/assets/bf6bf58f-f735-4f97-a8d7-c024071fac5a)

**Figura 7.2 Una página de subtemas**

## 7.2 Generación y edición de texto con ChatGPT

Si no solo tiene ganas de escribir, sino también de compartir lo que escribe con otras personas publicándolo en la web, es posible que le resulte un poco receloso utilizar ChatGPT como asistente de escritura o incluso como una especie de escritor fantasma (en la máquina). Si escribir es importante para usted, también es importante que sea su escritura, no algo creado por una IA.

Sin embargo, nada de eso significa que no puedas usar ChatGPT para parte del trabajo pesado asociado con la escritura. ¿Necesitas algunas ideas para el contenido? ChatGPT puede ayudarte. ¿Necesitas investigar para una publicación? ChatGPT es ideal para eso. ¿Te quedaste frente a una pantalla en blanco? Haz que ChatGPT genere algo, cualquier cosa, y tal vez una oración o incluso una frase de ese texto sea suficiente para despertar tu imaginación. ¿No estás satisfecho con algo que escribiste? Pídele a ChatGPT que lo revise y sugiera mejoras.

En realidad, no hay límite para las formas en que ChatGPT puede actuar como tu asistente personal de escritura. Y, por supuesto, si lo deseas, incluso puedes hacer que ChatGPT escriba todo por ti. Si puedes hacer eso y aún así dormir bien por las noches, bueno, no voy a intentar persuadirte de lo contrario.

### 7.2.1 Cómo hacer que ChatGPT sugiera ideas de escritura

ChatGPT se destaca en muchas tareas, pero una de sus mayores virtudes es sugerir ideas para escribir sobre casi cualquier tema, sin importar lo oscuro o misterioso que sea. Es decir, si tienes una idea general del tema que quieres abordar en tu escritura, ChatGPT puede generar ideas de contenido desde múltiples ángulos.

Debes comenzar tu mensaje asignando un rol a ChatGPT:

```text
You are an expert in [topic] and can generate interesting and creative ideas about [topic] based on the following question.
```

```text
Eres un experto en [topic] y puedes generar ideas interesantes y creativas sobre [topic] basándose en la siguiente pregunta.
```

Reemplazar `[topic]` con una palabra o frase que describa el tema o asunto sobre el que desea escribir.

Ahora, agrega una pregunta que hará que ChatGPT genere algunas ideas para una publicación. Aquí tienes algunos ejemplos para empezar:

```text
What are the pros and cons of [topic]?
What are the top ten features of [topic]?
What are five things everyone needs to know about [topic]?
What are some common myths about [topic]?
How does a beginner get started with [topic]?
What are half a dozen tips and tricks to get the most out of [topic]?
```

```text
¿Cuáles son los pros y contras de [ tema ]?
¿Cuáles son las diez características principales de [ tema ]?
¿Cuáles son las cinco cosas que todo el mundo necesita saber sobre [ tema ]?
¿Cuáles son algunos mitos comunes sobre [ tema ]?
¿Cómo puede un principiante empezar con [ tema ]?
¿Cuáles son media docena de consejos y trucos para aprovechar al máximo [ tema ]?
```

Nuevamente, en cada caso, reemplaza `[topic]` con una palabra o frase que describa el tema o asunto sobre el que quieres escribir. Por ejemplo, la figura 7.3 muestra las ideas que Copilot (en modo Creativo) generó para mí en base a la siguiente indicación:

```text
You are an expert in bread baking and can generate interesting and creative ideas about bread baking based on the following question.
  
How does a beginner get started with bread baking?
```

```text
Eres un experto en la elaboración de pan y puedes generar ideas interesantes y creativas sobre la elaboración de pan basándose en la siguiente pregunta.

¿Cómo puede un principiante iniciarse en la elaboración de pan?
```
  
![image](https://github.com/user-attachments/assets/0cabbf6a-2175-4452-a8f3-4ff076c553be)

**Figura 7.3 Ideas de ChatGPT para comenzar a hornear pan**

Estas son sugerencias excelentes y servirían como punto de partida para una publicación que interese a los principiantes en la elaboración de pan. Tenga en cuenta que es importante considerar las ideas de contenido de ChatGPT como solo el comienzo. Depende de usted desarrollar los detalles para crear una publicación increíble.

### 7.2.2 Generar ideas sobre cómo escribir sobre un tema

En la sección anterior, aprendiste a usar ChatGPT para generar ideas para escribir. Un uso similar de ChatGPT es preguntarle cómo escribir sobre un tema en particular o un enfoque particular sobre un tema.

Como de costumbre, comience su mensaje asignando un rol a ChatGPT:

```text
You are a writing coach and an expert on [topic] and can generate practical and creative advice on how to write about [topic] based on the following question.
```

```text
Eres un coach de escritura y un experto en [ tema ] y puedes generar consejos prácticos y creativos sobre cómo escribir sobre [ tema ] basándose en la siguiente pregunta.
```

Reemplazar `[topic]` con una palabra o frase que describa el tema o asunto que desea explorar a través de la escritura.

A continuación, agrega una pregunta que le pedirá a ChatGPT que sugiera ideas sobre cómo escribir sobre tu tema. A continuación, se muestran algunos ejemplos:

```text
What are the best ways to introduce a beginner to [topic]?
Once someone has learned the basics of [topic], what should I teach them next?
How do I get someone who knows nothing about [topic] excited about the subject?
What are some ways to write engagingly about [topic]?
What types of posts are most suited to writing about [topic]?
```

```text
¿Cuáles son las mejores formas de introducir a un principiante en [ tema ]?
Una vez que alguien ha aprendido los conceptos básicos de [ tema ], ¿qué debo enseñarle a continuación?
¿Cómo puedo lograr que alguien que no sabe nada sobre [ tema ] se entusiasme con el tema?
¿Cuáles son algunas formas de escribir de manera atractiva sobre [ tema ]?
¿Qué tipos de publicaciones son más adecuadas para escribir sobre [ tema ]?
```

Nuevamente, reemplaza `[topic]` en cada ejemplo con texto que describa el tema o asunto de tu escrito. Por ejemplo, la figura 7.4 muestra las ideas de escritura que Copilot (en modo Creativo) generó a partir de la siguiente indicación:

```text
You are a writing coach and an expert on bread baking and can generate practical and creative advice on how to write about bread baking based on the following question.
  
What are some ways to write engagingly about bread baking?
```

```text
Eres un coach de escritura y un experto en panadería y puedes generar consejos prácticos y creativos sobre cómo escribir sobre panadería basándose en la siguiente pregunta.
  
¿Cuáles son algunas formas de escribir de manera atractiva?¿Qué opinas sobre la elaboración del pan?
```

¡Éstas son excelentes sugerencias no sólo para escribir sobre cómo hornear pan, sino también para escribir sobre casi cualquier otra cosa!

![image](https://github.com/user-attachments/assets/10970d60-7e89-4063-97c3-2474340b4ccf)

**Figura 7.4 Consejos de ChatGPT para escribir de forma atractiva sobre la elaboración de pan**

### 7.2.3 Cómo obtener ayuda de ChatGPT para investigar un tema

Los modelos GPT que sustentan ChatGPT se entrenaron con una cantidad de datos imposible de imaginar, lo que significa que saben bastante sobre casi cualquier tema que se te ocurra. Eso hace que ChatGPT sea el asistente de investigación perfecto, ya que puedes pedirle ayuda para explorar cualquier tema sobre el que quieras escribir y recibirás muchos consejos útiles.

A continuación se muestra un mensaje que puede utilizar para solicitar asistencia a ChatGPT para su investigación:

```text
Help me research [topic] for a general audience. I'm interested in A, B, and C. Please provide X, Y, and Z. Also, include any interesting trivia or anecdotes that might be engaging for readers. The goal is to provide a depth of information that is accurate and detailed but also easily understood by a broad audience. Please provide links to your sources.
```

```text
Ayúdame a investigar [ tema ] para un público general. Estoy interesado en A , B y C. Proporciona X , Y y Z. Además, incluye datos curiosos o anécdotas interesantes que puedan resultar interesantes para los lectores. El objetivo es proporcionar una gran cantidad de información que sea precisa y detallada, pero que también sea fácil de entender para un público amplio. Proporciona enlaces a tus fuentes.
```

Como es habitual, `[topic]` se trata de una breve descripción del tema que desea investigar. Esto es lo que representan los demás marcadores de posición:

* `A`, `B`, y `C`: Temas generales relacionados con el tema general.

* `X`, `Y`, y `Z`: Aspectos específicos del tema general.

**TIP** La última oración del mensaje asume que estás usando una versión de ChatGPT que está conectada a la web. Recomiendo encarecidamente una versión conectada a la web para esto porque los enlaces generados te permiten verificar los resultados de ChatGPT y también te brindan más material para tu investigación.

He aquí un ejemplo:

```text
Help me research the history of coffee for a general audience. I'm interested in the discovery of coffee, its spread across the globe, and its cultural impact in different societies. Please provide key historical figures and events, notable varieties of coffee, and the evolution of coffee-drinking habits over time. Also, include any interesting trivia or anecdotes that might be engaging for readers. The goal is to provide a depth of information that is accurate and detailed but also easily understood by a broad audience. Please provide links to your sources.
```

```text
Ayúdame a investigar la historia del café para un público general. Me interesa el descubrimiento del café, su difusión por todo el mundo y su impacto cultural en diferentes sociedades. Proporciona figuras y eventos históricos clave, variedades notables de café y la evolución de los hábitos de consumo de café a lo largo del tiempo. Además, incluye cualquier dato curioso o anécdota interesante que pueda resultar interesante para los lectores. El objetivo es proporcionar una gran cantidad de información que sea precisa y detallada, pero también fácil de entender para un público amplio. Proporciona enlaces a tus fuentes.
```

La figura 7.5 muestra la última parte de una respuesta excepcionalmente larga a la pregunta anterior de Copilot (en modo creativo). La pregunta asume que estás escribiendo para un público general, pero, por supuesto, debes modificarla según el lector al que te dirijas.

![image](https://github.com/user-attachments/assets/e5cceeb8-d8c0-4f2b-86e3-7905a288d0b5)

**Figura 7.5 La última parte de la respuesta de ChatGPT a una solicitud de ayuda para investigar la historia del café.**

### 7.2.4 Cómo hacer que ChatGPT escriba con tu propia voz

Un objetivo difícil de alcanzar de la escritura generada por ChatGPT es lograr que el modelo produzca una prosa que suene como la tuya. Seguro, ChatGPT puede generar fácilmente (y, a menudo, de manera divertida) prosa al estilo de escritores famosos como James Joyce, Emily Dickinson y Dr. Seuss. Esto se debe a que ChatGPT fue entrenado (casi con certeza) con grandes muestras de los escritos de esos autores. Sin embargo, es poco probable que ChatGPT tenga la menor idea de cómo escribes .

Sin embargo, esto no es un problema, ya que puedes "entrenar" a ChatGPT para que escriba como tú. ¿Cómo? Dándole a ChatGPT varias muestras de tu escritura, pidiéndole que analice el tono y el estilo de esas muestras y luego pidiéndole que escriba algo nuevo con la misma voz.

Aquí está el mensaje:

```text
You are an experienced ghostwriter. Given several examples of an author's writing, you are skilled at detecting the tone and style of the writing and emulating that writer's voice to generate new writing. 
  
Below are several writing samples, with each sample between sets of triple quotation marks.
  
Examine the samples to determine the writer's unique voice.
  
Emulate the writer's voice to generate X.
  
"""
Writing sample #1
"""
  
"""
Writing sample #2
"""
  
"""
Writing sample #3
"""
  
"""
Writing sample #4
"""
  
"""
Writing sample #5
"""
```

```text
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
```

Reemplace cada instancia de `Writing sample #n` con una muestra de su escritura.

**Nota**: Lo ideal es que sus muestras de escritura utilicen el mismo estilo y tono que desea utilizar para el texto que desea crear.

No es necesario que incluyas las cinco muestras. Puedes usar solo dos o tres o incluso una sola muestra larga, pero recuerda que cuanto más texto proporciones, más preciso será el análisis que proporcione ChatGPT y más acertado será el mensaje.

**TIP**: Si tienes un autor favorito cuyo estilo de escritura admiras y te gustaría emular hasta cierto punto, inclúyelo en tu mensaje. Por ejemplo, para pedirle a ChatGPT que incluya un poco del estilo y el tono de Eudora Welty, agrega lo siguiente a tu mensaje: `Please also include about 10 percent of the tone and style of Eudora Welty`.

En el prompt, reemplaza X por una breve descripción del texto que quieres que ChatGPT genere. A continuación, se muestra un ejemplo:

```text
You are an experienced ghostwriter. Given several examples of an author's writing, you are skilled at detecting the tone and style of the writing and emulating that writer's voice to generate new writing. 
  
Below are several writing samples, with each sample between sets of triple quotation marks.
  
Examine the samples to determine the writer's unique voice.
  
Emulate the writer's voice to generate a satirical news story based on the multiple pronunciations of the letters "ough".
  
"""
Researchers from Aalborg University announced today that they have finally discovered the long sought-after Soup-Nuts Continuum. Scientists around the world have been searching for this elusive item ever since Albert Einstein's mother-in-law proposed its existence in 1922. "Today is an incredible day for the physics community and for humanity as a whole," said senior researcher Lars Grüntwerk. "Today, for the first time in history, we are on the verge of knowing everything from soup to, well, you know, nuts."
"""
  
"""
SCHECHENECTADY, NY--After a long and tempestuous marriage, the two senses of the word "oversight" have petitioned for a divorce. Citing irreconcilable differences, the "responsible" sense of the word ("Watchful care or management") and the "irresponsible" sense ("An omission or error") have separated. "It just got to be too much after a while," said responsible oversight. "The other oversight can't be trusted with even the smallest task. It's 'Oops!' this and 'Sorry!' that. I believe in being careful and in making sure that things get done right, so I just can't stand to live with such neglect."
"""
  
"""
AIEA, Hawaii--Former United Nations Secretary General Boutros-Boutros Ghali and current United Nations Undersecretary for Alphabet Mobilization Yada-Yada Yada announced today the formation of the United Nations International Vowel Assistance Committee. UNIVAC's mandate is "to help the vowel-deprived wherever they may live and to fund vowel relief efforts in the hardest hit areas." "We have a good stockpile of a's, e's, and o's," said Ng Ng, UNIVAC's Letter Distribution Officer. "We hope to have an adequate supply of i's and u's over the next six months. In the meantime, we can use our extra y's in a pinch."
"""
  
"""
KALAMAZOO, Michigan--A group of disgruntled grammarians calling themselves "Mad, We Are, As Hell" has filed a number of civil lawsuits over the past few weeks. The targets of these suits are writers, raconteurs, and professional man-in-the-street interviewees who, they claim, are inveterate violators of the rules of grammar. The group's spokesperson, Millicent Peevish, Head Shusher at the Kalamazoo District Library, said the grammarians could no longer sit back and allow "the splitting of blameless infinitives and the ending of sentences with evil, evil prepositions." A previous campaign -- called Shock and Appalled -- that focused on writing testy letters to the editors of various local publications, had no discernible effect.
"""
  
"""
In a scathing report released today, communications experts have declared that the instant messages teenagers exchange with each other are in reality nothing but gibberish. U.S. Chatmaster General Todd Dood, with technical help from the National Security Agency, examined thousands of instant messages. It has long been thought that teen instant messages contained abbreviations (such as LOL for "laughing out loud" and MAIBARP for "my acne is becoming a real problem"), short forms (such as L8R for "later" and R2D2 for "R2D2"), and slang (such as whassup for "what's up" and yo for "Hello, I am pleased to meet your acquaintance. Do you wish to have a conversation?").
"""
```

```text
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
```

La Figura 7.6 muestra la historia que GPT-4 (Copiloto en modo creativo) generó basándose en mis muestras de escritura.

![image](https://github.com/user-attachments/assets/fa4082c6-d2b8-48ff-bdfd-cbbcb9ac4ed5)

**Figura 7.6 La historia generada por Copilot en modo Creativo**

Este es un primer intento bastante bueno: coincide con el tono y el estilo de los ejemplos de escritura, es una idea narrativa decente y tiene un humor genuino. Sin embargo, está lejos de ser perfecto:

* Contiene algunos errores, como incluir “Pittsburgh” como ejemplo de una palabra que utiliza las letras “ough”.

* Algunos textos son torpes y será necesario reescribirlos considerablemente para ponerlos a punto.

* El uso de nombres reales (como el de la jueza Sonia Sotomayer) en una pieza satírica como ésta es una mala elección. Una mejor opción sería utilizar nombres inventados que jueguen con las letras “ough”.

Este tipo de problemas son comunes con los textos generados por IA, por lo que siempre debes revisar cuidadosamente todo lo creado por ChatGPT y estar preparado para reescribir bastante.

### 7.2.5 Reescritura del texto del post 

Después de haber escrito un texto, es posible que se pregunte si su prosa podría mejorarse de alguna manera para que sea más divertida, más concisa, más detallada, más fácil de entender, más académica, etc. Afortunadamente, siempre que su texto esté en línea o en un formato que pueda cargar en un navegador web (como un archivo HTML, un archivo de texto o un archivo PDF), ChatGPT (en concreto, la aplicación Microsoft Copilot) estará encantado de ayudarle. A continuación, le indicamos cómo:

   1. En el navegador Microsoft Edge, abra la barra lateral de Copilot.

   2. Navegue hasta la página o abra el archivo que contiene el texto que desea reescribir.

   3. Seleccione el texto que desea reescribir.

   4. En la barra lateral, verá el mensaje `Send selected or copied text to chat?`, como se muestra en la figura 7.7.

![image](https://github.com/user-attachments/assets/e06d68d2-bc48-4d6a-9111-75fd1adfb635)

**Figura 7.7 Seleccione algún texto en la página actual y Copilot le preguntará si desea enviarlo a la IA.**

   5. Haga clic en Enviar. Copilot le preguntará qué desea hacer con el texto.

   6. Escriba sus instrucciones. A continuación, se muestran algunos ejemplos:

   — Hazlo más divertido

   — Hazlo más conciso

   — Hazlo más fácil de entender

   — Hazlo más académico

   — Reescríbalo para un niño de 10 años.

   7. Pulse Enter o Return. Copilot revisará el texto seleccionado según las instrucciones que proporcionó en el paso 6.

La figura 7.8 muestra el resultado cuando le pedí a Copilot que reescribiera el texto seleccionado que se muestra en la figura 7.7 para un niño de 10 años.

![image](https://github.com/user-attachments/assets/c1be5248-d9b5-4eae-9005-552cc7c65bb1)

**Figura 7.8 El texto seleccionado de la figura 7.7, reescrito para un niño de 10 años.**

Es posible que hayas notado algo en todos los ejemplos de texto que he generado con ChatGPT hasta ahora. Así es: ¡no hay etiquetas HTML! Son importantes, así que aprenderás a incluirlas en tu texto generado con ChatGPT en la siguiente sección.

### 7.2.6 No olvides los tags HTML

Independientemente del texto que crees en colaboración con ChatGPT, al final el texto se encontrará en una página web. Esto significa que el texto debe estar estructurado con las etiquetas HTML adecuadas, en particular para los encabezados y párrafos del texto. Para que ChatGPT haga esto por ti, agrega lo siguiente al final de tu prompt de redacción:

```text
Please add HTML tags to the text, but don't generate the code for an entire web page.
```

```text
Agregue etiquetas HTML al texto, pero no genere el código para una página web completa.
```

Una vez que el texto de su sitio esté listo para publicar, es momento de que ChatGPT lo ayude a crear su home page. Aprenderá cómo hacerlo en la siguiente sección.

## 7.3 Creación de la home page

Como este proyecto es un sitio web de varias páginas, es mejor crear los componentes del sitio en etapas. El proceso básico se resume aquí:

1. Solicite a ChatGPT que genere el código HTML para la home page del sitio web.

2. Indique a ChatGPT que genere el código CSS para el estilo del sitio web. Tenga en cuenta que es mejor combinar estos dos primeros pasos en un solo mensaje.

3. Para cada una de las demás páginas de su sitio, solicite a ChatGPT que genere el código HTML para esa página. En particular, el prompt para cada una de las demás páginas del sitio debe incluir lo siguiente:

   1. Una instrucción para utilizar el mismo archivo CSS en el que guardó el CSS generado en el paso 2

   2. Una instrucción para no generar estilos adicionales, particularmente estilos en línea (es decir, código CSS insertado directamente en etiquetas HTML)

Antes de llegar a todo eso, tómese un minuto para familiarizarse con la nueva tecnología de página web presentada en este capítulo.

### 7.3.1 Trabajar con imágenes hero

La única tecnología nueva para páginas web que aprenderá en este capítulo es la imagen principal: una foto o ilustración llamativa que ocupa todo el ancho (y normalmente todo el alto) de la ventana del navegador cuando accede por primera vez a una página. La figura 7.9 muestra un ejemplo de página web que incluye una imagen principal.

![image](https://github.com/user-attachments/assets/9e85daae-be8c-48d2-97c6-e7d416f22eff)

**Figura 7.9 Una página web con una imagen hero**

A continuación se muestran algunos consejos a tener en cuenta al utilizar una imagen destacada:

* El asunto de la imagen debe ser relevante al tema de tu página.
* La imagen debe ser dramática o llamativa de alguna manera.
* Utilice una imagen de alta calidad y sin distorsiones como la pixelación. Si utiliza una fotografía, debe estar bien compuesta y bien iluminada.
* No utilice un archivo de imagen que sea demasiado pequeño, ya que se distorsionará cuando el navegador lo amplíe para que se ajuste a la ventana. Una imagen de 1200 píxeles de ancho con una relación de aspecto (es decir, la relación entre el ancho y la altura) de 16:9 es el tamaño ideal para la mayoría de las pantallas más grandes (y para las pantallas de dispositivos más pequeños en modo horizontal).
* Utilice una imagen que no sea tan recargada que el texto se pierda o sea ilegible.
* Como verás un poco más adelante, puedes indicarle a ChatGPT que oscurezca un poco la imagen, así que no te preocupes si tu imagen aparece demasiado clara para tu texto.
* Si no tiene una imagen adecuada, puede pedirle a DALL-E o al Creador de imágenes de Copilot que genere una para usted (como describí en el capítulo 5).

Para que ChatGPT agregue una imagen hero a una página, el mensaje debe incluir una instrucción similar a la siguiente:

```text
Include a header that uses the file hero.jpg as a hero image.
```

```text
Incluya un encabezado que utilice el archivo hero.jpg como imagen principal.
```

Curiosamente, cuando examinas el código HTML, no verás ninguna referencia al archivo de imagen. Por ejemplo, aquí está el código HTML que crea el header que se muestra en la figura 7.9:

```html
<header>
    <nav>
        <ul>
            <li><a href="index.html">Home</a></li>
            <li><a href="history.html">History</a></li>
            <li><a href="culture.html">Culture</a></li>
            <li><a href="language.html">Language</a></li>
        </ul>
    </nav>
    <h1>Bread in the Bone</h1>
    <p>A half-baked look at the history and culture of bread</p>
</header> 
```

La imagen del hero está incrustada en el elemento `header` en el CSS, como lo muestra esta lista parcial de la regla `header` utilizada para el elemento `header` en la figura 7.9:

```html
header {
    background: url('hero.jpg') no-repeat center center fixed;
    background-size: cover;
}
```

Este código le indica al navegador web que muestre el archivo de imagen `hero.jpg` como fondo del elemento `header` y que la imagen debe cubrir todo el elemento. El uso de una imagen hero es una excelente manera de captar la atención de un visitante desde el principio, por lo que ha sido una de las tendencias de diseño web más populares en los últimos años.

### 7.3.2 Elaboración del prompt para home page

El proyecto de este capítulo es un sitio web dedicado a un interés o pasatiempo. Ya casi está listo para construir la página de inicio de ChatGPT, pero primero debe asegurarse de tener estos elementos:

* Algunos o todos los siguientes: un logotipo de página, un título y un eslogan.
* Los nombres de los tipos de letra que desea utilizar para los encabezados de página y el texto de la página.
* Las palabras clave de los colores que desea aplicar a los fondos y textos de las páginas.

Consulta el capítulo 3 para obtener más información sobre estos elementos de diseño y cómo solicitar a ChatGPT sugerencias de título, tipo de letra y color.

El punto de partida para el sitio web de su interés o pasatiempo es la página de inicio, para cuya creación puede contar con la ayuda de ChatGPT. Su prompt debe comenzar así:

```text
I want to build a web page for a website home page. I don't know how to code, so I need you to provide the code for me.
  
First, write the HTML code for a web page that includes the following:
```

```text
Quiero crear una página web para la página de inicio de un sitio web. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
```

A continuación, especifique el contenido de su página, incluyendo lo siguiente (consulte la figura 7.10):

* Un encabezado que incluye su imagen principal, título de página, lema y una barra de navegación con enlaces a otras páginas de su sitio.
* Un elemento principal que comienza con un párrafo introductorio que da la bienvenida a los visitantes de su sitio.
* Para cada uno de los subtemas de su sitio, un elemento de sección que incluye un encabezado con el título del subtema, una descripción del subtema y un enlace al subtema.
* Un pie de página que incluye un aviso de derechos de autor

A continuación, solicite a ChatGPT que genere el CSS según el formato que desea para su página:

```text
Second, in a separate file please write the CSS code for the following:
```

```text
En segundo lugar, en un archivo separado, escriba el código CSS para lo siguiente:
```

Especifique el formato, incluido lo siguiente:

* El color de fondo de la página y el color del texto.
* Los tamaños de fuente y colores que desea utilizar para el título de la página, el lema y los enlaces de navegación.
* Las fuentes a utilizar para los encabezados y el texto de la página normal.
* Un ancho máximo para el elemento principal. Esto evita que las líneas de texto sean demasiado largas. Una longitud máxima de 800 px es adecuada para la mayoría de las páginas.

![image](https://github.com/user-attachments/assets/44c48e9e-e39a-46c7-a962-9bea610984dd)

**Figura 7.10 Las secciones de la página de inicio del sitio de interés**

A continuación se muestra un ejemplo de mensaje para mi propia página de inicio:

```text
I want to build a website home page. I don't know how to code, so I need you to provide the code for me.
  
First, write the HTML code for a web page that includes the following:
 * A header that uses the file hero.jpg as a hero image.
 * The header also includes the title "Bread in the Bone" and the tagline "A half-baked look at the history and culture of bread".
 * The header should also include four links in the upper-right corner:
   * The text "Home" that links to the file "index.html".
   * The text "History" that links to the file "history.html".
   * The text "Culture" that links to the file "culture.html".
   * The text "Language" that links to the file "language.html".
 * A main element that includes the following five elements:
   * An introductory paragraph that includes the text "Welcome to Bread in the Bone, where I, a bread baker, a bread eater, and an unabashed bread nerd, try to make sense of the historical, cultural, and linguistic significance of that most humble of home staples: the loaf of bread. It's the greatest thing since, well, you know..."
  * A second paragraph that consists of the text "This site is divided into three sections:"
  * The second-level heading "History" followed by a paragraph that includes the text "A potted and probably not very accurate history of bread, from its ancient origins to today's ancient grains." Then the text "Check it out." as a link to "history.html".
  * The second-level heading "Culture" followed by a paragraph that includes the text "A remarkably shallow examination of the cultural significance of bread, from its religious meanings to its social uses." Then the text "Read it." as a link to "culture.html".
  * The second-level heading "Language" followed by a paragraph that includes the text "A not-all-that-deep dive into the linguistic roots and uses of the word bread, from its etymology to its varied metaphors." Put the word "bread" in italics. Then add the text "Go there." as a link to "language.html".
 * A footer element that includes the Copyright symbol, followed by the current year, followed by "Paul McFedries".
  * In the page head section, include the tag <meta charset="utf-8">.
  
Second, in a separate file write the CSS code for the following:
 * The page background color is wheat.
 * The hero image covers the entire browser window.
 * Add a linear gradient to the header background to darken the hero image slightly.
 * Make all the header text white.
 * Make the title and tagline centered both horizontally and vertically.
 * Make the title 72px.
 * Make the tagline 36px.
 * Make the header links 24px.
 * Style the headings with size 48px, no bottom margin, the color saddlebrown, and the Raleway typeface from Google Fonts.
 * Style the rest of the page text with size 24px, a 20px bottom margin, and the Lato typeface from Google Fonts.
 * Style the main element's links with the color saddlebrown.
 * The main section has 25px padding all around and a maximum width of 800px.
 * The footer has a top border.
```

```text
Quiero crear una página de inicio para un sitio web. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
 * Un encabezado que utiliza el archivo hero.jpg como imagen hero.
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
 *La imagen del hero cubre toda la ventana del navegador.
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
```

ChatGPT debe crear primero el código HTML, que puedes copiar y pegar y guardar en un archivo llamado `index.html`. En ese código, deberías ver una línea cerca de la parte superior similar a la siguiente:

```html
<link rel="stylesheet" type="text/css" href="styles.css">
```

Este código le indica al navegador web que busque el código CSS en un archivo llamado `styles.css`, por lo que tu próxima tarea es copiar el código CSS generado, pegarlo en un archivo y guardarlo como `styles.css` (o cualquier nombre que veas en la etiqueta `<link>`). Asegúrate de guardar `styles.css` en la misma carpeta que tu archivo `index.html`. También debes copiar tu archivo de imagen principal en la misma carpeta. Consulta el apéndice A para obtener más información sobre cómo trabajar con archivos de páginas web.

Envié este mensaje a GPT-4 mediante la aplicación ChatGPT de OpenAI. El código generado generó la página que se muestra en la figura 7.11.

![image](https://github.com/user-attachments/assets/f177c4aa-8447-480f-88c6-69d785c8dbc6)

**Figura 7.11 La página de inicio generada por ChatGPT**

Si te gusta la home page que ChatGPT creó para ti, puedes saltarte el resto de esta sección y pasar a las otras páginas (consulta “Creación de indicaciones para las otras páginas del sitio”). Sin embargo, si quieres saber un poco más sobre el código que ChatGPT generó, la siguiente sección te ofrece una visión más detallada.

## 7.4 Examinar el código de la home page

Voy a darles una descripción general breve y no demasiado técnica del código de la home page que resultó de mi prompt de la sección anterior (esa página de inicio se muestra en la figura 7.11).

**Nota**: El código HTML y CSS generado para mi página de diario en línea están disponibles en el sitio web de este libro ( www.manning.com/books/build-a-website-with-chatgpt ) y en el repositorio de GitHub del libro: https://github.com/paulmcfe/websites-with-chatgpt.

Cada versión de ChatGPT debe generar código HTML y CSS que sea al menos similar a lo que se muestra en las siguientes dos secciones, por lo que mis anotaciones de código deberían ayudarlo a comprender lo que sucede bajo el capó.

### 7.4.1 Examinar el HTML

El código HTML que ChatGPT generó para la página de inicio del sitio web de mi interés se muestra aquí:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">                                              ①
    <title>Bread in the Bone</title>
    <link href="https://fonts.googleapis.com/css2?
        family=Lato:wght@700&family=Raleway:wght@400&
        display=swap"rel="stylesheet">                                  ②
    <link rel="stylesheet" href="styles.css">                           ③
</head>
<body>
    <header>                                                            ④
        <nav>                                                           ④⑤
            <ul>                                                        ④⑤
                <li><a href="index.html">Home</a></li>                  ④⑤
                <li><a href="history.html">History</a></li>             ④⑤
                <li><a href="culture.html">Culture</a></li>             ④⑤
                <li><a href="language.html">Language</a></li>           ④⑤
            </ul>                                                       ④⑤
        </nav>                                                          ④⑤
        <h1>Bread in the Bone</h1>                                      ④⑥
        <p>                                                             ⑦
            A half-baked look at the history                            ⑦
            and culture of bread                                        ⑦
        </p>                                                            ⑦⑧
    </header>                                                           ⑧
  
    <main>                                                              ⑨
        <p>                                                             ⑨⑩
            Welcome to Bread in the Bone, where I, a bread baker, a     ⑨⑩
            bread eater, and an unabashed bread nerd, try to make       ⑨⑩
            sense of the historical, cultural, and linguistic           ⑨⑩
            significance of that most humble of home staples: the loaf  ⑨⑩
            of bread. It's the greatest thing since, well, you know...  ⑨⑩
        </p>                                                            ⑨⑩
        <p>This site is divided into three sections:</p>                ⑨
    
        <section>                                                       ⑪⑫
            <h2>History</h2>                                            ⑪⑫
            <p>                                                         ⑪⑫
                A potted and probably not very accurate history of      ⑪⑫
                bread, from its ancient origins to today's ancient      ⑪⑫
                grains. <a href="history.html">Check it out.</a>        ⑪⑫
            </p>                                                        ⑪⑫
        </section>                                                      ⑪⑫
    
        <section>                                                       ⑫
            <h2>Culture</h2>                                            ⑫
            <p>                                                         ⑫
                A remarkably shallow examination of the cultural        ⑫
                significance of bread, from its religious meanings      ⑫
                to its social uses. <a href="culture.html">Read it.</a> ⑫
            </p>                                                        ⑫
        </section>                                                      ⑫
    
        <section>                                                       ⑫
            <h2>Language</h2>                                           ⑫
            <p>                                                         ⑫
                A not-all-that-deep dive into the linguistic roots      ⑫
                of bread, from its etymology to its varied metaphors.   ⑫
                <a href="language.html">Go there.</a>                   ⑫
            </p>                                                        ⑫
        </section>                                                      ⑫
    </main>                                                             ⑫
  
    <footer>                                                            ⑬
        &copy; 2023 Paul McFedries                                      ⑬
    </footer>                                                           ⑬
</body>
</html> 
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
<link rel="stylesheet" href="styles.css">
```

Esta etiqueta le dice al navegador web dónde encontrar el código CSS, que describo en la siguiente sección.

### 7.4.2 Examinando el CSS

El código CSS generado por ChatGPT para la página de inicio del sitio web de mi interés se muestra aquí:

```css
* {                                                            ①
    margin: 0;                                                 ①
    padding: 0;                                                ①
    box-sizing: border-box;                                    ①
}                                                              ①
body {                                                         ②
    background: wheat;                                         ②
    font-family: 'Lato', serif;                                ②
    font-size: 24px;                                           ②
    color: #333;                                               ②
}                                                              ②
header {
    background: url('hero.jpg') no-repeat center center fixed; ③
    background-size: cover;                                    ③
    color: white;
    display: flex;                                             ④
    flex-direction: column;                                    ④
    justify-content: center;                                   ④
    align-items: center;                                       ④
    height: 100vh;                                             ④
    position: relative;
    background-image:                                          ⑤
        linear-gradient(rgba(0, 0, 0, 0.5),                    ⑤
        rgba(0, 0, 0, 0.5)),                                   ⑤
        url('hero.jpg');                                       ⑤
}
nav ul {                                                       ⑥
    list-style-type: none;                                     ⑥
    display: flex;                                             ⑥
    gap: 20px;                                                 ⑥
    position: absolute;                                        ⑥
    top: 20px;                                                 ⑥
    right: 30px;                                               ⑥
}                                                              ⑥
nav a {                                                        ⑦
    color: white;                                              ⑦
    font-size: 24px;                                           ⑦
    text-decoration: none;                                     ⑦
}                                                              ⑦
nav a:hover {                                                  ⑧
    text-decoration: underline;                                ⑧
}                                                              ⑧
.title-container {
    text-align: center;
}
h1 {
    font-size: 72px;                                           ⑨
    font-family: 'Raleway', sans-serif;                        ⑨
    margin-bottom: 10px;
}
header p {
    font-size: 36px;                                           ⑩
}
h2 {
    color: saddlebrown;                                        ⑪
    font-size: 48px;                                           ⑪
    font-family: 'Raleway', sans-serif;                        ⑪
    margin-top: 30px;
}
main p {
    margin-bottom: 20px;                                       ⑫
}
main {
    padding: 25px;                                             ⑬
    max-width: 800px;                                          ⑬
    margin: 0 auto;                                            ⑬
}
a {
    color: saddlebrown;                                        ⑭
    text-decoration: none;                                     ⑭
}
a:hover {
    text-decoration: underline;                                ⑮
}
footer {
    margin-top: 50px;                                          ⑯
    text-align: center;                                        ⑯
    padding: 20px 0;                                           ⑯
    border-top: 1px solid black;                               ⑯
}
```

① Restablece algunos estilos

② Diseña el color de fondo de la página, la fuente, el tamaño de fuente y el color del texto.

③ Configura la imagen del hero para que llene la ventana del navegador

④ Centra el texto del encabezado

⑤ Oscurece la imagen del hero para que el texto sea más fácil de leer.

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

### 7.4.3 Personalización de la home page

Si no te gusta la home page que resulta del código generado por ChatGPT, puedes modificar el mensaje y volver a intentarlo. Sin embargo, si solo quieres hacer algunos pequeños cambios, considera editar el código manualmente.

Primero, aquí hay algunas sugerencias de personalización para el código HTML:

* En el encabezado, puedes editar el título o el eslogan. Solo asegúrate de no editar ni eliminar las etiquetas HTML asociadas: `<h1>` y `</h1>` para el título, y `<p>` y `</p>` para el eslogan.

* En el encabezado, edite el texto del enlace y el nombre del archivo del enlace según sea necesario para los archivos de su sitio web.

* Edite los elementos `section`, ajustando el encabezado, la descripción y el enlace según sea necesario.

* Para agregar una nueva sección, copie una sección existente (es decir, todo lo que se encuentre entre y incluyendo un solo par de etiquetas `<section>` y `</section>`), pegue el código donde lo desee en el elemento `main` (es decir, entre las etiquetas `<main>` y `</main>`) y luego ajuste el encabezado, la descripción y el enlace. (Consulte el capítulo 6 para obtener instrucciones más detalladas sobre cómo agregar un nuevo elemento `section`).

* En la sección de pie de página del código HTML, puedes agregar enlaces a tus cuentas de redes sociales, como describí en el capítulo 4.

A continuación se muestran algunas ideas de personalización para el código CSS:

* Para establecer la oscuridad de la imagen del hero, ChatGPT usa el siguiente código:

```css
linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)) 
```

Puedes controlar la oscuridad ajustando los números finales en las dos funciones `rgba`(los valores `0.5` en este código). La primera función `rgba` controla la oscuridad de la mitad superior de la imagen y la segunda función `rgba` controla la oscuridad de la mitad inferior. Utiliza valores más cercanos a `0` para una imagen más clara y más cercanos a `1` para una imagen más oscura. Aquí tienes un ejemplo más oscuro:

```css
linear-gradient(rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0.75))
```

* Para darle más espacio a tu texto, crea un espacio extra entre cada línea agregando la declaración `line-height: 1.5;`men algún lugar de la regla del código CSS body:

```css
body {
    background: wheat;
    font-family: 'Lato', serif;
    font-size: 24px;
    color: #333;
    line-height: 1.5;
} 
```

* Si desea que su página tenga un ancho máximo diferente, busque la regla `main` en el código CSS y cambie el valor `max-width` a algo distinto de `800px`. En el siguiente ejemplo, he cambiado el ancho máximo a `960px`:

```css
main {
    padding: 25px;
    max-width: 960px;
    margin: 0 auto;
}
```

* Para cualquier valor de color, puede cambiar el color existente a una palabra clave de color diferente.

* Para cualquier valor de tamaño de fuente, puede cambiar el número para aumentar o disminuir el tamaño de la fuente. Solo asegúrese de dejar la unidad `px` en su lugar.

* Para cualquier valor de margen o padding, puede cambiar el número para aumentar o disminuir el padding o los márgenes. En cada caso, asegúrese de dejar la unidad `px` en su lugar.

* Para que el código de tu página sea más accesible, considera convertir todas las medidas en px a medidas en rem. 1 rem equivale de manera predeterminada a 16 px, por lo que 20 px son 1,25 rem, 24 px son 1,5 rem, 32 px son 2 rem, 48 px son 3 rem, y así sucesivamente. La unidad rem es más accesible porque mide los tamaños de fuente en relación con el tamaño de fuente predeterminado que el usuario del navegador ha definido en la configuración de su navegador.

## 7.5 Creación de prompts para las demás páginas del sitio

Si bien es posible que el sitio web de tu interés o pasatiempo conste de una sola página, es mucho más probable que tengas varias páginas, una para cada subtema del tema principal de tu sitio. Si ese es el caso, tu siguiente tarea es solicitarle a ChatGPT el código para crear las demás páginas.

Afortunadamente, estas otras páginas tendrán una estructura muy similar a la de tu página de inicio, con la única diferencia de que el elemento `main` almacenará los encabezados y el texto de cada página. Todo esto significa que el prompt para cada página de subtema será muy similar al mensaje para tu página de inicio. Ten en cuenta también que no necesitas ningún CSS nuevo para estas páginas de subtemas, por lo que puedes omitir la parte CSS del mensaje.

A continuación se muestra un mensaje genérico que puedes utilizar:

```text
I want to build a website page. I don't know how to code, so I need you to provide the code for me.
  
Write the HTML code for a web page that includes the following:
 * A header element that includes the title "[page title]" and the tagline "[page tagline]".
 * The header should also include the following links in the upper-right corner:
[Copy your home page links here]
* A main element that includes the text between triple quotation marks.
 """
[page content goes here]
 """
 * A footer element that includes the Copyright symbol, followed by the current year, followed by "[your name]".
 * In the page head section, include the tag <meta charset="utf-8">.
 * In the page head section, include a reference to a stylesheet file named "styles.css".
 * In the page head section, include a reference to the Google fonts X and Y.
 * Do not add any inline styles.
```

```text
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
```

Tenga en cuenta la instrucción final a ChatGPT de no agregar estilos en línea, que se refiere al código CSS agregado directamente a una etiqueta HTML. En ausencia de instrucciones relacionadas con CSS, ChatGPT tiene una tendencia a insertar algunas sugerencias de formato en forma de estilos en línea. Debido a que todo el estilo que necesita ya está presente en su archivo `styles.css`, debe indicarle a ChatGPT que no agregue ningún estilo nuevo que pueda estropear sus páginas.

La figura 7.12 muestra una página de ejemplo generada por ChatGPT para el sitio de mis intereses. Cualquiera sea su interés o pasatiempo, ¿por qué no solicitar la ayuda de ChatGPT para compartir su entusiasmo con amigos, familiares y cualquier persona que visite su nuevo sitio web? ¡Nunca ha sido tan fácil mostrarle al mundo lo que le interesa!

![image](https://github.com/user-attachments/assets/dea9174e-37a5-414d-a3ee-b950f5f391b5)

**Figura 7.12 Una página de subtemas generada por ChatGPT**

## Resumen

* Una imagen hero es una foto o ilustración llamativa que ocupa todo el ancho (y generalmente todo el alto) de la ventana del navegador cuando ingresas por primera vez a una página.

* Puede utilizar ChatGPT para sugerir ideas de escritura, ofrecer consejos para escribir sobre temas específicos y ayudar a investigar temas.

* Para que ChatGPT escriba con su propia voz, proporciónele varios ejemplos de su escritura, pídale que analice las muestras en busca de tono y estilo, y luego pídale que escriba algo que emule su voz al escribir.

* Para obtener mejores resultados, el mensaje de su página debe ser lo más específico posible, incluidos colores, tamaños de fuente y niveles de encabezado.

* Para la página de inicio del sitio web, guarde el HTML generado en el archivo `index.html` y el CSS generado en el nombre de archivo sugerido por ChatGPT en el código HTML, generalmente `styles.css`.

* Para cada página de subtema del sitio web, solicite a ChatGPT que cree solo el código HTML y lo guarde en el nombre de archivo que esté usando para la página.
