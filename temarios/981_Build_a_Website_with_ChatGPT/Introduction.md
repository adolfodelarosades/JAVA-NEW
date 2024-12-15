# Front Matter

## Prefacio

“¡Oh, un mundo nuevo y valiente, con tanta gente!”. Esta cita pertenece a la obra de William Shakespeare La tempestad y la pronuncia Miranda de niña cuando se encuentra con una multitud por primera vez. Es poco probable que hayas sido desterrado a una isla remota cuando eras niño, pero es posible que aún repitas las palabras de Miranda cuando te encuentres con alguna de las aplicaciones de inteligencia artificial (IA) actuales por primera vez. Es un mundo nuevo y valiente, sin duda, el que tiene chatbots de este tipo.

Al principio, herramientas como ChatGPT parecen maravillosas porque parecen ser bastante buenas para unir palabras. Pídele a ChatGPT que lo haga **`Write a Shakespearean sonnet that summarizes the plot of Cormac McCarthy's novel "The Road"`** y lo hará. No, el poema resultante no tendrá la calidad de Shakespeare, pero será entretenido. Pero después de un tiempo, este tipo de entretenimiento barato se vuelve aburrido y la mayoría de los usuarios de ChatGPT se preguntan algo como "¿Para qué es realmente útil ChatGPT?".

En general, es una pregunta difícil de responder, con una excepción: el código. ChatGPT es realmente útil para convertir instrucciones de texto en código de programación. En particular, ChatGPT es bueno para convertir texto en el código necesario para construir una página web. Esto es extraordinario y significa que ahora cualquiera puede crear una presencia en la web, incluso si no puede o no quiere aprender las complejidades del desarrollo web.

Sin embargo, esta nueva forma de acceder a la Web tiene un par de inconvenientes. En primer lugar, sí, ChatGPT es muy bueno para convertir texto en código de página web, pero solo si sabes cómo formular ese texto con instrucciones detalladas para que ChatGPT las siga. En segundo lugar, incluso una vez que ChatGPT haya generado con éxito todo el código que necesitas para una página web, aún necesitas guardar ese código en algún lugar y luego subirlo a la Web de alguna manera.

Puede que parezcan obstáculos muy difíciles de superar, pero ahí es donde entra en juego este libro. En las páginas siguientes, aprenderá no solo a utilizar ChatGPT como un profesional para obtener exactamente la página web que desea, sino también a guardar ese código y luego implementarlo en la web para que todo el mundo lo vea. Bienvenido, entonces, al nuevo y valiente mundo de la creación de su propio sitio web con la ayuda de ChatGPT.

### Acknowledgments

El ensayista y poeta estadounidense E.B. White describió una vez a un editor como “una persona que sabe más sobre escritura que los escritores, pero que ha escapado al terrible deseo de escribir”. Creo que esto es cierto no sólo porque E.B. White era una persona sabia, sino también porque he llegado a confiar en mis editores para que me hagan parecer un mejor escritor del que soy.

Estoy seguro de que los editores de novelas, memorias y demás tienen mucho trabajo para poner a punto sus manuscritos, pero dediquemos un momento a los pobres editores de libros de informática. Tienen que asegurarse de que un libro de informática se lea bien y no esté plagado de errores ortográficos y gramaticales, y también tienen que asegurarse de que el libro sea técnicamente preciso. ¿Por qué? Porque incluso el más mínimo descuido del autor (o editorial) podría dar como resultado un libro que siembre confusión y consternación en lugar de certeza y deleite.

La buena gente de Manning Publications se asegura de que cada libro se lea bien y sea preciso al someter cada manuscrito a un aluvión de revisiones, no solo por parte de profesionales editoriales sino también por un equipo de personas externas dedicadas. En lugar de un proceso en el que una cantidad de ojos de un solo dígito miran el manuscrito, un libro de Manning es examinado por docenas. ¿El resultado? El libro que estás leyendo contiene información precisa y relevante que ha pasado la prueba de algunos de los ojos y oídos más agudos del negocio. Sí, mi nombre puede ser el único que aparece en la portada, pero toneladas de personas tuvieron un papel importante en la creación de lo que aparece entre las portadas (ya sean físicas o virtuales). Esos revisores fueron Adam Wan, Andres Sacco, Andriani Stylianou, Ashwin Mhatre, Beardsley Ruml, Bruno Sonnino, Charles Lam, Drew Leon, Erim Ertürk, Ganesh Falak, Halil Karakose, James Coates, Jeff Smith, José Alberto Reyes Quevedo, Julien Pohie, Lars Pesch, Marvin Schwarze, Matteo Battista, Mikhail Karaashev, Ozren Harlovic, Radhakrishna MV, Ranjit Sahai, Rui Liu, Saravanan Muniraj, Steve Prior, Swapneelkumar Deshpande y Tony Holdroyd.

Muchas gracias al editor técnico Anirudh Prabhu, que es un experimentado desarrollador de interfaces de usuario con más de una década de experiencia en el campo. Su carrera ha estado marcada por logros notables, incluida la publicación de cuatro libros aclamados. Además, se ha desempeñado como revisor técnico de varios títulos de editoriales poco estimadas y ha asumido un papel activo en la configuración del futuro del desarrollo web mediante la creación de materiales de capacitación integrales para HTML, CSS y jQuery.

Me gustaría extender mi más cálido agradecimiento a la editora Marjan Bace, al editor de adquisiciones Brian Sawyer, a la editora de desarrollo Karen Miller, a la coordinadora de proyectos Malena Selić, a la editora de copia Tiffany Taylor y al resto del personal de producción de Manning que ayudó a que este libro se hiciera realidad.

Por último, también me gustaría agradecer a todas las personas que se tomaron el tiempo de revisar los primeros manuscritos del libro y de ofrecer comentarios y sugerencias. Sus pequeños aportes fueron muy apreciados.

### Acerca de este libro

En este libro, aprenderá a instruir a ChatGPT para que genere el código de página web necesario para implementar una página según sus especificaciones. No se requiere experiencia con ChatGPT ni con el desarrollo web. Todo lo que necesita saber se proporciona a medida que lo necesita y no encontrará discusiones técnicas extensas ni argumentos filosóficos en estas páginas. Mi objetivo es que pueda acceder a la web con la ayuda de ChatGPT y todo lo que se incluye en el libro está al servicio de ese objetivo. Si alguna vez quiso crear una página web pero no pudo o no quiso aprender a codificar, este libro lo ayudará con la poderosa ayuda de ChatGPT.

Supongo que tienes una vida fuera de la pantalla de tu computadora, por lo que este libro está organizado de tal manera que no tienes que leerlo de principio a fin. Si recién estás comenzando, lee el capítulo 1 para obtener una base sólida y luego intenta el proyecto simple del capítulo 2 para obtener una página web generada por ChatGPT. A partir de allí, puedes intentar cualquiera de los proyectos de los capítulos 3 a 12 en cualquier orden. Para que sea más fácil de encontrar, la sección "Cómo está organizado este libro: una hoja de ruta" te brinda un resumen de los 13 capítulos del libro (y 3 apéndices).

### ¿Quién debería leer este libro?

Este libro está dirigido, en primer lugar, a todo aquel que quiera crear una presencia en la web, ya sea una humilde página de inicio, una página para mostrar un pasatiempo o un interés, o un sitio web para un club de lectura, un evento, una organización o un equipo. Más específicamente, este libro está dirigido a tres tipos de lectores:

* Alguien que no sabe cómo codificar páginas web y no quiere aprender: los detalles del desarrollo web han sido durante mucho tiempo una barrera para muchas personas que quieren establecerse en la web. Este libro tiene como objetivo mostrar cómo ChatGPT cambia todo eso para las personas que no tienen interés en aprender a codificar.

* Alguien que no sabe cómo codificar páginas web y quiere aprender: este libro se centra principalmente en las instrucciones que debe proporcionar a ChatGPT para que genere el código de página web que desea. Sin embargo, también doy algunos antecedentes sobre cada una de las tecnologías de código de página web utilizadas en el libro. Combine ese conocimiento de fondo con el enfoque práctico de este libro para los proyectos y aprenderá bastante sobre el desarrollo web.

* Alguien que sepa cómo codificar páginas web: incluso si ya conoce al menos los conceptos básicos del desarrollo web, puede usar ChatGPT para acelerar su trabajo de desarrollo y puede delegar algunas de las tareas más tediosas a ChatGPT. Este libro le muestra las indicaciones que puede usar para convencer a ChatGPT de que sea su asistente de programación.

### Cómo está organizado este libro: una hoja de ruta

El ***capítulo 1*** le presenta ChatGPT en general y, en particular, el uso de ChatGPT para generar código de páginas web. Aprenderá qué tipos de páginas puede crear con la ayuda de ChatGPT y obtendrá una visión general del proceso.

El ***capítulo 2*** te lleva a un viaje para crear e desplegar tu primera página web con la ayuda de ChatGPT. Aprenderás a solicitarle a ChatGPT que genere el código, lo copie y lo guarde en un archivo. A partir de ahí, probarás el código en un navegador web y luego lo implementarás de forma gratuita en la web.

El ***capítulo 3*** muestra cómo solicitar a ChatGPT que utilice fuentes, colores y encabezados en una página web. Aprenderá a solicitarle a ChatGPT que le proporcione sugerencias para el título y el eslogan de su sitio, las fuentes que debe utilizar y el esquema de colores que debe aplicar. Luego, reunirá todo esto en un mensaje que le solicite a ChatGPT que genere el código para una página de inicio personal.

El ***capítulo 4*** se centra en la estructura de una página web, por lo que aprenderá sobre encabezados, pies de página, relleno, bordes y márgenes. También aprenderá a agregar imágenes y enlaces a redes sociales a la página. El capítulo culmina con la solicitud a ChatGPT para que proporcione el código para crear una página de club de lectura.

El ***capítulo 5*** cubre la publicación de publicaciones en una página, así como el uso de IA para convertir mensajes de texto en imágenes. Todo esto se combina en un mensaje que le indica a ChatGPT que genere el código para una página de diario en línea.

El ***capítulo 6*** trata sobre enlaces y navegación. Aprenderá cómo funciona el código de enlaces para que pueda crear enlaces manualmente en lugar de pedirle siempre a ChatGPT que lo haga. También aprenderá a indicarle a ChatGPT que cree una barra de navegación de páginas con enlaces a otras páginas del sitio. El proyecto de este capítulo es un sitio de información.

El ***capítulo 7*** examina la destreza de escritura de ChatGPT mientras aprendes cómo pedirle ideas a Chatbot sobre temas, pautas de escritura y sugerencias de investigación. Incluso aprendes la mejor manera de pedirle a ChatGPT que escriba con tu propia voz. Más adelante en el capítulo, construyes una solicitud para que ChatGPT genere el código para una página de interés o pasatiempo.

El ***capítulo 8*** le proporciona las herramientas que necesita para indicarle a ChatGPT que cree formularios de páginas web que incluyan cuadros de texto, casillas de verificación, botones de opción, listas y más. También aprenderá a registrarse en un servicio que le permite recibir datos de formularios enviados a su dirección de correo electrónico. Todo esto se combina en un mensaje que le pide a ChatGPT que genere el código para una página de registro de eventos.

El ***capítulo 9*** presenta dos características comunes de las páginas web: listas con viñetas y listas numeradas. Aprenderá a indicarle a ChatGPT que cree estas listas y aprenderá varias formas de personalizarlas para que se adapten a sus necesidades. El capítulo concluye solicitando a ChatGPT el código para crear una página de recetas.

El ***capítulo 10*** le ofrece una visión más detallada del trabajo con imágenes en una página web. Aprenderá a codificar imágenes manualmente, a utilizar imágenes de marcador de posición y a trabajar con versiones en miniatura de las imágenes. El proyecto del capítulo es una página de galería de fotos sofisticada.

El ***capítulo 11*** le presenta uno de los patrones de páginas web más populares: la card-tarjeta, que puede utilizar para mostrar elementos como obras de arte, pasatiempos, personas o eventos. Puede aprovechar este conocimiento sobre tarjetas al obtener ChatGPT para ayudarlo a crear el proyecto de este capítulo: una página de portafolio.

El ***capítulo 12*** le ofrece un tutorial completo sobre el uso de etiquetas de diseño de páginas web, además de mostrarle cómo marcar palabras importantes y cómo enfatizar palabras en la página. También aprenderá una técnica eficaz para lograr que sus páginas se vean bien en pantallas más pequeñas. El proyecto de este capítulo es una página que muestra un artículo extenso con una barra lateral.

El ***capítulo 13*** presenta las páginas web basadas en datos, donde la mayor parte del contenido de la página se procesa desde un archivo de datos independiente. Primero aprenderá cómo lograr que ChatGPT cree el archivo de datos a partir de sus datos de Excel. Luego aprenderá cómo permitir que sus usuarios interactúen con los datos filtrándolos, ordenándolos y buscándolos. El proyecto de este capítulo es una página que muestra un catálogo de cursos en línea para una universidad ficticia.

El ***Apéndice A*** le proporciona información básica útil para prepararse para usar ChatGPT para crear páginas web. Aprenderá a configurar una cuenta de ChatGPT, a probar su código y a trabajar con archivos de páginas web.

El ***Apéndice B*** está dedicado a poner en línea el código web. Aprenderá a implementar el código en dos sitios gratuitos (Netlify y Cloudflare) y en otros sitios.

El ***Apéndice C*** mejora su juego ChatGPT al guiarlo a través de una extensa lista de mejores prácticas para activar ChatGPT y manejar cualquier error que surja.

### Acerca del código

No es de sorprender que un libro sobre cómo conseguir que un chatbot de IA genere código de página web contenga bastante código. Para ayudar a diferenciar el código de la página web del resto del texto, a lo largo de este libro, el código está formateado en un fixed-width font. El libro también tiene muchos listados de códigos separados. En estos listados, he intentado, en la medida de lo posible, que cada línea se ajuste al ancho de página disponible. Sin embargo, hay algunos casos en los que una línea es demasiado larga para ajustarse al ancho de página, por lo que la línea se traslada a una segunda línea, y esa segunda línea está precedida por un marcador de continuación de línea ( ➥ ).

Puede sentirse tentado a describir la cantidad de código generado por ChatGPT en este libro como desalentador si está operando bajo el supuesto de que va a necesitar escribir todo ese código a mano. ¡No es así! Todo el código de la página web del libro, así como todos los mensajes de ChatGPT del libro, están disponibles para ver, descargar y copiar como crea conveniente desde el repositorio de GitHub del libro en https://github.com/paulmcfe/websites-with-chatgpt. Para descargar todo, haga clic en el botón verde Código y luego haga clic en Descargar ZIP. De lo contrario, haga clic en un capítulo y luego haga clic en el archivo que desea ver.

Puede obtener fragmentos de código ejecutables de la versión liveBook (en línea) de este libro en https://livebook.manning.com/book/build-a-website-with-chatgpt. El código completo de los ejemplos del libro también está disponible para descargar desde el sitio web de Manning en www.manning.com/books/build-a-website-with-chatgpt .

### Foro de discusión de LiveBook

La compra de *Build a Website with ChatGPT* incluye acceso gratuito a liveBook, la plataforma de lectura en línea de Manning. Con las funciones de discusión exclusivas de liveBook, puede adjuntar comentarios al libro de manera global o a secciones o párrafos específicos. Es muy fácil tomar notas, hacer y responder preguntas técnicas y recibir ayuda del autor y otros usuarios. Para acceder al foro, visite https://livebook.manning.com/book/build-a-website-with-chatgpt/discussion. También puede obtener más información sobre los foros de Manning y las reglas de conducta en https://livebook.manning.com/discussion.

El compromiso de Manning con nuestros lectores es ofrecer un espacio donde pueda tener lugar un diálogo significativo entre lectores individuales y entre lectores y el autor. No se trata de un compromiso a una cantidad específica de participación por parte del autor, cuya contribución al foro sigue siendo voluntaria (y no remunerada). Le sugerimos que intente hacerle algunas preguntas desafiantes al autor para que no se desvíe de su interés. El foro y los archivos de discusiones anteriores estarán accesibles desde el sitio web de la editorial mientras el libro esté impreso.

### Acerca del autor

Paul McFedries ha sido un escritor técnico profesional durante más de 30 años. Tiene más de 100 libros en su haber, que en conjunto han vendido más de 4 millones de copias en todo el mundo. Su otro título de Manning es Web Design Playground, Second Edition. Cuando no está escribiendo libros, Paul está creando páginas web, lo que ha estado haciendo desde 1996, y tiene un conocimiento profundo de HTML y CSS. Paul ha codificado a mano muchos sitios, incluido su página de inicio web ( https://paulmcfedries.com ), Word Spy ( https://wordspy.com ), WebDev Workshop ( https://webdevworkshop.io ) y Web Design Playground ( https://webdesignplayground.io/2 ). A Paul le encanta enseñar, su escritura es clara y lógica, y tiene la empatía que surge de recordar cómo fue aprender un tema por primera vez.
