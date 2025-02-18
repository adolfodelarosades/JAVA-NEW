# Capítulo 2: Uso de contenedores web

1. Elección de un contenedor web
2. Instalación de Tomcat en su máquina
3. Implementación y anulación de la implementación de aplicaciones en Tomcat
4. Depuración de Tomcat desde su IDE
5. Resumen

### EN ESTE CAPÍTULO

* Elección de un contenedor web
* Instalación de Tomcat en su máquina
* Implementación y anulación de la implementación de aplicaciones en Tomcat
* Depuración de Tomcat desde IntelliJ IDEA
* Depuración de Tomcat desde Eclipse

### DESCARGAS DE CÓDIGOS DE WROX.COM PARA ESTE CAPÍTULO

Puede encontrar las descargas de código de wrox.com para este capítulo en http://www.wrox.com/go/projavaforwebapps en la pestaña Descargar código. El código para este capítulo se divide en los siguientes ejemplos principales:

* Archivo de aplicación WAR de implementación de muestra
* Ejemplo de proyecto de depuración de IntelliJ
* Ejemplo de depuración del proyecto Eclipse

### NUEVAS DEPENDENCIAS DE MAVEN PARA ESTE CAPÍTULO

No hay dependencias de Maven para este capítulo.

## ELEGIR UN CONTENEDOR WEB

En el capítulo anterior, se le presentó la plataforma Java, Enterprise Edition, y los conceptos de servlets, filtros y otros componentes de Java EE. También aprendió sobre algunas de las nuevas características de Java 7 y 8. Las aplicaciones web de Java EE se ejecutan dentro de servidores de aplicaciones Java EE y contenedores web (también conocidos como contenedores de servlets, y este libro utiliza los términos indistintamente).

Aunque la especificación Java EE está llena de muchas subespecificaciones más pequeñas, la mayoría de los contenedores web implementan solo las especificaciones Servlet, JSP y JSTL. Esto es diferente de los servidores de aplicaciones Java EE completos, que implementan toda la especificación Java EE. Cada servidor de aplicaciones contiene un contenedor web, que es responsable de administrar el ciclo de vida de los servlets, mapear las URL de solicitud al código de servlet, aceptar y responder a las solicitudes HTTP y administrar la cadena de filtros, cuando corresponda. Sin embargo, los contenedores web independientes suelen ser más livianos y más fáciles de usar cuando no se requiere todo el conjunto de características de Java EE.

Elegir un contenedor web (o un servidor de aplicaciones, en este caso) es una tarea que requiere una investigación cuidadosa y la consideración de los requisitos de su proyecto. Tiene muchas opciones para elegir un contenedor web, y cada una tiene sus ventajas y desafíos. Puede utilizar una variedad de contenedores web. Por ejemplo, puede decidir utilizar Apache Tomcat para pruebas locales en las máquinas de sus desarrolladores mientras utiliza GlassFish para su entorno de producción. O puede escribir una aplicación que sus clientes implementen en sus propios servidores, en cuyo caso probablemente desee realizar pruebas en muchos servidores de aplicaciones y contenedores web diferentes.

En esta sección aprenderá sobre algunos contenedores web y servidores de aplicaciones comunes, y en las secciones restantes analizará en profundidad el que utilizará para el resto de este libro.

Apache Tomcat
Apache Tomcat es el contenedor web más común y popular disponible en la actualidad. Los ingenieros de software de Sun Microsystems crearon originalmente este contenedor web como Sun Java Web Server, y fue la implementación de referencia original de la especificación Java EE Servlet. Sun lo donó más tarde a la Apache Software Foundation en 1999, y en ese momento se convirtió en Jakarta Tomcat y, finalmente, en Apache Tomcat. También es interesante observar que la evolución de Tomcat por parte de Apache condujo al desarrollo de la herramienta de compilación Apache Ant, que miles de proyectos comerciales y de código abierto utilizan hoy en día.

Las principales ventajas de Tomcat son su pequeño tamaño, su configuración sencilla y su larga trayectoria de participación en la comunidad. Normalmente, los desarrolladores pueden tener una instalación de Tomcat funcional en funcionamiento en 5 a 10 minutos, incluido el tiempo de descarga. Tomcat requiere muy poca configuración de fábrica para funcionar bien en una máquina de desarrollo, pero también se puede ajustar significativamente para que funcione bien en entornos de producción de alta disponibilidad y alta carga. Puede crear grandes clústeres de Tomcat para manejar grandes volúmenes de tráfico de forma fiable. Tomcat se utiliza a menudo en entornos de producción comercial debido a su simplicidad y perfil ligero. Sin embargo, Tomcat carece de la sofisticada interfaz de gestión web que ofrecen muchos de sus competidores para configurar el servidor. En su lugar, Tomcat proporciona sólo una interfaz sencilla para tareas básicas, como la implementación y anulación de la implementación de aplicaciones. Para una configuración adicional, los administradores deben manipular una colección de archivos de propiedades XML y Java. Además, como no es un servidor de aplicaciones completo, carece de muchos componentes Java EE, como la API de persistencia de Java, la API de validación de beans y el servicio de mensajes de Java.

Como puedes imaginar, esto hace que Tomcat sea ideal para muchas tareas, pero hace que la implementación de aplicaciones empresariales más complejas sea un desafío y, a veces, imposible. Si te gusta Tomcat pero necesitas un servidor de aplicaciones Java EE completo, puedes recurrir a Apache TomEE, que está desarrollado sobre Tomcat pero ofrece una implementación completa de todos los componentes Java EE. Al estar desarrollado sobre Tomcat, cuenta con toda la fuerza de la comunidad Tomcat y más de una década de pruebas a sus espaldas. Apache también ofrece Geronimo, otro servidor de aplicaciones Java EE completo de código abierto.

NOTA: TomEE y Geronimo son servidores de aplicaciones Java EE certificados por Oracle, lo que significa que se ha verificado que cumplen con todos los aspectos de la especificación Java EE. Debido a que Tomcat es solo un contenedor web, no tiene dicha certificación. Sin embargo, su enorme base de usuarios y su comunidad activa garantizan que implementa con precisión los componentes Java EE que proporciona.

Tomcat proporciona implementaciones de las especificaciones Servlet, Java Server Pages (JSP), Java Unified Expression Language (EL) y WebSocket. La Tabla 2-1 enumera varias versiones de Tomcat y las especificaciones que implementan. Solo Tomcat 6, 7 y 8 aún son compatibles. Las versiones 3.3, 4.1 y 5.5 llegaron al final de su vida útil hace años. Puede leer más sobre Apache Tomcat en el sitio web de Tomcat .

TABLA 2-1 : Versiones de Tomcat y sus especificaciones


Pez de cristal
GlassFish Server es una implementación de servidor de aplicaciones Java EE comercial y de código abierto. Proporciona todas las características de la especificación Java EE, incluido un contenedor web, y actualmente es la implementación de referencia para la especificación Java EE. Su contenedor web es en realidad un derivado de Apache Tomcat; sin embargo, ha evolucionado considerablemente desde que se bifurcó el núcleo de Tomcat para crear GlassFish, y el código es casi irreconocible hoy en día. La edición de código abierto de GlassFish ofrece soporte comunitario, mientras que Oracle GlassFish Server comercial proporciona soporte comercial pago a través de Oracle Corporation. Oracle solo ofrece soporte comercial a través de Java EE 7. A partir de Java EE 8, GlassFish no incluirá una opción de soporte comercial.

Una de las fortalezas de GlassFish es su interfaz de administración, que proporciona una interfaz de usuario web gráfica, una interfaz de línea de comandos y archivos de configuración para configurar cualquier cosa dentro del servidor. Los administradores de servidores pueden incluso usar la interfaz de administración para implementar nuevas instancias de GlassFish dentro de un clúster de GlassFish. Como implementación de referencia, también es siempre el primer servidor en implementar una nueva versión cada vez que se actualiza la especificación. La primera versión de GlassFish fueEn mayo de 2006, se lanzó la versión 2.0, que implementó la especificación Java EE 5. En septiembre de 2007, se agregó compatibilidad con capacidades de agrupamiento completas. La versión 3.0 (la implementación de referencia para Java EE 6, lanzada en diciembre de 2009) incluyó varias mejoras empresariales. Esta versión representó un punto de inflexión en la popularidad de GlassFish, y se volvió extremadamente simple administrar un entorno empresarial agrupado en GlassFish. En julio de 2011, la versión 3.1.1 mejoró varias características empresariales y agregó compatibilidad con Java SE 7, aunque Java SE 6 seguía siendo la versión mínima requerida. GlassFish 4.0 se lanzó en junio de 2013 como la implementación de referencia de Java EE 7 y requiere un mínimo de Java SE 7.

Puede leer más sobre GlassFish y descargarlo si lo desea en el sitio web de GlassFish .

JBoss y WildFly
El servidor de aplicaciones de software de código abierto JavaBeans de Red Hat (JBoss AS) fue el segundo servidor Java EE más popular, después de Tomcat, a principios de 2013. Históricamente, JBoss AS ha sido un contenedor web con soporte para Enterprise JavaBeans y algunas otras características de Java EE. Finalmente, obtuvo la certificación Web Profile y, en 2012, se certificó como servidor de aplicaciones Java EE completo. Con el tiempo, el nombre JBoss también se convirtió en sinónimo de una comunidad de desarrollo (como Apache) que proporcionaba varios productos, así como la plataforma comercial JBoss Enterprise Application Platform. El servidor de aplicaciones mantuvo el nombre JBoss AS hasta la versión 7.1.x, pero en 2012, la comunidad decidió que el nombre era fuente de demasiada confusión debido a otros proyectos JBoss. El servidor de aplicaciones pasó a llamarse WildFly a partir de la versión 8.0, lanzada a principios de 2014.

Al igual que GlassFish, WildFly es de código abierto con soporte gratuito proporcionado por la comunidad JBoss y soporte comercial pago proporcionado por Red Hat. Tiene un conjunto completo de herramientas de gestión y proporciona capacidades de agrupamiento y alta disponibilidad como Tomcat y GlassFish. Las versiones 4.0.x a 4.2.x de JBoss AS se crearon sobre Tomcat 5.5 y admitían funciones de Java EE 1.4. La versión 5.0 introdujo la compatibilidad con Java EE 5 y un nuevo contenedor web, y la 5.1 contenía las primeras implementaciones de algunas funciones de Java EE 6 (aunque seguía siendo un servidor de aplicaciones Java EE 5). JBoss AS 6.0 implementó el perfil web de Java EE 6, pero no buscó ni obtuvo una certificación de servidor de aplicaciones Java EE 6. JBoss AS 7.0 representó una reescritura completa del producto para reducir drásticamente su huella y aumentar su rendimiento, y también admitía solo el perfil web de Java EE 6. No fue hasta la versión 7.1 de JBoss AS que volvió a convertirse en un servidor de aplicaciones completo, logrando la certificación Java EE 6 más de 2 años después del lanzamiento de Java EE 6. WildFly 8.0 es un servidor de aplicaciones Java EE 7 completo y requiere un mínimo de Java SE 7. (En realidad, todos los servidores de aplicaciones Java EE 7 y contenedores web requieren un mínimo de Java SE 7).

Puede obtener más información y descargar JBoss AS 7.1 y versiones anteriores en el sitio web de JBoss , mientras que puede encontrar WildFly 8.0 en el sitio web de WildFly .

Otros contenedores y servidores de aplicaciones
Existen muchos otros contenedores web, como Jetty y Tiny, y servidores de aplicaciones Java EE de código abierto, como JOnAS, Resin, Caucho y Enhydra. También hay varios servidores de aplicaciones comerciales completos, de los cuales Oracle WebLogic e IBM WebSphere son los más populares. La Tabla 2-2 muestra algunos de estos servidores y las versiones que admitían varias especificaciones Java EE.

TABLA 2-2 : Versiones de contenedores y servidores de aplicaciones


Cada contenedor web o servidor de aplicaciones tiene sus propias ventajas y desventajas. La tarea de elegir un servidor de aplicaciones no se puede cubrir en un solo capítulo y está más allá del alcance de este libro. Se deben comprender las necesidades del proyecto de su organización y se debe elegir el contenedor web o servidor de aplicaciones adecuado que satisfaga esas necesidades. Se deben considerar los presupuestos operativos porque los servidores de aplicaciones comerciales tienden a tener un costo de licencia extremadamente alto. Todos estos factores afectarán su decisión y es posible que elija un servidor que ni siquiera se encuentra en la lista de este libro.

¿Por qué utilizarás Tomcat en este libro?
Ya se han esbozado muchas de las ventajas de Apache Tomcat (al que se hace referencia simplemente como Tomcat en el resto de este libro). Quizás la más importante de este libro es la facilidad con la que los desarrolladores pueden empezar a utilizar Tomcat. Sin duda, Tomcat es más fácil de poner en funcionamiento rápidamente que cualquier otro contenedor web, y proporciona todas las características que necesita para completar los ejemplos de este libro. Además, todos los principales IDE de Java proporcionan herramientas para ejecutar, implementar y depurar Tomcat, lo que facilita el desarrollo de su aplicación.

Aunque algunos desarrolladores prefieren utilizar otros contenedores web (y con el conocimiento adecuado, casi cualquier contenedor web puede resultar útil en una máquina de desarrollo), es difícil argumentar en contra del uso de Tomcat. Al utilizar Tomcat para este libro, puede centrarse en el código y las prácticas de desarrollo, prestando poca o ninguna atención a la gestión de su contenedor. El resto de este capítulo le ayudará a instalar y configurar Tomcat en su máquina. También le presenta la implementación y anulación de la implementación de aplicaciones con el administrador de Tomcat y la depuración de Tomcat en su IDE de Java.

## INSTALACIÓN DE TOMCAT EN SU MÁQUINA

Antes de poder instalar Tomcat en su máquina, debe descargarlo desde el sitio del proyecto Tomcat. Vaya a la página de descargas de Tomcat 8.0 y desplácese hacia abajo hasta la sección “Distribuciones binarias”. Hay muchas descargas en esta página y las únicas que necesita para este libro están bajo el encabezado “Core”. Como usuario de Windows, las dos descargas que le interesan son “32-bit/64-bit Windows Service Installer”(funciona para cualquier arquitectura de sistema) y el “zip de Windows de 32 bits” o el “zip de Windows de 64 bits” (según la arquitectura de su máquina). Si utiliza Linux, Mac OS X o algún otro sistema operativo, necesitará el zip que no sea de Windows, que se llama simplemente “zip”.

Instalación como servicio de Windows
Muchos desarrolladores quieren instalar Tomcat como un servicio de Windows. Esto tiene varias ventajas, especialmente en un entorno de producción o de control de calidad. Facilita la gestión de la memoria de la JVM y otros recursos, y simplifica enormemente el inicio automático de Tomcat cuando se inicia Windows. Sin embargo, en un entorno de desarrollo, instalar Tomcat como un servicio puede tener algunas desventajas. Esta técnica instala solo el servicio y no instala los scripts de línea de comandos que ejecutan Tomcat desde la línea de comandos. La mayoría de los IDE utilizan estos scripts de línea de comandos para ejecutar y depurar Tomcat desde el IDE. Puede instalar Tomcat como un servicio descargando el “Instalador de servicios de Windows de 32 bits/64 bits”, pero también necesita descargar el “zip de Windows” para ejecutar Tomcat desde su IDE.

Este libro no cubre la instalación de Tomcat como un servicio de Windows porque, por lo general, esto solo se haría en entornos de producción o control de calidad. La documentación del sitio web de Tomcat es muy útil si desea explorar esto más a fondo. Por supuesto, si no está utilizando Windows, el instalador de Windows no le será de utilidad. Hay formas de iniciar Tomcat automáticamente en otros sistemas operativos, pero también quedan fuera del alcance de este libro.

Instalación como una aplicación de línea de comandos
La mayoría de los desarrolladores de aplicaciones necesitan ejecutar Tomcat únicamente como una aplicación de línea de comandos y, por lo general, únicamente desde su IDE. Para ello, siga estos pasos:

Descargue el zip de Windows apropiado para la arquitectura (si usa Windows) o el zip que no es de Windows (si usa cualquier otro) de la página de descarga de Tomcat 8.0 y descomprima el directorio.
Coloque el contenido del directorio Tomcat de este archivo zip en la carpeta C:\Program Files\Apache Software Foundation\Tomcat 8.0de su máquina local (o en el directorio correspondiente para un servidor en su sistema operativo). Por ejemplo, el webappsdirectorio ahora debería estar ubicado en C:\Program Files\Apache Software Foundation\Tomcat 8.0\webapps.
Si utiliza Windows 7 o una versión más reciente, debe cambiar algunos permisos para que Tomcat sea accesible desde su IDE. Haga clic con el botón derecho Apache Software Foundationen el directorio C:\Program Filesy haga clic en Propiedades. En la pestaña Seguridad, haga clic en el botón Editar. Agregue su usuario o el grupo Usuarios y otorgue a esa entrada control total sobre el directorio.
Para configurar Tomcat para su primer uso, comience abriendo el archivo conf/tomcat-users.xmlen su editor de texto favorito. Coloque la siguiente etiqueta entre las <tomcat-users></tomcat-users>etiquetas XML:
    <user username="admin" password="admin" roles="manager-gui,admin-gui" />
ADVERTENCIA Esto configura un usuario administrador que puede utilizar para iniciar sesión en la interfaz de administración web de Tomcat. Por supuesto, esta combinación de nombre de usuario y contraseña es muy insegura y nunca debe utilizarse para servidores de producción o de acceso público. Sin embargo, para realizar pruebas en su máquina local es suficiente.

Abra el conf/web.xmlarchivo. Busque el texto org.apache.jasper.servlet.JspServlet. Debajo de la etiqueta que contiene este texto hay dos <init-param>etiquetas. En el próximo capítulo aprenderá sobre los parámetros de inicio de Servlet, pero por ahora agregue los siguientes parámetros de inicio debajo de los parámetros de inicio existentes:
        <init-param>
            <param-name>compilerSourceVM</param-name>
            <param-value>1.8</param-value>
        </init-param>
        <init-param>
            <param-name>compilerTargetVM</param-name>
            <param-value>1.8</param-value>
        </init-param>
De forma predeterminada, Tomcat 8.0 compila archivos JavaServer Pages con compatibilidad con el lenguaje Java SE 6 incluso si se ejecuta en Java SE 8. Estos nuevos parámetros de inicio de Servlet le indican a Tomcat que compile archivos JSP con características del lenguaje Java SE 8.

Después de realizar estos cambios y guardar estos archivos, ya debería estar listo para iniciar Tomcat y asegurarse de que se ejecuta correctamente. Abra un símbolo del sistema y cambie su directorio al directorio de inicio de Tomcat ( C:\Program Files\Apache Software Foundation\Tomcat 8.0).
Escriba el comando en un sistema operativo que no sea Windows y presione Entrar para verificar si la variable de entorno está configurada correctamente en el directorio de inicio de Java Development Kit (JDK). Si no es así, configure la variable de entorno y luego cierre la sesión y vuelva a iniciarla antes de continuar (consulte la Nota que sigue). Tomcat no puede ejecutarse sin que esta variable esté configurada correctamente.echo %JAVA_HOME% (or echo $JAVA_HOMEJAVA_HOME
Escriba el comando bin\startup.bat(o, bin/startup.shsi no utiliza Windows, presione Enter). Se abrirá una ventana de consola de Java que mostrará la salida del proceso Tomcat en ejecución. Después de unos segundos, debería ver el mensaje “INFO [main] org.apache.catalina.startup.Catalina.start Inicio del servidor en 1827 ms” o algo similar en la ventana de consola. Esto significa que Tomcat se ha iniciado correctamente.
NOTA: Al iniciarse, Tomcat busca inicialmente la JRE_HOME variable de entorno y la utiliza si está configurada. Si no lo está, busca la JAVA_HOME variable a continuación. Si no está configurada ninguna, Tomcat no se inicia. Sin embargo, para depurar Tomcat debe haberla JAVA_HOME configurado, por lo que es mejor simplemente continuar y configurarla.

Abra su navegador web favorito y navegue hasta http://localhost:8080/ . Debería ver una página que se parece a la Figura 2-1 . Esto significa que Tomcat se está ejecutando y que los JSP se están compilando correctamente con Java SE 8. Si esta pantalla no aparece o si observa un errorEn la consola Java, debes verificar los pasos anteriores y posiblemente consultar la documentación de Tomcat.

FIGURA 2-1

Cuando termine de usar Tomcat, puede detenerlo ejecutando el comando bin\shutdown.bat(o bin/shutdown.sh) en el símbolo del sistema en el directorio de inicio de Tomcat 8.0. La ventana de la consola de Java debería cerrarse y Tomcat se detendrá. Sin embargo, no lo haga todavía; en la siguiente sección, explorará la implementación y anulación de la implementación de aplicaciones en Tomcat. (Si ya ha cerrado Tomcat, no se preocupe. Es fácil volver a iniciarlo).

ADVERTENCIA Las primeras versiones de Tomcat 8.0 no admiten la compilación de JSP para Java 8. Sabrá que este es el caso de su versión si ve “ADVERTENCIA: Se ignora la VM 1.8 de origen desconocido” o algo similar en la consola de Java. Si es así, debe completar los siguientes pasos para “Configurar un compilador JSP personalizado”.

Configuración de un compilador JSP personalizado
Tomcat se entrega con el compilador Eclipse JDT y lo utiliza para compilar archivos JavaServer Pages en aplicaciones web. (Aprenderá más sobre los archivos JSP y cómo se compilan en el Capítulo 4). Esto permite que Tomcat se ejecute correctamente sin necesidad de una instalación de JDK. Con el compilador Eclipse, todo lo que necesita es una simple instalación de Java Runtime Edition (JRE). Debido a que los JSP suelen ser muy simples,El compilador Eclipse suele ser adecuado para cualquier entorno Tomcat. Sin embargo, existen circunstancias en las que no conviene utilizar el compilador Eclipse. Quizás encuentre un error en el compilador Eclipse que impida que uno de sus JSP se compile. O si sale una nueva versión de Java con características del lenguaje que desea utilizar en sus JSP, puede pasar algún tiempo hasta que Eclipse tenga un compilador compatible. Cualquiera sea el motivo, puede configurar fácilmente Tomcat para que utilice el compilador JDK en lugar de Eclipse.

Abra nuevamente el archivo de Tomcat conf/web.xmly búsquelo JspServletnuevamente.
Agregue el siguiente parámetro init, que le indica al Servlet que use Apache Ant con el compilador JDK para compilar JSP en lugar del compilador Eclipse.
        <init-param>
            <param-name>compiler</param-name>
            <param-value>modern</param-value>
        </init-param>
Tomcat no tiene una manera de usar el compilador JDK directamente, por lo que debe tener la última versión de Ant instalada en su sistema. También debe agregar el tools.jararchivo del JDK y los archivos ant.jarde Ant ant-launcher.jara su classpath. La forma más fácil de hacer esto es crear un bin\setenv.batarchivo y agregarle la siguiente línea de código (ignore las líneas nuevas aquí), reemplazando las rutas de archivo según sea necesario para su sistema.
set "CLASSPATH=C:\path\to\jdk8\lib\tools.jar;C:\path\to\ant\lib\ant.jar;
C:\path\to\ant\lib\ant-launcher.jar"
Por supuesto, esto se aplica únicamente a equipos con Windows. Para entornos que no sean Windows, debe crear un bin/setenv.sharchivo con el siguiente contenido y reemplazar las rutas de archivo según sea necesario para su sistema:

export CLASSPATH=/path/to/jdk8/lib/tools.jar:/path/to/ant/lib/ant.jar:
/path/to/ant/lib/ant-launcher.jar
Al ejecutar Tomcat con una configuración de compilación JSP personalizada, asegúrese de observar atentamente la salida en los registros de Tomcat. Si Tomcat no puede encontrar Ant o Ant no puede encontrar el compilador JDK, Tomcat recurre automáticamente al compilador Eclipse y solo muestra una advertencia en los registros.

## IMPLEMENTACIÓN Y ANULACIÓN DE APLICACIONES EN TOMCAT

En esta sección aprenderá a implementar y anular la implementación de aplicaciones web Java EE en Tomcat. Tiene dos opciones para lograrlo:

Manualmente colocando la aplicación en el webappsdirectorio
Uso de la aplicación de administración de Tomcat
Si aún no lo ha hecho, debe descargar la sample-deployment.waraplicación de muestra de la sección del Capítulo 2 en el sitio de descargas wrox.com . Esto es lo que debe usar para practicar la implementación y la anulación de la implementación.

Cómo realizar una implementación y anulación de implementación manual
Implementar una aplicación manualmente en Tomcat es simple: solo tiene que colocar el archivo en el directorio sample-deployment.warde Tomcat . Si Tomcat se está ejecutando, en unos momentos Tomcat debería descomprimir automáticamente el archivo de la aplicación en un directorio con el mismo nombre menos la extensión. Si Tomcat no se está ejecutando, puede iniciarlo y el archivo de la aplicación se descomprimirá cuando se inicie Tomcat. Cuando la aplicación se haya descomprimido, abra su navegador y navegue hasta http://localhost:8080/sample-deployment/ . Debería ver una página que se parece a la Figura 2-2 . Esto significa que la aplicación de muestra se ha implementado correctamente.webapps.war


FIGURA 2-2

Para anular la implementación de la aplicación, basta con realizar el proceso inverso. Elimine el sample-deployment.wararchivo y espere unos momentos. Cuando Tomcat detecte que se eliminó el archivo, anulará la implementación de la aplicación y eliminará el directorio descomprimido. La aplicación ya no será accesible desde su navegador. No es necesario cerrar Tomcat para realizar esta tarea.

Uso del administrador de Tomcat
También puede implementar una aplicación Java EE mediante la interfaz web del administrador de Tomcat. Para ello, siga estos pasos:

Abra su navegador y navegue a http://localhost:8080/manager/html .
Cuando se le solicite un nombre de usuario y una contraseña, ingrese admin como nombre de usuario y admin como contraseña (o lo que haya configurado en conf/tomcat-users.xml). La página que se le presente debería verse como la Figura 2-3 .

FIGURA 2-3

Desplácese hacia abajo hasta la sección Implementar y busque el formulario “Archivo WAR para implementar”. En el campo “Seleccionar archivo WAR para cargar”, elija el sample-deployment.wararchivo de su sistema de archivos, como se muestra en la Figura 2-4 , y luego haga clic en el botón Implementar. El archivo WAR se carga en Tomcat, que implementa la aplicación. El sample-deploymentdirectorio se vuelve a crear en el directorio de Tomcat webapps. Cuando finaliza, Tomcat lo regresa a la lista de aplicaciones donde puede ver que se ha implementado la aplicación de muestra, como se muestra en la Figura 2-5 .

FIGURA 2-4


FIGURA 2-5

Como antes, puedes ir a http://localhost:8080/sample-deployment/ y ver la página de muestra en la aplicación de muestra.
Ahora ha implementado la aplicación utilizando el administrador Tomcat.

La anulación de la implementación es igual de sencilla. En la página del administrador de Tomcat que vio anteriormente, debería ver un botón Anular implementación junto a la aplicación de muestra (consulte la Figura 2-5 ). Haga clic en este botón y la aplicación de muestra se anulará la implementación y se eliminará del webappsdirectorio. Cuando finalice, ya no podrá acceder a la aplicación en http://localhost:8080/sample-deployment/ .

## DEPURACIÓN DE TOMCAT DESDE SU IDE

Como desarrollador de Java EE, una de las habilidades más importantes que puede tener es la capacidad de implementar y depurar aplicaciones en Tomcat desde su IDE de Java. Esto le proporciona inconmensurables habilidades de resolución de problemas para determinar por qué una aplicación no se ejecuta o averiguar por qué ocurre el error que informó su cliente. Esta sección cubre la configuración, ejecución y depuración de aplicaciones web en Tomcat utilizando IntelliJ IDEA y Eclipse. Puede leer ambos conjuntos de instrucciones o solo el conjunto que pertenece al IDE que ha elegido; esa elección depende de usted.

En el resto de este libro hay muy pocas instrucciones para hacer esto. Esto mantiene el texto desvinculado de cualquier IDE en particular. Tampoco verá ninguna captura de pantalla específica de IDE después de este capítulo. Asegúrese de estar familiarizado y cómodo con la implementación y depuración de aplicaciones en Tomcat usando su IDE antes de continuar, incluso si eso significa repasar esta sección varias veces.

Uso de IntelliJ IDEA
Si utiliza IntelliJ IDEA 13 o una versión más reciente, solo tiene que seguir unos sencillos pasos para poner en funcionamiento sus aplicaciones web. Lo primero que debe hacer es configurar IntelliJ para que reconozcaSu instalación local de Tomcat u otro contenedor. Este es un paso que se realiza una sola vez: lo configura una vez en la configuración global de su IDE y luego puede usar el servidor de aplicaciones para cualquier proyecto de aplicación web. A continuación, configure cada proyecto de aplicación web para que use el contenedor configurado. Por último, solo necesita iniciar su aplicación desde IntelliJ y colocar puntos de interrupción donde desee depurar su aplicación.

Configuración de Tomcat 8.0 en IntelliJ
Para comenzar, debes configurar Tomcat en la lista de servidores de aplicaciones de IntelliJ.

Abra el cuadro de diálogo de configuración de IDE de IntelliJ. Con un proyecto abierto, puede ir a Archivo ⇒ Configuración, o hacer clic en el icono Configuración en la barra de herramientas (que se muestra aquí en el margen), o presionar Ctrl + Alt + S. Si no tiene un proyecto abierto, puede hacer clic en el botón Configurar y luego en el botón Configuración.
En el panel izquierdo del cuadro de diálogo Configuración, haga clic en Servidores de aplicaciones en Configuración de IDE. Inicialmente, no tiene ningún servidor de aplicaciones configurado.
Haga clic en el icono más verde para agregar un nuevo servidor de aplicaciones. Haga clic en el botón de exploración junto al campo Inicio de Tomcat para buscar y seleccionar el directorio de inicio de Tomcat (por ejemplo, C:\Program Files\Apache Software Foundation\Tomcat 8.0). Luego, haga clic en Aceptar. IntelliJ debería detectar automáticamente su versión de Tomcat y el cuadro de diálogo debería verse como el de la Figura 2-6 .

FIGURA 2-6

Haga clic en Aceptar nuevamente para terminar de agregar Tomcat a su lista de servidores de aplicaciones y cambie el nombre si lo desea. Todos los ejemplos de código IntelliJ que puede descargar para este libro asumen un nombre de servidor de aplicaciones de Tomcat 8.0 , por lo que para mayor facilidad debe cambiarle el nombre a Tomcat 8.0 si tiene otro nombre.
Haga clic en Aplicar para guardar los cambios y en Aceptar para cerrar el cuadro de diálogo Configuración.
Cómo agregar una configuración de Tomcat a un proyecto
Después de crear un proyecto y estar listo para implementarlo en Tomcat desde IntelliJ, debe agregar una configuración de ejecución/depuración de Tomcat a su proyecto.

Haga clic en el ícono de configuraciones de ejecución/depuración (una flecha hacia abajo) en la barra de herramientas, luego haga clic en Editar configuraciones.

En el cuadro de diálogo que aparece, haga clic en el icono más verde, desplácese hasta la parte inferior del menú Agregar nueva configuración, coloque el cursor sobre Servidor Tomcat y haga clic en Local. Esto crea una configuración de ejecución/depuración para ejecutar su proyecto en un Tomcat local, como se muestra en la Figura 2-7 .

FIGURA 2-7

Si Tomcat 8.0 es el único servidor de aplicaciones que ha agregado a IntelliJ, se seleccionará automáticamente como el servidor de aplicaciones que utilizará esta configuración de ejecución/depuración. Si tiene otros servidores de aplicaciones configurados, es posible que se seleccione uno de ellos, en cuyo caso debe hacer clic en el menú desplegable “Servidor de aplicaciones” y seleccionar Tomcat 8.0 en su lugar.
Asigne a la configuración de ejecución un nombre significativo. En la Figura 2-7 y en todos los proyectos de ejemplo de IntelliJ que descargue para este libro, la configuración de ejecución se llama Tomcat 8.0, como el servidor de aplicaciones que utiliza.
Probablemente verá una advertencia que indica que no hay artefactos marcados para su implementación. Corregir esto es simple. Haga clic en la pestaña Implementación y luego en el ícono más verde debajo del encabezado “Implementar al iniciar el servidor”. Haga clic en Artefacto y luego haga clic en el artefacto del archivo war expandido. Haga clic en Aceptar. Cambie el nombre del “Contexto de aplicación” para la implementación del artefacto a la URL relativa al servidor en la que desea implementarlo, como se muestra en la Figura 2-8 .

FIGURA 2-8

Haga clic en Aplicar y luego en Aceptar para guardar la configuración de ejecución/depuración y cerrar el cuadro de diálogo.
Puede descargar el proyecto Sample-Debug-IntelliJ desde el sitio de descarga de código wrox.com para ver una aplicación web de muestra ya configurada para ejecutarse en su servidor de aplicaciones Tomcat 8.0 local. (Sin embargo, aún debe configurar su instalación de Tomcat 8.0 en la configuración del IDE de IntelliJ).

Iniciar una aplicación y alcanzar puntos de interrupción
Ahora que ha configurado Tomcat en IntelliJ y ha configurado un proyecto IntelliJ para ejecutarse en Tomcat, está listo para iniciar la aplicación y depurarla dentro de su IDE.

Descargue el proyecto Sample-Debug-IntelliJ del sitio de descarga de código wrox.com y ábralo con IntelliJ IDEA.
Asegúrese de que la configuración de ejecución y depuración esté configurada correctamente para utilizar su servidor de aplicaciones Tomcat 8.0 local. Debe realizar esta comprobación para cada proyecto de muestra que descargue para este libro antes de intentar iniciarlo.
Al abrirlo, debería ver una pantalla como la Figura 2-9 , con dos puntos de interrupción establecidos para index.jsp.

FIGURA 2-9

Haga clic en el icono de depuración de la barra de herramientas (resaltado por el puntero del mouse en la Figura 2-9 ) o presione Shift + F9 para compilar e iniciar su aplicación en modo de depuración. IntelliJ debería iniciar su navegador predeterminado y debería acceder inmediatamente a los puntos de interrupción en index.jsp.
Debería ver nuevamente la página web de la Figura 2-2 para indicar que su aplicación se implementó correctamente.

NOTA: IntelliJ puede acceder a http://localhost:8080/sample-debug/ antes de iniciar su navegador. Esto se hace para garantizar que su aplicación se haya implementado correctamente. Si este es el caso, llegará a los puntos de interrupción dos veces: una vez cuando IntelliJ acceda a la aplicación y otra cuando su navegador se abra y acceda a la aplicación.

Usando Eclipse
El uso de Tomcat en Eclipse tiene algunas similitudes con el uso de Tomcat en IntelliJ IDEA, pero también tiene muchas diferencias y las pantallas se ven muy diferentes. Se sigue aplicando el mismo proceso básico: debe configurar Tomcat en la configuración global de Eclipse, configurarlo para un proyecto e iniciar y depurar el proyecto. En esta última parte de esta sección, aprenderá a usar Tomcat desde Eclipse en caso de que haya elegido esa plataforma como su IDE para este libro.

ADVERTENCIA Como se mencionó en la introducción, a la fecha de publicación de este libro, Eclipse aún no es compatible con Java SE 8, Java EE 7 o Tomcat 8.0. Debe esperar hasta el lanzamiento de Eclipse 4.4 Luna en junio de 2014 para obtener soporte para estas tecnologías. Por lo tanto, las instrucciones y figuras de Eclipse en esta sección pueden no ser completamente precisas y debe responder según sea necesario a los cambios realizados en la versión de lanzamiento de Eclipse Luna.

Configuración de Tomcat 8.0 en Eclipse
Para comenzar, debe configurar Tomcat 8.0 como entorno de ejecución en las preferencias globales de Eclipse. Para ello, siga estos pasos:

Abra su IDE Eclipse para desarrolladores de Java EE y vaya a Ventanas ⇒ Preferencias.
En el cuadro de diálogo Preferencias que aparece, expanda Servidor y, a continuación, haga clic en Entornos de ejecución. Aparecerá un panel Entornos de ejecución de servidor donde podrá administrar los servidores de aplicaciones y los contenedores web disponibles para todos sus proyectos de Eclipse.
Haga clic en el botón Agregar para abrir el cuadro de diálogo Nuevo entorno de ejecución del servidor.
Expande la carpeta Apache y selecciona Apache Tomcat v8.0, asegurándote de marcar la casilla “Crear un nuevo servidor local”. Luego haz clic en el botón Siguiente.
En la siguiente pantalla, haga clic en el botón Explorar y navegue hasta el directorio de inicio de Tomcat 8.0 (por ejemplo, C:\Program Files\Apache Software Foundation\Tomcat 8.0). Luego, haga clic en Aceptar.
En el menú desplegable JRE, seleccione su instalación local de Java SE 8 JRE. Nombre el servidor como desee. Los proyectos de ejemplo de Eclipse que descarga a lo largo de este libro suponen que el servidor se llama Apache Tomcat v8.0, que es el valor predeterminado de Eclipse. En este punto, debería ver una pantalla como la de la Figura 2-10 .

FIGURA 2-10

Haga clic en el botón Finalizar para terminar de agregar su servidor Tomcat local a Eclipse y luego haga clic en Aceptar para cerrar el cuadro de diálogo de preferencias.
Ahora está listo para usar Tomcat 8.0 en sus proyectos Eclipse.

Otra cosa que debe tener en cuenta es que, de forma predeterminada, Eclipse utiliza un navegador integrado para abrir sus aplicaciones web. Debe desactivar esta función y utilizar un navegador convencional, como Google Chrome, Mozilla Firefox o Microsoft Internet Explorer. Para cambiar esta configuración, vaya al menú Ventana ⇒ Navegador web y seleccione algo distinto a “0 Navegador web interno”. La opción “1 Navegador web predeterminado del sistema” debería ser suficiente en la mayoría de los casos, pero es fácil cambiar esta configuración con frecuencia para satisfacer sus necesidades en cualquier momento.

Uso del servidor Tomcat en un proyecto
Al crear un nuevo proyecto en Eclipse, debe seleccionar el servidor de tiempo de ejecución configurado que va a utilizar para ese proyecto en el primer cuadro de diálogo, como se muestra en la Figura 2-11 . Sin embargo, esto configura solo las bibliotecas para su aplicación. No selecciona el servidor Tomcat 8.0 que creó. Para ello, siga estos pasos:


FIGURA 2-11

Después de crear o abrir el proyecto, vaya a Proyecto ⇒ Propiedades y haga clic en el elemento de menú Servidor en el lado izquierdo del cuadro de diálogo Propiedades del proyecto que aparece.
De forma predeterminada, el servidor seleccionado es “<Ninguno>”, por lo que debe cambiarlo a “Servidor Tomcat v8.0 en localhost”, como se muestra en la Figura 2-12 .

FIGURA 2-12

Haga clic en Aplicar para guardar los cambios.
Cambie la URL del contexto de la aplicación en la que se implementa la aplicación en Tomcat (suponiendo que no la haya configurado al crear el proyecto). En el cuadro de diálogo Propiedades del proyecto, puede hacer clic en el elemento de menú Configuración del proyecto web y actualizar el campo “Raíz del contexto” para cambiar esta configuración.
Después de hacer clic en Aplicar para guardar los cambios, haga clic en Aceptar para cerrar el cuadro de diálogo.
Puede descargar el proyecto Sample-Debug-Eclipse desde el sitio de descarga de código wrox.com para ver una aplicación web de muestra ya configurada para ejecutarse en su servidor de aplicaciones Tomcat 8.0 local. (Sin embargo, aún necesita configurar su instalación de Tomcat 8.0 en las preferencias del IDE de Eclipse).

Iniciar una aplicación y alcanzar puntos de interrupción
Ahora está listo para iniciar su aplicación y depurarla desde Eclipse.

Descargue el proyecto Sample-Debug-Eclipse del sitio de descarga de código wrox.com y ábralo con Eclipse IDE para desarrolladores de Java EE.
Asegúrese de que la configuración del servidor esté configurada correctamente para utilizar el servidor de aplicaciones Tomcat 8.0 local. Debe realizar esta comprobación para cada proyecto de muestra que descargue para este libro antes de intentar iniciarlo.
Al abrirlo debería ver una pantalla como la Figura 2-13 , con un punto de interrupción ya establecido para index.jsp.

FIGURA 2-13

Haga clic en el icono Depurar de la barra de herramientas (resaltado por el puntero del ratón en la Figura 2-13 ) para compilar e iniciar su aplicación en modo de depuración. Eclipse debería iniciar el navegador configurado y debería alcanzar inmediatamente el punto de interrupción en index.jsp. Puede volver a ver la página web de la Figura 2-2 para indicar que su aplicación se implementó correctamente.
Para continuar desde el punto de interrupción, haga clic en el ícono de continuar (que se muestra aquí en el margen) en la barra de herramientas de Eclipse.
ADVERTENCIA Cuando ejecuta Tomcat desde Eclipse, Eclipse anula cualquier archivo conf\setenv.bat o configuración personalizada conf/setenv.sh que cree para configurar la compilación avanzada de JSP. Si no desea utilizar el compilador JDT de Eclipse para compilar sus JSP, debe agregar la CLASSPATH configuración de este archivo a otro archivo de configuración de Tomcat. Consulte la documentación de Tomcat para determinar el archivo apropiado donde colocarlo.

NOTA Probablemente haya notado que el JSP en Eclipse solo tiene un punto de interrupción, mientras que el JSP en IntelliJ IDEA tiene dos puntos de interrupción. El depurador JSP de Eclipse es mucho más limitado que el depurador JSP de IDEA, por lo que no es posible colocar un punto de interrupción en la línea 7 de este JSP en Eclipse.

## RESUMEN

En este capítulo, aprendió sobre los servidores de aplicaciones Java EE y los contenedores web y exploró varias implementaciones populares de ambos. Instaló Tomcat 8.0 en su máquina local, configuró la compilación JSP, la inició desde la línea de comandos y experimentó con la implementación y anulación de la implementación de aplicaciones en Tomcat. Por último, aprendió a configurar y ejecutar Tomcat 8.0 y a depurar sus aplicaciones utilizando IntelliJ IDEA y Eclipse IDE para desarrolladores de Java EE.

En el siguiente capítulo crearás Servlets y aprenderás cómo funcionan las aplicaciones web Java EE.
