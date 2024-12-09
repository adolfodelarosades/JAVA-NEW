# Apéndice C. Aprendiendo algunas prácticas recomendadas de ChatGPT
Los desarrolladores web saben que crear páginas web es un oficio que tiene tanto de arte como de tecnología, tanto de diseño como de codificación. Mi principal suposición con este libro es que usted no quiere (o no tiene ni el tiempo ni la inclinación) convertirse en un desarrollador web. Por lo tanto, el oficio que aprenderá en este libro es el oficio de hacer que ChatGPT genere el código y el texto que necesita para las páginas web que desea publicar en línea.

Una parte importante de convencer a ChatGPT para que realice las tareas de creación de su página web es utilizar sus indicaciones para exponer lo que desea con la menor ambigüedad posible. Ese es el objetivo detrás de todas las indicaciones que ve en el libro. Sin embargo, incitar a ChatGPT es un arte, lo que significa que hay muchas formas sutiles de mejorar sus indicaciones para obtener mejores resultados. Es posible que descubra (¡crucemos los dedos!) que las indicaciones de este libro proporcionan puntos de partida suficientemente buenos para lograr que ChatGPT lo ayude a crear su sitio web. Si es así, ¡genial! Sin embargo, si no es así, no se desespere. Como muestra este apéndice, hay bastantes consejos, trucos y mejores prácticas que puede utilizar para lograr que ChatGPT genere código y texto de página web de alta calidad.

C.1 Solicitar a ChatGPT que adopte una personalidad
Una característica sorprendente de ChatGPT es que puede adoptar una personalidad específica (por ejemplo, un profesor, un consultor o un analista de datos) durante una conversación. Decirle al modelo “quién” es no solo le da a ChatGPT una perspectiva general desde la cual generar su resultado, sino que también coloca la conversación en un contexto más específico, lo que generalmente ayuda al modelo a formular resultados más específicos.

Para la creación de páginas web, puedes iniciar tus conversaciones con ejemplos de indicaciones de personajes como los siguientes:

Eres un consultor de diseño web .

Actuar como desarrollador web senior .

Proporcionar código que un ingeniero web front-end crearía .

Eres un gerente de marketing de sitios web .

Consejo: Para obtener ayuda para escribir los mensajes de aviso de tu personaje, consulta el repositorio de GitHub llamado Awesome ChatGPT Prompts: https://github.com/f/awesome-chatgpt-prompts .

Por supuesto, también puedes pedirle a ChatGPT que asuma cualquier personalidad que se adapte a tus necesidades, lo que resulta especialmente útil cuando pides ayuda para generar texto de página web.

C.2 Más detalles es mejor que menos
Si omites información importante en tus indicaciones, ChatGPT intentará adivinar lo que quieres, lo que casi con certeza no producirá resultados de calidad. No temas agregar detalles importantes a tus indicaciones para darle a la parte transformadora de ChatGPT algo en qué pensar.

Por ejemplo, considere el siguiente mensaje (del capítulo 1):

Escriba el código de la página web para mostrar "Hola mundo" en una fuente grande.
El uso de la palabra grande aquí es vago, por lo que ChatGPT adivinará qué tamaño desea para el texto. Por ejemplo, en el capítulo 1, mostré un código generado por ChatGPT que formateó el texto en una fuente de 48 píxeles. Sin embargo, si sabe que desea que el texto se muestre en una fuente de 72 píxeles, agregue eso a su mensaje:

Escriba el código de la página web para mostrar "Hola mundo" en una fuente de 72 píxeles.
A continuación se muestra un código de ejemplo generado por ChatGPT a partir de este mensaje:

<!DOCTYPE html>
<html>
<cabeza>
    <title>Hola mundo</title>
    <estilo>
        h1 {
            tamaño de fuente: 72px;
        }
    </estilo>
</cabeza>
<cuerpo>
    Hola mundo
</cuerpo>
</html>
Advertencia Una de las formas en que se entrena un modelo de lenguaje grande (LLM) como ChatGPT para producir resultados que no sean (o no siempre sean ) aburridos o comunes es agregar una pizca de aleatoriedad al proceso. Esta aleatoriedad también significa, en primer lugar, que ChatGPT no necesariamente genera resultados idénticos a partir de indicaciones idénticas y, en segundo lugar, que a veces ChatGPT parece hacer todo lo posible para no comprender sus indicaciones. Para esto último, casi siempre es la mejor estrategia borrar la conversación actual y comenzar de nuevo.

Los detalles suelen ser muy útiles a la hora de iniciar ChatGPT, pero si ves que el modelo se queda sin tiempo, se confunde o produce resultados incompletos, es posible que el culpable sea un exceso de detalles. En ese caso, intenta dividir tus indicaciones detalladas en dos o más indicaciones menos detalladas.

C.3 Establecer una longitud de salida
Cuando trabaja con ChatGPT para generar texto, dependiendo del mensaje, ChatGPT puede generar un resultado largo y/o detallado. Ese resultado tan extenso puede ser exactamente lo que desea, pero los componentes de la página web suelen tener restricciones en cuanto a la cantidad de texto que pueden admitir. Por ejemplo, puede querer que la descripción de un producto sea lo suficientemente grande como para que quepa un componente de tarjeta; de manera similar, puede querer que las respuestas a algunas preguntas frecuentes sean breves.

Por lo tanto, cuando le pides a ChatGPT que genere texto para el sitio web, a menudo querrás que ese texto tenga una longitud máxima. Puede ser de 200 palabras, 3 párrafos, 4 oraciones o 5 viñetas. Sea cual sea la longitud, asegúrate de incluirla como parte de tu mensaje. Algunos ejemplos:

Provide an answer to the question "Why was Jerry Lewis so popular in France?". Make the answer 100 words or less.

In three paragraphs, write a buyer's guide to cubic zirconia jewelry.

List ten fun things to do in the Broad Ripple neighborhood of Indianapolis.

Consejo: Es probable que ChatGPT ignore la longitud de salida sugerida en su primera respuesta. Esto es particularmente cierto para las longitudes expresadas en palabras, párrafos y oraciones. Una vez que la respuesta esté completa, ejecute un mensaje de seguimiento para solicitarle a ChatGPT que reduzca la respuesta a la longitud que especificó en el mensaje original.

Establecer una longitud de salida es un ejemplo de restricción , que se refiere a cualquier aspecto del mensaje que limite la respuesta de ChatGPT de alguna manera. A continuación, se muestran algunos ejemplos de restricciones con las que puede experimentar:

Write your output in the style of X(donde Xes un autor o publicación).

Write the text in a manner that's X(donde Xes un adjetivo o una frase adjetival como académico , casual o accesible para un niño de 10 años ).

Make the text X(donde Xes un adjetivo como vívido , animado o humorístico ).

Restringir sus solicitudes es una excelente manera de lograr que ChatGPT escriba texto más interesante.

C.4 Delimitar la entrada de texto adicional con comillas triples
Si proporciona una entrada de texto adicional para que ChatGPT la use, rodee la entrada con comillas triples e incluya ese hecho en su mensaje. Por ejemplo, en un proyecto anterior, le pedí a ChatGPT que escribiera una breve biografía del poeta Walt Whitman. Copié esa biografía y luego la pegué en el siguiente mensaje:

Crea un limerick a partir del texto rodeado por comillas triples.

"""Walt Whitman (1819-1892) fue un poeta, ensayista y periodista estadounidense, conocido como uno de los poetas más influyentes del canon estadounidense. A menudo se lo denominaba el "padre del verso libre" debido a su uso poco convencional de la forma.
  
Whitman nació el 31 de mayo de 1819 en West Hills, Nueva York. Su familia se mudó a Brooklyn cuando era niño, donde asistió a la escuela pública antes de abandonarla a los once años para trabajar en una serie de empleos, como chico de los recados, aprendiz de impresor y maestro.
  
En 1841, Whitman se dedicó al periodismo y fundó el periódico semanal "Long Islander". Continuó escribiendo y editando para varias publicaciones periódicas durante la década de 1840 y se hizo conocido por sus opiniones progresistas, defendiendo cuestiones como los derechos de los trabajadores y el sufragio femenino.
  
La innovadora colección de poesía de Whitman, "Hojas de hierba", publicada por primera vez en 1855, no se parecía a ninguna poesía que se hubiera visto antes en su forma de verso libre y contenido sincero. Este volumen, que revisó y amplió a lo largo de su vida, exploraba temas de democracia, sexualidad, muerte y el lugar del individuo en el universo.
 
Durante la Guerra Civil estadounidense, Whitman trabajó como empleado del gobierno y se ofreció como enfermero voluntario en un hospital del ejército en Washington, DC. Sus experiencias con soldados heridos y las realidades de la guerra lo impactaron profundamente e influyeron en gran parte de su trabajo posterior, en particular su poema "¡Oh, Capitán! ¡Mi capitán!", de luto por la muerte del presidente Lincoln.
  
Whitman continuó escribiendo y publicando su obra hasta su muerte el 26 de marzo de 1892 en Camden, Nueva Jersey. Su estilo innovador y su voz típicamente estadounidense lo han convertido en un referente en el estudio de la literatura estadounidense.
ChatGPT aceptó el desafío con la siguiente cancioncilla:

En Nueva York, un poeta llamado Whit,
Cuyo verso fue un éxito de formación libre.
De "Hojas de hierba" surgió,
Un nuevo estilo cantó Whitman,
En el canon de América, él ocupa un lugar destacado.
Incluir un texto de ejemplo es especialmente útil cuando quieres que ChatGPT genere un texto nuevo utilizando tu propio estilo de escritura. Por ejemplo, puedes decir algo como esto:

Utilizando el mismo estilo que el texto rodeado de comillas triples, escribe un ensayo breve sobre los beneficios nutricionales de comer colinabos.
""" Incluya aquí algunos párrafos de su propia escritura """
Al incluir un texto de ejemplo en su mensaje, tenga en cuenta que la mayoría de las consultas de ChatGPT están limitadas a unas 500 palabras (aproximadamente el doble de la cantidad de palabras del mensaje anterior). Recuerde (como explico en el capítulo 7) que puede usar Copilot para evitar esta limitación navegando a una página que incluya el texto al que desea que ChatGPT haga referencia y luego usando la barra lateral de Copilot para escribir su mensaje.

C.5 Un ejemplo vale más que mil indicaciones
Si le pide a ChatGPT que muestre algo inusual o esotérico, es posible que el modelo no obtenga lo que desea. Para orientar a ChatGPT en la dirección correcta, incluya dos o tres ejemplos del tipo de resultado que está buscando. A continuación, se incluye un ejemplo:

Crea una docena de insultos únicos de la forma "No es el X más Y de la Z", reemplazando X, Y y Z con términos relacionados. Por ejemplo: "No es el cuchillo más afilado del cajón", "No es el conejo más rápido del bosque", "No es el crayón más brillante de la caja".
El mensaje que se muestra aquí es un ejemplo de un mensaje de plantilla , donde le proporciona a ChatGPT un patrón general ( ) que incluye uno o más marcadores de posición ( , , y ) y le indica a ChatGPT cómo desea que reemplace cada marcador de posición."Not the Xest Y in the Z"XYZ

Sin embargo, antes de dedicar tiempo a pensar en ejemplos, normalmente es mejor probar el mensaje por sí solo, sin ningún ejemplo. ChatGPT se ha entrenado con una cantidad de texto tan grande que, a menudo, recibe incluso solicitudes poco claras la primera vez.

C.6 Invertir la dirección de la conversación
La mayoría de las conversaciones de ChatGPT son unidireccionales, en las que le pides al modelo que realice algunas tareas y el modelo (con suerte) completa la solicitud con éxito. Si no estás obteniendo resultados de calidad, probablemente se deba a que no le estás dando indicaciones a ChatGPT que sean lo suficientemente buenas para que pueda determinar lo que necesitas. ¿Sabes quién podría determinar las indicaciones correctas para usar? ¡ChatGPT! Es decir, en lugar de molestar constantemente a ChatGPT para que dé resultados, cambia las cosas y haz que ChatGPT te pida que proporciones la información que necesita el modelo.

A continuación se muestran algunos ejemplos:

Ask me whatever questions you require me to answer for you to create an "About" page for my website.

I want to create a web page card for a product. I would like you to ask me questions until you have enough information to generate the HTML and CSS code for the card.

I want you to help me write a short story. What information do you need from me? Ask me one question at a time, please.

Tenga en cuenta que, en cada caso, el mensaje incluye un resultado, una meta o un resultado específico. Esto es importante porque permite que ChatGPT genere las preguntas adecuadas.

C.7 Pídale a ChatGPT que refine sus indicaciones
Uno de los problemas que encontrarás al usar ChatGPT para generar código de página web es que, al no ser un desarrollador web, no puedes estar seguro de que tus indicaciones estén redactadas correctamente, de que estén haciendo la pregunta correcta o de que estén buscando algo que simplemente no es posible. Uno de los principales objetivos de este libro es brindarte suficientes indicaciones de ejemplo para que te familiarices con una amplia gama de lo que puedes solicitar de ChatGPT. Sin embargo, si te encuentras en un territorio nuevo, sigue adelante y solicita a ChatGPT lo mejor que puedas. Si los resultados no son los que deseas, pídele a ChatGPT que refine tu indicación por ti:

Can you suggest a better version of my previous prompt?

Is there anything missing from my previous prompt that would help you generate a better response?

In the following conversation, each time I ask you to generate some code, suggest a better version of my request and ask me if I'd prefer to use that version instead of the original.

También puede resultar útil proporcionar algo de contexto. Por ejemplo, si está intentando crear páginas web más accesibles, infórmeselo a ChatGPT para que sus indicaciones mejoradas puedan tener en cuenta ese objetivo.

C.8 Pídale a ChatGPT que cree los pasos que debe seguir
Si desea aprender a realizar alguna tarea compleja (por ejemplo, implementar su sitio web en un servidor web que no se incluye en este libro), puede pedirle a ChatGPT que le indique los pasos a seguir para realizar esa tarea. Para este tipo de solicitud, normalmente debe proporcionarle a ChatGPT los siguientes datos:

El objetivo o tarea que estás intentando lograr

¿Qué información relacionada con ese objetivo o tarea ya conoces o qué pasos ya has realizado?

¿Qué pasos se requieren para lograr el objetivo o la tarea?

Los detalles de cualquier paso que tenga que ver con información que aún no tienes o pasos que aún no has realizado

A continuación se muestra un ejemplo de mensaje que solicita a ChatGPT los pasos necesarios para publicar un sitio web en Vercel:

Quiero implementar mi sitio web en Vercel. Sé que necesito una cuenta de Vercel. He completado mi sitio web y todos los archivos están en la carpeta my_app de mi computadora. ¿Qué pasos se requieren para implementar mi sitio web en Vercel? Proporcione información detallada para cada paso que aún no haya completado.
Una idea similar es pedirle a ChatGPT que le diga cómo usar el código de la página web que genera para usted. Por ejemplo, si ChatGPT le proporciona un código pero no está seguro de dónde debe ir el código en el archivo HTML, pídale a ChatGPT que le diga dónde colocar el código en el archivo.

C.9 Solicitar a ChatGPT que proporcione y califique alternativas
Con todos los diseños, excepto los más simples, siempre hay múltiples formas de codificar una página web o un componente de página. Después de que ChatGPT proporcione su salida inicial, siempre puede hacer clic en Regenerar respuesta para obtener otro bloque de código, pero ¿cómo sabe qué respuesta es la que debe usar? ¡Pregúntele a ChatGPT, por supuesto! Es decir, puede pedirle a ChatGPT no solo que proporcione enfoques alternativos a lo que está tratando de lograr, sino también que califique esos enfoques. A continuación, se muestran algunos ejemplos:

I want to add a responsive dropdown menu to my web page. If there are multiple ways to accomplish that goal, list the three best methods.

List up to four ways that I can add a navigation bar to my web pages and tell me the pros and cons of each method.

Tell me the most popular ways to get form data emailed to me and compare and contrast each method.

Dependiendo del mensaje, es posible que prefieras usar Copilot, que puede usar una búsqueda web para ayudarlo a calificar cada alternativa.

C.10 En Microsoft Copilot, elija el estilo de conversación adecuado
Si utiliza Copilot, asegúrese de elegir un estilo de conversación que sea adecuado para su tarea:

Más creativo : este estilo es el mejor cuando quieres que Copilot estire sus alas, por así decirlo, y genere texto o ideas que sean menos convencionales y más imaginativas o inventivas. Esta versión de Copilot puede generar texto verdaderamente alocado, pero tiende a afirmar que su resultado fantasioso es un hecho, por lo que caveat emptor . Este estilo tiene un límite de entrada de 4000 caracteres.

Más preciso : este estilo es el mejor cuando se buscan resultados concisos, sencillos y directos. Este estilo tiene un límite de entrada de 4000 caracteres.

Más equilibrado : este es el estilo predeterminado y presenta a Copilot como un asistente amigable e informativo con resultados que se encuentran en el límite entre la inventiva y la sencillez. Este estilo tiene un límite de entrada de 2000 caracteres.

Al generar el código de una página web, normalmente es mejor probar el estilo Más preciso, que crea un código relativamente libre de adornos innecesarios.

C.11 Solución de problemas de errores de ChatGPT
No es un gran misterio cómo hace ChatGPT lo que hace, y ciertamente no es magia, pero es extremadamente impresionante, como aprenderá a lo largo de este libro. Sin embargo, esa impresionante característica no significa que ChatGPT sea infalible, ni mucho menos. Sí, afortunadamente, la mayoría de las veces la respuesta que recibe de ChatGPT es un código que no solo coincide con lo que solicitó, sino que también funciona correctamente (lo que significa que cuando muestra el código en un navegador web, ve el contenido y el estilo que solicitó). Sin embargo, es fundamental comprender que, aunque muchas personas llaman a ChatGPT "IA", ni siquiera es remotamente inteligente. Puede (y, lamentablemente, a menudo lo hace) generar código que es inexacto, erróneo o, a veces, directamente sin sentido. Y, lo que es peor, ChatGPT presentará este código "malo" con la misma confianza alegre con la que presenta su código "bueno". ChatGPT simplemente no sabe la diferencia entre los dos.

Entonces, eso te deja con un gran problema: dado que no sabes (y presumiblemente no quieres saber) cómo codificar páginas web, ¿cómo puedes "arreglar" los problemas de código que crea ChatGPT? Afortunadamente, no estás atascado, porque tienes algunas formas de hacer que ChatGPT ayude a solucionar sus propios problemas:

Pídale a ChatGPT que regenere su respuesta. A veces es necesario un segundo o incluso un tercer intento para que todo salga bien.

Modifique su mensaje. Si el mensaje original era simple, intente agregar más detalles; si el mensaje original era complejo, intente dividirlo en varios mensajes que sean simples y/o se centren en una sola tarea.

Pídale a ChatGPT que genere uno o más mensajes que considere adecuados al resultado que está buscando.

Dile a ChatGPT que el código que generó no funciona y pídele que solucione el problema. ¡Te sorprenderá la frecuencia con la que esto ayuda!

Mi esperanza es que no tengas que cambiar al modo de resolución de problemas con tanta frecuencia porque ChatGPT realmente es bueno para generar código de páginas web.



