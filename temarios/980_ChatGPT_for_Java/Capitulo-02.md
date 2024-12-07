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

**CASO Ejecutado en mi Cuenta**

![image](https://github.com/user-attachments/assets/4c6dcf01-6369-49a1-af6e-976564e453cd)

![image](https://github.com/user-attachments/assets/9799ddbf-18cc-4329-911a-6faf8506a027)

![image](https://github.com/user-attachments/assets/6f1c636f-27dc-4721-abd7-a8a750aec2c3)


Certainly! Below is the Java code that corresponds to your cURL command. It uses the `HttpURLConnection` class to send a GET request to the OpenAI API to list the models. Save the file as `ListModels.java`.

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;

public class ListModels {
    private static final String API_URL = "https://api.openai.com/v1/models";
    private static final String API_KEY = System.getenv("OPENAI_API_KEY"); // Use environment variable for the API key

    public static void main(String[] args) {
        try {
            // Create a URL object
            URL url = new URL(API_URL);
            HttpURLConnection connection = (HttpURLConnection) url.openConnection();
            
            // Set the request method to GET
            connection.setRequestMethod("GET");
            
            // Set the Authorization header
            connection.setRequestProperty("Authorization", "Bearer " + API_KEY);
            
            // Get the response code
            int responseCode = connection.getResponseCode();
            System.out.println("Response Code: " + responseCode);
            
            // Read the response
            if (responseCode == HttpURLConnection.HTTP_OK) {
                BufferedReader in = new BufferedReader(new InputStreamReader(connection.getInputStream()));
                String inputLine;
                StringBuilder response = new StringBuilder();

                while ((inputLine = in.readLine()) != null) {
                    response.append(inputLine);
                }
                in.close();

                // Print the response from the API
                System.out.println("Response: " + response.toString());
            } else {
                System.out.println("GET request failed. Response Code: " + responseCode);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### Instructions to use the code:
1. **Create the File**: Open your text editor or IDE and create a file named `ListModels.java`.
2. **Copy the Code**: Copy and paste the provided code into the file.
3. **Set the API Key**: Ensure that your OpenAI API key is set as an environment variable named `OPENAI_API_KEY`. On Linux or macOS, you can set it using:
   ```bash
   export OPENAI_API_KEY=your_api_key_here
   ```
   On Windows, use:
   ```cmd
   set OPENAI_API_KEY=your_api_key_here
   ```
4. **Compile the Java File**: Open your terminal or command prompt and navigate to the directory where your `ListModels.java` file is located. Compile the Java file using:
   ```bash
   javac ListModels.java
   ```
5. **Run the Java Program**: Execute the compiled program with:
   ```bash
   java ListModels
   ```

This will perform the equivalent of the cURL command, making an authorized request to list the models from the OpenAI API and printing the response.


¡Fantástico! Ahora todo lo que tienes que hacer es reemplazar “$OPENAI_API_KEY” con el valor de tu clave API actual.

### Ejecución desde Java

![image](https://github.com/user-attachments/assets/e3c7b136-df90-4cd8-bdf0-aad4cf7683e6)

```json
Response: {  "object": "list",  "data": [    {      "id": "gpt-4o-2024-08-06",      "object": "model",      "created": 1722814719,      "owned_by": "system"    },    {      "id": "gpt-4o-realtime-preview",      "object": "model",      "created": 1727659998,      "owned_by": "system"    },    {      "id": "gpt-4o",      "object": "model",      "created": 1715367049,      "owned_by": "system"    },    {      "id": "dall-e-2",      "object": "model",      "created": 1698798177,      "owned_by": "system"    },    {      "id": "text-embedding-ada-002",      "object": "model",      "created": 1671217299,      "owned_by": "openai-internal"    },    {      "id": "gpt-4o-realtime-preview-2024-10-01",      "object": "model",      "created": 1727131766,      "owned_by": "system"    },    {      "id": "gpt-4-1106-preview",      "object": "model",      "created": 1698957206,      "owned_by": "system"    },    {      "id": "text-embedding-3-large",      "object": "model",      "created": 1705953180,      "owned_by": "system"    },    {      "id": "gpt-4o-mini",      "object": "model",      "created": 1721172741,      "owned_by": "system"    },    {      "id": "babbage-002",      "object": "model",      "created": 1692634615,      "owned_by": "system"    },    {      "id": "gpt-4o-2024-11-20",      "object": "model",      "created": 1731975040,      "owned_by": "system"    },    {      "id": "gpt-4-turbo-preview",      "object": "model",      "created": 1706037777,      "owned_by": "system"    },    {      "id": "o1-mini",      "object": "model",      "created": 1725649008,      "owned_by": "system"    },    {      "id": "davinci-002",      "object": "model",      "created": 1692634301,      "owned_by": "system"    },    {      "id": "o1-mini-2024-09-12",      "object": "model",      "created": 1725648979,      "owned_by": "system"    },    {      "id": "gpt-4-0125-preview",      "object": "model",      "created": 1706037612,      "owned_by": "system"    },    {      "id": "whisper-1",      "object": "model",      "created": 1677532384,      "owned_by": "openai-internal"    },    {      "id": "dall-e-3",      "object": "model",      "created": 1698785189,      "owned_by": "system"    },    {      "id": "gpt-4o-mini-2024-07-18",      "object": "model",      "created": 1721172717,      "owned_by": "system"    },    {      "id": "o1-preview",      "object": "model",      "created": 1725648897,      "owned_by": "system"    },    {      "id": "gpt-3.5-turbo-16k",      "object": "model",      "created": 1683758102,      "owned_by": "openai-internal"    },    {      "id": "o1-preview-2024-09-12",      "object": "model",      "created": 1725648865,      "owned_by": "system"    },    {      "id": "omni-moderation-latest",      "object": "model",      "created": 1731689265,      "owned_by": "system"    },    {      "id": "omni-moderation-2024-09-26",      "object": "model",      "created": 1732734466,      "owned_by": "system"    },    {      "id": "tts-1-hd-1106",      "object": "model",      "created": 1699053533,      "owned_by": "system"    },    {      "id": "gpt-4",      "object": "model",      "created": 1687882411,      "owned_by": "openai"    },    {      "id": "gpt-4-0613",      "object": "model",      "created": 1686588896,      "owned_by": "openai"    },    {      "id": "gpt-3.5-turbo",      "object": "model",      "created": 1677610602,      "owned_by": "openai"    },    {      "id": "gpt-3.5-turbo-0125",      "object": "model",      "created": 1706048358,      "owned_by": "system"    },    {      "id": "text-embedding-3-small",      "object": "model",      "created": 1705948997,      "owned_by": "system"    },    {      "id": "gpt-4-turbo",      "object": "model",      "created": 1712361441,      "owned_by": "system"    },    {      "id": "tts-1-hd",      "object": "model",      "created": 1699046015,      "owned_by": "system"    },    {      "id": "gpt-4-turbo-2024-04-09",      "object": "model",      "created": 1712601677,      "owned_by": "system"    },    {      "id": "gpt-3.5-turbo-1106",      "object": "model",      "created": 1698959748,      "owned_by": "system"    },    {      "id": "gpt-3.5-turbo-instruct",      "object": "model",      "created": 1692901427,      "owned_by": "system"    },    {      "id": "gpt-4o-audio-preview",      "object": "model",      "created": 1727460443,      "owned_by": "system"    },    {      "id": "gpt-4o-audio-preview-2024-10-01",      "object": "model",      "created": 1727389042,      "owned_by": "system"    },    {      "id": "tts-1",      "object": "model",      "created": 1681940951,      "owned_by": "openai-internal"    },    {      "id": "tts-1-1106",      "object": "model",      "created": 1699053241,      "owned_by": "system"    },    {      "id": "gpt-3.5-turbo-instruct-0914",      "object": "model",      "created": 1694122472,      "owned_by": "system"    },    {      "id": "chatgpt-4o-latest",      "object": "model",      "created": 1723515131,      "owned_by": "system"    },    {      "id": "gpt-4o-2024-05-13",      "object": "model",      "created": 1715368132,      "owned_by": "system"    }  ]}
```

### Llamada con Postman

![image](https://github.com/user-attachments/assets/8b4ce96e-586c-4f61-b346-1941e346a882)

```json
{
    "object": "list",
    "data": [
        {
            "id": "gpt-4o-2024-08-06",
            "object": "model",
            "created": 1722814719,
            "owned_by": "system"
        },
        {
            "id": "gpt-4o-realtime-preview",
            "object": "model",
            "created": 1727659998,
            "owned_by": "system"
        },
        {
            "id": "gpt-4o",
            "object": "model",
            "created": 1715367049,
            "owned_by": "system"
        },
        {
            "id": "dall-e-2",
            "object": "model",
            "created": 1698798177,
            "owned_by": "system"
        },
        {
            "id": "text-embedding-ada-002",
            "object": "model",
            "created": 1671217299,
            "owned_by": "openai-internal"
        },
        {
            "id": "gpt-4o-realtime-preview-2024-10-01",
            "object": "model",
            "created": 1727131766,
            "owned_by": "system"
        },
        {
            "id": "gpt-4-1106-preview",
            "object": "model",
            "created": 1698957206,
            "owned_by": "system"
        },
        {
            "id": "text-embedding-3-large",
            "object": "model",
            "created": 1705953180,
            "owned_by": "system"
        },
        {
            "id": "gpt-4o-mini",
            "object": "model",
            "created": 1721172741,
            "owned_by": "system"
        },
        {
            "id": "babbage-002",
            "object": "model",
            "created": 1692634615,
            "owned_by": "system"
        },
        {
            "id": "gpt-4o-2024-11-20",
            "object": "model",
            "created": 1731975040,
            "owned_by": "system"
        },
        {
            "id": "gpt-4-turbo-preview",
            "object": "model",
            "created": 1706037777,
            "owned_by": "system"
        },
        {
            "id": "o1-mini",
            "object": "model",
            "created": 1725649008,
            "owned_by": "system"
        },
        {
            "id": "davinci-002",
            "object": "model",
            "created": 1692634301,
            "owned_by": "system"
        },
        {
            "id": "o1-mini-2024-09-12",
            "object": "model",
            "created": 1725648979,
            "owned_by": "system"
        },
        {
            "id": "gpt-4-0125-preview",
            "object": "model",
            "created": 1706037612,
            "owned_by": "system"
        },
        {
            "id": "whisper-1",
            "object": "model",
            "created": 1677532384,
            "owned_by": "openai-internal"
        },
        {
            "id": "dall-e-3",
            "object": "model",
            "created": 1698785189,
            "owned_by": "system"
        },
        {
            "id": "gpt-4o-mini-2024-07-18",
            "object": "model",
            "created": 1721172717,
            "owned_by": "system"
        },
        {
            "id": "o1-preview",
            "object": "model",
            "created": 1725648897,
            "owned_by": "system"
        },
        {
            "id": "gpt-3.5-turbo-16k",
            "object": "model",
            "created": 1683758102,
            "owned_by": "openai-internal"
        },
        {
            "id": "o1-preview-2024-09-12",
            "object": "model",
            "created": 1725648865,
            "owned_by": "system"
        },
        {
            "id": "omni-moderation-latest",
            "object": "model",
            "created": 1731689265,
            "owned_by": "system"
        },
        {
            "id": "omni-moderation-2024-09-26",
            "object": "model",
            "created": 1732734466,
            "owned_by": "system"
        },
        {
            "id": "tts-1-hd-1106",
            "object": "model",
            "created": 1699053533,
            "owned_by": "system"
        },
        {
            "id": "gpt-4",
            "object": "model",
            "created": 1687882411,
            "owned_by": "openai"
        },
        {
            "id": "gpt-4-0613",
            "object": "model",
            "created": 1686588896,
            "owned_by": "openai"
        },
        {
            "id": "gpt-3.5-turbo",
            "object": "model",
            "created": 1677610602,
            "owned_by": "openai"
        },
        {
            "id": "gpt-3.5-turbo-0125",
            "object": "model",
            "created": 1706048358,
            "owned_by": "system"
        },
        {
            "id": "text-embedding-3-small",
            "object": "model",
            "created": 1705948997,
            "owned_by": "system"
        },
        {
            "id": "gpt-4-turbo",
            "object": "model",
            "created": 1712361441,
            "owned_by": "system"
        },
        {
            "id": "tts-1-hd",
            "object": "model",
            "created": 1699046015,
            "owned_by": "system"
        },
        {
            "id": "gpt-4-turbo-2024-04-09",
            "object": "model",
            "created": 1712601677,
            "owned_by": "system"
        },
        {
            "id": "gpt-3.5-turbo-1106",
            "object": "model",
            "created": 1698959748,
            "owned_by": "system"
        },
        {
            "id": "gpt-3.5-turbo-instruct",
            "object": "model",
            "created": 1692901427,
            "owned_by": "system"
        },
        {
            "id": "gpt-4o-audio-preview",
            "object": "model",
            "created": 1727460443,
            "owned_by": "system"
        },
        {
            "id": "gpt-4o-audio-preview-2024-10-01",
            "object": "model",
            "created": 1727389042,
            "owned_by": "system"
        },
        {
            "id": "tts-1",
            "object": "model",
            "created": 1681940951,
            "owned_by": "openai-internal"
        },
        {
            "id": "tts-1-1106",
            "object": "model",
            "created": 1699053241,
            "owned_by": "system"
        },
        {
            "id": "gpt-3.5-turbo-instruct-0914",
            "object": "model",
            "created": 1694122472,
            "owned_by": "system"
        },
        {
            "id": "chatgpt-4o-latest",
            "object": "model",
            "created": 1723515131,
            "owned_by": "system"
        },
        {
            "id": "gpt-4o-2024-05-13",
            "object": "model",
            "created": 1715368132,
            "owned_by": "system"
        }
    ]
}
```


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

![image](https://github.com/user-attachments/assets/d30b6480-995a-4fa4-9e51-3801beb54b34)

![image](https://github.com/user-attachments/assets/d85b4bf1-b9b1-4b4c-933c-1ce13be2c125)

![image](https://github.com/user-attachments/assets/0624481a-4c32-4ad5-b403-a0d97a9bd55c)

![image](https://github.com/user-attachments/assets/f9c9500b-b0c2-41a2-bff6-9dfc4b202c96)

![image](https://github.com/user-attachments/assets/6de88f49-1c9a-43aa-910d-ac8e382d8ba5)

![image](https://github.com/user-attachments/assets/f21e32b0-1086-472b-a3c5-db27bbb79855)


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

![image](https://github.com/user-attachments/assets/cf476d4f-8f54-429c-a982-54b6202f2a67)

![image](https://github.com/user-attachments/assets/eef18105-89f9-49d9-b472-53a8d2e2cda5)

![image](https://github.com/user-attachments/assets/579766f0-8106-4a38-8b43-b386d7c0a394)

![image](https://github.com/user-attachments/assets/51445c8a-41a4-49da-8832-0b8cb69f6cc3)


![image](https://github.com/user-attachments/assets/d2977bd4-bf48-43b1-9fb3-9f5cf4de7703)

![image](https://github.com/user-attachments/assets/7732c767-cd3f-4ea2-9edc-b1940ff332d7)

![image](https://github.com/user-attachments/assets/f71cf840-b248-4202-9d51-0b6f582b06d1)

![image](https://github.com/user-attachments/assets/3e258d84-c3d8-4982-99db-da0644509a9b)

![image](https://github.com/user-attachments/assets/8fc0a1ed-f198-47d1-b4d0-e10819f2043e)

![image](https://github.com/user-attachments/assets/0a356588-c371-4279-92d9-1e77ed7af0b6)


El listado 2-5 es un ejemplo de la respuesta JSON después de invocar el punto final de chat.

**Listado 2-5 El JSON response después de invocaar el endpoint Chat.**

![image](https://github.com/user-attachments/assets/099cce5c-f582-4a40-9560-6b7feee95be9)

### Espera, ¿cuántos tokens hay en mi Prompt(mensaje)?

En un momento dado, comenzarás a pensar en los mensajes que planeas enviar a ChatGPT y a pensar mucho en las limitaciones de tokens (y los costos) con respecto al modelo que deseas utilizar. En caso de que lo hayas olvidado, asegúrate de volver a consultar la Tabla 1-1 para obtener una lista de modelos y el precio de los tokens. Además, OpenAI creó un sitio web fácil de usar que te permite ver cuántos tokens hay en tu mensaje, como se muestra en la Figura 2-1 .

#### Contador de tokens ChatGPT

https://platform.openai.com/tokenizer

![image](https://github.com/user-attachments/assets/960d356c-f798-4a83-83a8-5ac2103851fe)

**Figura 2-1 El tokenizador ChatGPT puede brindarle un recuento rápido de los tokens en su mensaje**


### Creación de la próxima aplicación Java: `ChatGPTClient.java`

Ahora es el momento de crear nuestro propio ChatGPTClient. Vamos a empezar y a proporcionarle a ChatGPT la información que necesita a través de ChatGPT Playground.

![image](https://github.com/user-attachments/assets/1fcdf222-fa5a-422d-a8da-3dec6fc3ae04)

**Listado 2-6 La conversación inicial para crear `ChatGPTClient.java`**

```sh
System: You are a Java developer
User: Convert the following cURL command to Java. Make sure the URL and API keys to the API are variables. I want to use the Jackson library to create the JSON object in the request. Name the main class, ChatGPTClient, and create helper classes if necessary.
User:
curl https://api.openai.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -d '{
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
}'
```

La respuesta de ChatGPT fue un buen comienzo, pero no tenía todo exactamente como yo quería. Ahora bien, como no especifiqué exactamente cómo se debían haber realizado las llamadas HTTP, ChatGPT decidió utilizar la biblioteca Apache HTTPClient. Por lo tanto, agregué el siguiente mensaje de usuario (Listado 2-7 ).

![image](https://github.com/user-attachments/assets/c23ec256-5ea6-4c30-a75f-d509c4d6ca00)

**Listado 2-7 PROMPT: Cómo añadir información adicional a la conversación para crear `ChatGPTClient.java`**

El objetivo aquí es tener una conversación. No es práctico esperar que ChatGPT produzca exactamente lo que quieres en un solo mensaje. ¡Ni siquiera los desarrolladores hacen eso! Por lo tanto, siéntete libre de tener una conversación con ChatGPT y aclararle cosas que puede haber adivinado o asumido incorrectamente.

**El listado 2-8 muestra el resultado final para `ChatGPTClient.java`.**

![image](https://github.com/user-attachments/assets/84ac7e49-1683-4006-bcba-aa6209471c19)

```java
import com.fasterxml.jackson.core.JsonProcessingException;
import com.fasterxml.jackson.databind.ObjectMapper;
import com.fasterxml.jackson.annotation.JsonProperty;
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.OutputStream;
import java.net.HttpURLConnection;
import java.net.URL;
import java.util.ArrayList;
import java.util.List;
public class ChatGPTClient {
        public static void main(String[] args) {
        String openAIKey = "insert your API key here";
        String endpoint = "https://api.openai.com/v1/chat/completions";
        String model = "gpt-3.5-turbo";
        float temperature = 1.0f;
        int max_tokens = 256;
        float top_p = 1.0f;
        int frequency_penalty = 0;
        int presence_penalty = 0;
        List<Message> messages = new ArrayList<>();
        messages.add(new Message("system", "You are a product marketer."));
        messages.add(new Message("user", "Explain why Java is so widely used in the enterprise"));
        String jsonInput = null;
        try {
            ObjectMapper mapper = new ObjectMapper();
            Chat chat = new Chat(model, messages, temperature, max_tokens, top_p, frequency_penalty, presence_penalty);
            jsonInput = mapper.writeValueAsString(chat);
        } catch (JsonProcessingException e) {
            e.printStackTrace();
        }
        try {
            URL url = new URL(endpoint);
            HttpURLConnection connection = (HttpURLConnection) url.openConnection();
            connection.setRequestMethod("POST");
            connection.setRequestProperty("Content-Type", "application/json");
            connection.setRequestProperty("Authorization", "Bearer " + openAIKey);
            connection.setDoOutput(true);
            OutputStream outputStream = connection.getOutputStream();
            outputStream.write(jsonInput.getBytes());
            outputStream.flush();
            outputStream.close();
            int responseCode = connection.getResponseCode();
            if (responseCode == HttpURLConnection.HTTP_OK) {
                BufferedReader reader = new BufferedReader(new InputStreamReader(connection.getInputStream()));
                StringBuilder response = new StringBuilder();
                String line;
                while ((line = reader.readLine()) != null) {
                    response.append(line);
                }
                reader.close();
                // Print the response
                System.out.println(response.toString());
            } else {
                System.out.println("Error: " + responseCode);
            }
            connection.disconnect();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
    // Helper class to represent the Chat object
    static class Chat {
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
        public Chat(String model, List<Message> messages, float temperature, int max_tokens, float top_p, int frequency_penalty, int presence_penalty) {
            this.model = model;
            this.messages = messages;
            this.temperature = temperature;
            this.max_tokens = max_tokens;
            this.top_p = top_p;
            this.frequency_penalty = frequency_penalty;
            this.presence_penalty = presence_penalty;
        }
        // Getters and setters (optional, but can be useful if you need to modify the object later)
        }
    // Helper class to represent the Chat Message
    static class Message {
        @JsonProperty("role")
        private String role;
        @JsonProperty("content")
        private String content;
        public Message(String role, String content) {
            this.role = role;
            this.content = content;
        }
    }
}
```


**Listado 2-8 RESPONSE. `ChatGPTClient.java`**

Al examinar la lista de códigos anterior, verá que las llamadas HTTP se realizan utilizando API de Java puras y no utilizando ninguna biblioteca externa, tal como solicité en el mensaje. Sin embargo, tenga en cuenta que crear y analizar objetos JSON en Java puro puede ser una molestia, por lo que especifiqué personalmente que se debe utilizar la API de Jackson, lo que (como puede ver) se refleja en las declaraciones de importación y en el código en sí.

El código resultante incluye dos clases internas, Chat y Message , que se pueden separar fácilmente en archivos Java independientes. Puedo hacerlo manualmente o agregar un nuevo mensaje de "Usuario" a ChatGPT para solicitar que las clases internas se separen en archivos Java distintos.

Después de ejecutar `ChatGPTClient.java`, el Listado 2-9 tiene la respuesta.

![image](https://github.com/user-attachments/assets/299345f6-949b-4270-a52e-2f8d1ba81dc0)

```json
{
  "id": "chatcmpl-7xIRvjByGobmWH9Vo7OObHCSSwzgI",
  "object": "chat.completion",
  "created": 1694366627,
  "model": "gpt-3.5-turbo-0613",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "Java is widely used in the enterprise primarily due to its numerous benefits and features that make it a popular choice among large organizations. Here are some key reasons why Java is so widely adopted in the enterprise:\n\n1. Platform Independence: One of the biggest advantages of Java is its platform independence. Java programs can run on any operating system, making it highly adaptable across a wide range of devices and platforms. This makes it easier for enterprises to develop applications that can be deployed on different systems without any major modifications.\n\n2. Robustness and Stability: Java is known for its strong emphasis on reliability, stability, and error handling. It has a built-in memory management system that prevents memory leaks and ensures robust performance. This stability is highly valued in enterprise environments where systems need to run consistently without disruptions.\n\n3. Scalability: Java offers excellent scalability, making it suitable for large-scale enterprise applications. It provides robust support for multi-threading, allowing applications to handle a large number of concurrent users smoothly. Java's ability to handle high traffic loads and distribute processing across multiple servers makes it ideal for enterprise-level systems.\n\n4. Rich Standard Library and Frameworks: Java comes with a comprehensive standard library, offering a wide range of pre-built functions and classes that simplify development. Additionally, Java has a"
      },
      "finish_reason": "length"
    }
  ],
  "usage": {
    "prompt_tokens": 28,
    "completion_tokens": 256,
    "total_tokens": 284
  }
}
```

**Listado 2-9 9RESPONSE. Los resultados de llamar a `ChatGPTClient.java`**

¿Observaste en la lista anterior que la respuesta a mi solicitud se truncó? “Además, Java tiene un” no es una oración completa, pero como solicité que no se usaran más de 256 tokens en la respuesta, no superó esa limitación.

### Conclusión

Contrariamente a la creencia popular, ChatGPT no lee la mente. No tiene la capacidad de reemplazar a los desarrolladores y arquitectos porque es (¡ja!) artificialmente inteligente. Es muy útil para hacer una sola pregunta y recibir una respuesta inmediata y directa. Definitivamente se puede usar para convertir un mensaje (o solicitud) en lenguaje natural en código, pero definitivamente se necesita un desarrollador para tomar la decisión de si el código resultante se debe usar, refinar o descartar por completo.
