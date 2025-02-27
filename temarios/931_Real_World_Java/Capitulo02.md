# 2. Conozca su IDE: el secreto del éxito

**¿QUÉ HAY EN ESTE CAPÍTULO?**

* Comprender la historia de IDE
* Comenzando un nuevo proyecto
* Creación de una configuración de ejecución
* Conozca los atajos del teclado
* Depuración de su código
* Refactorizando su código
* Explotando al editor
* Ampliación del IDE
* Mirando hacia Eclipse
* Echando un vistazo a VS Code
* Comparación de IDE

Ya seas carpintero o programador, la primera decisión crítica que tomarás será la selección de herramientas. Elegir tu entorno de desarrollo integrado (IDE) y conocerlo bien será una de las cosas más importantes que harás en tu carrera como programador.

En los primeros tiempos de Java, uno podía leer una copia de la API de Java, un libro de 200 páginas que contenía todo lo que necesitaba saber para hacer grandes cosas. Hoy en día, necesitaría una docena de libros de 500 páginas para entender lo mismo. O bien, podía ahorrar algo de tiempo y confiar en su IDE para obtener asistencia y orientación profesional.

En este capítulo, analizaremos los tres grandes IDE (**IntelliJ**, **Eclipse** y **Visual Studio Code**) y cubriremos los siguientes temas:

* **Conozca los atajos de teclado**: su IDE es una herramienta de productividad y, a menudo, puede identificar a los profesionales de la codificación por el uso de atajos de teclado. Hay muchos, pero en esta sección, analizaremos algunos de los más importantes y cómo aprenderlos, y le mostraremos cómo descubrir más.
* **Refactorización de código profesional**: si haces tantas revisiones de código como las que hemos hecho nosotros, podrás detectar fácilmente a los no profesionales por la forma en que repiten fragmentos de código en toda su base de código. Verás cómo tu IDE puede ayudarte a localizar y corregir el código "copiado y pegado".
* **Otras perlas de productividad**: ¡No olvides que el objetivo principal de tu IDE es la *edición*! Revisaremos algunas funciones de edición potentes y menos conocidas.

Este capítulo no pretende ser una guía completa de todas las funciones. Puede obtenerla en los manuales de usuario. En lugar de ello, haremos hincapié en las técnicas para aprovechar las funciones de su IDE y mejorar enormemente su productividad.

<hr>

**DESCARGAS DE CÓDIGOS PARA ESTE CAPÍTULO**

El código fuente de este capítulo está disponible en la página del libro en www.wiley.com. Haga clic en el enlace Descargas. El código también se puede encontrar en https://github.com/realworldjava/Ch02-IDEs. Consulte el README.mdarchivo en ese repositorio para obtener más detalles.

<hr>

## COMPRENDIENDO LA HISTORIA DE IDE

Hay un viejo dicho que aconseja no hablar nunca de religión o política en compañía de otras personas. A eso deberíamos añadir el hecho de hablar de tu IDE favorito. Pero en los círculos de élite, el IDE de elección parece ser **IntelliJ IDE**. “¿Por qué?”, te preguntarás.

Para responder a esta pregunta, repasemos un poco la historia. Cuando Java apareció por primera vez en escena, había algunos IDE populares llamados **Symantec Visual Café** (el primer IDE de Java), **Microsoft Visual J++**, **Borland JBuilder** y una variedad de otras ofertas especializadas. Estos IDE ofrecían funciones como la finalización de código y una serie de detalles interesantes diseñados para ayudar a los desarrolladores a abrirse paso entre la maleza cada vez más compleja.

**Visual J++** habría ganado la batalla de los IDE si no hubiera sido por la batalla más grande que tuvieron con el fundador de Java, Sun Microsystems, que finalmente resultó en su propio lenguaje de bytecode **C#** y la repentina retirada de Visual J++ del planeta. Pero las guerras de los IDE estallaron cuando aparecieron el proyecto gratuito **Eclipse**, respaldado por la industria, y el propio **NetBeans** de Sun Micro (también gratuito), seguidos poco después por el súper ingenioso **IntelliJ Idea**, una oferta paga con muchas funciones de una empresa llamada JetBrains.

Veinticinco años después, **IntelliJ** y **Eclipse** siguen innovando, y **Microsoft Visual Studio** ahora ofrece compatibilidad con Java y ha estado creciendo de manera constante, especialmente entre los desarrolladores jóvenes o aquellos que comenzaron con otros lenguajes como JavaScript o Python. Hace algunos años, **IntelliJ** presentó una **"edición comunitaria" (CE)** gratuita para competir con las otras ofertas gratuitas. CE incluye la mayoría de las características que la gente usa todos los días, siendo la excepción más notable su falta de integración especial con Spring; todavía funciona con Spring, por supuesto, *pero si desea la rica experiencia Spring al estilo IntelliJ, le piden que pague.

En nuestra humilde opinión, IntelliJ tiene una característica destacada: está muy centrado en la experiencia del desarrollador, por lo que el IDE puede hacer casi cualquier cosa que puedas imaginar. Hay muchas capacidades, como puedes ver al mirar los menús.Hay un localizador de código integrado que encuentra código duplicado en distintos archivos, incluso en una base de código grande, y las refactorizaciones son siempre intuitivas, precisas y confiables. Dicho esto, Eclipse todavía se usa ampliamente y Visual Studio ha estado creciendo tanto en capacidad como en tracción.

En este capítulo, analizaremos los tres grandes IDE, empezando por IntelliJ y concluyendo con las diferencias importantes entre él, Eclipse y Visual Studio. ***En el resto de este libro, utilizaremos principalmente IntelliJ***. No obstante, si eres un usuario fiel de Eclipse o VS Code, gran parte de esta discusión se traducirá fácilmente, diferenciándose principalmente en los atajos de teclado y las ofertas de menú. IntelliJ proporciona un atajo de teclado para todas sus funciones importantes, y puedes agregarlos y modificarlos como quieras. También puedes seleccionar un tema de Eclipse que tome prestados muchos de esos atajos, en caso de que tengas una amplia experiencia con Eclipse. Los otros IDE también proporcionan asignaciones de teclas básicas listas para usar y te permiten crear tus propias asignaciones personalizadas. Pero si disfrutas del poder de los atajos de teclado, descubrirás que IntelliJ ofrece la mayor selección de estos de forma predeterminada.

<hr>

**TIP** :  Cuando inicie IntelliJ, aparecerá una ventana con sugerencias sobre funciones. ¡Léalas!

<hr>

Existen versiones de los tres IDE principales disponibles para Windows, Mac y Linux. Cuanto más potente sea su computadora, más rápido y con mayor capacidad de respuesta será su IDE. Consulte la sección “Más referencias” para descargar un nuevo IDE si desea probar uno diferente al que está acostumbrado.

Comencemos analizando IntelliJ. Recuerde leerlo incluso si planea usar Eclipse o VS Code, ya que esas secciones suponen que ha leído el capítulo completo. Es, sin duda, nuestro IDE favorito y, quién sabe, ¡quizás incluso decida probar IntelliJ una vez que vea lo que puede hacer!

## INICIANDO UN NUEVO PROYECTO

Cuando desee iniciar un nuevo proyecto, puede elegir entre varias opciones, como se muestra en la Figura 2.1 .

![image](https://github.com/user-attachments/assets/a35e64a2-0474-4095-8e14-99a0e4b23212)

**FIGURA 2.1 :Creación de un nuevo proyecto**

### Creando un proyecto desde cero

Para crear un proyecto desde cero, seleccione Proyecto en el menú. Se mostrará una lista grande de tipos de proyectos para que elija, como se muestra en la Figura 2.2 . Realice su selección en función del tipo de proyecto. Al comenzar, deberá seleccionar New Project para crear un proyecto mínimo con solo una clase principal.

![image](https://github.com/user-attachments/assets/ea7879b7-c2d8-4b76-8efd-326ee475744d)

**FIGURA 2.2: Creación de una nueva aplicación desde cero**

AQUIIIIIIIIIIIIII

Hay muchas otras opciones, incluida la de si desea utilizar una herramienta de compilación, que se cubre en profundidad en el Capítulo 4 , “Automatización de sus compilaciones CI/CD con Maven, Gradle y Jenkins”.

NOTA:  Una vez que aprenda sobre Spring Boot en el Capítulo 6 , “Conociendo el marco Spring”, a menudo elegirá el tipo Spring Initializer.

Creación de un proyecto a partir de fuentes existentes
También puede importar el código fuente desde un directorio existente a IntelliJ seleccionando Proyecto desde fuentes existentes y apuntando al directorio que contiene el proyecto existente. IntelliJ hace un gran trabajo al ubicar sus herramientas de compilación, pruebas, etc., y preparar todo para que usted lo ejecute.

SUGERENCIA:  Crear un proyecto a partir de fuentes existentes es particularmente útil si está cambiando desde otro IDE como Eclipse o si está usando una herramienta de compilación y ya tiene los directorios en su máquina.

Creación de un proyecto desde el control de versiones
Cuando trabajas en un proyecto con un equipo, lo más frecuente es que importes un proyecto existente desde el control de versiones. Para ello, clonarás un repositorio remoto. (Para obtener más información sobre la clonación de un repositorio, consulta el Capítulo 3 , “Colaboración en toda la empresa con Git, Jira y Confluence”).

Cómo agregar un proyecto al control de versiones
En la mayoría de los casos, clonarás un proyecto existente, pero cada proyecto tiene un inicio y, si ese es el caso, deberás agregar tu nuevo proyecto al control de versiones después de crearlo. Para ello, realiza los siguientes pasos. (Usamos GitHub, pero el proceso es similar para otros tipos de repositorios. Para obtener más información sobre Git, consulta el Capítulo 3 ).

En su navegador, cree un repositorio en GitHub y obtenga la URL.
En IntelliJ, seleccione el elemento de menú VCS ➪ Habilitar integración de control de versiones en el menú desplegable.
Seleccione un sistema de control de versiones (en nuestro caso Git).
Agregue algunos archivos a su proyecto y quizás un README.mdarchivo.
Seleccione el elemento de menú Git ➪ Confirmar.
Ahora haz un push al control remoto (selecciona el menú Git ➪ Push, o presiona Ctrl+Shift+K/Cmd+Shift+K).
En la ventana Push Commits, haga clic en el botón Definir remoto.
Ahora puedes navegar a la URL que proporcionaste, donde encontrarás tu código, como se muestra en la Figura 2.3 .


FIGURA 2.3 :Definición de Git Remote

Cómo agregar un módulo a un proyecto existente
Es común tener varios servicios (que son esencialmente aplicaciones distintas) que prestan servicio a una sola aplicación. En tales casos, es posible que desee que esos servicios residan en un proyecto maestro. Para lograrlo, puede elegir el elemento de menú Archivo ➪ Nuevo módulo o Archivo ➪ Nuevo módulo a partir de fuentes existentes, que ofrece opciones similares a las del elemento de menú Archivo ➪ Nuevo proyecto.

CREACIÓN DE UNA CONFIGURACIÓN DE EJECUCIÓN
Existen muchas formas de ejecutar el main()método de una clase. Si bien todas requieren una configuración de ejecución (que contiene la clase principal, los argumentos de tiempo de ejecución, la versión de Java que se utilizará, etc.), IntelliJ creará una para usted con valores predeterminados si simplemente ejecuta la aplicación. Para ejecutar la aplicación, puede realizar una de las siguientes acciones:

Haga clic en la flecha verde a la izquierda del nombre de la clase, como se muestra en la Figura 2.4 .
Haga clic en la flecha verde a la izquierda del main()método.
Haga clic derecho en el editor de clases.

FIGURA 2.4 :Ejecución y depuración

Todas estas opciones le ofrecen la opción de elegir Ejecutar en el menú contextual, lo que creará una configuración de ejecución predeterminada. (La depuración también es una opción. Consulte la sección “Depuración del código” para obtener más información sobre la depuración). Todas estas opciones también le ofrecen la opción Modificar la configuración de ejecución, posiblemente en un submenú que le permite especificar los detalles de su configuración de ejecución.

Como alternativa, puede hacer clic en Archivo actual en la parte superior y elegir Editar configuraciones en el menú desplegable que aparece ( Figura 2.5 ). A pesar del nombre, tiene la opción de agregar una nueva configuración de tiempo de ejecución además de editar las existentes.


FIGURA 2.5 :Edición de la configuración

Seleccione un tipo de aplicación adecuado (por ejemplo, Aplicación para una aplicación Java estándar). Consulte la Figura 2.6 .


FIGURA 2.6 :Agregar una configuración de aplicación

Luego complete el formulario de configuración ingresando una clase principal, una versión de Java, etc., como en la Figura 2.7 .

Si está en una clase de prueba (anotada con @Test; consulte el Capítulo 7 , “Cómo probar su código con herramientas de prueba automatizadas”), puede hacer clic en la flecha verde junto a cualquier método de prueba y seleccionar la opción Ejecutar.


FIGURA 2.7 :Adición de unmain()método

CONOZCA LOS ATAJOS DE TECLADO
Sea cual sea el IDE que le resulte más cómodo, nuestro consejo es que aprenda los atajos y los utilice. ¿Cómo se hace eso? Cada vez que busque una función en el menú, mire el atajo de teclado para esa función (que aparece a la derecha del elemento del menú, como se muestra en la Figura 2.8 ), luego cierre el menú y utilice el atajo. Comience con las funciones que utiliza con más frecuencia hasta que sus dedos las recuerden sin pensar.


FIGURA 2.8 :Uso de menús para descubrir atajos de teclado

Por ejemplo, para obtener una lista de los archivos en los que ha trabajado recientemente, presione Ctrl+E/Cmd+E. Le llevará varias veces recordarla, así que siga estos consejos:

Búscalo en el menú.
Cerrar el menú.
Utilice el atajo.
SUGERENCIA  Muchos atajos difieren entre Windows y Mac. Cuando eso sucede, escribimos el atajo de Windows seguido de una barra y luego la versión de Mac. Si usa Linux, siga los atajos de Windows, ya que suelen ser los mismos.

En las siguientes secciones, verá muchos atajos útiles. Habrá otros a lo largo del capítulo a medida que cubramos temas específicos. Después de un breve período, los atajos del teclado se habrán grabado en su memoria y notará que su productividad aumenta considerablemente.

Navegando por su base de código
Quiere poder navegar por su código base sin hacer demasiados clics con el mouse. El IDE lo hace fácil.

Para abrir un archivo de clase en IntelliJ, utilice el atajo Ctrl+N/Cmd+O. No necesita escribir el nombre de archivo completo, e incluso puede utilizar el método CamelCase para ingresar prefijos para partes del nombre. Por ejemplo, la Figura 2.9 muestra cómo puede buscar el comienzo de Order Processor escribiendo .OrPro


FIGURA 2.9 :Navegación a una clase

De manera similar, puede abrir un archivo que no sea un archivo de clase utilizando el atajo Ctrl+Shift+N/Cmd+Shift+O. Y puede buscar un nombre de método o un nombre de variable de clase/instancia utilizando Ctrl+Alt+Shift+N/Cmd+Option+O. La Figura 2.10 utiliza la técnica de mayúsculas y minúsculas para buscar el método sendEma il Confirmation escribiendo sendEmaCon.


FIGURA 2.10 :Navegación hacia un símbolo

Puedes navegar hasta la última posición que hayas visitado, y luego a la anterior, y así sucesivamente, usando Ctrl+Alt+Flecha izquierda/Cmd+[. Luego, puedes navegar hacia adelante usando Ctrl+Alt+Flecha derecha/Cmd+].

Puedes navegar hasta la última posición de edición usando Ctrl+Shift+Backspace/Cmd+Shift+Backspace. Si bien eso te permite retroceder a través de las ediciones recientes, no hemos visto un atajo para avanzar después. Como solución alternativa, puedes mover el cursor a cualquier lugar y luego la siguiente combinación de Ctrl+Shift+Backspace/Cmd+Shift+Backspace comenzará nuevamente desde la posición de edición más reciente.

Si desea buscar usos de un método determinado, puede hacer clic en el nombre del método mientras mantiene presionada la tecla Ctrl/Cmd para obtener una ventana emergente con esta información. También puede usar Alt+F7/Opción+F7 para ver la lista en una ventana en la parte inferior de su IDE.

Puede crear su propia navegación personalizada mediante marcadores. En IntelliJ, Ctrl+Shift+1 (o cualquier número del 1 al 9) establecerá un marcador numerado en la ubicación del cursor. Luego, puede regresar a ese marcador utilizando Ctrl+1 (o el número que haya utilizado para crear el marcador). ¡Estos son algunos de los pocos atajos que son iguales en Windows y Mac!

Para obtener un esquema rápido de la API del archivo actual, utilice Ctrl+F12/Cmd+F12, como se muestra en la Figura 2.11 . Puede hacer clic dentro del esquema para ir directamente a esa parte del archivo.


FIGURA 2.11 :Vista de esquema

Copiar y pegar atajos
¿Copiar y pegar? Ya sabes cómo hacerlo. Sin embargo, Ctrl+C/Cmd+C funciona de forma diferente a lo que estás acostumbrado con otras herramientas. La filosofía de IntelliJ es no perder el tiempo intentando seleccionar una línea entera; simplemente coloca el cursor en la línea que quieres copiar, pulsa Ctrl+C/Cmd+C y la línea entera se copiará en el portapapeles. Por supuesto, si quieres copiar parte de una línea o varias líneas, puedes seleccionarlas como siempre y pulsar Ctrl+C/Cmd+C.

Para cortar toda la línea, se utiliza Ctrl+X/Cmd+X. Nuevamente, sin seleccionar nada, se corta toda la línea del cursor y se guarda en el portapapeles.

Para recuperar el portapapeles, Ctrl+V/Cmd+V funciona en IntelliJ igual que en otras herramientas. Sin embargo, la combinación más útil Ctrl+Shift+V/Cmd+Shift+V muestra el historial del portapapeles y le permite seleccionar qué corte del portapapeles desea pegar, como se muestra en la Figura 2.12 .

Código de reordenamiento
A continuación, pruebe las combinaciones únicas Ctrl+W/Opción+Flecha arriba y Ctrl+Shift+W/Opción+Flecha abajo. Cada vez que presione Ctrl+W/Opción+Flecha arriba, comenzará en el cursor y seleccionará un alcance creciente: primero una palabra, luego una frase, luego un bloque, un método, una clase, etc. Ctrl+Shift+W/Opción+Flecha abajo invierte el orden y lo lleva de regreso a un clic.a la vez a su selección original. Si aplica Ctrl+W/Opción+Flecha arriba a una expresión aritmética, cada Ctrl+W/Opción+Flecha arriba selecciona en el orden en que se calculará.


FIGURA 2.12 :Menú contextual de Pegado especial

Hay un truco para seleccionar un método completo en dos clics, y es colocar el cursor en cualquier espacio a la izquierda del nombre del método y presionar Ctrl+W/Option+Flecha arriba dos veces. Otro clic seleccionará Javadoc y anotaciones. Esto es muy útil para reordenar los métodos en el código, porque con el método completo seleccionado, puede usar Ctrl+Shift+Flecha arriba/Cmd+Shift+Flecha arriba y Ctrl+Shift+Flecha abajo/Cmd+Shift+Flecha abajo para mover el método hacia arriba o hacia abajo en el archivo, más allá del siguiente método por encima o por debajo de él, y también moverá cualquier Javadoc junto con él. (¡El buen código se autodocumenta; el gran código tiene un gran Javadoc!)

Cómo usar otros atajos útiles
Primero vienen tres atajos cuando se trabaja con líneas.

Ctrl+D/Cmd+D duplica la línea actual.
Ctrl+Y/Cmd+Retroceso elimina la línea actual.
Ctrl+Alt+Flecha arriba/Opción+Mayús+Flecha arriba y Flecha abajo mueven la línea actual hacia arriba o hacia abajo, respectivamente.
A continuación, cuando desee encontrar errores y advertencias en su código, utilice F2 para encontrar los que están después del cursor y utilice Shift+F2 para navegar hacia atrás lejos del cursor.

El atajo Alt+Enter/Option+Enter abre un menú contextual. Por ejemplo, puede usarlo para corregir un error del compilador o generar código para su clase.

Cada IDE tiene sus propios atajos de teclado. En esta sección, hemos visto algunos ejemplos de algunos de los atajos de teclado más útiles y, a medida que vayamos cubriendo más funciones, mencionaremos los atajos relacionados. Está más allá del alcance de este libro cubrir todos los atajos, pero le animamos a que los explore y los domine. Puede obtener la lista completa desde el IDE de su sistema operativo: seleccione el elemento de menú Ayuda ➪ Atajos de teclado PDF. Anímese a aprender atajos. El dominio de los atajos de teclado le convertirá en un programador mejor, más rápido y más profesional.

ATAJOS META
IntelliJ tiene una filosofía de “primero el teclado”, lo que genera algunos atajos muy poderosos. Afortunadamente, hay tres atajos más generales que conviene aprender a medida que se dominan otros más específicos.

Shift+Shift abre una función llamada Buscar en cualquier lugar. Es una forma rápida de buscar archivos o símbolos o incluso acciones de IntelliJ.
Control+Control abre la función Ejecutar cualquier cosa, que le permite ejecutar cosas como un método principal o una prueba.
Ctrl+Shift+A/Cmd+Shift+A abre la posibilidad de buscar cualquier acción. Este es un subconjunto de Shift+Shift, pero resulta útil para ir directamente a esa lista.
DEPURACIÓN DEL CÓDIGO
El verdadero poder de su IDE comienza a emerger cuando utiliza el depurador. El depurador le permite establecer puntos de interrupción en su código de modo que cuando su programa alcance un punto de interrupción, pausará la ejecución. Inicie su programa en modo de depuración y, cuando el código alcance un punto de interrupción, se pausará, lo que le permitirá ver los valores actuales de las variables que están visibles en el ámbito actual. Puede cambiar los valores. Desde allí, puede avanzar un paso a la vez o hacer que la ejecución continúe hasta el siguiente punto de interrupción. O puede ingresar a un método o pasar por encima o salir de un método. También le permite navegar por la pila de llamadas , lo que le permite ver las variables disponibles para los métodos que llamaron al que está en el punto de interrupción. La depuración es valiosa no solo para perseguir errores, sino también para comprender bien el funcionamiento interno de su código. Cuando intenta comprender el código, no hay nada mejor que establecer algunos puntos de interrupción estratégicos y dejar que su depurador lo lleve a un recorrido por el código.

Depuración de un programa
El código de muestra en el repositorio de GitHub para este capítulo es un sistema de procesamiento de pedidos simulado, donde un cliente puede pedir una pieza y el sistema verificará (de manera simulada) la cuenta de cobro del cliente, así como el inventario. Si el pedido se realiza correctamente, enviará un correo electrónico indicando que se realizó correctamente. De lo contrario, enviará un correo electrónico indicando que se canceló el pedido. (En nuestro ejemplo, solo imprimirá un mensaje en la consola).

Primero, debes importar el proyecto. Puedes usar el elemento de menú Archivo ➪ Nuevo ➪ Proyecto desde el control de versiones y proporcionar la URL de GitHub https://github.com/realworldjava/Ch02-IDEs.

Antes de iniciar una sesión de depuración, tómese un momento para comprender qué hace este código. El flujo del programa comienza llamando al mainmétodo, que a su vez crea un nuevo método OrderProcessory luego lo llama processOrder.

Para ver el depurador en acción, establezca dos puntos de interrupción donde se indica en los comentarios, uno en el mainmétodo en la línea 6 y otro en chargeAndAdjustInventoryla línea 28.

A continuación, inicie el programa haciendo clic en la flecha verde en el margen a la izquierda del mainmétodo y seleccionando Depurar OrderProcessor.main(), o haga clic en el ícono de depuración del menú.

Esto abrirá la ventana de depuración (ver Figura 2.13 ).

El programa se interrumpirá en la línea 6. Seleccione Pasar a la siguiente línea (o presione F8) y observe cómo la ejecución avanza una línea. Ahora seleccione Reanudar programa (F9) y la ejecución continuará hasta que alcance el siguiente punto de interrupción en el chargeAndAdjustInventorymétodo.

Cuando el programa falla, observe las variables en la ventana del depurador (consulte la Figura 2.14 ).

Ahora haga clic en el siguiente cuadro de la pila de llamadas ( processOrderlínea 13) y observe las variables en ese ámbito. Luego haga lo mismo para el maincuadro :7.

De esta manera, puede recorrer la pila de llamadas y ver e incluso modificar las variables en cada ámbito. Para modificar una variable, haga clic en la variable en la ventana de variables, haga clic con el botón derecho en la variable y elija Establecer valor (o presione la tecla F2).


FIGURA 2.13 :Descripción general de la ventana de depuración


FIGURA 2.14 :Variables del depurador

Si hay clases de biblioteca en la pila de llamadas, puede elegir ignorarlas haciendo clic en el ícono de embudo Ocultar marcos de las bibliotecas en la parte superior de la ventana de marcos de depuración, como en la Figura 2.14 .

También puede pasar el ratón sobre una variable en el editor para ver su valor. Los valores de cadena también se muestran (en una fuente alternativa) junto a la variable en el editor. Las cadenas y los primitivos se mostrarán tal como están. En cuanto a otros tipos de objetos, puede hacer clic en los valores para obtener información detallada sobre ellos.

Si se aleja del punto de ejecución abriendo otras ventanas o desplazándose, siempre puede regresar al punto de ejecución presionando el ícono Mostrar punto de ejecución (Alt+F10/Opción+F10).

Puede silenciar todos los puntos de interrupción pulsando el icono Silenciar puntos de interrupción y, a continuación, haciendo clic en Reanudar programa (F9). La ejecución continuará sin interrupciones hasta que active el sonido.

Si hace clic con el botón derecho en un punto de interrupción, podrá encontrar configuraciones para desactivarlo temporalmente, establecer una condición que debe ser verdadera para que se pause y habilitar otras configuraciones. Si coloca un punto de interrupción en un método de interfaz, cualquier ejecución que llegue a ese método provocará la interrupción del depurador.

SUGERENCIA  Supongamos que estás ejecutando el depurador y recibes una excepción inesperada que te lleva lejos de donde estabas. ¿Dónde se produjo esa excepción? Presiona Ctrl+Alt+Izquierda/Cmd+Alt+Flecha izquierda para volver a la ubicación anterior.

Aceleración del rendimiento del depurador
Si la memoria de su computadora es limitada o si su programa es muy grande, es posible que note que su depurador se vuelve más lento. Puede acelerar considerablemente las cosas ajustando el depurador. Para ello, navegue a Archivo ➪ Configuración en Windows o al menú IntelliJ IDEA en Mac. Luego seleccione Generar, Ejecución, Depurador ➪ Vistas de datos ➪ Java y desactive la configuración, como se muestra en la Figura 2.15 . Si el depurador es lento, ajuste estas configuraciones y notará una mejora considerable en el rendimiento.


FIGURA 2.15 :Ajuste de la configuración de depuración

Puede realizar mejoras de rendimiento adicionales si realiza ajustes en la configuración de diseño, en la parte superior derecha de la ventana de depuración. Las opciones Subprocesos, Memoria y Gastos generales deben estar desmarcadas, como se muestra en la Figura 2.16 .


FIGURA 2.16 :Más configuraciones de optimización de depuración

Depuración remota
La depuración es una herramienta muy útil cuando se escribe una aplicación y se diagnostican problemas que se pueden reproducir fácilmente. Sin embargo, como dice la ley de Murphy, "todo lo que puede salir mal, saldrá mal". Esto se manifiesta como un problema que puede salir mal, saldrá mal en el servidor, pero no se puede reproducir localmente. En estos casos, Java admite la depuración remota, que permite depurar código que se ejecuta en un servidor remoto, establecer puntos de interrupción y ver variables, como si la aplicación se estuviera ejecutando localmente.

No mostramos un ejemplo aquí, pero para realizar una depuración remota en el trabajo, cree una nueva configuración de ejecución y seleccione Depuración remota de JVM como tipo. Ingrese el nombre del host, pero conserve los valores predeterminados a menos que el sistema remoto le solicite que los cambie.

Antes de poder realizar una depuración remota, debe iniciar el servidor mediante un agente de depuración remota especial. Para ello, copie los argumentos de la línea de comandos agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=*:5005de la configuración de tiempo de ejecución, como se muestra en la Figura 2.17 , y agréguelos a los argumentos de tiempo de ejecución de la aplicación.

Una vez configurada la depuración remota, puedes depurar la aplicación como si se estuviera ejecutando localmente, siguiendo los pasos que vamos a analizar.


FIGURA 2.17 :Argumentos de la línea de comandos

Depuración con intercambio en caliente
Durante la depuración, es posible que encuentre errores en su programa (después de todo, ¡se llama depuración !). Mucha gente piensa que necesita reiniciar la aplicación después de cada cambio; sin embargo, ese no siempre es el caso. Si realiza cambios simples, no tiene que reiniciar su sesión. Simplemente vuelva a compilar la clase donde realizó el cambio (seleccione el elemento de menú Generar ➪ Recompilar o presione Ctrl+Shift+F9/Cmd+Shift+F9), y voilá , la característica Hot Swap de Java volverá a cargar las clases y su programa simplemente funcionará. Sin embargo, algunas advertencias: Hot Swap funcionará solo si no se cambian las firmas de clase. Eso significa que no puede haber nuevas variables de clase o variables de instancia, ningún método nuevo o eliminado y ningún cambio en la firma del método o en la anotación. Si intenta aplicar Hot Swap después de cualquiera de esos cambios más grandes, el IDE le advertirá que el Hot Swap no funcionó y deberá reiniciar la aplicación.

DESPLAZAMIENTO DE REGISTRO
Una última palabra sobre la depuración: cuando esté en la pestaña del depurador, si desea ver la salida del registro, cambie a la pestaña de la consola. Si el registro se está enviando a la consola muy rápidamente, puede detener el desplazamiento simplemente haciendo clic en la ventana de la consola. Los mensajes de registro se seguirán adjuntando en la parte inferior, pero el desplazamiento se detendrá en la línea en la que hizo clic. Esta función de pausa con un clic también está disponible en la consola de ejecución, no solo en la consola de depuración.

La depuración es una habilidad fundamental para que su IDE le permita conocer el flujo de ejecución de su código. Todos los IDE tienen capacidades de depuración similares a las que se describen aquí. En la siguiente sección, analizaremos otra habilidad fundamental, que es la refactorización de código.

Refactorizando su código
En palabras del gran Martin Fowler, quien popularizó por primera vez el término refactorización , “Cualquier tonto puede escribir código que una computadora pueda entender. Los buenos programadores escriben código que un humano puede entender”.

La refactorización es el arte de mejorar el código existente mediante la aplicación de patrones conocidos para reorganizarlo. Algunos ejemplos de refactorización incluyen la eliminación de variables superfluas y la eliminación del código copiado y pegado. Pero tenga en cuenta que la refactorización tiene un riesgo: cuando cambia el código existente, está exponiendo oportunidades para problemas de regresión; es decir, corre el riesgo de romper cosas que funcionaban antes. Aquí es donde entra en juego el IDE. Verá, todos los IDE principales ofrecen un menú Refactor, y las refactorizaciones automatizadas son mucho más seguras que las manuales.

Recomendamos encarecidamente familiarizarse con cada uno de los elementos del menú de refactorización, especialmente los de extracción e inserción. Se ha escrito mucho sobre el tema de la refactorización, pero incluso sin leerlo todo, puede aprender bastante sobre refactorización con sentido común simplemente con el menú de refactorización.

CONSEJO  IntelliJ tiene por lejos las opciones de refactorización más amplias de los principales IDE de Java.

Cómo evitar el código duplicado
Nuestra primera regla de refactorización es no copiar y pegar nunca código. Si necesitas introducir alguna funcionalidad en dos o más lugares, extrae esa funcionalidad en un método. Si alguno de esos métodos está contenido en clases diferentes, llévalos a una superclase común o extráelos a una clase de utilidad. Si estás trabajando en una base de código que tiene código repetitivo, hazte cargo de refactorizarlo.

Para extraer código en un método, seleccione el código, vaya al menú Refactorizar y seleccione Extraer/Introducir ➪ Método, como se muestra en la Figura 2.18 . El atajo es Ctrl+Alt+M/Cmd+Opción+M y será uno de los atajos más utilizados, así que úselo hasta que lo recuerde.


FIGURA 2.18 :Menú de refactorización de IntelliJ IDE

En la Figura 2.19 , tenemos dos métodos para enviar correos electrónicos. El primero lo hace semanalmente y el segundo lo hace cada dos semanas. Una mirada más de cerca revela que los dos métodos están haciendo básicamente lo mismo, con algunas ligeras variaciones. ¿Por qué no extraer la funcionalidad común en un método y pasar las diferencias como parámetros? Esta es la técnica: comience con un método, digamos el primero, processWeeklyReminders()en la Figura 2.19 .


FIGURA 2.19 :Extracción de funcionalidad común a un método

El paso 1 es factorizar los elementos no comunes extrayendo las diferencias de las variables. En nuestro ejemplo, nuestros métodos semanales y quincenales son similares, aunque tienen elementos no comunes, específicamente el número de semanas y el método para enviar el correo electrónico. Seleccione el número 1 (la weeksToAddvariable en la línea 10) y elija el elemento de menú Refactorizar ➪ Extraer/Introducir ➪ Variable y asígnelo a la variable denominada numWeeks. Reorganice las líneas si es necesario para que numWeeksy Comsumerestén antes del código para extraer (consulte la Figura 2.20 ).


FIGURA 2.20 :Extracción de diferencias en variables

A continuación, seleccione la funcionalidad común que desea extraer, como en la Figura 2.21 .


FIGURA 2.21 :Selección de la funcionalidad común

Seleccione Ctrl+Alt+M/Cmd+Opción+M, el atajo para extraer un método. El IDE le asignará un nombre, que usted desea cambiar por algo significativo, sendIfTimeen nuestro caso, como se muestra en la Figura 2.22 .

El IDE ofrecerá reemplazar otros lugares con el método extraído, como se muestra en la Figura 2.23 .


FIGURA 2.22 :Extracción del método


FIGURA 2.23 :El IDE ayuda a localizar oportunidades para aplicar el nuevo método.

Puede colocar el cursor en el nombre del método y usar Ctrl+Shift/Cmd+Shift con las teclas de flecha arriba o abajo para mover los métodos hacia arriba y hacia abajo en la clase, como se muestra en la Figura 2.24 .

El código se vería mucho más ordenado si incorporara los mailerparámetros en el código. Simplemente haga clic en el nombre de la variable y elija Refactorizar ➪ Variable en línea (Ctrl+Alt+N) para incorporar las variables, como se muestra en la Figura 2.25 . Verá la incorporación nuevamente en breve.


FIGURA 2.24 :El primer borrador refactorizado


FIGURA 2.25 :La versión refactorizada final. Compárese conla Figura 2.19.

Puedes ver que el código ahora está mucho más ordenado, con dos métodos más pequeños que delegan al método extraído que contiene el código principal. Usa esta técnica para refactorizar de forma segura código del mundo real mucho más complejo.

CONSEJO:  No es necesario que el código duplicado sea útil para que el método de extracción sea útil. También resulta útil para lidiar con métodos que son demasiado largos tener métodos más pequeños con nombres claros para encargarse de parte de la lógica.

Se podría decir que la extracción de métodos es el patrón de refactorización más importante, pero todos los patrones de refactorización contribuyen a un código limpio y de calidad. Veamos otra refactorización importante: el cambio de nombre de miembros, es decir, el cambio de nombre de métodos y variables.

Cambiar el nombre de los miembros
Nuestra siguiente regla para la refactorización es nombrar los métodos y las variables con nombres significativos. Recuerde que, al cambiar los nombres, debe evitar las abreviaturas no estándar. Esto es importante para que su código se autodocumente. Si está trabajando con código heredado con nombres de variables o métodos que son demasiado cortos o confusos, será útil cambiar el nombre de las variables y los métodos por algo significativo.

Para cambiar el nombre de una variable, haz clic en ella (no es necesario seleccionarla por completo, solo haz clic en cualquier parte de ella), presiona Shift+F6 y luego escribe el nuevo nombre. Se reemplazará con la nueva versión en todo el código base. ¿Y adivina qué? ¡Este es otro atajo que es el mismo en Windows y Mac!

También puedes cambiar el nombre de los métodos y clases usando el mismo atajo Shift+F6, y puedes estar seguro de que tu código seguirá compilando y conservará la misma semántica.

Cambiar el nombre de los miembros es un patrón importante para que el código sea más legible. Pero a veces hay variables o métodos que son simplemente innecesarios y, en esos casos, nos beneficiaremos de la incorporación de valores en línea.

Inserción en línea
El uso de variables puede hacer que el código sea más claro, pero no siempre. Habrá ocasiones en las que la declaración de la variable simplemente ocupe una línea adicional sin agregar claridad en absoluto. Por ejemplo, en el siguiente fragmento de código, la declaración de la variable rgbIntocupa una línea adicional, posiblemente sin agregar claridad en absoluto. En tales casos, tendría sentido simplemente incluir la expresión en línea y eliminar la declaración de la variable, como se muestra en la Figura 2.26 .


FIGURA 2.26 :La declaración de variable en la línea 8 no agrega claridad; inclúyala en línea.

Puede insertar en línea la variable no deseada haciendo clic en cualquier aparición de la variable en el código (por ejemplo, puede ver la ubicación del cursor de inserción en la Figura 2.26 , línea 6) y luego presionar Ctrl+Alt+N/Cmd+Option+N. Lo anterior cambia a lo que puede ver en la Figura 2.27 .


FIGURA 2.27 :La variable está en línea.

No repasaremos todos los aspectos de la refactorización aquí, pero si desea llevar sus habilidades de programación al siguiente nivel, consulte la sección “Referencias adicionales” para obtener un excelente libro sobre refactorización.

Hubo un tiempo en que los IDE tenían capacidades de refactorización muy limitadas, si es que tenían alguna. Había técnicas para realizar la refactorización de la manera más segura posible. Pero ahora que la mayoría de los patrones de refactorización comunes están integrados en los IDE, es necesario hacer un esfuerzo para estudiarlos y utilizarlos.

Pero la refactorización no es lo único en lo que los IDE son excelentes. Veamos otras herramientas interesantes.

Cambiar firmas: agregar y eliminar parámetros
Con frecuencia, encontrará métodos en los que no se utilizan argumentos o que se pueden obtener de alguna otra manera. O puede descubrir que los argumentos de los métodos se prestan a un orden más natural en la lista de argumentos.

Puede agregar, eliminar o reordenar fácilmente los argumentos en la firma de un método haciendo clic en el nombre del método y presionando Ctrl+F6/Cmd+F6 para abrir la ventana emergente Cambiar firma. Luego, puede mover los elementos como desee. No tiene que navegar hasta la declaración del método; la refactorización se puede aplicar en cualquier lugar donde se invoque el nombre del método.

EXPLOTANDO AL EDITOR
Un IDE es, ante todo, un editor, e IntelliJ ofrece un conjunto sólido de capacidades de edición con las que debería familiarizarse. En esta sección, aprenderá algunas capacidades de edición importantes y mejoras de productividad. Le recomendamos que mantenga abierto su IDE y siga los ejemplos que describimos aquí.

Una nota importante: esto no debería ser necesario decirlo, pero si no estás conforme con algo, simplemente presiona Ctrl+Z/Cmd+Z para deshacerlo. Hemos visto a desarrolladores no adoctrinados tratando de deshacer una maraña de ediciones o refactorizaciones insatisfechas cuando todo lo que necesitaban hacer era presionar Ctrl+Z/Cmd+Z para deshacerlo.

En IntelliJ, puedes agregar comillas alrededor de una cadena seleccionando la cadena y simplemente presionando la tecla de comillas dobles ("). Por ejemplo, supongamos que tienes la siguiente línea:

public static final String TEXT = text;
Resalte las letras texty presione la comilla doble ( "). El código se transforma en esto:

public static final String TEXT = "text";
Las comillas simples, los paréntesis y los corchetes deberían funcionar de manera similar, aunque hemos encontrado resultados variables al usar diferentes asignaciones de teclado.

Si tiene dos líneas de código que desea fusionar en una sola, simplemente presione Ctrl+J/Ctrl+Shift+J. Esto es ideal para cambiar el formato de los comentarios o para fusionar una declaración con una tarea. Por ejemplo, si tiene las siguientes dos líneas:

11: String name = null;
12: name = "Henry";
13: // Assignment was done
Coloque el cursor en cualquier lugar de la línea 11 y presione Ctrl+J/Ctrl+Shift+J. Esto dará como resultado lo siguiente:

11: String name = "Henry";
12: // Assignment was done
Reformateo automático del código
IntelliJ ofrece algunas opciones para organizar el código de forma más ordenada, lo que puede darle un aspecto más profesional.

Organizando las importaciones
Mantener limpias las importaciones es una cuestión sencilla: solo hay que utilizar la opción de menú Código ➪ Optimizar importaciones (Ctrl+Alt+O/Ctrl+Opción+O). Esta opción elimina las importaciones no utilizadas y las ordena para que estén más organizadas.

Código de reformateo
Para reformatear el código, puede seleccionar el elemento de menú Código ➪ Reformatear (Ctrl+Alt+L/Cmd+Opción+L), que aplicará el formato a todo el archivo. Si selecciona un fragmento de código, ese mismo comando solo reformateará el código.fragmento de código seleccionado. También puede seleccionar un paquete o directorio en el Explorador de proyectos y ese mismo comando reformateará todo lo que contenga ese directorio.

El comando de reformateo entiende los tipos de archivos que se están reformateando y aplicará el formato apropiado para Java, JSON, CSS, XML, etc.

El cambio de formato utiliza formatos estándar para cada tipo de archivo, pero puede modificar aspectos como agregar espacios alrededor de un signo igual en las asignaciones o dónde colocar el corchete ondulado al final de una declaración de método. Estos se encuentran en el elemento de menú Archivo para Windows o en el elemento de menú IntelliJ para Mac. Luego, seleccione Configuración ➪ Estilo de código para cada tipo de archivo. Por ejemplo, la Figura 2.28 muestra las opciones de Java.


FIGURA 2.28 :Opciones de reformateo

Desempaquetado
Un código que encontramos a menudo, incluso entre desarrolladores experimentados, tiene que ver con el manejo de excepciones. Somos alérgicos a cualquier código que diga throw new Exception("some message");. La forma correcta de manejar excepciones es manejar la excepción lo antes posible. Si debe lanzar una excepción, lance una excepción lo más específica posible.

Una técnica que utilizamos para descubrir oportunidades de corregir el manejo de excepciones es buscar instancias de catch(Exception e). Si hay una throws Exceptioncláusula en la firma del método, simplemente elimínela. Luego, elimine un carácter de la palabra Exceptionen el catchbloque, lo que hará que el IDE crea que la excepción no se manejó y colocará un subrayado rojo debajo de cada excepción que se debe manejar. Si no hay ninguna, puede desenrollar el try-catchbloque utilizando la función Desenrollar. Simplemente coloque el cursor dentro del try-catchbloque y presione Ctrl+Shift+Delete/Cmd+Shift+Delete. Se le solicitará que desenrolle el intento. Después de confirmar, desaparece.

SUGERENCIA:  También puedes desenrollar cláusulas if and else , cadenas, etc. ¡Pruébalo!

Comparando código
Debemos mencionar otra alergia: el código duplicado. Si cree que hay archivos similares y que pueden necesitar ser refactorizados, puede hacer una comparación lado a lado seleccionando los dos o más archivos en el Explorador de proyectos y eligiendo el elemento de menú Ver ➪ Comparar archivos (Ctrl+D/Cmd+D). Esto abrirá los archivos en ventanas contiguas, donde puede editarlos en ambos lados.

De manera similar, puede copiar una selección al portapapeles y luego hacer otra selección, hacer clic derecho y elegir Comparar con portapapeles.

Uso del modo columna
Existen situaciones en las que es necesario editar una serie de líneas similares en un archivo, por ejemplo, cuando es necesario agregar una función común delante de una serie de líneas similares. Para activar el modo de columna, siga estos pasos:

Presione Ctrl/Opción una vez.
Presione nuevamente, pero esta vez manteniéndolo presionado.
Presione la flecha hacia abajo hasta que haya seleccionado toda la columna que desea editar. (Ver Figura 2.29 ).
Ahora puedes pegar en esa columna desde el portapapeles o puedes editar en el lugar. Pulsa la tecla Fin para mover los cursores al final de la línea y la tecla Inicio los llevará al principio. También puedes utilizar Ctrl+Flecha izquierda/Cmd+Opción+Mayús+Flecha izquierda y Ctrl+Flecha derecha/Cmd+Opción+Mayús+Flecha izquierda para moverlos hacia la izquierda o hacia la derecha, una palabra a la vez.

En el siguiente fragmento, hay una serie de triples RGB. Digamos que desea cambiar el triple del medio a 255 para cada línea. Coloque el cursor en cualquier lugar de la línea superior y seleccione la columna que desea editar utilizando la secuencia de teclado de tres teclas Ctrl/Opción, Ctrl/Opción, Flecha hacia abajo, hasta que se seleccione cada fila que desee cambiar, como se muestra en la Figura 2.29 .


FIGURA 2.29 :Selección del modo de columna

Luego presione la tecla Fin y los cursores se moverán al final de cada línea, como se muestra en la Figura 2.30 .


FIGURA 2.30 :Todos los cursores al final de la línea

Ahora presione Ctrl+Flecha izquierda/Opción+Flecha izquierda para mover todos los cursores una palabra a la izquierda, y presione una Flecha izquierda más para llevarlos a la izquierda de la coma, como se muestra en la Figura 2.31 .


FIGURA 2.31 :Todos los cursores se mueven hacia la izquierda

Por último, al presionar Ctrl+Retroceso/Opción+Retroceso se eliminará todo el segmento central, como se muestra en la Figura 2.32 .


FIGURA 2.32 :Todas las líneas eliminando el segmento medio

Ahora simplemente escriba el texto de reemplazo, como se muestra en la Figura 2.33 .


FIGURA 2.33 :Texto de reemplazo en todas las líneas

Encontrará esta técnica útil al cambiar configuraciones similares, como cadenas de conexión, indicaciones de texto e incluso al cambiar líneas adyacentes de código similar.

AMPLIACIÓN DEL IDE
Si bien IntelliJ tiene muchas funciones integradas, hay muchas más funciones disponibles a través de complementos . Un complemento es un fragmento de código que se ejecuta en el IDE para agregar o personalizar el comportamiento. Muchos complementos vienen incluidos con IntelliJ. Otros se descargan desde una ubicación llamada Marketplace.

Para instalar un complemento desde el Marketplace, comience en el elemento de menú Archivo para Windows o en el elemento de menú IntelliJ para Mac. Luego elija Configuración ➪ Complementos. Esto abre el Marketplace donde puede elegir el complemento que desea, como se muestra en la Figura 2.34 . Por ejemplo, Key Promoter es bueno para aprender atajos de teclado. Cuando hace algo con el mouse, una ventana emergente le muestra qué atajo podría haber usado. Haga clic en Instalar y se descargará el complemento. Luego se le solicitará que reinicie el IDE y el complemento estará disponible.


FIGURA 2.34 :Instalación de un complemento en IntelliJ

Mirando al eclipse
Ahora que comprende IntelliJ, es hora de analizar Eclipse. Primero, hay dos diferencias de vocabulario importantes que debe comprender. En IntelliJ, abre un proyecto , que consta de uno o más módulos . En Eclipse, abre un espacio de trabajo , que también consta de uno o más módulos . Por lo tanto, proyecto significa cosas diferentes en los IDE: en IntelliJ, proyecto se refiere a la entidad de nivel superior y en Eclipse se refiere a un artefacto compilable. Eclipse es de código abierto y, por lo tanto, de uso gratuito. Recibe contribuciones de empresas importantes como IBM y Oracle.

¿SIEMPRE VERDE?
IntelliJ tiene un principio rector llamado "siempre verde". En IntelliJ, se espera que el código se compile en todo momento. Si tiene un error de compilación en cualquier clase del módulo, no podrá ejecutar ningún método principal ni ninguna prueba. Por el contrario, Eclipse hace todo lo posible para ejecutar el código. Si el código que no se compila no necesita ser ejecutado por su ruta de código, Eclipse le permitirá ejecutarlo.

Para comenzar a utilizar Eclipse, abra un nuevo proyecto seleccionando Archivo ➪ Nuevo ➪ Proyecto Java, como se muestra en la Figura 2.35 .


FIGURA 2.35 :Creación de un proyecto en Eclipse

Al igual que en IntelliJ, se te solicita un nombre de proyecto y la versión de Java como mínimo. Como alternativa, puedes usar Archivo ➪ Importar ➪ Git ➪ Proyectos desde Git para extraer un proyecto del control de versiones, o puedes usar Archivo ➪ Importar ➪ General ➪ Proyectos existentes en el espacio de trabajo para usar un proyecto que ya se haya creado.

Hay tres formas comunes de ejecutar una aplicación Java:

Seleccione el menú desplegable en el icono de flecha verde y seleccione Ejecutar como ➪ Aplicación Java, como se muestra en la Figura 2.36 .
Haga clic derecho en el nombre de la clase Java y elija una de las opciones de ejecución.
Seleccione la opción de menú Ejecutar y luego Ejecutar como ➪ Aplicación Java.

FIGURA 2.36 :Ejecución de una aplicación en Eclipse

Todos estos enfoques tienen una opción para configurar la ejecución, al igual que en IntelliJ, donde puede guardar configuraciones para ejecutar la aplicación. Para usar el depurador, inicie su programa utilizando el ícono de error en lugar del ícono de flecha. El ícono de error pone su programa en modo de depuración.

Al igual que IntelliJ, puedes ampliar el comportamiento del IDE a través de complementos. Ve al menú Ayuda ➪ Eclipse Marketplace. Una vez que hayas elegido el complemento que deseas, instálalo y reinicia Eclipse para que surta efecto.

Si planeas usar Eclipse, te recomendamos que mires la configuración. En Windows, se encuentra en Ventana ➪ Preferencias. En Mac, se encuentra en Eclipse ➪ Configuración.

Eclipse tiene muchos atajos de teclado. Exploraremos algunos en la sección “Comparación de IDE”. Uno particularmente útil es Ctrl+3/Cmd+3, que abre una ventana emergente donde puedes escribir el nombre de cualquier comando para ejecutar.

ECHANDO UN VISTAZO AL CÓDIGO VS
Visual Studio (VS) Code de Microsoft tiene su propio conjunto de vocabulario. Al igual que Eclipse, la entidad de nivel superior es un espacio de trabajo. Las unidades de nivel inferior se denominan simplemente carpetas . VS Code se denomina editor , en lugar de entorno de desarrollo integrado.

Visual Studio es un producto independiente, que no debe confundirse con VS Code. Ambos son distribuidos por Microsoft, pero Visual Studio es un IDE comercial que suelen utilizar los desarrolladores de .NET, mientras que VS Code es un editor gratuito. Esta distinción entre editor e IDE suele manifestarse en la funcionalidad limitada, aunque ha ido mejorando rápidamente.

SUGERENCIA  Dado que VS Code es un editor, te permite abrir fácilmente un solo archivo y editarlo.

Al igual que con IntelliJ y Eclipse, puedes descargar código que amplíe la funcionalidad del IDE. VS Code llama a esas extensiones en lugar de a complementos. Debes instalar la extensión de Java antes de comenzar a escribir código en el IDE. Las extensiones se encuentran en Archivo ➪ Preferencias ➪ Extensiones en Windows y Código ➪ Configuración ➪ Extensiones en Mac. En Marketplace, busca “Paquete de extensiones para Java”, haz clic en Instalar y reinicia VS Code.

¿QUÉ EXTENSIÓN DE JAVA?
Hay al menos dos paquetes de extensión que agregan soporte para Java a VS Code.

Paquete de extensión para Java (de Microsoft)
Extensión de la plataforma Oracle para Visual Studio Code
Dado que la compatibilidad de Java con VS Code es más reciente, estos complementos están evolucionando rápidamente. Vale la pena explorar los de Microsoft y Oracle para ver cuál es el mejor en el momento en que estás leyendo esto.

También hay soporte de lenguaje para Java de RedHat, pero el de Microsoft lo incluye en su extensión, por lo que no es necesario probarlo de forma independiente.

Cuando abre una nueva ventana en VS Code, tiene tres opciones. Puede abrir una carpeta existente en el disco, obtener el código del control de versiones o crear un nuevo proyecto Java, como se muestra en la Figura 2.37 .


FIGURA 2.37 :Creación de un proyecto en VS Code

Si elige crear un nuevo proyecto, primero se le preguntará qué herramienta de compilación desea utilizar. Puede elegir no usar ninguna herramienta de compilación por ahora. En el Capítulo 4 , aprenderá sobre herramientas de compilación como Maven y Gradle. Luego, se le solicitará que navegue hasta el directorio donde desea almacenar el proyecto. Finalmente, ingrese un nombre de proyecto.

Hay tres formas comunes de ejecutar un programa Java.

Haga clic en el texto Ejecutar en el archivo, como se muestra en la Figura 2.38 .
Haga clic con el botón derecho en el nombre de la clase Java y seleccione Ejecutar Java.
En el menú Ejecutar, elija Ejecutar sin depurar.

FIGURA 2.38 :Ejecución de una aplicación en VS Code

La opción para ejecutar en modo de depuración se encuentra en las mismas ubicaciones. VS Code invoca las configuraciones guardadas para ejecutar y depurar una configuración de lanzamiento. Haga clic en el ícono en la navegación izquierda (que muestra una flecha y un error) para obtener la opción para crear una configuración de lanzamiento, como se muestra en la Figura 2.39 .


FIGURA 2.39 :Creación de una configuración de lanzamiento en VS Code

Si planeas usar VS Code, te recomendamos que mires la configuración. En Windows, selecciona Archivo ➪ Preferencias ➪ Configuración. En Mac, selecciona Código ➪ Configuración ➪ Configuración.

VS Code tiene muchos atajos de teclado. Exploraremos algunos en la sección “Comparación de IDE”. Uno particularmente útil es el atajo para abrir la paleta de comandos. Al presionar Ctrl+Shift+P/Cmd+Shift+P se abre la paleta para que puedas escribir el nombre de cualquier comando de VS Code.

COMPARACIÓN DE IDE
En algunas empresas, todos usan el mismo IDE. En otras, cada desarrollador puede usar su favorito. Incluso en esos casos, deberías poder entender de qué están hablando las personas que usan un IDE diferente. La Tabla 2.1 muestra las principales diferencias de vocabulario.

Todos los IDE ofrecen una amplia variedad de atajos de teclado. La Tabla 2.2 compara algunos de los más comunes para que te hagas una idea de la variedad. Ten en cuenta que algunos IDE te permiten importar asignaciones de teclado de otros. Si estás acostumbrado a un IDE, es posible que puedas mantener esas configuraciones en otro. Sin embargo, aprender los atajos predeterminados tiene sus ventajas, de modo que puedas trabajar más fácilmente con otras personas que utilicen ese IDE.

TABLA 2.1 :Terminología IDE

ARTÍCULO	INTELIGENCIA	ECLIPSE	Código VS
Unidad construible	Módulo	Espacio de trabajo	Espacio de trabajo
Configuraciones compartidas y hogar para unidades construibles	Proyecto	Proyecto	Carpeta
Bibliotecas opcionales para personalizar el comportamiento del IDE	Complemento	Complemento	Extensión
Configuraciones guardadas para ejecuciones	Ejecutar configuración	Ejecutar configuración	Configuración de lanzamiento
TABLA 2.2 :Resumen de atajos de teclado IDE

DOMINIO	INTELIGENCIA	ECLIPSE	Código VS
Ejecutar cualquier comando	Mayús+Mayús	Ctrl+3/
Cmd+3	Ctrl+Mayús+P/
Cmd+Mayús+P
Abrir un archivo	Ctrl+N/
Cmd+O	Ctrl+Mayús+T/
Cmd+Mayús+R	Ctrl+P/
Cmd+P
Ejecutar una aplicación	Mayús+F10/
Ctrl+R	Ctrl+Mayús+F11/
Cmd+Mayús+F11	Ctrl+F5
Extraer un método	Ctrl+Alt+M/
Cmd+Alt+M	Ctrl+Alt+M/
Cmd+Opción+M	Ctrl+Shift+R y luego Ctrl+E
Organizando las importaciones	Ctrl+Alt+O/
Ctrl+Opción+O	Ctrl+Mayús+O/
Cmd+Mayús+O	Opción+Mayús+O/
Alt+Mayús+0
Código de formato	Ctrl+Alt+L/
Ctrl+Opción+L	Ctrl+Mayús+F/
Cmd+Mayús+F	Ctrl+Mayús+I/
Cmd+Mayús+I
REFERENCIAS ADICIONALES
https://www.jetbrains.com/idea
Descargar IntelliJ IDEA

https://www.eclipse.org/downloads
Descargar Eclipse

https://code.visualstudio.com/download
Descargar VS Code

Refactorización: mejora del diseño del código existente (Addison-Wesley, 2018)
Libro clásico sobre refactorización de Kent Beck y Martin Fowler

https://dev.java/learn/debugging
Artículo de Jeanne sobre el uso de un depurador

RESUMEN
Se podría decir que el IDE es el elemento más importante del ecosistema Java, y el éxito como programador comienza cuando aprendes a utilizar todo el poder de esta herramienta vital. Los elementos más importantes son dominar los atajos de teclado, utilizar las funciones de refactorización y aprender a utilizar todas las sutilezas del propio editor.

En este capítulo, exploramos la evolución del IDE de Java y aprendimos cómo la familiaridad con el IDE puede convertirlo en un programador experto. Analizamos en profundidad algunas de las características más importantes de IntelliJ IDEA, incluidos los atajos de teclado, la refactorización y otras funciones importantes del editor.
En el resto del libro, nos centraremos más en la programación, pero analizaremos otras capacidades del IDE apropiadas para las tecnologías que cubrimos.
