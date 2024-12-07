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

AQUIIIIII
### ChatGPT está aquí para quitarle el trabajo a todo el mundo (en realidad, no)
En mi humilde opinión, todas las empresas del mundo tienen una mina de oro de información sin explotar. Si utiliza un sistema que lleva un registro de los intercambios entre empleados, una base de datos de solicitudes de asistencia de sus clientes o cualquier gran repositorio de texto (sí, esto incluye su correo electrónico, Microsoft Exchange y Gmail corporativo), entonces tiene un gran repositorio de texto no estructurado que está esperando a ser utilizado.

Por lo tanto, el mejor uso de ChatGPT no es eliminar el trabajo de nadie, sino que debe utilizarse para aumentar y extender lo que los miembros del equipo de su empresa ya están haciendo. Como vimos en el capítulo anterior, como programador, ChatGPT puede funcionar como un programador en pares muy eficaz. También es muy bueno para realizar ciertas tareas difíciles de manera muy eficiente y rápida. Veamos un ejemplo práctico de lo que se puede hacer para aprovechar una gran fuente de texto no estructurado.

Análisis de un problema real: atención al cliente para una empresa de software
Una de las tareas más agotadoras en el desarrollo de software es brindar soporte técnico. Imagine la alegría de recibir llamadas y mensajes todo el día de personas que podrían estar frustradas, confundidas o simplemente necesitar una solución mientras usan su software . Estas son algunas de las razones por las que la atención al cliente es un hueso duro de roer:
Sus usuarios finales y sus clientes son notoriamente malos a la hora de explicar los problemas con su software.

Los técnicos de nivel 1, que suelen ser la primera línea de defensa, suelen ocuparse de los problemas más básicos o de los errores de los usuarios. Pero cuando los problemas se vuelven más complejos, los usuarios pasan al nivel 2.

El nivel medio es un lugar complicado, porque tienen más conocimientos y experiencia que el personal de soporte técnico del nivel 1; sin embargo, no tienen la oportunidad de obtener respuestas directamente del usuario final.

Los problemas realmente graves se escalan al nivel 3; sin embargo, este es el personal de soporte técnico más caro porque tiene más conocimientos y experiencia. Tienen experiencia práctica con el código, así como con los servidores y la infraestructura.

Trabajemos con un ejemplo real de una conversación típica dentro de un canal de soporte técnico típico dentro de Slack. A continuación, se incluye una lista de los miembros del equipo y sus funciones dentro de una empresa ficticia :
Fátima (Representante de Servicio al Cliente)

John (Ingeniero de software)

Dave (primer ministro)

Keith (director técnico)

El listado 3-5 ofrece un ejemplo de una conversación entre los miembros del equipo de una empresa de software emergente. Fátima, la representante de atención al cliente, informa al equipo que su aplicación se bloquea inmediatamente después de iniciarse (no es un problema agradable). Keith, el director de tecnología, interviene de inmediato para escalar el problema.
