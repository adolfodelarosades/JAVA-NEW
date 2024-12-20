# 1. Introduction to Generative AI

1. Join our book community on Discord
2. Introducing generative AI
   1. Domains of generative AI
   2. Text generation
   3. Image generation
   4. Music generation
   5. Video generation
3. The history and current status of research
4. 18 months later: main trends and innovations
   1. Retrieval Augmented Generation
   2. Multimodality
   3. AI Agents
   4. Small Language Models
5. Summary
6. References

## Únete a nuestra comunidad de libros en Discord

https://packt.link/EarlyAccess

¡Hola! ¡Bienvenidos a la *The Ultimate Guide to ChatGPT and OpenAI*! En este libro, exploraremos el fascinante mundo de la **Generative Artificial Intelligence (GAI) - Inteligencia Artificial Generativa (GAI)** y sus aplicaciones innovadoras. La IA generativa ha transformado la forma en que interactuamos con las máquinas, permitiendo que las computadoras creen, predigan y aprendan sin instrucciones humanas explícitas. Desde ***el lanzamiento de ChatGPT en noviembre de 2023***, hemos sido testigos de avances sin precedentes en el procesamiento del lenguaje natural, la síntesis de imágenes y videos y muchos otros campos. Ya sea que sea un principiante curioso o un profesional experimentado, esta guía lo equipará con el conocimiento y las habilidades para navegar por el apasionante panorama de la IA generativa. Entonces, profundicemos y comencemos con algunas definiciones del contexto en el que nos movemos.

Este capítulo proporciona una descripción general del campo de la IA generativa, que consiste en crear datos o contenidos nuevos y únicos utilizando algoritmos de **machine learning (ML) - aprendizaje automático**.

Se centra en las aplicaciones de la IA generativa en diversos campos, como la síntesis de imágenes, la generación de texto y la composición musical, destacando el potencial de la IA generativa para revolucionar diversas industrias. Esta introducción a la IA generativa proporcionará contexto sobre dónde se encuentra esta tecnología, así como el conocimiento para ubicarla dentro del amplio mundo de la IA, el ML y el **Deep Learning ( DL )**. Luego, nos detendremos en las principales áreas de aplicación de la IA generativa con ejemplos concretos y desarrollos recientes para que pueda familiarizarse con el impacto que puede tener en las empresas y la sociedad en general.

Además, estar al tanto del recorrido de investigación hacia el estado actual del arte de la IA generativa le permitirá comprender mejor los fundamentos de los desarrollos recientes y los modelos de última generación.

Todo esto lo cubriremos con los siguientes temas:

* Comprender la IA generativa
* Explorando los dominios de la IA generativa
* Historia y estado actual de la investigación sobre IA generativa

Al final de este capítulo, estará familiarizado con el apasionante mundo de la IA generativa, sus aplicaciones, la historia de investigación detrás de ella y los desarrollos actuales, que podrían tener (y están teniendo actualmente) un impacto disruptivo en las empresas.

## Presentamos la IA generativa

La IA ha avanzado mucho en los últimos años y una de las áreas que ha experimentado un crecimiento considerable es la **IA generativa**. ***La IA generativa es un subcampo de la IA y el aprendizaje automático que se centra en generar contenido nuevo, como imágenes, texto, música y vídeo, mediante el uso de algoritmos y modelos que se han entrenado con datos existentes mediante técnicas de aprendizaje automático***.

Para comprender mejor la relación entre **IA**, **ML**, **DL** e **IA generativa**, considere ***la IA como la base***, ***mientras que ML, DL e IA generativa representan áreas de estudio y aplicación cada vez más especializadas y enfocadas***:

* La **IA** representa el amplio campo de creación de sistemas que puedan realizar tareas, mostrando inteligencia y capacidad humana y siendo capaces de interactuar con el ecosistema.

* **ML** es una rama que se centra en la creación de algoritmos y modelos que permiten que esos sistemas aprendan y mejoren con el tiempo y el entrenamiento. Los modelos de ML aprenden de los datos existentes y actualizan automáticamente sus parámetros a medida que crecen .

* El **DL** es una rama del **ML**, en el sentido de que abarca modelos de aprendizaje automático profundo. Estos modelos profundos se denominan **neural networks - redes neuronales** y son especialmente adecuados en dominios como la **computervision - visión artificial** o el **Natural Language Processing (NLP) - procesamiento del lenguaje natural ( NLP )**. Cuando hablamos de modelos de ML y DL, normalmente nos referimos a modelos discriminativos, cuyo objetivo es hacer predicciones o inferir patrones a partir de datos.

* Y finalmente, llegamos a la **IA generativa**, otra subrama del **DL**, que no utiliza redes neuronales artificiales profundas para agrupar, clasificar o hacer predicciones sobre datos existentes: utiliza esos poderosos modelos de redes neuronales artificiales para generar contenido completamente nuevo, desde imágenes hasta lenguaje natural, desde música hasta video.
  
La siguiente figura muestra cómo se relacionan estas áreas de investigación entre sí:

![image](https://github.com/user-attachments/assets/9f0ac018-2e7a-4ad7-95c1-f3e7e22f50c2)

**Figura 1.1 – Relación entre IA, ML, DL e IA generativa**

Los modelos de IA generativos se pueden entrenar con grandes cantidades de datos y luego pueden generar nuevos ejemplos desde cero utilizando patrones en esos datos. Este proceso generativo es diferente de los modelos discriminativos, que se entrenan para predecir la clase o etiqueta de un ejemplo determinado.

El tipo de Redes Neuronales que incorporan IA Generativa se denominan **Large Foundation Models LFMs - Grandes Modelos de Fundación**. En el caso de modelos de lenguaje como ChatGPT, hablamos de **Large Language Models (LLMs)**.

*Los Large Language Models son un tipo de red neuronal artificial que se caracteriza por una arquitectura de transformador. Se caracterizan por una enorme cantidad de parámetros (del orden de billones de parámetros) y han sido entrenados con miles de millones de palabras. Dado el conjunto de entrenamiento, los LLM son capaces de comprender y generar lenguaje natural a partir de la entrada del usuario.*

Aunque la comprensión y generación de texto es probablemente una de las características más destacadas de la IA Generativa, este campo abarca muchos dominios.

### Dominios de la IA generativa

En los últimos años, la IA generativa ha logrado avances significativos y ha ampliado sus aplicaciones a una amplia gama de dominios, como el arte, la música, la moda, la arquitectura y muchos más. En algunos de ellos, está transformando la forma en que creamos, diseñamos y entendemos el mundo que nos rodea. En otros, está mejorando y haciendo más eficientes los procesos y operaciones existentes.

El hecho de que la IA generativa se utilice en muchos ámbitos también implica que sus modelos pueden manejar distintos tipos de datos, desde lenguaje natural hasta audio o imágenes. Veamos cómo los modelos de IA generativa abordan distintos tipos de datos y dominios.

### Generación de texto

Una de las mayores aplicaciones de la IA generativa (y la que abordaremos más a lo largo de este libro) es su capacidad para producir nuevos contenidos en lenguaje natural. De hecho, los algoritmos de IA generativa pueden utilizarse para generar nuevos textos, como artículos, poesía y descripciones de productos.

Por ejemplo, un modelo de lenguaje como GPT-4o, desarrollado por OpenAI, puede entrenarse con grandes cantidades de datos de texto y luego usarse para generar texto nuevo, coherente y gramaticalmente correcto en diferentes idiomas (tanto en términos de entrada como de salida), así como para extraer características relevantes del texto, como palabras clave, temas o resúmenes completos.

A continuación se muestra un ejemplo de cómo trabajar con GPT-3:

![image](https://github.com/user-attachments/assets/e8115283-a800-4bea-b97f-6a3b776f142b)


**Figura 1.2 – Ejemplo de ChatGPT respondiendo a un mensaje del usuario y agregando referencias**

A continuación, pasaremos a la generación de imágenes.

### Generación de imágenes

Uno de los primeros y más conocidos ejemplos de IA generativa en la síntesis de imágenes es la arquitectura **Generative Adversarial Network (GAN)** introducida en el artículo de 2014 de I. Goodfellow et al., *Generative Adversarial Networks*. El propósito de las GAN es generar imágenes realistas que sean indistinguibles de las imágenes reales. Esta capacidad tenía varias aplicaciones comerciales interesantes, como la generación de conjuntos de datos sintéticos para entrenar modelos de visión artificial, la generación de imágenes realistas de productos y la generación de imágenes realistas para aplicaciones de realidad virtual y realidad aumentada.

A continuación se muestra un ejemplo de caras de personas que no existen ya que están generadas íntegramente por IA:

![image](https://github.com/user-attachments/assets/e6424007-fd48-4467-bf4a-c99dc59fc234)

**Figura 1.3 – Caras imaginarias generadas por GAN StyleGAN2 en https://this-person-does-not-exist.com/en**

En 2021, OpenAI introdujo un nuevo modelo de IA generativa en este campo: **DALL-E**. A diferencia de las GAN, el modelo DALL-E está diseñado para generar imágenes a partir de descripciones en lenguaje natural (las GAN toman un vector de ruido aleatorio como entrada) y puede generar una amplia gama de imágenes, que pueden no parecer realistas, pero que aún así representan los conceptos deseados.

DALL-E tiene un gran potencial en industrias creativas como la publicidad, el diseño de productos y la moda, entre otras, para crear imágenes únicas y creativas.

Desde su primer lanzamiento hasta la fecha (diciembre de 2024), DALL-E ha mejorado notablemente, como se puede ver en los siguientes ejemplos. Veamos a continuación una creación artística de DALL-E en los albores de su vida:

![image](https://github.com/user-attachments/assets/24cea1eb-e8f8-41d8-b102-30829205b83d)

**Figura 1.4 – Imágenes generadas por DALL-E con un mensaje en lenguaje natural como entrada**

Veamos ahora lo que**DALL-E3**, la versión más reciente del modelo en el momento de escribir este libro, puede producir (aquí estoy usando **Microsoft Image Creator** con tecnología DALL-E3. Puedes probarlo en https://copilot.microsoft.com/images/create):

![image](https://github.com/user-attachments/assets/779fa8c9-9cc8-4e29-93eb-c7d7a4982a83)

**Figura 1.5 – Imágenes generadas por DALL-E3 con un mensaje en lenguaje natural como entrada**

Es impresionante ver el nivel de mejora de este modelo en menos de 18 meses. Curiosamente, esto es solo la punta del iceberg de las enormes mejoras que se han producido en los últimos meses en el campo de la IA generativa.

### Generación musical

Los primeros acercamientos a la IA generativa para la generación musical se remontan a los años 50, con investigaciones en el campo de la composición algorítmica, una técnica que utiliza algoritmos para generar composiciones musicales. De hecho, en 1957, Lejaren Hiller y Leonard Isaacson crearon la Suite Illiac para Cuarteto de Cuerdas ( https://www.youtube.com/watch?v=n0njBFLQSk8 ), la primera pieza musical compuesta íntegramente por IA. Desde entonces, el campo de la IA generativa para la música ha sido objeto de investigación continua durante varias décadas. Entre los desarrollos de los últimos años, nuevas arquitecturas y frameworks se han generalizado entre el público general, como la arquitectura **WaveNet** introducida por Google en 2016, que ha sido capaz de generar muestras de audio de alta calidad, o el proyecto **Magenta**, también desarrollado por Google, que utiliza **Recurrent Neural Networks (RNNs) - Redes Neuronales Recurrentes ( RNN )** y otras técnicas de ML para generar música y otras formas de arte. Luego, en 2020, OpenAI también anunció **Jukebox**, una red neuronal que genera música, con la posibilidad de personalizar la salida en términos de estilo musical y vocal, género, artista de referencia, etc.

Estos y otros frameworks se convirtieron en los cimientos de muchos asistentes de composición de IA para la generación de música. Un ejemplo es **Flow Machines**, desarrollado por Sony CSL Research. Este sistema de IA generativa se entrenó en una gran base de datos de piezas musicales para crear nueva música en una variedad de estilos. Fue utilizado por el compositor francés Benoît Carré para componer un álbum llamado Hello World ( https://www.helloworldalbum.net/ ), que incluye colaboraciones con varios músicos humanos.

Aquí podéis ver un ejemplo de una pista generada íntegramente por **Music Transformer**, uno de los modelos dentro del proyecto **Magenta**:

![image](https://github.com/user-attachments/assets/f2bdef50-5abb-4775-9967-877e73b2aa7a)

**Figura 1.6 – Music Transformer permite a los usuarios escuchar interpretaciones musicales generadas por IA**

Otra aplicación increíble de la IA generativa en el ámbito de la música es la síntesis de voz. De hecho, es posible encontrar muchas herramientas de IA que pueden crear audio a partir de entradas de texto en las voces de cantantes famosos.

Por ejemplo, si siempre te has preguntado cómo sonarían tus canciones si Kanye West las interpretara, bueno, ahora puedes cumplir tus sueños con herramientas como **FakeYou.com** ( https://fakeyou.com/ ), **Deep Fake Text to Speech** o **UberDuck.ai** ( https://uberduck.ai/ ).

![image](https://github.com/user-attachments/assets/c5d7b3a9-392e-4a84-8613-19615fe8f59b)

**Figura 1.7 – Síntesis de texto a voz con UberDuck.ai**

Debo decir que el resultado es realmente impresionante. Si quieres divertirte, también puedes probar voces de tus dibujos animados favoritos, como Winnie The Pooh...

Vayamos un paso más allá. ¿Qué pasaría si pudiéramos generar una canción desde cero, simplemente pidiéndole a GenAI que lo haga por nosotros en lenguaje natural? Bueno, hoy podemos hacerlo sin problemas y sin ningún conocimiento sobre música. Entre los productos GenAI que están surgiendo en el mercado de la música actualmente, un gran ejemplo es Suno, cuya misión es “[...] construir un futuro en el que cualquiera pueda hacer buena música. Ya seas un cantante de ducha o un artista de las listas de éxitos, rompemos las barreras entre tú y la canción que sueñas hacer. No se necesita ningún instrumento, solo imaginación. De tu mente a la música”. (Fuente: https://suno.com/about ).


¿Puedes creer que se convirtió en mi éxito del verano de 2024? Si tú también quieres crear tu éxito del verano, puedes probarlo gratis en https://suno.com/create .

Generación de video
La IA generativa para la generación de vídeo comparte una cronología de desarrollo similar a la de la generación de imágenes. De hecho, uno de los avances clave en el campo de la generación de vídeo ha sido el desarrollo de las GAN. Gracias a su precisión a la hora de producir imágenes realistas, los investigadores han comenzado a aplicar estas técnicas también a la generación de vídeo. Uno de los ejemplos más notables de generación de vídeo basada en GAN es Motion to Video de DeepMind , que generó vídeos de alta calidad a partir de una única imagen.

y una secuencia de movimientos. Otro gran ejemplo es el marco basado en DL Video-to-Video Synthesis ( Vid2Vid ) de NVIDIA , que utiliza GAN para sintetizar videos de alta calidad a partir de videos de entrada.

El sistema Vid2Vid puede generar vídeos consistentes en el tiempo, es decir, que mantienen un movimiento fluido y realista a lo largo del tiempo. La tecnología se puede utilizar para realizar diversas tareas de síntesis de vídeo, como las siguientes:

Convertir vídeos de un dominio a otro (por ejemplo, convertir un vídeo diurno en un vídeo nocturno o un boceto en una imagen realista)
Modificar vídeos existentes (por ejemplo, cambiar el estilo o la apariencia de los objetos en un vídeo)
Creación de nuevos vídeos a partir de imágenes estáticas (por ejemplo, animar una secuencia de imágenes fijas)
En septiembre de 2022, los investigadores de Meta anunciaron la disponibilidad general de Make-A-Video ( https://makeavideo.studio/ ), un nuevo sistema de IA que permite a los usuarios convertir sus indicaciones en lenguaje natural en videoclips. Detrás de esta tecnología se pueden reconocer muchos de los modelos que hemos mencionado para otros dominios hasta ahora: comprensión del lenguaje para la indicación, generación de imágenes y movimiento con generación de imágenes y música de fondo creada por compositores de IA.

Ahora bien, todo lo que hemos mencionado anteriormente palidece en comparación con los últimos modelos de conversión de texto a vídeo. Por nombrar uno, OpenAI anunció en febrero de 2024 un nuevo modelo de conversión de texto a vídeo llamado SORA y publicó algunos experimentos preliminares que resultaron algo inesperado:


Figura 1: Vídeos generados por SORA a partir de un mensaje en lenguaje natural. Fuente: https://openai.com/index/sora/
Figura 1: Vídeos generados por SORA a partir de un mensaje en lenguaje natural. Fuente: https://openai.com/index/sora/
Te recomiendo que visites la página web de SORA para que eches un vistazo a los increíbles vídeos que ha creado. Al momento de escribir esto, SORA no está disponible públicamente, ya que está pasando por varias pruebas realizadas por el equipo rojo de OpenAI.

En general, la IA generativa ha tenido un impacto en muchos ámbitos durante años, y algunas herramientas de IA ya brindan soporte de manera consistente a artistas, organizaciones y usuarios en general. El futuro parece muy prometedor; sin embargo, antes de pasar a los modelos definitivos disponibles en el mercado hoy en día, primero debemos comprender más profundamente las raíces de la IA generativa, su historial de investigación y los desarrollos recientes que eventualmente conducen a los modelos OpenAI actuales.

Historia y estado actual de la investigación
En secciones anteriores, hemos hecho un repaso de las tecnologías más recientes y punteras en el campo de la IA generativa, todas ellas desarrolladas en los últimos años. Sin embargo, la investigación en este campo se remonta a décadas atrás.

Podemos marcar el inicio de la investigación en el campo de la IA generativa en la década de 1960, cuando Joseph Weizenbaum desarrolló el chatbot ELIZA, uno de los primeros ejemplos de un sistema de PNL. Era un sistema de interacción simple basado en reglas destinado a entretener a los usuarios con respuestas basadas en la entrada de texto, y allanó el camino para futuros desarrollos tanto en PNL como en IA generativa. Sin embargo, sabemos que la IA generativa moderna es un subcampo del DL y, aunque las primeras redes neuronales artificiales ( ANN ) se introdujeron por primera vez en la década de 1940, los investigadores se enfrentaron a varios desafíos, incluido el poder de computación limitado y la falta de comprensión de la base biológica del cerebro. Como resultado, las ANN no habían ganado mucha atención hasta la década de 1980 cuando, además de nuevos desarrollos de hardware y neurociencia, la llegada del algoritmo de retropropagación facilitó la fase de entrenamiento de las ANN. De hecho, antes de la llegada de la retropropagación, el entrenamiento de redes neuronales era difícil porque no era posible calcular eficientemente el gradiente del error con respecto a los parámetros o pesos asociados a cada neurona, mientras que la retropropagación permitió automatizar el proceso de entrenamiento y posibilitó la aplicación de las ANN.

Luego, en las décadas de 2000 y 2010, el avance en las capacidades computacionales, junto con la enorme cantidad de datos disponibles para el entrenamiento, generó la posibilidad de hacer que el aprendizaje automático fuera más práctico y estuviera disponible para el público en general, con el consiguiente impulso a la investigación.

En 2013, Kingma y Welling introdujeron una nueva arquitectura de modelos en su artículo Auto-Encoding Variational Bayes , llamada Variational Autoencoders ( VAE ). Los VAE son modelos generativos que se basan en el concepto de inferencia variacional. Proporcionan una forma de aprendizaje con una representación compacta de datos al codificarlos en un espacio de menor dimensión llamado espacio latente (con el componente codificador ) y luego descodificándolos nuevamente en el espacio de datos original (con el componente decodificador ).

La innovación clave de los VAE es la introducción de una interpretación probabilística del espacio latente. En lugar de aprender una asignación determinista de la entrada al espacio latente, el codificador asigna la entrada a una distribución de probabilidad sobre el espacio latente. Esto permite a los VAE generar nuevas muestras mediante el muestreo del espacio latente y la decodificación de las muestras en el espacio de entrada.

Por ejemplo, digamos que queremos entrenar un VAE que pueda crear nuevas imágenes de gatos y perros que parezcan reales.

Para ello, la VAE toma primero una fotografía de un gato o un perro y la comprime en un conjunto más pequeño de números en el espacio latente, que representan las características más importantes de la fotografía. Estos números se denominan variables latentes .

Luego, el VAE toma estas variables latentes y las utiliza para crear una nueva imagen que parece una imagen real de un gato o un perro. Esta nueva imagen puede tener algunas diferencias con respecto a las imágenes originales, pero debería parecer que pertenece al mismo grupo de imágenes.

El VAE mejora en la creación de imágenes realistas con el tiempo comparando sus imágenes generadas con las imágenes reales y ajustando sus variables latentes para hacer que las imágenes generadas se parezcan más a las reales.

Las VAE allanaron el camino hacia un rápido desarrollo en el campo de la IA generativa. De hecho, solo un año después, Ian Goodfellow introdujo las GAN. A diferencia de la arquitectura de las VAE, cuyos elementos principales son el codificador y el decodificador, las GAN constan de dos redes neuronales (un generador y un discriminador) que trabajan una contra la otra en un juego de suma cero.

El generador crea datos falsos (en el caso de las imágenes, crea una nueva imagen) que pretenden parecer datos reales (por ejemplo, la imagen de un gato). El discriminador toma tanto datos reales como falsos e intenta distinguirlos: es el crítico en nuestro ejemplo del falsificador de arte.

Durante el entrenamiento, el generador intenta crear datos que puedan engañar al discriminador para que piense que son reales, mientras que el discriminador intenta mejorar su capacidad para distinguir entre datos reales y falsos. Las dos partes se entrenan juntas en un proceso llamado entrenamiento adversarial .

Con el tiempo, el generador mejora en la creación de datos falsos que parecen reales, mientras que el discriminador mejora en la distinción entre datos reales y falsos. Con el tiempo, el generador se vuelve tan bueno en la creación de datos falsos que ni siquiera el discriminador puede distinguir entre datos reales y falsos.

A continuación se muestra un ejemplo de rostros humanos generados completamente por una GAN:

Figura 1.8 – Ejemplos de caras fotorrealistas generadas por GAN (tomado de Crecimiento progresivo de GAN para mejorar la calidad, la estabilidad y la variación, 2017: https://arxiv.org/pdf/1710.10196.pdf)
Figura 1.8 – Ejemplos de caras fotorrealistas generadas por GAN (tomado de Crecimiento progresivo de GAN para mejorar la calidad, la estabilidad y la variación, 2017: https://arxiv.org/pdf/1710.10196.pdf)
Ambos modelos, VAE y GAN, están pensados ​​para generar datos completamente nuevos que sean indistinguibles de las muestras originales, y su arquitectura ha mejorado desde su concepción, junto con el desarrollo de nuevos modelos como PixelCNN, propuesto por Van den Oord y su equipo, y WaveNet, desarrollado por Google DeepMind, lo que ha llevado a avances en la generación de audio y voz.

Otro gran hito se logró en 2017 cuando los investigadores de Google introdujeron una nueva arquitectura, llamada Transformer , en el artículo Attention Is All You Need . Fue revolucionario en el campo de la generación de lenguaje, ya que permitió el procesamiento paralelo mientras se conservaba la memoria sobre el contexto del lenguaje, superando los intentos anteriores de modelos de lenguaje basados ​​en RNN o marcos de memoria a largo plazo ( LSTM ).

Los transformadores fueron de hecho la base de los modelos de lenguaje masivos llamados Representaciones de Codificador Bidireccional de Transformadores ( BERT ), introducidos por Google en 2018, y pronto se convirtieron en la línea de base en los experimentos de PNL.

Los transformadores también son la base de todos los modelos generativos preentrenados ( GPT ) introducidos por OpenAI, incluido GPT-3, el modelo detrás de ChatGPT, así como otros modelos de base grandes.

Aunque hubo una cantidad importante de investigación y logros en esos años, no fue hasta la segunda mitad de 2022 que la atención general del público se desplazó hacia el campo de la IA generativa.

No es casualidad que 2022 haya sido denominado el año de la IA generativa . Fue el año en el que se generalizaron entre el público en general potentes modelos y herramientas de IA: servicios de imágenes basados ​​en difusión (MidJourney, DALL-E 2 y Stable Diffusion), ChatGPT de OpenAI, herramientas de conversión de texto a vídeo (Make-a-Video e Imagen Video) y de texto a 3D (DreamFusion, Magic3D y Get3D) se pusieron a disposición de los usuarios individuales, a veces también de forma gratuita.

Esto tuvo un impacto disruptivo por dos razones principales:

Una vez que los modelos de IA generativa se difundieron al público, cada usuario u organización tuvo la posibilidad de experimentar con su potencial y apreciarlo, incluso sin ser un científico de datos o un ingeniero de ML.
Los resultados de esos nuevos modelos y la creatividad que llevaban implícita fueron objetivamente asombrosos y a menudo preocupantes. Se levantó un llamado urgente a la adaptación, tanto de los individuos como de los gobiernos.
De ahora en adelante, en un futuro muy cercano, probablemente seremos testigos de un aumento en la adopción de sistemas de IA tanto para uso individual como para proyectos a nivel empresarial.

18 meses después: principales tendencias e innovaciones
Desde noviembre de 2022 hasta hoy, hemos sido testigos de una enorme cantidad de innovaciones en el campo de GenAI. Muchas de estas innovaciones están vinculadas a los nuevos modelos desarrollados y lanzados al público, como GPT-4o y DALL-E3 de OpenAI, pero también Google Gemini, Meta Llama 3, Microsoft Phi3 y muchos otros.

Sin embargo, los logros más notables probablemente residan en la forma en que interactuamos con esos modelos y creamos aplicaciones en torno a ellos. En esta sección, exploraremos tres avances principales que han marcado las arquitecturas de referencia más populares para las aplicaciones impulsadas por GenAI.

Recuperación Generación Aumentada
Una de las primeras limitaciones de ChatGPT y, en general, de los LLM, fue la del corte de la base de conocimiento. De hecho, el conocimiento de los LLM se limita al conjunto de conocimientos (compuesto por información pública de Internet) en el que han sido formados y, si bien este puede ser exhaustivo, no está actualizado. Además, carece de la base de conocimiento propia que podría ser relevante para nosotros o nuestra organización. Por ejemplo, si le preguntas a ChatGPT "¿cuál es la política de mi empresa en materia de seguro médico para los empleados?", el modelo no podrá responder ya que no tiene acceso a esta información.

Para superar esta limitación, se diseñó un nuevo marco que permite a los estudiantes de posgrado navegar por la documentación personalizada que podemos proporcionarles. Este marco se denomina Generación Aumentada de Recuperación (RAG).

La idea detrás de RAG es la de desacoplar el LLM de la base de conocimiento por la que queremos navegar. Para que esto sea posible, la base de conocimiento externa debe transformarse en vectores numéricos a través de un proceso llamado incrustación y almacenarse en una base de datos de vectores especializada.

Una incrustación es una forma de representar datos no numéricos de alta dimensión, como palabras u oraciones, en un espacio de menor dimensión, como un vector. Una incrustación de texto puede capturar las características semánticas y sintácticas del texto, como el significado, el contexto y la similitud.

Cada incrustación es un vector de números de punto flotante, de modo que la distancia entre dos incrustaciones en el espacio vectorial está correlacionada con la similitud semántica entre dos entradas
en el formato original.

Por ejemplo, si dos conceptos son similares, entonces sus representaciones vectoriales también deberían ser similares.


El RAG se compone de tres fases:

Recuperación : dada la consulta de un usuario y su vector correspondiente, se recuperan los documentos más similares (aquellos que corresponden a los vectores que están más cerca del vector de la consulta del usuario) y se utilizan como contexto base para el LLM.


Ampliación : el contexto recuperado se enriquece mediante instrucciones adicionales, reglas, medidas de seguridad y prácticas similares que son típicas de las técnicas de ingeniería rápida (cubriremos el tema de la ingeniería rápida en el Capítulo 3).


Generación : en función del contexto aumentado, el LLM genera la respuesta a la consulta del usuario.

El proceso general es el siguiente:


RAG combina las ventajas de los modelos generativos y los sistemas de recuperación de información para mejorar la calidad y la relevancia del contenido generado. Los modelos generativos tradicionales dependen únicamente de sus datos de entrenamiento para generar respuestas, lo que a veces puede dar como resultado información obsoleta o irrelevante. RAG aborda esta limitación integrando bases de conocimiento externas durante el proceso de generación.

Por ejemplo, ChatGPT de OpenAI, cuando se mejora con RAG, puede extraer datos actuales de fuentes confiables para responder una consulta sobre eventos recientes, lo que quedaría fuera del alcance de su límite de entrenamiento. Esta sinergia de recuperación y generación amplía la aplicabilidad de la IA generativa, haciéndola más robusta y útil en entornos dinámicos y ricos en información.

Multimodalidad
En el primer párrafo de este capítulo, vimos los distintos dominios de la IA generativa, que van desde el texto hasta las imágenes, desde los videos hasta la música. Por lo general, los modelos de base grandes tienden a ser específicos de un dominio, como vimos en el caso de los modelos de lenguaje grandes en el caso de la comprensión y generación de lenguajes, o DALL-E3 en el caso de la generación de imágenes.

Sin embargo, los avances recientes en IA generativa han permitido el desarrollo de grandes modelos multimodales (LMM) que pueden procesar y generar diferentes tipos de datos, como texto, imágenes, audio y vídeo.

Los LMM comparten con los Grandes Modelos de Lenguaje (LLM) “estándar” la capacidad de generalización y adaptación típica de los Grandes Modelos de Fundación. Sin embargo, los LMM son capaces de procesar datos heterogéneos con la idea de reflejar la forma en que los humanos interactuamos con el ecosistema que nos rodea, es decir, con todos nuestros sentidos.

Un gran ejemplo de modelo multimodal es el GPT-4o de OpenAI, que es capaz de interactuar con los usuarios a través de texto, imágenes y audio. Veamos el siguiente ejemplo:


Como puede ver, el modelo pudo analizar la imagen y razonar sobre ella. Ahora, sigamos adelante y pidamos al modelo que genere una ilustración:


El hecho más interesante de los LMM es que conservan sus capacidades de razonamiento, lo que los hace adecuados para el razonamiento complejo en contextos de datos heterogéneos. Consideremos este último ejemplo (que muestra solo las primeras líneas de la respuesta):


Como podéis imaginar, esto abre un panorama de aplicaciones en diversas industrias, y veremos algunos ejemplos concretos en los próximos capítulos.

Agentes de IA
En secciones anteriores, descubrimos cómo los LFM son geniales cuando se trata de generar resonancia y contenido. Sin embargo, les falta una habilidad, que es la de tomar acciones e interactuar con el ecosistema circundante que va más allá del usuario individual. Por ejemplo, ¿qué pasa si queremos que nuestro LLM sea capaz no solo de generar una publicación increíble en LinkedIn, sino también de publicarla en nuestra página?

Para superar esta limitación, los agentes de IA surgen como actores clave. Pero, ¿qué son exactamente? Los agentes pueden considerarse sistemas de IA impulsados ​​por grandes modelos de lenguaje que, dada la consulta de un usuario, pueden interactuar con el ecosistema circundante en la medida en que se lo permitamos. El perímetro del ecosistema está delimitado por las herramientas (o complementos) que proporcionamos a los agentes (en nuestro ejemplo anterior, podríamos proporcionar al agente un complemento de LinkedIn, para que pueda publicar el contenido generado).

Los agentes están compuestos de los siguientes ingredientes:

Un LLM que actúa como motor de razonamiento del sistema de IA
Un mensaje del sistema que indica al Agente que se comporte y piense de una manera determinada. Por ejemplo, puede diseñar un Agente como asistente de enseñanza para estudiantes con el siguiente mensaje del sistema: “Usted es un asistente de enseñanza. Dada la consulta de un estudiante, NUNCA proporcione la respuesta final, sino más bien proporcione algunas pistas para llegar a ella”.
Un conjunto de herramientas que el Agente puede aprovechar para interactuar con el ecosistema circundante.
Los agentes de IA son una representación perfecta del significado de “LLM como motor de razonamiento de una aplicación”. De hecho, la belleza de los agentes es que pueden elegir la mejor herramienta para usar con el fin de cumplir con la solicitud de un usuario. Por ejemplo, supongamos que tenemos un agente de IA para producir contenido de LinkedIn y le proporcionamos dos herramientas: un complemento de LinkedIn y un complemento de búsqueda web (cada uno con una descripción adecuada de su funcionalidad). Luego, exploremos el comportamiento del agente ante dos preguntas diferentes:

Genera una historia sobre un perrito que camina por las montañas. El Agente generará la historia sin involucrar ningún complemento.
Generar una historia sobre el clima actual en Milán. El Agente invocará el complemento de búsqueda web para obtener el clima actual en Milán.
Generar una publicación de LinkedIn sobre el clima actual en Milán y publicarla en mi perfil: el Agente invocará el complemento de búsqueda web para obtener el clima actual en Milán y el complemento de LinkedIn para publicarlo en mi perfil.
Las combinaciones de instrucciones y conjuntos de complementos hacen que los agentes de IA sean extremadamente versátiles y puedan crear entidades altamente especializadas para abordar escenarios específicos.

Y eso no es todo.

¿Por qué tener un solo agente si puedes crear tu propio equipo de agentes que se comuniquen y cooperen entre sí? Imagina varios agentes, cada uno con una experiencia y un objetivo específicos, que se comunican e interactúan entre sí para realizar una tarea. Así es como se ven las aplicaciones multiagente y, en los últimos meses, este patrón comenzó a mostrar comportamientos emergentes.

Consideremos el siguiente ejemplo. Queremos elaborar un discurso breve sobre el cambio climático. Para ello, necesitamos información actualizada (las últimas tendencias e investigaciones, perspectivas futuras, etc.), así como una investigación sólida basada en artículos académicos. Además, tenemos que ser concisos, pero precisos y eficaces, y ofrecer toda la información clave en un discurso muy breve.

Ahora, podríamos pedirle todo eso a un solo agente, proporcionándole todas las herramientas necesarias y con largas instrucciones para realizar la tarea. Sin embargo, está demostrado que los LLM tienden a tener un peor desempeño cuando les damos “demasiadas cosas que hacer”. En su lugar, utilicemos un enfoque multiagente, creando un equipo con los siguientes profesionales de IA:

Un analista de mercado que puede buscar en la web las últimas noticias sobre el cambio climático; será un agente con un complemento de búsqueda web e instrucciones específicas para buscar noticias;
Un investigador experto que pueda navegar fácilmente a través de artículos de investigación académica sobre el cambio climático. Será un agente con un complemento de Arxiv e instrucciones específicas sobre cómo recuperar información relevante;
Un experto en hablar en público que pueda consolidar fácilmente toda la información en un solo discurso, este será un agente con instrucciones adecuadas sobre cómo realizar discursos perfectos;
Un crítico que revisará el discurso y propondrá algunos cambios al experto en oratoria, de ser necesario será un Agente con instrucciones adecuadas sobre cómo realizar discursos perfectos;
Así, ante la pregunta del usuario “Generar un elevator pitch sobre el tema actual del cambio climático”, todos los agentes pueden empezar a trabajar en el proyecto.

Existen muchos marcos de trabajo que pueden ayudar a los desarrolladores con aplicaciones multiagente (incluidos AutoGen, LangGraph, CrewAI), especialmente en lo que respecta al “flujo” que queremos que sigan nuestros agentes. Por ejemplo, podríamos querer imponer un número específico de iteraciones; o que todos los agentes se invoquen al menos una vez; o incluso involucrarnos, como usuarios, en cada iteración para proporcionar más comentarios que se incorporarán en la próxima iteración.

En el momento de escribir este artículo, el marco multiagente muestra avances prometedores, pero aún se encuentra en una fase de experimentación y probablemente aún esté lejos de estar listo para la empresa. No obstante, es un atisbo de las extraordinarias capacidades de razonamiento que hay detrás de los LLM y de cómo pueden abrir nuevas formas de resolución y creación de problemas.

Modelos de lenguaje pequeños
Como era de esperar, los modelos de lenguaje grandes son grandes. Esto significa que la arquitectura de la red neuronal artificial que incluye los LLM está formada por una enorme cantidad de parámetros, del orden de billones. Lo ideal es que cuanto mayor sea el número de parámetros, mejores serán las capacidades de razonamiento del LLM. Sin embargo, un gran número de parámetros conlleva un alto coste de entrenamiento y alojamiento, ya que se necesita una infraestructura de IA potente. Además, el consumo de energía que requieren esos modelos plantea serias dudas sobre el impacto medioambiental del entrenamiento de los LLM y su sostenibilidad general a largo plazo. Para que te hagas una idea, estos son algunos números relacionados con los LLM de código abierto con diferentes tamaños (medidos en número de parámetros):

Figura 2: Huella de carbono y potencia de cálculo necesaria para entrenar distintos modelos en el mismo centro de datos. Fuente: https://arxiv.org/pdf/2302.13971
Figura 2: Huella de carbono y potencia de cálculo necesaria para entrenar distintos modelos en el mismo centro de datos. Fuente: https://arxiv.org/pdf/2302.13971
Afortunadamente, en los últimos meses hemos sido testigos de un creciente interés e inversión en la investigación de modelos más pequeños, con el objetivo de mantener capacidades de razonamiento decentes al tiempo que se reduce el número de parámetros. La idea es que los modelos más pequeños, incluso si son “menos inteligentes”, pueden alcanzar los requisitos deseados si se especializan en actividades más específicas. Después de todo, ¿realmente necesitamos modelos enormes y superpoderosos de billones de parámetros para resolver todas las tareas que tenemos en mente?

Estos modelos más pequeños se denominan Small Language Models (SML) y, además de ser más ligeros y menos exigentes en términos de infraestructura, también están mostrando un rendimiento sorprendentemente alto.

Por ejemplo, si consideramos la versión más pequeña de Phi-3, parte de la popular familia SLM Phi desarrollada por Microsoft, con “solo” 7 mil millones de parámetros, podemos ver que supera a GPT-3.5-turbo en todos los benchmarks LLM más populares:

Figura 3: tabla comparativa de las capacidades de Phi-3 Small en comparación con otras SLM y LLM. Fuente: https://azure.microsoft.com/en-us/blog/introducing-phi-3-redefining-whats-possible-with-slms/
Figura 3: tabla comparativa de las capacidades de Phi-3 Small en comparación con otras SLM y LLM. Fuente: https://azure.microsoft.com/en-us/blog/introducing-phi-3-redefining-whats-possible-with-slms/
Ahora, podríamos pensar que el GPT-3.5-turbo está algo “obsoleto”, sin embargo debemos recordar que, con sus parámetros 175B, solía ser el modelo más poderoso del mercado hace solo 1 año, y es notable ver que un modelo 7B es capaz de mejores resultados.

El campo de los SLM es definitivamente una línea de investigación a la que hay que prestar atención, especialmente cuando se trata de aquellos escenarios en los que podría querer implementar mi modelo localmente o incluso personalizarlo con ajustes finos (cubriremos los ajustes finos en el próximo capítulo).

Resumen
En este capítulo, exploramos el apasionante mundo de la IA generativa y sus diversos dominios de aplicación, incluida la generación de imágenes, texto, música y vídeo. Aprendimos cómo los modelos de IA generativa, como ChatGPT y DALL-E, entrenados por OpenAI, utilizan técnicas de aprendizaje automático para aprender patrones en grandes conjuntos de datos y generar contenido nuevo que sea novedoso y coherente. También analizamos la historia de la IA generativa, sus orígenes y el estado actual de la investigación al respecto.

El objetivo de este capítulo fue proporcionar una base sólida sobre los conceptos básicos de la IA generativa e inspirarlo a explorar más este fascinante campo.

En el próximo capítulo, nos centraremos en una de las tecnologías más prometedoras disponibles en el mercado hoy en día, ChatGPT: repasaremos la investigación detrás de ella y su desarrollo por parte de OpenAI, la arquitectura de su modelo y los principales casos de uso que puede abordar a día de hoy.

Referencias
https://arxiv.org/abs/1406.2661
https://www.youtube.com/watch?v=Iy9vRvyRf_E
https://arxiv.org/abs/1912.04958
Esta persona no existe: https://esta-persona-no-existe.com
https://arxiv.org/abs/1808.06601
https://www.microsoft.com/en-us/research/blog/un-modelo-generativo-profundo-trifecta-tres-avances-que-funcionan-para-aprovechar-la-energia-a-gran-escala/
https://tcwang0509.github.io/vid2vid/
https://arxiv.org/pdf/2302.13971
https://azure.microsoft.com/en-us/blog/introduciendo-phi-3-redefining-whats-pos   
