# 2. Usar ChatGPT como su pareja programador de Java

Bruce Hopkins 1  
(1)
Beaverton, Oregón, Estados Unidos
<hr>
 
Soy un gran admirador de algunas de las prácticas de XP (eXtreme Programming), y especialmente de la programación en pareja. No importa qué tipo de programación en pareja prefieras, implica que dos ingenieros se sienten frente a la misma pantalla y resuelvan el mismo problema juntos. Uno de los mayores beneficios que obtienes es un par de ojos nuevos sobre un problema y, por supuesto, ahora tienes dos ingenieros que han "tocado" el código base en lugar de uno solo. A veces puedes hacer que un ingeniero escriba el código y el otro escriba las pruebas y los comentarios. No importa cómo lo mires, todo es bueno.

Ahora, las API REST de OpenAI para ChatGPT y sus otros modelos son oficialmente compatibles con Python, Typescript, y por supuesto, cURL (que es el estándar de facto para las API REST ).

Existen algunas API de Java creadas por desarrolladores externos, pero el mayor problema (en mi opinión) es que este espacio está cambiando rápidamente. OpenAI actualiza constantemente sus modelos y sus interfaces HTTP y, como resultado, agregan o eliminan características y funcionalidades con frecuencia. Si elige utilizar una API de Java de terceros para su proyecto, corre el riesgo de usar una API que esté desactualizada o que no esté sincronizada con la API REST de OpenAI.

Entonces, en este capítulo, vamos a usar ChatGPT como nuestro programador en pareja y simplemente trasladaremos las API REST oficiales de OpenAI directamente a Java. Cada vez que OpenAI realiza algún cambio en sus lenguajes e interfaces oficialmente compatibles, tenemos todo lo necesario para actualizar nuestra propia biblioteca al instante. ¡Hagámoslo!

## Cómo crear su primera aplicación Java ChatGPT: `ListModels.java`

En realidad, aquí vamos a realizar dos tareas a la vez. Vamos a crear una aplicación básica en Java utilizando las API de OpenAI y, en el proceso, vamos a verificar que hayamos obtenido una clave API correctamente. Por lo tanto, no hace falta decir que, en caso de que aún no lo haya hecho, siga las instrucciones del Capítulo 1 para crear su cuenta de desarrollador de OpenAI y obtener su clave API. De ahora en adelante, todos los ejemplos de código de este libro requieren una clave API válida.

### List Models Endpoint

Uno de los servicios más básicos (pero también esenciales) a los que podemos recurrir es el endpoint **List Models**. ¿Por qué?, te preguntarás. El endpoint List Models te permite obtener una lista de todos los modelos de IA que están actualmente disponibles para que los utilicen los desarrolladores a través de la API REST.

#### Creando la Request

En la Tabla 2-1 se enumeran todos los parámetros HTTP necesarios para llamar al punto final de Modelos de lista.

**Tabla 2-1 Los parámetros HTTP necesarios para llamar al Endpoint List Models**
![image](https://github.com/user-attachments/assets/11fa126f-edbf-431c-a239-9d6e742415b4)



#### Manejo de la JSON Response

Después de invocar con éxito el endpoint **List Models**, el servicio proporcionará una respuesta JSON con la estructura que se muestra en la Tabla 2-2 .

#### Modelo (JSON)

**Tabla 2-2 La estructura del Model JSON Object**

![image](https://github.com/user-attachments/assets/4f07bd32-0262-49eb-8950-060b532a3788)

**Nota**: Dado que los objetos JSON pueden contener matrices (que pueden ser difíciles de representar en una tabla), utilizamos la notación “↳” para indicar los elementos de una matriz. Como puede ver en la tabla anterior, “id”, “object”, “created” y “owned_by” son todos elementos de la matriz “data” en la respuesta JSON.

Ahora que tenemos los detalles de la solicitud y la respuesta HTTP, podemos crear la aplicación ListModel.java usando el mensaje que se muestra en el Listado 2-1.

![image](https://github.com/user-attachments/assets/09b073e4-9a62-4d31-b0aa-d62a4cc2864e)

```sh
System: You are a Java developer
User: Take the following cURL command and convert it to Java. Name the file, "ListModels.java"
User: curl https://api.openai.com/v1/models \
  -H "Authorization: Bearer $OPENAI_API_KEY"
```

**Listado 2-1 INSTRUCCIÓN. Uso de ChatGPT para crear la aplicación `ListModels.java`**

Entonces, después de enviar el mensaje, ChatGPT le proporcionará una respuesta como se muestra en el Listado 2-2 .


![image](https://github.com/user-attachments/assets/7aa8ea62-6f85-4e6f-801f-0d9865e82ebd)

```java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;
public class ListModels {
    public static void main(String[] args) {
        try {
            // Create URL object for the API endpoint
            URL url = new URL("https://api.openai.com/v1/models");
            // Create HttpURLConnection object
            HttpURLConnection conn = (HttpURLConnection) url.openConnection();
            // Set request method
            conn.setRequestMethod("GET");
            // Set Authorization header
            conn.setRequestProperty("Authorization", "Bearer $OPENAI_API_KEY");
            // Get response code
            int responseCode = conn.getResponseCode();
            // If the request was successful (status code 200)
            if (responseCode == HttpURLConnection.HTTP_OK) {
                // Read the response from the API
                BufferedReader in = new BufferedReader(new InputStreamReader(conn.getInputStream()));
                String inputLine;
                StringBuilder response = new StringBuilder();
                while ((inputLine = in.readLine()) != null) {
                    response.append(inputLine);
                }
                in.close();
                // Print the response
                System.out.println(response.toString());
            } else {
                System.out.println("Request failed. Response Code: " + responseCode);
            }
            // Close the connection
            conn.disconnect();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**Listado 2-2 RESPONSE. `ListModels.java`**

¡Fantástico! Ahora todo lo que tienes que hacer es reemplazar “$OPENAI_API_KEY” con el valor de tu clave API actual.

Después de ejecutar esta clase, obtendrá un archivo JSON que contiene todos los modelos ofrecidos por la API de OpenAI, como se muestra en el Listado 2-3 .

![image](https://github.com/user-attachments/assets/795a97cc-039c-465f-9072-11eec5305ef5)

```json
{
  "object": "list",
  "data": [
    {
      "id": "text-search-babbage-doc-001",
      "object": "model",
      "created": 1651172509,
      "owned_by": "openai-dev"
    },
    {
      "id": "gpt-4",
      "object": "model",
      "created": 1687882411,
      "owned_by": "openai"
    },
    {
      "id": "gpt-3.5-turbo-16k",
      "object": "model",
      "created": 1683758102,
      "owned_by": "openai-internal"
    },
    {
      "id": "curie-search-query",
      "object": "model",
      "created": 1651172509,
      "owned_by": "openai-dev"
    },
    {
      "id": "text-davinci-003",
      "object": "model",
      "created": 1669599635,
      "owned_by": "openai-internal"
    },
    {
      "id": "text-search-babbage-query-001",
      "object": "model",
      "created": 1651172509,
      "owned_by": "openai-dev"
    },
    {
      "id": "babbage",
      "object": "model",
      "created": 1649358449,
      "owned_by": "openai"
    },
...
```

**Listado 2-3 3RESPONSE. La respuesta JSON parcial después de ejecutar `ListModels.java`**

Los listados 2 y 3 son una lista parcial debido a la gran cantidad de modelos disponibles para que los utilicen los desarrolladores. Sin embargo, la buena noticia es que la respuesta completa se proporciona como una tabla en el Apéndice.

Ahora que podemos obtener mediante programación una lista de modelos disponibles para usar, es momento de enviar mensajes a ChatGPT mediante Java. Esto se logra mediante el Endpoint Chat.

### Endpoint Chat

El Endpoint Chat (anteriormente llamado “Chat Completion”) es un servicio REST que es básicamente una representación 1 a 1 de lo que puede hacer en el Chat Playground; por lo tanto, este servicio debería resultarle algo natural.

#### Creando la Request

En la Tabla 2-3 se enumeran todos los parámetros HTTP necesarios para llamar al punto final de chat.

**Tabla 2-3 Los parámetros HTTP para el endpoint Chat**

![image](https://github.com/user-attachments/assets/0620dec6-b350-4ef7-8e55-b3759efc38f9)

La Tabla 2-4 describe el formato del objeto JSON necesario para el request body del endpoint Chat. Después de un vistazo rápido, puede ver que solo se requieren algunos campos para invocar el servicio correctamente.

#### Chat (JSON)

**Tabla 2-4 La estructura del objeto JSON de Chat**

![image](https://github.com/user-attachments/assets/6bdc54fb-02fb-4d72-9438-36072d11744f)

![image](https://github.com/user-attachments/assets/f1a2b780-e235-4e55-af26-f9b564808f68)

![image](https://github.com/user-attachments/assets/252287c9-35ae-4620-b45c-699db538739e)

![image](https://github.com/user-attachments/assets/9397eb29-d2b4-45b2-9e6c-d3e3f8ff3617)

![image](https://github.com/user-attachments/assets/7b917425-5533-4a7c-960c-42e53e082acb)

![image](https://github.com/user-attachments/assets/a36b61e3-fe97-406c-a72a-ee4ae443276f)

![image](https://github.com/user-attachments/assets/50d5f0aa-43f8-41ce-90ec-710d59a9881b)

![image](https://github.com/user-attachments/assets/0d24e6fe-37a6-4f13-976f-b6c5434c4958)

![image](https://github.com/user-attachments/assets/9ef33b8f-9321-4fc3-95f8-fd52a4eaab34)

![image](https://github.com/user-attachments/assets/6edbd5a6-6f8b-4cda-a728-78b6e297e5c7)

![image](https://github.com/user-attachments/assets/b2aba6d4-e490-4dea-a902-ff187e5db477)

![image](https://github.com/user-attachments/assets/8743560b-1415-4079-8888-709e51071810)


**Nota**: En este libro, trabajaremos con el parámetro "stream" configurado, en su configuración predeterminada, que es falsa. Esto significa que recibiremos todos los resultados de ChatGPT a la vez como una única respuesta HTTP. Sin embargo, hay casos en los que desearía que esta configuración se establezca en verdadero. Digamos que está creando, por ejemplo, un bot de chat interactivo habilitado por voz. Digamos también que está interesado en convertir el texto de ChatGPT a audio para que sus usuarios puedan escuchar una respuesta audible. En tal caso, definitivamente querrá establecer el parámetro "stream" en verdadero. ¿Por qué es así? Cuando la respuesta se transmite de vuelta a su aplicación Java, tiene la oportunidad en ese momento de convertir el fragmento de texto a audio. Esto le permitirá trabajar en paralelo con la conversión de fragmentos de texto a audio mientras recibe más texto simultáneamente. Esto hará que la respuesta parezca más natural para el usuario final y ayudará a que la conversación se sienta como una conversación real.

El listado 2-4 es un ejemplo de cómo se vería el objeto JSON para invocar correctamente el Endpoint Chat.

```json
{
  "model": "gpt-3.5-turbo",
  "messages": [
    {
      "role": "system",
      "content": "You are a product marketer"
    },
    {
      "role": "user",
      "content": "Explain why Java is so widely used in the enterprise "
    }
  ],
  "temperature": 1,
  "max_tokens": 256,
  "top_p": 1,
  "frequency_penalty": 0,
  "presence_penalty": 0
}
```

**Listado 2-4 Ejemplo del Chat JSON Object**

### Manejo de la Response

Después de invocar correctamente el  Endpoint Chat, la API responderá con un Chat Completion object o con un stream de fragmentos de finalización si la transmisión está habilitada. A continuación, se muestra un desglose del objeto de finalización de chat.

#### Chat Completion (JSON)

**Tabla 2-5 La estructura del Chat Competion JSON Object**



El listado 2-5 es un ejemplo de la respuesta JSON después de invocar el punto final de chat.


Listado 2-5El objeto JSON de finalización de chat
Espera, ¿cuántos tokens hay en mi mensaje?
En un momento dado, comenzarás a pensar en los mensajes que planeas enviar a ChatGPT y a pensar mucho en las limitaciones de tokens (y los costos) con respecto al modelo que deseas utilizar. En caso de que lo hayas olvidado, asegúrate de volver a consultar la Tabla 1-1 para obtener una lista de modelos y el precio de los tokens. Además, OpenAI creó un sitio web fácil de usar que te permite ver cuántos tokens hay en tu mensaje, como se muestra en la Figura 2-1 .

Contador de tokens ChatGPT
https://platform.openai.com/tokenizer

Figura 2-1El tokenizador ChatGPT puede brindarle un recuento rápido de los tokens en su mensaje
Creación de la próxima aplicación Java: ChatGPTClient.java
Ahora es el momento de crear nuestro propio ChatGPTClient . Vamos a empezar y a proporcionarle a ChatGPT la información que necesita a través de ChatGPT Playground.
Sistema : Eres un desarrollador de Java
Usuario : Convierte el siguiente comando cURL a Java. Asegúrate de que la URL y las claves API sean variables. Quiero usar la biblioteca Jackson para crear el objeto JSON en la solicitud. Nombra la clase principal ChatGPTClient y crea clases auxiliares si es necesario.
Usuario:
rizo https://api.openai.com/v1/chat/completions \
  -H "Tipo de contenido: aplicación/json" \
  -H "Autorización: Portador $OPENAI_API_KEY" \
  -d '{
  "modelo": "gpt-3.5-turbo",
  "mensajes": [
    {
      "rol": "sistema",
      "contenido": "Eres un comercializador de productos"
    },
    {
      "rol": "usuario",
      "content": "Explique por qué Java se utiliza tan ampliamente en la empresa"
    }
  ],
  "temperatura": 1,
  "máximo_tokens": 256,
  "arriba_p": 1,
  "penalización de frecuencia": 0,
  "penalización por presencia": 0
}'
Listado 2-6La conversación inicial para crear ChatGPTClient.java
La respuesta de ChatGPT fue un buen comienzo, pero no tenía todo exactamente como yo quería. Ahora bien, como no especifiqué exactamente cómo se debían haber realizado las llamadas HTTP, ChatGPT decidió utilizar la biblioteca Apache HTTPClient. Por lo tanto, agregué el siguiente mensaje de usuario (Listado 2-7 ).
Usuario : tengo un entorno Java 11, por lo que utilizo clases HTTP de Java 11 para las llamadas a la API. Prefiero utilizar Java puro en lugar de Apache HttpClient
Listado 2-7AVISO: Cómo añadir información adicional a la conversación para crear ChatGPTClient.java
El objetivo aquí es tener una conversación. No es práctico esperar que ChatGPT produzca exactamente lo que quieres en un solo mensaje. ¡Ni siquiera los desarrolladores hacen eso! Por lo tanto, siéntete libre de tener una conversación con ChatGPT y aclararle cosas que puede haber adivinado o asumido incorrectamente.

El listado 2-8 muestra el resultado final para ChatGPTClient.java .

importar com.fasterxml.jackson.core.JsonProcessingException;
importar com.fasterxml.jackson.databind.ObjectMapper;
importar com.fasterxml.jackson.annotation.JsonProperty;
importar java.io.BufferedReader;
importar java.io.IOException;
importar java.io.InputStreamReader;
importar java.io.OutputStream;
importar java.net.HttpURLConnection;
importar java.net.URL;
importar java.util.ArrayList;
importar java.util.List;
clase pública ChatGPTClient {
        public static void principal (cadena [] argumentos) {
        String openAIKey = "inserte su clave API aquí";
        Punto final de cadena = "https://api.openai.com/v1/chat/completions";
        Modelo de cadena = "gpt-3.5-turbo";
        temperatura del flotador = 1.0f;
        int máximo_tokens = 256;
        flotante top_p = 1.0f;
        int frecuencia_penalidad = 0;
        int presencia_penalidad = 0;
        Lista<Mensaje> mensajes = nueva ArrayList<>();
        mensajes.add(new Message("sistema", "Usted es un comercializador de productos.");
        messages.add(new Message("usuario", "Explique por qué Java se usa tan ampliamente en la empresa"));
        Cadena jsonInput = nulo;
        intentar {
            ObjectMapper mapeador = nuevo ObjectMapper();
            Chat chat = new Chat(modelo, mensajes, temperatura, max_tokens, top_p, penalización_de_frecuencia, penalización_de_presencia);
            jsonInput = mapper.writeValueAsString(chat);
        } captura (JsonProcessingException e) {
            es.printStackTrace();
        }
        intentar {
            URL url = nueva URL(punto final);
            HttpURLConnection conexión = (HttpURLConnection) url.openConnection();
            conexión.setRequestMethod("POST");
            conexión.setRequestProperty("Tipo-de-contenido", "application/json");
            connection.setRequestProperty("Autorización", "Portador " + openAIKey);
            conexión.setDoOutput(true);
            OutputStream outputStream = conexión.getOutputStream();
            salidaStream.write(jsonInput.getBytes());
            salidaStream.flush();
            flujo de salida.close();
            int responseCode = conexión.getResponseCode();
            si (código de respuesta == HttpURLConnection.HTTP_OK) {
                lector BufferedReader = nuevo BufferedReader(nuevo InputStreamReader(connection.getInputStream()));
                Respuesta de StringBuilder = new StringBuilder();
                Línea de cuerda;
                mientras ((linea = lector.readLine()) != null) {
                    respuesta.append(linea);
                }
                lector.close();
                //Imprime la respuesta
                Sistema.out.println(respuesta.toString());
            } demás {
                System.out.println("Error: " + código de respuesta);
            }
            conexión.desconectar();
        } captura (IOException e) {
            es.printStackTrace();
        }
    }
    // Clase auxiliar para representar el objeto Chat
    clase estática Chat {
        @JsonProperty("modelo")
        modelo de cadena privada;
        @JsonProperty("mensajes")
        Lista privada<Mensaje> mensajes;
        @JsonProperty("temperatura")
        temperatura flotante privada;
        @JsonProperty("máximo_tokens")
        int privado max_tokens;
        @JsonProperty("top_p")
        flotante privado top_p;
        @JsonProperty("penalización de frecuencia")
        privado int frecuencia_penalty;
        @JsonProperty("penalización por presencia")
        privado int presencia_penalty;
        público Chat(String modelo, List<Mensaje> mensajes, float temperatura, int max_tokens, float top_p, int frequency_penalty, int presence_penalty) {
            este.modelo = modelo;
            this.messages = mensajes;
            esta.temperatura = temperatura;
            esto.max_tokens = max_tokens;
            esto.top_p = top_p;
            esto.frequency_penalty = penalización_de_frecuencia;
            esto.penalización_de_presencia = pena_de_presencia;
        }
        // Getters y setters (opcionales, pero pueden ser útiles si necesita modificar el objeto más adelante)
        }
    // Clase auxiliar para representar el mensaje de chat
    clase estática Mensaje {
        @JsonProperty("rol")
        rol de cadena privada;
        @JsonProperty("contenido")
        contenido de cadena privada;
        mensaje público (cadena rol, cadena contenido) {
            este.role = rol;
            este.contenido = contenido;
        }
    }
}
Listado 2-8RESPUESTA. ChatGPTClient.java
Al examinar la lista de códigos anterior, verá que las llamadas HTTP se realizan utilizando API de Java puras y no utilizando ninguna biblioteca externa, tal como solicité en el mensaje. Sin embargo, tenga en cuenta que crear y analizar objetos JSON en Java puro puede ser una molestia, por lo que especifiqué personalmente que se debe utilizar la API de Jackson, lo que (como puede ver) se refleja en las declaraciones de importación y en el código en sí.

El código resultante incluye dos clases internas, Chat y Message , que se pueden separar fácilmente en archivos Java independientes. Puedo hacerlo manualmente o agregar un nuevo mensaje de "Usuario" a ChatGPT para solicitar que las clases internas se separen en archivos Java distintos.

Después de ejecutar ChatGPTClient.java , el Listado 2-9 tiene la respuesta.

{
  "id": "chatcmpl-7xIRvjByGobmWH9Vo7OObHCSSwzgI",
  "objeto": "chat.completado",
  "creado": 1694366627,
  "modelo": "gpt-3.5-turbo-0613",
  "opciones": [
    {
      "índice": 0,
      "mensaje": {
        "rol": "asistente",
        "content": "Java se utiliza ampliamente en las empresas, principalmente debido a sus numerosos beneficios y características que lo convierten en una opción popular entre las grandes organizaciones. A continuación, se muestran algunas de las razones clave por las que Java se adopta tan ampliamente en las empresas:\n\n1. Independencia de la plataforma: una de las mayores ventajas de Java es su independencia de la plataforma. Los programas Java pueden ejecutarse en cualquier sistema operativo, lo que lo hace muy adaptable a una amplia gama de dispositivos y plataformas. Esto facilita que las empresas desarrollen aplicaciones que se puedan implementar en diferentes sistemas sin modificaciones importantes.\n\n2. Robustez y estabilidad: Java es conocido por su fuerte énfasis en la confiabilidad, la estabilidad y el manejo de errores. Tiene un sistema de administración de memoria incorporado que evita fugas de memoria y garantiza un rendimiento sólido. Esta estabilidad es muy valorada en entornos empresariales donde los sistemas deben ejecutarse de manera constante sin interrupciones.\n\n3. Escalabilidad: Java ofrece una excelente escalabilidad, lo que lo hace adecuado para aplicaciones empresariales a gran escala. Proporciona un soporte sólido para subprocesos múltiples, lo que permite que las aplicaciones gestionen una gran cantidad de usuarios simultáneos sin problemas. La capacidad de Java para manejar altas cargas de tráfico y distribuir el procesamiento entre múltiples servidores lo hace ideal para sistemas de nivel empresarial.\n\n4. Biblioteca estándar y marcos de trabajo enriquecidos: Java viene con una biblioteca estándar integral, que ofrece una amplia gama de funciones y clases predefinidas que simplifican el desarrollo. Además, Java tiene una "
      },
      "finish_reason": "longitud"
    }
  ],
  "uso": {
    "tokens_de_aviso": 28,
    "tokens_de_finalización": 256,
    "total_tokens": 284
  }
}
Listado 2-9RESPUESTA. Los resultados de llamar a ChatGPTClient.java
¿Observaste en la lista anterior que la respuesta a mi solicitud se truncó? “Además, Java tiene un” no es una oración completa, pero como solicité que no se usaran más de 256 tokens en la respuesta, no superó esa limitación.

Conclusión
Contrariamente a la creencia popular, ChatGPT no lee la mente. No tiene la capacidad de reemplazar a los desarrolladores y arquitectos porque es (¡ja!) artificialmente inteligente. Es muy útil para hacer una sola pregunta y recibir una respuesta inmediata y directa. Definitivamente se puede usar para convertir un mensaje (o solicitud) en lenguaje natural en código, pero definitivamente se necesita un desarrollador para tomar la decisión de si el código resultante se debe usar, refinar o descartar por completo.
