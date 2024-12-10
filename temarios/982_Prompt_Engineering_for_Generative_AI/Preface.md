# Prefacio

El rápido ritmo de innovación en IA generativa promete cambiar la forma en que vivimos y trabajamos, pero cada vez es más difícil seguir el ritmo. La [cantidad de artículos sobre IA publicados en arXiv está creciendo exponencialmente](https://x.com/MarioKrenn6240/status/1577102743927652354), [Stable Diffusion](https://x.com/a16z/status/1592922394275872768?s=20) ha estado entre los proyectos de código abierto de más rápido crecimiento en la historia y el [Midjourney’s Discord server](https://x.com/hammer_mt/status/1657730978125869056?s=20) tiene decenas de millones de miembros, superando incluso a las comunidades de juegos más grandes. Lo que más capturó la imaginación del público fue el lanzamiento de ChatGPT por parte de OpenAI, que alcanzó los [100 millones de usuarios en dos meses](https://x.com/kylelf_/status/1623679176246185985), lo que la convirtió en la aplicación para consumidores de más rápido crecimiento en la historia. Aprender a trabajar con IA se ha convertido rápidamente en una de las habilidades más demandadas.

Todos los que utilizan la IA de manera profesional aprenden rápidamente que la calidad del resultado depende en gran medida de lo que se proporciona como entrada. La disciplina de la *prompt engineering* ha surgido como un conjunto de mejores prácticas para mejorar la fiabilidad, la eficiencia y la precisión de los modelos de IA. "En diez años, la mitad de los empleos del mundo estarán en prompt engineering", [afirma Robin Li](https://www.forbes.com/sites/craigsmith/2023/04/05/mom-dad-i-want-to-be-a-prompt-engineer/), cofundador y director ejecutivo del gigante tecnológico chino Baidu. Sin embargo, esperamos que la ingeniería rápida sea una habilidad requerida para muchos trabajos, similar a la competencia en Microsoft Excel, en lugar de un título de trabajo popular en sí mismo. Esta nueva ola de disrupción está cambiando todo lo que creíamos saber sobre las computadoras. Estamos acostumbrados a escribir algoritmos que devuelven el mismo resultado cada vez, no es así para la IA, donde las respuestas no son deterministas. El costo y la latencia son factores reales nuevamente, después de décadas de que la ley de Moore nos hiciera complacientes al esperar computación en tiempo real a un costo insignificante. El mayor obstáculo es la tendencia de estos modelos a inventar cosas con confianza, denominada *alucinación*, lo que nos obliga a repensar la forma en que evaluamos la precisión de nuestro trabajo.

Hemos estado trabajando con IA generativa desde la versión beta de GPT-3 en 2020 y, a medida que vimos que los modelos progresaban, muchos de los primeros trucos y atajos de incitación dejaron de ser necesarios. Con el tiempo, surgió un conjunto coherente de principios que seguían siendo útiles con los modelos más nuevos y funcionaban tanto en la generación de texto como de imágenes. Hemos escrito este libro basándonos en estos principios atemporales, para ayudarte a aprender habilidades transferibles que seguirán siendo útiles sin importar lo que suceda con la IA en los próximos cinco años. La clave para trabajar con IA no es "descubrir cómo hackear la indicación agregando una palabra mágica al final que cambie todo lo demás", como afirma [el cofundador de OpenAI, Sam Altman](https://greylock.com/greymatter/sam-altman-ai-for-the-next-era/), sino que lo que siempre importará es la "calidad de las ideas y la comprensión de lo que quieres". Si bien no sabemos si lo llamaremos "prompt engineering" en cinco años, trabajar de manera efectiva con IA generativa solo será más importante.

## Requisitos de software para este libro

Todo el código de este libro está en Python y fue diseñado para ejecutarse en un [Jupyter Notebook](https://jupyter.org/) o un [notebook de Google Colab](https://colab.research.google.com/). Los conceptos que se enseñan en el libro se pueden transferir a JavaScript o a cualquier otro lenguaje de codificación si se prefiere, aunque el enfoque principal de este libro está en las técnicas de inducción en lugar de las habilidades de codificación tradicionales. Todo el código se puede [encontrar en GitHub](https://github.com/BrightPool/prompt-engineering-for-generative-ai-examples/) y enlazaremos a los notebooks relevantes a lo largo del libro. Se recomienda encarecidamente que utilices el [repositorio de GitHub](https://github.com/BrightPool/prompt-engineering-for-generative-ai-examples/) y ejecutes los ejemplos proporcionados mientras lees el libro.

Para los ejemplos que no son non-notebook, puedes ejecutar el script con el formato `python content/chapter_x/script.py` en tu terminal, donde `x` es el número de capítulo y `script.py` es el nombre del script. En algunos casos, las claves de API deben configurarse como variables de entorno, y lo dejaremos en claro. Los paquetes utilizados se actualizan con frecuencia, así que instala nuestro [requirements.txt](https://github.com/BrightPool/prompt-engineering-for-generative-ai-examples/blob/main/requirements.txt) en un entorno virtual antes de ejecutar ejemplos de código.

El archivo `requirements.txt` se genera para Python 3.9. Si desea utilizar una versión diferente de Python, puede generar un nuevo archivo `requirements.txt` a partir de este archivo [requirements.in](https://github.com/BrightPool/prompt-engineering-for-generative-ai-examples/blob/main/requirements.in) que se encuentra en el repositorio de GitHub ejecutando estos comandos:

![image](https://github.com/user-attachments/assets/3d32c848-a887-48c3-9e23-857cf39ff78c)

```sh
pip install pip-tools
pip-compile requisitos.in
```

Para usuarios de Mac:

1. Abrir Terminal: puedes encontrar la aplicación Terminal en tu carpeta Aplicaciones, en Utilidades, o usar Spotlight para buscarla.
2. Vaya a la carpeta de su proyecto: use el comando `cd` para cambiar el directorio a la carpeta de su proyecto. Por ejemplo: `cd path/to/your/project`.
3. Cree el entorno virtual: use el siguiente comando para crear un entorno virtual llamado venv(puede nombrarlo como desee): `python3 -m venv venv`.
4. Activar el entorno virtual: antes de instalar los paquetes, es necesario activar el entorno virtual. Para ello, utilice el comando `source venv/bin/activate`.
5. Instalar paquetes: ahora que su entorno virtual está activo, puede instalar paquetes mediante `pip`. Para instalar paquetes desde el archivo `requirements.txt`, utilice `pip install -r requirements.txt`.
6. Desactivar el entorno virtual: cuando hayas terminado, puedes desactivar el entorno virtual escribiendo `deactivate`.

Para usuarios de Windows:

1. Abrir el símbolo del sistema: puede buscarlo `cmd` en el menú Inicio.
2. Vaya a la carpeta de su proyecto: use el comando `cd` para cambiar el directorio a la carpeta de su proyecto. Por ejemplo: `cd path\to\your\project`.
3. Crear el entorno virtual: utilice el siguiente comando para crear un entorno virtual llamado `venv`: `python -m venv venv`.
4. Activar el entorno virtual: Para activar el entorno virtual en Windows, utilice `.\venv\Scripts\activate`.
5. Instalar paquetes: Con el entorno virtual activo, instale los paquetes necesarios: `pip install -r requirements.txt`.
6. Desactivar el entorno virtual: Para salir del entorno virtual, simplemente escriba: `deactivate`.

A continuación se ofrecen algunos consejos adicionales sobre la configuración:

* Asegúrese siempre de que su Python esté actualizado para evitar problemas de compatibilidad.
* Recuerda activar tu entorno virtual cada vez que trabajes en el proyecto.
* El archivo `requirements.txt` debe estar en el mismo directorio donde crea su entorno virtual, o debe especificar la ruta al mismo cuando utilice `pip install -r`.

Se asume que tiene acceso a una cuenta de desarrollador de OpenAI, ya que **OPENAI_API_KEY** debe configurarse como una variable de entorno en cualquier ejemplo que importe la biblioteca OpenAI, para la que usamos la versión 1.0. Puede encontrar instrucciones de inicio rápido para configurar su entorno de desarrollo en la documentación de OpenAI en su sitio web.

También debe asegurarse de que la facturación esté habilitada en su cuenta de OpenAI y de que se haya adjuntado un método de pago válido para ejecutar parte del código incluido en el libro. Los ejemplos del libro utilizan GPT-4 cuando no se indica, aunque cubrimos brevemente el modelo competidor [Claude 3](https://www.anthropic.com/news/claude-3-family) de Anthropic, así como el código abierto de Meta [Llama 3](https://www.llama.com/) y [Google Gemini](https://gemini.google.com/) .

Para la generación de imágenes, utilizamos [Midjourney](https://www.midjourney.com/home), para lo cual necesitas una cuenta de Discord para registrarte, aunque estos principios se aplican igualmente a **DALL-E 3** (disponible con una suscripción a ChatGPT Plus o a través de la API) o **Stable Diffusion** (disponible como [API](https://platform.stability.ai/) o puede [ejecutarse localmente](https://huggingface.co/blog/stable_diffusion) en tu computadora si tiene una GPU). Los ejemplos de generación de imágenes en este libro utilizan Midjourney v6, Stable Diffusion v1.5 (ya que muchas extensiones todavía son compatibles solo con esta versión) o Stable Diffusion XL , y especificamos las diferencias cuando esto es importante.

Proporcionamos ejemplos que utilizan bibliotecas de código abierto siempre que sea posible, aunque incluimos proveedores comerciales cuando corresponde; por ejemplo, el Capítulo 5 sobre bases de datos vectoriales muestra tanto **FAISS**(una biblioteca de código abierto) como **Pinecone**(un proveedor pago). Los ejemplos que se muestran en el libro deberían poder modificarse fácilmente para modelos y proveedores alternativos, y las habilidades que se enseñan son transferibles. El Capítulo 4 sobre generación avanzada de texto se centra en el marco **LLM LangChain**, y el Capítulo 9 sobre generación avanzada de imágenes se basa en la interfaz de usuario web de difusión estable de código abierto de **AUTOMATIC1111**.

### Convenciones utilizadas en este libro

En este libro se utilizan las siguientes convenciones tipográficas:

*Italic*

Indica nuevos términos, URL, direcciones de correo electrónico, nombres de archivos y extensiones de archivos.

`Constant width`

Se utiliza para listados de programas, así como dentro de párrafos para hacer referencia a elementos del programa, como nombres de variables o funciones, bases de datos, tipos de datos, variables de entorno, declaraciones y palabras clave.

`Constant width bold`

Muestra comandos u otro texto que el usuario debe escribir literalmente.

`Constant width italic`

Muestra texto que debe reemplazarse con valores proporcionados por el usuario o por valores determinados por el contexto.

**CONSEJO**

Este elemento significa un consejo o sugerencia.

**NOTA**

Este elemento significa una nota general.

**ADVERTENCIA**

Este elemento indica una advertencia o precaución.

A lo largo del libro reforzamos lo que llamamos los Cinco Principios de la Incitación, identificando qué principio es más aplicable al ejemplo en cuestión. Puede consultar el Capítulo 1, que describe los principios en detalle.

**NOMBRE DEL PRINCIPIO**

Esto explicará cómo se aplica el principio al ejemplo o sección de texto actual.

## Usando ejemplos de código

El material complementario (ejemplos de código, ejercicios, etc.) está disponible para descargar en https://oreil.ly/prompt-engineering-for-generative-ai.

Si tiene una pregunta técnica o un problema al utilizar los ejemplos de código, envíe un correo electrónico a bookquestions@oreilly.com .

Este libro está aquí para ayudarle a hacer su trabajo. En general, si se ofrece código de ejemplo con este libro, puede usarlo en sus programas y documentación. No necesita ponerse en contacto con nosotros para solicitar permiso a menos que esté reproduciendo una parte importante del código. Por ejemplo, escribir un programa que utilice varios fragmentos de código de este libro no requiere permiso. Vender o distribuir ejemplos de los libros de O'Reilly sí requiere permiso. Responder a una pregunta citando este libro y citando código de ejemplo no requiere permiso. Incorporar una cantidad significativa de código de ejemplo de este libro en la documentación de su producto sí requiere permiso.

Agradecemos la atribución, pero por lo general no la exigimos. Una atribución suele incluir el título, el autor, el editor y el ISBN. Por ejemplo: “ Ingeniería rápida para la IA generativa por James Phoenix y Mike Taylor (O'Reilly). Copyright 2024 Saxifrage, LLC y Just Understanding Data LTD, 978-1-098-15343-4”.

Si considera que su uso de ejemplos de código no se considera un uso justo o no está dentro del permiso otorgado anteriormente, no dude en contactarnos a permissions@oreilly.com .

### Aprendizaje en línea de O'Reilly

**NOTA**

Durante más de 40 años, O'Reilly Media ha brindado capacitación, conocimiento y perspectiva sobre tecnología y negocios para ayudar a las empresas a tener éxito.

Nuestra red única de expertos e innovadores comparte sus conocimientos y experiencia a través de libros, artículos y nuestra plataforma de aprendizaje en línea. La plataforma de aprendizaje en línea de O'Reilly le brinda acceso a pedido a cursos de capacitación en vivo, rutas de aprendizaje en profundidad, entornos de codificación interactivos y una vasta colección de textos y videos de O'Reilly y más de 200 editoriales. Para obtener más información, visite https://oreilly.com .

Cómo contactarnos
Por favor, dirija sus comentarios y preguntas sobre este libro al editor:

O'Reilly Media, Inc.
1005 Gravenstein Highway Norte
Sebastopol, CA 95472
800-889-8969 (en Estados Unidos o Canadá)
707-827-7019 (internacional o local)
707-829-0104 (fax)
soporte@oreilly.com
https://www.oreilly.com/about/contact.html
Contamos con una página web para este libro, donde enumeramos erratas, ejemplos y cualquier información adicional. Puede acceder a esta página en https://oreil.ly/prompt-engineering-generativeAI .

Para noticias e información sobre nuestros libros y cursos, visita https://oreilly.com .

Encuéntrenos en LinkedIn: https://linkedin.com/company/oreilly-media .

Míranos en YouTube: https://youtube.com/oreillymedia .

### Expresiones de gratitud

Nos gustaría agradecer a las siguientes personas por su contribución al realizar una revisión técnica del libro y su paciencia al corregir un objetivo que se mueve rápidamente:

* Mayo Oshin, colaborador inicial de LangChain y fundador de SeinnAI Analytics

* Ellis Crosby, fundador de Scarlett Panda y la agencia de inteligencia artificial Incremen.to

* Dave Pawson, autor de O'Reilly XSL-FO

* Mark Phoenix, ingeniero de software senior

* Aditya Goel, consultor de GenAI

* Sanyam Kumar, director asociado, ciencia de datos, Genmab

* Lakshmanan Sethu, TAM, Soluciones Gen AI, Google

* Janit Anjaria, directora general del personal, Aurora Innovation Inc.

También agradecemos a nuestras familias por su paciencia y comprensión y nos gustaría asegurarles que todavía preferimos hablar con ellos a través de ChatGPT.
