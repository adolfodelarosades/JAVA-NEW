#### Jacquie Barker
## Beginning Java Objects
### From Concepts to Code
#### 3rd ed.

## Prefacio
¡Bienvenidos a la tercera edición de Beginning Java Objects (BJO)! Desde que se publicó la primera edición de BJO en noviembre de 2000 y la segunda edición en 2005, me han encantado los numerosos correos electrónicos y críticas positivas que he recibido de lectores que encontraron que mi libro era un "inicio" perfecto en Java y la programación orientada a objetos (OO) . Muchos libros de Java para principiantes se sumergen en una discusión del lenguaje en sí sin fundamentar adecuadamente a los lectores sobre cómo "pensar" y estructurar una aplicación desde cero para aprovechar al máximo los principios orientados a objetos; estoy encantado de que haya elegido BJO para comenzar su viaje en Java.

Mi libro se basa en principios atemporales que son independientes de la versión del lenguaje, lo que significa que no es necesario revisarlo cada vez que se lanza una nueva versión de Java. Lo que sí cambia, a veces aparentemente en un abrir y cerrar de ojos, son las tecnologías de terceros que se utilizan junto con el lenguaje Java central, por lo que hemos reemplazado el material que detallaba las tecnologías obsoletas con un solo capítulo (Capítulo 15 ) que explica conceptualmente cómo avanzar en la creación de una aplicación que logre una separación adecuada entre el modelo , la capa de datos y la capa de presentación.

También hemos incluido mención de algunas de las mejoras significativas del lenguaje Java desde las versiones 8 a la 17 (la versión más nueva que se lanzará al momento de escribir la tercera edición).

Como siempre, agradezco los comentarios de los lectores y espero recibir noticias suyas en jacquie.barker@gmail.com.

Atentamente,

Jacquie

Introducción
Este es un libro, ante todo, sobre objetos de software: qué son, por qué son tan “mágicos” y a la vez tan sencillos, y cómo estructurar una aplicación de software para utilizar los objetos de forma adecuada.

Este también es un libro sobre Java: no es un libro específico que explica todo lo que hay que saber sobre Java, sino más bien una introducción suave pero completa al lenguaje, con especial énfasis en cómo hacer la transición desde un modelo de objetos a una aplicación Java funcional, algo que pocos libros, si es que hay alguno, ofrecen.

Objetivos de este libro
Mis objetivos al escribir este libro (y, espero, los suyos por comprarlo) son:
Hacer que se sienta cómodo con la terminología y los conceptos fundamentales orientados a objetos (OO).

Proporcionarle experiencia práctica con el modelado de objetos , es decir, con el desarrollo de un “plano” orientado a objetos que pueda usarse como base para construir posteriormente un sistema de software orientado a objetos.

Ilustre los conceptos básicos de cómo dicho modelo de objetos se traduce en una aplicación de software funcional (una aplicación Java, para ser específico, aunque las técnicas que aprenderá para el modelado de objetos se aplican igualmente bien a cualquier lenguaje OO).

Le ayudaremos a convertirse en un programador Java competente a lo largo del camino.

Si ya tienes experiencia con el lenguaje Java (pero no con los fundamentos de la programación orientada a objetos), es fundamental para que puedas utilizarlo con éxito que aprendas sobre sus raíces orientadas a objetos. Por otro lado, si eres nuevo en Java, este libro te ayudará a empezar de la mejor manera. De cualquier manera, este libro es una lectura obligada para cualquiera que desee dominar un lenguaje de programación orientado a objetos como Java.

Igualmente importante es que este libro no pretende...
Convertirse en un profesional del modelado de objetos de la noche a la mañana: como todas las habilidades avanzadas, sentirse totalmente cómodo con el modelado de objetos requiere dos cosas: una buena base teórica y mucha práctica. En este libro le doy las bases, incluida una introducción al lenguaje de modelado unificado (UML) , el estándar de la industria para representar un "plano" orientado a objetos de una aplicación de software. (UML se adoptó por primera vez como estándar para modelar sistemas de software orientados a objetos en 1997 y sigue siendo relevante hoy en día). Dicho esto, la única forma en que realmente llegará a ser competente en el modelado de objetos es participando en proyectos de desarrollo y modelado OO a lo largo del tiempo.

Mi libro le brindará las habilidades y, con suerte, la confianza para comenzar a aplicar técnicas de objetos en un entorno profesional, que es donde tendrá lugar su verdadero aprendizaje, particularmente si tiene un mentor con experiencia en OO que lo guíe en su primer proyecto de "fuerza industrial".

Le enseñaré “todo” lo que necesitará saber sobre Java: Java es un lenguaje muy rico, que consta de cientos de clases básicas y literalmente miles de operaciones que se pueden realizar con y mediante estas clases. Además, Oracle Corporation publica nuevas versiones del lenguaje Java cada año, pero la buena noticia es que las características clave de Java necesarias para representar un problema de software de una manera orientada a objetos adecuada no han cambiado con el paso de los años. Si Java ofrece una docena de formas alternativas de hacer algo en particular, explico una o dos formas que considero que se adaptan mejor al problema en cuestión, para que pueda apreciar cómo se hacen las cosas. No obstante, definitivamente verá suficiente del lenguaje Java en este libro para prepararlo para un rol como programador Java profesional.

Con los fundamentos que obtenga de este libro, estará preparado para apreciar un tratamiento más exhaustivo de Java, como el que ofrecen las muchas otras referencias de Java que se encuentran actualmente en el mercado, o una revisión más profunda de las técnicas de modelado de objetos a partir de una referencia UML en profundidad. Haremos recomendaciones de dichos libros en el Capítulo 15 .

¿Por qué es tan importante comprender los objetos para ser un programador OO exitoso?
Una y otra vez me encuentro con desarrolladores de software (en mi lugar de trabajo, en las oficinas de los clientes, en conferencias profesionales, en campus universitarios) que han intentado dominar un lenguaje de programación orientado a objetos (OOPL) como Java tomando un curso de Java, leyendo un libro sobre Java o instalando y usando un entorno de desarrollo integrado (IDE) de Java como Eclipse , IntelliJ IDEA , NetBeans o BlueJ . Sin embargo, hay algo que falta fundamentalmente en prácticamente todos estos enfoques: una comprensión básica de qué son los objetos y, lo que es más importante, el conocimiento de cómo estructurar una aplicación de software desde cero para aprovechar al máximo los objetos .

Imagina que te han pedido que construyas una casa y que conoces los conceptos básicos de la construcción de viviendas. De hecho, eres un constructor de viviendas de renombre mundial cuyos servicios tienen una gran demanda. Has construido casas de todos los estilos arquitectónicos posibles, utilizando todos los tipos de materiales de construcción conocidos: ladrillo, madera, piedra, metal, etc. Por lo tanto, cuando tu cliente te dice que quiere que utilices un nuevo tipo de material de construcción, que él te proporcionará, estás encantado de complacerlo.


El día en que se van a iniciar las obras, un camión se detiene en el lugar de las obras y descarga una gran pila de bloques de aspecto extraño con forma de estrella azul y agujeros en el medio. ¡Estás totalmente desconcertado! Has construido innumerables casas con materiales más conocidos, pero no tienes ni idea de cómo montar una casa con estrellas azules.


Rascándote la cabeza, sacas un martillo y unos clavos e intentas unir las estrellas azules como si estuvieras trabajando con madera, pero las estrellas no encajan muy bien. Luego intentas rellenar los huecos con el mismo mortero que usarías para unir los ladrillos entre sí, pero el mortero no se adhiere muy bien a las estrellas azules. Sin embargo, como estás trabajando con limitaciones de costo y tiempo para construir esta casa para tu cliente (y porque te da vergüenza admitir que, como experto constructor de viviendas, no sabes cómo trabajar con estos materiales modernos), sigues adelante. Al final, terminas con algo que parece (al menos en la superficie) una casa.


Su cliente viene a inspeccionar el trabajo y se queda muy decepcionado. Una de las razones por las que había elegido las estrellas azules como material de construcción era que son extremadamente eficientes energéticamente; pero, como ha utilizado clavos y mortero para ensamblarlas, han perdido gran parte de su capacidad inherente para aislar la casa.

Para compensar, su cliente le pide que reemplace todas las ventanas de la casa por ventanas de vidrio térmico de triple panel para que permitan que escape menos calor. ¡ En este punto, está entrando en pánico! Cambiar las ventanas requerirá que literalmente destroce las paredes, destruyendo la casa.

Cuando le dices esto a tu cliente, ¡se pone furioso ! Otro motivo por el que eligieron las estrellas azules como material de construcción fue por su modularidad y, por lo tanto, por su facilidad para adaptarse a los cambios de diseño; pero, debido a la forma ineficaz en que has ensamblado estas estrellas, también han perdido esta flexibilidad.


Lamentablemente, muchos programadores terminan creando una aplicación orientada a objetos sin la formación adecuada en las propiedades fundamentales de los componentes básicos de dicha aplicación, es decir, los objetos de software. Peor aún, la gran mayoría de los aspirantes a programadores orientados a objetos ignoran por completo la necesidad de comprender los objetos para programar en un lenguaje orientado a objetos. Por eso, comienzan a programar con un lenguaje como Java y terminan con un resultado que dista mucho de ser ideal: una aplicación que carece de flexibilidad cuando se produce una inevitable "corrección a mitad de camino" en respuesta a los requisitos cambiantes después de que se haya implementado la aplicación.

¿Para quién está escrito este libro?
¡Cualquiera que quiera sacar el máximo partido a un lenguaje de programación orientado a objetos como Java! Ha sido escrito para
Cualquiera que aún no se haya enfrentado a Java, pero quiera empezar con el pie derecho con el lenguaje.

Cualquiera que haya comprado alguna vez un libro sobre Java y lo haya leído fielmente, que comprenda los “bits y bytes” del lenguaje, pero que no sepa exactamente cómo estructurar una aplicación para aprovechar al máximo las características orientadas a objetos de Java.

Cualquiera que haya creado una aplicación Java, pero se haya sentido decepcionado por lo difícil que fue mantenerla o modificarla cuando se presentaron nuevos requisitos más adelante en el ciclo de vida de la aplicación.

Cualquier persona que haya aprendido algo previamente sobre modelado de objetos, pero no esté segura de cómo realizar la transición de un modelo de objetos a un código real en vivo (Java o de otro tipo).

La conclusión es que cualquiera que realmente quiera dominar un lenguaje OO como Java debe convertirse en un experto en objetos PRIMERO.

Para sacar el máximo provecho de este libro, debes tener algo de experiencia en programación; prácticamente cualquier lenguaje servirá. Debes comprender conceptos de programación simples como
Tipos de datos simples (enteros, de punto flotante, etc.)

Variables y su alcance (incluida la noción de datos globales)

Control de flujo (declaraciones “ if … then … else ”, bucles for /do/while, etc.)

¿Qué son los arrays y cómo utilizarlos?

El concepto de función/subrutina/procedimiento de software: cómo pasar datos y obtener resultados

Pero no es necesario que hayas tenido ningún contacto previo con Java. Y tampoco es necesario que hayas estado expuesto a objetos, ¡al menos en el sentido de software! Como aprenderás en el Capítulo 2 , los seres humanos naturalmente vemos el mundo entero desde la perspectiva de los objetos.

Incluso si ya ha desarrollado una aplicación Java completa, ciertamente no es demasiado tarde para leer este libro si aún no está seguro de los aspectos de los objetos a la hora de estructurar una aplicación; en última instancia, conocer los "porqués" de la orientación a objetos en lugar de simplemente la mecánica del lenguaje hace que alguien sea un mejor programador de Java. Es muy probable que vea algunos puntos de referencia familiares (en forma de ejemplos de código Java) en este libro, pero es de esperar que obtenga muchas nuevas perspectivas a medida que aprenda la lógica de por qué hacemos muchas de las cosas que hacemos cuando programamos en Java (o cualquier otro lenguaje de programación orientado a objetos, de hecho).

Debido a que este libro tiene sus raíces en cursos que enseño a nivel universitario, es ideal para usarse como libro de texto para un curso universitario de un semestre de duración o un curso avanzado de escuela secundaria, ya sea sobre modelado de objetos o programación Java.

¿Qué pasa si estás interesado en el modelado de objetos, pero no necesariamente en la programación Java?
¿Mi libro seguirá siendo de utilidad para usted? ¡Sin duda! Incluso si no tiene pensado dedicarse profesionalmente a la programación (como es el caso de muchos de mis estudiantes de modelado de objetos), he descubierto que estar expuesto a ejemplos de código escritos en un lenguaje orientado a objetos como Java realmente ayuda a consolidar los conceptos de objetos. Por lo tanto, le recomiendo que lea las partes 1 y 3 incluso si nunca tiene intención de poner las manos sobre el teclado para programar en Java después.

Cómo está organizado este libro
El libro está estructurado en torno a tres temas principales, como se detalla a continuación.

Parte 1: El ABC de los objetos
Antes de profundizar en los procedimientos de modelado de objetos y los detalles de la programación orientada a objetos en Java, es importante que todos hablemos el mismo idioma con respecto a los objetos. La Parte 1, que consta de los Capítulos 1 a 7 , comienza lentamente, definiendo los conceptos básicos que sustentan todos los enfoques de desarrollo de software, orientados a objetos o de otro tipo. Pero los capítulos avanzan rápidamente hacia una discusión de conceptos avanzados de objetos, de modo que, al final de la Parte 1, usted será un "experto en objetos".

Parte 2: Modelado de objetos 101
En la Parte 2 (capítulos 8 a 12 del libro) me centro en los principios subyacentes de cómo y, lo que es más importante, por qué hacemos lo que hacemos cuando desarrollamos un modelo de objetos de una aplicación: principios que son comunes a todas las técnicas de modelado de objetos. Es importante estar familiarizado con el UML, por lo que le enseñaré los conceptos básicos del UML y lo utilizaré para todos los ejemplos de modelado concretos de mi libro. Utilizando las técnicas de modelado presentadas en estos capítulos, desarrollaremos un "modelo" de modelo de objetos para un Sistema de Registro de Estudiantes (SRS) , cuya especificación de requisitos se presenta al final de esta introducción.

Parte 3: Traducir un “plano” de un objeto a código Java
En la Parte 3 del libro (capítulos 13 a 15 ) ilustro cómo convertir el modelo de objetos SRS que hemos desarrollado en la Parte 2 en una aplicación Java completamente funcional, para que sirva como capa de modelo en una aplicación de tres niveles, y también hablaremos conceptualmente sobre cómo se pueden aprovechar las tecnologías de terceros para proporcionar tanto una interfaz de usuario (conocida como capa de presentación o tier ) como persistencia de datos (conocida como capa de datos o tier ). El código fuente de SRS está disponible para descargar desde GitHub ( github.com/Apress/Beginning-Java-Objects-3e ), y le recomiendo encarecidamente que descargue y experimente con este código cuando llegue a ese capítulo.

La especificación de requisitos para el SRS está escrita en el estilo narrativo con el que se expresan a menudo los requisitos del sistema de software. Puede estar seguro de que podría crear una aplicación hoy para resolver este problema, pero al final de mi libro, debería sentirse mucho más seguro de su capacidad para crearla como una aplicación orientada a objetos . En el Apéndice se presentan tres estudios de caso adicionales (para un sistema de seguimiento de recetas médicas , un sistema de reserva de salas de conferencias y un sistema de reserva de aerolíneas , respectivamente); estos sirven como base para muchos de los ejercicios presentados al final de cada capítulo.

En el capítulo final se ofrecen sugerencias sobre cómo puede continuar con su proceso de descubrimiento orientado a objetos después de terminar mi libro. En ese capítulo, le proporciono una lista de libros recomendados que lo llevarán al siguiente nivel de competencia, según cuál sea su intención de aplicar lo que ha aprendido en mi libro.

Convenciones
Para ayudarle a aprovechar al máximo el texto y realizar un seguimiento de lo que sucede, hemos utilizado una serie de convenciones a lo largo del libro.

Por ejemplo:

Las notas se muestran de esta manera y reflejan información de fondo importante.

En cuanto a los estilos en el texto:
Cuando introducimos palabras importantes, las ponemos en negrita para resaltarlas.

Mostramos nombres de archivos, URL y código dentro del texto de la siguiente manera: objectstart.com .

Ponemos en negrita las líneas de código dentro de pasajes de código largos si queremos llamar su atención sobre esas líneas en particular:
// El uso de negrita se utiliza para llamar la atención sobre código nuevo o significativo:
Estudiante s = nuevo Estudiante();
// mientras que el código sin negrita es código que es menos importante en el
// contexto actual, o ya visto antes.
int x = 3;
Usamos fuente de código cursiva en lugar de regular para representar pseudocódigo :
// Este es el código real:
para (int i = 0; i <= 10; i++) {
    //¡Esto es pseudocódigo!
    Calcular la calificación del i-ésimo estudiante
}
¿En qué versión de Java se basa este libro?
Como se mencionó anteriormente, Oracle Corporation continúa lanzando nuevas versiones del lenguaje Java de manera regular. La buena noticia es que, como en mi libro me concentro únicamente en la sintaxis básica del lenguaje Java (características del lenguaje que han sido estables desde el inicio de Java), este libro no es específico de una versión. Las técnicas y los conceptos que aprenderá leyendo mi libro le serán igualmente útiles cuando aparezcan nuevas versiones de Java. Dicho esto, todos los ejemplos de código en BJO son compatibles con las versiones de Java 8 a 17. (En términos generales, las nuevas versiones del lenguaje Java son compatibles con versiones posteriores, lo que significa que el código escrito para una versión anterior del lenguaje se compilará correctamente en una versión más nueva).

Una última reflexión antes de empezar
Gran parte del material de mi libro (en particular, el comienzo de la Parte 1) puede parecer demasiado simplista para los programadores experimentados. Esto se debe a que gran parte de la tecnología de objetos se basa en principios básicos de ingeniería de software que se han puesto en práctica durante muchos años y, en muchos casos, simplemente se han reempaquetado de forma ligeramente diferente. De hecho, hay algunos trucos nuevos que hacen que los lenguajes orientados a objetos sean extremadamente poderosos y que eran prácticamente imposibles de lograr con lenguajes no orientados a objetos , por ejemplo, la herencia y el polimorfismo, sobre los que aprenderá más en los Capítulos 5 y 7 , respectivamente. (Estas técnicas se pueden simular a mano en un lenguaje no orientado a objetos, de la misma manera que los programadores podrían programar su propio sistema de gestión de bases de datos (DBMS) desde cero en lugar de utilizar un producto comercial como Oracle o SQL Server, pero ¿quién querría hacerlo?)

El mayor desafío para los programadores experimentados a la hora de dominar los objetos es reorientar la manera en que piensan sobre el problema que van a automatizar:
Los ingenieros de software/programadores que han desarrollado aplicaciones utilizando métodos no orientados a objetos a menudo tienen que “desaprender” ciertos enfoques utilizados en los métodos tradicionales de análisis y diseño de software.

Paradójicamente, a las personas que recién comienzan como programadores (o como modeladores OO) a veces les resulta más fácil aprender el enfoque OO para el desarrollo de software como su único enfoque.

Afortunadamente, la forma en que necesitamos pensar sobre los objetos cuando desarrollamos software resulta ser la forma natural en que la gente piensa sobre el mundo en general. Por lo tanto, aprender a “pensar” en objetos (y a programarlos en Java) es tan fácil como (Parte) 1, (Parte) 2, (Parte) 3.

El código fuente de este libro se puede encontrar en https://​github.​com/​Apress/​Beginning-Java-Objects-3rd-ed .

Caso práctico del sistema de registro de estudiantes (SRS)
ESPECIFICACIÓN DE REQUISITOS DEL SISTEMA DE REGISTRO DE ESTUDIANTES (SRS)
Se nos ha pedido que desarrollemos un sistema automatizado de registro de estudiantes (SRS). Este sistema permitirá a los estudiantes registrarse en línea para los cursos cada semestre, así como realizar un seguimiento del progreso del estudiante hacia la finalización de su título.

Cuando un estudiante se inscribe por primera vez en la universidad, utiliza el SRS para establecer un plan de estudios en cuanto a los cursos que planea tomar para satisfacer un programa de grado en particular y elegir un asesor docente. El SRS verificará si el plan de estudios propuesto satisface o no los requisitos del título que el estudiante está buscando. Una vez que se ha establecido un plan de estudios, durante el período de inscripción anterior a cada semestre, los estudiantes pueden ver el cronograma de clases en línea y elegir las clases a las que desean asistir, indicando la sección preferida (día de la semana y hora del día) si la clase es ofrecida por más de un profesor. El SRS verificará si el estudiante ha cumplido o no con los requisitos previos necesarios para cada curso solicitado consultando el expediente académico en línea del estudiante de los cursos completados y las calificaciones recibidas (el estudiante puede revisar su expediente académico en línea en cualquier momento).

Suponiendo que (a) se cumplen los requisitos previos para los cursos solicitados, (b) los cursos cumplen con uno de los requisitos del plan de estudios del estudiante y (c) hay lugar disponible en cada una de las clases, el estudiante queda inscrito en las clases.

Si se cumplen los puntos (a) y (b), pero no (c), el estudiante pasa a una lista de espera por orden de llegada. Si una clase o sección para la que estaba en lista de espera se vuelve disponible (ya sea porque otro estudiante ha abandonado la clase o porque se ha aumentado la capacidad de asientos para la clase), el estudiante queda inscrito automáticamente en la clase en lista de espera y se le envía un mensaje de correo electrónico a tal efecto. Es su responsabilidad abandonar la clase si ya no la desea; de lo contrario, se le facturará el curso.

Cualquier código fuente u otro material complementario al que hace referencia el autor en este libro está disponible para los lectores en GitHub a través de la página del producto del libro, ubicada en https://github.com/Apress/Beginning-Java-Objects-3e.

### Acerca del autor
Jacquie Barker
Jacquie es ingeniera de software profesional, autora y ex miembro de la facultad adjunta de la Universidad George Mason en Fairfax, Virginia, y de la Universidad George Washington en Washington, DC. Con más de 30 años de experiencia como desarrolladora de software y gerente de proyectos, Jacquie ha pasado los últimos 15 años enfocada en la tecnología de objetos y es competente como modeladora de objetos y programadora Java certificada por Sun Microsystems.

Jacquie obtuvo una licenciatura en Ciencias en ingeniería informática con los máximos honores del Case Institute of Technology/Case Western Reserve University en Cleveland, Ohio, y una maestría en Ciencias de la Computación, con énfasis en ingeniería de sistemas de software, de la Universidad de California, Los Ángeles. Posteriormente, realizó estudios de posgrado en tecnología de la información en la Universidad George Mason en Fairfax, Virginia. La fórmula ganadora de Jacquie para enseñar los fundamentos de los objetos sigue recibiendo elogios de lectores de todo el mundo, y Beginning Java Objects: From Concepts to Code ha sido adoptado por muchas universidades como un libro de texto clave en sus programas básicos de TI.

En lo personal, las pasiones de Jacquie incluyen a su esposo, Steve, y sus tres gatos, Walter, Rocky y Tanner; su trabajo como fundadora y directora ejecutiva de Pets Bring Joy, una organización de rescate de animales sin fines de lucro 501(c)(3) (visite pbj.org); y su reciente lanzamiento de un servicio de consultoría informática pro bono para organizaciones sin fines de lucro emergentes (visite probonoit.org). Puede comunicarse con Jacquie en jacquie.barker@gmail.com.

 
Acerca del revisor técnico
Manuel Jordán

es un desarrollador e investigador autodidacta que disfruta aprendiendo nuevas tecnologías para sus propios experimentos sobre la creación de nuevas integraciones entre ellas.
Manuel ganó el premio Springy 2010 : Campeón de la comunidad y Campeón de primavera 2013. En su poco tiempo libre, lee la Biblia y compone música con su bajo y guitarra.

Manuel considera que la formación y la capacitación constantes son muy valiosas para cualquier desarrollador, al igual que la refactorización y el testing. Manuel puede ofrecer estos servicios para su empresa gracias a su experiencia en Java y Spring.

Puedes contactarlo principalmente a través de su cuenta de Twitter @dr_pompeii.
