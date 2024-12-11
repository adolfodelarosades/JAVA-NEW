# 3. Una guía paso a paso para crear Prompts efectivas

## Tabla de contenido

* Varias plataformas y sus formatos de Prompts
* Reconocimiento de personajes y profundidad de los Prompts
   * Algunas plataformas pueden tener limitaciones de caracteres en los Prompts
   * Los Prompts necesitan profundidad y contexto
   * Diferenciar entre Prompts implícitas y explícitas
   * Probar con frecuencia e iterar
* Comprender un diccionario de Prompts
   * Consistencia
   * Mejoramiento
   * Capacitación e incorporación
   * Flexibilidad
* Factores clave a tener en cuenta: contexto, claridad y concisión
   * Proporcionar contexto
   * Claridad
   * Concisión
   * Algunos ejemplos de uso cotidiano
      * Servicio de atención al cliente mediante chatbot
      * Diagnóstico médico con IA
      * Creación de contenido
      * Herramientas de análisis financiero
      * Dispositivos domésticos inteligentes
* Errores comunes que se deben evitar al elaborar indicaciones
   * Ser demasiado vago
   * Complicando demasiado el mensaje
   * No proporcionar suficiente contexto
   * Suponiendo que el modelo conoce el contexto más reciente
   * Uso de jerga o lenguaje excesivamente técnico
   * Frases ambiguas
   * No especificar el formato deseado
   * Descuidar el establecimiento de límites
   * Confiar únicamente en el sesgo implícito
   * Esperando una intuición humana
   * Confiar demasiado en la precisión de la IA
   * No iterar ni refinar el mensaje
   * Malinterpretación de respuestas abiertas
   * Ignorar la configuración de temperatura
   * Suponiendo que la IA entiende las emociones

Los Prompts sirven como puente de comunicación entre los humanos y los sistemas de IA. Elaborar un mensaje eficaz es esencial para garantizar que los sistemas de IA comprendan la intención del usuario y proporcionen respuestas significativas. A continuación, se muestran algunas formas habituales de crear un prompt. En este capítulo, analizaremos los aspectos esenciales de la generación de mensajes o, en otras palabras, cómo proporcionar comandos a la IA generativa que sean eficaces.

* **The first method is known as descriptive phrasing - El primer método se conoce como redacción descriptiva**: comience con un lenguaje claro y descriptivo. En lugar de simplemente indicar una palabra clave o un tema, explique brevemente. Por ejemplo, en lugar de preguntar “Elefantes”, podría preguntar: “Proporcione información sobre el hábitat y el comportamiento de los elefantes africanos”.

* **Use a question-based approach - Utilice un enfoque basado en preguntas**: plantear la pregunta como una pregunta directa puede ser una forma eficaz de buscar respuestas específicas. Por ejemplo, “¿Cuáles son las principales causas del cambio climático?” probablemente produciría una respuesta más concreta que una afirmación más ambigua.

* **Think in terms of scenario framing - Piense en términos de planteamiento de escenarios**: plantee un escenario o situación hipotética. Esto es particularmente útil cuando se buscan respuestas detalladas u orientadas a procesos. Un ejemplo podría ser: “Imagínese que está enseñando en una clase de secundaria. Explique el proceso de la fotosíntesis en términos simples”.

* **Ask for comparison requests - Solicitar comparaciones**: pedirle a la IA que compare dos o más elementos puede aclarar temas complejos. Por ejemplo, “Comparar los impactos económicos de la energía solar frente al carbón”.

* **Use explicit formatting - Utilice un formato explícito**: si busca un formato específico en la respuesta, indíquelo en la pregunta. Por ejemplo, “Enumere los cinco países más poblados del mundo”.
El método que elija dependerá en gran medida de su objetivo y de la naturaleza de la información que busque. La clave es ser claro, específico y brindar suficiente contexto para guiar al sistema de IA. A medida que la IA continúa evolucionando, dominar el arte de dar indicaciones se vuelve aún más crucial para aprovechar todo su potencial.

## Varias plataformas y sus formatos de mensajes

Las distintas plataformas y herramientas de IA generativa suelen tener formatos o convenciones únicos para sus indicaciones, adaptados a sus funcionalidades y objetivos específicos. A continuación, se muestran algunas plataformas y sus respectivos estilos de indicaciones:

* **OpenAI's GPT models - Modelos GPT de OpenAI**: los modelos de OpenAI, especialmente aquellos como GPT-3, funcionan bien con indicaciones en lenguaje natural. Las indicaciones pueden ser preguntas, afirmaciones o escenarios. Por ejemplo, “Traduce el siguiente texto en inglés al francés: 'Hola, ¿cómo estás?'”
  
* **BERT and transformers - BERT y transformadores**: estos modelos, que se utilizan para tareas como la clasificación de textos o la respuesta a preguntas, requieren que las indicaciones se conviertan en tokens y se pasen como secuencias de entrada. Por ejemplo, dada una pregunta y un pasaje, la indicación podría ser una secuencia de tokens combinada de ambos.

* **Image classification - Clasificación de imágenes ( p. ej., ResNet, VGG)**: en este caso, la "prompt" suele ser una imagen, procesada y estandarizada para ajustarse a las dimensiones de entrada del modelo. El usuario no proporciona un prompt de texto, sino que selecciona una imagen para clasificar.

* **StyleGAN and image generators - StyleGAN y generadores de imágenes**: en estos modelos, el mensaje podría ser una descripción de texto como “una casa de ladrillo de dos pisos a la luz del día”, que el modelo intenta generar visualmente.

* **Music generators - Generadores de música (por ejemplo, MuseNet)**: las indicaciones pueden incluir algunas notas, un género o una descripción, guiando al modelo para producir un estilo específico o una continuación de música.
  
* **Tacotron for speech synthesis - Tacotron para síntesis de voz**: La instrucción es textual, por ejemplo: “Lea este texto con calma”. Luego, el modelo convierte el texto en voz, teniendo en cuenta la instrucción proporcionada.

Al crear indicaciones para diferentes plataformas, es esencial comprender los requisitos de la plataforma y la naturaleza del modelo subyacente. Familiarizarse con la documentación y las pautas de la plataforma es crucial para crear indicaciones efectivas que produzcan los resultados deseados. A medida que los sistemas de IA generativa se vuelven más complejos, es muy posible que puedan comprender indicaciones más sencillas.

## Reconocimiento de personajes y profundidad de los Prompts

La creación de prompts para la IA no se trata solo de las palabras que se utilizan, sino también de comprender la profundidad y los matices necesarios para lograr el resultado deseado. Reconocer el límite de caracteres y la profundidad de las indicaciones puede marcar una diferencia sustancial en los resultados obtenidos. A continuación, se presentan algunas características de las indicaciones que se deben tener en cuenta.

### Algunas plataformas pueden tener limitaciones de caracteres en los Prompts

Muchos modelos de IA, especialmente los modelos de lenguaje, tienen un límite máximo de tokens o caracteres para sus entradas. Por ejemplo, GPT-3 tiene un límite de tokens que incluye tanto el prompt como la response. Si un prompt es demasiado larga, puede truncar o limitar la respuesta. Por lo tanto, es fundamental ser conciso y preciso con los prompts, asegurándose de que transmitan la intención sin ser demasiado verbosas.

### Los Prompts necesitan profundidad y contexto

Un Prompt debe brindar suficiente profundidad y contexto para que el modelo comprenda el resultado deseado. Por ejemplo, en lugar de pedir “Traducir”, un mensaje más detallado podría ser “Traducir el siguiente texto del inglés al francés”. Esta especificidad garantiza que la IA conozca los idiomas de origen y destino.

### Diferenciar entre Prompts implícitas y explícitas

A veces, un Prompt más extenso y explícito puede dar mejores resultados que una más breve e implícito. Por ejemplo, “Escribe un resumen detallado sobre la Segunda Guerra Mundial centrándote en sus causas” puede dar resultados más concretos que simplemente “Cuéntame sobre la Segunda Guerra Mundial”.

### Probar con frecuencia e iterar

A menudo resulta beneficioso probar distintas profundidades de indicaciones (desde indicaciones concisas hasta otras más detalladas) para observar cuál da el mejor resultado. Este enfoque iterativo ayuda a refinar la eficacia de la indicación.

En resumen, reconocer el carácter y la profundidad de los prompts es crucial para aprovechar las capacidades de la IA de manera eficaz. Si bien es necesario ser conciso debido a los límites de tokens, garantizar que el prompt tenga la profundidad y el contexto suficientes es igualmente importante para guiar a la IA hacia el resultado deseado.

## Comprender un Prompt Dictionary

Un diccionario de Prompts sirve como un compendio de indicaciones cuidadosamente elaboradas y adaptadas a tareas específicas, lo que garantiza una comunicación eficiente con los modelos de IA. Esta guía tiene como objetivo desglosar el concepto y los beneficios de un diccionario de Prompts.

* **¿Qué es entonces un diccionario de Prompts?** Un diccionario de Prompts es una lista o base de datos seleccionada de Prompts estandarizadas, diseñadas para lograr respuestas o acciones específicas de un modelo de IA. Piense en ello como un “manual de frases” para interactuar con la IA.

Algunas ventajas de utilizar un diccionario de Prompts son las siguientes.

**Consistencia**

Uno de los principales beneficios de un diccionario de Prompts es garantizar la coherencia. Independientemente de quién utilice la IA, el uso de Prompts estandarizadas del diccionario garantiza la uniformidad de las respuestas, lo que hace que los resultados de la IA sean predecibles y fiables.

**Mejoramiento**

Con el tiempo, a medida que los usuarios interactúan con los modelos de IA, identifican qué Prompt dan los mejores resultados. Un diccionario de Prompts se puede actualizar continuamente para incluir estas Prompts optimizados, mejorando así la eficiencia y la precisión del modelo.

**Capacitación e incorporación**

Para los usuarios nuevos que no están familiarizados con la interacción con modelos de IA, un diccionario de Prompts es un recurso valioso. Les proporciona una lista de Prompts efectivos, lo que garantiza que puedan lograr los resultados deseados sin una curva de aprendizaje prolongada.

**Flexibilidad**

Si bien un diccionario de Prompts proporciona indicaciones estandarizadas, también puede incluir variaciones o frases alternativas para adaptarse a diferentes contextos o matices.

En esencia, un diccionario de Prompts agiliza el proceso de interacción con los modelos de IA. No solo garantiza la coherencia, sino que también ayuda a lograr respuestas más precisas y significativas. Para cualquier persona que trabaje habitualmente con IA, mantener y actualizar periódicamente un diccionario de Prompts puede ser un punto de inflexión.

## Factores clave a tener en cuenta: contexto, claridad y concisión

### Proporcionar contexto

El contexto, en el ámbito de la creación de mensajes de IA, es la columna vertebral que proporciona un contexto completo para cualquier consulta, lo que garantiza que la respuesta resultante no solo sea precisa, sino también relevante para la intención del usuario. La importancia del contexto surge de varios factores:

* Al incorporar el contexto, el sistema de IA está mejor preparado para comprender los matices de una consulta. Por ejemplo, la indicación “Traducir este texto en inglés sobre procedimientos médicos al francés” ofrece más claridad que simplemente “Traducir esto al francés”. La información contextual sobre los procedimientos médicos garantiza una traducción que tenga en cuenta la terminología médica.

* Un contexto bien definido puede reducir drásticamente las posibilidades de que la IA interprete mal una pregunta. Si un usuario pregunta sobre "Java", la respuesta puede variar desde programación hasta geografía. Pero si el contexto especifica "programación Java", la IA se centra en el tema relevante.

* Los usuarios suelen buscar respuestas detalladas y personalizadas. Al comprender el contexto, la IA puede evitar respuestas genéricas. Por ejemplo, “¿Cómo estará el clima?” podría arrojar un pronóstico actual, pero “¿Cómo estará el clima en Seattle en diciembre?” ofrece una respuesta específica y procesable para el contexto.

* En lugar de tener que entablar un intercambio prolongado con la IA para obtener aclaraciones, una indicación contextual a menudo puede conducir a la respuesta deseada en una sola interacción.

* En esencia, el contexto es como una brújula para los sistemas de IA, que les proporciona la dirección que necesitan para generar respuestas perspicaces, precisas y relevantes para el usuario. Aprovechar el contexto de forma adecuada puede mejorar la calidad de las interacciones y ofrecer una experiencia de usuario más fluida.

### Claridad

La claridad es un factor crucial en el ámbito de la creación de indicaciones de IA. Garantiza que el modelo de IA capte la intención del usuario sin ambigüedad, lo que genera resultados más precisos y útiles. A continuación, se explica por qué la claridad es fundamental:

* Las indicaciones claras eliminan cualquier imprecisión y guían a la IA hacia una comprensión precisa. Por ejemplo, pedir “información sobre la manzana” podría llevar a obtener datos sobre la fruta o la empresa tecnológica. Sin embargo, especificar “información sobre Apple Inc.” brinda claridad. Una indicación explícita a menudo significa que la IA puede generar una respuesta más rápidamente, sin la necesidad de considerar numerosas interpretaciones posibles o hacer preguntas de seguimiento.

* Los usuarios suelen preferir una interacción directa en la que formulan una pregunta y reciben una respuesta directa. La claridad en la indicación inicial minimiza las posibilidades de que haya errores de comunicación, lo que hace que la experiencia sea fluida. Las indicaciones ambiguas pueden hacer que la IA procese grandes cantidades de información innecesaria antes de generar una respuesta. Una indicación clara garantiza un uso óptimo de los recursos computacionales.

* Cuando los usuarios reciben respuestas precisas y relevantes de manera constante gracias a indicaciones claras, tienden a confiar más en el sistema de IA. Esta confianza es vital para la adopción generalizada y la satisfacción del usuario.

* La claridad es fundamental para una comunicación eficaz, no solo entre humanos, sino también entre humanos e IA. Al garantizar que las indicaciones sean claras, los usuarios pueden extraer la máxima utilidad de los sistemas de IA, lo que garantiza interacciones productivas y sin frustraciones.

### Concisión

La concisión en la creación de mensajes es el arte de transmitir un mensaje con la menor cantidad de palabras posible sin sacrificar la claridad. Al interactuar con modelos de IA, la brevedad puede ser una herramienta vital por varias razones:

* Los modelos de IA, aunque complejos, prosperan con instrucciones claras y concisas. Una indicación concisa a menudo puede dar lugar a una respuesta más rápida y precisa porque el modelo no tiene que filtrar información superflua. Para los usuarios, especialmente en entornos empresariales o profesionales, el tiempo es esencial. Ser capaz de elaborar una indicación breve pero clara puede ahorrar segundos valiosos y mejorar la productividad.

* Los mensajes breves suelen requerir menos potencia computacional para su procesamiento, lo que garantiza que el sistema funcione de manera eficiente y minimiza los costos potenciales. Cada palabra adicional en un mensaje es una vía potencial para la ambigüedad. Al mantener los mensajes breves, los usuarios pueden reducir las posibilidades de que la IA malinterprete su solicitud. Una interacción concisa reduce la carga cognitiva de los usuarios, que no necesitan elaborar oraciones largas y complejas, sino que pueden confiar en mensajes breves y claros para obtener la información o la acción que desean.

En esencia, la concisión no se trata solo de brevedad, sino de optimizar la comunicación. Garantiza que las interacciones con IA sean fluidas, eficientes y libres de complejidades innecesarias. A medida que los sistemas de IA continúan permeando varios sectores, comprender el poder de las indicaciones concisas se vuelve cada vez más crucial para los usuarios que buscan aprovechar todo el potencial de estas tecnologías.

### Algunos ejemplos de uso cotidiano

La combinación de contexto, claridad y concisión se puede observar en varios escenarios prácticos al interactuar con modelos de IA. A continuación, se ofrecen algunos ejemplos ilustrativos:

<img width="1093" alt="image" src="https://github.com/user-attachments/assets/fd187984-eb50-4eb8-abf9-4b0d8c26826c">

```text
Chatbot Customer Service Poor: “Help me!”

Improved: “How do I reset my password?”

Best: “Instructions for password reset?”

Here, the last option is both concise and clear, eliminating any ambiguity about the user's intent and thereby expediting the resolution process.

Medical Diagnosis AI Poor: “I don't feel well.”

Improved: “I have a fever and sore throat.”

Best: “Symptoms: fever, sore throat.”
```

```text
Servicio de atención al cliente  deficiente por chatbot: “¡Ayúdenme!”

Mejorado: “¿Cómo restablezco mi contraseña?”

Mejor: “¿Instrucciones para restablecer la contraseña?”

Aquí, la última opción es concisa y clara, eliminando cualquier ambigüedad sobre la intención del usuario y agilizando así el proceso de resolución.

Diagnóstico médico IA  Pobre: ​​“No me siento bien”.

Mejorado: “Tengo fiebre y dolor de garganta”.

Mejor: “Síntomas: fiebre, dolor de garganta”.
```

El mensaje final proporciona todo el contexto necesario y está libre de palabras adicionales, que pueden resultar fundamentales en una emergencia médica.

<img width="1093" alt="image" src="https://github.com/user-attachments/assets/54bc6b3d-ba23-4248-a8dc-2fbe15e1b1b5">

```text
Content Creation Poor: “Write something about climate change.”

Improved: “Write a 500-word essay on climate change impacts.”

Best: “500-word essay, climate change impacts.”

The latter prompt is succinct but still contains all the critical information for generating the required content.

Finance Analysis Tools Poor: “Tell me about stocks.”

Improved: “What's the current value of Apple stocks?”

Best: “Current value, Apple stocks?”
```

```text
Creación de contenido  deficiente: “Escribe algo sobre el cambio climático”.

Mejorado: “Escribe un ensayo de 500 palabras sobre los impactos del cambio climático”.

Mejor: “Ensayo de 500 palabras, impactos del cambio climático”.

El último mensaje es conciso pero aún así contiene toda la información crítica para generar el contenido requerido.

Herramientas de análisis financiero  deficientes: “Háblame de las acciones”.

Mejorado: "¿Cuál es el valor actual de las acciones de Apple?"

Mejor: “¿Valor actual de las acciones de Apple?”
```

En finanzas, donde la información en tiempo real es crucial, el último aviso podría producir resultados más rápidos y precisos.

<img width="990" alt="image" src="https://github.com/user-attachments/assets/ec982707-31f7-4018-a001-3408e9921b55">

```text
Smart Home Devices Poor: “Can you make it cooler here?”

Improved: “Set the thermostat to 22 degrees.”

Best: “Thermostat, 22 degrees.”
```

```text
Dispositivos domésticos inteligentes  Pobre: ​​"¿Puedes hacer que esté más fresco aquí?"

Mejorado: “Ponga el termostato a 22 grados”.

Mejor: “Termostato, 22 grados”.
```

Para los dispositivos domésticos inteligentes que dependen de comandos de voz, la brevedad y la claridad pueden hacer que las interacciones sean más naturales y eficientes.

Al optimizar el contexto, la claridad y la concisión, los usuarios pueden interactuar de manera más efectiva con los modelos de IA en una variedad de aplicaciones.

### Errores comunes que se deben evitar al elaborar Prompts

La creación de indicaciones para los modelos de IA es tanto un arte como una ciencia. Los modelos de IA son cada vez más complejos y versátiles, y los matices de cómo interpretan las indicaciones cambian rápidamente. Como resultado, es cada vez más esencial comprender no solo lo que funciona, sino también lo que no. En la siguiente sección se destacan algunos errores comunes que se deben evitar.

<img width="939" alt="image" src="https://github.com/user-attachments/assets/b7cfd546-00c8-4a19-911f-31c337245de8">

```text
Being Overly Vague Mistake: Using general or ambiguous language.

Example: “Tell me something interesting.”

Consequences: The AI can return a wide variety of results, many of which might not be relevant to the user's actual intent.

Solution: Specify the domain or context, e.g. “Tell me an interesting fact about space.”
```

<img width="949" alt="image" src="https://github.com/user-attachments/assets/63aa7a60-5e1a-4a0e-9e19-30d198b54250">

```text
Overcomplicating the Prompt Mistake: Using lengthy and complex sentences when a simpler one would do.

Example: “Can you provide me with a list of all the prime numbers that are below the number 100?”

Consequences: This can confuse the model or result in unnecessary computational processing.

Solution: “List prime numbers below 100.”
```

<img width="970" alt="image" src="https://github.com/user-attachments/assets/a1eb943c-56d8-4db9-b1e4-b73c4cca907d">

```text
Not Providing Enough Context Mistake: Leaving out key details that would guide the model's response.

Example: “Translate the following.” (without mentioning the source and target language)

Consequences: The AI might make assumptions, possibly choosing a default language, or ask for further clarification, slowing the interaction.

Solution: “Translate the following from English to French.”
```

<img width="995" alt="image" src="https://github.com/user-attachments/assets/025e096e-914d-4a5f-9254-f7d8087378dd">


```text
Assuming the Model Knows the Latest Context Mistake: Assuming the AI remembers past interactions or has knowledge of recent, post-training events.

Example: “What did I ask earlier?” or “Who won the latest Oscars?”

Consequences: Models such as GPT-3 don't have memory of past interactions, and their training data might not cover the most recent events.

Solution: Always provide necessary context within the prompt or inquire about events within the model's last training data cutoff.
```

<img width="1013" alt="image" src="https://github.com/user-attachments/assets/0a642184-4015-49a7-9c1e-865c607903a2">


```text
Using Jargon or Overly Technical Language Mistake: Assuming the AI will understand highly technical terms without context.

Example: “Explain eigenvalues.” (in a non-mathematical conversation)

Consequences: The response might not be tailored to the assumed expertise level of the user.

Solution: “Explain eigenvalues in simple terms.”
```

<img width="999" alt="image" src="https://github.com/user-attachments/assets/3984d6a0-5c46-4d94-89fe-f471475e536a">


```text
Ambiguous Phrasing Mistake: Using words or phrases that can be interpreted in multiple ways.

Example: “How heavy is a cricket?”

Consequences: The AI could interpret “cricket” as the sport or the insect, leading to confusing answers.

Solution: “What's the weight of an average cricket insect?”
```

<img width="1034" alt="image" src="https://github.com/user-attachments/assets/dafb73e3-87d9-4296-a701-c1284cb0eb20">


```text
Not Specifying the Desired Format Mistake: Not guiding the AI on how you want the answer presented.

Example: “Tell me about World War II.”

Consequences: The model might provide a broad overview when you wanted a timeline or specific details about a battle.

Solution: “Provide a timeline of major events in World War II.”
```

<img width="1055" alt="image" src="https://github.com/user-attachments/assets/490a6079-4b9c-43dd-8854-a0b479e4930e">

```text
Neglecting to Set Boundaries Mistake: Not setting explicit guidelines, which can lead to overly verbose or out-of-scope answers.

Example: “Write about the ocean.”

Consequences: The model might generate a lengthy general essay rather than focusing on a specific aspect.

Solution: “Write a short paragraph about oceanic zones.”
```

<img width="1026" alt="image" src="https://github.com/user-attachments/assets/6e9e9fe5-85d7-4f40-ace2-fb0870ba8113">


```text
Relying Solely on Implicit Bias Mistake: Not recognizing that AI models can have biases based on their training data.

Example: “Who is the best artist?”

Consequences: The answer can reflect cultural biases or popular opinions from the training data.

Solution: Frame questions objectively or seek data-backed answers.
```

<img width="1079" alt="image" src="https://github.com/user-attachments/assets/98377ebb-0518-4e72-8ae9-ceba53e62829">

```text
Expecting Humanlike Intuition Mistake: Assuming the AI will understand human nuances, humor, or cultural references.

Example: “Explain the joke behind ‘why did the chicken cross the road?’”

Consequences: While the AI can provide an explanation, it doesn't “understand” humor in the way humans do.

Solution: Understand the AI's strengths and limitations. Use it for data-driven insights rather than humanlike intuition.
```

<img width="1019" alt="image" src="https://github.com/user-attachments/assets/5cfa8059-2a88-4057-abd7-d00e8984580f">

```text
Over-Relying on AI's Accuracy Mistake: Assuming every answer the AI provides is 100% correct without verifying.

Example: “Give me the complete list of symptoms for disease X.”

Consequences: While AI strives for accuracy, it's not infallible and can sometimes miss nuances or recent updates in information.

Solution: Always cross-check critical information using trusted sources and don't rely solely on AI for medical or legal advice.
```

<img width="993" alt="image" src="https://github.com/user-attachments/assets/4f588854-577a-48f2-8841-06d59c7ecda5">

```text
Not Iterating or Refining the Prompt Mistake: Accepting the first answer without trying different prompt structures.

Example: If a vague prompt doesn't provide the desired answer, some users may not refine their question.

Consequences: Settling for incomplete or not fully relevant information.

Solution: If the first response isn't satisfactory, rephrase or specify the query further.
```

<img width="1067" alt="image" src="https://github.com/user-attachments/assets/dc192b8f-47b0-4808-850e-1c4c5ce162cc">


```text
Misinterpreting Open-Ended Responses Mistake: Asking open-ended questions and expecting a definitive answer.

Example: “What's the meaning of life?”

Consequences: Getting philosophical or generalized answers that might not meet user expectations.

Solution: Ask more focused and concrete questions to get specific answers.
```

<img width="1026" alt="image" src="https://github.com/user-attachments/assets/6ff4dd0b-a456-43eb-b516-c3093ebf80d2">

```text
Ignoring the Temperature Setting Mistake: Not adjusting the “temperature” setting (in models where this is available), which influences the randomness of the output.

Example: Keeping a high temperature for a prompt that requires a precise answer.

Consequences: Getting varied and potentially off-topic answers.

Solution: For specific, clear answers, use a lower temperature; for more creative prompts, a higher setting might be appropriate.
```

<img width="1064" alt="image" src="https://github.com/user-attachments/assets/320b4b8e-5e4d-42d6-9979-be0764b8f396">


```text
Assuming AI Understands Emotions Mistake: Believing that AI can empathize or understand human emotions deeply.

Example: “How do I cope with a breakup?”

Consequences: While AI can offer general advice or steps based on data, it lacks genuine human empathy.

Solution: Understand that AI responses are based on patterns and data, not genuine emotional understanding. For emotional or psychological issues, seek human support or professional counseling.
```

```text
```


```text
```


Error de ser demasiado vago  : utilizar un lenguaje general o ambiguo.

Ejemplo: “Cuéntame algo interesante”.

Consecuencias: La IA puede devolver una amplia variedad de resultados, muchos de los cuales podrían no ser relevantes para la intención real del usuario.

Solución: especifique el dominio o contexto, por ejemplo: “Cuéntame un dato interesante sobre el espacio”.

Error al complicar demasiado la instrucción  : utilizar oraciones largas y complejas cuando una más simple sería suficiente.

Ejemplo: “¿Puede proporcionarme una lista de todos los números primos que están por debajo del número 100?”

Consecuencias: Esto puede confundir el modelo o generar un procesamiento computacional innecesario.

Solución: “Enumere los números primos menores de 100”.

Error de no proporcionar suficiente contexto  : omitir detalles clave que guiarían la respuesta del modelo.

Ejemplo: “Traduzca lo siguiente” (sin mencionar el idioma de origen y de destino)

Consecuencias: La IA podría hacer suposiciones, posiblemente eligiendo un idioma predeterminado o solicitar más aclaraciones, lo que ralentizaría la interacción.

Solución: “Traduce lo siguiente del inglés al francés”.

Suponer que el modelo conoce el contexto más reciente  Error: Suponer que la IA recuerda interacciones pasadas o tiene conocimiento de eventos recientes posteriores al entrenamiento.

Ejemplo: “¿Qué pregunté antes?” o “¿Quién ganó los últimos Oscar?”

Consecuencias: Los modelos como GPT-3 no tienen memoria de interacciones pasadas y sus datos de entrenamiento podrían no cubrir los eventos más recientes.

Solución: proporcione siempre el contexto necesario dentro del mensaje o pregunte sobre eventos dentro del último corte de datos de entrenamiento del modelo.

Error al usar jerga o lenguaje excesivamente técnico  : suponer que la IA entenderá términos altamente técnicos sin contexto.

Ejemplo: “Explica los valores propios” (en una conversación no matemática)

Consecuencias: La respuesta podría no estar adaptada al nivel de experiencia asumido del usuario.

Solución: “Explique los valores propios en términos simples”.

Error de redacción ambigua  : utilizar palabras o frases que puedan interpretarse de múltiples maneras.

Ejemplo: “¿Cuánto pesa un grillo?”

Consecuencias: La IA podría interpretar “cricket” como el deporte o el insecto, lo que daría lugar a respuestas confusas.

Solución: “¿Cuál es el peso promedio de un insecto grillo?”

No especificar el formato deseado  Error: no guiar a la IA sobre cómo desea que se presente la respuesta.

Ejemplo: “Cuéntame sobre la Segunda Guerra Mundial”.

Consecuencias: El modelo puede proporcionar una descripción general amplia cuando desea una línea de tiempo o detalles específicos sobre una batalla.

Solución: “Proporcione una cronología de los principales eventos de la Segunda Guerra Mundial”.

No establecer límites  Error: No establecer pautas explícitas, lo que puede dar lugar a respuestas demasiado verbosas o fuera del alcance.

Ejemplo: “Escribe sobre el océano”.

Consecuencias: El modelo podría generar un ensayo general extenso en lugar de centrarse en un aspecto específico.

Solución: “Escribe un párrafo breve sobre las zonas oceánicas”.

Error al confiar únicamente en sesgos implícitos  : no reconocer que los modelos de IA pueden tener sesgos basados ​​en sus datos de entrenamiento.

Ejemplo: “¿Quién es el mejor artista?”

Consecuencias: La respuesta puede reflejar sesgos culturales u opiniones populares de los datos de entrenamiento.

Solución: Formule las preguntas de forma objetiva o busque respuestas respaldadas por datos.

Error al esperar una intuición similar a la humana  : suponer que la IA entenderá los matices humanos, el humor o las referencias culturales.

Ejemplo: “Explica el chiste detrás de ‘¿Por qué la gallina cruzó la calle?’”

Consecuencias: Si bien la IA puede brindar una explicación, no “entiende” el humor como lo hacemos los humanos.

Solución: comprender las fortalezas y limitaciones de la IA. Utilícela para obtener información basada en datos en lugar de una intuición humana.

Error de confiar demasiado en la precisión de la IA  : suponer que cada respuesta que proporciona la IA es 100 % correcta sin verificarla.

Ejemplo: “Dame la lista completa de síntomas de la enfermedad X”.

Consecuencias: Si bien la IA se esfuerza por lograr la precisión, no es infalible y a veces puede pasar por alto matices o actualizaciones recientes en la información.

Solución: Verifique siempre la información crítica utilizando fuentes confiables y no confíe únicamente en la IA para obtener asesoramiento médico o legal.

No iterar ni refinar la propuesta  Error: Aceptar la primera respuesta sin probar diferentes estructuras de propuesta.

Ejemplo: si una indicación vaga no proporciona la respuesta deseada, es posible que algunos usuarios no refinen su pregunta.

Consecuencias: Conformarse con información incompleta o no totalmente relevante.

Solución: Si la primera respuesta no es satisfactoria, reformule o especifique más la consulta.

Malinterpretar las respuestas abiertas  Error: Hacer preguntas abiertas y esperar una respuesta definitiva.

Ejemplo: “¿Cuál es el sentido de la vida?”

Consecuencias: Obtener respuestas filosóficas o generalizadas que podrían no cumplir con las expectativas de los usuarios.

Solución: Haga preguntas más específicas y enfocadas para obtener respuestas específicas.

Error en la configuración de la temperatura  : no ajustar la configuración de “temperatura” (en los modelos donde está disponible), lo que influye en la aleatoriedad de la salida.

Ejemplo: Mantener una temperatura alta para una instrucción que requiere una respuesta precisa.

Consecuencias: Recibir respuestas variadas y potencialmente fuera de tema.

Solución: Para obtener respuestas específicas y claras, utilice una temperatura más baja; para indicaciones más creativas, puede ser adecuado utilizar una temperatura más alta.

Suponer que la IA entiende las emociones  Error: creer que la IA puede empatizar o comprender profundamente las emociones humanas.

Ejemplo: “¿Cómo afronto una ruptura?”

Consecuencias: Si bien la IA puede ofrecer consejos generales o pasos a seguir basados ​​en datos, carece de empatía humana genuina.

Solución: comprenda que las respuestas de la IA se basan en patrones y datos, no en una comprensión emocional genuina. Para problemas emocionales o psicológicos, busque apoyo humano o asesoramiento profesional.

En conclusión, si bien los modelos de IA, especialmente los modelos de lenguaje, han avanzado mucho en la comprensión y generación de textos similares a los humanos, no son infalibles. La elaboración de indicaciones eficaces es una habilidad que requiere comprender tanto el potencial como las limitaciones del sistema de IA. Al evitar estos errores comunes, los usuarios pueden tener interacciones más productivas y precisas con los modelos de IA.
