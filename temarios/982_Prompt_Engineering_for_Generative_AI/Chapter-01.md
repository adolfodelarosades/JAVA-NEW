# Capítulo 1. Los cinco principios del Prompting

La ***Prompt engineering*** es el proceso de descubrir indicaciones que producen de manera confiable resultados útiles o deseados.

Un ***prompt*** es la entrada que usted proporciona, normalmente texto, al interactuar con un modelo de IA como **ChatGPT** o **Midjourney**. El mensaje sirve como un conjunto de instrucciones que el modelo utiliza para predecir la respuesta deseada: texto de modelos de lenguaje grandes (LLM) como [ChatGPT](https://chatgpt.com/), o imágenes de modelos de difusión como [Midjourney](https://www.midjourney.com/home).

A continuación se muestra un ejemplo sencillo de una entrada rápida para un generador de nombres de productos (inspirado en uno de los [ejemplos de OpenAI](https://platform.openai.com/examples/) ) y el resultado de ChatGPT.

![image](https://github.com/user-attachments/assets/3eeca345-c46d-4109-8339-f1dd7d444f80)

Input:

```text
Can I have a list of product names for a pair of shoes that
can fit any foot size?
```

Output:

```text
Certainly! Here's a list of product names for a pair of shoes
that can fit any foot size:

UniFit SoleStrides
FlexiSize All-Fit Shoes
OmniFit FootFlex
...
AnyStep AdaptiWalkers
FlexiRange UniversalSteps
PerfectGlide MultiFit Shoes
```

Entrada:

```text
¿Puedo tener una lista de nombres de productos para un par de zapatos que...
¿Puede adaptarse a cualquier tamaño de pie?
```

Salida:

```text
¡Por supuesto! Aquí tienes una lista de nombres de productos para un par de zapatos
que puede adaptarse a cualquier tamaño de pie:

Zapatillas SoleStrides de UniFit
Zapatos FlexiSize All-Fit
Flexibilidad de pies OmniFit
...
Andadores adaptables AnyStep
Escaleras universales FlexiRange
Zapatillas PerfectGlide MultiFit
```

Esta es una respuesta notable para un mensaje ingenuo, que parece mágico porque llegamos hasta aquí con muy poco esfuerzo. A medida que los modelos de última generación mejoran, la probabilidad de obtener resultados suficientemente buenos en el primer intento aumenta. Para cualquier interacción descartable con una IA, en la que no planee realizar la misma tarea nuevamente, el enfoque ingenuo es todo lo que necesita.

Sin embargo, si planeas poner este mensaje en producción, te beneficiarás si inviertes más trabajo para hacerlo bien. Los errores te cuestan dinero en términos de las tarifas que cobra OpenAI en función de la longitud del mensaje y la respuesta, así como el tiempo que se dedica a corregir los errores. Si estuvieras creando un generador de nombres de productos con miles de usuarios, hay algunos problemas obvios que querrías intentar solucionar:

* **Dirección vaga**
  
   No estás informando a la IA sobre qué estilo de ¿Qué nombre quieres o qué atributos debería tener? ¿Quieres una sola palabra o una concatenación? ¿Se pueden inventar las palabras o es importante que estén en inglés real? ¿Quieres que la IA emule a alguien a quien admires y que sea famoso por sus fantásticos nombres de productos?

* **Salida sin formato**
  
   Obtendrá una lista de nombres separados línea por línea, de longitud no especificada. Cuando ejecute este mensaje varias veces, verá que a veces aparece una lista numerada y, a menudo, tiene texto al principio, lo que dificulta su análisis programático.

* **Ejemplos faltantes**
  
   No le has dado ningún ejemplo a la IA. Cómo son los buenos nombres. Se completa automáticamente utilizando un promedio de sus datos de entrenamiento, es decir, todo Internet (con todo su sesgo inherente), pero ¿es eso lo que quieres? Lo ideal sería que le proporcionaras ejemplos de nombres exitosos, nombres comunes en una industria o incluso otros nombres que te gusten.

* **Evaluación limitada**
  
   No tienes una forma consistente o escalable de definir qué nombres son buenos o malos, por lo que hay que revisar manualmente cada respuesta. Si se puede implementar un sistema de calificación u otra forma de medición, se puede optimizar el mensaje para obtener mejores resultados e identificar cuántas veces falla.

* **Sin división de tareas**
  
   Estás pidiendo mucho. Un solo mensaje aquí: hay muchos factores que intervienen en el nombre del producto, y esta importante tarea se está subcontratando ingenuamente a la IA de una sola vez, sin especialización de tareas ni visibilidad de cómo maneja esta tarea por usted.

Abordar estos problemas es la base de los principios básicos que utilizamos a lo largo de este libro. Existen diferentes formas de pedirle a un modelo de IA que haga la misma tarea, e incluso pequeños cambios pueden hacer una gran diferencia. Los LLM funcionan prediciendo continuamente el siguiente token (aproximadamente tres cuartos de una palabra), a partir de lo que estaba en su indicación. Cada nuevo token se selecciona en función de su probabilidad de aparecer a continuación, con un elemento de aleatoriedad (controlado por el parámetro de temperatura). Como se muestra en la Figura 1-1 , la palabra shoes tenía una menor probabilidad de aparecer después del inicio del nombre AnyFit (0,88 %), mientras que una respuesta más predecible sería Athletic(72,35 %).

![image](https://github.com/user-attachments/assets/983f5e20-3fb0-4aea-9d8c-0829ca352302)

**Figura 1-1. Cómo se descompone la respuesta en tokens**

Los modelos LLM se entrenan básicamente con todo el texto de Internet y luego se perfeccionan para brindar respuestas útiles. Las indicaciones promedio arrojarán respuestas promedio, lo que hace que algunas personas se sientan decepcionadas cuando sus resultados no estén a la altura de las expectativas. Lo que se incluye en la indicación cambia la probabilidad de que se genere cada palabra, por lo que es muy importante para los resultados que se obtendrán. Estos modelos han visto lo mejor y lo peor de lo que los humanos han producido y son capaces de emular casi cualquier cosa si se sabe la forma correcta de preguntar. OpenAI cobra en función de la cantidad de [tokens utilizados](https://openai.com/chatgpt/pricing/) en la indicación y la respuesta, por lo que los ingenieros de indicaciones deben hacer que estos tokens cuenten optimizando las indicaciones en términos de costo, calidad y confiabilidad.

He aquí el mismo ejemplo con la aplicación de varias técnicas de prompt engineering. Pedimos nombres al estilo de Steve Jobs, indicamos que queremos una lista separada por comas y proporcionamos ejemplos de la tarea realizada correctamente.

![image](https://github.com/user-attachments/assets/8a60819a-d466-4f3c-b7f3-f71e810a6c74)

![image](https://github.com/user-attachments/assets/d7b539be-7eb2-42a8-bb2b-148c39016f21)

Input:

```text
Brainstorm a list of product names for a shoe that fits any
foot size, in the style of Steve Jobs.

Return the results as a comma-separated list, in this format:
Product description: A shoe that fits any foot size
Product names: [list of 3 product names]

## Examples
Product description: A refrigerator that dispenses beer
Product names: iBarFridge, iFridgeBeer, iDrinkBeerFridge

Product description: A watch that can tell accurate time in
space
Product names: iNaut, iSpace, iTime

Product description: A home milkshake maker
Product names: iShake, iSmoothie, iShake Mini
```

Output:

```text
Product description: A shoe that fits any foot size
Product names: iFitFoot, iPerfectFit, iShoeSize
```

Entrada:

```text
Piense en una lista de nombres de productos para un zapato que se adapte a cualquier persona.
Tamaño del pie, al estilo de Steve Jobs.

Devuelve los resultados como una lista separada por comas, en este formato:
Descripción del producto: Un zapato que se adapta a cualquier tamaño de pie.
Nombres de productos: [lista de 3 nombres de productos]

## Ejemplos
Descripción del producto: Un refrigerador que dispensa cerveza.
Nombres de productos: iBarFridge, iFridgeBeer, iDrinkBeerFridge

Descripción del producto: Un reloj que puede indicar la hora exacta en
espacio
Nombres de productos: iNaut, iSpace, iTime

Descripción del producto: Una batidora casera
Nombres de productos: iShake, iSmoothie, iShake Mini
```

Salida:

```text
Descripción del producto: Un zapato que se adapta a cualquier tamaño de pie.
Nombres de productos: iFitFoot, iPerfectFit, iShoeSize
```

Si bien ningún mensaje es perfecto, este mensaje está optimizado para ofrecer nombres de productos sólidos y confiables en el formato correcto. El usuario de su generador de nombres de productos puede elegir a alguien que no sea Steve Jobs para obtener los tipos de nombres que le gustan, puede cambiar el formato de respuesta si es necesario y el resultado de este mensaje puede convertirse en la entrada de otro. Por último, puede actualizar periódicamente los ejemplos que utiliza en el mensaje en función de los comentarios de los usuarios, lo que hace que su sistema sea más inteligente con el tiempo.

## Descripción general de los cinco principios del Prompting

El proceso para optimizar este mensaje sigue los cinco principios del Prompting, que analizaremos en detalle utilizando este ejemplo en el resto de este capítulo y recordaremos a lo largo del libro. Se corresponden exactamente con los cinco problemas que planteamos al analizar el prompt de texto ingenuo. Encontrará referencias a estos principios en el resto del libro para ayudarlo a conectar los puntos con la forma en que se utilizan en la práctica. Los cinco principiosLos principios del Prompting son los siguientes:

* **Dar dirección**

   Describir lo deseado estilo en detalle, o hacer referencia a una persona relevante

* **Especificar formato**
  
   Definir qué reglas seguir y la estructura requerida de la respuesta

* **Proporcionar ejemplos**

   Insertar un conjunto diverso de casos de prueba donde la tarea se realizó correctamente

* **Evaluar la calidad**

   Identificar errores y evaluar las respuestas, probando qué impulsa el rendimiento.

* **Dividir el trabajo**
  
   Dividir las tareas en múltiples pasos, encadenados entre sí para lograr objetivos complejos.

Estos principios no son consejos ni trucos efímeros, sino convenciones generalmente aceptadas que son útiles para trabajar con cualquier nivel de inteligencia, biológica o artificial. Estos principios son independientes del modelo y deberían funcionar para mejorar su mensaje sin importar qué modelo de texto o imagen generativo esté utilizando. Publicamos estos principios por primera vez en julio de 2022 en la publicación del blog "[Prompt Engineering: From Words to Art and Copy](https://www.saxifrage.xyz/post/prompt-engineering)" y han resistido la prueba del tiempo, incluida la correspondencia bastante cercana con la propia [Prompt Engineering Guide de OpenAI](https://platform.openai.com/docs/guides/prompt-engineering), que se publicó un año después. Es probable que cualquiera que trabaje de cerca con modelos de IA generativa converja en un conjunto similar de estrategias para resolver problemas comunes y, a lo largo de este libro, verá cientos de ejemplos demostrativos de cómo pueden ser útiles para mejorar sus mensajes.

Hemos proporcionado páginas únicas descargables para generación de texto e imágenes que puede utilizar como lista de verificación al aplicar estos principios. Estos se crearon para nuestro popular curso de [Udemy The Complete Prompt Engineering for AI Bootcamp](https://www.udemy.com/course/prompt-engineering-for-ai/?couponCode=KEEPLEARNING) (más de 70 000 estudiantes), que se basó en los mismos principios pero con diferentes material para este libro.

* [Generación de texto de una página](https://github.com/BrightPool/prompt-engineering-for-generative-ai-examples/blob/main/images/OnePager-Text.png)
* [Generación de imágenes en una sola página](https://github.com/BrightPool/prompt-engineering-for-generative-ai-examples/blob/main/images/OnePager-Images.png)

Para demostrar que estos principios se aplican igualmente bien a los modelos de imágenes de estímulo, usemos el siguiente ejemplo y expliquemos cómo aplicar cada uno de los cinco principios de estímulo a este escenario específico. Copie y pegue el mensaje de entrada completo en el Bot Midjourney en Discord, incluido el enlace a la imagen al principio, después de escribir `/imagine` para activar el cuadro de aviso que aparecerá (requiere una cuenta gratuita de [Discord](https://discord.com/) y una cuenta de paga de [Midjourney](https://www.midjourney.com/)).

![image](https://github.com/user-attachments/assets/d234e247-738c-4348-b331-4aa941984dff)


Input:

```text
https://s.mj.run/TKAsyhNiKmc stock photo of business meeting
of 4 people watching on white MacBook on top of glass-top
table, Panasonic, DC-GH5
```

Entrada:

```text
https://s.mj.run/TKAsyhNiKmc foto de archivo de una reunión de negocios
de 4 personas mirando desde una MacBook blanca sobre una cubierta de vidrio
Mesa Panasonic DC-GH5
```
La figura 1-2 muestra la salida.

![image](https://github.com/user-attachments/assets/0d4a5003-0e6d-4584-9539-8ce2ad682d79)

**Figura 1-2. Fotografía de archivo de una reunión de negocios**

Este mensaje aprovecha la capacidad de Midjourney para tomar una imagen base como ejemplo subiendo la imagen a Discord y luego copiando y pegando la URL en el mensaje ( https://s.mj.run/TKAsyhNiKmc ), para lo cual se utiliza la imagen libre de regalías de Unsplash ( Figura 1-3 ). Si te encuentras con un error con el mensaje, intenta subir la imagen tú mismo y revisa la [documentación de Midjourney](https://docs.midjourney.com/docs/image-prompts) para ver si hay cambios de formato.

![image](https://github.com/user-attachments/assets/89f900e5-0934-43ec-ab3f-e1438f37428f)

**Figura 1-3. Foto de Mimi Thian en Unsplash**

Comparemos este mensaje bien diseñado en comparación con lo que se obtiene de Midjourney si se pide ingenuamente una foto de archivo de la forma más simple posible, la figura 1-4 muestra un ejemplo de lo que se obtiene sin prompt engineering: una imagen con un estilo más oscuro y estilizado de una foto de archivo de lo que se esperaría normalmente.

![image](https://github.com/user-attachments/assets/0e8afc54-40b3-41b3-8c59-47a91073f126)

Input:

```text
people in a business meeting
```

Entrada:

```text
personas en una reunión de negocios
```

La figura 1-4 muestra la salida.

Aunque se trata de un problema menos destacado a partir de la versión 5 de Midjourney, los mecanismos de retroalimentación de la comunidad (cuando los usuarios seleccionan una imagen para cambiar su tamaño a una resolución más alta, esa elección puede utilizarse para entrenar el modelo) han sesgado el modelo hacia una estética de fantasía, que es menos adecuada para el caso de uso de fotografías de archivo. Los primeros usuarios de Midjourney provenían del mundo del arte digital y naturalmente se inclinaron por los estilos de fantasía y ciencia ficción, lo que se puede reflejar en los resultados del modelo incluso cuando esta estética no es adecuada.

![image](https://github.com/user-attachments/assets/9fba0d6f-47a9-4b21-a5eb-78be72045914)

**Figura 1-4. Personas en una reunión de negocios**

A lo largo de este libro se utilizarán los ejemplos: ser compatible con ChatGPT Plus (GPT-4) como modelo de texto y Midjourney v6 o Stable Diffusion XL como modelo de imagen, aunque especificaremos si es importante. Estos modelos básicos son el estado actual de la técnica y son buenos para una amplia gama de tareas. Los principios están pensados ​​para que sean a prueba de futuro tanto como sea posible, por lo que si estás leyendo este libro cuando GPT-5, Midjourney v7 o Stable Diffusion XXL estén disponibles, o si estás usando otro proveedor como Google, todo lo que aprendas aquí debería resultarte útil.

 
## 1. Dar dirección

Uno de los problemas con el texto prompt el problema que se mencionó anteriormente fue que no se le estaba informando a la IA sobre qué tipos de nombres de productos quería. Hasta cierto punto, ponerle nombre a un producto es una tarea subjetiva y sin darle a la IA una idea de qué nombres le gustan, tiene pocas probabilidades de acertar.

Por cierto, un humano también tendría dificultades para completar esta tarea sin un buen *resumen*, por lo que las agencias creativas y de branding requieren una sesión informativa detallada sobre cualquier tarea de sus clientes.

**CONSEJO**

Si bien no es un mapeo perfecto, puede ser útil imaginar qué contexto podría necesitar un humano para esta tarea e intentar incluirlo en la indicación.

En el mensaje de ejemplo dimos instrucciones mediante el uso de *role-playing - juegos de rol*, en ese caso emulando el estilo de Steve Jobs, quien era famoso por nombrar productos de manera icónica. Si cambia este aspecto del mensaje por el de otra persona que sea famosa en los datos de entrenamiento (además de hacer coincidir los ejemplos con el estilo correcto), obtendrá resultados radicalmente diferentes.

<img width="837" alt="image" src="https://github.com/user-attachments/assets/a57c19a8-2971-40a9-9b14-c57ea4a3c5db">

<img width="831" alt="image" src="https://github.com/user-attachments/assets/d8e62680-df39-4aa2-94f4-4a20a27f0ad7">

Input:

```text
Brainstorm a list of product names for a shoe that fits any
foot size, in the style of Elon Musk.

Return the results as a comma-separated list, in this format:
Product description: A shoe that fits any foot size
Product names: [list of 3 product names]

## Examples
Product description: A refrigerator that dispenses beer
Product names: Teslacool, FridgeX, Neuradrink

Product description: A watch that can tell accurate time in
space
Product names: WatchX, iSpace, The Watch Company

Product description: A home milkshake maker
Product names: ShakeX, The Milkshake Company, HyperShake
```

Output:

```text
ShoeX, MarsFit, The Shoe Company
```

Entrada:

```text
Piense en una lista de nombres de productos para un zapato que se adapte a cualquier persona.
Tamaño del pie, al estilo de Elon Musk.

Devuelve los resultados como una lista separada por comas, en este formato:
Descripción del producto: Un zapato que se adapta a cualquier tamaño de pie.
Nombres de productos: [lista de 3 nombres de productos]

## Ejemplos
Descripción del producto: Un refrigerador que dispensa cerveza.
Nombres de productos: Teslacool, FridgeX, Neuradrink

Descripción del producto: Un reloj que puede indicar la hora exacta en
espacio
Nombres de productos: WatchX, iSpace, The Watch Company

Descripción del producto: Una batidora casera
Nombres de productos: ShakeX, The Milkshake Company, HyperShake
```

Salida:

```Text
ShoeX, MarsFit, la empresa de calzado
```

También existen algunas reglas o mejores prácticas que debes seguir. Sería bueno seguirlo, lo que podría incluirse en el mensaje como contexto para guiar a la IA hacia un nombre que funcione. Esta técnica a veces se conoce como *prewarming - precalentamiento* o *internal retrieval - recuperación interna*, y es simple pero efectiva ( [Liu et al., 2021](https://arxiv.org/abs/2110.08387) ). Comenzar la conversación pidiendo consejos sobre las mejores prácticas y luego pedirle que siga sus propios consejos puede ayudar mucho. En efecto, lo estás usando para generar su propia dirección.

<img width="835" alt="image" src="https://github.com/user-attachments/assets/ba5a5ac1-0bac-41e4-b30e-a418e929570c">

<img width="625" alt="image" src="https://github.com/user-attachments/assets/f6799b23-184d-4299-8f81-6b231b6c37ff">

Input:

```text
Please give me 5 tips for naming products based on expert
industry advice.
```

Output:

```text
Certainly! Naming a product is crucial as it often gives the
first impression to potential customers. Here are five expert
tips to guide you in naming products:

1. **Simplicity & Memorability**: Opt for names that are
short, easy to spell, and memorable. Long, complicated names
can be difficult for customers to recall. Remember, the
easier the name is to remember, the more likely it is that
consumers will think of your product when making a purchase
decision.

...

5. **Positive Connotations**: Names that evoke positive
emotions or imagery can create a favorable perception of
your product. Avoid names that have negative or
controversial associations in any of the primary languages
or cultures where you intend to do business. It's often
worthwhile to conduct linguistic checks and market testing
to ensure there aren't unintended meanings.

Lastly, once you've shortlisted a few names, it's a good
idea to run them by diverse focus groups or conduct surveys
to gauge reactions. Also, ensure that the name you choose is
available for trademarking and doesn't infringe on existing
trademarks.
```

Entrada:

```text
Por favor, denme 5 consejos para nombrar productos según los expertos.
Asesoramiento industrial.
```

Salida:

```text
¡Por supuesto! Ponerle nombre a un producto es crucial, ya que a menudo le da el nombre que necesita.
La primera impresión que dan a los clientes potenciales. Aquí cinco expertos
Consejos para guiarte en la denominación de productos:

1. **Simplicidad y memorabilidad**: Opte por nombres que sean
Nombres cortos, fáciles de escribir y memorables. Nombres largos y complicados.
Puede resultar difícil para los clientes recordarlo. Recuerde, el
Cuanto más fácil sea recordar el nombre, más probable es que...
Los consumidores pensarán en su producto al realizar una compra.
decisión.

...

5. **Connotaciones positivas**: Nombres que evocan positividad.
Las emociones o las imágenes pueden crear una percepción favorable de
su producto. Evite nombres que tengan un significado negativo o
asociaciones controvertidas en cualquiera de los idiomas principales
o culturas en las que pretendes hacer negocios. A menudo es
Vale la pena realizar comprobaciones lingüísticas y pruebas de mercado
para garantizar que no haya significados no deseados.

Por último, una vez que hayas seleccionado algunos nombres, es una buena idea...
idea de ejecutarlos mediante diversos grupos de enfoque o realizar encuestas
para medir las reacciones. Además, asegúrate de que el nombre que elijas sea
Disponible para registro de marca y no infringe ninguna marca existente.
marcas comerciales.
```

Luego, dentro de la misma ventana de chat, donde el modelo tiene el contexto del consejo pasado que dio, le pides tu mensaje inicial sobre la tarea que querías completar.

<img width="839" alt="image" src="https://github.com/user-attachments/assets/0fbef287-4ca0-4e35-afaf-4ccf6973f497">

<img width="673" alt="image" src="https://github.com/user-attachments/assets/2d2f8135-b5da-418c-8ded-9a910f06a2a9">

Input:

```text
Using this advice, can I have a list of product names for a
pair of shoes that can fit any foot size?
```

Output:

```text
Certainly! Based on the criteria given:

1. **Simplicity & Memorability**
2. **Relevance & Descriptiveness**
3. **Differentiation & Uniqueness**
4. **Adaptable & Scalable**
5. **Positive Connotations**

Here's a list of potential product names for shoes that can
fit any foot size:

1. **FitAll Walkers**: A simple and memorable name that
instantly suggests a universal fit.

...

10. **TrueFit Universals**: Emphasizing genuine comfort and
fit for all.

Before finalizing any name, remember to check for trademarks
to ensure there's no conflict with existing products or
brands.
```

Entrada:

```text
Con este consejo, ¿puedo tener una lista de nombres de productos para un
¿Un par de zapatos que se adapten a cualquier tamaño de pie?
```

Salida:

```text
¡Por supuesto! Según los criterios establecidos:

1. **Simplicidad y memorabilidad**
2. **Relevancia y carácter descriptivo**
3. **Diferenciación y singularidad**
4. **Adaptable y escalable**
5. **Connotaciones positivas**

Aquí hay una lista de posibles nombres de productos para zapatos que pueden
Se adapta a cualquier tamaño de pie:

1. **FitAll Walkers**: Un nombre simple y memorable que
Sugiere instantáneamente un ajuste universal.

...

10. **TrueFit Universals**: enfatizando la comodidad genuina y
Apto para todos.

Antes de decidir cualquier nombre, recuerde comprobar las marcas comerciales.
para garantizar que no haya ningún conflicto con productos existentes o
marcas.
```

Según nuestra experiencia, otra estrategia fructífera es tomar los mejores consejos disponibles para la tarea que desea realizar e insertar ese contexto en la solicitud. Por ejemplo, puede tomar las 5 reglas de oro de Brandwatch para nombrar un producto u otro recurso externo confiable que encuentre e insertarlo como contexto en la solicitud. Esto aumentará significativamente la longitud de la solicitud, lo que cuesta más dinero (cuando se usa la API como desarrollador), pero puede valer la pena si la calidad de la respuesta mejora.

<img width="765" alt="image" src="https://github.com/user-attachments/assets/45c789f5-1a17-4bd3-9004-39be515a4cc0">

<img width="756" alt="image" src="https://github.com/user-attachments/assets/bc0b6e91-2f7a-4f11-be2a-2dca59dc86e4">

Input:

```text
Can I have a list of product names for a pair of shoes that
can fit any foot size? Please follow the five rules below:

1. It should be readable and writable.
If your product name is hard to pronounce, people won’t talk about it,
and if they can’t write it down (and spell it correctly!)
when they hear it, how do you expect them to Google it?

Keep it simple and don’t go with any wacky spellings just for the sake of it.

...

5. It should evoke an emotion, feeling, or idea.
Your product name should tie back into what your product is, what the
feeling you want people to have when experiencing your product is, and/or
what idea are you trying to get across.

It should be emotive and inspiring.
```

Output:

```text
1. FlexFit Footwear
2. OmniSize Sneakers
3. AdaptStride Shoes
...
18. OmniComfort Kicks
19. FlexSize Footwear
20. Boundless Soles
```

Entrada:

```text
¿Puedo tener una lista de nombres de productos para un par de zapatos que...
¿Se adapta a cualquier tamaño de pie? Siga las cinco reglas que se indican a continuación:

1. Debe ser legible y escribible.
Si el nombre de su producto es difícil de pronunciar, la gente no hablará de él.
y si no pueden escribirlo (¡y deletrearlo correctamente!)
Cuando lo escuchan, ¿cómo esperas que lo busquen en Google?

Mantenlo simple y no uses ortografías raras solo por hacerlo.

...

5. Debe evocar una emoción, sentimiento o idea.
El nombre de su producto debe estar relacionado con lo que es su producto, lo que...
La sensación que desea que la gente tenga cuando experimente su producto es, y/o
¿Qué idea estás intentando transmitir?

Debe ser emotivo e inspirador.
```

Salida:

```text
1. Calzado FlexFit
2. Zapatillas OmniSize
3. Zapatillas AdaptStride
...
18. Zapatillas OmniComfort
19. Calzado FlexSize
20. Suelas sin límites
```

Hay otras innumerables formas de proporcionar una dirección. En el ejemplo de generación de imágenes, la dirección se proporcionó especificando que la reunión de negocios se lleva a cabo alrededor de una mesa con tapa de vidrio. Si cambia solo ese detalle, puede obtener una imagen completamente diferente, como se detalla en la Figura 1-5 .

Input:

```text
https://s.mj.run/TKAsyhNiKmc stock photo of business meeting
of four people gathered around a campfire outdoors in the
woods, Panasonic, DC-GH5
```

Entrada:

```text
https://s.mj.run/TKAsyhNiKmc foto de archivo de una reunión de negocios
de cuatro personas reunidas alrededor de una fogata al aire libre en el
Bosques, Panasonic, DC-GH5
```

La figura 1-5 muestra la salida.

<img width="821" alt="image" src="https://github.com/user-attachments/assets/02155de3-735f-43ce-b817-aaa5d93cf9cb">

**Figura 1-5. Fotografía de archivo de una reunión de negocios en el bosque**

El juego de roles también es importante para generación de imágenes. Una de las formas más eficaces de orientar a Midjourney es proporcionar el nombre de un artista o estilo artístico que emular. Un artista que aparece mucho en el mundo del arte de la IA es Van Gogh, conocido por sus pinceladas audaces y dramáticas y su uso vívido de los colores. Observa lo que sucede cuando incluyes su nombre en la indicación, como se muestra en la Figura 1-6 .

<img width="837" alt="image" src="https://github.com/user-attachments/assets/cd45e669-8e67-49ed-9914-cf95ce819816">

Input:

```text
people in a business meeting, by Van Gogh
```

Entrada:

```text
Personas en una reunión de negocios, de Van Gogh
```

La figura 1-6 muestra la salida.

<img width="833" alt="image" src="https://github.com/user-attachments/assets/4d47c755-7ccc-411b-b63b-946b21f88817">

**Figura 1-6. Personas en una reunión de negocios, de Van Gogh**

Para que funcione ese último mensaje, debes: Elimina muchas de las otras direcciones. Por ejemplo, si eliminas la imagen base y las palabras "*stock photo - foto de archivo*" y la cámara Panasonic, DC-GH5, podrás incorporar el estilo de Van Gogh. El problema con el que te puedes encontrar es que, a menudo, si se aplica demasiada dirección, el modelo puede llegar rápidamente a una combinación conflictiva que no puede resolver. Si tu indicación es demasiado específica, es posible que no haya suficientes muestras en los datos de entrenamiento para generar una imagen que sea coherente con todos tus criterios. En casos como estos, debes elegir qué elemento es más importante (en este caso, Van Gogh) y ceñirte a eso.

La dirección es uno de los principios más utilizados y más amplios. Puede adoptar la forma de simplemente usar las palabras descriptivas adecuadas para aclarar su intención o canalizar las personalidades de celebridades empresariales relevantes. Si bien demasiada dirección puede limitar la creatividad de la empresa, modelo, muy poca dirección es el problema más común.

## 2. Especificar formato

Los modelos de IA son traductores universales. No solo ¿Eso significa traducir del francés al inglés, o del urdu al klingon, pero también entre estructuras de datos como JSON a YAML ? o lenguaje natural a código Python. Estos modelos son capaces de devolver una respuesta en casi cualquier formato, por lo que una parte importante de la prompt engineering es encontrar formas de especificar en qué formato desea que esté la respuesta.

De vez en cuando, verás que el mismo mensaje devuelve un formato diferente, por ejemplo, una lista numerada en lugar de separada por comas. Esto no es un gran problema la mayor parte del tiempo, porque la mayoría de los mensajes son únicos y se escriben en ChatGPT o Midjourney. Sin embargo, cuando incorporas herramientas de IA en software de producción, los cambios ocasionales en el formato pueden causar todo tipo de errores.

Al igual que cuando trabajas con un humano, puedes evitar el desperdicio de esfuerzo si especificas de antemano el formato en el que esperas que esté la respuesta. Para los modelos de generación de texto, a menudo puede ser útil generar JSON en lugar de una simple lista ordenada, ya que es el formato universal para las respuestas de API, lo que puede simplificar el análisis y la detección de errores, así como su uso para representar el HTML del frontend de una aplicación. YAML también es otra opción popular porque impone una estructura analizable y, al mismo tiempo, es simple y legible para humanos.

En el mensaje original, diste instrucciones a través de los dos ejemplos proporcionados y los dos puntos al final del mensaje indicaban que debía completar la lista en línea. Para cambiar el formato a JSON, debes actualizar ambos y dejar el JSON sin completar, para que GPT-4 sepa que debe completarlo.

<img width="839" alt="image" src="https://github.com/user-attachments/assets/2998210c-4563-44e7-87d4-500aaf364cdb">

<img width="836" alt="image" src="https://github.com/user-attachments/assets/14baffc3-5d0b-4529-bfd8-023657472b45">

Input:

```text
Return a comma-separated list of product names in JSON for
"A pair of shoes that can fit any foot size.".
Return only JSON.

Examples:
[{
		"Product description": "A home milkshake maker.",
		"Product names": ["HomeShaker", "Fit Shaker",
		"QuickShake", "Shake Maker"]
	},
	{
		"Product description": "A watch that can tell
		accurate time in space.",
		"Product names": ["AstroTime", "SpaceGuard",
		"Orbit-Accurate", "EliptoTime"]}
]
```

Output:

```text
[
	{
		"Product description": "A pair of shoes that can \
		fit any foot size.",
		"Product names": ["FlexFit Footwear", "OneSize Step",
		"Adapt-a-Shoe", "Universal Walker"]
	}
]
```

Entrada:

```text
Devuelve una lista separada por comas de nombres de productos en JSON para
"Un par de zapatos que se adaptan a cualquier tamaño de pie".
Devuelve sólo JSON.

Ejemplos:
[{
		"Descripción del producto": "Máquina para hacer batidos caseros.",
		"Nombres de productos": ["HomeShaker", "Fit Shaker",
		"QuickShake", "Fabricante de batidos"]
	},
	{
		"Descripción del producto": "Un reloj que puede decir
		tiempo exacto en el espacio.",
		"Nombres de productos": ["AstroTime", "SpaceGuard",
		"Precisión de órbita", "EliptoTime"]}
]
```

Salida:

```text
[
	{
		"Descripción del producto": "Un par de zapatos que pueden \
		"Se adapta a cualquier tamaño de pie.",
		"Nombres de productos": ["Calzado FlexFit", "OneSize Step",
		"Adapta-un-zapato", "Andador universal"]
	}
]
```

El resultado que obtenemos es el JSON completo que contiene los nombres de los productos. Luego, se puede analizar y utilizar de forma programática en una aplicación o en un script local. Desde este punto, también es fácil comprobar si hay un error en el formato utilizando un analizador JSON como el de Python’s standard json library, ya que el JSON dañado generará un error de análisis, que puede actuar como un disparador para volver a intentar el mensaje o investigar antes de continuar. Si aún no obtiene el formato correcto, puede ser útil especificar al principio o al final del mensaje, o en el mensaje del sistema si usa un modelo de chat: `You are a helpful assistant that only responds in JSON`, o especificar la [JSON output](https://community.openai.com/t/openai-api-guide-using-json-mode/557265) en los parámetros del modelo cuando esté disponible (esto se llama gramáticas con [Llama models](https://til.simonwillison.net/llms/llama-cpp-python-grammars) ).

**CONSEJO**

Para familiarizarse con JSON si no está familiarizado, W3Schools tiene [una buena introducción](https://www.w3schools.com/js/js_json_intro.asp).

Para la generación de imágenes en el caso de los modelos, el formato es muy importante, ya que las posibilidades de modificar una imagen son casi infinitas. Van desde formatos obvios como `stock photo`, `illustration`, y `oil painting`, hasta formatos más inusuales como `xdashcam footage`, `ice sculpture`, o in `Minecraft`(consulte la Figura 1-7 ).

<img width="831" alt="image" src="https://github.com/user-attachments/assets/32a56996-a8a2-4891-93d1-8f584cc93fc4">


Input:

```text
business meeting of four people watching on MacBook on top of
table, in Minecraft
```

Entrada:

```text
Reunión de negocios de cuatro personas que miran en MacBook encima de
mesa, en minecraft
```

La figura 1-7 muestra la salida.

<img width="773" alt="image" src="https://github.com/user-attachments/assets/ac80c2a3-2789-4e25-8c9e-4978de5b62db">

**Figura 1-7. Reunión de negocios en Minecraft**

Al configurar un formato, a menudo es necesario eliminar otros aspectos del mensaje que podrían entrar en conflicto con el formato especificado. Por ejemplo, si proporciona una imagen base de una foto de archivo, el resultado es una combinación de la foto de archivo y el formato que desea. Hasta cierto punto, los modelos de generación de imágenes pueden generalizarse a nuevos escenarios y combinaciones que no han visto antes en su conjunto de entrenamiento, pero en nuestra experiencia, cuantas más capas de elementos no relacionados, más probabilidades hay de obtener una imagen inadecuada.

A menudo hay cierta superposición entre el primer y el segundo principio son dar dirección y especificar el formato. El último trata de definir el tipo de resultado que desea, por ejemplo, el formato JSON o el formato de una foto de archivo. El primero trata del estilo de respuesta que desea, independientemente del formato, por ejemplo, nombres de productos al estilo de Steve Jobs o una imagen de una reunión de negocios al estilo de Van Gogh. Cuando hay conflictos entre el estilo y el formato, a menudo es mejor resolverlos descartando cualquier elemento que sea menos importante para el resultado final.

## 3. Proporcione ejemplos

El mensaje original no le dio ningún ejemplo a la IA de cómo crees que se ven los buenos nombres. Por lo tanto, la respuesta se aproxima a un promedio de Internet, y puedes hacerlo mejor que eso. Los investigadores llamarían a un mensaje sin ejemplos *zero-shot*, y es siempre es una sorpresa agradable cuando la IA puede incluso hacer una tarea sin ningún tipo de preparación: es una señal de que el modelo es potente. Si no proporcionas ningún ejemplo, estás pidiendo mucho sin dar mucho a cambio. Incluso proporcionar un solo ejemplo ( *one-shot* ) ayuda considerablemente, y es la norma entre los investigadores probar cómo funcionan los modelos con múltiples ejemplos ( *few-shot* ). Una de esas investigaciones es el famoso artículo de GPT-3 “[Language Models are Few-Shot Learners](https://arxiv.org/abs/2005.14165)” (Los modelos de lenguaje son aprendices con pocos ejemplos) , cuyos resultados se ilustran en la Figura 1-8 , que muestra que agregar un ejemplo junto con una indicación puede mejorar la precisión en algunas tareas del 10% a casi el 50%.

<img width="829" alt="image" src="https://github.com/user-attachments/assets/beeb6f2d-648e-4195-9e55-8592d90519fb">

**Figura 1-8. Número de ejemplos en contexto**

Cuando se le da una sesión informativa a un colega o se capacita a un empleado junior sobre una nueva tarea, es natural que se incluyan ejemplos de ocasiones en las que esa tarea se había realizado bien anteriormente. Trabajar con IA es lo mismo, y la fuerza de una indicación a menudo se reduce a los ejemplos utilizados. Proporcionar ejemplos a veces puede ser más fácil que tratar de explicar exactamente qué es lo que te gusta de esos ejemplos, por lo que esta técnica es más eficaz cuando no eres un experto en el área temática de la tarea que estás intentando completar. La cantidad de texto que puedes incluir en una indicación es limitada (al momento de escribir esto, alrededor de 6000 caracteres en Midjourney y aproximadamente 32 000 caracteres para la versión gratuita de ChatGPT), por lo que gran parte del trabajo de prompt engineering implica seleccionar e insertar ejemplos diversos e instructivos.

Existe un equilibrio entre la fiabilidad y la creatividad: si superas los tres o cinco ejemplos, tus resultados serán más fiables, aunque sacrificarás la creatividad. Cuantos más ejemplos proporciones y menor sea la diversidad entre ellos, más limitada será la respuesta para que coincida con tus ejemplos. Si cambias todos los ejemplos por nombres de animales en la pregunta anterior, tendrás un fuerte efecto en la respuesta, que devolverá de forma fiable solo nombres que incluyan animales.

<img width="846" alt="image" src="https://github.com/user-attachments/assets/9760150c-149d-4026-8551-ddae53c94b72">

<img width="836" alt="image" src="https://github.com/user-attachments/assets/f86ce0ab-fd70-4648-8835-66fe1a6b4042">

Input:

```text
Brainstorm a list of product names for a shoe that fits any
foot size.

Return the results as a comma-separated list, in this format:
Product description: A shoe that fits any foot size
Product names: [list of 3 product names]

## Examples:
Product description: A home milkshake maker.
Product names: Fast Panda, Healthy Bear, Compact Koala

Product description: A watch that can tell accurate time in
space.
Product names: AstroLamb, Space Bear, Eagle Orbit

Product description: A refrigerator that dispenses beer
Product names: BearFridge, Cool Cat, PenguinBox
```

Output:

```text
Product description: A shoe that fits any foot size
Product names: FlexiFox, ChameleonStep, PandaPaws
```

Entrada:

```text
Piense en una lista de nombres de productos para un zapato que se adapte a cualquier persona.
Tamaño del pie.

Devuelve los resultados como una lista separada por comas, en este formato:
Descripción del producto: Un zapato que se adapta a cualquier tamaño de pie.
Nombres de productos: [lista de 3 nombres de productos]

## Ejemplos:
Descripción del producto: Una máquina para hacer batidos caseros.
Nombres de productos: Fast Panda, Healthy Bear, Compact Koala

Descripción del producto: Un reloj que puede indicar la hora exacta en
espacio.
Nombres de productos: AstroLamb, Space Bear, Eagle Orbit

Descripción del producto: Un refrigerador que dispensa cerveza.
Nombres de productos: BearFridge, Cool Cat, PenguinBox
```

Salida:

```text
Descripción del producto: Un zapato que se adapta a cualquier tamaño de pie.
Nombres de productos: FlexiFox, ChameleonStep, PandaPaws
```

Por supuesto, esto corre el riesgo de no poder devolver un nombre mucho mejor que no se ajuste al espacio limitado que queda para que la IA juegue. La falta de diversidad y variación en los ejemplos también es un problema a la hora de manejar casos extremos o escenarios poco comunes. Incluir de uno a tres ejemplos es fácil y casi siempre tiene un efecto positivo, pero por encima de esa cantidad se vuelve esencial experimentar con la cantidad de ejemplos que se incluyen, así como con la similitud entre ellos. Hay algunas pruebas ( [Hsieh et al., 2023](https://arxiv.org/pdf/2308.00675) ) de que la dirección funciona mejor que proporcionar ejemplos, y normalmente no es sencillo recopilar buenos ejemplos, por lo que suele ser prudente intentar primero el principio de dar dirección.

En el espacio de generación de imágenes, proporcionar ejemplos generalmente se presenta en forma de una imagen base en el mensaje de solicitud, llamada ***img2img*** en la comunidad de código abierto [Stable Diffusion](https://stability.ai/news/stable-diffusion-public-release). Según el modelo de generación de imágenes que se utilice, estas imágenes se pueden utilizar como punto de partida para generar el modelo, lo que afecta en gran medida los resultados. Puede mantener todo lo relacionado con el mensaje de solicitud igual, pero cambiar la imagen base proporcionada para obtener un efecto radicalmente diferente, como en la Figura 1-9.

<img width="835" alt="image" src="https://github.com/user-attachments/assets/7d727af7-8825-4343-84a8-c462997d80a4">

Input:

```text
stock photo of business meeting of 4 people watching on
white MacBook on top of glass-top table, Panasonic, DC-GH5
```

Entrada:

```text
Fotografía de stock de una reunión de negocios de 4 personas mirando
MacBook blanco sobre una mesa de cristal, Panasonic, DC-GH5
```

La figura 1-9 muestra la salida.

<img width="899" alt="image" src="https://github.com/user-attachments/assets/c360fbbb-561f-4925-956f-c2f32441881c">

**Figura 1-9. Fotografía de archivo de una reunión de negocios de cuatro personas**

En este caso, al sustituir la imagen que se muestra en la Figura 1-10, también de **Unsplash**, se puede ver cómo el modelo fue llevado en una dirección diferente y ahora incorpora pizarrones y notas adhesivas.

**PRECAUCIÓN**

Estos ejemplos demuestran las capacidades de los modelos de generación de imágenes, pero debemos tener cuidado al cargar imágenes base para usarlas en los mensajes. Verifique la licencia de la imagen que planea cargar y usar en su mensaje como imagen base y evite usar imágenes con derechos de autor claros. Si lo hace, puede meterse en problemas legales y va en contra de los términos de uso. Servicio para todos los principales proveedores de modelos de generación de imágenes.

<img width="814" alt="image" src="https://github.com/user-attachments/assets/485a9346-c5cb-49b3-8c6d-27492531fbcd">

**Figura 1-10. Foto de Jason Goodman en Unsplash**

## 4. Evaluar la calidad

Hasta el momento, no ha habido un circuito de retroalimentación para que juzgue la calidad de sus respuestas, además del ensayo y error básico de ejecutar el mensaje y ver los resultados, conocido como mensajes a ciegas - [https://oreil.ly/42rSz](https://mitchellh.com/writing/prompt-engineering-vs-blind-prompting). Esto está bien cuando sus mensajes se usan temporalmente para una sola tarea y rara vez se revisan. Sin embargo, cuando reutiliza el mismo mensaje varias veces o crea una aplicación de producción que depende de un mensaje, debe ser más riguroso con la medición de los resultados.

Hay varias formas de evaluar el rendimiento y esto depende en gran medida de las tareas que se esperan lograr. Cuando se lanza un nuevo modelo de IA, el enfoque tiende a estar en qué tan bien se desempeñó el modelo en las evaluaciones *evals*, un conjunto estandarizado de preguntas con respuestas predefinidas o criterios de calificación que se utilizan para probar el desempeño en los distintos modelos. Los distintos modelos funcionan de manera diferente en distintos tipos de tareas, y no hay garantía de que una indicación que funcionó anteriormente se traduzca bien a un nuevo modelo. OpenAI ha hecho que su [evals framework](https://github.com/openai/evals) el desempeño de los LLM sea de código abierto y alienta a otros a contribuir con plantillas de evaluación adicionales.

Además de las evaluaciones académicas estándar, también hay pruebas más destacadas como la [GPT-4 para aprobar el examen de abogacía](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4389233). La evaluación es difícil para las tareas más subjetivas y puede llevar mucho tiempo o resultar prohibitivamente costosa para equipos más pequeños. En algunos casos, los investigadores han recurrido al uso de modelos más avanzados como la GPT-4 para evaluar las respuestas de modelos menos sofisticados, como se hizo con el lanzamiento de [Vicuna-13B](https://lmsys.org/blog/2023-03-30-vicuna/), un modelo perfeccionado basado en el modelo de código abierto Llama de Meta (consulte la Figura 1-11 ).

<img width="816" alt="image" src="https://github.com/user-attachments/assets/4d0b285f-56a3-4262-8bea-f7b0d964f9b6">

**Figura 1-11. Evaluaciones Vicuna GPT-4**

Se necesitan técnicas de evaluación más rigurosas al escribir artículos científicos o calificar una nueva versión de modelo de base, pero a menudo solo necesitará ir un paso más allá del ensayo y error básico. Es posible que descubra que un simple sistema de calificación de aprobación/desaprobación implementado en un Jupyter Notebook puede ser suficiente para agregar algo de rigor a la optimización de las indicaciones, sin agregar demasiados recursos. Una prueba común es ver si proporcionar ejemplos vale la pena el costo adicional en términos de extensión de la indicación, o si puede salirse con la suya sin proporcionar ejemplos en la indicación. El primer paso es obtener respuestas para múltiples ejecuciones de cada indicación y almacenarlas en una hoja de cálculo, lo que haremos después de configurar nuestro entorno.

Puedes instalar OpenAI Python package con `pip install openai`. Si tiene problemas de compatibilidad con este paquete, cree un entorno virtual e instale nuestro [requirements.txt](https://github.com/BrightPool/prompt-engineering-for-generative-ai-examples/blob/main/requirements.txt) (las instrucciones se encuentran en el prólogo).

Para utilizar la API, deberás: Necesita [crear una cuenta OpenAI](https://auth.openai.com/authorize?audience=https%3A%2F%2Fapi.openai.com%2Fv1&auth0Client=eyJuYW1lIjoiYXV0aDAtc3BhLWpzIiwidmVyc2lvbiI6IjEuMjEuMCJ9&client_id=DRivsnm2Mu42T3KOpqdtwB3NYviHYzwD&device_id=7238f877-21fa-4a66-855f-b0a1d86e9bdd&issuer=https%3A%2F%2Fauth.openai.com&max_age=0&nonce=MH52ZzVuVDZublZKb3dRNFZETjRicVdDaDN1S1p%2BZWlYdEM0WjVfbzhMcw%3D%3D&redirect_uri=https%3A%2F%2Fplatform.openai.com%2Fauth%2Fcallback&response_mode=query&response_type=code&scope=openid+profile+email+offline_access&screen_hint=signup&state=N0szU1ZreVNrM0txR0locmxaTzVkSDRvdFozaHNIM01JalhKLm9FZFdsTg%3D%3D&flow=treatment) y luego [navegar aquí para obtener su clave API](https://platform.openai.com/api-keys).

**ADVERTENCIA**

No se recomienda codificar las claves API en los scripts por razones de seguridad. En su lugar, utilice variables de entorno o archivos de configuración para administrar las claves.

Una vez que tenga una clave API, es fundamental asignarla como una variable de entorno ejecutando el siguiente comando y reemplazándola `api_key` con el valor de su clave API real:

<img width="829" alt="image" src="https://github.com/user-attachments/assets/cdf98208-12a1-411a-bebd-0f22d921955e">

```text
export OPENAI_API_KEY="api_key"
```

O en Windows:

<img width="828" alt="image" src="https://github.com/user-attachments/assets/4bfa2e98-be36-4656-984e-7743a92ca9fc">

```text
set OPENAI_API_KEY=api_key
```

Como alternativa, si prefiere no preestablecer una clave API, puede establecer la clave manualmente al inicializar el modelo o cargarla desde un archivo `.env` mediante [python-dotenv](https://pypi.org/project/python-dotenv/). Primero, instale la biblioteca con `pip install python-dotenv`, y luego cargue las variables de entorno con el siguiente código en la parte superior de su script o cuaderno:

<img width="825" alt="image" src="https://github.com/user-attachments/assets/72de8c94-d3f1-4f5e-bcb7-cce689f8f392">

```text
from dotenv import load_dotenv

load_dotenv()  # take environment variables from .env.
```

El primer paso es obtener respuestas para múltiples ejecuciones de cada indicación y almacenarlas en una hoja de cálculo.

Input:

```text
# Define two variants of the prompt to test zero-shot
# vs few-shot
prompt_A = """Product description: A pair of shoes that can
fit any foot size.
Seed words: adaptable, fit, omni-fit.
Product names:"""

prompt_B = """Product description: A home milkshake maker.
Seed words: fast, healthy, compact.
Product names: HomeShaker, Fit Shaker, QuickShake, Shake
Maker

Product description: A watch that can tell accurate time in
space.
Seed words: astronaut, space-hardened, eliptical orbit
Product names: AstroTime, SpaceGuard, Orbit-Accurate,
EliptoTime.

Product description: A pair of shoes that can fit any foot
size.
Seed words: adaptable, fit, omni-fit.
Product names:"""

test_prompts = [prompt_A, prompt_B]

import pandas as pd
from openai import OpenAI
import os

# Set your OpenAI key as an environment variable
# https://platform.openai.com/api-keys
client = OpenAI(
  api_key=os.environ['OPENAI_API_KEY'],  # Default
)

def get_response(prompt):
    response = client.chat.completions.create(
        model="gpt-3.5-turbo",
        messages=[
            {
                "role": "system",
                "content": "You are a helpful assistant."
            },
            {
                "role": "user",
                "content": prompt
            }
        ]
    )
    return response.choices[0].message.content

# Iterate through the prompts and get responses
responses = []
num_tests = 5

for idx, prompt in enumerate(test_prompts):
    # prompt number as a letter
    var_name = chr(ord('A') + idx)

    for i in range(num_tests):
        # Get a response from the model
        response = get_response(prompt)

        data = {
            "variant": var_name,
            "prompt": prompt,
            "response": response
            }
        responses.append(data)

# Convert responses into a dataframe
df = pd.DataFrame(responses)

# Save the dataframe as a CSV file
df.to_csv("responses.csv", index=False)

print(df)
```

Ouput:

```text
variant                                             prompt
  \
0       A  Product description: A pair of shoes that can ...
1       A  Product description: A pair of shoes that can ...
2       A  Product description: A pair of shoes that can ...
3       A  Product description: A pair of shoes that can ...
4       A  Product description: A pair of shoes that can ...
5       B  Product description: A home milkshake maker.\n...
6       B  Product description: A home milkshake maker.\n...
7       B  Product description: A home milkshake maker.\n...
8       B  Product description: A home milkshake maker.\n...
9       B  Product description: A home milkshake maker.\n...

                                            response
0  1. Adapt-a-Fit Shoes \n2. Omni-Fit Footwear \n...
1  1. OmniFit Shoes\n2. Adapt-a-Sneaks \n3. OneFi...
2  1. Adapt-a-fit\n2. Flexi-fit shoes\n3. Omni-fe...
3  1. Adapt-A-Sole\n2. FitFlex\n3. Omni-FitX\n4. ...
4  1. Omni-Fit Shoes\n2. Adapt-a-Fit Shoes\n3. An...
5  Adapt-a-Fit, Perfect Fit Shoes, OmniShoe, OneS...
6       FitAll, OmniFit Shoes, SizeLess, AdaptaShoes
7       AdaptaFit, OmniShoe, PerfectFit, AllSizeFit.
8  FitMaster, AdaptoShoe, OmniFit, AnySize Footwe...
9        Adapt-a-Shoe, PerfectFit, OmniSize, FitForm
```

Aquí usamos la API OpenAI para generar el modelo. Respuestas a un conjunto de indicaciones y almacenamiento de los resultados en un marco de datos, que se guarda en un archivo CSV. Así es como funciona:

1. Se definen dos variantes del mensaje y cada variante consta de una descripción del producto, palabras clave y posibles nombres de productos, pero `prompt_B` se proporcionan dos ejemplos.

2. Se llaman declaraciones de importación para la biblioteca Pandas, la biblioteca OpenAI y la biblioteca del sistema operativo.

3. La función `get_response` toma un mensaje como entrada y devuelve una respuesta del modelo `gpt-3.5-turbo`. El mensaje se pasa como un mensaje de usuario al modelo, junto con un mensaje del sistema para establecer el comportamiento del modelo.

4. Se almacenan dos variantes de prompt en la lista `test_prompts`.

5. Se crea una lista vacía `responses` para almacenar las respuestas generadas y la variable `num_tests` se establece en `5`.

6. Un bucle anidado se utiliza para generar respuestas. El bucle externo itera sobre cada mensaje y el bucle interno genera `num_tests`(cinco en este caso) un número de respuestas por mensaje .

   a. La función `enumerate` se utiliza para obtener el índice y el valor de cada mensaje en `test_prompts`. Luego, este índice se convierte en una letra mayúscula correspondiente (por ejemplo, 0 se convierte en A, 1 se convierte en B ) para usarse como nombre de variante.

   b. Para cada iteración, `get_response` se llama a la función con el mensaje actual para generar una respuesta del modelo.

   c. Se crea un diccionario con el nombre de la variante, el mensaje y la respuesta del modelo, y este diccionario se agrega a la lista `responses`.

7. Una vez generadas todas las respuestas, la lista `responses` (que ahora es una lista de diccionarios) se convierte en un Pandas DataFrame.

8. Luego, este marco de datos se guarda en un archivo CSV con la función incorporada de Pandas `to_csv`, lo que hace que el archivo `responses.csv` con `index=False` escriba índices de fila.

9. Finalmente, el marco de datos se imprime en la consola.

Tener estas respuestas en una hoja de cálculo ya es útil, porque se puede ver de inmediato, incluso en la respuesta impresa, que `prompt_A`(zero-shot) en las primeras cinco filas nos da una lista numerada, mientras que `prompt_B`(few-shot) en las últimas cinco filas tiende a generar el formato deseado de una lista en línea separada por comas. El siguiente paso es dar una calificación a cada una de las respuestas, lo que se hace mejor de forma ciega y aleatoria para evitar favorecer una pregunta sobre otra.

Input:

```text
import ipywidgets as widgets
from IPython.display import display
import pandas as pd

# load the responses.csv file
df = pd.read_csv("responses.csv")

# Shuffle the dataframe
df = df.sample(frac=1).reset_index(drop=True)

# df is your dataframe and 'response' is the column with the
# text you want to test
response_index = 0
# add a new column to store feedback
df['feedback'] = pd.Series(dtype='str')

def on_button_clicked(b):
    global response_index
    #  convert thumbs up / down to 1 / 0
    user_feedback = 1 if b.description == "\U0001F44D" else 0

    # update the feedback column
    df.at[response_index, 'feedback'] = user_feedback

    response_index += 1
    if response_index < len(df):
        update_response()
    else:
        # save the feedback to a CSV file
        df.to_csv("results.csv", index=False)

        print("A/B testing completed. Here's the results:")
        # Calculate score and num rows for each variant
        summary_df = df.groupby('variant').agg(
            count=('feedback', 'count'),
            score=('feedback', 'mean')).reset_index()
        print(summary_df)

def update_response():
    new_response = df.iloc[response_index]['response']
    if pd.notna(new_response):
        new_response = "<p>" + new_response + "</p>"
    else:
        new_response = "<p>No response</p>"
    response.value = new_response
    count_label.value = f"Response: {response_index + 1}"
    count_label.value += f"/{len(df)}"

response = widgets.HTML()
count_label = widgets.Label()

update_response()

thumbs_up_button = widgets.Button(description='\U0001F44D')
thumbs_up_button.on_click(on_button_clicked)

thumbs_down_button = widgets.Button(
    description='\U0001F44E')
thumbs_down_button.on_click(on_button_clicked)

button_box = widgets.HBox([thumbs_down_button,
thumbs_up_button])

display(response, button_box, count_label)
```

La salida se muestra en la Figura 1-12:

<img width="827" alt="image" src="https://github.com/user-attachments/assets/cfbffdc4-1a73-4447-9d43-6415d6899f3e">

**Figura 1-12. Sistema de calificación de pulgares hacia arriba/pulgares hacia abajo**

Si ejecuta esto en un Jupyter Notebook, un widget muestra cada respuesta de IA, con un botón de pulgar hacia arriba o pulgar hacia abajo (consulte la Figura 1-12 ). Esto proporciona una interfaz simple para etiquetar rápidamente las respuestas, con una sobrecarga mínima. Si desea hacer esto fuera de un Jupyter Notebook, puede cambiar los emojis de pulgar hacia arriba y pulgar hacia abajo por Y y N , e implementar un bucle utilizando la función incorporada `input()`, como un reemplazo de solo texto para iPyWidgets.

Una vez que hayas terminado de etiquetar las respuestas, obtendrás el resultado, que te muestra cómo funciona cada mensaje.

<img width="838" alt="image" src="https://github.com/user-attachments/assets/ed207414-b1cb-4c94-8558-8938c4a74485">

Output:

```text
A/B testing completed. Here's the results:
  variant  count  score
0       A      5    0.2
1       B      5    0.6
```

El marco de datos se barajó al azar y cada respuesta se etiquetó como ciega (sin ver la indicación), de modo que se obtiene una imagen precisa de la frecuencia con la que se ejecutó cada indicación. Aquí se incluye la explicación paso a paso:

1. Se importan tres módulos: `ipywidgets`, `IPython.display`, y `pandas`. `ipywidgets` contiene widgets HTML interactivos para Jupyter Notebooks y el kernel IPython. `IPython.display` proporciona clases para mostrar varios tipos de salida como imágenes, sonido, visualización de HTML, etc. Pandas es una poderosa biblioteca de manipulación de datos.

2. La biblioteca Pandas se utiliza para leer el archivo CSV `responses.csv`, que contiene las respuestas que desea probar. Esto crea un Pandas DataFrame llamado `df`.

3. `df` se baraja utilizando la función `sample()` con `frac=1`, lo que significa que utiliza todas las filas. Se `reset_index(drop=True)` utiliza para restablecer los índices al índice estándar 0, 1, 2, …​, n.

4. El script se define `response_index` como 0. Esto se utiliza para rastrear qué respuesta del marco de datos está viendo actualmente el usuario.

5. Se agrega una nueva columna `feedback` al marco de datos `df` con el tipo de datos como `str` o string.

6. A continuación, el script define una función `on_button_clicked(b)` que se ejecutará cada vez que se haga clic en uno de los dos botones de la interfaz.

   a. La función primero verifica si `description` el botón en el que se hizo clic fue el de pulgar hacia arriba ( `\U0001F44D;` \U0001F44D; ), y lo establece `user_feedback` como 1, o si fue el de pulgar hacia abajo ( `\U0001F44E;` \U0001F44E; ), lo establece `user_feedback` como 0.

   b. Luego actualiza la columna `feedback` del marco de datos en el actual `response_index` con `user_feedback`.

   c. Después de eso, se incrementa `response_index` para pasar a la siguiente respuesta.

   d. Si `response_index` todavía es menor que el número total de respuestas (es decir, la longitud del marco de datos), llama a la función `update_response()`.

   e. Si no hay más respuestas, guarda el marco de datos en un nuevo archivo CSV `results.csv`, luego imprime un mensaje y también imprime un resumen de los resultados por variante, mostrando el recuento de comentarios recibidos y el puntaje promedio (media) para cada variante.

7. La función `update_response()` obtiene la siguiente respuesta del marco de datos, la envuelve en etiquetas HTML de párrafo (si no es nulo), actualiza el `response` widget para mostrar la nueva respuesta y actualiza el `count_label` widget para reflejar el número de respuesta actual y el número total de respuestas.

8. Se crean dos widgets `response`(un widget HTML) y `count_label`(un widget de etiqueta). Luego se llama a la función `update_response()` para inicializar estos widgets con la primera respuesta y la etiqueta adecuada. 

9. Se crean dos widgets más, `thumbs_up_button` y `thumbs_down_button`(ambos widgets de botón), con emojis de pulgar hacia arriba y pulgar hacia abajo como descripciones, respectivamente. Ambos botones están configurados para llamar a la función `on_button_clicked()` cuando se hace clic en ellos.

10. Los dos botones se agrupan en un cuadro horizontal (`button_box`) mediante la función `HBox`.

11. Finalmente, los widgets `response`, `button_box`, y `count_label` se muestran al usuario mediante la función `display()` del módulo `IPython.display`.

Un sistema de calificación simple como este puede ser útil para juzgar la calidad de las indicaciones y detectar casos extremos. Por lo general, en menos de 10 ejecuciones de prueba de una indicación, se descubre una desviación que, de otro modo, no se habría detectado hasta que se comenzó a utilizar en producción. La desventaja es que puede resultar tedioso calificar muchas respuestas manualmente, y es posible que las calificaciones no representen las preferencias de la audiencia a la que se dirige. Sin embargo, incluso una pequeña cantidad de pruebas puede revelar grandes diferencias entre dos estrategias de indicaciones y revelar problemas no obvios antes de llegar a producción.

La iteración y prueba de los mensajes puede llevar a reducciones radicales en la longitud del mensaje y, por lo tanto, en el costo y la latencia de su sistema. Si puede encontrar otro mensaje que funcione igual de bien (o mejor) pero que utilice un mensaje más corto, puede permitirse ampliar considerablemente su operación. A menudo, en este proceso encontrará que muchos elementos de un mensaje complejo son completamente superfluos o incluso contraproducentes.

Los pulgares hacia arriba u otros indicadores de calidad etiquetados manualmente no tienen por qué ser los únicos criterios de evaluación. La evaluación humana generalmente se considera la forma más precisa de retroalimentación. Sin embargo, puede ser tedioso y costoso calificar muchas muestras manualmente. En muchos casos, como en los casos de uso de matemáticas o clasificación, puede ser posible establezca la verdad básica (respuestas de referencia para casos de prueba) para evaluar programáticamente los resultados, lo que le permitirá ampliar considerablemente sus esfuerzos de prueba y monitoreo. La siguiente no es una lista exhaustiva porque hay muchas motivaciones para evaluar su indicar programáticamente:

* Costo

   Los mensajes que utilizan muchos tokens o que funcionan solo con modelos más costosos pueden resultar poco prácticos para el uso en producción.

* Estado latente

   Del mismo modo, cuanto más tokens haya o cuanto mayor sea el modelo requerido, más tiempo llevará completar una tarea, lo que puede perjudicar la experiencia del usuario.

* Llamadas

   Muchos sistemas de IA requieren múltiples llamadas en un bucle para completar una tarea, lo que puede ralentizar gravemente el proceso.

* Actuación

   Implementar algún tipo de sistema de retroalimentación externa, por ejemplo, un motor de física u otro modelo para predecir resultados del mundo real.

* Clasificación

   Determinar con qué frecuencia una indicación etiqueta correctamente un texto dado, utilizando otro modelo de IA o etiquetado basado en reglas.

* Razonamiento

   Determinar en qué casos la IA no aplica el razonamiento lógico o realiza errores matemáticos en comparación con los casos de referencia.

* Alucinaciones

   Observa con qué frecuencia tienes alucinaciones, medida según la invención de términos nuevos no incluidos en el contexto del mensaje.

* Seguridad

   Marque cualquier escenario en el que el sistema pueda devolver resultados inseguros o no deseados mediante un filtro de seguridad o un sistema de detección.

* Rechazos

   Descubra con qué frecuencia el sistema se niega incorrectamente a satisfacer una solicitud razonable de un usuario marcando el lenguaje de rechazo conocido.

* Adversario

   Haga que el indicador sea robusto contra ataques de inyección de indicador conocidos que pueden hacer que el modelo ejecute indicadores no deseados en lugar de lo que usted programó.

* Semejanza

   Utilice palabras y frases compartidas ( BLEU o ROGUE ) o distancia vectorial (explicada en el Capítulo 5 ) para medir la similitud entre el texto generado y el de referencia.

Una vez que comience a calificar qué ejemplos fueron buenos, podrá actualizar más fácilmente los ejemplos utilizados en su solicitud como una forma de hacer que su sistema sea cada vez más inteligente con el tiempo. Los datos de esta retroalimentación también pueden incorporarse a ejemplos para realizar ajustes, lo que comienza a superar la ingeniería de solicitudes una vez que pueda proporcionar unos pocos miles de ejemplos, como se muestra en la Figura 1-13 .

<img width="558" alt="image" src="https://github.com/user-attachments/assets/749a4899-007a-443a-9b36-60aad10fe60e">

**Figura 1-13. ¿Cuántos puntos de datos vale un prompt?**

Al pasar de un pulgar hacia arriba a un pulgar hacia abajo, puede implementar un sistema de calificación de 3, 5 o 10 puntos para obtener comentarios más detallados sobre la calidad de sus indicaciones. También es posible determinar el rendimiento relativo agregado al comparar las respuestas una al lado de la otra, en lugar de analizar las respuestas una a la vez. A partir de esto, puede construir una comparación justa entre modelos utilizando una [calificación Elo](https://en.wikipedia.org/wiki/Elo_rating_system), como es popular en ajedrez y se usa en [Chatbot Arena](https://lmarena.ai/?arena) de lmsys.org.

Para la generación de imágenes, la evaluación generalmente adopta la forma de una indicación de permutación, en la que se introducen múltiples direcciones o formatos y se genera una imagen para cada combinación. Las imágenes se pueden escanear o disponer posteriormente en una cuadrícula para mostrar el efecto que pueden tener los distintos elementos de la indicación en la imagen final.


<img width="834" alt="image" src="https://github.com/user-attachments/assets/99422e74-0ed7-41a0-9853-f4c6096a0b61">

Input:

```text
{stock photo, oil painting, illustration} of business
meeting of {four, eight} people watching on white MacBook on
top of glass-top table
```

En Midjourney esto se compilaría en seis indicaciones diferentes, una para cada combinación de los tres formatos (fotografía de archivo, pintura al óleo, ilustración) y dos números de personas (cuatro, ocho).

<img width="835" alt="image" src="https://github.com/user-attachments/assets/6c3119be-259a-4ded-ad0e-395707ce33ae">

Input:

```text
1. stock photo of business meeting of four people watching
on white MacBook on top of glass-top table

2. stock photo of business meeting of eight people watching
on white MacBook on top of glass-top table

3. oil painting of business meeting of four people watching
on white MacBook on top of glass-top table

4. oil painting of business meeting of eight people watching
on white MacBook on top of glass-top table

5. illustration of business meeting of four people watching
on white MacBook on top of glass-top table

6. illustration of business meeting of eight people watching
on white MacBook on top of glass-top table
```

Cada prompt genera sus propias cuatro imágenes como de costumbre, lo que hace que el resultado sea un poco más difícil de ver. Hemos seleccionado una de cada mensaje para ampliarla y luego las hemos puesto juntas en una cuadrícula, como se muestra en la Figura 1-14 . Notarás que el modelo no siempre obtiene la cantidad correcta de personas (los modelos de IA generativa son sorprendentemente malos en matemáticas), pero ha inferido correctamente la intención general al agregar más personas a las fotos de la derecha que a las de la izquierda.

La figura 1-14 muestra la salida.

<img width="731" alt="image" src="https://github.com/user-attachments/assets/16fcd079-29d1-4eb0-8adf-ad54e9b2393b">

**Figura 1-14. Cuadrícula de permutaciones de indicaciones**

Con modelos que tienen API como Stable Diffusion, puede manipular las fotos con mayor facilidad y mostrarlas en formato de cuadrícula para escanearlas con facilidad. También puede manipular la semilla aleatoria de la imagen para fijar un estilo en su lugar para lograr la máxima reproducibilidad. Con los clasificadores de imágenes, también puede ser posible clasificar las imágenes programáticamente en función de su contenido seguro o si contienen ciertos elementos asociados con éxito o con fracaso.

## 5. Dividir el trabajo

A medida que vaya desarrollando su mensaje, comienceLlegar al punto en el que le estás pidiendo mucho en una sola llamada a la IA. Cuando las indicaciones se hacen más largas y más complicadas, es posible que las respuestas se vuelvan menos deterministas y aumenten las alucinaciones o anomalías. Incluso si logras llegar a una indicación confiable para tu tarea, es probable que esa tarea sea solo una de varias tareas interrelacionadas que necesitas para hacer tu trabajo. Es natural comenzar a explorar cuántas otras de estas tareas podría realizar la IA y cómo podrías unirlas.

Uno de los principios básicos de la ingeniería esUtilice la descomposición de tareas para dividir los problemas en sus partes componentes, de modo que pueda resolver más fácilmente cada problema individual y luego volver a agregar los resultados. Dividir su trabajo de IA en múltiples llamadas encadenadas puede ayudarlo a realizar tareas más complejas, así como a brindar más visibilidad sobre qué parte de la cadena está fallando.

Hay muchos factores que intervienen en la elección del nombre de un producto, y una tarea importante se delega ingenuamente en la IA sin que se sepa cómo se pondera la importancia de estos factores (si es que se sabe). De la forma en que funciona nuestro sistema actual, obtenemos una lista de nombres, pero todos los nombres se muestran con la misma importancia sin ningún contexto adicional que nos ayude a decidir. Afortunadamente, las herramientas de IA son capaces de autoevaluarse; si añadimos un segundo paso a nuestra tarea, podemos comprobar automáticamente si hay resultados no deseados.

<img width="831" alt="image" src="https://github.com/user-attachments/assets/869bddba-71a2-470b-a0e7-fa65e8a529c6">

<img width="839" alt="image" src="https://github.com/user-attachments/assets/e718f074-57ce-4555-bf1f-b7bb6707b265">

Input:

```text
Rate this list of product names for a pair of shoes that can
fit any foot size. The rating should be out of 10, inline
next to the product name:

UniFit SoleStrides
FlexiSize All-Fit Shoes
OmniFit FootFlex
...
AnyStep AdaptiWalkers
FlexiRange UniversalSteps
PerfectGlide MultiFit Shoes
```

Output:

```text
UniFit SoleStrides: 7/10
FlexiSize All-Fit Shoes: 8/10
OmniFit FootFlex: 7/10
...
AnyStep AdaptiWalkers: 7/10
FlexiRange UniversalSteps: 7.5/10
PerfectGlide MultiFit Shoes: 9/10

This ranking is based on clarity, memorability, and how well
the name communicates the unique selling point of the
product (that they can fit any foot size). Remember, these
ratings are subjective and the ultimate success of a product
name also depends on the target market, branding, and
marketing efforts.
```

Al ejecutar esto varias veces, califica constantemente el nombre “OneSize Glovewalkers” como el peor, lo que proporciona contexto (si lo preguntas) de que el concepto puede ser confuso en un contexto de calzado. Quizás te preguntes por qué, si el modelo sabe que este es un mal nombre, lo sugiere en primer lugar. Los LLM funcionan prediciendo el siguiente token en una secuencia y, por lo tanto, tienen dificultades para saber cuál será la respuesta general cuando termine. Sin embargo, cuando tiene todos los tokens de una respuesta anterior para revisar, puede predecir más fácilmente si esta se etiquetará como una buena o mala respuesta.

Podemos seguir encadenando varias llamadas para mejorar los resultados de nuestra tarea. Por ejemplo, podríamos dividir esto en tres calificaciones independientes: claridad, facilidad de memorización y qué tan bien el nombre comunica el argumento de venta exclusivo del producto. Estas calificaciones podrían entregarse a un humano como contexto adicional para la decisión final, o incluso calcularse juntas para seleccionar el nombre final de manera programática.

La verdadera clave para aprender a trabajar profesionalmente con IA en lugar de simplemente jugar con indicaciones es darse cuenta de que cada parte del sistema se puede dividir en una serie de pasos iterativos. Incluso con una sola indicación, este principio se aplica, ya que simplemente agregar elementos `Let's think step by step` a la indicación puede generar mejoras demostrables en el razonamiento y la competencia, además de proporcionar un registro de auditoría para el control de calidad y la depuración. Cuando se dedica tiempo y fichas a razonar, las calificaciones cambian y son más coherentes con los criterios de puntuación.

<img width="830" alt="image" src="https://github.com/user-attachments/assets/4d39dc37-a553-4426-b971-7a53b98275c5">

<img width="759" alt="image" src="https://github.com/user-attachments/assets/35416bac-e63c-4f84-ad34-e32684643afc">

Input:

```text
Let's think step by step. Rate this list of product names
for a pair of shoes that can fit any foot size. The rating
should be out of 10, inline next to the product name:

UniFit SoleStrides
FlexiSize All-Fit Shoes
OmniFit FootFlex
...
AnyStep AdaptiWalkers
FlexiRange UniversalSteps
PerfectGlide MultiFit Shoes
```

Ouput:

```text
Here's a rating out of 10 for each product name, considering
factors like descriptiveness, catchiness, and overall
appeal:

1. **UniFit SoleStrides**: 7/10 - Sounds unifying but may
not immediately convey the "fit any size" idea.
2. **FlexiSize All-Fit Shoes**: 8.5/10 - Combines
flexibility and the notion that it fits all sizes.
3. **OmniFit FootFlex**: 8/10 - Omnipresence (fitting all)
and flexibility nicely conveyed.
...
18. **AnyStep AdaptiWalkers**: 7.5/10 - "AnyStep" suggests
versatility, but the overall name might be less direct.
19. **FlexiRange UniversalSteps**: 8/10 - Combines
flexibility and universal fit.
20. **PerfectGlide MultiFit Shoes**: 8.5/10 - "MultiFit" is
clear, and "PerfectGlide" suggests a comfortable experience.

Remember, the best name can also be influenced by your
target audience, branding strategy, and the overall message
you want to convey.
```

OpenAI [lo llama](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/) “darle tiempo al modelo para pensar”, y es un principio clave de la ingeniería rápida. En efecto, las técnicas de cadena de pensamiento como esto, donde se anima al modelo a enumerar sus pasos, es como dividir una tarea dentro de la misma indicación. Una vez que hemos automatizado la denominación del producto dada una idea de producto, podemos llamar a ChatGPT nuevamente para describir cada producto, que a su vez se puede introducir en Midjourney para generar una imagen de cada producto. El uso de un modelo de IA para generar una indicación para un modelo de IA es una indicación meta y funciona porque los LLM son ingenieros de indicaciones de nivel humano ( [Zhou, 2022](https://arxiv.org/abs/2211.01910) ).

<img width="838" alt="image" src="https://github.com/user-attachments/assets/d4d625a9-8914-45df-8304-bb8d8e411337">

Input:

```text
Describe the new product "OneFit UltraStride Shoes," a shoe
that can fit any foot size, in great detail:
```

Ouput:

```text
Introducing the revolutionary "OneFit UltraStride Shoes,"
the footwear innovation designed to fit any foot size with
unparalleled comfort and style. These shoes are a result of
cutting-edge technology and meticulous craftsmanship,
ensuring a truly personalized and enjoyable walking or
running experience for everyone.

Design and Materials:
The OneFit UltraStride Shoes boast an elegant and modern
design that appeals to both fashion-forward individuals and
sports enthusiasts. They feature a sleek and streamlined
silhouette, crafted using premium materials for durability
and aesthetic appeal. The shoe's upper is constructed from a
combination of breathable mesh and flexible synthetic
materials, allowing for excellent airflow and a lightweight
feel.

...

Color and Customization:
OneFit UltraStride Shoes are available in a variety of
vibrant colors and stylish patterns, catering to diverse
personal preferences. You can choose from classic
monochromatic options for a timeless look or opt for bold
and vibrant hues to make a fashion statement. The ability to
customize the shoe's appearance allows individuals to
express their unique style while enjoying the benefits of
the OneFit technology.

Conclusion:
The OneFit UltraStride Shoes represent a breakthrough in
footwear technology, eliminating the hassle of finding the
perfect fit for your feet. With their adaptive design,
superior comfort, and stylish aesthetics, these shoes offer
a truly personalized experience for individuals of all foot
sizes. Stay comfortable, confident, and on-trend with the
OneFit UltraStride Shoes, the ultimate choice for those
seeking unmatched versatility and a perfect fit.
```

DALL-E es bien conocido por GPT-4 y, por lo tanto, puedes invocar su nombre dentro de ChatGPT y hace un trabajo razonable al crear un mensaje para una herramienta de generación de imágenes. Si planeabas usar este mensaje en producción, puedes considerar aplicar el principio de mensajes para proporcionar ejemplos, pero hace un trabajo lo suficientemente bueno para nuestros propósitos sin ejemplos.

<img width="752" alt="image" src="https://github.com/user-attachments/assets/455c0f33-46fa-4a54-9da9-798d8ef5e1c9">

Input:

```text
Convert this description into a short prompt for an AI image
generation model such as DALL-E:
```

Ouput:

```text
Create an eye-catching image that visually represents the
"OneFit UltraStride Shoes," a revolutionary footwear product
that adapts to any foot size. Showcase a sleek and modern
shoe design incorporating a stretchable upper, an adjustable
lacing system, and a cushioned insole for optimal comfort.
Emphasize the shoe's versatility by displaying it in action
on various surfaces, highlighting its excellent traction.
Incorporate vibrant colors and patterns to convey the
customizable nature of the product. The image should capture
the essence of innovation, style, and personalized fit that
the OneFit UltraStride Shoes offer.
```

El resultado de este mensaje se puede incorporar a herramientas de generación de imágenes como DALL-E o Midjourney como mensaje, lo que puede brindarle un buen punto de partida para visualizar cómo se vería el producto. Aunque es posible que este no sea el diseño final que elija, ver una imagen es más evocador y ayuda a las personas a formarse una opinión más rápido. Es más fácil, desde el punto de vista cognitivo, criticar o elogiar una imagen existente que imaginar una nueva imagen a partir de una página en blanco o una sección de texto.

La figura 1-15 muestra la salida.

<img width="816" alt="image" src="https://github.com/user-attachments/assets/d2d2f520-987a-4a46-bf7e-7ad732c50fb8">

**Figura 1-15. Zapatillas OneFit UltraStride**

Es una práctica común cuando se trabaja con la IA encadena de forma profesional múltiples llamadas a la IA, e incluso múltiples modelos, para lograr objetivos más complejos. Incluso las aplicaciones con un único mensaje suelen crearse de forma dinámica, basándose en el contexto externo consultado desde varias bases de datos u otras llamadas a un modelo de IA. La biblioteca [LangChain](https://www.langchain.com/) ha desarrollado herramientas para encadenar múltiples plantillas de mensajes y consultas, lo que hace que este proceso sea más observable y esté mejor estructurado. Un ejemplo fundamental es el resumen progresivo, en el que el texto que es demasiado grande para caber en una ventana de contexto se puede dividir en varios fragmentos de texto, y cada uno de ellos se resume, antes de resumir finalmente los resúmenes. Si habla con los desarrolladores de los primeros productos de IA, descubrirá que todos ellos encadenan en secreto múltiples mensajes, lo que se denomina encadenamiento de IA, para lograr mejores resultados en el resultado final.

El marco [Reason and Act](https://til.simonwillison.net/llms/python-react-pattern) (ReAct) fue uno de los primeros intentos populares de crear agentes de IA, incluidos los proyectos de código abierto [BabyAGI](https://github.com/yoheinakajima/babyagi),[AgentGPT](https://github.com/reworkd/AgentGPT) y [Microsoft AutoGen](https://microsoft.github.io/autogen/0.2/). En efecto, estos agentes son el resultado de encadenar múltiples llamadas de IA para planificar, observar, actuar y luego evaluar los resultados de la acción. Los agentes autónomos se tratarán en el Capítulo 6, pero todavía no se utilizan ampliamente en producción al momento de escribir este artículo. Esta práctica de agentes con razonamiento automático aún es temprana y propensa a errores, pero hay señales prometedoras de que este enfoque puede ser útil para lograr tareas complejas y es probable que sea parte de la siguiente etapa en la evolución de los sistemas de IA.

Hay una batalla de IA en curso entre grandes empresas de tecnología como Microsoft y Google, así como una amplia gama de proyectos de código abierto en Hugging Face y nuevas empresas financiadas con capital de riesgo como OpenAI y Anthropic. A medida que continúan proliferando nuevos modelos, se están diversificando para competir por diferentes segmentos del creciente mercado. Por ejemplo, Claude 2 de Anthropic tenía una ventana de contexto de [100.000 tokens](https://www.anthropic.com/news/claude-2), en comparación con los [8.192 tokens](https://platform.openai.com/docs/models/gpt-4-and-gpt-4-turbo) estándar de GPT-4 . OpenAI pronto respondió con una versión de ventana de [128.000 tokens de GPT-4](https://openai.com/index/new-models-and-developer-products-announced-at-devday/), y Google promociona una longitud de contexto de 1 millón de tokens con [Gemini 1.5](https://blog.google/technology/ai/google-gemini-next-generation-model-february-2024/). A modo de comparación, uno de los libros de Harry Potter tendría alrededor de 185.000 tokens, por lo que puede volverse común que un libro completo quepa dentro de un solo mensaje, aunque procesar millones de tokens con cada llamada a la API puede tener un costo prohibitivo para la mayoría de los casos de uso.

Este libro se centra en GPT-4 para técnicas de generación de texto, así como en Midjourney v6 y Stable Diffusion XL para técnicas de generación de imágenes, pero en cuestión de meses estos modelos pueden dejar de ser de última generación. Esto significa que será cada vez más importante poder seleccionar el modelo adecuado para el trabajo y encadenar varios sistemas de IA. Las plantillas de indicaciones rara vez son comparables cuando se transfieren a un nuevo modelo, pero el efecto de los cinco principios de indicación mejorará constantemente cualquier modelo le indicamos el uso que le dará, para cualquier modelo, resultados más confiables.

## Resumen

En este capítulo, aprendiste sobre la importancia de la ingeniería de indicaciones en el contexto de la IA generativa. Definimos la ingeniería de indicaciones como el proceso de desarrollar indicaciones efectivas que produzcan los resultados deseados al interactuar con modelos de IA. Descubriste que brindar una dirección clara, dar formato a los resultados, incorporar ejemplos, establecer un sistema de evaluación y dividir las tareas complejas en indicaciones más pequeñas son principios clave de la ingeniería de indicaciones. Al aplicar estos principios y usar técnicas de indicaciones comunes, puedes mejorar la calidad y la confiabilidad de los resultados generados por IA.

También exploró el papel de la ingeniería de indicaciones en la generación de nombres e imágenes de productos. Observó cómo especificar el formato deseado y proporcionar ejemplos instructivos puede influir en gran medida en el resultado de la IA. Además, aprendió sobre el concepto de juego de roles, donde puede pedirle a la IA que genere resultados como si fuera una persona famosa como Steve Jobs. El capítulo enfatizó la necesidad de una dirección y un contexto claros para lograr los resultados deseados al usar modelos de IA generativos. Además, descubrió la importancia de evaluar el rendimiento de los modelos de IA y los diversos métodos utilizados para medir los resultados, así como las compensaciones entre la calidad y el uso de tokens, el costo y la latencia.

En el siguiente capítulo, se le presentarán los modelos de generación de texto. Aprenderá sobre los diferentes tipos de modelos básicos y sus capacidades, así como sus limitaciones. El capítulo también revisará las ofertas estándar de OpenAI, así como los competidores y las alternativas de código abierto. Al final del capítulo, tendrá una comprensión sólida de la historia de los modelos de generación de texto y sus fortalezas y debilidades relativas. Este libro volverá a la generación de imágenes mediante indicaciones en los capítulos 7, 8 y 9, por lo que puede omitir este capítulo si esa es su necesidad inmediata. Prepárese para profundizar en la disciplina de la ingeniería de indicaciones y ampliar su comodidad al trabajar con IA.
