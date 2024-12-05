# Chapter 1:​ Introducing ChatGPT for Java Developers

* Who Is This Book For?​
* Chapter Overview
* Download the Code Now!
* So, What Exactly Is ChatGPT and Why Do I Need to Use the OpenAI APIs?​
* Regex vs.​ ChatGPT:​ Fight!
* Analysis Question #1:​ Who Didn’t Get Any Ice Cream and Why?​
* Analysis Question #2:​ Which Kid Was Probably Left Sad?​
* Let’s Unlearn Some Words in Order to Learn More About the ChatGPT API
* Models.​ Models?​ Models!!!
* When We Talk About Tokens, Think About the StringTokenizer and Not Access Tokens
* Temperature Is All About Creativity
* Getting Started with the OpenAI Playground
* 1.​ System
* 2.​ User
* 3.​ Assistant (Optional)
* 4.​ Add Message (Optional)
* 5.​ View Code (Optional)
* 6.​ Model (Optional)
* 7.​ Temperature (Optional)
* 8.​ Maximum Length (Optional)
* Try It Now! Experimenting with the “System” Role
* Conclusion

## ¿Para quién es este libro?

En primer lugar, este libro está dirigido a desarrolladores de Java que no tienen formación ni experiencia en inteligencia artificial, procesamiento de lenguaje natural, aprendizaje automático o aprendizaje profundo. Es posible que hayas oído hablar del término "modelo de lenguaje", pero supongo que NO es un término que uses todos los días.

En segundo lugar, es posible que esté familiarizado con (o haya probado) ChatGPT, pero no comprende bien cómo funciona todo "debajo del capó" y no está seguro de cómo comenzar para usar Java y ChatGPT programáticamente juntos para "habilitar IA" a sus propias aplicaciones y servicios.

Nota: Aunque ChatGPT es un nombre muy conocido, OpenAI, la empresa que lo respalda, carece de un amplio reconocimiento y no es tan conocida. Por lo tanto, aunque este libro trata sobre cómo usar ChatGPT de manera programática dentro de sus aplicaciones Java, las API que usaremos son oficialmente las API REST de OpenAI. Por lo tanto, usaremos los términos "API de ChatGPT" y "API de OpenAI" como sinónimos.

## Resumen del capítulo

En este capítulo, vamos a profundizar en el tema y a explicar algunos términos con los que quizás no estés familiarizado, para luego pasar directamente a Playground de ChatGPT. Playground es, en esencia, una interfaz web para desarrolladores que se basa en la API REST de ChatGPT. Por lo tanto, una vez que te familiarices con Playground, las llamadas y respuestas de la API de ChatGPT te resultarán algo natural.

### ¡Descarga el código ahora!

![image](https://github.com/user-attachments/assets/6244bc49-8506-4352-9335-2b795f2fbcbd)

Este libro está repleto de ejemplos y códigos de ejemplo, así que ¿por qué molestarse en escribir todo usted mismo? A continuación se muestra la URL del repositorio de GitHub para acceder al código fuente.

https://github.com/Apress/ChatGPT-for-Java

## Entonces, ¿qué es exactamente ChatGPT y por qué necesito utilizar las API de OpenAI?

En términos simples, ChatGPT es un grupo de **modelos de lenguaje** (que son el resultado del entrenamiento de algoritmos de aprendizaje profundo) desarrollados por OpenAI que son capaces de generar respuestas de texto similares a las humanas en función de indicaciones(**prompts**) dadas. Entonces, ¿qué es un **prompt**? Un **prompt**-indicación es simplemente el texto de entrada que le das a ChatGPT. Entonces, comencemos dándole a ChatGPT una indicación para preguntarle qué tan familiarizado está con los patrones de diseño de Java (Listado 1-1 ).

```sh
Describe 3 commonly used design patterns used by Java developers and why those patterns are important
Describe tres patrones de diseño comúnmente utilizados por los desarrolladores de Java y por qué esos patrones son importantes.
```

**Listado 1-1 PROMPT. Un mensaje sencillo con ChatGPT sobre patrones de diseño de Java**

Si ha tenido la oportunidad de trabajar en una empresa que utiliza Java de manera profesional, es probable que haya recibido una pregunta muy similar a la anterior en una entrevista. La lista 1-2 es la respuesta de ChatGPT .

```sh
Certainly! Design patterns are reusable solutions to common problems that arise in software design. They are best practices that experienced developers have discovered and refined over time. Java developers frequently utilize design patterns due to the language's object-oriented nature. Here are three commonly used design patterns in Java:
1. Singleton Pattern:
   - Purpose: This pattern ensures that a class has only one instance and provides a global point of access to that instance. It's particularly useful when you want to control access to shared resources, such as configuration managers or connection pools.
   - Importance: The Singleton pattern is important because it provides a controlled mechanism to prevent creating multiple instances of a class, which can save memory and synchronize access to resources. Moreover, it ensures that operations using the singleton are using the same instance and data, which is critical in scenarios where consistent state or coordinated actions are required.
2. Observer Pattern:
   - Purpose: This pattern defines a one-to-many dependency between objects. When one object (known as the subject or observable) changes its state, all of its dependents (observers) are notified and updated automatically. It's the underlying principle behind the Model-View-Controller (MVC) architecture, where the model is the subject and the views are observers.
   - Importance: The Observer pattern is vital for building systems that are modular and decoupled. Changes in one part of the system don't directly affect others, allowing for easier maintenance and scalability. This pattern also makes it easier to add new observers without modifying existing code, enhancing the system's extensibility.
3. Factory Pattern:
   - Purpose: The Factory pattern provides an interface for creating instances of a class, but it's up to the derived subclasses to implement the method and determine which class to instantiate. It promotes the loose coupling by eliminating the need to bind application-specific classes into the code. Instead, the code interacts only with the resulting interface or abstract class, so the system can evolve without altering the calling code.
   - Importance: Using the Factory pattern, a system can be more flexible and scalable. If there's a need to introduce a new product or modify an existing one, it can be done without disturbing the existing code. It encapsulates the object creation process and separates it from the main logic of the program, promoting the Single Responsibility Principle. This ensures that a class is only responsible for one reason to change.
All these patterns, and many more, provide a vocabulary for developers, making it easier to communicate complex software designs and concepts. They embody solutions to recurring problems and can significantly speed up the development process, reduce errors, and improve code quality.

¡Por supuesto! Los patrones de diseño son soluciones reutilizables para problemas comunes que surgen en el diseño de software. Son prácticas recomendadas que los desarrolladores experimentados han descubierto y perfeccionado con el tiempo. Los desarrolladores de Java utilizan con frecuencia patrones de diseño debido a la naturaleza orientada a objetos del lenguaje. A continuación, se muestran tres patrones de diseño de uso común en Java:
1. Patrón Singleton:
   - Propósito: Este patrón garantiza que una clase tenga solo una instancia y proporciona un punto de acceso global a esa instancia. Es particularmente útil cuando se desea controlar el acceso a recursos compartidos, como administradores de configuración o grupos de conexiones.
   - Importancia: El patrón Singleton es importante porque proporciona un mecanismo controlado para evitar la creación de múltiples instancias de una clase, lo que puede ahorrar memoria y sincronizar el acceso a los recursos. Además, garantiza que las operaciones que utilizan el patrón Singleton utilicen la misma instancia y los mismos datos, lo que es fundamental en escenarios en los que se requiere un estado coherente o acciones coordinadas.
2. Patrón del observador:
   - Propósito: Este patrón define una dependencia de uno a muchos entre objetos. Cuando un objeto (conocido como sujeto u observable) cambia su estado, todos sus dependientes (observadores) reciben una notificación y se actualizan automáticamente. Es el principio subyacente detrás de la arquitectura Modelo-Vista-Controlador (MVC), donde el modelo es el sujeto y las vistas son los observadores.
   - Importancia: El patrón Observer es vital para construir sistemas modulares y desacoplados. Los cambios en una parte del sistema no afectan directamente a las demás, lo que permite un mantenimiento y una escalabilidad más sencillos. Este patrón también facilita la incorporación de nuevos observadores sin modificar el código existente, lo que mejora la extensibilidad del sistema.
3. Patrón de fábrica:
   - Propósito: El patrón Factory proporciona una interfaz para crear instancias de una clase, pero las subclases derivadas son las que implementan el método y determinan qué clase instanciar. Promueve el acoplamiento flexible al eliminar la necesidad de vincular clases específicas de la aplicación al código. En cambio, el código interactúa solo con la interfaz resultante o la clase abstracta, por lo que el sistema puede evolucionar sin alterar el código de llamada.
   - Importancia: Al utilizar el patrón Factory, un sistema puede ser más flexible y escalable. Si es necesario introducir un nuevo producto o modificar uno existente, se puede hacer sin alterar el código existente. Encapsula el proceso de creación de objetos y lo separa de la lógica principal del programa, promoviendo el principio de responsabilidad única. Esto garantiza que una clase solo sea responsable de un motivo de cambio.
Todos estos patrones, y muchos más, proporcionan un vocabulario a los desarrolladores, lo que facilita la comunicación de conceptos y diseños de software complejos. Incorporan soluciones a problemas recurrentes y pueden acelerar significativamente el proceso de desarrollo, reducir errores y mejorar la calidad del código.
```

**Listado 1-2 2 RESPONSE. Respuesta de ChatGPT a la solicitud del listado 1-1

Respuestas del 04/12/2024:

![image](https://github.com/user-attachments/assets/1eb9c4aa-2c21-47b9-bb0f-94803284a595)


No está mal, ¿no? ChatGPT no solo pudo proporcionar una lista de patrones de diseño comunes utilizados por los desarrolladores de Java, sino que también explicó razones válidas de por qué son importantes, todo en lenguaje natural.

Entonces, al final del día, ¿qué significa esto para los desarrolladores de Java? Bueno, en realidad es algo muy importante. Esto se debe a que los desarrolladores ahora pueden crear aplicaciones que pueden tener algún tipo de "comprensión" del texto en lenguaje natural. Antes de la llegada de herramientas de IA como ChatGPT, los desarrolladores normalmente tenían que crear expresiones regulares (también llamadas "regex") para realizar una coincidencia rudimentaria de caracteres y patrones de cadenas dentro de un cuerpo de texto. Sin embargo, la coincidencia de patrones y la comprensión del lenguaje natural son dos cosas totalmente diferentes.

## Regex vs. ChatGPT: ¡Pelea!

**Nota**: Si ya sabe que una expresión regular no puede realizar comprensión del lenguaje natural ni análisis de sentimientos, puede omitir esta sección.

Estoy completamente convencido de que todos los programadores, en algún momento de su vida, han conocido a alguien que resulta ser un experto en la escritura de expresiones regulares. Las expresiones regulares son geniales porque sirven para analizar grandes cantidades de texto con el fin de encontrar patrones dentro del texto mediante programación.

Sin embargo, una de las mayores desventajas de las expresiones regulares es que una vez escritas, son extremadamente difíciles de leer (en mi opinión, incluso para el desarrollador que las escribió originalmente).

Entonces, veamos cómo se comporta regex frente a ChatGPT, que tiene capacidades de procesamiento de lenguaje natural (NLP) y comprensión del lenguaje natural (NLU) .

El listado 1-3 es la historia de una situación triste y poco práctica. Sin embargo, pone de manifiesto que, si bien las expresiones regulares se pueden utilizar para buscar palabras y frases dentro de un cuerpo de texto, no se pueden utilizar para proporcionar ningún tipo de NLU.

```sh
In the city of Buttersville,USA on Milkmaid street, there’s a group of three friends: Marion Yogurt, Janelle de Queso, and Steve Cheeseworth III. On a hot summer’s day, they heard the music from an ice cream truck, and decided to buy something to eat.
Marion likes strawberries, Janelle prefers chocolate, and Steve is lactose intolerant. That day, only two kids ate ice cream, and one of them bought a bottle of room-temperature water. The ice cream truck was fully stocked with the typical flavors of ice cream.

En la ciudad de Buttersville, Estados Unidos, en la calle Milkmaid, hay un grupo de tres amigos: Marion Yogurt, Janelle de Queso y Steve Cheeseworth III. Un caluroso día de verano, oyeron la música de un camión de helados y decidieron comprar algo para comer.
A Marion le gustan las fresas, a Janelle el chocolate y a Steve no le gusta la lactosa. Ese día, solo dos niños comieron helado y uno de ellos compró una botella de agua a temperatura ambiente. El camión de helados estaba repleto de los sabores típicos de helado.
```

**Listado 1-3 Sadstory.txt - Una historia triste sobre un niño que no comía helado**

### Pregunta de análisis n.° 1: ¿Quién no recibió helado y por qué?

Ahora analicemos esto un poco y hagamos algunas preguntas entre nosotros. En primer lugar, ¿quién no compró helado y por qué? La respuesta obvia es que Steve no compró helado debido a su intolerancia a la lactosa. Sin embargo, dado que la historia no dice directamente que Steve no compró helado, no hay forma de que una expresión regular coincida con un patrón de texto en la historia.

La expresión regular podría buscar palabras clave como “no tenía”, “no había helado” o los nombres de los niños. Sin embargo, solo podría proporcionar una respuesta basada en la presencia de estos patrones. Por ejemplo, si la expresión regular coincide con el patrón “no tenía” o “no había helado” con el nombre de Steve, podría mostrarle el resultado del patrón de texto. Sin embargo, ciertamente no podría explicar por qué Steve fue el que no comió helado ni proporcionar ningún razonamiento específico del contexto.

Ahora, proporcionemos la misma historia a ChatGPT y hagamos la pregunta: "¿Quién no recibió helado?". El Listado 1-4 toma nuestra pregunta y la historia anterior y las reúne como un mensaje.

```sh
Using the information in the following story, who didn't get any ice cream and why?
###
In the city of Buttersville,USA on Milkmaid street, there’s a group of three friends: Marion Yogurt, Janelle de Queso, and Steve Cheeseworth III. On a hot summer’s day, they heard the music from an ice cream truck, and decided to buy something to eat.
Marion likes strawberries, Janelle prefers chocolate, and Steve is lactose intolerant. That day, only two kids ate ice cream, and one of them bought a bottle of room-temperature water. The ice cream truck was fully stocked with the typical flavors of ice cream.

Utilizando la información de la siguiente historia, ¿quién no recibió helado y por qué?
###
En la ciudad de Buttersville, Estados Unidos, en la calle Milkmaid, hay un grupo de tres amigos: Marion Yogurt, Janelle de Queso y Steve Cheeseworth III. Un caluroso día de verano, oyeron la música de un camión de helados y decidieron comprar algo para comer.
A Marion le gustan las fresas, a Janelle el chocolate y a Steve no le gusta la lactosa. Ese día, solo dos niños comieron helado y uno de ellos compró una botella de agua a temperatura ambiente. El camión de helados estaba repleto de los sabores típicos de helado.
```

**Listado 1-4 PROMPT. La triste historia plasmada en un mensaje**

Observe que es una buena práctica proporcionar algún tipo de separación, en este caso, “###”, al crear un mensaje (como el anterior) en el que se tienen instrucciones y datos juntos. Más adelante, cuando comencemos a usar Playground o Java para invocar programáticamente la API ChatGPT, verá que hay una forma mucho mejor de proporcionar esa separación.

Entonces, después de enviar el mensaje, ChatGPT le proporcionará una respuesta como se muestra en el Listado 1-5.

```sh
Based on the given information, Steve is lactose intolerant and therefore cannot eat ice cream. Therefore, Steve is the one who didn't get any ice cream.

Según la información proporcionada, Steve es intolerante a la lactosa y, por lo tanto, no puede comer helado. Por lo tanto, Steve es el que no tomó ningún helado.
```

**Listado 1-5 5RESPONSE. Respuesta de ChatGPT a la pregunta de análisis n.° 1**

![image](https://github.com/user-attachments/assets/70803d48-ff50-4a0b-a36d-bf9b58a8f08e)

![image](https://github.com/user-attachments/assets/b9780856-1673-4ec3-a8c8-8a40aadf3451)

Como puede ver, ChatGPT puede utilizar NLP y NLU y, por lo tanto, puede comprender (de manera artificialmente inteligente, claro está) el contexto del escenario. Puede interpretar las relaciones entre los niños, sus preferencias y la intolerancia a la lactosa de Steve. Es capaz de entender que los apellidos de los niños, el nombre de la calle y el nombre de la ciudad son nombres de productos lácteos, pero obviamente son irrelevantes para la pregunta en cuestión.

### Pregunta de análisis n.° 2: ¿Qué niño probablemente quedó triste?

Ahora, para demostrar aún más el punto de que una expresión regular no puede proporcionar ningún tipo de procesamiento del lenguaje natural (PLN) o lenguaje natural del lenguaje (NLU), ahora usemos un nuevo término llamado análisis de sentimientos . Por lo tanto, después de que el camión de helados se fue, ¿qué niño se quedó triste?

Dado que la historia no menciona ninguno de los sentimientos o emociones de los niños, no existe ningún patrón de texto que permita que cualquier expresión regular devuelva una coincidencia.

Sin embargo, si plantea la misma pregunta a ChatGPT, devolverá una respuesta como la que se muestra en el Listado 1-6.

```sh
Since Steve is lactose intolerant and cannot eat ice cream, he would be the kid left sad because he couldn't enjoy the ice cream like Marion and Janelle.

Como Steve es intolerante a la lactosa y no puede comer helado, él sería el niño que quedaría triste porque no podría disfrutar del helado como Marion y Janelle.
```

**Listado 1-6 RESPONSE. Respuesta de ChatGPT a la pregunta de análisis n.° 2**

![image](https://github.com/user-attachments/assets/77893cdc-9ca1-47ba-a82f-2900334f8e7d)

![image](https://github.com/user-attachments/assets/a2c56e35-5772-4440-9ccd-c3f949ad1c34)


Por lo tanto, ChatGPT es capaz de comprender el escenario, razonar la información y proporcionar una respuesta correcta junto con una explicación para esa respuesta.

## Desaprenderemos algunas palabras para aprender más sobre la API ChatGPT

En primer lugar, antes de comenzar a trabajar con las API de ChatGPT y OpenAI, hay algunas palabras y términos con los que debe familiarizarse; de ​​lo contrario, las cosas no tendrán mucho sentido. Por lo tanto, asegurémonos de que todos tenemos clara la definición de modelos, indicaciones, tokens y temperatura al usar ChatGPT de forma programática.

### Modelos. ¿Modelos? ¡¡¡Modelos!!!

Como desarrollador de Java, cuando escuchas el término "modelo", es posible que pienses inmediatamente en la programación orientada a objetos y en la representación de entidades del mundo real en tu clase Java, ¿verdad? Por ejemplo, piensa en el término "modelo de objetos". Además, si alguna vez has trabajado con algún tipo de base de datos, entonces el término "modelo" TAMBIÉN puede evocar en tu mente la idea de la representación de datos y sus relaciones en tu base de datos. Por ejemplo, piensa en el término "modelo de datos".

Sin embargo, al trabajar con las API de ChatGPT (y con la inteligencia artificial en general), es necesario olvidarse de ambas definiciones, porque no son aplicables. **En el ámbito de la inteligencia artificial, un *"modelo"* es una red neuronal entrenada previamente**.

Recuerde que, como mencioné anteriormente, no necesitará un doctorado en aprendizaje automático para leer este libro. Entonces, ¿qué es una red neuronal? En términos simples, ***una red neuronal es un componente fundamental de los sistemas de inteligencia artificial***, porque están diseñados para simular la forma en que funciona el cerebro humano mediante el uso de capas interconectadas de neuronas artificiales para procesar y analizar datos. Estas redes se pueden entrenar con grandes cantidades de datos para aprender patrones, relaciones y hacer predicciones.

![image](https://github.com/user-attachments/assets/f376dde0-e1eb-46c3-a8c0-c5fef031bd30)

**Figura 1-1 Un modelo de IA se entrena con grandes cantidades de datos**

En el contexto de la IA, ***un “modelo preentrenado” se refiere a una red neuronal que ha sido entrenada en una tarea o conjunto de datos específicos antes de estar disponible para su uso por parte de los desarrolladores***. Este proceso de entrenamiento implica exponer el modelo a grandes cantidades de datos etiquetados y categorizados (también llamados “anotados”) y ajustar sus parámetros internos para optimizar su rendimiento en la tarea determinada.

Veamos algunos de los modelos proporcionados por OpenAI para que los desarrolladores los utilicen para habilitar IA en sus aplicaciones.


### GPT-4

   GPT-4 es la última generación del conjunto de modelos GPT de OpenAI. **GPT significa Generative Pre-trained Transformer (Transformador generativo preentrenado)** y estos modelos han sido entrenados para comprender el lenguaje natural, así como varios lenguajes de programación. Los modelos GPT-4 toman texto e imágenes como entradas como indicaciones y proporcionan texto como salida.

   Algunos de los modelos GPT-4 disponibles son

   * **gpt-4**
   * **gpt-4-32k**
   * **gpt-4-visión**

### GPT-3.5

   GPT-3.x es la generación anterior del conjunto de modelos GPT de OpenAI. El ChatGPT original lanzado al público en noviembre de 2022 utilizaba GPT 3.

   Algunos de los modelos GPT-3 disponibles son

   * **gpt-3.5-turbo**
   * **gpt-3.5-turbo-16k**

### DALL·É

   El modelo DALL·E puede generar y editar imágenes a partir de una indicación en lenguaje natural.

   Más adelante en este libro, en el Capítulo 4, nos divertiremos un poco con el modelo DALL·E para visualizar la conversación de lo que se está discutiendo en su episodio de podcast favorito.

   Algunos de los modelos DALL·E disponibles son

   * **de-e-3**
   * **de-e-2**

### TTS

   El modelo TTS toma texto y lo convierte en audio con resultados sorprendentemente buenos. En la mayoría de los casos, el audio es casi indistinguible de una voz humana.

   Algunos de los modelos TTS disponibles son

   * **tts-1**
   * **tts-1-hd**

### Whisper

   En términos simples, el modelo Whisper convierte el audio en texto.

   En este libro, utilizaremos el modelo Whisper para buscar texto en un episodio de podcast.

### Embeddings

   El modelo de incrustaciones puede convertir grandes cantidades de texto en una representación numérica de cómo se relacionan las cadenas del texto. ¿Por qué es útil? Las incrustaciones permiten a los desarrolladores realizar tareas específicas utilizando conjuntos de datos personalizados. Sí, esto significa que puede entrenar el modelo de incrustaciones con datos específicos que sean relevantes para su aplicación. Esto le permite realizar operaciones como

   * Búsqueda dentro de su propio cuerpo de texto
   * Agrupar datos de modo que las cadenas de texto se agrupen por su similitud
   * Obtener recomendaciones (donde se recomiendan elementos con cadenas de texto relacionadas)
   * Detección de anomalías (donde se identifican valores atípicos con poca relación)
   * Medición de la diversidad (donde se analizan distribuciones de similitud)
   * Clasificación de datos (donde las cadenas de texto se clasifican por su etiqueta más similar)

### Moderation

   Los modelos de moderación son modelos afinados que pueden detectar si un texto puede ser sensible o inseguro. Estos modelos pueden analizar el contenido del texto y clasificarlo según las siguientes categorías:

   * Odiar
   * Odio/amenaza
   * Acoso
   * Acoso/amenaza
   * Autolesión
   * Autolesión/intención
   * Autolesión/instrucciones
   * Sexual
   * Sexual/menores
   * Violencia
   * Violencia/gráfica

   Los modelos de moderación disponibles son

   * Moderación de textos más reciente
   * Moderación de texto estable

### Legacy and Deprecated

   Desde el debut de ChatGPT, OpenAI ha seguido dando soporte a sus modelos de IA más antiguos, pero se los ha etiquetado como modelos “heredados” u “obsoletos” . Estos modelos siguen existiendo; sin embargo, han lanzado otros modelos que son más precisos, más rápidos y más económicos de usar.

**Nota**: ¡Esta no es de ninguna manera una lista exhaustiva de los modelos disponibles para desarrolladores proporcionados por OpenAI! A medida que se publiquen modelos más nuevos, los modelos más antiguos se marcarán como heredados o en desuso. Por lo tanto, es importante mantenerse actualizado consultando la lista de modelos disponibles en la lista de modelos de la documentación de OpenAI: https://platform.openai.com/docs/models

### Cuando hablamos de tokens, pensemos en StringTokenizer y no en tokens de acceso

Al utilizar una API de terceros, es posible que piense en un token en el mismo sentido que en un token de acceso, que normalmente es un UUID que le permite identificarse y mantener una sesión con el servicio. Bueno, olvídese de esa definición por ahora.

Ahora bien, como desarrollador de Java, probablemente hayas tenido la oportunidad de usar la clase `java.util.StringTokenizer` para tomar una cadena y dividirla en una matriz de cadenas más pequeñas para poder iterarla con el propósito que necesites. Por ejemplo, si tienes un párrafo de texto, puedes dejar que tu delimitador sea “.” para obtener una matriz de oraciones en el párrafo.

La buena noticia es que el concepto de token de la API de OpenAI es muy similar al concepto de Java en el sentido de que es un fragmento de texto. **Para las API de OpenAI, un token es un fragmento de texto de aproximadamente 4 caracteres de longitud**. Eso es todo, nada más especial.

Entonces, si un token es un fragmento de texto de aproximadamente 4 caracteres, ¿por qué nos importa?

Al trabajar con los modelos textuales de OpenAI, los desarrolladores deben tener en cuenta las limitaciones de tokens, ya que afectan el costo y el rendimiento de las llamadas a la API. Por ejemplo, el modelo gpt-3.5-turbo tiene una limitación de tokens de 4096 tokens, mientras que el modelo gpt-4-vision tiene una limitación de 128 000 tokens (que es aproximadamente el tamaño de una novela de 300 páginas). Las limitaciones de tokens para los modelos se denominan **context windows-ventanas de contexto**.

Como resultado, los desarrolladores deben tener en cuenta la longitud de las indicaciones como entradas y salidas de los modelos, asegurándose de que se ajusten a las restricciones de token del modelo.

La Tabla 1-1 proporciona una lista de algunos de los modelos más actuales con las limitaciones de token y sus precios.

**Tabla 1-1 Lista de modelos con sus limitaciones de tokens y el costo por token**

![image](https://github.com/user-attachments/assets/83698081-4bad-4fba-9b71-b248a7dead84)

### La temperatura es cuestión de creatividad

Por supuesto, ChatGPT no es un ser consciente, por lo que no es capaz de pensar como lo hacemos los humanos. Sin embargo, al ajustar la configuración de temperatura en sus mensajes a la API de ChatGPT, puede permitir que las respuestas sean más creativas. Pero comprender lo que entiende es crucial si desea aprovechar al máximo su potencial.

![image](https://github.com/user-attachments/assets/8cd7a103-90c1-4887-8df1-466dda914b64)

**Figura 1-2 Modificar la temperatura para obtener respuestas más (o menos) creativas**

## Introducción a OpenAI Playground

¡Ahora es el momento de tomar los conceptos que hemos aprendido hasta ahora y comenzar a ponerlos en práctica! Sin embargo, debemos hacer lo primero y, por lo tanto, necesitarás tener una cuenta de desarrollador con OpenAI y crear una clave API.

Dirígete a la siguiente URL para crear tu cuenta de desarrollador y clave API:

https://platform.openai.com/account/api-keys

Como puede ver en la imagen de la Figura 1-3, puede nombrar su clave API como desee.

![image](https://github.com/user-attachments/assets/005ca599-4ce6-4c36-a4ee-61645504db6a)

**Figura 1-3 Antes de poder acceder al área de juegos o realizar llamadas API, necesita tener una clave API**

**Debe tener en cuenta que, como requisito para crear una clave API, deberá proporcionar a OpenAI una tarjeta de crédito para que se le pueda facturar el uso de sus modelos.**

Ahora que tienes tu clave API, vayamos directamente al Chat Playground en la siguiente URL:

https://platform.openai.com/playground

Al ingresar al Playground, haga clic en el cuadro combinado en la parte superior y seleccione la opción Chat para finalizar el Playground de chat, como se muestra en la Figura 1-4.

![image](https://github.com/user-attachments/assets/d74a2130-a171-4e8b-9896-2a3c46bf972b)

**Figura 1-4 Después de ingresar al Playground, seleccione la opción de chat**

La Figura 1-5 muestra el Playground de chat, con ciertas partes numeradas para que puedan identificarse fácilmente.

![image](https://github.com/user-attachments/assets/5c8dedc7-5717-49ae-9f60-90c2d725b634)

**Figura 1-5 El Playground de chat puede resultar un poco intimidante a primera vista**

#### 1. System

Como puede ver, la interfaz de usuario de Chat Playground es mucho más compleja que la del sitio web ChatGPT que utilizan todos los demás. Hablemos ahora del campo Sistema (consulte la Figura 1-5 , elemento 1).

En mi opinión, ChatGPT puede describirse como “una forma de inteligencia artificial sumamente poderosa… con amnesia”. Por lo tanto, cuando uses ChatGPT de manera programática, ¡debes informarle al sistema quién participa en la conversación!

La Figura 1-6, que se muestra a continuación, le brinda una idea de los miles de roles diferentes que ChatGPT puede desempeñar en una conversación.

![image](https://github.com/user-attachments/assets/77103341-1cde-4a1e-97bf-7d9b34dcd3cc)

**Figura 1-6 El campo Sistema en el área de chat le permite establecer el rol que desempeñará ChatGPT en la conversación**

#### 2. User

El campo User (Figura 1-5, elemento 2) en el Playground de ChatGPT es donde escribe su mensaje para ChatGPT, que puede ser cualquier cosa que desee, por ejemplo, "describe how telemedicine will affect the medical industry - describe cómo la telemedicina afectará la industria médica".

#### 3. Assistant - Asistente (opcional)

Cuando cargas por primera vez el Chat Playground, el campo Asistente (Figura 1-5, elemento 3) no está visible. Para que aparezca, debes hacer clic en el símbolo “ + ” junto a “Agregar mensaje”. Ahora, te estarás preguntando: “¿Por qué es necesario este campo?”. Bueno, esa es una buena pregunta. Si quieres que ChatGPT recuerde algo que ya te ha dicho en una conversación anterior, entonces debes escribir en el campo Asistente todo lo que ya te haya dicho y que creas que es relevante para continuar con la conversación. Recuerda, es una IA muy poderosa, ¡pero tiene amnesia!

#### 4. Agregar mensaje - Message  (opcional)

El símbolo “ + ” de **Add Message- Agregar mensaje** (Figura 1-5 , elemento 4) es donde debe hacer clic para agregar un mensaje del Asistente a la conversación u otro mensaje de Usuario . Ahora, puede preguntarse: “¿Qué sentido tiene agregar otro mensaje de Usuario a la conversación cuando puedo escribir lo que quiero en el campo de Usuario original que se encuentra arriba?” Buena pregunta.

Si desea separar su comando de sus datos, deberá utilizar un mensaje de usuario separado para eso.

¿Recuerdas que en el Listado 1-4 anterior de este capítulo teníamos que usar el “###” para separar el comando a ChatGPT de los datos que queríamos que analizara? Bueno, esto ya no es necesario porque el comando sería el primer mensaje de usuario y los datos serían el segundo mensaje de usuario .

#### 5. Ver código (opcional)

Después de haber enviado su mensaje usando el área de juegos, puede hacer clic en el botón Ver código (Figura 1-5 , elemento 5) para ver el código necesario para enviar el mismo mensaje usando cualquiera de los idiomas que admiten.

Es posible que notes que Java no es un lenguaje admitido oficialmente, pero lo solucionaremos en el Capítulo 2 , cuando usemos ChatGPT como programador en pareja y portemos su interfaz REST a Java nosotros mismos.

#### 6. Modelo (opcional)

Anteriormente en este capítulo, hablamos sobre los distintos modelos que están disponibles para los desarrolladores. Haga clic en el campo de modelo para ver una lista de los modelos disponibles.

También puede ver que algunos modelos tienen un mes y un día asociados a su nombre, que es simplemente una instantánea de ese modelo. La selección programática de una instantánea permite a los desarrolladores tener algún tipo de previsibilidad en las respuestas que recibirán de ChatGPT, porque los modelos actuales siempre se actualizan.

#### 7. Temperatura (opcional)

Como se señaló anteriormente en este capítulo, el selector de temperatura varía entre 0 y 2 y le permite seleccionar la “aleatoriedad” de la respuesta.

#### 8. Longitud máxima (opcional)

¿Recuerdas la discusión anterior en este capítulo sobre los tokens? Al seleccionar cualquier elemento en el rango de este elemento, puedes ajustar la cantidad de tokens (que afecta directamente la cantidad de palabras ) en la respuesta.

¡Pruébelo ahora! Experimente con el rol de “sistema”
Ahora que estamos familiarizados con varias de las funciones de Chat Playground, enviemos nuestro primer mensaje usando las configuraciones que mencionamos anteriormente. Los listados 1-7 y 1-8 usan el mismo mensaje para pedirle a ChatGPT que escriba algunos párrafos sobre telemedicina, pero la función del sistema es muy diferente entre sí.
Sistema : Eres un investigador estrictamente factual.
Usuario : Escribe 3 párrafos sobre los pros y contras de la telemedicina.
Listado 1-7PROMPT. Pros y contras de la telemedicina para investigadores
Sistema : Eres un bloguero de salud con muchas opiniones que siempre tiene historias con experiencias de primera mano.
Usuario : Escribe 3 párrafos sobre los pros y contras de la telemedicina.
Listado 1-8PROMPT. Los pros y contras de la telemedicina según un bloguero de salud con opiniones
Se le recomienda que pruebe estas dos indicaciones usted mismo y vea cuáles son las respuestas. Ajuste la configuración de la temperatura y la longitud de la ficha para familiarizarse con la forma en que esos parámetros afectan el resultado.

Conclusión
Acabas de aprender más sobre cómo los desarrolladores pueden usar ChatGPT. Cubrimos algunos de los conceptos básicos de Chat Playground, que es una interfaz web para que los desarrolladores interactúen con la API de ChatGPT.

Hablamos sobre cómo configurar los roles de sistema, usuario y asistente en el Chat Playground y cómo ajustar configuraciones como la temperatura y la duración máxima de salida.

Aprendió sobre algunos de los parámetros y la terminología necesarios para usar Chat Playground, como el modelo, la temperatura y los tokens. Familiarizarse con los parámetros de Chat Playground es esencial para saber cómo usar la API REST, ya que Playground es un subconjunto de las capacidades que ofrece la API REST.

En el próximo capítulo, veremos cómo usar ChatGPT como su “programador en pareja” y portar la interfaz REST ChatGPT oficialmente soportada a Java.
