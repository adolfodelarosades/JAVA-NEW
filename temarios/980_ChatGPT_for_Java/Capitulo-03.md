# 3. ¡Uso de IA en la empresa! Creación de un resumen de texto para mensajes de Slack

Bruce Hopkins 1  

(1)

Beaverton, Oregón, Estados Unidos
https://doi.org/10.1007/979-8-8688-0116-7_3

<hr>

En el mundo corporativo actual, es muy común que las empresas tengan una instancia de Slack (o Microsoft Teams) para organizarse y la utilicen como un lugar central de comunicación para todos en la empresa. Ahora bien, si alguna vez has utilizado Slack, creo que sabes con qué facilidad un canal puede inundarse con un montón de mensajes porque ALGUNA cosa importante sucedió EN ALGÚN LUGAR de la empresa o del mundo.

Por supuesto, cuanto mayor sea la responsabilidad que tengas dentro de la empresa (es decir, gerente, líder de equipo, arquitecto, etc.), más canales se espera que utilices. En mi opinión, Slack es un arma de doble filo. Debes usarlo para hacer tu trabajo, pero como desarrollador, definitivamente no puedes asistir a una reunión diaria y decir: "Ayer, eh, pasé todo el día leyendo Slack. No hay obstáculos".

Además, si trabajas para una empresa con clientes en distintas zonas horarias (lo cual es bastante común hoy en día), es bastante desalentador abrir Slack por la mañana y ver un montón de mensajes que se publicaron mientras estabas lejos del teclado.

En este capítulo, aplicaremos la IA en la empresa para que Slack sea más útil. Aprovecharemos el código del capítulo anterior y crearemos un bot de Slack en Java que resumirá las conversaciones importantes en un canal de Slack. Utilizaremos las capacidades de ChatGPT para el resumen de texto y nos centraremos un poco más en **Prompt Engineering**.

### Entonces, ¿qué es la Prompt Engineering?

En pocas palabras, Prompt Engineeringes el proceso de crear y refinar cuidadosamente las indicaciones y los parámetros de entrada para indicar y guiar el comportamiento de ChatGPT y otros modelos de IA. Básicamente, es el término que se usa en toda la industria para crear la entrada correcta para obtener el resultado que estás buscando.

Sin embargo, antes de continuar, hagamos un poco de limpieza y mejoremos nuestro `ChatGPTClient.java` del capítulo anterior.

### Actualización de `ChatGPTClient.java` (y clases relacionadas) con el patrón Builder

Entonces, en el capítulo anterior, creamos `ChatGPTClient.java` como una aplicación básica para enviar nuestras indicaciones al Endpoint Chat. Fue un buen comienzo, pero definitivamente había margen de mejora.

Veamos primero el constructor del objeto Chat, que modela el objeto Chat JSON que se envía al punto final de chat como se ve en el Listado 3-1.

![image](https://github.com/user-attachments/assets/0fccaa77-eff9-4972-8df1-8d33ae95c262)

```java
public Chat(String model, List<Message> messages, float temperature,
                    int max_tokens, float top_p, int frequency_penalty,
                    int presence_penalty) {
            this.model = model;
            this.messages = messages;
            this.temperature = temperature;
            this.max_tokens = max_tokens;
            this.top_p = top_p;
            this.frequency_penalty = frequency_penalty;
            this.presence_penalty = presence_penalty;
        }

```

**Listado 3-1 El constructor del objeto Chat**

Por lo tanto, si vuelve a consultar la Tabla 2-4 del Capítulo 2, verá que solo los parámetros `model` y `messages` son realmente necesarios para invocar correctamente el Endpoint Chat. Todos los demás parámetros son opcionales y algunos de ellos tienen sus propios valores predeterminados incorporados si no especifica nada. Esas son las razones por las que no necesitábamos "modelar" todo el Chat JSON object.

Por lo tanto, este constructor básicamente pide a gritos que se lo refactorice utilizando el **patrón Builder**. El patrón Builder nos permite obtener una instancia del objeto que queremos, mientras que SOLO especificamos los parámetros que nos interesan.

Además, tiene sentido que los objetos Chat y Message ya no sean clases internas y existan en sus propios archivos .java. El listado 3-2 muestra cómo podemos obtener una instancia del objeto Chat que se ha modificado utilizando el patrón Builder.

![image](https://github.com/user-attachments/assets/7768c4ef-6e66-4c0f-b5d2-6f552605c241)

```java
Chat chat = Chat.builder()
        .model(model)
        .messages(messages)
        .temperature(temperature)
        .maxTokens(max_tokens)
        .topP(top_p)
        .frequencyPenalty(frequency_penalty)
        .presencePenalty(presence_penalty)
        .build();
```

**Listado 3-2 Obtención de una instancia del objeto Chat**

Dado que la solicitud al Endpoint Chat DEBE tener un modelo y un mensaje especificados en el objeto JSON de chat, se han agregado algunos valores predeterminados a la clase `Chat.java` para que sea más segura de usar (más segura en el sentido de que sea menos propensa a errores para los usuarios de la clase). El listado 3-3 es el nuevo archivo `Chat.java`.

```java
import java.util.List;
import java.util.ArrayList;
import com.fasterxml.jackson.annotation.JsonProperty;
public class Chat {
    @JsonProperty("model")
    private String model;
    @JsonProperty("messages")
    private List<Message> messages;
    @JsonProperty("temperature")
    private float temperature;
    @JsonProperty("max_tokens")
    private int max_tokens;
    @JsonProperty("top_p")
    private float top_p;
    @JsonProperty("frequency_penalty")
    private int frequency_penalty;
    @JsonProperty("presence_penalty")
    private int presence_penalty;
    private Chat(ChatBuilder builder) {
        this.model = builder.model;
        this.messages = builder.messages;
        this.temperature = builder.temperature;
        this.max_tokens = builder.max_tokens;
        this.top_p = builder.top_p;
        this.frequency_penalty = builder.frequency_penalty;
        this.presence_penalty = builder.presence_penalty;
    }
    public static ChatBuilder builder() {
        // we need a default message here to avoid 400 errors from the API
        List<Message> messages = new ArrayList<>();
        messages.add(new Message("system", "You are a helpful assistant"));
        messages.add(new Message("user", "hello"));
        return new ChatBuilder().messages(messages);
    }
    public static class ChatBuilder {
        private String model = "gpt-3.5-turbo";
        private List<Message> messages = null;
        private float temperature = 1.0f;
        private int max_tokens = 2048;
        private float top_p = 0f;
        private int frequency_penalty = 0;
        private int presence_penalty = 0;
        private ChatBuilder() {
        }
        public ChatBuilder model(String model) {
            this.model = model;
            return this;
        }
        public ChatBuilder messages(List<Message> messages) {
            this.messages = messages;
            return this;
        }
        public ChatBuilder temperature(float temperature) {
            this.temperature = temperature;
            return this;
        }
        public ChatBuilder maxTokens(int max_tokens) {
            this.max_tokens = max_tokens;
            return this;
        }
        public ChatBuilder topP(float top_p) {
            this.top_p = top_p;
            return this;
        }
        public ChatBuilder frequencyPenalty(int frequency_penalty) {
            this.frequency_penalty = frequency_penalty;
            return this;
        }
        public ChatBuilder presencePenalty(int presence_penalty) {
            this.presence_penalty = presence_penalty;
            return this;
        }
        public Chat build() {
            return new Chat(this);
        }
    }
}
```

**Listado 3-3 `Chat.java` ahora utiliza el patrón Builder**

Esta clase (con este patrón de diseño) es lo suficientemente flexible como para que puedas agregar o eliminar los parámetros que necesitas para invocar el Endpoint Chat. Si en algún momento OpenAI agrega nuevos parámetros y funciones al Endpoint Chat, puedes modificar esta clase para que admita los nuevos requisitos.

Para completar, el Listado 3-4 muestra la clase `Message.java`.

```java
import com.fasterxml.jackson.annotation.JsonProperty;
public class Message {
    @JsonProperty("role")
    private String role;
    @JsonProperty("content")
    private String content;
    public Message(String role, String content) {
        this.role = role;
        this.content = content;
    }
}
```

**Listado 3-4 `Message.java`**

### ChatGPT está aquí para quitarle el trabajo a todo el mundo (en realidad, no)

En mi humilde opinión, todas las empresas del mundo tienen una mina de oro de información sin explotar. Si utiliza un sistema que lleva un registro de los intercambios entre empleados, una base de datos de solicitudes de asistencia de sus clientes o cualquier gran repositorio de texto (sí, esto incluye su correo electrónico, Microsoft Exchange y Gmail corporativo), entonces tiene un gran repositorio de texto no estructurado que está esperando a ser utilizado.

Por lo tanto, el mejor uso de ChatGPT no es eliminar el trabajo de nadie, sino que debe utilizarse para aumentar y extender lo que los miembros del equipo de su empresa ya están haciendo. Como vimos en el capítulo anterior, como programador, ChatGPT puede funcionar como un programador en pares muy eficaz. También es muy bueno para realizar ciertas tareas difíciles de manera muy eficiente y rápida. Veamos un ejemplo práctico de lo que se puede hacer para aprovechar una gran fuente de texto no estructurado.

### Análisis de un problema real: atención al cliente para una empresa de software

Una de las tareas más agotadoras en el desarrollo de software es brindar soporte técnico. Imagine la alegría de recibir llamadas y mensajes todo el día de personas que podrían estar frustradas, confundidas o simplemente necesitar una solución mientras usan su software. Estas son algunas de las razones por las que la atención al cliente es un hueso duro de roer:

* Sus usuarios finales y sus clientes son notoriamente malos a la hora de explicar los problemas con su software.

* Los técnicos de nivel 1, que suelen ser la primera línea de defensa, suelen ocuparse de los problemas más básicos o de los errores de los usuarios. Pero cuando los problemas se vuelven más complejos, los usuarios pasan al nivel 2.

* El nivel medio es un lugar complicado, porque tienen más conocimientos y experiencia que el personal de soporte técnico del nivel 1; sin embargo, no tienen la oportunidad de obtener respuestas directamente del usuario final.

* Los problemas realmente graves se escalan al nivel 3; sin embargo, este es el personal de soporte técnico más caro porque tiene más conocimientos y experiencia. Tienen experiencia práctica con el código, así como con los servidores y la infraestructura.

Trabajemos con un ejemplo real de una conversación típica dentro de un canal de soporte técnico típico dentro de Slack. A continuación, se incluye una lista de los miembros del equipo y sus funciones dentro de una empresa ficticia :

* Fatima (Customer Service Representative) - Fátima (Representante de Servicio al Cliente)

* John (Software Engineer) - John (Ingeniero de software)

* Dave (PM) - Dave (primer ministro)

* Keith (CTO) - Keith (director técnico)


El listado 3-5 ofrece un ejemplo de una conversación entre los miembros del equipo de una empresa de software emergente. Fátima, la representante de atención al cliente, informa al equipo que su aplicación se bloquea inmediatamente después de iniciarse (no es un problema agradable). Keith, el director de tecnología, interviene de inmediato para escalar el problema.

<img width="909" alt="image" src="https://github.com/user-attachments/assets/bc385a47-e9cc-4518-9193-1f4187f8a327">

```text
Fatima [16:00 | 02/08/2019]: Hey everyone, I have an urgent issue to discuss. I just got off a call with a client who's experiencing app crashes as soon as they load it. They're really frustrated. Can we get this sorted ASAP? 
Keith [16:01 | 02/08/2019]: Thanks for bringing this to our attention, Fatima. Let's jump on this right away. @John, can you take the lead in investigating the issue since our architect is out sick today?
John [16:02 | 02/08/2019]: Sure thing, Keith. I'll dive into the codebase and see if I can find any potential culprits for the crashes.
John [16:02 | 02/08/2019]: Fatima, could you gather some additional information from the client? Ask them about the specific device, operating system, and any recent updates they might have installed.
Fatima [16:03 | 02/08/2019]: Absolutely, John. I'll reach out to the client immediately and gather those details. Will update you all once I have them.
Dave [16:04 | 02/08/2019]: I understand the urgency here. Let's make sure we keep the client informed about our progress  Fatima. We don't want them feeling left in the dark during this troubleshooting process.
Fatima [16:04 | 02/08/2019]: Definitely, Dave.  I'll keep the client updated at regular intervals, providing them with any relevant information we uncover.
John [16:20 | 02/08/2019]: I've checked the codebase, and so far, I haven't found any obvious issues. It's strange that the app is crashing on load. Could it be a memory-related issue? Keith, do we have any recent reports of memory leaks or high memory usage?
Keith [16:22 | 02/08/2019]: I'll pull up the monitoring logs, John, and check if there have been any memory-related anomalies in recent releases. Let me get back to you on that.
Fatima [17:01 | 02/08/2019]: Quick update, everyone. The client is using an iPhone X running iOS 15.1. They mentioned that the issue started after updating their app a few days ago 
Keith [17:05 | 02/08/2019]: Thanks for the update, Fatima. That's helpful information. John, let's focus on testing the latest app update on an iPhone X simulator with iOS 15.1 to see if we can replicate the issue.
John [17:06 | 02/08/2019]: Good idea, Keith. I'll set up the emulator and run some tests right away.
Keith [17:30 | 02/08/2019]: John, any progress on replicating the issue on the emulator?
John [17:32 | 02/08/2019]: Yes, Keith. I managed to reproduce the crash on the emulator. It seems to be related to a compatibility issue with iOS 15.1 . I suspect it's due to a deprecated method call. I'll fix it and run more tests to confirm.
John [18:03 | 02/08/2019]: Fixed the deprecated method issue, and the app is no longer crashing on load. It looks like we've identified and resolved the problem. I'll prepare a patch and send it to you, Keith, for review and deployment.
Keith [18:04 | 02/08/2019]:  Thank you, please provide me with the patch as soon as possible. Once I review it, we'll deploy the fix to the app store.
Dave [18:06 | 02/08/2019]: Great job, team!  John, please keep the client informed about the progress and let them know we have a fix ready for them on the next app update. Can someone make sure the release notes reflect this?
John [18:07 | 02/08/2019]: Will do, Dave. I'll update the client and ensure they're aware of the upcoming fix.
Keith [18:27 | 02/08/2019]: Patch reviewed and approved, John. Please proceed with updating the app in the store. Let's aim to have it done within the next hour.
John [18:26 | 02/08/2019]: Understood, Keith. I'm in the process of uploading it now.
Fatima [18:38 | 02/08/2019]: I just informed the client about the fix. They're relieved and grateful for our prompt response. Thanks, everyone, for your collaboration and quick action. It's a pleasure working with such a competent team!
Dave [18:40 | 02/08/2019]: Well done, team! Your efforts are greatly appreciated. We managed to turn this urgent problem around in record time. Let's keep up the good work! 
```

**Listing 3-5 Team Members Within a Slack Channel Trying to Analyze a Customer’s Problem**

```text
Fatima [16:00 | 08/02/2019]: Hola a todos, tengo un problema urgente que tratar. Acabo de terminar una llamada con un cliente que está experimentando fallos en la aplicación apenas la carga. Está muy frustrado. ¿Podemos solucionar esto lo antes posible?
Keith [16:01 | 08/02/2019]: Gracias por informarnos sobre esto, Fátima. Vamos a ocuparnos de esto de inmediato. @John, ¿puedes encargarte de investigar el problema ya que nuestro arquitecto está de baja hoy por enfermedad?
John [16:02 | 08/02/2019]: Por supuesto, Keith. Analizaré el código base y veré si puedo encontrar posibles culpables de los fallos.
John [16:02 | 08/02/2019]: Fátima, ¿podrías obtener información adicional del cliente? Pregúntales sobre el dispositivo específico, el sistema operativo y las actualizaciones recientes que hayan podido instalar.
Fatima [16:03 | 08/02/2019]: Por supuesto, John. Me comunicaré con el cliente de inmediato y reuniré esos detalles. Les informaré a todos cuando los tenga.
Dave [16:04 | 08/02/2019]: Entiendo la urgencia. Asegurémonos de mantener al cliente informado sobre nuestro progreso Fátima. No queremos que se sientan abandonados a su suerte durante este proceso de resolución de problemas.
Fátima [16:04 | 08/02/2019]: Definitivamente, Dave. Mantendré al cliente actualizado a intervalos regulares, proporcionándole cualquier información relevante que descubramos.
John [16:20 | 08/02/2019]: He revisado el código base y, hasta ahora, no he encontrado ningún problema evidente. Es extraño que la aplicación se bloquee al cargar. ¿Podría ser un problema relacionado con la memoria? Keith, ¿tenemos algún informe reciente de fugas de memoria o uso elevado de la memoria?
Keith [16:22 | 08/02/2019]: John, buscaré los registros de monitoreo y comprobaré si hubo alguna anomalía relacionada con la memoria en las versiones recientes. Te responderé al respecto.
Fatima [17:01 | 08/02/2019]: Una actualización rápida para todos. El cliente usa un iPhone X con iOS 15.1. Mencionaron que el problema comenzó después de actualizar su aplicación hace unos días.
Keith [17:05 | 08/02/2019]: Gracias por la actualización, Fatima. Es una información útil. John, centrémonos en probar la última actualización de la aplicación en un simulador de iPhone X con iOS 15.1 para ver si podemos replicar el problema.
John [17:06 | 08/02/2019]: Buena idea, Keith. Configuraré el emulador y ejecutaré algunas pruebas de inmediato.
Keith [17:30 | 08/02/2019]: John, ¿hay algún progreso en replicar el problema en el emulador?
John [17:32 | 08/02/2019]: Sí, Keith. Logré reproducir el error en el emulador. Parece estar relacionado con un problema de compatibilidad con iOS 15.1 Sospecho que se debe a una llamada a un método obsoleto. Lo solucionaré y realizaré más pruebas para confirmarlo.
John [18:03 | 08/02/2019]: Se solucionó el problema del método obsoleto y la aplicación ya no se bloquea al cargarse. Parece que hemos identificado y resuelto el problema. Prepararé un parche y te lo enviaré, Keith, para que lo revises y lo implementes.
Keith [18:04 | 08/02/2019]:Gracias, por favor envíenme el parche lo antes posible. Una vez que lo revisemos, implementaremos la solución en la tienda de aplicaciones.
Dave [18:06 | 08/02/2019]: ¡Buen trabajo, equipo! John, mantén informado al cliente sobre el progreso y hazle saber que tenemos una solución lista para ellos en la próxima actualización de la aplicación. ¿Alguien puede asegurarse de que las notas de la versión reflejen esto?
John [18:07 | 08/02/2019]: Lo haré, Dave. Informaré al cliente y me aseguraré de que esté al tanto de la próxima solución.
Keith [18:27 | 08/02/2019]: Revisión revisada y aprobada, John. Continúa con la actualización de la aplicación en la tienda. Intentaremos hacerlo en la próxima hora.
John [18:26 | 08/02/2019]: Entendido, Keith. Estoy en proceso de subirlo ahora.
Fatima [18:38 | 08/02/2019]: Acabo de informar al cliente sobre la solución. Están aliviados y agradecidos por nuestra pronta respuesta. Gracias a todos por su colaboración y rápida actuación. ¡Es un placer trabajar con un equipo tan competente!
Dave [18:40 | 08/02/2019]: ¡Bien hecho, equipo! Sus esfuerzos son muy apreciados. Logramos resolver este problema urgente en un tiempo récord. ¡Sigamos con el buen trabajo!
```

**Listado 3-5 Miembros del equipo dentro de un canal de Slack que intentan analizar el problema de un cliente**

### Prompt Engineering 101: resumen de texto

Por lo tanto, no hace falta decir que nadie quiere pasar el día navegando constantemente por los canales de Slack leyendo sobre problemas y cuestiones que están en auge. Vamos a utilizar las capacidades de ChatGPT para el resumen de texto. Para simplificar las cosas, probemos algunas indicaciones para enviar la lista completa de mensajes de chat a ChatGPT para que nos brinde un resumen útil de todos los eventos que han sucedido.

#### Prompt #1: “tl;dr”

Este mensaje es breve, conciso y directo. Por si no lo conoces, es un término que se usa en Internet con frecuencia para resumir brevemente un artículo largo. Literalmente significa "Demasiado largo; no lo leí", que es lo que pienso sobre muchas conversaciones en Slack cuando estoy abrumado por el trabajo. Convenientemente, ChatGPT puede entender este término simple (no necesariamente lo llamaría una palabra) como un mensaje, y los resultados son bastante impresionantes.

<img width="913" alt="image" src="https://github.com/user-attachments/assets/740827ee-da8a-4f57-9717-ad941158a714">

```text
System: You are a helpful assistant
User:  Fatima [16:00 | 02/08/2019]: Hey everyone, I have an urgent ...
User: Tl;dr
Model: gpt-4
Temperature: 1
Maximum length: 360
Top P: 1
Frequency penalty: 0
Presence penalty: 0
```
**Listing 3-6 PROMPT. Asking for a Summarized Version of a Longer Conversation**

```text
Sistema : Eres un asistente útil
Usuario : Fatima [16:00 | 08/02/2019]: Hola a todos, tengo una consulta urgente...
Usuario : Tl;dr
Modelo : gpt-4
Temperatura : 1
Longitud máxima: 360
P superior: 1
Penalización de frecuencia: 0
Penalización por presencia: 0
```
**Listado 3-6 PROMPT. Cómo pedir una versión resumida de una conversación más larga**

**Nota**: Ahora tienes dos opciones para enviar el mensaje anterior a ChatGPT. La primera opción es usar la aplicación `ChatGPTClient.java` y sus clases de soporte. La segunda opción es usar Chat Playground. En cualquier caso, asegúrate de que el primer mensaje de usuario contenga todo el texto que se encuentra en el Listado 3-5. Está truncado en el Listado 3-6 para que sea máslegible.

Observe cómo la cantidad de tokens se mantiene pequeña, en 360, lo que en última instancia ayudará a ChatGPT a crear una respuesta breve. Observe también que la temperatura se deja en 1 (el valor predeterminado), pero que la P superior se aumenta hasta su máximo (que es 1). Por lo tanto, es importante experimentar con la temperatura y otras configuraciones para controlar el tono y la variedad de las respuestas de ChatGPT.

El listado 3-7 muestra el resumen de ChatGPT de la conversación del Listado 3-5.

<img width="915" alt="image" src="https://github.com/user-attachments/assets/586f2491-8266-46c6-be0f-fc3787f81650">

```text
The team quickly responds to a client's app crashing issue. John investigates the codebase while Fatima gathers information from the client. They discover a compatibility issue with iOS 15.1 and John fixes it. The patch is reviewed and approved, and the app is updated in the store. The client is informed and grateful for the quick resolution. The team is praised for their collaboration and prompt action.
```

**Listing 3-7 RESPONSE. Getting a Summarized Version of a Very Long Conversation**

```text
El equipo responde rápidamente al problema de bloqueo de la aplicación de un cliente. John investiga el código base mientras Fatima recopila información del cliente. Descubren un problema de compatibilidad con iOS 15.1 y John lo soluciona. Se revisa y aprueba el parche, y la aplicación se actualiza en la tienda. El cliente está informado y agradecido por la rápida resolución. Se elogia al equipo por su colaboración y su pronta acción.
```

**Listado 3-7 RESPONSE. Cómo obtener una versión resumida de una conversación muy larga**

¡Es fantástico! Ha reducido esa conversación extremadamente larga a un resumen simple y breve de solo 68 palabras. Como puedes ver, ChatGPT no reemplaza un trabajo; sin embargo, definitivamente hará que alguien sea más productivo. Ahora, probemos con algunas indicaciones más, ¿te parece?

#### Prompt #2: “Explique esto en 3 oraciones o menos”

Por lo tanto, si "tl;dr" no le ofrece una explicación lo suficientemente breve, podemos indicarle a ChatGPT que simplifique aún más las cosas. ChatGPT funciona bien con los parámetros, por lo que especificaremos que la explicación no debe tener más de 3 oraciones, como se muestra en el Listado 3-8.


<img width="907" alt="image" src="https://github.com/user-attachments/assets/076ee004-c129-472d-84ae-e21deef9f87c">

```text
System: You are a helpful assistant
User:  Fatima [16:00 | 02/08/2019]: Hey everyone, I have an urgent ...
User: Explain this in 3 sentences or less.
Model: gpt-4
Temperature: 1
Maximum length: 250
Top P: 0
Frequency penalty: 0
Presence penalty: 0
```

**Listing 3-8 PROMPT. Asking for a Shorter Version of a Longer Conversation**

```text
Sistema : Eres un asistente útil
Usuario : Fatima [16:00 | 08/02/2019]: Hola a todos, tengo una consulta urgente...
Usuario : Explique esto en 3 oraciones o menos.
Modelo : gpt-4
Temperatura : 1
Longitud máxima: 250
P superior: 0
Penalización de frecuencia: 0
Penalización por presencia: 0
```

**Listado 3-8 PROMPT. Cómo pedir una versión más corta de una conversación más larga**

Como habrás notado, la temperatura está configurada en 0,82 en este ejemplo. Realmente queremos que ChatGPT nos dé una respuesta concisa, por lo que cuanto más “seca”, mejor.

<img width="915" alt="image" src="https://github.com/user-attachments/assets/3635cce7-d0c3-4ab7-be7c-c316c441b68a">

```text
A customer reported an urgent issue of app crashes to the team. John investigates the issue and asks Fatima to gather additional information from the client. They discover that the issue is related to a compatibility problem with iOS 15.1. John fixes the problem and Keith approves the deployment of the fix to the client's production environment.
```

**Listing 3-9 RESPONSE. Getting a 3 Sentence Summary**

```text
Un cliente informó al equipo sobre un problema urgente de fallas de la aplicación. John investiga el problema y le pide a Fatima que recopile información adicional del cliente. Descubren que el problema está relacionado con un problema de compatibilidad con iOS 15.1. John soluciona el problema y Keith aprueba la implementación de la solución en el entorno de producción del cliente.
```

**Listado 3-9 RESPONSE. Obtener un resumen de 3 oraciones**

#### Prompt #3: “Soy gerente. Explícame qué sucedió”

Cuando no desea sonar como la única persona que no entiende, ChatGPT tiene la capacidad de reformular lo que se ha dicho y desglosarlo hasta que sea muy simple (Listado 3-10 ).

<img width="917" alt="image" src="https://github.com/user-attachments/assets/7d7da953-d1ac-4e96-971b-1b622dcb024c">

```text
System: You are a helpful assistant
User:  Fatima [16:00 | 02/08/2019]: Hey everyone, I have an urgent ...
User: Summarize this conversation and explain it to me like I'm a manager with little technical experience.
Model: gpt-3.5-turbo
Temperature: 0.82
Maximum length: 750
Top P: 1
Frequency penalty: 0
Presence penalty: 0
```

**Listing 3-10 PROMPT. Asking for a Simplified Version of a More Complex Conversation**

```text
Sistema : Eres un asistente útil
Usuario : Fatima [16:00 | 08/02/2019]: Hola a todos, tengo una consulta urgente...
Usuario : Resume esta conversación y explícamela como si fuera un gerente con poca experiencia técnica.
Modelo : gpt-3.5-turbo
Temperatura : 0,82
Longitud máxima: 750
P superior: 1
Penalización de frecuencia: 0
Penalización por presencia: 0
```

**Listado 3-10 PROMPT. Cómo pedir una versión simplificada de una conversación más compleja**

Nuevamente, la temperatura se establece por debajo de 1.0 para que ChatGPT pueda ofrecer una respuesta breve y fácil de entender. Aumentamos la longitud del token para que ChatGPT pueda tomarse el tiempo de explicar algunos conceptos potencialmente técnicos.

<img width="908" alt="image" src="https://github.com/user-attachments/assets/1fb9368d-20ed-4080-a46e-1a10b06d459d">

```text
In this conversation, Fatima brings up an urgent issue with a client who is experiencing app crashes as soon as they load it. Keith assigns John to investigate the issue since their architect is out sick. John asks Fatima to gather additional information from the client about their device, operating system, and recent updates. Dave emphasizes the importance of keeping the client informed throughout the troubleshooting process.
John checks the codebase but doesn't find any obvious issues, so he suspects it could be a memory-related problem. Keith agrees to check for memory-related anomalies in recent releases. Fatima provides an update that the client is using an iPhone X running iOS 15.1 and mentioned that the issue started after updating the app. Keith suggests testing the latest app update on an iPhone X simulator with iOS 15.1 to replicate the issue.
John successfully reproduces the crash on the emulator and identifies a compatibility issue with iOS 15.1, possibly due to a deprecated method call. He fixes the issue and prepares a patch for review and deployment. Keith approves the patch and asks John to update the app in the store. Dave requests that the client be kept informed and that the release notes reflect the upcoming fix.
John uploads the patch and informs the client about the fix. Keith reviews and approves the patch, and John proceeds with updating the app in the store. Fatima informs the client about the fix, and they express relief and gratitude for the prompt response. Dave commends the team for their collaboration and quick action, emphasizing the importance of maintaining good work.
In summary, the team quickly addressed an urgent issue where a client's app was crashing on load. They investigated the issue, identified a compatibility problem with iOS 15.1, fixed it, and prepared a patch for deployment. The client was kept informed throughout the process, and the fix was successfully implemented, resulting in a relieved and grateful client.
```

**Listing 3-11 RESPONSE. Getting a Simplified Version of a More Complex Conversation**

```text
En esta conversación, Fatima plantea un problema urgente con un cliente que experimenta fallas en la aplicación apenas la carga. Keith le asigna a John la tarea de investigar el problema, ya que su arquitecto está de baja por enfermedad. John le pide a Fatima que recopile información adicional del cliente sobre su dispositivo, sistema operativo y actualizaciones recientes. Dave enfatiza la importancia de mantener informado al cliente durante todo el proceso de resolución de problemas.
John revisa el código base pero no encuentra ningún problema obvio, por lo que sospecha que podría ser un problema relacionado con la memoria. Keith acepta verificar si hay anomalías relacionadas con la memoria en las versiones recientes. Fatima proporciona una actualización de que el cliente está usando un iPhone X con iOS 15.1 y menciona que el problema comenzó después de actualizar la aplicación. Keith sugiere probar la última actualización de la aplicación en un simulador de iPhone X con iOS 15.1 para replicar el problema.
John reproduce con éxito el fallo en el emulador e identifica un problema de compatibilidad con iOS 15.1, posiblemente debido a una llamada a un método obsoleto. Soluciona el problema y prepara un parche para su revisión e implementación. Keith aprueba el parche y le pide a John que actualice la aplicación en la tienda. Dave solicita que se mantenga informado al cliente y que las notas de la versión reflejen la próxima corrección.
John carga el parche e informa al cliente sobre la solución. Keith revisa y aprueba el parche, y John procede a actualizar la aplicación en la tienda. Fatima informa al cliente sobre la solución y este expresa alivio y gratitud por la pronta respuesta. Dave elogia al equipo por su colaboración y acción rápida, y enfatiza la importancia de mantener un buen trabajo.
En resumen, el equipo abordó rápidamente un problema urgente en el que la aplicación de un cliente se bloqueaba al cargar. Investigaron el problema, identificaron un problema de compatibilidad con iOS 15.1, lo solucionaron y prepararon un parche para su implementación. Se mantuvo informado al cliente durante todo el proceso y la solución se implementó con éxito, lo que resultó en un cliente aliviado y agradecido.
```

**Listado 3-11 RESPONSE. Cómo obtener una versión simplificada de una conversación más compleja**

#### Prompt #4: “Give Me Suggestions on Next Steps”

Además de hacer un resumen más fácil de entender, ChatGPT puede explicarlo en diferentes estilos y “tonos”. Vamos a aumentar la P superior a 0,75 porque queremos que ChatGPT piense en más posibilidades que las predeterminadas. También vamos a aumentar la penalización por presencia a 0,5 porque queremos fomentar una respuesta versátil.

<img width="910" alt="image" src="https://github.com/user-attachments/assets/da26ccee-fb82-45ad-9939-0e1c934347ec">

```text
System: You are a helpful assistant
User:  Fatima [16:00 | 02/08/2019]: Hey everyone, I have an urgent ...
User: I'm a QA engineer at the company. Give me suggestions on next steps.
Model: gpt-4
Temperature: 1
Maximum length: 1200
Top P: 0.75
Frequency penalty: 0
Presence penalty: 0.5
```

**Listing 3-12 PROMPT. Asking to ChatGPT for Advice on the Best Next Steps**

```text
As a QA engineer, here are some suggestions for next steps:
1. Test the patch: Once the patch has been deployed to the app store, thoroughly test it on various devices and operating systems to ensure that the issue has been resolved and there are no new bugs or regressions introduced.
2. Conduct regression testing: In addition to testing the specific issue, perform a comprehensive regression test to ensure that the fix does not have any unintended side effects on other functionalities of the app.
3. Communicate the fix to the client: Keep the client updated on the progress and let them know that the fix is available in the latest app update. Provide them with clear instructions on how to update their app and encourage them to test it on their end as well.
4. Monitor user feedback: Keep an eye on user feedback after the fix has been deployed. Encourage users to report any issues they encounter, and be proactive in addressing them promptly.
5. Document the issue and resolution: Create a detailed report documenting the issue, the steps taken to reproduce and resolve it, and any other relevant information. This will serve as a reference for future troubleshooting and help improve the development process.
6. Conduct a post-mortem analysis: After the issue has been resolved and the fix has been deployed, schedule a post-mortem meeting with the team to discuss the root cause, lessons learned, and any process improvements that can be implemented to prevent similar issues in the future.
7. Continuous improvement: Use this incident as an opportunity to identify areas of improvement in the development and testing processes. Evaluate if there are any changes that can be made to prevent similar issues from occurring in the future.
Remember, open communication, collaboration, and continuous learning are key to ensuring the highest quality of your app and maintaining a strong relationship with your clients.
```

**Listing 3-13 RESPONSE. Suggestions from ChatGPT on Possible Next Steps**

```text
Sistema : Eres un asistente útil
Usuario : Fatima [16:00 | 08/02/2019]: Hola a todos, tengo una consulta urgente...
Usuario : Soy ingeniero de control de calidad en la empresa. Denme sugerencias sobre los próximos pasos.
Modelo : gpt-4
Temperatura : 1
Longitud máxima: 1200
P superior: 0,75
Penalización de frecuencia: 0
Penalización por presencia: 0,5
```

**Listado 3-12 PROMPT. Pida a ChatGPT que le aconseje sobre los mejores pasos a seguir**

```text
Como ingeniero de control de calidad, aquí hay algunas sugerencias para los próximos pasos:
1. Pruebe el parche: una vez que el parche se haya implementado en la tienda de aplicaciones, pruébelo exhaustivamente en varios dispositivos y sistemas operativos para asegurarse de que el problema se haya resuelto y de que no se hayan introducido nuevos errores ni regresiones.
2. Realice pruebas de regresión: además de probar el problema específico, realice una prueba de regresión integral para asegurarse de que la solución no tenga efectos secundarios no deseados en otras funcionalidades de la aplicación.
3. Comunique la solución al cliente: mantenga al cliente informado sobre el progreso y hágale saber que la solución está disponible en la última actualización de la aplicación. Bríndele instrucciones claras sobre cómo actualizar su aplicación y anímelo a que la pruebe también en su dispositivo.
4. Controle los comentarios de los usuarios: esté atento a los comentarios de los usuarios después de que se haya implementado la solución. Incentive a los usuarios a que informen sobre cualquier problema que encuentren y sea proactivo para abordarlo rápidamente.
5. Documente el problema y su resolución: cree un informe detallado que documente el problema, los pasos que se tomaron para reproducirlo y resolverlo, y cualquier otra información relevante. Esto servirá como referencia para la resolución de problemas en el futuro y ayudará a mejorar el proceso de desarrollo.
6. Realice un análisis post mortem: después de que se haya resuelto el problema y se haya implementado la solución, programe una reunión post mortem con el equipo para analizar la causa raíz, las lecciones aprendidas y cualquier mejora de proceso que se pueda implementar para evitar problemas similares en el futuro.
7. Mejora continua: Utilice este incidente como una oportunidad para identificar áreas de mejora en los procesos de desarrollo y prueba. Evalúe si hay cambios que se puedan realizar para evitar que se produzcan problemas similares en el futuro.
Recuerde, la comunicación abierta, la colaboración y el aprendizaje continuo son clave para garantizar la máxima calidad de su aplicación y mantener una relación sólida con sus clientes.
```

**Listado 3-13 RESPONSE. Sugerencias de ChatGPT sobre posibles pasos a seguir**

Ahora bien, por supuesto, ChatGPT (como cualquier otra forma de inteligencia artificial del planeta) no es del todo perfecto. Por ejemplo, la recomendación número 3 es válida, salvo por el hecho de que no suele ser responsabilidad de una persona de control de calidad comunicar algo directamente al cliente. Esa comunicación se puede hacer a través del soporte técnico o con un gerente de producto que tenga esos canales de comunicación (especialmente si es un cliente importante). Por lo tanto, la sugerencia está bien, pero no es adecuada para una persona con ese rol dentro de una empresa.

#### Hablemos de ingeniería real

Si buscas en Google el término “prompt engineering - ingeniería de indicaciones”, encontrarás un montón de ejemplos, blogs e incluso sitios web completos con planes de suscripción que intentarán convencerte de que las indicaciones perfectas se pueden crear simplemente utilizando texto. Como has visto en los ejemplos anteriores, la ingeniería de indicaciones no se puede lograr únicamente mediante la elaboración de entradas de texto.

En realidad, el proceso es bastante similar a cocinar un plato sofisticado. Imagínese intentar cocinar, por ejemplo, beef bourguignon utilizando solo sal como condimento y descuidando todos los demás ingredientes y especias. Sinceramente, el resultado palidecería en comparación con el plato en sí.

De manera similar, intente armar una orquesta completa pero use solo un instrumento y un músico. Esa es una vergonzosa "banda de un solo hombre". Por lo tanto, simplemente ajustar el texto al mensaje no es suficiente para realizar una verdadera ingeniería de mensajes. Los parámetros como la temperatura del modelo, que controla la aleatoriedad; el top-p, que afecta la probabilidad de tokens; el modelo específico utilizado; la cantidad de tokens; y los demás parámetros del punto final juegan un papel muy importante para obtener una gran respuesta.

Este libro no trata sobre prompt engineering, ya que (como puede ver en la explicación anterior) involucra varios factores que no tienen nada que ver con Java. Sin embargo, se le recomienda encarecidamente que experimente con TODOS los parámetros de los modelos y puntos finales proporcionados por OpenAI para encontrar lo que funciona mejor para su caso de uso.

### Cómo registrar una Slack Bot App

Ahora que conocemos las distintas formas en que ChatGPT puede resumir un gran cuerpo de texto para nosotros, veamos qué es necesario para crear un bot simple en Java que capture programáticamente todos los mensajes de un canal dentro de una instancia de Slack.

**Nota**: Para llevar a cabo los pasos, necesitarás tener acceso administrativo a un espacio de trabajo de Slack. La mayoría de los desarrolladores NO tendrán estos niveles de permisos; por lo tanto, para experimentar a fondo, te recomiendo que crees tu propio espacio de trabajo personal de Slack para realizar pruebas. De esta manera, tendrás todos los derechos y privilegios para instalar tu bot de Slack.

Pero vayamos paso a paso. Primero, vamos a crear nuestra Slack bot app, así que dirígete al sitio web de la API de Slack (Figura 3-1 ).

https://api.slack.com/

<img width="835" alt="image" src="https://github.com/user-attachments/assets/4376ee6c-7500-4795-a6ad-3869e5f23855">

**Figura 3-1 Para crear un bot de Slack, vaya al sitio web de la API de Slack**

Por supuesto, necesitarás tener una cuenta de Slack para que esto funcione, así que si no tienes una, primero deberás crear una.

Después de iniciar sesión, vaya a la parte superior derecha de la página y navega hasta “**Your apps ➤ Create your first app**”, como se muestra en la Figura 3-1. En la terminología de Slack, un “bot” es una “aplicación” y los bots no pueden ejecutarse en una instancia de Slack a menos que se hayan registrado primero en Slack.

<img width="825" alt="image" src="https://github.com/user-attachments/assets/c16e23d8-14a7-4199-8c52-d6cd4559e0d7">

**Figura 3-2 Creación de una nueva aplicación de bot para Slack**

Como se muestra en la Figura 3-2, accederás a la página **Your Apps**, donde podrás administrar tus aplicaciones de Slack. Inmediatamente, verás una ventana emergente con el botón **Create an App** en el medio de la pantalla.

Selecciona la opción para crear tu aplicación desde cero. Esto se debe a que queremos poder manipular todos los detalles de la aplicación nosotros mismos sin complicar demasiado las cosas con un montón de configuraciones predeterminadas.

Luego, se le pedirá que especifique un nombre para su bot y que seleccione el espacio de trabajo al que desea que su bot tenga acceso, como se muestra en la Figura 3-3 .

Haga clic en el botón **Create App** para continuar.

<img width="825" alt="image" src="https://github.com/user-attachments/assets/532d3345-0fa2-4ac5-ac4b-996661b899ba">

**Figura 3-3 Creando una nueva aplicación de bot para Slack**

#### Cómo especificar lo que su bot puede (y no puede) hacer configurando el alcance

Ahora, verás una pantalla con muchas opciones para bots en espacios de trabajo de Slack. Sin embargo, lo primero que debes hacer es, desde la barra lateral de la izquierda, hacer clic en **OAuth & Permissions**.

Nuestro bot será bastante simple: todo lo que necesita hacer es leer los mensajes de un canal para darnos un resumen de lo que se dijo. Además de leer los mensajes, también necesitamos saber los nombres de las personas en el espacio de trabajo de Slack; de lo contrario, obtendremos una representación UUID de la persona en lugar de su nombre, lo cual no tiene sentido para nosotros.

Entonces, desplácese hacia abajo y asegúrese de agregar los siguientes ámbitos OAuth a su bot de Slack, como se muestra en la Figura 3-4.


* channels:history

* channels:read

* users:read

<img width="838" alt="image" src="https://github.com/user-attachments/assets/a6ea2fee-232a-4094-80be-fb4c4a930c92">

**Figura 3-4 Cómo agregar ámbitos para la aplicación Slack Bot**

#### Confirmando su configuración

Después de haber agregado los alcances apropiados para su bot, desplácese hacia arriba y haga clic en **Basic Information** en la barra lateral izquierda.

En la página que sigue, verá que ahora hay una marca de verificación verde junto a "Add features and functionality", lo que confirma que ha agregado sus alcances correctamente, como se muestra en la Figura 3-5.

<img width="825" alt="image" src="https://github.com/user-attachments/assets/6baabbf0-6988-4b74-9d52-9000e2df56e4">


**Figura 3-5 Confirme su configuración**

### Visualización de OAuth y Permissions Page

Como se muestra en la Figura 3-6, navegue a la página **OAuth & Permissions** y haga clic en el botón “Install to Workspace”.

<img width="826" alt="image" src="https://github.com/user-attachments/assets/69119cd2-5f0e-449d-b446-aa9a19f25712">


**Figura 3-6 La pantalla de OAuth & Permission**

### Cómo instalar la aplicación Slack Bot en tu espacio de trabajo

Ahora que se han solicitado todos los permisos, es momento de instalar el bot en el espacio de trabajo. Durante el proceso de instalación, deberías ver una pantalla como la que se muestra en la Figura 3-7.

<img width="828" alt="image" src="https://github.com/user-attachments/assets/671a4a4f-2056-4a01-9b10-1c35ab1b9194">

**Figura 3-7 “Instalación” de una nueva aplicación de bot de Slack**

Haga clic en el botón **Allow** para autorizar el bot y permitir los permisos que asignó en el paso anterior.

**Nota**: Es importante entender qué significa "instalar" aquí. En el sentido tradicional de Java, instalar una aplicación significa cargar un archivo JAR, WAR o EAR en otra máquina y ejecutarlo. Eso no es lo que sucede aquí.

Aquí, cuando "instalas" una aplicación de bot, estás habilitando tu espacio de trabajo de Slack para que una aplicación se una al espacio de trabajo, eso es todo. El código de tu bot se ejecutará en tu propia máquina, no en los servidores de Slack.

#### Cómo obtener tu Slack Bot (Access) Token

Esta vez, “token” en realidad significa token de acceso. Para conectarse a la API de Slack y acceder a los mensajes y a la información del usuario mediante programación, necesita un token OAuth específico generado para su bot de Slack.

<img width="827" alt="image" src="https://github.com/user-attachments/assets/7b1bb8f3-7cac-4fa9-b9ea-c82edb1ab203">

**Figura 3-8 Copia tu OAuth Token para tu Slack Bot App**

De regreso a la página **OAuth & Permissions**, asegúrese de copiar el token del bot (que generalmente comienza con “`xoxb-`”) desde la page here, como se muestra en la Figura 3-8 .

### Invitar tu Bot a tu Channel

A continuación, irás al canal que deseas usar para probar tu bot y escribirás el siguiente comando en el canal.

<img width="831" alt="image" src="https://github.com/user-attachments/assets/a6c1a44f-a2a1-473f-953f-fceef9fef8d9">

Seleccione la opción “**Add apps to this channel**”, y luego seleccione el nombre del bot de Slack que especificó anteriormente cuando registró el bot con Slack.

<img width="828" alt="image" src="https://github.com/user-attachments/assets/152a83df-c000-43b4-9245-1ba9c13bbd3c">

**Figura 3-9 Cómo agregar su Slack Bot a su Channel**

¡Felicitaciones! Ya registraste correctamente una aplicación de bot de Slack con Slack, la habilitaste para leer mensajes en tu espacio de trabajo y agregaste el bot de Slack a un canal. Antes de que podamos escribir el código Java para acceder al canal en nuestro espacio de trabajo, necesitamos saber cuál es el ID interno que Slack usa para nuestro canal.

#### Cómo encontrar el ID de tu canal

Vale, este es un paso sencillo de realizar. En Slack, haz clic con el botón derecho en el nombre de tu canal y selecciona la opción “**View Channel details**”. En la parte inferior de la ventana emergente aparece el ID de tu canal. Copia ese número y guárdalo para más adelante. Tu aplicación Java necesitará esto para unirse al canal correcto en tu espacio de trabajo de Slack.

### Cómo usar la aplicación Slack Bot para capturar automáticamente mensajes de un canal

Muy bien, ahora que hemos cumplido con todos los requisitos previos y conocemos el ID de nuestro canal, vayamos al código en Java que accede a todos los mensajes de un canal de Slack en particular.

#### Configurando sus dependencias

La biblioteca de API de Slack para Java proporciona métodos prácticos para interactuar con la plataforma Slack. Casi todo lo que necesitamos proviene de los paquetes `com.slack.api.methods.*` o `com.slack.api.model.*`, que existen en los archivos jar `slack-api-client-<VERSION>` y el `slack-api-model-<VERSION>`.

La API de Java de Slack tiene sus propias dependencias, que son:

* GSON
   * `gson-<VERSION>.jar`

* Kotlin
   * `kotlin-stdlib-<VERSION>.jar`
   * `kotlin-stdlib-jdk8-<VERSION>.jar`

* OK HTTP y OK IO
   * `okhttp-<VERSION>.jar`
   * `okio-<VERSION>.jar`
   * `okio-jvm-<VERSION>.jar`

* SL4J
   * `slf4j-api-<VERSION>.jar`
 
Por lo tanto, los listados 3-14 y 3-15 son fragmentos de los archivos Maven `pom.xml` y Gradle `build.gradle` necesarios (con las versiones con las que hice pruebas) para poder compilar todo.

```xml
<dependencies>
        <!-- Gson library -->
        <dependency>
            <groupId>com.google.code.gson</groupId>
            <artifactId>gson</artifactId>
            <version>2.10.1</version>
        </dependency>
        <!-- Kotlin standard libraries -->
        <dependency>
            <groupId>org.jetbrains.kotlin</groupId>
            <artifactId>kotlin-stdlib</artifactId>
            <version>1.6.20</version>
        </dependency>
        <dependency>
            <groupId>org.jetbrains.kotlin</groupId>
            <artifactId>kotlin-stdlib-jdk8</artifactId>
            <version>1.6.20</version>
        </dependency>
        <!-- OkHttp library -->
        <dependency>
            <groupId>com.squareup.okhttp3</groupId>
            <artifactId>okhttp</artifactId>
            <version>4.11.0</version>
        </dependency>
        <!-- Okio library -->
        <dependency>
            <groupId>com.squareup.okio</groupId>
            <artifactId>okio</artifactId>
            <version>3.2.0</version>
        </dependency>
        <dependency>
            <groupId>com.squareup.okio</groupId>
            <artifactId>okio-jvm</artifactId>
            <version>3.2.0</version>
        </dependency>
        <!-- Slack SDK libraries -->
        <dependency>
            <groupId>com.slack.api</groupId>
            <artifactId>slack-api-client</artifactId>
            <version>1.30.0</version>
        </dependency>
        <dependency>
            <groupId>com.slack.api</groupId>
            <artifactId>slack-api-model</artifactId>
            <version>1.30.0</version>
        </dependency>
        <!-- SLF4J logging facade -->
        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>slf4j-api</artifactId>
            <version>2.0.7</version>
        </dependency>
    </dependencies>
```

**Listado 3-14 Maven `pom.xml`**
