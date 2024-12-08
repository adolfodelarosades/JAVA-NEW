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

Dado que las libraries estándar de Java no tienen un amplio soporte para varios formatos multimedia, utilizamos una combinación de las libraries **FFmpeg** y **JavaCV** (ambas son gratuitas y de código abierto).

El objetivo es sencillo: dividir un archivo MP3 en segmentos contiguos de no más de 10 minutos de duración utilizando el lenguaje Java. En esta sencilla aplicación, realizamos los siguientes pasos:

* En primer lugar, especificamos la ruta del archivo de entrada, el directorio de salida y la duración del segmento deseado en segundos (10 minutos).

* A continuación, utilizamos **FFmpegFrameGrabber** para abrir el archivo MP3 de entrada y recopilar información sobre él, como la velocidad de cuadros, el códec de audio, la frecuencia de muestreo y más.

* Luego, iteramos a través del archivo MP3 de entrada, segmentándolo en partes más pequeñas de la duración especificada (10 minutos o menos). Para cada segmento, creamos un nuevo **FFmpegFrameRecorder**, configuramos sus parámetros y grabamos los fotogramas dentro de la duración del segmento.

* Por último, incrementamos el tiempo de inicio del segmento y el número de segmento para cada segmento hasta que hayamos procesado todo el archivo MP3 de entrada.

Para que esto funcione, necesitas tener las libraries **JavaCV** y **FFmpeg** instaladas y configuradas correctamente en tu proyecto.

**Nota**: **FFmpeg** es un open source binary que deberá instalar en su máquina y colocarlo en su PATH o hacerlo accesible dentro de su proyecto. **JavaCV** utiliza **FFmpeg** a través de JNI (la interfaz nativa de Java). **FFmpeg** es un conversor de medios extremadamente versátil que no solo maneja archivos de audio MP3, sino también otros formatos de archivos de audio (incluidos M4A, OGG y WAV). Puede convertir formatos de video, así como imágenes estáticas como PNG, JPEG y GIF.

Después de ejecutar la utilidad `AudioSplitter.java` en un archivo MP3, tendrá una carpeta llena de archivos de audio segmentados de diez minutos de duración o menos. Con la utilidad `AudioSplitter.java`, tendrá todo dentro de un solo archivo Java para modificar las configuraciones que funcionen mejor para usted. Para nuestros propósitos, el objetivo aquí es tener archivos de audio que tengan `<` 25 MB, por lo que si está transcribiendo procedimientos legales de 8 horas, por ejemplo, en formato WAV, es posible que deba ajustar la duración para que sea más corta, como 6 minutos de duración.

Al utilizar AudioSplitter, la mejor práctica es que la carpeta de salida sea una carpeta diferente de la de entrada, y verá por qué cuando comencemos a invocar el punto Endpoint Transcriptions utilizando el modelo Whisper.

### Creación del transcriptor de audio: `WhisperClient.java`

Ahora, construyamos nuestra próxima aplicación Java, `WhisperClient.java` Nuevamente, vamos a programar en pares con ChatGPT para obtener una base con la que trabajar. Esta vez, vamos a solicitar que se use la biblioteca HTTP OK para esta aplicación por dos motivos:

* Ya hemos utilizado la library en el Capítulo 3 para la aplicación Slack Bot.

* La library HTTP OK hace que las cosas sean un poco más fáciles de usar cuando se trabaja con formularios HTTP multiparte.

El listado 4-4 es el mensaje que se debe incluir en el Chat Playground para comenzar. Recuerde que solicito un tiempo de espera de solicitud HTTP de 60 segundos, ya que Whisper puede tardar un poco en generar la transcripción.

<img width="913" alt="image" src="https://github.com/user-attachments/assets/d164615a-75fa-4c8b-b122-d7389c3a7677">

```text
System: You are a Java developer.
User: Convert the following code from cURL to Java, using OkHttp to send the request. Make sure that I have a 60 second timeout on my request. Iterate over a single folder on my local computer and send all the files in the folder to the webservice. Name the file, WhisperClient.java.
User: curl https://api.openai.com/v1/audio/transcriptions \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: multipart/form-data" \
  -F file="@/path/to/file/audio.mp3" \
  -F model="whisper-1"
Model: gpt-4
Temperature: 1
Maximum Length: 1150
```

**Listing 4-4 PROMPT: Asking ChatGPT to Convert cURL to Java and Send to Whisper’s API**

```text
Sistema: Eres un desarrollador de Java.
Usuario: Convierte el siguiente código de cURL a Java, utilizando OkHttp para enviar la solicitud. Asegúrate de que mi solicitud tenga un tiempo de espera de 60 segundos. Itera sobre una sola carpeta en mi computadora local y envía todos los archivos de la carpeta al servicio web. Nombra el archivo WhisperClient.java.
Usuario: curl https://api.openai.com/v1/audio/transcriptions \
  -H "Autorización: Portador $OPENAI_API_KEY" \
  -H "Tipo de contenido: multipart/form-data" \
  -F archivo="@/ruta/al/archivo/audio.mp3" \
  -F modelo="susurro-1"
Modelo: gpt-4
Temperatura: 1
Longitud máxima: 1150
```

**Listado 4-4 PROMPT: Solicitar a ChatGPT que convierta cURL a Java y lo envíe a la API de Whisper**

Después de algunas idas y vueltas, aquí está la respuesta que nos dio ChatGPT que funcionó, como se muestra en el Listado 4-5.

<img width="932" alt="image" src="https://github.com/user-attachments/assets/f041b9b7-bfbf-4310-b049-a7425713f607">

```java
import java.io.*;
import java.nio.file.*;
import okhttp3.*;
import java.util.*;
import java.util.concurrent.TimeUnit;
import java.util.stream.Collectors;
import java.util.stream.Stream;
/**
 * Client class to transcribe MP3 files using the OpenAI Whisper model.
 */
public class WhisperClient {
    public static void main(String[] args) throws IOException {
        // API key for OpenAI (this should be replaced with your actual API key)
        String openAIKey = "";
        // OpenAI transcription endpoint
        String endpoint = "https://api.openai.com/v1/audio/transcriptions";
        // Model used for transcription
        String model = "whisper-1";
        // Media type for the MP3 files
        MediaType MEDIA_TYPE_MP3 = MediaType.parse("audio/mpeg");
        // Folder containing the MP3 files to be transcribed
        String mp3FolderPath = "/Users/me/audio/segments";
        // Desired format for the transcription response
        String responseFormat = "text";
        // Configure the HTTP client with specified timeouts
        OkHttpClient client = new OkHttpClient.Builder()
            .connectTimeout(60, TimeUnit.SECONDS)
            .writeTimeout(60, TimeUnit.SECONDS)
            .readTimeout(60, TimeUnit.SECONDS)
            .build();
        // List to store all mp3 files from the directory
        List<File> mp3Files = new ArrayList<>();
        // Try to collect all mp3 files in the directory and store them in the list
        try (Stream<Path> paths = Files.walk(Paths.get(mp3FolderPath))) {
            mp3Files = paths
                .filter(Files::isRegularFile)
                .filter(p -> p.toString().endsWith(".mp3"))
                .map(Path::toFile)
                .sorted(Comparator.comparing(File::getName)) // Sort the files alphabetically
                .collect(Collectors.toList());
        } catch (IOException e) {
            System.out.println("File reading error: " + e.getMessage());
            return; // Exit if there's an error reading the files
        }
        // Iterate over each MP3 file, transcribe it, and print the response
        for (File mp3File : mp3Files) {
            // Construct the request body for transcription
            RequestBody requestBody = new MultipartBody.Builder()
                .setType(MultipartBody.FORM)
                .addFormDataPart(
                    "file",
                    mp3File.getName(),
                    RequestBody.create(mp3File, MEDIA_TYPE_MP3))
                .addFormDataPart("model", model)
                .addFormDataPart("response_format", responseFormat)
                .build();
            // Build the HTTP request
            Request request = new Request.Builder()
                .url(endpoint)
                .header("Authorization", "Bearer " + openAIKey)
                .post(requestBody)
                .build();
            // Make the request and process the response
            try (Response response = client.newCall(request).execute()) {
                if (!response.isSuccessful()) throw new IOException("Unexpected code " + response);
                System.out.println(response.body().string());
            } catch (IOException e) {
                System.out.println("Request error for file: " + mp3File.getName() + " - " + e.getMessage());
            }
        }
    }
}
```

**Listado 4-5 RESPONSE: `WhisperClient.java`**

Como puedes ver, la clase `OkHttpClient` nos permite usar el patrón Builder para crear una instancia de la clase con los tiempos de espera que especificamos.

Ahora bien, esta es la razón por la que es una buena idea, al usar la utilidad `AudioSplitter.java`, separar la carpeta de salida de la carpeta de entrada. Estamos creando una colección de todos los archivos MP3 de un directorio. Más específicamente, es una “`List<File>`” que se llama “`mp3Files`” para almacenar todos los archivos que queremos transcribir. Por lo tanto, si el archivo que queremos dividir en segmentos más pequeños está en la misma carpeta que los segmentos mismos, entonces enviaremos el archivo grande (el que tiene más de 25 MB) junto con los archivos más pequeños al Endpoint Transcription, lo que anula todo el propósito de usar la aplicación `AudioSplitter.java`.

Por lo tanto, el método “`Files.walk()`” nos permite recorrer recursivamente el directorio “`mp3FolderPath`” y recolectar todos los archivos MP3 y filtrar aquellos que no terminen con la extensión “.mp3” (por razones de seguridad y para evitar errores con el servicio web). Luego, asignamos cada “Path” a su objeto “File” correspondiente y ordenamos los archivos alfabéticamente en función de sus nombres. Finalmente, usamos el método “`Collectors.toList()`” para recolectar todos los archivos ordenados en la lista “`mp3Files`”.

Con una colección de archivos MP3 en la mano, ahora es el momento de enviarlos al Endpoint Transcription. A medida que creamos el RequestBody, las líneas más importantes a las que debe prestar atención son:

<img width="910" alt="image" src="https://github.com/user-attachments/assets/3971b8ed-89d7-464a-b2c9-f0322b674ff0">

```java
           .addFormDataPart("modelo", modelo)
           .addFormDataPart("formato_de_respuesta", formato_de_respuesta)
```

Esto se debe al hecho de que si desea agregar parámetros opcionales a la solicitud HTTP (consulte la Tabla 4-2 para ver todos los parámetros), como el mensaje o la temperatura, debe agregarlos aquí de la misma manera que especificamos el modelo y el formato de respuesta.

**Nota** Permítanme reiterar: invocar el Endpoint Transcription es completamente diferente al Endpoint Chat. Es posible que ya hayan notado que una de las principales diferencias entre `ChatGPTClient.java` y `WhisperClient.java` son las declaraciones de importación. `ChatGPTClient.java` (en los capítulos 2 y 3) tiene la library Jackson dentro de sus declaraciones de importación, ya que necesitamos enviar la solicitud como un objeto JSON. Sin embargo, las importaciones en `WhisperClient.java` no mencionan a Jackson, ya que estamos enviando todo como datos de formulario.

### Divertirse un poco y probar cosas nuevas con un podcast

Bien, hagamos una prueba usando el código que hemos presentado hasta ahora. “This American Life” es un programa de radio público semanal (y también un podcast) presentado por Ira Glass y producido en colaboración con WBEZ Chicago.

<img width="615" alt="image" src="https://github.com/user-attachments/assets/1cdd4269-6656-4808-ae20-e64f01c04d1d">

**Figura 4-2 Si buscas un buen podcast con historias cautivadoras, te recomiendo escuchar “This American Life” Crédito de la imagen: WBEZ Chicago**

Cada episodio entrelaza una serie de historias centradas en un tema o tópico específico. Algunas historias son periodismo de investigación y otras son simplemente entrevistas con personas comunes con historias cautivadoras. El episodio 811 se titula “El único lugar al que no puedo ir” y el archivo tiene 56 MB en formato MP3. Como ya sabemos que 56 MB es demasiado grande para enviarlo a Whisper para su transcripción, el Listado 4-6 muestra el resultado de `AudioSplitter.java` en el archivo MP3.

<img width="561" alt="image" src="https://github.com/user-attachments/assets/3fccb1ec-eedb-4ac5-a2a1-a8c9f97858d3">

```text
[mp3 @ 0x139e9c6a0] Estimating duration from bitrate, this may be inaccurate
Input #0, mp3, from '/Users/me/thislife/ep811.mp3':
  Metadata:
    encoder         : Lavf58.78.100
    comment         : preroll_1;postroll_1
  Duration: 00:58:58.34, start: 0.000000, bitrate: 128 kb/s
  Stream #0:0: Audio: mp3, 44100 Hz, stereo, fltp, 128 kb/s
Output #0, mp3, to '/Users/me/thislife/segments/segment_1.mp3':
  Metadata:
    TSSE            : Lavf60.3.100
  Stream #0:0: Audio: mp3, 44100 Hz, stereo, fltp, 192 kb/s
[libmp3lame @ 0x139ea92e0] 2 frames left in the queue on closing
Output #0, mp3, to '/Users/me/thislife/segments/segment_2.mp3':
  Metadata:
    TSSE            : Lavf60.3.100
  Stream #0:0: Audio: mp3, 44100 Hz, stereo, fltp, 192 kb/s
[libmp3lame @ 0x13b167720] 2 frames left in the queue on closing
Output #0, mp3, to '/Users/me/thislife/segments/segment_3.mp3':
  Metadata:
    TSSE            : Lavf60.3.100
  Stream #0:0: Audio: mp3, 44100 Hz, stereo, fltp, 192 kb/s
[libmp3lame @ 0x13b166df0] 2 frames left in the queue on closing
Output #0, mp3, to '/Users/me/thislife/segments/segment_4.mp3':
  Metadata:
    TSSE            : Lavf60.3.100
  Stream #0:0: Audio: mp3, 44100 Hz, stereo, fltp, 192 kb/s
[libmp3lame @ 0x13b166df0] 2 frames left in the queue on closing
Output #0, mp3, to '/Users/me/thislife/segments/segment_5.mp3':
  Metadata:
    TSSE            : Lavf60.3.100
  Stream #0:0: Audio: mp3, 44100 Hz, stereo, fltp, 192 kb/s
[libmp3lame @ 0x139ea35f0] 2 frames left in the queue on closing
Output #0, mp3, to '/Users/me/thislife/segments/segment_6.mp3':
  Metadata:
    TSSE            : Lavf60.3.100
  Stream #0:0: Audio: mp3, 44100 Hz, stereo, fltp, 192 kb/s
[libmp3lame @ 0x139ea3540] 2 frames left in the queue on closing
```

**Listado 4-6 El resultado de ejecutar `AudioSplitter.java` en el episodio 811 de This American Life**

Dado que la utilidad `AudioSplitter.java` utiliza un contenedor JNI para interactuar con FFmpeg, verá muchos mensajes de diagnóstico durante el proceso de división de audio, como se muestra en el Listado 4-6 . A menos que le interesen los códecs, las frecuencias y las tasas de bits, la mayor parte de la información presentada no tendrá sentido para usted. Sin embargo, la buena noticia es que ahora tenemos una carpeta con 6 archivos MP3 listos para la transcripción.

Por supuesto, como puede ver en el código del Listado 4-5, `WhisperClient.java` itera sobre todos los archivos en una carpeta y los envía al Endpoint Transcription para usar el modelo Whisper.

El listado 4-7 es un extracto de la transcripción completa del episodio.

```text
"...My younger cousin Camille is not really a dog person, but there is one dog she adored. Her name was Foxy, because she looked exactly like a fox, except she was black. She was the neighbor's dog, but she and Camille seemed to have a real kinship, maybe because they both weren't very far from the ground. Camille was around four or five years old back then, and she had a little lisp, so Foxy came out as Fozzie. I thought it was one of the cutest things I'd ever heard.
The way Camille remembers Foxy, it's almost like a movie. Her memories feel like endless summer, hazy and perfect, like a scene shot on crackly film. I just remembered like the feeling of being excited to go and see Foxy. I have an image in my head of like coming to the house, and I could see Foxy was like outside. I can see Foxy through the door that leads to the garden. There's a story about Camille and Foxy that I think about fairly often. I've talked about it with my sister for years, but never with Camille. And it's this. Once when they were playing..."
```

**Listing 4-7 The Partial Transcript of Episode 811 of This American Life**

Para abreviar, solo mostramos un extracto de la transcripción. La transcripción completa tiene más de 8000 palabras debido a que el episodio dura casi 1 hora.

### Going Meta: Prompt Engineering GPT-4 para escribir un Prompt para DALL·E

Dado que la transcripción del texto completo del episodio del podcast que queremos visualizar tiene miles de palabras, vamos a utilizar GPT-4 para crear automáticamente el mensaje necesario para el modelo DALL⋅E. DALL⋅E puede tomar una descripción textual en un mensaje y crear una imagen, pero es mejor mantener el mensaje lo más breve posible. El listado 4-8 es el mensaje para que GPT-4 genere un mensaje para DALL⋅E.


```text
System: You are a service that helps to visualize podcasts.
User: Read the following transcript from a podcast. Describe for a visually impaired person the background and subject that best represents the overall theme of the episode. Start with any of the following phrases:
- "A photo of"
- "A painting of"
- "A macro 35mm photo of"
- "Digital art of "
User: Support for This American Life comes from Squarespace...
Model: gpt-4-32k
Temperature: 1.47
Maximum length: 150
Top P: 0
Frequency penalty: 0.33
Presence penalty: 0
Listing 4-8The Prompt for GPT-4 to Create a Prompt for DALL⋅E
```


```text
Sistema : Eres un servicio que ayuda a visualizar podcasts.
Usuario : Lea la siguiente transcripción de un podcast. Describa para una persona con discapacidad visual el contexto y el tema que mejor representen el tema general del episodio. Comience con cualquiera de las siguientes frases:
- "Una foto de"
- "Un cuadro de"
- "Una fotografía macro de 35 mm de"
- "Arte digital de"
Usuario: El soporte para This American Life proviene de Squarespace...
Modelo : gpt-4-32k
Temperatura : 1,47
Longitud máxima: 150
P superior: 0
Penalización de frecuencia: 0,33
Penalización por presencia: 0
Listado 4-8Solicitud de GPT-4 para crear una solicitud para DALL⋅E
```
