# 2. Usar ChatGPT como su programador en pareja de Java
Bruce Hopkins 1  
(1)
Beaverton, Oregón, Estados Unidos
 
Soy un gran admirador de algunas de las prácticas de XP (eXtreme Programming ), y especialmente de la programación en pareja. No importa qué tipo de programación en pareja prefieras, implica que dos ingenieros se sienten frente a la misma pantalla y resuelvan el mismo problema juntos. Uno de los mayores beneficios que obtienes es un par de ojos nuevos sobre un problema y, por supuesto, ahora tienes dos ingenieros que han "tocado" el código base en lugar de uno solo. A veces puedes hacer que un ingeniero escriba el código y el otro escriba las pruebas y los comentarios. No importa cómo lo mires, todo es bueno.

Ahora, las API REST de OpenAI para ChatGPT y sus otros modelos son oficialmente compatibles con Python, Typescript y, por supuesto, cURL (que es el estándar de facto para las API REST ).

Existen algunas API de Java creadas por desarrolladores externos, pero el mayor problema (en mi opinión) es que este espacio está cambiando rápidamente. OpenAI actualiza constantemente sus modelos y sus interfaces HTTP y, como resultado, agregan o eliminan características y funcionalidades con frecuencia. Si elige utilizar una API de Java de terceros para su proyecto, corre el riesgo de usar una API que esté desactualizada o que no esté sincronizada con la API REST de OpenAI.

Entonces, en este capítulo, vamos a usar ChatGPT como nuestro programador en pareja y simplemente trasladaremos las API REST oficiales de OpenAI directamente a Java. Cada vez que OpenAI realiza algún cambio en sus lenguajes e interfaces oficialmente compatibles, tenemos todo lo necesario para actualizar nuestra propia biblioteca al instante. ¡Hagámoslo!

Cómo crear su primera aplicación Java ChatGPT: ListModels.java
En realidad, aquí vamos a realizar dos tareas a la vez. Vamos a crear una aplicación básica en Java utilizando las API de OpenAI y, en el proceso, vamos a verificar que hayamos obtenido una clave API correctamente. Por lo tanto, no hace falta decir que, en caso de que aún no lo haya hecho, siga las instrucciones del Capítulo 1 para crear su cuenta de desarrollador de OpenAI y obtener su clave API. De ahora en adelante, todos los ejemplos de código de este libro requieren una clave API válida.

Punto final de los modelos de lista
Uno de los servicios más básicos (pero también esenciales) a los que podemos recurrir es el punto de conexión List Models . ¿Por qué?, te preguntarás. El punto de conexión List Models te permite obtener una lista de todos los modelos de IA que están actualmente disponibles para que los utilicen los desarrolladores a través de la API REST.

Creando la solicitud
En la Tabla 2-1 se enumeran todos los parámetros HTTP necesarios para llamar al punto final de Modelos de lista.
Tabla 2-1Los parámetros HTTP necesarios para llamar al punto final de los modelos de lista
Parámetro HTTP

Descripción

URL del punto final

https://api.openai.com/v1/models

Método

CONSEGUIR

Encabezamiento

Autorización: Portador $OPENAI_API_KEY

Manejo de la respuesta JSON
Después de invocar con éxito el punto final de Modelos de lista, el servicio proporcionará una respuesta JSON con la estructura que se muestra en la Tabla 2-2 .

Modelo (JSON)
Tabla 2-2La estructura del objeto JSON del modelo
Campo

Tipo

Descripción

objeto

Cadena

Esto siempre devuelve el literal "lista".

datos

Formación

Una lista de modelos de IA ofrecidos por OpenAI

  ↳ identificación

Cadena

El identificador único del modelo de IA, que es esencialmente el nombre completo del modelo.

  ↳ objeto

Cadena

Esto siempre devuelve el literal "modelo".

  ↳ creado

entero

La fecha de creación del modelo.

  ↳ propiedad de

Cadena

El nombre de la organización propietaria del modelo.

permiso

Formación

Esta es una matriz de metadatos para los permisos del modelo.

raíz

Cadena

Normalmente, se trata de una copia del campo data.id, que es el nombre del modelo.

padre

Cadena

Este es un campo actualmente sin uso

NotaDado que los objetos JSON pueden contener matrices (que pueden ser difíciles de representar en una tabla), utilizamos la notación “↳” para indicar los elementos de una matriz. Como puede ver en la tabla anterior, “id”, “object”, “created” y “owned_by” son todos elementos de la matriz “data” en la respuesta JSON.
Ahora que tenemos los detalles de la solicitud y la respuesta HTTP, podemos crear la aplicación ListModel.java usando el mensaje que se muestra en el Listado 2-1 .
Sistema : Eres un desarrollador de Java
Usuario : tome el siguiente comando cURL y conviértalo a Java. Nombre el archivo "ListModels.java"
Usuario : curl https://api.openai.com/v1/models \
  -H "Autorización: Portador $OPENAI_API_KEY"
Listado 2-1INSTRUCCIÓN. Uso de ChatGPT para crear la aplicación ListModels.java
Entonces, después de enviar el mensaje, ChatGPT le proporcionará una respuesta como se muestra en el Listado 2-2 .

importar java.io.BufferedReader;
importar java.io.InputStreamReader;
importar java.net.HttpURLConnection;
importar java.net.URL;
clase pública ListModels {
        public static void principal (cadena [] argumentos) {
        intentar {
            // Crear objeto URL para el punto final de la API
            URL URL = nueva URL ("https://api.openai.com/v1/models");
            // Crear objeto HttpURLConnection
            Conexión HttpURL conn = (ConexiónHttpURL) url.openConnection();
            // Establecer el método de solicitud
            conn.setRequestMethod("OBTENER");
            // Establecer encabezado de autorización
            conn.setRequestProperty("Autorización", "Portador $OPENAI_API_KEY");
            // Obtener código de respuesta
            int responseCode = conn.getResponseCode();
            // Si la solicitud fue exitosa (código de estado 200)
            si (código de respuesta == HttpURLConnection.HTTP_OK) {
                //Leer la respuesta de la API
                BufferedReader en = nuevo BufferedReader(nuevo InputStreamReader(conn.getInputStream()));
                Cadena de entrada Linea;
                Respuesta de StringBuilder = new StringBuilder();
                mientras ((inputLine = in.readLine()) != null) {
                respuesta.append(inputLine);
                }
                cercar();
                //Imprime la respuesta
                Sistema.out.println(respuesta.toString());
            } demás {
                System.out.println("La solicitud falló. Código de respuesta: " + responseCode);
            }
            //Cerrar la conexión
            conn.desconectar();
        } captura (Excepción e) {
            es.printStackTrace();
        }
        }
}
Listado 2-2RESPUESTA. ListModels.java
¡Fantástico! Ahora todo lo que tienes que hacer es reemplazar “$OPENAI_API_KEY” con el valor de tu clave API actual.

Después de ejecutar esta clase, obtendrá un archivo JSON que contiene todos los modelos ofrecidos por la API de OpenAI, como se muestra en el Listado 2-3 .

{
  "objeto": "lista",
  "datos": [
    {
      "id": "busqueda-de-texto-babbage-doc-001",
      "objeto": "modelo",
      "creado": 1651172509,
      "propiedad_de": "openai-dev"
    },
    {
      "id": "gpt-4",
      "objeto": "modelo",
      "creado": 1687882411,
      "propiedad_de": "openai"
    },
    {
      "id": "gpt-3.5-turbo-16k",
      "objeto": "modelo",
      "creado": 1683758102,
      "propiedad_de": "openai-interno"
    },
    {
      "id": "consulta de búsqueda de curie",
      "objeto": "modelo",
      "creado": 1651172509,
      "propiedad_de": "openai-dev"
    },
    {
      "id": "texto-davinci-003",
      "objeto": "modelo",
      "creado": 1669599635,
      "propiedad_de": "openai-interno"
    },
    {
      "id": "búsqueda de texto-consulta-babbage-001",
      "objeto": "modelo",
      "creado": 1651172509,
      "propiedad_de": "openai-dev"
    },
    {
      "id": "babbage",
      "objeto": "modelo",
      "creado": 1649358449,
      "propiedad_de": "openai"
    },
...
Listado 2-3RESPUESTA. La respuesta JSON parcial después de ejecutar ListModels.java
Los listados 2 y 3 son una lista parcial debido a la gran cantidad de modelos disponibles para que los utilicen los desarrolladores. Sin embargo, la buena noticia es que la respuesta completa se proporciona como una tabla en el Apéndice.

Ahora que podemos obtener mediante programación una lista de modelos disponibles para usar, es momento de enviar mensajes a ChatGPT mediante Java. Esto se logra mediante el punto final de chat.

Punto final de chat
El punto final de chat (anteriormente llamado “Finalización de chat”) es un servicio REST que es básicamente una representación 1 a 1 de lo que puede hacer en el área de juegos de chat; por lo tanto,Este servicio debería resultarle algo natural.

Creando la solicitud
En la Tabla 2-3 se enumeran todos los parámetros HTTP necesarios para llamar al punto final de chat.
Tabla 2-3Los parámetros HTTP para el punto final del chat
Parámetro HTTP

Descripción

URL del punto final

https://api.openai.com/v1/chat/completions

Método

CORREO

Encabezamiento

Autorización: Portador $OPENAI_API_KEY

Tipo de contenido

aplicación/json

La Tabla 2-4 describe el formato del objeto JSON necesario para el cuerpo de la solicitud del punto final de chat. Después de un vistazo rápido, puede ver que solo se requieren algunos campos para invocar el servicio correctamente.

Chat (JSON)
Tabla 2-4La estructura del objeto JSON de Chat
Campo

Tipo

¿Requerido?

Descripción

modelo

Cadena

Requerido

El ID del modelo que desea utilizar para completar el chat. Los modelos compatibles incluyen

•  gpt-4

•  gpt-4-0613

•  gpt-4-32k

•  gpt-4-32k-0613

•  gpt-3.5-turbo

•  gpt-3.5-turbo-0613

•  gpt-3.5-turbo-16k

•  gpt-3.5-turbo-16k-0613

mensajes

Formación

Requerido

Un conjunto de mensajes que forman parte de la conversación en curso.

Cada mensaje de la matriz tiene dos propiedades: "rol" y "contenido".

  ↳ papel

Cadena

Requerido

Especifica la función del mensaje, que puede ser cualquiera de las siguientes:

•  "sistema"

•  "usuario"

•  "asistente"

•  "herramienta"

  ↳ contenido

Cadena

Requerido

Contiene el texto del mensaje para el rol especificado.

herramientas

Formación

Opcional

Esto le permite especificar una lista de herramientas que el modelo puede llamar. Actualmente, el único tipo de herramienta compatible es una función.

Este parámetro le permite definir un conjunto de funciones para las que el modelo puede generar entradas JSON.

  ↳ tipo

Cadena

Requerido

Este es un tipo de herramienta, que puede ser cualquiera de las siguientes:

•  "función"

Función   ↳

Formación

Opcional

Una matriz de funciones que el modelo puede usar para llamar en la finalización del chat.

  ↳↳ nombre

Cadena

Requerido

El nombre de la función que se llamará. Los nombres válidos deben ser az, AZ, 0-9 o contener guiones bajos y guiones.

La longitud máxima es de 64 caracteres.

  ↳↳ descripción

Cadena

Opcional

Una descripción de lo que hace la función. Esto ayuda al modelo a decidir si llamar a la función en la finalización del chat.

  ↳↳ parámetros

Objeto JSON

Requerido

Los parámetros que acepta la función en el formato de un objeto de esquema JSON.

elección de herramienta

Objeto de cadena o JSON

por defecto:

"ninguno" cuando no se incluyen funciones en la solicitud

"auto" cuando se incluyen funciones en la solicitud

Opcional

Esto le permite determinar qué función, si hay alguna, debe invocar el modelo.

Cuando se establece en "ninguno", el modelo se abstendrá de llamar a ninguna función y solo generará una respuesta de mensaje.

Cuando se establece en "automático", el modelo tiene la flexibilidad de elegir entre generar una respuesta de mensaje o invocar una función basada en su proceso interno de toma de decisiones.

temperatura

Número o nulo

predeterminado: 1

Opcional

Los valores válidos oscilan entre 0 y 2.

Controla la aleatoriedad de la salida del modelo.

La mejor práctica es ajustar top_p o la temperatura, pero no ambos.

arriba_p

Número o valor nulo predeterminado: 1

Opcional

Los valores válidos oscilan entre 0 y 1. Indica si se deben considerar pocas posibilidades (0) o todas las posibilidades (1).

La mejor práctica es ajustar top_p o la temperatura, pero no ambos.

norte

entero o nulo

predeterminado: 1

Opcional

Especifica cuántas opciones de finalización de chat debe generar el modelo para cada mensaje de entrada.

arroyo

Booleano o nulo

predeterminado: falso

Opcional

Si "stream" se establece en "true", las actualizaciones parciales de mensajes se enviarán como eventos enviados por el servidor.

Esto significa que los tokens se enviarán como eventos de solo datos a medida que estén disponibles, y la transmisión finalizará con un mensaje "datos: [DONE]".

detener

Cadena / matriz / nulo

predeterminado: nulo

Opcional

Puede proporcionar hasta 4 secuencias en las que la API debería dejar de generar más tokens.

Esto puede ser útil para controlar la longitud o el contenido de las respuestas.

máximo_tokens

entero o nulo

predeterminado: inf

Opcional

Este parámetro establece la cantidad máxima de tokens que puede tener la finalización de chat generada.

formato_respuesta

Objeto JSON

Opcional

Tienes dos opciones:

{ "type": "json_object" } para una respuesta de objeto JSON

o

{ "type": "text" } para una respuesta de texto

semilla

entero o nulo

Opcional

Al especificar una semilla, el sistema intentará generar resultados repetibles.

En teoría, esto significa que si realiza solicitudes repetidas con la misma semilla y parámetros, debe esperar recibir el mismo resultado.

Para obtener el valor de semilla que se colocará en la solicitud posterior, copie el system_fingerprint de su última respuesta.

penalización por presencia

Número o nulo

predeterminado: 0

Opcional

Un número entre -2,0 y 2,0.

Los valores positivos penalizan los nuevos tokens en función de si aparecen en el historial de conversaciones, lo que anima al modelo a hablar sobre nuevos temas.

penalización de frecuencia

Número o nulo

valores predeterminados: 0

Opcional

Un número entre -2,0 y 2,0.

Los valores positivos penalizan los tokens en función de su frecuencia existente en el historial de conversación, lo que reduce la probabilidad de repetir las mismas líneas textualmente.

sesgo logit

Mapa JSON

predeterminado: nulo

Opcional

Le permite modificar la probabilidad de que aparezcan tokens específicos en la finalización.

Proporciona un objeto JSON que asigna tokens (especificados por su ID de token en el tokenizador) a valores de sesgo asociados de -100 a 100.

Este sesgo se agrega a los logits del modelo antes del muestreo.

usuario

Cadena

Opcional

Se trata de una identificación única que puedes generar de forma opcional para representar a tu usuario final. Esto ayudará a OpenAI a monitorear y detectar abusos.

NotaEn este libro, trabajaremos con el parámetro "stream" configurado en su configuración predeterminada, que es falsa. Esto significa que recibiremos todos los resultados de ChatGPT a la vez como una única respuesta HTTP.
Sin embargo, hay casos en los que desearía que esta configuración se establezca en verdadero. Digamos que está creando, por ejemplo, un bot de chat interactivo habilitado por voz. Digamos también que está interesado en convertir el texto de ChatGPT a audio para que sus usuarios puedan escuchar una respuesta audible. En tal caso, definitivamente querrá establecer el parámetro "stream" en verdadero. ¿Por qué es así? Cuando la respuesta se transmite de vuelta a su aplicación Java, tiene la oportunidad en ese momento de convertir el fragmento de texto a audio. Esto le permitirá trabajar en paralelo con la conversión de fragmentos de texto a audio mientras recibe más texto simultáneamente. Esto hará que la respuesta parezca más natural para el usuario final y ayudará a que la conversación se sienta como una conversación real .

El listado 2-4 es un ejemplo de cómo se vería el objeto JSON para invocar correctamente el punto final de chat.
{
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
}
Listado 2-4Ejemplo del objeto JSON Chat
Manejo de la respuesta
Después de invocar correctamente el punto final de chat, la API responderá con un objeto de finalización de chat o con un flujo de fragmentos de finalización si la transmisión está habilitada. A continuación, se muestra un desglose del objeto de finalización de chat.

Finalización del chat (JSON)
Tabla 2-5La estructura del objeto JSON de la competencia de chat
Campo

Tipo

Descripción

identificación

Cadena

El identificador único para la finalización del chat.

objeto

Cadena

Esto siempre devuelve el literal "chat.completion".

huella digital del sistema

Cadena

Utilice este parámetro como "semilla" en una solicitud posterior si desea obtener resultados reproducibles de una conversación anterior.

creado

entero

La marca de tiempo de la finalización del chat.

modelo

Cadena

El modelo utilizado para completar el chat.

opciones

Formación

Una lista de opciones de finalización de chat disponibles.

Puede obtener más de una opción de mensajes si especifica la cantidad de respuestas deseadas con el parámetro "n" en la solicitud JSON de Chat. Consulte la Tabla 2-4 .

  ↳ índice

entero

El índice de la elección en la lista.

  ↳ mensaje

Formación

Un mensaje de finalización de chat generado por el modelo.

  ↳ motivo_de_finalización

Cadena

Cada respuesta incluirá un finish_reason. Los valores posibles para finish_reason son

stop: La API devolvió un mensaje completo o un mensaje finalizado por una de las secuencias de detención proporcionadas a través del parámetro de detención.

longitud: La salida del modelo estaba incompleta debido al parámetro max_tokens en la solicitud o al límite de token del modelo en sí.

tool_call: El modelo llama a una herramienta, como una función.

content_filter: La respuesta se terminó debido a una violación de los filtros de contenido.

null: La respuesta de la API aún está en proceso o incompleta.

uso

Formación

Estadísticas de uso de la solicitud de finalización, incluida la cantidad de tokens en la solicitud, la finalización y la solicitud total.

  ↳ tokens_de_aviso

entero

La cantidad de tokens utilizados en el mensaje.

  ↳ tokens de finalización

entero

La cantidad de tokens utilizados en la respuesta.

  ↳ total_tokens

entero

La suma total de todos los tokens en la solicitud y la respuesta.

El listado 2-5 es un ejemplo de la respuesta JSON después de invocar el punto final de chat.

{
  "identificación": "chatcmpl-7wUOFQ3S34scDLmrLdWTTqvHmXztQ",
  "objeto": "chat.completado",
  "creado": 1694174199,
  "modelo": "gpt-3.5-turbo-0613",
  "opciones": [
    {
      "índice": 0,
      "mensaje": {
        "rol": "asistente",
        "content": "Java se utiliza ampliamente en las empresas porque es independiente de la plataforma, lo que permite que las aplicaciones se ejecuten en cualquier sistema. Además, Java tiene un ecosistema grande y maduro con una amplia gama de bibliotecas, marcos y herramientas, lo que facilita a los desarrolladores la creación de aplicaciones empresariales sólidas y escalables".
      },
      "finish_reason": "detenerse"
    }
  ],
  "uso": {
    "tokens_de_aviso": 32,
    "tokens_de_finalización": 55,
    "total_tokens": 87
  }
}
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
