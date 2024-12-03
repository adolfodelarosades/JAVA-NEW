# Chapter 1:​ Abstraction and Modeling

* Simplification Through Abstraction
* Generalization Through Abstraction
* Organizing Abstractions into Classification Hierarchies
* Abstraction as the Basis for Software Development
* Reuse of Abstractions
* Inherent Challenges
* What Does It Take to Be a Successful Object Modeler?​
* Summary

Como seres humanos, estamos inundados de información todos los días de nuestra vida. Incluso si pudiéramos apagar temporalmente todas las fuentes de “información electrónica” que nos bombardean constantemente (correos electrónicos, mensajes de voz, podcasts, tuits y similares), nuestros cinco sentidos por sí solos recopilan millones de bits de información por día solo de nuestro entorno. Sin embargo, logramos darle sentido a toda esta información, generalmente sin agobiarnos. Nuestros cerebros simplifican naturalmente los detalles de todo lo que observamos para que estos detalles sean manejables a través de un proceso conocido como **abstracción**.

En este capítulo aprenderás

* Cómo la abstracción sirve para simplificar nuestra visión del mundo

* Cómo organizamos nuestro conocimiento jerárquicamente para minimizar la cantidad de información que tenemos que manejar mentalmente en un momento dado

* La relevancia de la abstracción para el desarrollo de software

* Los desafíos inherentes que enfrentamos como desarrolladores de software cuando intentamos modelar una situación del mundo real en el software

## Simplificación a través de la abstracción

Tómate un momento para mirar alrededor de la habitación en la que estás leyendo este libro. Al principio, puedes pensar que en realidad no hay muchas cosas para observar: algunos muebles, lámparas, tal vez algunas plantas, obras de arte, incluso otras personas o mascotas. Tal vez haya una ventana por la que mirar y que abra el mundo exterior a la observación.

Ahora mira de nuevo. Para cada cosa que ves, hay una miríada de detalles que observar: su tamaño, su color, su propósito previsto, los componentes con los que está ensamblada (las patas de una mesa, las bombillas de una lámpara), etc. Además, cada uno de estos componentes a su vez tiene detalles asociados a él: el tipo de material utilizado para hacer las patas de la mesa (madera o metal), el vataje de las bombillas, etc. Ahora ten en cuenta tus otros sentidos: el sonido de alguien roncando (¡espero que no mientras lees este libro!), el olor a palomitas de maíz que sale del horno microondas del pasillo, etc. Por último, piensa en todos los detalles invisibles de estos objetos: quién los fabricó o cuál es su composición química, molecular o genética.

Está claro que la cantidad de información que debe procesar nuestro cerebro es realmente abrumadora. Sin embargo, para la gran mayoría de las personas, esto no supone un problema, ya que tenemos una habilidad innata para la abstracción, un proceso que implica reconocer y centrarse en las características importantes de una situación u objeto y filtrar o ignorar todos los detalles no esenciales.

Un ejemplo conocido de abstracción es un mapa de carreteras. Como abstracción, un mapa de carreteras representa aquellas características de un área geográfica dada que son relevantes para alguien que intenta navegar con el mapa, tal vez en automóvil: carreteras principales y lugares de interés, obstáculos como grandes masas de agua, etc. Por necesidad, un mapa de carreteras no puede incluir todos los edificios, árboles, señales de calle, vallas publicitarias, semáforos, restaurantes de comida rápida, etc. que existen físicamente en el mundo real. Si así fuera, estaría tan desordenado que sería prácticamente inutilizable; ninguna de las características importantes se destacaría. Comparemos un mapa de carreteras con un mapa topográfico, un mapa climatológico y un mapa de densidad de población de la misma región: cada uno abstrae diferentes características del mundo real, es decir, aquellas relevantes para el usuario previsto del mapa en cuestión.

Como otro ejemplo, considere un paisaje. Un artista puede mirar el paisaje desde la perspectiva de los colores, las texturas y las formas como un tema potencial para una pintura. Un constructor de viviendas puede mirar el mismo paisaje desde la perspectiva de cuál puede ser el mejor sitio para construir en la propiedad, evaluando cuántos árboles necesitará talar para dejar paso a un proyecto de construcción. Un ecologista puede estudiar de cerca las especies individuales de árboles y otras formas de vida vegetal y animal en busca de su biodiversidad, con el objetivo de preservarlas y protegerlas, mientras que un niño puede simplemente mirar todos los árboles en busca del mejor sitio para una casa en el árbol. Algunos elementos son comunes a las abstracciones del paisaje de los cuatro observadores (los tipos, tamaños y ubicaciones de los árboles, por ejemplo), mientras que otros no son relevantes para todas las abstracciones.

## Generalización a través de la abstracción

Si eliminamos suficientes detalles de una abstracción, esta se vuelve lo suficientemente genérica como para poder aplicarse a una amplia gama de situaciones o instancias específicas. Estas abstracciones genéricas pueden resultar a menudo muy útiles. Por ejemplo, un diagrama de una célula genérica del cuerpo humano, como el de la Figura 1-1 , podría incluir solo algunas características de las estructuras que se encuentran en una célula real.

![image](https://github.com/user-attachments/assets/77af9bf8-6bcf-4f81-aa6c-73a9db16387d)

Figura 1-1 Una abstracción genérica de una célula.

Este diagrama excesivamente simplificado no parece una célula nerviosa real, ni una célula muscular real, ni una célula sanguínea real; y, sin embargo, puede usarse en un entorno educativo para describir ciertos aspectos de la estructura y función de todos estos tipos de células, es decir, aquellas características que los diversos tipos de células tienen en común.

Cuanto más simple sea una abstracción (es decir, cuantas menos características presente), más general será y más versátil será para describir una variedad de situaciones del mundo real. Cuanto más compleja sea una abstracción, más restrictiva será y, por lo tanto, menos situaciones podrá describir.

### Organización de abstracciones en jerarquías de clasificación

Aunque nuestro cerebro es experto en abstraer conceptos como mapas de carreteras y paisajes, todavía nos quedamos con millones de abstracciones independientes con las que lidiar a lo largo de nuestra vida. Para hacer frente a este aspecto de la complejidad, los seres humanos organizan sistemáticamente la información en categorías según criterios establecidos; este proceso se conoce como **clasificación**.

Por ejemplo, la ciencia clasifica todos los objetos naturales como pertenecientes al reino animal, vegetal o mineral. Para que un objeto natural se clasifique como animal, debe cumplir las siguientes reglas:

* Debe ser (o haber sido en algún momento) un ser vivo.
* Debe ser capaz de movimiento espontáneo.
* Debe ser capaz de responder motoramente rápidamente a la estimulación.

Las reglas sobre lo que constituye una planta, por otro lado, son diferentes:

* Debe ser un ser vivo (lo mismo que un animal).
* Debe faltarle un sistema nervioso evidente.
* Debe poseer paredes celulares de celulosa.

Dadas reglas claras como estas, colocar un objeto en la categoría o clase apropiada es bastante sencillo. Luego podemos “profundizar” y especificar reglas adicionales que diferencien varios tipos de animales, por ejemplo, hasta que hayamos construido una jerarquía de abstracciones cada vez más complejas de arriba a abajo. En la Figura 1-2 se muestra un ejemplo simple de una jerarquía de abstracciones de este tipo.

![image](https://github.com/user-attachments/assets/1020a179-1ed8-4462-9b04-560aacd2c8f8)

Figura 1-2 Una simple jerarquía de abstracción de objetos naturales.

Cuando pensamos en una jerarquía de abstracción como la que se muestra en la Figura 1-2, avanzamos mentalmente hacia arriba y hacia abajo en la jerarquía, concentrándonos automáticamente solo en la capa o subconjunto de la jerarquía (conocido como subárbol) que es importante para nosotros en un momento dado. Por ejemplo, podemos estar interesados ​​solo en los mamíferos y, por lo tanto, podemos centrarnos en el subárbol de mamíferos, que se muestra en la Figura 1-3 , ignorando temporalmente el resto de la jerarquía.

![image](https://github.com/user-attachments/assets/c195369c-b399-42f4-b347-f8f349e3992a)

Figura 1-3 Centrarse en un pequeño subconjunto de la jerarquía es menos abrumador

Al hacerlo, reducimos automáticamente la cantidad de conceptos que necesitamos manejar mentalmente en cualquier momento a un subconjunto manejable de la jerarquía de abstracción general; en nuestro ejemplo simplista, ahora estamos tratando con solo cuatro conceptos en lugar de los 13 originales. No importa cuán compleja se vuelva una jerarquía de abstracción, no tiene por qué abrumarnos si está organizada adecuadamente.

No siempre es fácil determinar con precisión qué reglas son necesarias para clasificar correctamente un objeto dentro de una jerarquía de abstracción. Tomemos, por ejemplo, las reglas que podríamos definir para lo que constituye un pájaro: es decir, algo que

* Tiene plumas
* Tiene alas
* Pone huevos
* Es capaz de volar

Dadas estas reglas, ni un avestruz ni un pingüino podrían clasificarse como aves (aunque ambos deberían serlo), porque ninguno de ellos puede volar (ver Figura 1-4 ).

![image](https://github.com/user-attachments/assets/666e398d-c25a-4593-a5a3-380bf7dd8c36)

Figura 1-4 Derivar las reglas de clasificación correctas puede ser difícil

Si intentamos hacer que el conjunto de reglas sea menos restrictivo eliminando la regla de “es capaz de volar”, nos quedamos con

* Tiene plumas
* Tiene alas
* Pone huevos

De acuerdo con este conjunto de reglas, ahora podemos clasificar correctamente tanto al avestruz como al pingüino como aves, como se muestra en la Figura 1-5 .


![image](https://github.com/user-attachments/assets/926a3c42-bcdc-47bd-9c3a-22d19cb03a2c)

Figura 1-5 Se han establecido reglas de clasificación adecuadas

Este conjunto de reglas sigue siendo innecesariamente complicado, porque resulta que la regla de “pone huevos” es redundante: ya sea que la mantengamos o la eliminemos, no cambia nuestra decisión de qué constituye un pájaro o un no pájaro. Por lo tanto, simplificamos el conjunto de reglas una vez más:

* Tiene plumas
* Tiene alas

Sintiéndonos particularmente atrevidos(!), tratamos de llevar nuestro proceso de simplificación un paso más allá eliminando otra regla, definiendo un pájaro como algo que

* Tiene alas

Como muestra la Figura 1-6 , esta vez hemos ido demasiado lejos: ¡la abstracción de un pájaro es ahora tan general que incluiríamos aviones, insectos y todo tipo de otros seres que no son pájaros en la mezcla!

![image](https://github.com/user-attachments/assets/dd52f6a2-2eff-429e-87ad-e28184edb169)

Figura 1-6 Un conjunto de reglas demasiado laxo es un problema tan grande como un conjunto de reglas demasiado restrictivo.

El proceso de definición de reglas para fines de categorización implica seleccionar el conjunto correcto de reglas (no demasiado generales, ni demasiado restrictivas, y sin redundancias) para definir la membresía correcta en una clase particular.

#### La abstracción como base para el desarrollo de software

Al determinar los requisitos para un proyecto de desarrollo de sistemas de información, normalmente comenzamos por recopilar detalles sobre la situación real en la que se basará el sistema. Estos detalles suelen ser una combinación de:

* Aquellos que se nos ofrecen explícitamente a medida que entrevistamos a los usuarios previstos del sistema.
* Aquellos que de otra manera observamos

Debemos tomar una decisión sobre cuáles de estos detalles son relevantes para el propósito final del sistema. Esto es esencial, ya que no podemos automatizarlos todos. Incluir demasiados detalles es complicar excesivamente el sistema resultante, haciéndolo mucho más difícil de diseñar, programar, probar, depurar, documentar, mantener y ampliar en el futuro.

Al igual que con todas las abstracciones, todas nuestras decisiones de inclusión o eliminación al crear un sistema de software deben realizarse dentro del contexto del propósito general y el dominio, o el enfoque temático, del futuro sistema. Al representar a una persona en un sistema de software, por ejemplo, ¿es importante su color de ojos? ¿Y su perfil genético? ¿Su salario? ¿Sus pasatiempos? La respuesta es que cualquiera de estas características de una persona puede ser relevante o irrelevante, dependiendo de si el sistema que se va a desarrollar es un

* Sistema de nómina
* Sistema de demografía de marketing
* Base de datos de pacientes del optometrista
* El sistema de rastreo de los “más buscados” del FBI

Una vez que hemos determinado los aspectos esenciales de una situación (algo que exploraremos en la Parte 2 de este libro), podemos preparar un modelo de esa situación. El modelado es el proceso mediante el cual desarrollamos un patrón para que algo se haga. Un plano de una casa personalizada, un diagrama esquemático de un circuito impreso y un cortador de galletas son ejemplos de tales patrones. Como veremos en las Partes 2 y 3, un modelo de objeto de un sistema de software es un patrón de este tipo. El modelado y la abstracción van de la mano, porque un modelo es esencialmente una representación física o gráfica de una abstracción; antes de que podamos modelar algo de manera efectiva, debemos haber determinado los detalles esenciales del tema que se va a modelar.

## Reutilización de abstracciones

Cuando aprendemos algo nuevo, automáticamente buscamos en nuestro archivo mental otras abstracciones/modelos que hemos construido y dominado previamente, para buscar similitudes sobre las que podamos construir. Cuando aprendiste a andar en una bicicleta de dos ruedas por primera vez, por ejemplo, es posible que hayas recurrido a lecciones que aprendiste sobre andar en triciclo cuando eras niño (ver Figura 1-7 ). Ambos tienen manubrios que se usan para conducir; ambos tienen pedales que se usan para impulsar la bicicleta hacia adelante. Aunque las abstracciones no coincidían perfectamente (una bicicleta de dos ruedas introdujo el nuevo desafío de tener que mantener el equilibrio), había suficiente similitud para permitirte recurrir a la experiencia de dirección y pedaleo que ya dominabas y concentrarte en aprender la nueva habilidad de cómo mantener el equilibrio sobre dos ruedas.

![image](https://github.com/user-attachments/assets/58545889-6da5-4bd1-992c-94c502fb613b)

Figura 1-7 El cerebro humano es experto en aprender basándose en abstracciones ya establecidas.

Esta técnica de comparación de características para encontrar una abstracción que sea lo suficientemente similar como para ser reutilizada con éxito se conoce como **pattern matching and reuse - coincidencia y reutilización de patrones**. Como veremos más adelante en el libro, la reutilización de patrones también es una técnica importante para el desarrollo de software orientado a objetos, ya que nos ahorra tener que reinventar la rueda con cada nuevo proyecto. Si podemos reutilizar una abstracción o un modelo de un proyecto anterior, podemos centrarnos en aquellos aspectos del nuevo proyecto que difieren del anterior, lo que genera una enorme cantidad de productividad en el proceso.

### Desafíos inherentes

A pesar de que la abstracción es un proceso tan natural para los seres humanos, desarrollar un modelo apropiado para un sistema de software es quizás el aspecto más difícil de la ingeniería de software, porque:

* Las posibilidades son ilimitadas. La abstracción depende hasta cierto punto del observador: es casi seguro que varios observadores diferentes que trabajen independientemente llegarán a diferentes modelos. ¿Quién es el mejor? ¡Han surgido apasionadas discusiones!

* Para complicar aún más las cosas, prácticamente nunca existe un único modelo “mejor” o “correcto”, sino sólo modelos “mejores” o “peores” en relación con el problema que se debe resolver. La misma situación se puede modelar de diversas formas igualmente válidas. Cuando nos pongamos a hacer algunos modelos en la Parte 2 de este libro, veremos una serie de abstracciones alternativas válidas para nuestro caso de estudio del Sistema de Registro de Estudiantes (SRS) que se presentó al final de la Introducción.

* Sin embargo, hay que tener en cuenta que existen modelos incorrectos, es decir, aquellos que tergiversan la situación del mundo real (por ejemplo, modelar a una persona como si tuviera dos tipos de sangre diferentes).

* No existe una prueba de fuego para determinar si un modelo ha capturado adecuadamente todos los requisitos de un usuario. La prueba definitiva de si una abstracción fue apropiada o no está en el éxito que resulte el sistema de software resultante. Por ello, es fundamental que aprendamos formas de comunicar nuestro modelo de forma concisa e inequívoca con frecuencia a lo largo del ciclo de vida del desarrollo ágil.

* Los futuros usuarios previstos de nuestra aplicación, para que puedan proporcionar una comprobación de nuestra comprensión del problema que se debe resolver antes de embarcarnos en el desarrollo del software.

* Nuestros colegas ingenieros de software, para que los miembros del equipo puedan compartir una visión común de lo que vamos a construir de manera colaborativa.

A pesar de todos estos desafíos, es fundamental lograr que la abstracción inicial sea “correcta” antes de comenzar a construir un sistema. Cuanto más tarde en el ciclo de vida del software se detecte un error de modelado, más costoso será solucionarlo en órdenes de magnitud. Esto no implica que una abstracción deba ser rígida, ¡todo lo contrario! El arte y la ciencia del modelado de objetos, cuando se aplica correctamente, produce un modelo que es lo suficientemente flexible como para soportar una amplia variedad de cambios funcionales. Además, las propiedades especiales de los objetos de software se prestan aún más a soluciones de software flexibles, como aprenderá a lo largo del resto del libro.

¿Qué se necesita para ser un modelador de objetos exitoso?
Para elaborar una abstracción adecuada como base para un modelo de sistema de software se requiere:
Una visión del dominio del problema : lo ideal sería que pudiéramos recurrir a nuestras propias experiencias en el mundo real, como nuestra experiencia anterior o actual como estudiantes, lo que será útil al momento de determinar los requisitos para el Sistema de Registro de Estudiantes (SRS) , la base de nuestros esfuerzos de modelado y codificación en las Partes 2 y 3 del libro.

Creatividad : Debemos ser capaces de pensar “fuera de la caja”, en caso de que los futuros usuarios a quienes entrevistamos hayan estado inmersos en el área del problema durante tanto tiempo que no logren ver innovaciones que se podrían realizar.

Buenas habilidades para escuchar : estas serán útiles cuando los futuros usuarios del sistema describan cómo hacen su trabajo actualmente o cómo imaginan hacerlo en el futuro, con la ayuda del sistema que estamos a punto de desarrollar.

Buenas dotes de observación : las acciones suelen decir más que las palabras. Con solo observar a los usuarios en sus actividades diarias, podemos detectar un detalle esencial que no han mencionado porque lo hacen tan rutinariamente que se ha convertido en un hábito.

Pero todo esto no es suficiente. También necesitamos
Un proceso organizado para determinar cuál debería ser la abstracción. Si seguimos una lista de verificación de pasos comprobada para producir un modelo, entonces reducimos en gran medida la probabilidad de que omitamos alguna característica importante o descuidemos un requisito crítico.

Una forma de comunicar el modelo resultante de forma concisa e inequívoca a nuestros compañeros desarrolladores de software y a las partes interesadas/usuarios previstos de nuestra aplicación. Si bien es posible describir una abstracción en un texto narrativo, una imagen vale más que mil palabras, por lo que el lenguaje con el que comunicamos un modelo suele ser una notación gráfica . A lo largo de este libro, nos centraremos en la notación del Lenguaje de modelado unificado (UML; consulte la Figura 1-8 ) como nuestro lenguaje de comunicación de modelos (aprenderá los conceptos básicos de UML en los Capítulos 10 y 11 ). Piense en un modelo gráfico como un plano de la aplicación de software que se va a crear.


Figura 1-8Describir un paisaje en notación UML
Lo ideal sería una herramienta de software que nos ayudara a automatizar el proceso de producción de dicho plano.

La segunda parte de este libro cubre estos tres aspectos del modelado (proceso, notación y herramienta) en detalle.

A lo largo del resto de este libro, nos centraremos en el siguiente caso de estudio como base de las lecciones de modelado de objetos y codificación Java:

Especificación de requisitos del sistema de registro de estudiantes (SRS)
Se nos ha pedido que desarrollemos un Sistema automatizado de Registro de Estudiantes (SRS)Este sistema permitirá a los estudiantes registrarse en línea para cursos cada semestre, así como realizar un seguimiento del progreso del estudiante hacia la finalización de su título.

Cuando un estudiante se inscribe por primera vez en la universidad, utiliza el SRS para establecer un plan de estudios en cuanto a los cursos que planea tomar para satisfacer un programa de grado en particular y elegir un asesor docente. El SRS verificará si el plan de estudios propuesto satisface o no los requisitos del título que el estudiante está buscando. Una vez que se ha establecido un plan de estudios, durante el período de inscripción anterior a cada semestre, los estudiantes pueden ver el cronograma de clases en línea y elegir las clases a las que desean asistir, indicando la sección preferida (día de la semana y hora del día) si la clase es ofrecida por más de un profesor. El SRS verificará si el estudiante ha cumplido o no con los requisitos previos necesarios para cada curso solicitado consultando el expediente académico en línea del estudiante de los cursos completados y las calificaciones recibidas (el estudiante puede revisar su expediente académico en línea en cualquier momento).

Suponiendo que (a) se cumplen los requisitos previos para los cursos solicitados, (b) los cursos cumplen con uno de los requisitos del plan de estudios del estudiante y (c) hay lugar disponible en cada una de las clases, el estudiante queda inscrito en las clases.

Si se cumplen los puntos (a) y (b), pero no (c), el estudiante pasa a una lista de espera por orden de llegada. Si una clase o sección para la que estaba en lista de espera se vuelve disponible (ya sea porque otro estudiante ha abandonado la clase o porque se ha aumentado la capacidad de asientos para la clase), el estudiante queda inscrito automáticamente en la clase en lista de espera y se le envía un mensaje de correo electrónico a tal efecto. Es su responsabilidad abandonar la clase si ya no la desea; de lo contrario, se le facturará el curso.

Resumen
En este capítulo, has aprendido que

La abstracción es una técnica fundamental que la gente utiliza para percibir el mundo.

Desarrollar una abstracción del problema que se va a automatizar es un primer paso necesario en todo desarrollo de software.

Naturalmente organizamos la información en jerarquías de clasificación basadas en reglas que estructuramos cuidadosamente, de modo que no sean ni demasiado generales ni demasiado restrictivas.

A menudo reutilizamos abstracciones cuando intentamos modelar un nuevo concepto.

Producir una abstracción de un sistema que se va a construir, conocida como modelo, es en cierto sentido algo natural para nosotros y, sin embargo, paradójicamente, es una de las cosas más difíciles que los desarrolladores de software tienen que hacer en el ciclo de vida de un proyecto de sistemas de información. También es una de las más importantes.

Ceremonias
1.	
Dibuje una jerarquía de clases que se relacione con todas las siguientes clases de una manera razonable:

Manzana

Banana

Carne de res

Bebida

Queso

Consumible

Producto lácteo

Alimento

Fruta

Judías verdes

Carne

Leche

Cerdo

Espinaca

Verdura

Justifique su respuesta, señalando en particular cualquier desafío que haya enfrentado al hacerlo.

 
2.	
¿Qué aspectos de un televisor serían importantes abstraer desde la perspectiva de...
¿Un consumidor que desea comprar uno?

¿Un ingeniero encargado de diseñar uno?

¿Un minorista que los venda?

¿El fabricante?

 
3.	
Seleccione un área problemática que le gustaría modelar desde una perspectiva orientada a objetos. Lo ideal sería que se trate de un problema en el que realmente vaya a trabajar en su lugar de trabajo o en el que tenga un gran interés. Suponga que va a escribir un programa para automatizar algún aspecto de esta área problemática y escriba una descripción general de una página de los requisitos para este programa, siguiendo el modelo del estudio de caso de SRS .

Asegúrese de que el primer párrafo resuma la intención del sistema, como lo hace el primer párrafo del caso práctico de SRS. Además, enfatice los requisitos funcionales (es decir, aquellos que un usuario final no técnico podría indicar sobre cómo debería comportarse el sistema) y evite indicar requisitos técnicos , por ejemplo, “Este sistema debe ejecutarse en una plataforma Unix y debe utilizar el protocolo TCP/IP para…”

 
4.	
Lea el estudio de caso de un sistema de seguimiento de recetas (PTS) en el Apéndice. En su opinión, ¿qué tan efectivo es este estudio de caso como abstracción? ¿Hay detalles que cree que podrían haberse omitido o faltan detalles que cree que habría sido importante incluir? Si tuviera la oportunidad de entrevistar a los usuarios previstos del PTS, ¿qué preguntas adicionales les haría para refinar mejor esta abstracción?
