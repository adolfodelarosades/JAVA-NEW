# 4. Multimodal AI: Creación de un visualizador de Podcast con Whisper y DALL·E 3

Bruce Hopkins 1  
(1)
Beaverton, Oregón, Estados Unidos

<hr>

Ahora, introduzcamos un nuevo término: **multimodal AI**. En términos muy simples, los modelos de IA generativa pueden crear contenido en uno de cuatro formatos:

* Texto
* Audio
* Imágenes
* Video

Cada uno de esos formatos es un modo. La IA multimodal es el proceso de utilizar varios modelos de IA juntos para generar (o comprender) contenido donde la entrada es un tipo de modo y la salida es un tipo de modo diferente.

Tomemos como ejemplo el modelo Whisper de OpenAI. Si le proporcionamos audio, es capaz de crear una transcripción de todo lo que se dice en texto. Lo mismo se aplica a DALL⋅E. Si le proporcionas un mensaje de texto, puede generar una imagen de lo que has descrito.

En este capítulo, llevaremos la IA multimodal al siguiente nivel. Como ávido oyente de podcasts, a menudo me he preguntado cómo se verían el paisaje, las imágenes, los personajes, el tema o el fondo mientras escuchaba una historia muy envolvente en formato de audio.

Vamos a crear un visualizador de podcasts utilizando varios modelos de OpenAI. Hay algunos pasos involucrados, pero los resultados finales son sorprendentes. Mientras escuchaba un podcast sobre un tipo que cocinaba cosas increíbles con tofu (no lo critiques hasta que lo pruebes), el visualizador de podcasts mostró la imagen de la Figura 4-1.

<img width="684" alt="image" src="https://github.com/user-attachments/assets/5255442f-ffe9-470d-a2a5-bd75528af7cb">

**Figura 4-1 El resultado generado por IA de la visualización de un podcast sobre tofu utilizando los modelos GPT-4, Whisper y DALL·E**

Para que el código del Podcast Visualizer sea fácil de seguir, haremos las cosas por separado en los siguientes tres pasos:

* **Paso 1**: Tome un episodio de podcast y utilice el modelo Whisper para obtener una transcripción.

* **Paso 2**: Tome la transcripción resultante y utilice el modelo GTP-4 para describir los aspectos visuales de lo que se está discutiendo en el episodio del podcast.

* **Paso 3**: Tome la descripción resultante y utilice el modelo DALL⋅E para generar una imagen.

El código presentado aquí en este capítulo tiene toneladas de usos prácticos, por ejemplo:

* Si simplemente tienes curiosidad sobre cómo podrían verse las cosas en un episodio de podcast (que siempre es mi caso), puedes obtener una imagen visual representativa simple para asociarla con lo que estás escuchando.

* Para las personas con problemas de audición, es muy fácil convertir un podcast o un programa de radio en una presentación de diapositivas con imágenes. Esto mejora enormemente la accesibilidad del contenido.

* Para los podcasters, ahora pueden tener una forma sencilla de agregar una imagen o un elemento visual a cada uno de sus episodios. Esto es útil ya que los reproductores de podcasts como Apple Podcasts y Spotify permiten a los podcasters mostrar una sola imagen para asociarla con un episodio individual. Esto puede ayudar a generar interacción con sus oyentes.

### Presentamos el modelo Whisper de OpenAI

Ahora vamos a introducir otro término nuevo: Reconocimiento automático de voz (ASR, por sus siglas en inglés). El consumidor medio está muy familiarizado con esta tecnología debido a su integración en teléfonos móviles (por ejemplo, Siri para el iPhone) y altavoces inteligentes (por ejemplo, cualquier dispositivo Alexa). En esencia, la tecnología ASR convierte el lenguaje hablado en texto.

Susurroes el modelo de reconocimiento de voz de OpenAI y su precisión es sorprendentemente alta. El listado 4-1 es una transcripción de un episodio del popular podcast en español de DuoLingo, que hace que el idioma español sea fácil de entender para los oyentes angloparlantes al combinar el inglés y el español en una historia narrativa entrelazada. La transcripción se generó utilizando el modelo Whisper.

<img width="743" alt="image" src="https://github.com/user-attachments/assets/135ca45a-0df7-4e2d-ac53-290ff783b2ab">

```text
...I'm Martina Castro. Every episode we bring you fascinating, true stories to help you improve your Spanish listening and gain new perspectives on the world. The storyteller will be using intermediate Spanish and I'll be chiming in for context in English. If you miss something, you can always skip back and listen again. We also offer full transcripts at podcast.duolingo.com.
Growing up, Linda was fascinated with her grandmother, Erlinda. Erlinda was a healer or curandera, someone who administers remedies for mental, emotional, physical, or spiritual illnesses.
In Guatemala, this is a practice passed down orally through generations in the same family. Mal de ojo, or the evil eye, is considered an illness by many Guatemalans who believe humans have the power to transfer bad energy to others. Neighbors would bring their babies to Linda's grandmother when they suspected an energy imbalance. Su madre lo llevaba a nuestra casa para curarlo...
```

**Listado 4-1 El modelo Whisper realiza reconocimiento de voz para convertir audio en texto**

Si alguna vez has trabajado con un sistema de reconocimiento de voz (incluso con tecnologías sofisticadas como Siri y Alexa), sabrás que tiene problemas, por ejemplo:

* **El reconocimiento de voz tiene problemas con la puntuación**

  * ¿Has notado que nadie habla con signos de puntuación? En inglés, usamos cambios de tono o volumen para hacer una pregunta o dar una exclamación. También usamos pausas cortas y largas para las comas y los puntos.

* **El reconocimiento de voz tiene problemas con palabras y acentos extranjeros.**
  
   * Dependiendo de a quién le preguntes, hay al menos 170.000 palabras en inglés. Sin embargo, en el inglés conversacional, siempre usamos palabras extranjeras como:
   
      * Tsunami (origen japonés): Una gran ola marina a menudo causada por un terremoto.

      * Hors d'oeuvre (origen francés): Un aperitivo.

      * Lencería (origen francés): Ropa interior o ropa de dormir femenina.

      * Aficionado (origen español): Alguien que es muy apasionado por una actividad o tema específico.

      * Piñata (origen español): Una caja de dulces de colores brillantes para que los niños los golpeen sin descanso.

* **El reconocimiento de voz tiene problemas con los nombres**
  
   * Ciertos nombres de personas, empresas y sitios web a menudo pueden ser difíciles de escribir y comprender.

* **El reconocimiento de voz tiene problemas con los homófonos**
  
   * ¿Recuerdas esas palabras que suenan igual pero se escriben y significan de forma diferente? ¡El fantástico editor de este libro las conoce todas!

      * Would / Wood
      * Flour / Flower
      * Two / Too / To
      * They’re / There / Their
      * Pair / Pare / Pear
      * Break / Brake
      * Allowed / Aloud

Como puede ver en el Listado 4-1 , Whisper pudo comprender toda la puntuación del audio, identificar todas las palabras extranjeras (de las cuales había varias) y comprender los nombres, así como el nombre de la empresa ("duolingo") dentro de una URL. Por supuesto, si se dio cuenta, también pudo comprender la diferencia entre “wood - madera” y “would - querría”.

### Características y limitaciones del modelo Whisper

El modelo Whisper puede convertir audio hablado de los siguientes idiomas en texto:

* Afrikaans
* Arabic
* Armenian
* Azerbaijani
* Belarusian
* Bosnian
* Bulgarian
* Catalan
* Chinese
* Croatian
* Czech
* Danish
* Dutch
* English (of course!)
* Estonian
* Finnish
* French
* Galician
* German
* Greek
* Hebrew
* Hindi
* Hungarian
* Icelandic
* Indonesian
* Italian
* Japanese
* Kannada
* Kazakh
* Korean
* Latvian
* Lithuanian
* Macedonian
* Malay
* Marathi
* Maori
* Nepali
* Norwegian
* Persian
* Polish
* Portuguese
* Romanian
* Russian
* Serbian
* Slovak
* Slovenian
* Spanish
* Swahili
* Swedish
* Tagalog
* Tamil
* Thai
* Turkish
* Ukrainian
* Urdu
* Vietnamese
* Welsh

Así que, al final del día, podrá entender el audio hablado por usted y probablemente cualquier idioma hablado por sus amigos y colegas.

Los desarrolladores están limitados a no enviar más de 50 solicitudes por minuto al endpoint, por lo que esta restricción debe tenerse en cuenta si desea transcribir grandes cantidades de audio.

Whisper admite audio en formatos flac, mp3, mp4, mpeg, mpga, m4a, ogg, wav o webm. Independientemente del formato que utilice, el tamaño máximo de archivo para enviar al endpoint es de 25 MB.

Ahora bien, si no has trabajado mucho con archivos de audio, ten en cuenta que algunos formatos crean archivos REALMENTE GRANDES (por ejemplo, el formato wav) y otros crean archivos realmente pequeños (por ejemplo, el formato m4a). Por lo tanto, convertir tu archivo a un formato diferente puede ayudarte con la limitación de 25 MB. Sin embargo, más adelante en este capítulo, veremos el código de una herramienta que toma un solo archivo de audio grande y lo divide en varios archivos más pequeños.

### Transcriptions Endpoint

El Endpoint Transcriptions es un servicio REST que convierte audio en texto y solo es compatible con el modelo Whisper.

#### Creando la Request

En la Tabla 4-1 se enumeran todos los parámetros HTTP necesarios para llamar al Endpoint Transcriptions.

**Tabla 4-1 Los parámetros HTTP para el Endpoint Transcriptions**

<img width="854" alt="image" src="https://github.com/user-attachments/assets/5720a176-7b8c-46ce-845d-9e0ab7076c45">

**Nota**: ¡Presta mucha atención al tipo de contenido en la tabla anterior! A diferencia del Endpoint Chat que envía todos los parámetros de solicitud HTTP como un objeto JSON, el Endpoint Transcriptions solo acepta parámetros como elementos de datos de formulario. Si intentas enviar un objeto JSON con un formato correcto (o incluso con un formato deficiente), el Endpoint Transcriptions devolverá un error muy opaco.

#### Request Body (Multipart Form Data)

**Tabla 4-2 El Request Body para Whisperr**

<img width="908" alt="image" src="https://github.com/user-attachments/assets/3b346529-c0e1-4e55-9142-01d6de7f8c9e">

<img width="906" alt="image" src="https://github.com/user-attachments/assets/b64a99f3-77cc-4626-a596-9a380b6c9a64">

<img width="897" alt="image" src="https://github.com/user-attachments/assets/e3420fdf-8e6f-43ee-aeba-abbfee9aaf54">

<img width="908" alt="image" src="https://github.com/user-attachments/assets/7e0620de-d07c-4c8c-9174-defd260ff7cb">

<img width="909" alt="image" src="https://github.com/user-attachments/assets/6c3e4b56-66cf-4a85-830c-07832d354c09">

<img width="913" alt="image" src="https://github.com/user-attachments/assets/ff766dcc-f523-469e-85d0-038d0507d248">

<img width="910" alt="image" src="https://github.com/user-attachments/assets/b0f8d842-d75f-4f90-807f-b5506f89dbf2">

<img width="905" alt="image" src="https://github.com/user-attachments/assets/ab9a9a15-6a18-419b-ba2f-3b1cd1aad5d9">

<img width="907" alt="image" src="https://github.com/user-attachments/assets/1d22cdf3-9bec-49c8-adaf-f5e1f9ebd6d3">

<img width="909" alt="image" src="https://github.com/user-attachments/assets/d2af8c46-f3d7-4b6a-bb6f-bd2a37e5aa32">

<img width="903" alt="image" src="https://github.com/user-attachments/assets/55c37364-f4a3-4f53-b87b-4d6e7f79adca">

### Creación de una aplicación de utilidad para dividir archivos de audio: `AudioSplitter.java`

Por lo tanto, casi llegamos al punto en el que podemos invocar programáticamente el modelo Whisper mediante el Endpoint Transcriptions. Sin embargo, el modelo Whisper tiene una limitación de 25 MB por archivo.

Ahora bien, esto no es un problema si estás escuchando, por ejemplo, el podcast StarDate de la Universidad de Texas en Austin. Este podcast te ofrece una excelente visión de lo que puedes buscar en el cielo nocturno en aproximadamente 2 minutos de audio. Sin embargo, ese no es el caso de otros programas de audio que tienden a durar hasta una hora (o incluso más). En casos como ese, definitivamente superarás el límite de archivo de 25 MB.

Por lo tanto, programemos en pares con ChatGPT y usemos nuestra inteligencia humana para crear nuestra propia utilidad que tomará un solo archivo de audio y lo dividirá en varios archivos más pequeños.

**Nota**: En esta sección, presento una de las muchas posibilidades disponibles para segmentar un archivo de audio grande en fragmentos más pequeños. Por ejemplo, puedes usar aplicaciones de edición de audio populares (como la herramienta de código abierto **Audacity** o la herramienta con licencia Adobe **Audition**) para cortar manualmente un archivo grande en archivos más pequeños.

El listado 4-2 es el mensaje que envié a ChatGPT para obtener una aplicación básica que divida archivos de audio.

<img width="905" alt="image" src="https://github.com/user-attachments/assets/982c3205-9ae2-480c-8078-1d4e9083d861">

```text
System: You are a Java developer
User: Write an application that takes as input a single MP3 file and splits the file into contiguous segments no longer than 10 minutes. Name the file, "AudioSplitter.java"
```

**Listing 4-2 PROMPT. Using ChatGPT to Create the `AudioSplitter.java` App**

```text
Sistema : Eres un desarrollador de Java
Usuario : Escriba una aplicación que tome como entrada un único archivo MP3 y lo divida en segmentos contiguos de no más de 10 minutos de duración. Nombre el archivo "AudioSplitter.java"
```

**Listado 4-2 PROMPT. Uso de ChatGPT para crear la aplicación `AudioSplitter.java`**

Después de un poco de ida y vuelta, pude crear (como se muestra en el Listado 4-3 ) la aplicación `AudioSplitter.Java` que incluye mis ediciones a lo generado por ChatGPT.

<img width="923" alt="image" src="https://github.com/user-attachments/assets/f764566c-63c1-4347-bf83-2d7bce733194">

```java
import org.bytedeco.javacv.FFmpegFrameGrabber;
import org.bytedeco.javacv.FFmpegFrameRecorder;
import java.io.IOException;
public class AudioSplitter {
        public static void main(String[] args) {
        String inputFilePath = "path/to/file/sample.mp3";
        String outputDirectory = "path/to/folder/";
        int segmentDurationInSeconds = 600; // 10 minutes in seconds
        try (FFmpegFrameGrabber grabber = new FFmpegFrameGrabber(inputFilePath)) {
            grabber.start();
            long totalDurationInSeconds = (long) grabber.getLengthInTime() / 1000000; // Convert microseconds to seconds
            double frameRate = grabber.getFrameRate();
            long segmentStartTime = 0;
            long segmentEndTime;
            int segmentNumber = 1;
            while (segmentStartTime < totalDurationInSeconds) {
                String outputFilePath = outputDirectory + "segment_" + segmentNumber + ".mp3";
                try (FFmpegFrameRecorder recorder = new FFmpegFrameRecorder(outputFilePath, 0)) {
                    recorder.setAudioChannels(2);
                    recorder.setAudioCodecName("libmp3lame"); // Set the audio codec to MP3
                    recorder.setAudioBitrate(192000); // Adjust bitrate as needed
                    recorder.setSampleRate(44100); // Adjust sample rate as needed
                    recorder.setFrameRate(frameRate);
                    recorder.setFormat("mp3"); // Set the output format to MP3
                    recorder.start();
                    segmentEndTime = Math.min(segmentStartTime + segmentDurationInSeconds, totalDurationInSeconds);
                    grabber.setTimestamp(segmentStartTime * 1000000); // Set the grabber's timestamp to the start time in microseconds
                    while (grabber.getTimestamp() / 1000000 < segmentEndTime) {
                        recorder.record(grabber.grabSamples());
                    }
                }
                segmentStartTime = segmentEndTime;
                segmentNumber++;
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
        }
}
```

**Listado 4-3 RESPONSE. `AudioSplitter.java`**
