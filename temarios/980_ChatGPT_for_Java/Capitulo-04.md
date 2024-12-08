# 4. IA multimodal: creación de un visualizador de podcasts con Whisper y DALL·E 3
Bruce Hopkins 1  
(1)
Beaverton, Oregón, Estados Unidos
 
Ahora, introduzcamos un nuevo término: IA multimodal . En términos muy simples, los modelos de IA generativa pueden crear contenido en uno de cuatro formatos:
Texto

Audio

Imágenes

Video

Cada uno de esos formatos es un modo . La IA multimodal es el proceso de utilizar varios modelos de IA juntos para generar (o comprender) contenido donde la entrada es un tipo de modo y la salida es un tipo de modo diferente.

Tomemos como ejemplo el modelo Whisper de OpenAI . Si le proporcionamos audio, es capaz de crear una transcripción de todo lo que se dice en texto.Lo mismo se aplica a DALL⋅E. Si le proporcionas un mensaje de texto, puede generar una imagen de lo que has descrito.

En este capítulo, llevaremos la IA multimodal al siguiente nivel. Como ávido oyente de podcasts, a menudo me he preguntado cómo se verían el paisaje, las imágenes, los personajes, el tema o el fondo mientras escuchaba una historia muy envolvente en formato de audio.

Vamos a crear un visualizador de podcasts utilizando varios modelos de OpenAI. Hay algunos pasos involucrados, pero los resultados finales son sorprendentes. Mientras escuchaba un podcast sobre un tipo que cocinaba cosas increíbles con tofu (no lo critiques hasta que lo pruebes), el visualizador de podcasts mostró la imagen de la Figura 4-1 .

Figura 4-1El resultado generado por IA de la visualización de un podcast sobre tofu utilizando los modelos GPT-4, Whisper y DALL·E
Para que el código del Podcast Visualizer sea fácil de seguir, haremos las cosas por separado en los siguientes tres pasos:
Paso 1: Tome un episodio de podcast y utilice el modelo Whisper para obtener una transcripción.

Paso 2: Tome la transcripción resultante y utilice el modelo GTP-4 para describir los aspectos visuales de lo que se está discutiendo en el episodio del podcast.

Paso 3: Tome la descripción resultante y utilice el modelo DALL⋅E para generar una imagen.

El código presentado aquí en este capítulo tiene toneladas de usos prácticos, por ejemplo:
Si simplemente tienes curiosidad sobre cómo podrían verse las cosas en un episodio de podcast (que siempre es mi caso), puedes obtener una imagen visual representativa simple para asociarla con lo que estás escuchando.

Para las personas con problemas de audición, es muy fácil convertir un podcast o un programa de radio en una presentación de diapositivas con imágenes. Esto mejora enormemente la accesibilidad del contenido.

Para los podcasters, ahora pueden tener una forma sencilla de agregar una imagen o un elemento visual a cada uno de sus episodios. Esto es útil ya que los reproductores de podcasts como Apple Podcasts y Spotify permiten a los podcasters mostrar una sola imagen para asociarla con un episodio individual. Esto puede ayudar a generar interacción con sus oyentes.

Presentamos el modelo Whisper de OpenAI
Ahora vamos a introducir otro término nuevo: Reconocimiento automático de voz (ASR, por sus siglas en inglés) . El consumidor medio está muy familiarizado con esta tecnología debido a su integración en teléfonos móviles (por ejemplo, Siri para el iPhone) y altavoces inteligentes (por ejemplo, cualquier dispositivo Alexa). En esencia, la tecnología ASR convierte el lenguaje hablado en texto.

Susurroes el modelo de reconocimiento de voz de OpenAI y su precisión es sorprendentemente alta. El listado 4-1 es una transcripción de un episodio del popular podcast en español de DuoLingo, que hace que el idioma español sea fácil de entender para los oyentes angloparlantes al combinar el inglés y el español en una historia narrativa entrelazada. La transcripción se generó utilizando el modelo Whisper.
...Soy Martina Castro. En cada episodio te traemos historias fascinantes y reales para ayudarte a mejorar tu comprensión auditiva en español y obtener nuevas perspectivas sobre el mundo. El narrador utilizará un español intermedio y yo intervendré para dar contexto en inglés. Si te pierdes algo, siempre puedes volver atrás y escucharlo de nuevo. También ofrecemos transcripciones completas en podcast.duolingo.com.
Mientras crecía, Linda se sentía fascinada por su abuela, Erlinda. Erlinda era una curandera, una persona que administra remedios para enfermedades mentales, emocionales, físicas o espirituales.
En Guatemala, esta es una práctica que se transmite de generación en generación en la misma familia. El mal de ojo es considerado una enfermedad por muchos guatemaltecos que creen que los humanos tienen el poder de transferir malas energías a otros. Los vecinos llevaban a sus bebés a la abuela de Linda cuando sospechaban que había un desequilibrio energético. Su madre lo llevaba a nuestra casa para curarlo...
Listado 4-1El modelo Whisper realiza reconocimiento de voz para convertir audio en texto
Si alguna vez has trabajado con un sistema de reconocimiento de voz (incluso con tecnologías sofisticadas como Siri y Alexa), sabrás que tiene problemas, por ejemplo:
El reconocimiento de voz tiene problemas con la puntuación
¿Has notado que nadie habla con signos de puntuación? En inglés, usamos cambios de tono o volumen para hacer una pregunta o dar una exclamación. También usamos pausas cortas y largas para las comas y los puntos.

El reconocimiento de voz tiene problemas con palabras y acentos extranjeros.
Dependiendo de a quién le preguntes, hay al menos 170.000 palabras en inglés. Sin embargo, en el inglés conversacional, siempre usamos palabras extranjeras como
Tsunami (origen japonés): Una gran ola marina a menudo causada por un terremoto.

Hors d'oeuvre (origen francés): Un aperitivo.

Lencería (origen francés): Ropa interior o ropa de dormir femenina.

Aficionado (origen español): Alguien que es muy apasionado por una actividad o tema específico.

Piñata (origen español): Una caja de dulces de colores brillantes para que los niños los golpeen sin descanso.

El reconocimiento de voz tiene problemas con los nombres
Ciertos nombres de personas, empresas y sitios web a menudo pueden ser difíciles de escribir y comprender.

El reconocimiento de voz tiene problemas con los homófonos
¿Recuerdas esas palabras que suenan igual pero se escriben y significan de forma diferente? ¡El fantástico editor de este libro las conoce todas!
Quisiera / Madera

Harina / Flor

Dos / Demasiado / Para

Ellos están / allí / sus

Par / Pare / Pera

Frenar / Frenar

Permitido / En voz alta

Como puede ver en el Listado 4-1 , Whisper pudo comprender toda la puntuación del audio, identificar todas las palabras extranjeras (de las cuales había varias) y comprender los nombres, así como el nombre de la empresa (" duolingo ") dentro de una URL. Por supuesto, si se dio cuenta, también pudo comprender la diferencia entre“madera” y “querría”.

Características y limitaciones del modelo Whisper
El modelo Whisper puede convertir audio hablado de los siguientes idiomas en texto :
africaans

árabe

armenio

Azerbaiyano

Bielorruso

bosnio

búlgaro

catalán

Chino

croata

checo

danés

Holandés

Inglés (¡por supuesto!)

estonio

finlandés

Francés

gallego

Alemán

Griego

hebreo

hindi

húngaro

islandés

indonesio

italiano

japonés

Canarés

Kazajo

coreano

letón

lituano

macedónio

malayo

Maratí

maorí

Nepalí

noruego

persa

Polaco

portugués

rumano

ruso

serbio

eslovaco

esloveno

Español

swahili

sueco

Tagalo

Tamil

tailandés

turco

ucranio

Urdú

vietnamita

galés

Así que, al final del día, podrá entender el audio hablado por usted y probablemente cualquier idioma hablado por sus amigos y colegas.

Los desarrolladores están limitados a no enviar más de 50 solicitudes por minuto al punto final, por lo que esta restricción debe tenerse en cuenta si desea transcribir grandes cantidades de audio.

Whisper admite audio en formatos flac, mp3, mp4, mpeg, mpga, m4a, ogg, wav o webm. Independientemente del formato que utilice, el tamaño máximo de archivo para enviar al punto final es de 25 MB.

Ahora bien, si no has trabajado mucho con archivos de audio, ten en cuenta que algunos formatos crean archivos REALMENTE GRANDES (por ejemplo, el formato wav) y otros crean archivos realmente pequeños (por ejemplo, el formato m4a). Por lo tanto, convertir tu archivo a un formato diferente puede ayudarte con la limitación de 25 MB. Sin embargo, más adelante en este capítulo, veremos el código de una herramienta que toma un solo archivo de audio grande y lo divide en varios archivos más pequeños.

Punto final de transcripciones
El punto final de transcripciones es un servicio REST que convierte audio en texto y solo es compatible con el modelo Whisper .

Creando la solicitud
En la Tabla 4-1 se enumeran todos los parámetros HTTP necesarios para llamar al punto final de transcripciones.
Tabla 4-1Los parámetros HTTP para el punto final de transcripciones
Parámetro HTTP

Descripción

URL del punto final

https://api.openai.com/v1/audio/transcriptions

Método

CORREO

Encabezamiento

Autorización: Portador $OPENAI_API_KEY

Tipo de contenido

multiparte/datos de formulario

Nota¡Presta mucha atención al tipo de contenido en la tabla anterior! A diferencia del punto final de chat que envía todos los parámetros de solicitud HTTP como un objeto JSON, el punto final de transcripciones solo acepta parámetros como elementos de datos de formulario . Si intentas enviar un objeto JSON con un formato correcto (o incluso con un formato deficiente), el punto final de transcripciones devolverá un error muy opaco.
Cuerpo de la solicitud (datos de formulario de varias partes)
Tabla 4-2El cuerpo de la solicitud para Whisper
