# 1 Introducción a la Creación de Sitios Web con ChatGPT

Este capítulo cubre

* Presentamos ChatGPT
* Comprender qué tipos de páginas web puedes crear con la ayuda de ChatGPT
* Conociendo las limitaciones de crear páginas web con ChatGPT
* Descubra cómo ChatGPT le permite crear sus propias páginas web

El escritor de ciencia ficción británico Arthur C. Clarke formuló una vez tres verdades que llegaron a conocerse como las tres leyes de Clarke, la tercera de las cuales es la que se cita con más frecuencia: **"Cualquier tecnología suficientemente avanzada es indistinguible de la magia"**. Si siempre ha querido crear páginas web pero la tecnología lo intimidó, entonces la premisa de este libro (que puede crear su propio sitio web con la ayuda de ChatGPT) puede parecerle magia. Eso no es una sorpresa, porque si alguna tecnología en la memoria reciente merece la descripción de "suficientemente avanzada", es ChatGPT y otras llamadas IA generativas similares: aplicaciones de inteligencia artificial que pueden crear poesía, prosa y, sí, páginas web.

En este capítulo, mi objetivo es desmitificar ChatGPT y hacer que parezca un poco menos mágico y mucho más práctico. En las siguientes páginas, obtendrá una breve explicación de los conceptos básicos de ChatGPT, una descripción general de los tipos de páginas que puede crear con la ayuda de ChatGPT (y, para equilibrar, algunas notas sobre los tipos de páginas que no puede crear) y un recorrido detrás de escena y afortunadamente no técnico sobre cómo puede usar ChatGPT para realizar la hazaña aparentemente mágica, pero en realidad meramente matemática, de tomar una simple solicitud escrita y convertirla en una página web completa y lista para navegar.

## 1.1 ¿Qué es ChatGPT?

A menos que hayas estado encerrado en una ermita durante el último año o dos, probablemente hayas oído hablar de GPT y/o ChatGPT, los agentes de inteligencia artificial que han conquistado el mundo (o, al menos, esa parte del mundo que presta atención a las redes sociales). Sin embargo, saber sobre ChatGPT es una cosa, pero saber qué es realmente ChatGPT es otra muy distinta.

Para que te hagas una idea de qué es ChatGPT y qué hace, te resultará útil desglosar cada componente del nombre para ver qué significa. Comenzaré con GPT:

* **G** — La G en GPT significa ***generative - generativo***, lo que significa que GPT puede crear (o generar) contenido nuevo. GPT es un **Large Language Model (LLM) - Modelo de Lenguaje Grande**, lo que generalmente significa que está diseñado para generar texto, como ensayos, historias e incluso poemas. Más específicamente para nuestros propósitos en este libro, las capacidades generativas de GPT también se extienden al código de programación, particularmente el código que sustenta las páginas web.

* **P** — La P en GPT significa ***pretrained - preentrenado***, lo que significa que GPT fue expuesto a enormes cantidades de texto (a eso se refiere el término “large - grande” en el *Large Language Model*). Durante este proceso de preentrenamiento, GPT aprendió los patrones y las estructuras del lenguaje, como por ejemplo cómo se forman las oraciones normalmente. En particular, dado un texto existente, el preentrenamiento permite a GPT predecir qué palabra o frase suele venir a continuación. En cierto sentido, eso es todo lo que GPT hace realmente: *¡predecir la siguiente palabra!* GPT también fue entrenado en un conjunto inimaginablemente grande de datos de programación; por lo tanto, debido a que el código de programación suele ser más predecible que la escritura normal, GPT se destaca en la generación de código.

* **T**: la T de GPT significa ***transformer - transformador***, lo que significa que GPT puede tomar una entrada de texto (como un request para crear una página web) y transformar ese texto en sus componentes más importantes mientras ignora o da menor prioridad a los componentes menos importantes del texto. Esto permite que GPT produzca resultados con mayor relevancia y precisión.

La parte de **Chat** de ChatGPT significa que *tienes acceso conversacional a GPT, lo que significa que puedes intercambiar mensajes con GPT más o menos como lo haces en una conversación de chat*. En el contexto de la creación de páginas web, estas "conversaciones" implicarán que solicites algún componente de la página y ChatGPT proporcione el código necesario. Sin embargo, ChatGPT también tiene una capacidad limitada para "recordar" mensajes anteriores en la conversación actual, lo que ocasionalmente puede ser útil en tus tareas de creación de sitios web.

Mientras escribo esto, hay dos versiones principales de GPT disponibles: **GPT-3.5**, lanzada en ***noviembre de 2022***, y **GPT-4**, lanzada en ***marzo de 2023***. Si usa la aplicación OpenAI (que analizaremos en un momento) con una cuenta gratuita de ChatGPT (obtenga más información en el apéndice A) o sin cuenta, solo tendrá acceso a GPT-3.5; si tiene una cuenta de paga de ChatGPT Plus y usa la aplicación OpenAI, tendrá acceso tanto a GPT-3.5 como a GPT-4.

Para acceder a ChatGPT y ayudarle a crear páginas web, tiene tres opciones preferidas:

* **OpenAI app**: esta es una aplicación en línea operada por OpenAI, los creadores de GPT y ChatGPT. La aplicación está disponible en https://chat.openai.com . No necesita una cuenta OpenAI para acceder a ella, pero tener una cuenta elimina ciertas restricciones (consulte el apéndice A para saber cómo crear una cuenta para acceder a ChatGPT). Si tiene una cuenta de paga ChatGPT Plus, puede elegir entre GPT-3.5 y GPT-4, como se muestra en la figura1.1.

   <img width="827" alt="image" src="https://github.com/user-attachments/assets/6ec26861-ab74-4482-afe3-d14e40c409f8">

   **Figura 1.1 Con una cuenta ChatGPT Plus, la aplicación OpenAI le brinda acceso tanto a GPT-3.5 como a GPT-4.**

   Mi ChatGPT.

   <img width="1512" alt="image" src="https://github.com/user-attachments/assets/ee290dee-ee54-41b9-a7b3-22875a71e430" />

   <img width="1512" alt="image" src="https://github.com/user-attachments/assets/98640033-303a-4d53-a28d-f7ee97d3f604" />

   **Figura 1.1 Con una cuenta ChatGPT Plus, la aplicación OpenAI le brinda acceso tanto a GPT-3.5 como a GPT-4.**

* **Microsoft Copilot en Bing**: esta es la versión mejorada con IA del motor de búsqueda de Microsoft, que ofrece una función de chat que utiliza GPT-4 en segundo plano y también tiene acceso a la web. Vaya a https://bing.com y seleccione la pestaña Copilot para comenzar, como se muestra en la figura 1.2. Tenga en cuenta que no necesita una cuenta ChatGPT para usar Bing Copilot. (Si tiene dudas sobre las tres opciones de "estilo de conversación", las explico en detalle en el apéndice A).

   <img width="782" alt="image" src="https://github.com/user-attachments/assets/973439ba-f3c7-456a-930c-67cd99a4a0f6">

   **Figura 1.2 Utilice Bing Copilot para trabajar con GPT-4.**

  Bing Copilot

  <img width="1512" alt="image" src="https://github.com/user-attachments/assets/b867587d-4803-4170-9ee2-cd3f1c238105" />

   **Figura 1.2 Utilice Bing Copilot para trabajar con GPT-4.**
  
* **Microsoft Copilot**: esta es la implementación independiente de la versión de Microsoft de ChatGPT, que utiliza el modelo GPT-4. Vaya a https://copilot.microsoft.com, como se muestra en la figura 1.3. Tenga en cuenta que no necesita una cuenta de ChatGPT para usar Microsoft Copilot, pero sí necesita una cuenta de Microsoft. (Nuevamente, explico las tres opciones de "estilo de conversación" en el apéndice A).

   <img width="829" alt="image" src="https://github.com/user-attachments/assets/4e4c8fb1-bbd6-42f0-be6c-01d741f4ef5c">

   **Figura 1.3 Si tiene una cuenta Microsoft, utilice Copilot para trabajar con GPT-4.**

   Mi Microsoft Copilot

   <img width="1512" alt="image" src="https://github.com/user-attachments/assets/d0ec9fd0-b3fd-4e4e-8963-b6b0e61d4297" />

   **Figura 1.3 Si tiene una cuenta Microsoft, utilice Copilot para trabajar con GPT-4.**

**Nota**: Hay muchas otras formas de acceder a ChatGPT, ya sea de forma directa o indirecta. Por ejemplo, existen aplicaciones ChatGPT para iOS y Android. Estos otros métodos están bien para jugar con ChatGPT, pero para crear páginas web, es mejor quedarse con la aplicación OpenAI, Bing Copilot o Microsoft Copilot porque le brindan un acceso fácil al código generado por ChatGPT.

¿Qué método deberías usar para acceder a ChatGPT? Cuando se trata de crear el código de página web relativamente simple que se cubre en este libro, no importa tanto. GPT-4 tiende a producir un código más "moderno", lo que generalmente es algo bueno. (Sin embargo, esto puede significar que tus páginas no funcionen bien en navegadores más antiguos como Internet Explorer. ¿Mi consejo? ¡Ignora esos navegadores antiguos y adopta la web moderna!) Si no tienes una cuenta ChatGPT y no quieres las restricciones que la aplicación Open AI impone a quienes no tienen una cuenta, Bing Copilot es el camino a seguir.

## 1.2 ChatGPT permite a cualquier persona crear páginas web

Nunca he tenido la suerte de contar con un asistente, pero me imagino que es un buen negocio. Después de todo, ¿a quién no le gustaría tener a alguien dedicado a realizar tareas necesarias pero mundanas como organizar reuniones virtuales, organizar vuelos, hoteles y otros detalles de viaje y armar presentaciones? Tener un asistente es aún más valioso si no sabes (y no quieres saber) cómo organizar una reunión de Zoom, navegar por el sitio web de Expedia o crear una presentación de PowerPoint.

Sin duda, estas tareas no son triviales, pero parecen ejercicios de jardín de infantes en comparación con el diseño, la codificación y la implementación de una página web o incluso de un sitio web completo. Por supuesto, existen plantillas y herramientas de creación de páginas similares que ofrecen páginas web listas para usar, pero los resultados casi siempre son decepcionantes porque solo se obtiene un control limitado sobre el resultado. Se tiene un tema excelente para un sitio y se tiene una imagen mental de cómo debería verse, pero hay una barrera entre usted y su visión: el código de la página web.

Los tres tipos principales de código de páginas web (HTML, CSS y JavaScript) se encuentran en una pronunciada curva de aprendizaje: una pendiente que para muchas personas es una subida demasiado onerosa cuando todo lo que quieren es crear una página o tres para sí mismos o para un equipo, un pasatiempo, un proyecto, una organización benéfica o un evento. Si desea crear una presencia en la web pero se ha sentido decepcionado con las soluciones prefabricadas disponibles o se estremeció ante la idea de aprender HTML, CSS y JavaScript, no todo está perdido, porque ahora puede "contratar" (gratis, si lo prefiere) un asistente para generar código de página web según sus especificaciones exactas. Ese asistente es ChatGPT, que se encuentra en el otro lado de la curva de aprendizaje del desarrollo web y está listo, dispuesto y es muy capaz de ayudarlo a convertir su visión de página web en una realidad. Al proporcionarle al modelo algunas instrucciones simples y en un lenguaje sencillo, puede convencer a ChatGPT para que traduzca esas instrucciones en código de página web funcional. Luego, puede cargar ese código en la web (ChatGPT incluso puede ayudarlo con ese paso) y ¡listo!

Vale, quizá no sea tan fácil (de lo contrario, no habría tenido mucho sentido escribir el resto de este libro), pero el procedimiento básico es tan sencillo como lo he explicado aquí.

## 1.3 Comprender los tipos de páginas que puedes (y no puedes) crear

A estas alturas, puede que estés pensando que transformar ChatGPT en un asistente robótico para la creación de sitios web debe tener algún tipo de trampa. Después de todo, para los no iniciados, crear páginas web parece una tarea casi por excelencia compleja, por lo que afirmar que puedes delegar casi todo ese trabajo a un modelo de IA sin tener que aprender a codificar tú mismo debe tener una trampa bastante grande. Sorprendentemente, no hay tales moscas en la sopa de ChatGPT, pero hay algunas salvedades que tener en cuenta.

En primer lugar, debes saber que los tipos de páginas web que se crean con mayor facilidad con la ayuda de ChatGPT son los que se describen como estáticos en el sector del desarrollo web. Una página web estática es aquella que contiene texto y datos que no cambian después de que se carga la página. Puede parecer restrictivo, pero en realidad no hay límite en los tipos de páginas estáticas que puedes pedirle a ChatGPT que te ayude a crear. Aquí tienes 10 ideas:

* Personal home page - Página home Personal
* Information page for a team, organization, or event - Página de información de un equipo, organización o evento
* Product landing page - Página del producto
* Hobby page - Página de pasatiempos
* Photo gallery - Galería de fotos
* Portfolio page - Página de portafolio
* Post page (essay, review, fan fiction, or whatever) - Página de publicación (ensayo, reseña, fan fiction o lo que sea)
* Top-10 list - Lista de los 10 mejores
* How-to instructions - Instrucciones de cómo hacerlo
* Travel guide - Guía de viaje

Apuesto a que puedes crear fácilmente 10 páginas más por tu cuenta. Estos son los tipos de páginas que aprenderás a crear con la ayuda de ChatGPT en este libro. Y la gran noticia es que, a menos que optes por una suscripción de paga a ChatGPT Plus, puedes hacer todo, desde acceder a ChatGPT hasta guardar el código generado e implementar tus páginas, completamente gratis.

En segundo lugar, una de las características de los tipos de páginas que acabo de enumerar es que solo requieren lo que los expertos en desarrollo web llaman código frontend, es decir, código (HTML, CSS y JavaScript) que se ejecuta en el navegador web. Algo muy diferente es el código backend, es decir, código que se ejecuta en un servidor web y que generalmente se utiliza para proporcionar texto y datos para una página web dinámica, donde el texto y los datos cambian sobre la marcha.

Técnicamente, es posible pedirle a ChatGPT que proporcione dicho código de backend, pero en términos prácticos, estamos hablando de tareas de configuración que son un orden de magnitud más complicadas, mucho más complejas en términos de organizar e implementar el código generado, enormes riesgos de seguridad porque los servidores web son vulnerables a muchos tipos de ataques y se deben usar técnicas de codificación avanzadas para fortalecer el código de backend contra usuarios maliciosos, y casi siempre costos adicionales porque las cuentas de alojamiento web que permiten el acceso a un servidor generalmente requieren un plan de suscripción pago. Por todas estas razones, no aprenderá a usar ChatGPT para generar código de backend en este libro.

## 1.4 Cómo usar ChatGPT para crear páginas web

**Fritterware** es un antiguo término informático que se refiere a cualquier software que seduce al usuario para que pase cantidades excesivas de tiempo jugando con las funciones y opciones del programa. Una vez que tenga una cuenta de ChatGPT (que cubro en el apéndice A; sin embargo, recuerde que tener una cuenta es opcional), tendrá acceso instantáneo a uno de los mejores programas de fritterware jamás inventados. Es fácil dedicar un montón de tiempo a hacer que ChatGPT haga todo tipo de cosas divertidas y tontas, pero con el tiempo, querrá dejar de perder el tiempo y comenzar a crear.

El proceso creativo de ChatGPT varía según lo que estés creando, pero para nuestros propósitos aquí, necesitas conocer el proceso general para que ChatGPT te ayude a crear páginas web. La versión simplificada de ese proceso se resume en la figura 1.4. Las siguientes secciones explican cada paso y el capítulo 2 te muestra un ejemplo completo del proceso.

<img width="843" alt="image" src="https://github.com/user-attachments/assets/3a80f365-7ddf-4315-aede-632726e78fc8">

**Figura 1.4 Un diagrama simplificado del proceso que utiliza para que ChatGPT le ayude a crear una página web**

### 1.4.1 Prompting ChatGPT

El proceso siempre comienza con un request que especifica lo que desea que ChatGPT cree para usted. Este request se denomina **prompt**. Cuando inicia sesión en la aplicación ChatGPT (consulte la figura 1.1) o navega a Bing Copilot (consulte la figura 1.2), verá un cuadro de texto donde escribe su **prompt**.

Los mensajes pueden ser tan simples como una sola oración (como se muestra en la figura 1.3) o tan complejos como varios párrafos. Sin embargo, el cielo no es el límite aquí, ya que la mayoría de las versiones de ChatGPT solo aceptan hasta 4000 caracteres por mensaje. Eso es aproximadamente unas 500 palabras, lo que debería ser más que suficiente para la mayoría de los mensajes de creación web.

No es una exageración decir que el prompting  ChatGPT es el paso más importante porque la calidad del prompt determina directamente la calidad del resultado que devuelve ChatGPT. En cierto sentido, este libro trata de proporcionarle prompts de alta calidad que hagan que ChatGPT realice tareas específicas de creación de páginas web. También dedico bastantes páginas en el apéndice C a explicar algunas prácticas recomendadas asociadas con prompting ChatGPT (un proceso llamado **prompt engineering** por los entendidos).

**Advertencia** Aunque es cierto que ChatGPT es un modelo de calidad de entrada y calidad de salida, como todos los modelos de lenguaje grandes, es propenso a producir ocasionalmente resultados inutilizables o francamente extraños incluso cuando el prompt es bueno. Hablo sobre algunas formas de solucionar estos problemas en el apéndice A.

### 1.4.2 Visualización de los resultados de ChatGPT

Cuando envías tu prompt, ChatGPT se pone a trabajar y normalmente comienza a “escribir” su respuesta en unos pocos segundos. La Figura 1.5 muestra un ejemplo de respuesta al siguiente mensaje:

<img width="826" alt="image" src="https://github.com/user-attachments/assets/3783a264-2679-4610-b465-dc0acccae03f">

```text
Write web page code to display “Hello World!” in a large font.
```

```text
Escriba el código de la página web para mostrar “¡Hola mundo!” en una fuente grande.
```

<img width="838" alt="image" src="https://github.com/user-attachments/assets/4376490e-54a9-4279-a35e-118b299ffb51">

**Figura 1.5 En este ejemplo, la respuesta de ChatGPT al mensaje incluye el código solicitado.**

Como se muestra en la figura 1.5, el resultado en este caso consiste en una respuesta amigable a su solicitud seguida de un cuadro con el título `html` que incluye el código de la página web que se solicitó. Este código sin duda le parecerá un galimatías, pero créame cuando le digo que hace exactamente lo que la solicitud le pidió: muestra el mensaje `Hello World!` en una fuente grande (en este caso, de 48 puntos). Tenga en cuenta que, por diversas razones técnicas, ChatGPT puede no devolver el mismo código cada vez que ejecute la solicitud. Sin embargo, debido a que a menudo hay varias formas de lograr el mismo resultado con HTML y CSS, el código generado seguirá produciendo una página web que se ve igual (o al menos muy similar).

💻 Mi ejemplo

![image](https://github.com/user-attachments/assets/5e8f793a-a565-430b-9dc5-c2d1c7fd3d76)

https://webdesignplayground.io/

![image](https://github.com/user-attachments/assets/69ca7e60-3fed-41e4-b52a-d6336f2b8c0b)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello World</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
        }
        h1 {
            font-size: 5rem;
            color: #333;
        }
    </style>
</head>
<body>
    <h1>Hello World!</h1>
</body>
</html>
```

### 1.4.3 Obtener el código en un archivo

El ejemplo que utilicé en la sección anterior es sencillo, sin duda, pero aún así es más que asombroso que, a los pocos segundos de enviar este prompt, ChatGPT haya generado un código de página web funcional que satisfizo la request. A medida que trabaje en sus proyectos de páginas web con ChatGPT a su lado, por así decirlo, esa sensación de asombro surgirá una y otra vez a medida que el modelo genere rápidamente y sin esfuerzo el código que solicitó.

Sin embargo, el código de la página web producido por ChatGPT, sin importar lo preciso que sea o lo adecuado que sea para sus necesidades, no hace nada. Esto se debe a que, por sí solo, el código de la página web es inerte; es solo una colección de palabras y símbolos de apariencia extraña. Para que el código de la página web cobre vida, debe mostrarse en un navegador web; y antes de poder hacer eso, debe colocar el código en un archivo al que pueda acceder un navegador.

El Apéndice A analiza en profundidad los detalles de los archivos de páginas web. La Figura 1.6 muestra el código generado por ChatGPT (consulte la Figura 1.5) pegado en un archivo HTML, que se ha guardado como `index.html`. En este punto, puede cargar el archivo HTML guardado en su navegador web favorito (consulte el capítulo 2 para obtener más detalles), pero un verdadero proyecto web requiere un paso más: implementar el código en la propia web.

<img width="675" alt="image" src="https://github.com/user-attachments/assets/03d041e8-d98f-4d4a-a4e8-dd2c2c3fe94a">

**Figura 1.6 El código copiado de ChatGPT y guardado en un archivo HTML**

💻 Mi ejemplo.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/6ae2d379-0100-43c9-9be8-c69161d99e96" />


### 1.4.4 Despliegue del archivo HTML

La única forma de que otras personas puedan ver sus páginas es que usted las coloque en la Web. Para los proyectos relativamente simples que crea en este libro, este proceso de despliegue implica copiar el archivo o los archivos que ChatGPT le ayudó a crear a un servicio que aloja páginas web. En el apéndice B explico este proceso con más detalle, pero en su mayor parte, solo significa cargar la carpeta en la que ha almacenado los archivos de su página web al servidor. La Figura 1.7 muestra un ejemplo del proceso en el que arrastré la carpeta `hello-world` desde la ventana del Finder a la derecha y estoy a punto de soltarla en la ventana de la izquierda. Una vez cargados los archivos de su página web, puede verlos de inmediato en su navegador web favorito, como se muestra en la Figura 1.8.

<img width="846" alt="image" src="https://github.com/user-attachments/assets/3a3fb3fe-d7fd-41e5-923b-5415df2156a2">

**Figura 1.7 Con algunos servicios, como Netlify que se muestra aquí, la implementación es una cuestión simple de arrastrar y soltar.**

<img width="791" alt="image" src="https://github.com/user-attachments/assets/1c7d81ff-f907-4e76-b7ce-9575fb7a677d">

**Figura 1.8 La página web creada por ChatGPT está en la web.**

Las secciones anteriores te han guiado a través de un proceso ***prompt-copy-save-deploy*** (solicitud-copia-guardado-implementación) que, creo que estarás de acuerdo, tiene una sencillez satisfactoria (y más que sorprendente). Sin embargo, no todos tus proyectos serán tan sencillos, en particular si te aventurarás a crear páginas web que vayan mucho más allá de decir "¡Hola mundo!". Para estos proyectos más ambiciosos, la mayoría de las veces utilizarás dos técnicas adicionales: repetir el proceso de ***prompt-copy-save-deploy*** para crear varias páginas y componentes de página; y refinar y revisar tus solicitudes de ChatGPT.

💻 Mi instalación.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/567a65ee-0dfe-40f1-bfd1-56723c7462ff" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/7d0eba77-9755-4338-913d-e2460a5b2846" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/ec4493d9-5b10-4baf-a4fd-cb52811adaac" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/df18f30a-be7c-4148-9c82-b937649fe2bf" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/13e52f0c-3966-4e10-84dd-e26052ee3e8a" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/225cb0fe-9a5d-4b56-b3c4-bcffa1a4e3cf" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/61be5e93-e3e4-4d33-8e1d-59630f2ffac3" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/0a3a8f49-288f-42d4-85f1-8bbb4feda73e" />

https://graceful-melba-e262b8.netlify.app/

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/1a7e9a9e-e3f6-4a80-bd89-d63df4dad939" />

### 1.4.5 Repetir según sea necesario

En tu carrera como creador de páginas web, será relativamente raro que aparezca un único mensaje que cree una única página web. Es mucho más probable que tengas que realizar el ciclo de mensaje-copia-guardado-implementación varias veces antes de terminar con todo el contenido que necesitas. Hay dos escenarios a tener en cuenta:

* **Creación de varias páginas**: muchos sitios web constan de una sola página, pero el caso más común es un sitio web que consta de varias páginas. Incluso un sitio web modesto puede constar de una página de inicio, una página Acerca de(About) (que describe su sitio), una página de Contacto(Contact) (que enumera las distintas formas en que los visitantes del sitio pueden ponerse en contacto con usted) y páginas separadas para contenido como ensayos, fotos y portafolios. Para un sitio web de este tipo, deberá repetir el ciclo de solicitud-copia-guardado-implementación para cada página.

* **Creación de varios componentes para una sola página**: la mayoría de las páginas web modernas constan de varios componentes, como un encabezado, una barra de navegación o un menú, un área de contenido, una barra lateral y un pie de página. Es posible incluir todos los componentes que necesita en un solo mensaje, pero obtendrá resultados más satisfactorios si utiliza un mensaje independiente para cada componente. En este caso, el proceso se convierte en uno en el que se repite la parte del ciclo de mensaje-copia-guardado para cada componente, y el código copiado se inserta en el mismo archivo HTML. Luego, implementa el código solo después de haber agregado todos los componentes de la página.

Si todo esto parece un poco abstracto o confuso ahora, no se preocupe: el resto de este libro tiene como objetivo que se sienta cómodo con los aspectos específicos de la creación de múltiples páginas y componentes de página.

### 1.4.6 Refinar y revisar sus indicaciones

El proceso de creación de páginas asistido por ChatGPT que se muestra en la figura 1.3 funciona para páginas web sencillas y para aquellas ocasiones en las que ChatGPT cumple con su solicitud. Pero a medida que sus páginas web (y sus mensajes) se vuelvan más complejos, es casi seguro que tendrá que agregar algunos pasos más al proceso. He incluido estos pasos adicionales en el área sombreada del diagrama de proceso que se muestra en la figura 1.9.

<img width="559" alt="image" src="https://github.com/user-attachments/assets/640d2656-7526-40c0-98ea-d4621ef3f951">

**Figura 1.9 Refinamiento y revisión de las indicaciones de su página web**

A primera vista, parece un proceso mucho más complejo, pero en realidad, existen dos caminos adicionales que este nuevo proceso puede tomar. Estos dos caminos se presentan en forma de preguntas:

* **¿Es esto lo que querías?** Haces esta pregunta inmediatamente después de que ChatGPT genere el código que solicitaste en tu mensaje. Básicamente, estás examinando el código (lo mejor que puedes, de todos modos) para asegurarte de que hace el trabajo por ti. Si la respuesta es "Sí", pasas a la siguiente pregunta; si la respuesta es "No", perfeccionas el mensaje de alguna manera (por ejemplo, haciéndolo más específico) y vuelves a intentarlo.

* **¿Funciona?** Esta pregunta requiere que pruebes el código copiándolo y pegándolo en un sitio en línea diseñado para probar el código de páginas web, como describo en el apéndice A. Si el código es correcto, puedes guardarlo en un archivo HTML. Si el código es incorrecto de alguna manera, debes corregir el error revisando tu mensaje de alguna manera y luego volviéndolo a enviar; nuevamente, el apéndice A es el lugar al que debes acudir para obtener algunas sugerencias para la resolución de problemas.

Por supuesto, sería fantástico si ChatGPT generara un código increíble en todo momento. Y es fantástico que cada nueva versión de ChatGPT mejore no solo en la producción de código preciso, sino también en la creación de código que coincida incluso con indicaciones vagas o generales. Pero aunque ChatGPT pueda algún día generar código de página web perfecto en todo momento, todavía no ha llegado a ese punto, por lo que deberá refinar y revisar sus indicaciones para obtener las páginas que desea.

## Resumen

* GPT significa ***generativo*** (está diseñado para generar texto), ***preentrenado*** (fue expuesto a grandes cantidades de texto para aprender patrones y estructuras del lenguaje), ***transformador*** (analiza las solicitudes para dar mayor prioridad a los componentes más importantes).

* ChatGPT es una aplicación que permite el acceso conversacional a GPT a través de la aplicación OpenAI en https://chat.openai.com, a través de Bing Copilot en https://bing.com (seleccione la pestaña Copilot) o a través de Microsoft Copilot en https://copilot.microsoft.com .

* GPT ha sido entrenado en cantidades masivas de código de programación, incluido el código utilizado para crear páginas web: HTML, CSS y JavaScript. Esta capacitación permite a ChatGPT generar código de página web a partir de instrucciones en inglés simple.

* ChatGPT se utiliza mejor para crear páginas web estáticas que no requieren ni dependen de datos almacenados en un servidor web.

* ChatGPT le ayuda a crear páginas web utilizando un ciclo básico de solicitud-copia-guardado-implementación(prompt-copy-save-deploy), donde la solicitud(**prompt**) es la instrucción que le dice a ChatGPT qué tipo de página desea, copiar significa copiar(*copy*) el código generado por ChatGPT y pegarlo en un archivo, guardar(*save*) significa guardar el código como un archivo HTML e implementar(*deploy*) significa cargar el archivo HTML a un proveedor de alojamiento web.

* Para obtener mejores resultados, generalmente tendrás que refinar tus indicaciones para lograr que la estructura y el contenido de tu página sean correctos, y generalmente tendrás que revisar tus indicaciones para corregir problemas de la página.
