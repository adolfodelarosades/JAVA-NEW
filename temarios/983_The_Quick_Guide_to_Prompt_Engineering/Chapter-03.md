# 3.
Una guía paso a paso para crear indicaciones efectivas
Tabla de contenido
Varias plataformas y sus formatos de mensajes
Reconocimiento de personajes y profundidad de las indicaciones
Algunas plataformas pueden tener limitaciones de caracteres en los mensajes
Las indicaciones necesitan profundidad y contexto
Diferenciar entre indicaciones implícitas y explícitas
Probar con frecuencia e iterar
Comprender un diccionario de indicaciones
Consistencia
Mejoramiento
Capacitación e incorporación
Flexibilidad
Factores clave a tener en cuenta: contexto, claridad y concisión
Proporcionar contexto
Claridad
Concisión
Algunos ejemplos de uso cotidiano
Servicio de atención al cliente mediante chatbot
Diagnóstico médico con IA
Creación de contenido
Herramientas de análisis financiero
Dispositivos domésticos inteligentes
Errores comunes que se deben evitar al elaborar indicaciones
Ser demasiado vago
Complicando demasiado el mensaje
No proporcionar suficiente contexto
Suponiendo que el modelo conoce el contexto más reciente
Uso de jerga o lenguaje excesivamente técnico
Frases ambiguas
No especificar el formato deseado
Descuidar el establecimiento de límites
Confiar únicamente en el sesgo implícito
Esperando una intuición humana
Confiar demasiado en la precisión de la IA
No iterar ni refinar el mensaje
Malinterpretación de respuestas abiertas
Ignorar la configuración de temperatura
Suponiendo que la IA entiende las emociones
Los mensajes sirven como puente de comunicación entre los humanos y los sistemas de IA. Elaborar un mensaje eficaz es esencial para garantizar que los sistemas de IA comprendan la intención del usuario y proporcionen respuestas significativas. A continuación, se muestran algunas formas habituales de crear un mensaje. En este capítulo, analizaremos los aspectos esenciales de la generación de mensajes o, en otras palabras, cómo proporcionar comandos a la IA generativa que sean eficaces.

El primer método se conoce como redacción descriptiva: comience con un lenguaje claro y descriptivo. En lugar de simplemente indicar una palabra clave o un tema, explique brevemente. Por ejemplo, en lugar de preguntar “Elefantes”, podría preguntar: “Proporcione información sobre el hábitat y el comportamiento de los elefantes africanos”.
Utilice un enfoque basado en preguntas: plantear la pregunta como una pregunta directa puede ser una forma eficaz de buscar respuestas específicas. Por ejemplo, “¿Cuáles son las principales causas del cambio climático?” probablemente produciría una respuesta más concreta que una afirmación más ambigua.
Piense en términos de planteamiento de escenarios: plantee un escenario o situación hipotética. Esto es particularmente útil cuando se buscan respuestas detalladas u orientadas a procesos. Un ejemplo podría ser: “Imagínese que está enseñando en una clase de secundaria. Explique el proceso de la fotosíntesis en términos simples”.
Solicitar comparaciones: pedirle a la IA que compare dos o más elementos puede aclarar temas complejos. Por ejemplo, “Comparar los impactos económicos de la energía solar frente al carbón”.
Utilice un formato explícito: si busca un formato específico en la respuesta, indíquelo en la pregunta. Por ejemplo, “Enumere los cinco países más poblados del mundo”.
El método que elija dependerá en gran medida de su objetivo y de la naturaleza de la información que busque. La clave es ser claro, específico y brindar suficiente contexto para guiar al sistema de IA. A medida que la IA continúa evolucionando, dominar el arte de dar indicaciones se vuelve aún más crucial para aprovechar todo su potencial.

Varias plataformas y sus formatos de mensajes
Las distintas plataformas y herramientas de IA generativa suelen tener formatos o convenciones únicos para sus indicaciones, adaptados a sus funcionalidades y objetivos específicos. A continuación, se muestran algunas plataformas y sus respectivos estilos de indicaciones:

Modelos GPT de OpenAI: los modelos de OpenAI, especialmente aquellos como GPT-3, funcionan bien con indicaciones en lenguaje natural. Las indicaciones pueden ser preguntas, afirmaciones o escenarios. Por ejemplo, “Traduce el siguiente texto en inglés al francés: 'Hola, ¿cómo estás?'”
BERT y transformadores: estos modelos, que se utilizan para tareas como la clasificación de textos o la respuesta a preguntas, requieren que las indicaciones se conviertan en tokens y se pasen como secuencias de entrada. Por ejemplo, dada una pregunta y un pasaje, la indicación podría ser una secuencia de tokens combinada de ambos.
Clasificación de imágenes ( p. ej., ResNet, VGG): en este caso, la "solicitud" suele ser una imagen, procesada y estandarizada para ajustarse a las dimensiones de entrada del modelo. El usuario no proporciona una solicitud de texto, sino que selecciona una imagen para clasificar.
StyleGAN y generadores de imágenes: en estos modelos, el mensaje podría ser una descripción de texto como “una casa de ladrillo de dos pisos a la luz del día”, que el modelo intenta generar visualmente.
Generadores de música (por ejemplo, MuseNet): las indicaciones pueden incluir algunas notas, un género o una descripción, guiando al modelo para producir un estilo específico o una continuación de música.
Tacotron para síntesis de voz: La instrucción es textual, por ejemplo: “Lea este texto con calma”. Luego, el modelo convierte el texto en voz, teniendo en cuenta la instrucción proporcionada.
Al crear indicaciones para diferentes plataformas, es esencial comprender los requisitos de la plataforma y la naturaleza del modelo subyacente. Familiarizarse con la documentación y las pautas de la plataforma es crucial para crear indicaciones efectivas que produzcan los resultados deseados. A medida que los sistemas de IA generativa se vuelven más complejos, es muy posible que puedan comprender indicaciones más sencillas.

Reconocimiento de personajes y profundidad de las indicaciones
La creación de indicaciones para la IA no se trata solo de las palabras que se utilizan, sino también de comprender la profundidad y los matices necesarios para lograr el resultado deseado. Reconocer el límite de caracteres y la profundidad de las indicaciones puede marcar una diferencia sustancial en los resultados obtenidos. A continuación, se presentan algunas características de las indicaciones que se deben tener en cuenta.

Algunas plataformas pueden tener limitaciones de caracteres en los mensajes
Muchos modelos de IA, especialmente los modelos de lenguaje, tienen un límite máximo de tokens o caracteres para sus entradas. Por ejemplo, GPT-3 tiene un límite de tokens que incluye tanto la solicitud como la respuesta. Si una solicitud es demasiado larga, puede truncar o limitar la respuesta. Por lo tanto, es fundamental ser conciso y preciso con las solicitudes, asegurándose de que transmitan la intención sin ser demasiado verbosas.

Las indicaciones necesitan profundidad y contexto
Un mensaje debe brindar suficiente profundidad y contexto para que el modelo comprenda el resultado deseado. Por ejemplo, en lugar de pedir “Traducir”, un mensaje más detallado podría ser “Traducir el siguiente texto del inglés al francés”. Esta especificidad garantiza que la IA conozca los idiomas de origen y destino.

Diferenciar entre indicaciones implícitas y explícitas
A veces, una indicación más extensa y explícita puede dar mejores resultados que una más breve e implícita. Por ejemplo, “Escribe un resumen detallado sobre la Segunda Guerra Mundial centrándote en sus causas” puede dar resultados más concretos que simplemente “Cuéntame sobre la Segunda Guerra Mundial”.

Probar con frecuencia e iterar
A menudo resulta beneficioso probar distintas profundidades de indicaciones (desde indicaciones concisas hasta otras más detalladas) para observar cuál da el mejor resultado. Este enfoque iterativo ayuda a refinar la eficacia de la indicación.

En resumen, reconocer el carácter y la profundidad de las indicaciones es crucial para aprovechar las capacidades de la IA de manera eficaz. Si bien es necesario ser conciso debido a los límites de tokens, garantizar que la indicación tenga la profundidad y el contexto suficientes es igualmente importante para guiar a la IA hacia el resultado deseado.

Comprender un diccionario de indicaciones
Un diccionario de indicaciones sirve como un compendio de indicaciones cuidadosamente elaboradas y adaptadas a tareas específicas, lo que garantiza una comunicación eficiente con los modelos de IA. Esta guía tiene como objetivo desglosar el concepto y los beneficios de un diccionario de indicaciones.

¿Qué es entonces un diccionario de indicaciones? Un diccionario de indicaciones es una lista o base de datos seleccionada de indicaciones estandarizadas, diseñadas para lograr respuestas o acciones específicas de un modelo de IA. Piense en ello como un “manual de frases” para interactuar con la IA.
Algunas ventajas de utilizar un diccionario de indicaciones son las siguientes.

Consistencia
Uno de los principales beneficios de un diccionario de indicaciones es garantizar la coherencia. Independientemente de quién utilice la IA, el uso de indicaciones estandarizadas del diccionario garantiza la uniformidad de las respuestas, lo que hace que los resultados de la IA sean predecibles y fiables.

Mejoramiento
Con el tiempo, a medida que los usuarios interactúan con los modelos de IA, identifican qué indicaciones dan los mejores resultados. Un diccionario de indicaciones se puede actualizar continuamente para incluir estas indicaciones optimizadas, mejorando así la eficiencia y la precisión del modelo.

Capacitación e incorporación
Para los usuarios nuevos que no están familiarizados con la interacción con modelos de IA, un diccionario de indicaciones es un recurso valioso. Les proporciona una lista de indicaciones efectivas, lo que garantiza que puedan lograr los resultados deseados sin una curva de aprendizaje prolongada.

Flexibilidad
Si bien un diccionario de indicaciones proporciona indicaciones estandarizadas, también puede incluir variaciones o frases alternativas para adaptarse a diferentes contextos o matices.

En esencia, un diccionario de sugerencias agiliza el proceso de interacción con los modelos de IA. No solo garantiza la coherencia, sino que también ayuda a lograr respuestas más precisas y significativas. Para cualquier persona que trabaje habitualmente con IA, mantener y actualizar periódicamente un diccionario de sugerencias puede ser un punto de inflexión.

Factores clave a tener en cuenta: contexto, claridad y concisión
Proporcionar contexto
El contexto, en el ámbito de la creación de mensajes de IA, es la columna vertebral que proporciona un contexto completo para cualquier consulta, lo que garantiza que la respuesta resultante no solo sea precisa, sino también relevante para la intención del usuario. La importancia del contexto surge de varios factores:

Al incorporar el contexto, el sistema de IA está mejor preparado para comprender los matices de una consulta. Por ejemplo, la indicación “Traducir este texto en inglés sobre procedimientos médicos al francés” ofrece más claridad que simplemente “Traducir esto al francés”. La información contextual sobre los procedimientos médicos garantiza una traducción que tenga en cuenta la terminología médica.
Un contexto bien definido puede reducir drásticamente las posibilidades de que la IA interprete mal una pregunta. Si un usuario pregunta sobre "Java", la respuesta puede variar desde programación hasta geografía. Pero si el contexto especifica "programación Java", la IA se centra en el tema relevante.
Los usuarios suelen buscar respuestas detalladas y personalizadas. Al comprender el contexto, la IA puede evitar respuestas genéricas. Por ejemplo, “¿Cómo estará el clima?” podría arrojar un pronóstico actual, pero “¿Cómo estará el clima en Seattle en diciembre?” ofrece una respuesta específica y procesable para el contexto.
En lugar de tener que entablar un intercambio prolongado con la IA para obtener aclaraciones, una indicación contextual a menudo puede conducir a la respuesta deseada en una sola interacción.
En esencia, el contexto es como una brújula para los sistemas de IA, que les proporciona la dirección que necesitan para generar respuestas perspicaces, precisas y relevantes para el usuario. Aprovechar el contexto de forma adecuada puede mejorar la calidad de las interacciones y ofrecer una experiencia de usuario más fluida.
Claridad
La claridad es un factor crucial en el ámbito de la creación de indicaciones de IA. Garantiza que el modelo de IA capte la intención del usuario sin ambigüedad, lo que genera resultados más precisos y útiles. A continuación, se explica por qué la claridad es fundamental:

Las indicaciones claras eliminan cualquier imprecisión y guían a la IA hacia una comprensión precisa. Por ejemplo, pedir “información sobre la manzana” podría llevar a obtener datos sobre la fruta o la empresa tecnológica. Sin embargo, especificar “información sobre Apple Inc.” brinda claridad. Una indicación explícita a menudo significa que la IA puede generar una respuesta más rápidamente, sin la necesidad de considerar numerosas interpretaciones posibles o hacer preguntas de seguimiento.
Los usuarios suelen preferir una interacción directa en la que formulan una pregunta y reciben una respuesta directa. La claridad en la indicación inicial minimiza las posibilidades de que haya errores de comunicación, lo que hace que la experiencia sea fluida. Las indicaciones ambiguas pueden hacer que la IA procese grandes cantidades de información innecesaria antes de generar una respuesta. Una indicación clara garantiza un uso óptimo de los recursos computacionales.
Cuando los usuarios reciben respuestas precisas y relevantes de manera constante gracias a indicaciones claras, tienden a confiar más en el sistema de IA. Esta confianza es vital para la adopción generalizada y la satisfacción del usuario.
La claridad es fundamental para una comunicación eficaz, no solo entre humanos, sino también entre humanos e IA. Al garantizar que las indicaciones sean claras, los usuarios pueden extraer la máxima utilidad de los sistemas de IA, lo que garantiza interacciones productivas y sin frustraciones.
Concisión
La concisión en la creación de mensajes es el arte de transmitir un mensaje con la menor cantidad de palabras posible sin sacrificar la claridad. Al interactuar con modelos de IA, la brevedad puede ser una herramienta vital por varias razones:

Los modelos de IA, aunque complejos, prosperan con instrucciones claras y concisas. Una indicación concisa a menudo puede dar lugar a una respuesta más rápida y precisa porque el modelo no tiene que filtrar información superflua. Para los usuarios, especialmente en entornos empresariales o profesionales, el tiempo es esencial. Ser capaz de elaborar una indicación breve pero clara puede ahorrar segundos valiosos y mejorar la productividad.
Los mensajes breves suelen requerir menos potencia computacional para su procesamiento, lo que garantiza que el sistema funcione de manera eficiente y minimiza los costos potenciales. Cada palabra adicional en un mensaje es una vía potencial para la ambigüedad. Al mantener los mensajes breves, los usuarios pueden reducir las posibilidades de que la IA malinterprete su solicitud. Una interacción concisa reduce la carga cognitiva de los usuarios, que no necesitan elaborar oraciones largas y complejas, sino que pueden confiar en mensajes breves y claros para obtener la información o la acción que desean.
En esencia, la concisión no se trata solo de brevedad, sino de optimizar la comunicación. Garantiza que las interacciones con IA sean fluidas, eficientes y libres de complejidades innecesarias. A medida que los sistemas de IA continúan permeando varios sectores, comprender el poder de las indicaciones concisas se vuelve cada vez más crucial para los usuarios que buscan aprovechar todo el potencial de estas tecnologías.

Algunos ejemplos de uso cotidiano
La combinación de contexto, claridad y concisión se puede observar en varios escenarios prácticos al interactuar con modelos de IA. A continuación, se ofrecen algunos ejemplos ilustrativos:

Servicio de atención al cliente  deficiente por chatbot: “¡Ayúdenme!”

Mejorado: “¿Cómo restablezco mi contraseña?”

Mejor: “¿Instrucciones para restablecer la contraseña?”

Aquí, la última opción es concisa y clara, eliminando cualquier ambigüedad sobre la intención del usuario y agilizando así el proceso de resolución.

Diagnóstico médico IA  Pobre: ​​“No me siento bien”.

Mejorado: “Tengo fiebre y dolor de garganta”.

Mejor: “Síntomas: fiebre, dolor de garganta”.

El mensaje final proporciona todo el contexto necesario y está libre de palabras adicionales, que pueden resultar fundamentales en una emergencia médica.

Creación de contenido  deficiente: “Escribe algo sobre el cambio climático”.

Mejorado: “Escribe un ensayo de 500 palabras sobre los impactos del cambio climático”.

Mejor: “Ensayo de 500 palabras, impactos del cambio climático”.

El último mensaje es conciso pero aún así contiene toda la información crítica para generar el contenido requerido.

Herramientas de análisis financiero  deficientes: “Háblame de las acciones”.

Mejorado: "¿Cuál es el valor actual de las acciones de Apple?"

Mejor: “¿Valor actual de las acciones de Apple?”

En finanzas, donde la información en tiempo real es crucial, el último aviso podría producir resultados más rápidos y precisos.

Dispositivos domésticos inteligentes  Pobre: ​​"¿Puedes hacer que esté más fresco aquí?"

Mejorado: “Ponga el termostato a 22 grados”.

Mejor: “Termostato, 22 grados”.

Para los dispositivos domésticos inteligentes que dependen de comandos de voz, la brevedad y la claridad pueden hacer que las interacciones sean más naturales y eficientes.

Al optimizar el contexto, la claridad y la concisión, los usuarios pueden interactuar de manera más efectiva con los modelos de IA en una variedad de aplicaciones.

Errores comunes que se deben evitar al elaborar indicaciones
La creación de indicaciones para los modelos de IA es tanto un arte como una ciencia. Los modelos de IA son cada vez más complejos y versátiles, y los matices de cómo interpretan las indicaciones cambian rápidamente. Como resultado, es cada vez más esencial comprender no solo lo que funciona, sino también lo que no. En la siguiente sección se destacan algunos errores comunes que se deben evitar.

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
