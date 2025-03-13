# 4
Cómo automatizar sus compilaciones de CI/CD con Maven, Gradle y Jenkins
¿QUÉ HAY EN ESTE CAPÍTULO?
Construyendo con Maven
Construyendo con Gradle
Encontrar una dependencia
Integración con Jenkins
Escaneo con sonar
Explicación de las prácticas de CI/CD
Hasta ahora, has visto cómo escribir código en tu máquina en el Capítulo 2 , “Conociendo tu IDE: El secreto del éxito”, y cómo compartirlo con otros en el Capítulo 3 , “Colaboración en toda la empresa con Git, Jira y Confluence”. En este capítulo, verás cómo compilar y empaquetar el código usando Maven y Gradle.

Si bien es posible ejecutar Jenkins en su propia computadora, las empresas lo ejecutan en un servidor remoto, al igual que sus sistemas de control de versiones. Esto garantiza una compilación limpia y que no dependa del entorno de un solo desarrollador. Además, permite que Jenkins se ejecute más rápido al no competir con un desarrollador por los recursos de la computadora. Además, ¡el servidor de compilación nunca necesita suspenderse ni tomar vacaciones!

Jenkins realiza integración continua , que es el nombre de un proceso de compilación automatizado que recupera el código más reciente del repositorio de control de versiones, lo compila, ejecuta pruebas y controles de calidad, y luego lo empaqueta y, opcionalmente, lo implementa. A pesar del nombre, la integración continua no se ejecuta continuamente. Normalmente se configura para ejecutarse después de cada envío al repositorio. Ejecutar continuamente solo desperdiciaría recursos si el código no ha cambiado.

Como mencionamos, la integración continua de Jenkins también se puede configurar para implementar el software. La entrega continua va un paso más allá de la integración continua y garantiza que el software esté listo para implementarse.Producción. Con la entrega continua, el software suele implementarse en un entorno de preproducción. Con la entrega continua, la implementación en producción requiere un paso manual.

La práctica más avanzada es la implementación continua , que se implementa automáticamente en producción sin intervención manual. Esto requiere un alto grado de automatización y madurez de los procesos para evitar la introducción de problemas en la producción.

Existen numerosas herramientas de integración continua en la empresa, como GitLab CI y GitHub Actions. En este capítulo, abordamos Jenkins, pero los conceptos son similares en todas las tecnologías.

DESCARGAS DE CÓDIGOS PARA ESTE CAPÍTULO
El código fuente de este capítulo está disponible en la página del libro en [Insert www.wiley.com]. Haga clic en el enlace "Descargas". El código también se encuentra en [Insert] https://github.com/realworldjava/Ch04-CICD. Consulte el README.mdarchivo en ese repositorio para obtener más información.

CONSTRUYENDO CON MAVEN
Los servidores de compilación no compilan nada, al menos no sin ayuda. En cambio, coordinan herramientas como Maven o Gradle para compilar, probar e implementar el código. Si bien Maven puede, y a menudo lo hace, gestionar las necesidades de compilación, informes y documentación de un proyecto, a menudo se le denomina herramienta de compilación .

Uno de los principios de Maven es la convención sobre la configuración. Esto significa que se asumen muchas propiedades de configuración (aunque se pueden sobrescribir si es necesario). Este enfoque de aplicar valores predeterminados razonables tiene la ventaja de facilitar a los desarrolladores el cambio entre proyectos, ya que suelen estar configurados con los mismos valores predeterminados.

Por ejemplo, la mayoría de los proyectos Maven utilizan la estructura de directorios de la Figura 4.1, con un srcdirectorio bajo la raíz del proyecto que contiene un maindirectorio para el código que se empaquetará y otro testpara el código relacionado con las pruebas que no se implementará. El Capítulo 7 , "Prueba de código con herramientas de pruebas automatizadas", explicará cómo usar este testdirectorio. javaComo era de esperar, el subdirectorio contiene código fuente de Java y resourcesse utiliza para archivos de texto, como la configuración de la base de datos y otras propiedades de la aplicación. Este targetdirectorio es donde se almacenan los resultados de la compilación.


FIGURA 4.1 :Estructura de directorios en Maven

Construyendo un proyecto básico de Maven
Comencemos creando un proyecto Maven simple y luego analicemos algunas de sus características. Cada proyecto Maven tiene un pom.xmlarchivo. POM significa Modelo de Objetos del Proyecto y es un archivo XML que contiene información de compilación para nuestro proyecto. Para más información sobre XML, consulte el apéndice "XML y JSON". El pom.xmlarchivo más corto posible se ve así:

1:  <?xml version="1.0" encoding="UTF-8"?>
2:
3:  <project xmlns="http://maven.apache.org/POM/4.0.0"
4:     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
5:     xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
6:     https://maven.apache.org/xsd/maven-4.0.0.xsd">
7:
8:     <modelVersion>4.0.0</modelVersion>
9:
10:    <groupId>com.wiley.realworldjava.maven</groupId>
11:    <artifactId>basic-pom</artifactId>
12:    <version>1.0.0-SNAPSHOT</version>
13: </project>
Las líneas 1 a 8 son código repetitivo que se incluirá en cada archivo POM. Indican que este archivo XML está diseñado para analizarse como un POM de Maven. Normalmente, el IDE generará este código automáticamente al crear un nuevo proyecto. También puede copiar y pegar este código repetitivo desde otro proyecto de Maven.

Las líneas 10 a 12 son donde se especifican las coordenadas del proyecto Maven. El ID de grupo suele corresponder al nombre del paquete o a un prefijo del mismo. Crea un espacio de nombres para evitar conflictos con otros artefactos Maven. El ID de artefacto representa el nombre específico del proyecto dentro del ID de grupo. Finalmente, la etiqueta de versión permite asignar un número de versión a cada compilación para poder revisar y consultar versiones anteriores. Antes de publicar el código, se asigna un SNAPSHOTsufijo a la versión, lo que indica a Maven que no se trata de una versión final. (Aprenderá más sobre las versiones en las siguientes secciones). En conjunto, estas tres etiquetas se denominan las coordenadas GAV (ID de grupo, ID de artefacto, versión) del proyecto.

Para ejecutar una compilación en la línea de comandos, puede ejecutar mvn verifydesde el directorio que contiene el pom.xmlarchivo, lo que hará todo lo siguiente:

Descargue todas las dependencias necesarias para la compilación y almacénelas en su caché de Maven.
Copie cualquier archivo que encuentre src/main/resourcesen target/classes.
Compilar cualquier código a partir del src/main/javaalmacenamiento de los resultados en target/classes.
Copie cualquier archivo que encuentre src/test/resourcesen target/test-classes.
Compilar cualquier código a partir del src/test/javaalmacenamiento de los resultados en target/test-classes.
Ejecute comprobaciones en forma de pruebas unitarias para verificar que la compilación sea válida y cumpla con ciertos estándares de calidad.
Cree un archivo JAR llamado <artifactId>-<version>.jar(en este caso basic-pom-1.0.0-SNAPSHOT.jar) con los archivos que ahora se encuentran en target/classesy guárdelo en target.
Eso es mucho trabajo para un POM con 13 líneas, la mayoría repetitivas. Este es el poder de la convención sobre la configuración. Como no indicamos lo contrario, Maven asume lo predeterminado: que queremos compilar y probar el código, almacenando los resultados en un archivo JAR.

MAVEN 3 VS. MAVEN 4
Este libro utiliza Maven 3, ya que era la versión más reciente al momento de escribirlo. Maven 4 tiene un alto grado de retrocompatibilidad, por lo que todo lo aprendido seguirá siendo aplicable. Tenga en cuenta que el código estándar modelVersionse actualizará a la versión 4.1.0 cuando esté listo para usar Maven 4.

Comprensión del repositorio Maven y sus dependencias
Lo primero que hizo la compilación de Maven fue buscar dependencias . Estas son bibliotecas que la compilación necesita descargar para ejecutarse. Hay dos tipos de dependencias. Algunas son necesarias específicamente para el proyecto y se especifican en el POM. Las verá en breve. Otras son necesarias para el propio Maven. Al igual que los IDE que vio en el Capítulo 2 , Maven usa complementos para proporcionar funcionalidad. La primera vez que ejecuta una compilación de Maven, descarga estos complementos. Esto puede tardar un tiempo; de hecho, hay un chiste que dice que Maven necesita "descargar Internet".

Por defecto, Maven descarga todo lo que necesita de un repositorio llamado Maven Central. A diferencia de GitHub, que es un repositorio de código fuente, como se vio en el Capítulo 3 , Maven Central es un repositorio binario. Su propósito principal es almacenar artefactos que no se pueden abrir en un editor de texto, como archivos JAR.

A continuación se muestra la salida de Maven al descargar solo un complemento:

Downloading from central: https://repo.maven.apache.org/maven2/
org/apache/maven/plugins/maven-compiler-plugin/3.11.0/
maven-compiler-plugin-3.11.0.pom
Downloaded from central: https://repo.maven.apache.org/maven2/
org/apache/maven/plugins/maven-compiler-plugin/3.11.0/
maven-compiler-plugin-3.11.0.pom (9.8 kB at 28 kB/s)
Downloading from central: https://repo.maven.apache.org/maven2/
org/apache/maven/plugins/maven-compiler-plugin/3.11.0/
maven-compiler-plugin-3.11.0.jar
Downloaded from central: https://repo.maven.apache.org/maven2/
org/apache/maven/plugins/maven-compiler-plugin/3.11.0/
maven-compiler-plugin-3.11.0.jar (66 kB at 1.2 MB/s)
Como puede ver, hay dos pares de mensajes: uno cuando Maven inicia la descarga y otro cuando finaliza. Primero, Maven busca el POM de cada artefacto, lo que le indica si el artefacto necesita otras dependencias, también conocidas como dependencias transitivas , para ejecutarse. De ser así, Maven las busca y también las descarga, y así sucesivamente. Tras procesar el POM, Maven descarga el JAR solicitado.

Afortunadamente, el artefacto de cada GAV se descarga solo una vez y se almacena en tu repositorio local para uso futuro. En tu directorio personal, hay un .m2subdirectorio. En Windows, es C:\Users\<your id>\.m2. En Mac, es /Users/<your id>/.m2.

Dentro de la .m2carpeta hay una carpeta llamada repository, que contiene subdirectorios para cada ID de grupo. Los artefactos y las versiones se almacenan en subdirectorios debajo de ellos. Por ejemplo, los archivos descargados para el complemento del compilador se encuentran en este directorio:

.m2/repository/org/apache/maven/plugins/maven-compiler-plugin/3.11.0
El directorio incluye los archivos POM y JAR descargados, junto con .sha1los archivos , que contienen un hash que Maven usa para confirmar que el archivo se descargó correctamente.

Cada vez que ejecutas una compilación, Maven lee todo lo que puede de tu repositorio local. Si falta algo, Maven lo descargará desde Maven Central o desde tu repositorio binario corporativo. Esto garantiza que la caché de compilación local de Maven evite tener que descargar archivos repetidamente para cada compilación.

Como se mencionó anteriormente, la misma técnica funciona para las dependencias que se especifican explícitamente en el POM de Maven. Este ejemplo muestra un POM que especifica una dependencia en la eclipse-collectionsbiblioteca.

<?xml version="1.0" encoding="UTF-8"?>
 
<project xmlns="http://maven.apache.org/POM/4.0.0"
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
   xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
   https://maven.apache.org/xsd/maven-4.0.0.xsd">
 
   <modelVersion>4.0.0</modelVersion>
 
   <groupId>com.wiley.realworldjava.maven</groupId>
   <artifactId>with-dependency</artifactId>
   <version>1.0.0-SNAPSHOT</version>
    
   <dependencies>
       <dependency>
           <groupId>org.eclipse.collections</groupId>
           <artifactId>eclipse-collections</artifactId>
           <version>11.1.0</version>
       </dependency>
    </dependencies>
</project>
Puede especificar tantas dependencias como desee simplemente agregando más <dependency>etiquetas dentro de la <dependencies>etiqueta.

NOTA:  Eclipse Collections no está relacionado con el IDE de Eclipse. Recibe su nombre de la Fundación Eclipse y va más allá del marco de colecciones incluido en el Kit de Desarrollo de Java (JDK).

Ahora que has visto dos ejemplos de un POM, omitiremos el texto estándar y comenzaremos los ejemplos con la <groupId>etiqueta.

MÁS SOBRE LAS DEPENDENCIAS DE MAVEN
A menudo, el GAV es suficiente para especificar una dependencia. Sin embargo, se puede incluir más información en una <dependency>etiqueta.

Una etiqueta opcional es el clasificador. Se utiliza cuando se publican varios artefactos con el mismo artifactId. Por ejemplo, un clasificador podría utilizarse para diferenciar entre archivos JAR de diferentes versiones del JDK o de diferentes sistemas operativos.

<classifier>jdk21</classifier>
Otra etiqueta opcional es la typeetiqueta , que normalmente se utiliza cuando el tipo de empaquetado es algo distinto a jar, como por ejemplo un war(archivo web).

<type>war</type>
También debe estar familiarizado con la scopeetiqueta opcional.

Maven admite los siguientes ámbitos:

compileLa dependencia está disponible para los directorios src/main/javay src/test/javadurante la compilación. Este es el alcance predeterminado para todas las dependencias que no especifican un alcance.
testLas dependencias solo están disponibles para [nombre del usuario src/test/java]. Este es el ámbito más común para especificar.
provided:Las dependencias son necesarias para la compilación, pero no se empaquetarán porque se espera que se proporcionen en el tiempo de ejecución.
runtimeLas dependencias no son necesarias para la compilación, pero serán necesarias para la ejecución.
system:Esto es como providedel alcance, pero debes proporcionar explícitamente el JAR.
import:Esto se utiliza dentro de una <dependencyManagement>sección para importar dependencias potenciales de otro archivo POM (por ejemplo, una lista de materiales [BOM] POM, que describimos más adelante en el capítulo).
Diferenciación de las fases del ciclo de vida
Para iniciar la compilación anterior de Maven, ejecutamos mvn verify. El verifycomando corresponde a una de las fases del ciclo de vida de Maven. Cada fase ejecuta la fase anterior del ciclo de vida antes de ejecutarse. La Tabla 4.1 muestra las fases más comunes del ciclo de vida predeterminado de Maven.

TABLA 4.1 :Fases del ciclo de vida predeterminado de Maven

FASE	DESCRIPCIÓN
validate	Verifique que el archivo POM esté correctamente formateado y que se proporcione toda la información necesaria.
compile	validate+ compilar código en src/main/java.
test	compile+ ejecutar pruebas unitarias (ver Capítulo 7 ).
package	test+ crear archivo JAR.
integration-test	package+ ejecutar cualquier prueba de integración (ver Capítulo 7 ).
verify	integration-test+ confirmar que el paquete es válido.
install	verify+ instala el paquete en tu repositorio Maven local para que lo utilicen otras compilaciones.
deploy	install+ publicar el paquete fuera de su máquina.
Conviértete en el mejor amigo de verifyMaven, ya que es la fase más común que se ejecuta en tu máquina. Si trabajas en varios proyectos interrelacionados, necesitarás [nombre del proyecto install], pero no debería ser tu opción preferida, ya que tarda más en ejecutarse y no suele ser necesario.

¿Y QUÉ PASA CON LA LIMPIEZA?
Esta cleanfase elimina todo lo generado en ejecuciones anteriores, lo que garantiza una compilación limpia. No se ejecuta por defecto con las fases mencionadas, ya que las compilaciones se ejecutan más rápido al no tener que recompilar todo desde cero. Al ejecutar en un servidor de compilación como Jenkins, puede ser útil ejecutar una compilación limpia. Sin embargo, generalmente solo es necesario ejecutarla cleanen el propio equipo cuando surgen problemas.

Tenga en cuenta también que puede ejecutar más de una fase en el mismo comando, por lo que es común escribir esto:

mvn clean verify 
Explorando el POM
En esta sección, aprenderá acerca de muchas de las capacidades disponibles en el POM.

Trabajar con propiedades
En código Java, no es recomendable codificar "números mágicos" (valores sin contexto) en las clases. En su lugar, es mejor usar una constante con nombre. De igual forma, en un POM, es común colocar los números de versión y otros datos de configuración en propiedades, que normalmente se incluirían al principio del archivo POM. Esto también permite compartir números de versión entre múltiples dependencias que deben mantener la misma versión. El siguiente método es equivalente al POM anterior, excepto que extrae el número de versión en una propiedad:

<groupId>com.wiley.realworldjava.maven</groupId>
<artifactId>with-properties</artifactId>
<version>1.0.0-SNAPSHOT</version>
 
<properties>
   <eclipse.collections.version>11.1.0</eclipse.collections.version>
</properties>
    
<dependencies>
   <dependency>
      <groupId>org.eclipse.collections</groupId>
      <artifactId>eclipse-collections</artifactId>
      <version>${eclipse.collections.version}</version>
   </dependency>
</dependencies>
Puedes definir tantas propiedades como quieras en una <properties>etiqueta. En este caso, hay una con el nombre eclipse.collections.versiony el valor 11.1.0. Para usar la propiedad, consulta el nombre de la variable dentro del ${}marcador de posición y Maven lo reemplazará automáticamente con el valor de la propiedad.

Especificación de la información del proyecto
Como se mencionó anteriormente, Maven aspira a gestionar la mayor cantidad posible de información de su proyecto. Si bien no es exhaustivo, este ejemplo le da una idea del tipo de información que se puede incluir.

11: <groupId>com.wiley.realworldjava.maven</groupId>
12: <artifactId>project-info</artifactId>
13: <version>1.0.0-SNAPSHOT</version>
14: <name>Project Info Test</name>
15: <description>This project shows using more tags 
16:    than just the GAV to describe the project</description>
17: <url>https://www.wiley.com/en-us/Real+World+Java%3A+Helping+
18:    You+Navigate+the+Java+Ecosystem-p-9781394275724</url>
19: <inceptionYear>2024</inceptionYear>
20:
21: <properties>
22:    <git.url>https://github.com/realworldjava/Ch04-CICD</git.url>
23: </properties>
24:
25: <scm>
26:    <connection>scm:git:h${git.url}.git</connection>
27:    <developerConnection>scm:git:${git.url}.git</developerConnection>
28:    <url>${git.url}</url>
29:    <tag>HEAD></tag>
30: </scm>
Las líneas 14 y 15 proporcionan un nombre para mostrar y detalles del proyecto, que pueden ser utilizados por otras herramientas. La línea 17 muestra la URL para obtener más información sobre el proyecto, o en este caso, la URL del libro. La línea 19 muestra el año de inicio del proyecto.

Algunos complementos requieren información adicional. Por ejemplo, las líneas 25 a 30 muestran un formato para especificar una URL de GitHub que se utiliza al realizar lanzamientos. También muestra la ventaja de definir una propiedad; esta se utiliza tres veces.

Otra información que se puede incluir en un POM incluye un enlace al proyecto Jira y la información de contacto de todos los desarrolladores del proyecto.

Comprensión de los números de versión
Al trabajar con código, se usa una SNAPSHOTversión como 1.0.0-SNAPSHOT. Una vez listo para el lanzamiento, SNAPSHOTse elimina el sufijo y se convierte en 1.0.0.

Quizás hayas notado que los números de versión tienen tres partes separadas por puntos. Los artefactos de Maven suelen seguir el control de versiones semántico . El primer número se incrementa para las versiones principales, que podrían introducir nuevas interfaces de programación de aplicaciones (API) o funcionalidades deficientes. El segundo número se usa para versiones menores, generalmente compatibles y posiblemente mejoradas. El tercer número se incrementa generalmente para la corrección de errores.

No todos los proyectos siguen esta convención de nomenclatura, pero la mayoría sigue variantes de ella, como agregar .betao .releaseal final de un nombre para obtener más información.

Además, los números inferiores a 1.0.0 suelen indicar una versión preliminar. Por lo tanto, 0.2.6 podría indicar que el proyecto no está listo para su lanzamiento inicial completo.

Es importante entender esto, así que considere la secuencia de eventos indicada en la Tabla 4.2 .

Uso de complementos comunes
Como viste antes, los plugins le dan a Maven su funcionalidad. También proporcionan el mecanismo para personalizar el comportamiento. Los plugins de Maven están bien documentados, y comprender cómo usar la documentación es tan importante como saber cómo escribir código que los use.

En las siguientes secciones, verá cómo usar un complemento común y comprender la documentación. Luego, aprenderá a evitar configuraciones repetidas y, a continuación, una descripción general de otros complementos.

Configurar un complemento
Analicemos el plugin del compilador. Con su buscador favorito, busque "complemento del compilador Maven", lo que le llevará a [nombre del plugin] https://maven.apache.org/plugins/maven-compiler-plugin, como se muestra en la Figura 4.2 . La mayoría de los plugins son fáciles de encontrar con una simple búsqueda. Además, los plugins comunes comparten un formato de documentación, así que una vez que comprenda el plugin del compilador, sabrá qué necesita para los demás.

TABLA 4.2 :Ejemplo de número de versión

VERSIÓN	EJEMPLO DE SIGNIFICADO
0.0.1-SNAPSHOT	Comenzar el trabajo inicial.
0.0.1	Listo para probadores.
0.0.2-SNAPSHOT	Ups. Encontramos un error. Trabaja en ello.
0.0.2	Error corregido. Listo de nuevo para los probadores.
1.0.0-SNAPSHOT	Listo para el gran momento. Prepárense para el lanzamiento de la versión 1.0.0.
1.0.0	Listo para distribuir 1.0.0.
1.0.1-SNAPSHOT	Ups. Otro error. Estoy trabajando en el error.
1.0.1	Error corregido. Lo conseguimos esta vez.
1.1.1-SNAPSHOT	Es hora de trabajar en una pequeña mejora.
1.1.1	Listo para distribuir mejoras menores.
2.0.0-SNAPSHOT	Trabajando en el próximo lanzamiento importante

FIGURA 4.2 :Página de inicio de la documentación del compilador Maven

La página de documentación del plugin enumera los objetivos que forman parte del plugin, en este caso compiler:compile, y compiler:testCompile. También indica a qué fase del ciclo de vida se vinculan automáticamente, si corresponde. Estos objetivos se vinculan a las fases compiley test-compile, respectivamente. Los plugins no necesitan estar vinculados a una fase específica; se pueden llamar explícitamente. Sin embargo, en este capítulo, todos los plugins están vinculados. El capítulo 7 muestra un ejemplo del uso de código para vincularlos integration-testsa una fase del ciclo de vida, de modo que se ejecuten automáticamente durante la compilación.

La navegación izquierda de la página de documentación incluye opciones de menú para lo siguiente:

Objetivos: Detalles sobre todos los complementos incluidos, con especial atención a los parámetros obligatorios y opcionales.
Uso: Muestra cómo incluir el complemento en su POM
Ejemplos: Uno o más enlaces que muestran cómo configurar escenarios comunes
Este ejemplo muestra cómo configurar el complemento del compilador para usar Java 21:

<groupId>com.wiley.realworldjava.maven</groupId>
<artifactId>compile</artifactId>
<version>1.0.0-SNAPSHOT</version>
 
<properties>
   <java.version>21</java.version>
</properties>
    
<build>
   <plugins>
      <plugin>
         <groupId>org.apache.maven.plugins</groupId>
         <artifactId>maven-compiler-plugin</artifactId>
         <version>3.13.0</version>
         <configuration>
            <source>${java.version}</source>
            <target>${java.version}</target>
         </configuration>
      </plugin>
   </plugins>
</build>
Presta atención a la configurationetiqueta. Ahí es donde se ubican los parámetros en la documentación de "objetivos". En este caso, especifica que quieres usar Java 21 tanto para compilar como para generar el bytecode.

SUGERENCIA:  Si obtienes error: invalid target release: 21, significa que tienes una versión anterior de Java en tu ruta.

Uno de los ejemplos en la documentación es cómo “Pasar argumentos del compilador” y es el siguiente:

<project>
   […]
   <build>
      […]
      <plugins>
         <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-compiler-plugin</artifactId>
            <version>3.13.0</version>
            <configuration>
               <compilerArgs>
                  <arg>-verbose</arg>
                  <arg>-Xlint:all,-options,-path</arg>
               </compilerArgs>
            </configuration>
         </plugin>
      </plugins>
      […]
   </build>
   […]
</project>
Al comparar este ejemplo con el anterior, se puede observar que la configurationsección contiene argumentos del compilador. La documentación suele […]indicar que podría haber otro código en su POM en esas ubicaciones.

Reconociendo complementos comunes
Ahora que entiendes cómo leer la documentación de un plugin, podemos presentarte otros plugins comunes. Cada uno tiene opciones de configuración personalizadas que puedes consultar al usarlos en tus proyectos. Los siguientes plugins comunes se encuentran en el grupo id org.apache.maven.plugins:

maven-assembly-pluginCrea archivos zip para combinaciones de archivos. Útil al implementar en múltiples entornos con diferentes configuraciones.
maven-compiler-plugin:Compila tu código.
maven-dependency-plugin:Varios objetivos para trabajar con dependencias, como enumerarlas o descomprimirlas.
maven-deploy-plugin:Carga el artefacto creado a un repositorio binario.
maven-enforcer-plugin:La compilación falla si su POM no sigue las reglas especificadas.
maven-failsafe-pluginEjecuta pruebas de integración. Consulte el capítulo 7 para obtener más información.
maven-install-plugin:Actualiza su repositorio local con el artefacto creado.
maven-jar-plugin:Crea un artefacto de archivo JAR.
maven-javadoc-plugin:Cree páginas HTML de Javadoc para su proyecto.
maven-release-plugin:Varios objetivos para lanzar su software, incluido el etiquetado del repositorio y la actualización del número de versión de POM.
maven-resources-plugin:Copia los recursos de origen y de prueba al directorio de salida.
maven-shade-plugin:Crea un uber-jar que contenga tus clases junto con las clases de todas las dependencias.
maven-site-plugin:Genera páginas HTML con información sobre el proyecto actual, como Javadoc y notas de la versión.
maven-source-plugin:Crea un archivo JAR que contiene el código fuente del proyecto.
maven-surefire-pluginEjecuta pruebas unitarias. Consulte el capítulo 7 para obtener más información.
No todos los complementos tienen el mismo ID de grupo. Algunos son proporcionados por otras organizaciones. Por ejemplo, Sonar, una herramienta de análisis estático, proporciona un complemento. Está en el ID de grupo org.sonarsource.scanner.maveny el ID de artefacto sonar-maven-plugin. El ID de grupo muestra que es proporcionado por SonarSource y no por Apache.

Trabajar con un padre POM
Como sabes, en Java, cada clase tiene una superclase. De forma similar, en Maven, cada POM tiene un POM padre . En Java, el ancestro común es java.lang.Objectincluso si no se extendsespecifica nada. De igual forma, Maven tiene un super POM que se hereda si no se especifica ningún padre. Este super POM es donde se especifican las convenciones sobre valores predeterminados de configuración, como el src/main/javadirectorio. Puedes encontrar un enlace al super POM en "Referencias adicionales". Como alternativa, puedes ejecutar mvn help:effective-pomdesde el directorio de tu proyecto para ver el POM efectivo, que incluye tu configuración junto con todo lo que hereda del super POM.

Creando tu propio POM para padres
En la empresa, es común tener un POM personalizado a nivel de empresa, departamento o equipo. Esto permite que los estándares locales estén centralizados.

Un POM padre usa el tipo de empaquetado pom. Esto indica a Maven que no espere código Java y que, en su lugar, publique únicamente el archivo POM. A continuación, un ejemplo:

<groupId>com.wiley.realworldjava.maven</groupId>
<artifactId>parent</artifactId>
<version>1.0.0-SNAPSHOT</version>
<packaging>pom</packaging>
Hay diferentes valores que se pueden asignar a la etiqueta de empaquetado. Por ejemplo, jares el valor predeterminado, que indica que se debe crear un JAR. Por el contrario, pomse especifica al crear un POM principal. Un POM principal puede contener propiedades y complementos como cualquier otro POM.

SUGERENCIA:  Una vez que haya creado un POM principal, recuerde ejecutar mvn install en lugar de mvn verify para el POM principal, ya que eso lo coloca en su repositorio Maven local y lo pone a disposición de todos los hijos potenciales.

Un POM secundario especifica el padre que desea utilizar mediante el GAV:

<artifactId>child</artifactId>
<version>1.0.0-SNAPSHOT</version>
 
<parent>
   <groupId>com.wiley.realworldjava.maven</groupId>
   <artifactId>parent</artifactId>
   <version>1.0.0-SNAPSHOT</version>
</parent>
Tenga en cuenta que el elemento secundario no especifica un groupId. Esta etiqueta es opcional si el elemento principal y el secundario tienen el mismo groupId.

Herencia de los padres
Un POM principal solo es útil si tiene contenido. Vea este POM principal de ejemplo, que presenta dos nuevas secciones dependencyManagement:pluginManagement

<groupId>com.wiley.realworldjava.maven</groupId>
<artifactId>parent</artifactId>
<version>1.0.0-SNAPSHOT</version>
<packaging>pom</packaging>
 
<properties>
    <java.version>21</java.version>
    <eclipse.collections.version>11.1.0</eclipse.collections.version>
    <compiler.plugin.version>3.13.0</compiler.plugin.version>
</properties>
 
<dependencyManagement>
   <dependencies>
      <dependency>
         <groupId>org.eclipse.collections</groupId>
         <artifactId>eclipse-collections</artifactId>
         <version>${eclipse.collections.version}</version>
      </dependency>
   </dependencies>
</dependencyManagement>
 
<build>
   <pluginManagement>
      <plugins>
         <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-compiler-plugin</artifactId>
            <version>${compiler.plugin.version}</version>
            <configuration>
               <source>${java.version}</source>
               <target>${java.version}</target>
            </configuration>
         </plugin>
     </plugins>
   </pluginManagement>
</build>
Observe primero que en esta propertiessección se definen varias propiedades para que puedan usarse en lugar de codificar números en otras partes del POM. Esta técnica permite a los POM secundarios usar valores predeterminados estándar, pero también sobrescribir cualquiera de las propiedades. Esto es como tener una protectedvariable en una superclase en Java. Resulta útil poder cambiar cualquiera de estos valores de forma independiente sin tener que cambiar a un POM principal diferente ni depender de un proyecto diferente para realizar un cambio.

A continuación viene la dependencyManagementsección. El contenido debería verse como dependenciesen un POM normal. La diferencia clave es que los artefactos dependencyManagementno se cargan hasta que se hace referencia a ellos en un POM secundario. De igual forma, pluginManagementconfigura los complementos en caso de que el POM secundario los use.

¿Cómo especifica un hijo que quiere usar una dependencia o un complemento? Observe un POM hijo que usa este padre:

<artifactId>child</artifactId>
<version>1.0.0-SNAPSHOT</version>
 
<parent>
   <groupId>com.wiley.realworldjava.maven</groupId>
   <artifactId>parent</artifactId>
   <version>1.0.0-SNAPSHOT</version>
 </parent>
 
 <dependencies>
   <dependency>
      <groupId>org.eclipse.collections</groupId>
      <artifactId>eclipse-collections</artifactId>
   </dependency>
</dependencies>
 
<build>
   <plugins>
      <plugin>
         <groupId>org.apache.maven.plugins</groupId>
         <artifactId>maven-compiler-plugin</artifactId>
      </plugin>
   </plugins>
</build>
Observe que la configuración es mínima. No es necesario especificar los números de versión ni la configuración; todo proviene del POM principal.

Supongamos que no desea la eclipse-collectionsdependencia del POM principal. No hay problema: en el POM secundario, simplemente omita la dependencia y se ignorará.

<artifactId>child-without-dependency</artifactId>
<version>1.0.0-SNAPSHOT</version>
 
<parent>
   <groupId>com.wiley.realworldjava.maven</groupId>
   <artifactId>parent</artifactId>
   <version>1.0.0-SNAPSHOT</version>
 </parent>
 
<build>
   <plugins>
      <plugin>
         <groupId>org.apache.maven.plugins</groupId>
         <artifactId>maven-compiler-plugin</artifactId>
      </plugin>
   </plugins>
</build>
Otros cambios también son sencillos. Si desea una versión diferente de eclipse-collectionso de maven-compiler-plugin, anule la propiedad de versión en el POM secundario, lo que anulará la del POM principal. Como alternativa, puede agregar una etiqueta de versión explícita en lugar de heredarla.

Trabajar con un proyecto multimódulo
Hasta ahora en este capítulo, cada vez que ejecutamos una compilación de Maven, se ejecutó un [nombre del pom.xmlproyecto]. A veces se tiene un grupo de proyectos relacionados. En este caso, se puede crear un proyecto multimódulo. Sigue habiendo un POM principal, pero con un proyecto multimódulo, todos los hijos están en subdirectorios. Por ejemplo, la estructura de directorios se vería así:

module-parent
|- pom.xml
|- module-services
|  |- pom.xml
| -module-util
    |- pom.xml
Primero veamos el POM padre:

<groupId>com.wiley.realworldjava.maven</groupId>
<artifactId>module-parent</artifactId>
<version>1.0.0-SNAPSHOT</version>
<packaging>pom</packaging>
 
<modules>
   <module>module-services</module>
   <module>module-util</module>
</modules>
El POM contiene una nueva modulessección que contiene una lista de los módulos de los subdirectorios del proyecto que deben incluirse en la compilación. El orden en que se listan los módulos no es necesariamente el orden en que se compilarán.

Un hijo puede contener opcionalmente a otro en su lista de dependencias. En nuestro ejemplo, module-services"will depend on" module-util. Maven es lo suficientemente inteligente como para determinar el orden correcto para construir los hijos según sus dependencias.

SUGERENCIA:  Si module-services depende de module-util, entonces module-util no puede depender de module-services. Esto crearía una dependencia cíclica y provocaría un fallo en la compilación de Maven.

A continuación, veremos el module-utilPOM, que es agradable y simple, y solo hace referencia al padre:

<artifactId>module-util</artifactId>
<version>1.0.0-SNAPSHOT</version>
 
<parent>
   <groupId>com.wiley.realworldjava.maven</groupId>
   <artifactId>module-parent</artifactId>
   <version>1.0.0-SNAPSHOT</version>
 </parent>
El module-servicePOM hace lo mismo pero también especifica una dependencia:

<artifactId>module-services</artifactId>
<version>1.0.0-SNAPSHOT</version>
 
<parent>
   <groupId>com.wiley.realworldjava.maven</groupId>
   <artifactId>module-parent</artifactId>
   <version>1.0.0-SNAPSHOT</version>
</parent>
 
<dependencies>
   <dependency>
      <groupId>com.wiley.realworldjava.maven</groupId>
      <artifactId>module-util</artifactId>
      <version>1.0.0-SNAPSHOT</version>
   </dependency>
</dependencies>
Como en este ejemplo todo está contenido en un solo proyecto, se puede ejecutar mvn clean verifyen el module-parentnivel. El resultado contiene la lista de módulos creados y si se ejecutaron correctamente.

[INFO] --------------------------------------------------------
[INFO] Reactor Summary for module-parent 1.0.0-SNAPSHOT:
[INFO] 
[INFO] module-parent ………………… SUCCESS [  0.077 s]
[INFO] module-util ………………….. SUCCESS [  0.571 s]
[INFO] module-services ………………. SUCCESS [  0.040 s]
[INFO] --------------------------------------------------------
Tenga en cuenta que Maven se ejecutó module-servicesen último lugar porque dependía de module-util.

Uso de otras funciones de Maven
Si bien hay muchas características de Maven, esta sección cubre algunas con las que probablemente te toparás, incluidas la configuración de las propiedades del sistema, el uso de una lista de materiales y el lanzamiento de tu proyecto.

Configuración de las propiedades del sistema
Las propiedades del sistema Java son argumentos opcionales de la línea de comandos que modifican el comportamiento de la compilación. Puedes pasarlas al llamar a Maven desde -Dla línea de comandos, por ejemplo:

mvn -Dproject.build.sourceEncoding=UTF-8 clean verify
Se puede identificar una propiedad del sistema porque empieza por -D. Se pueden especificar otras propiedades del sistema en el POM, en la sección de configuración de un complemento. Por ejemplo, al escribir pruebas unitarias, se puede especificar lo siguiente:

<configuration>
   <systemPropertyVariables>
       <myPropertyName>myPropertyValue</myPropertyName>
   </systemPropertyVariables>
</configuration>
Consulta la documentación de tu complemento para obtener información detallada. Asegúrate de seguir la documentación para saber si debes pasar la propiedad del sistema a Maven o a un complemento dentro del POM.

Uso de una lista de materiales
Una lista de materiales es un archivo POM especial que especifica dependencias opcionales. Resulta útil cuando se incorporan muchas dependencias relacionadas entre sí.

Una lista de materiales utiliza la gestión de dependencias, como se vio en la sección del POM principal. El proveedor de la lista de materiales certifica que las versiones de las dependencias incluidas en ella sean compatibles entre sí.

La forma más común de utilizar una lista de materiales es especificarla en una dependencyManagementsección de su POM de la siguiente manera:

<groupId>com.wiley.realworldjava.maven</groupId>
<artifactId>using-bom</artifactId>
<version>1.0.0-SNAPSHOT</version>
 
<properties>
   <jackson.bom.version>2.17.0</jackson.bom.version>
</properties>
 
<dependencyManagement>
   <dependencies>
      <dependency>
         <groupId>com.fasterxml.jackson</groupId>
         <artifactId>jackson-bom</artifactId>
         <version>${jackson.bom.version}</version>
         <scope>import</scope>
         <type>pom</type>
      </dependency>   
   </dependencies>
</dependencyManagement>
Tenga en cuenta que " scopeis" import, que solo se permite cuando type"is" pom. Este ámbito expande el valor de las dependencias POM importadas como si las hubiera incluido directamente en " dependencyManagement. Es mucho más fácil de leer que si las hubiera escrito todas. Por ejemplo, " jackson-bomtiene más de 60 dependencias especificadas". ¡Y solo tiene jackson.bom.versionque mantener actualizado un número () en lugar de todas las dependencias individualmente!

Liberando su proyecto
En algún momento, terminas el trabajo inicial de tu proyecto y estás listo para publicarlo. maven-release-pluginTiene varios objetivos. Se ejecutan desde el comando Maven, como mvn verify. Los cuatro más útiles son los siguientes:

release-clean:Limpie todos los archivos provisionales de versiones anteriores.
release-prepareVerificar que el proyecto esté listo para su lanzamiento. Por ejemplo, el POM no puede hacer referencia SNAPSHOTa dependencias, ya que esto impediría una versión repetible (recuerde que SNAPSHOTlas versiones están sujetas a cambios). release-prepareTambién actualiza el número de versión en el POM.
release-perform:Etiquete el código en el control de versiones y almacene el artefacto en un repositorio binario.
release-rollback:Restaurar los archivos POM de un archivo prepare.
Conociendo Maven en el IDE
Como vio en el Capítulo 2 , usar el entorno de desarrollo integrado (IDE) puede ser mucho más eficiente que ejecutar desde la línea de comandos. Dado que ejecutar una compilación es una operación tan básica, la mostramos en los tres IDE principales.

Usando IntelliJ
Si tiene un proyecto Maven, verá un icono de "m" minúscula que representa Maven en la barra lateral derecha. Haga clic en él para expandir la ventana de Maven. Expanda la opción "Ciclo de vida" como se muestra en la Figura 4.3 . Puede hacer doble clic en el objetivo deseado (por ejemplo, [nombre del verifyproyecto]) para ejecutar una compilación o hacer clic derecho para ver más opciones.


FIGURA 4.3 :Ejecución de Maven desde IntelliJ

IntelliJ ofrece otras opciones para Maven. Por ejemplo, el POM efectivo es útil para ver el aspecto del POM una vez aplicadas todas las configuraciones heredadas. La Figura 4.4 muestra que puede encontrar esta opción haciendo clic derecho en el proyecto y seleccionando el menú Maven.


FIGURA 4.4 :Visualización del POM efectivo en IntelliJ

Si su proyecto tiene muchas dependencias, puede resultarle útil hacer clic derecho en el proyecto en la barra lateral de Maven y seleccionar "Analizar Dependencias". En esta lista, puede hacer clic en cualquier dependencia y ver su origen, incluso si es transitiva.

GRÁFICO DE DEPENDENCIA
IntelliJ también permite mostrar un gráfico de dependencias, una herramienta visual que muestra las dependencias transitivas y sus relaciones. Para usarlo, haga clic en Maven en la barra lateral derecha y luego en el icono "Mostrar diagrama" en la parte superior, como se muestra en la Figura 4.5 .


FIGURA 4.5 :Gráfico de dependencia de IntelliJ

Usando Eclipse
En Eclipse, se ejecuta una compilación de Maven haciendo clic derecho en el proyecto en el Explorador de paquetes y seleccionando el menú Ejecutar. La Figura 4.6 muestra este menú, donde puede hacer clic para seleccionar un objetivo a ejecutar.

Eclipse también permite ver la jerarquía de dependencias y POM vigente al abrir el pom.xmlarchivo. El editor cuenta con pestañas para ambos, como se puede ver en la Figura 4.7 .

Usando VS Code
En VS Code, tienes un menú desplegable "Maven" en la esquina inferior izquierda. Al expandirlo, verás los objetivos en la Figura 4.8 . Puedes hacer clic derecho en cualquiera de ellos para ejecutar tu compilación de Maven.

Para ver el POM efectivo, haga clic derecho en el pom.xmlarchivo y seleccione Maven en el menú. Luego, haga clic en "Mostrar POM efectivo", como se muestra en la Figura 4.9 .


FIGURA 4.6 :Ejecución de Maven desde Eclipse


FIGURA 4.7 :Visualización del POM efectivo en Eclipse


FIGURA 4.8 :Ejecución de Maven desde VS Code


FIGURA 4.9 :Ejecución de Maven desde VS Code

Si bien existe una lista de dependencias en VS Code, actualmente no está al nivel de IntelliJ y Eclipse.

Configuración de los ajustes de Maven para la empresa
En la empresa, Maven Central rara vez se utiliza directamente como repositorio binario. En su lugar, se utiliza un repositorio binario como JFrog Artifactory o Sonatype Nexus como proxy. Esta solución ofrece, entre otras ventajas:

Rendimiento: Los artefactos se descargan de Internet una vez y se almacenan en caché dentro de la intranet para un acceso rápido.
Seguridad: proporciona controles sobre quién puede acceder a artefactos particulares y puede escanearlos en busca de vulnerabilidades de seguridad antes de ponerlos a disposición de los desarrolladores.
Anonimato: Solo una solicitud de su organización se envía a Internet, y todas las demás llamadas provienen de la caché. Esto evita que se filtre la prevalencia del uso de un artefacto en su organización.
Auditoría: Los repositorios generalmente requieren autenticación, lo que permite ver quién descargó qué artefactos.
Repositorios personalizados: el repositorio binario empresarial puede alojar bibliotecas internas y bibliotecas de terceros que no están disponibles en Maven Central.
Todas las configuraciones generales de Maven se configuran en un archivo llamado settings.xml, incluidas las ubicaciones de los repositorios, las credenciales de autenticación, los perfiles predeterminados y otras configuraciones.

Puedes tener los settings.xmlarchivos en uno o dos lugares. Las propiedades globales, como la URL de tu repositorio binario, generalmente se configuran en [nombre del archivo] <maven install>/conf/settings.xml. Las propiedades específicas del usuario, como las contraseñas de token (idealmente cifradas), pueden incluirse en [nombre del archivo <user home>/.m2/settings.xml]. Si se especifican ambas, se fusionan y, si hay duplicados, se utilizan las específicas del usuario.

Los settings.xmlarchivos generalmente se personalizarán para su entorno. Esto no es obligatorio y, si se omite, Maven usará el repositorio local predeterminado en ~/.m2/repositorysistemas Linux y Mac, o C:\Users\<username>\.m2\repositoryen Windows. Utilizará Maven Central ( https://repo.maven.apache.org/maven2) como repositorio remoto predeterminado para las dependencias binarias. Esto es adecuado para uso doméstico; puede preguntar a sus compañeros de equipo cómo configurarlo en su empresa.

CONSTRUYENDO CON GRADLE
Maven y Gradle comparten muchas similitudes, y ambos se utilizan ampliamente en el ámbito empresarial. Gradle también es la herramienta de compilación predeterminada para aplicaciones Android. Dado que ya hemos analizado Maven en detalle, abordaremos Gradle con más detalle.

Mientras que Maven usa [nombre de archivo] pom.xml, Gradle usa un archivo llamado [nombre de archivo] build.gradlepara especificar configuraciones como dependencias, complementos y tareas. El archivo de compilación se especifica en Groovy o Kotlin, según su elección. Ambos son lenguajes que se ejecutan en la Máquina Virtual de Java (JVM), al igual que Java.

Al igual que Maven, Gradle prioriza la convención sobre la configuración. La srcestructura de directorios es la misma, pero la salida se guarda en un builddirectorio en lugar de en un targetdirectorio, como se muestra en la Figura 4.10 .


FIGURA 4.10 :Estructura de directorios en Maven

Cuando el build.gradlearchivo contiene configuración específica del proyecto, el settings.gradlearchivo opcional puede contener más información sobre su proyecto.

Gradle generará un archivo llamado gradlew.batpara ejecutarse en Windows y un gradlewarchivo para ejecutarse en Linux y Mac. El gradledirectorio contiene un wrappersubdirectorio, que contiene un archivo JAR con el código que realmente ejecuta Gradle.

NOTA:  La sintaxis de Gradle se vuelve más compleja a medida que aumentan las necesidades de compilación. Este capítulo solo cubre los conceptos básicos.

Construyendo un proyecto básico de Gradle
Comencemos creando un proyecto Gradle sencillo antes de analizar algunas características. Primero, revisemos el settings.gradlearchivo:

rootProject.name = 'basic-gradle'
Eso es todo, ¡y es bastante breve! El settings.gradlearchivo más simple solo contiene el nombre del proyecto, que es equivalente a [nombre del proyecto] artifactIden Maven.

El build.gradlearchivo es un poco más largo:

1:  plugins {
2:     id 'java'
3:  }
4:
5:  group = 'com.wiley.realworldjava.gradle'
6:  version = '1.0.0-SNAPSHOT'
7:
8:  repositories {
9:     mavenCentral()
10: }
Las líneas 1 a 3 especifican que se trata de un proyecto Java. Las líneas 5 y 6 proporcionan el grupo y la versión. Combinado con el nombre del proyecto de [nombre del proyecto] settings.gradle, esto es suficiente para definir las coordenadas del proyecto.

Finalmente, las líneas 8 a 10 indican que esta compilación usará Maven Central como repositorio predeterminado para descargar dependencias. Maven y Gradle generan el mismo formato de artefactos y, por lo tanto, pueden usar el mismo repositorio binario remoto.

Para ejecutar una compilación en la línea de comandos, ejecute ./gradlew builddesde el directorio que contiene build.gradle.

Esto generará una gran cantidad de resultados dinámicos en pantalla. En lugar de registrar todos los resultados secuencialmente, como en Maven, Gradle actualiza dinámicamente la salida de la consola con el progreso de la compilación. Finalmente, muestra un resumen de los resultados:

Starting a Gradle Daemon (subsequent builds will be faster)
> Task :compileJava
> Task :processResources
> Task :classes
> Task :jar
> Task :assemble
> Task :compileTestJava
> Task :processTestResources
> Task :testClasses
> Task :test NO-SOURCE
> Task :check UP-TO-DATE
> Task :build
 
BUILD SUCCESSFUL in 0s
5 actionable tasks: 5 executed
Las tareas que se listan en esta salida serán similares a la salida de Maven. Compilan el proyecto, ejecutan las pruebas y crean un artefacto. Los archivos creados se encuentran en las siguientes ubicaciones:

build/lib:Contiene el basic-gradle-1.0.0.jararchivo.
build/classesContiene los archivos de clase generados durante la compilación. Están separados en [nombre del archivo] build/classes/java/mainy [nombre del archivo build/classes/java/test].
build/resources:Contiene copias de los recursos separados en build/resources/mainy build/resources/test.
GROOVY CONTRA KOTLIN
Tiene la opción de usar Kotlin en build.gradlelugar de Groovy. Estas dos opciones de lenguaje se conocen como lenguaje específico de dominio (DSL) para Gradle. La compatibilidad con Kotlin se añadió recientemente, pero la documentación se ha actualizado completamente para que sea compatible con ambos.

Los ejemplos básicos de Gradle son similares en Groovy y Kotlin. Primero, el settings.gradle.ktsarchivo:

rootProject.name = "basic-gradle"
La única diferencia es que Kotlin requiere comillas dobles. En Groovy, se permiten comillas simples o dobles, siendo las simples más comunes. A continuación, el build.gradle.ktsarchivo.

plugins {
   `java-library`
}
 
group = "com.wiley.realworldjava.gradle"
version = "1.0.0-SNAPSHOT"
 
repositories {
    mavenCentral()
}
Además de las comillas dobles, tenga en cuenta que en la versión de Kotlin java-libraryse escriben entre comillas invertidas. Finalmente, los nombres de archivo de compilación de Kotlin tienen una .ktsextensión.

En este capítulo, mostraremos otras diferencias entre los archivos de compilación de Groovy y Kotlin a medida que presentamos cada característica.

Comprensión del repositorio local de Gradle y sus dependencias
Al igual que Maven, Gradle almacena localmente los artefactos descargados. En tu directorio personal, hay un .gradlesubdirectorio. En Windows, es C:\Users\<your id>\.gradle. En Linux y Mac, es /Users/<your id>/.gradle.

Gradle almacena mucho más que artefactos descargados para agilizar tus compilaciones. Las dependencias descargadas se almacenan en el directorio .gradle/caches/modules-2/files-2.1.

Por ejemplo, los archivos descargados para eclipse-collectionsestán en este directorio:

.gradle/caches/modules-2/files-2.1/org.eclipse.collections/
   eclipse-collections/11.1.0/
El directorio tiene un subdirectorio cuyo nombre es un hash, lo que confirma que el archivo se descargó correctamente. Ese subdirectorio contiene el archivo JAR.

Para especificar esta dependencia en Groovy, agréguela a la sección de dependencia en su build.gradlearchivo.

dependencies {
   implementation group: 'org.eclipse.collections', 
      name: 'eclipse-collections', version: '11.1.0'
}
Estas son las mismas coordenadas que viste anteriormente en Maven. El implementation`especifica` es el tipo de dependencia más común, el que se usa para la compilación. Ten en cuenta que classifiertambién se permite cuando se necesita para diferenciar un artefacto.

Gradle también admite una abreviatura para especificar el grupo completo, el nombre y la versión de una dependencia utilizando un único valor:

dependencies {
   implementation 'org.eclipse.collections:eclipse-collections:11.1.0'
}
En esta sintaxis, las coordenadas están en una cadena separada por dos puntos.

La sintaxis Kotlin correspondiente se incluiría en el build.gradle.ktsarchivo de la siguiente manera:

dependencies {
   implementation("org.eclipse.collections:eclipse-collections:11.1.0")
}
Esta vez, la llamada de implementación parece un método. Los tres enfoques especifican claramente el grupo, el nombre y la versión para que Gradle sepa qué se busca.

TIPOS DE DEPENDENCIAS DE GRADLE
En el ejemplo anterior, se vio implementationcomo el tipo de configuración de dependencia. Algunos de los tipos de dependencia comunes incluyen los siguientes:

implementation:Disponible en tiempo de ejecución para su aplicación
testImplementation: Disponible desde test/javapero no desdesrc/java
compileOnly: Disponible para compilar pero no en tiempo de ejecución
runtimeOnly: Disponible en tiempo de ejecución pero no para compilar
Especificación de variables
Dado que un archivo de compilación de Gradle es en realidad código de Groovy o Kotlin, se pueden especificar variables en el código. Por ejemplo, este código de Groovy declara una variable:

def collVersion = "11.1.0"
 
dependencies {
   implementation 
   "org.eclipse.collections:eclipse-collections:${collVersion}"
}
Groovy usa defla sintaxis para declarar una variable. ${}Gradle debe sustituir el valor de la variable. Para que la expansión funcione, se deben usar comillas dobles. En Groovy, las cadenas entre comillas simples no permiten esta función.

Por el contrario, un archivo de compilación de Kotlin también puede usar una variable:

val collVersion = "11.1.0"
 
dependencies {
   implementation 
   "org.eclipse.collections:eclipse-collections:${collVersion}"
}
La única diferencia entre ambos es que Groovy usa defpara declarar una variable, mientras que Kotlin usa valpara declarar variables inmutables y varvariables mutables. Dado que la versión se declara una sola vez y no se modifica en el archivo de compilación, este ejemplo usa val.

Uso del complemento de Java
En Maven, viste que había varios plugins como maven-compiler-plugin, maven-surefire-pluginy maven-jar-plugin. En Gradle, el plugin de Java contiene la mayor parte de esa funcionalidad. El enlace a la documentación del plugin de Java se encuentra en la sección "Referencias adicionales". Documenta las personalizaciones que puedes realizar. Por ejemplo, el siguiente ejemplo define la versión de Java que se usará:

java {
   toolchain {
      languageVersion = JavaLanguageVersion.of(21)
   }
}
Quizás hayas notado que no indicamos si este era un ejemplo de Groovy o Kotlin. ¡Es de ambos! Este código en particular tiene la misma sintaxis en ambos lenguajes.

CONSEJO:  Además del java complemento Gradle, existe un java-library complemento que lo extiende. Este java-library complemento añade funcionalidad adicional, como la configuración de la API.

La página del complemento de Java incluye la configuración de pruebas, Javadoc y empaquetado. También incluye descripciones para configurar los cambios en los valores predeterminados, como los directorios de origen.

NOTA:  Gradle también admite compilaciones multiproyecto, como las compilaciones multimódulo de Maven. Se agrega una include instrucción al settings.gradle archivo.

Conociendo Gradle en el IDE
Al igual que Maven, es fácil ejecutar una compilación de Gradle en los tres IDE principales.

En IntelliJ, hay un icono de elefante en la barra lateral derecha de los proyectos Gradle. Este es el logotipo de Gradle. Una vez identificado el logotipo, siga estos pasos para ejecutar una compilación de Gradle:

Haga clic en el logotipo para expandir la ventana de Gradle.
Ampliar la opción Tareas.
Expandir compilación. La figura 4.11 muestra la interfaz de usuario en este punto.
Haga clic derecho en la tarea deseada, como Compilar, y elija la opción Ejecutar.

FIGURA 4.11 :Ejecución de Gradle desde IntelliJ

SUGERENCIA:  El menú "Analizar Dependencias" también está disponible para proyectos Gradle, al igual que para proyectos Maven. Simplemente abra la barra lateral de Gradle, haga clic derecho en el proyecto y seleccione "Analizar Dependencias".

En Eclipse, comience con la vista "Tareas de Gradle" en la parte inferior de la pantalla. Luego, siga estos pasos para ejecutar una compilación de Gradle:

Ampliar el proyecto.
Expandir Construir. La figura 4.12 muestra esta vista.
Haga clic derecho en Compilar y seleccione Ejecutar tareas de Gradle.

FIGURA 4.12 :Ejecución de Gradle desde Eclipse

En VS Code, la extensión Maven está incluida en el paquete de extensiones de Java. Para Gradle, debe instalar la extensión usted mismo. Vaya a Marketplace e instale la extensión Gradle para Java.

Una vez instalada la extensión y abierto un proyecto de Gradle, verá el logotipo del elefante en el panel de navegación izquierdo. Siga estos pasos para ejecutar una compilación de Gradle:

Ampliar proyectos Gradle.
Amplíe el nombre de su proyecto.
Expandir tareas.
Expandir compilación. La figura 4.13 muestra el aspecto de VS Code en este punto.
Haga clic derecho en Compilar y seleccione Ejecutar tarea.
ENCONTRANDO UNA DEPENDENCIA
Tanto si usas Maven como Gradle, con frecuencia necesitarás encontrar las coordenadas de los proyectos en Maven Central. Una forma de encontrarlas es ir a [nombre del proyecto] https://central.sonatype.comy buscar tu artefacto. La página resultante incluye un menú desplegable para Maven y las variantes de Gradle, para que puedas copiarlo y pegarlo en tu compilación.


FIGURA 4.13 :Ejecución de Gradle desde VS Code

Sin embargo, hay una manera más rápida. Si buscas "Maven Central" y el nombre del artefacto en tu buscador favorito, probablemente el primer resultado sea [nombre del archivo] https://mvnrepository.com. Por ejemplo, si buscas "Maven Central Eclipse Collections" [nombre del archivo] https://mvnrepository.com/artifact/org.eclipse.collections/eclipse-collections. El sitio del Repositorio de Maven fue creado por un desarrollador en España y contiene la misma información que Maven Central. En este libro, usamos [nombre del archivo] mvnrepository.comal mencionar URLs debido a su mejor optimización para motores de búsqueda.

La Figura 4.14 muestra las opciones disponibles al hacer clic en una versión específica de un artefacto.

Al momento de escribir este artículo, elegimos la versión de Eclipse Collections 11.1.0para el ejemplo de este capítulo. Tenga en cuenta que existe una versión posterior, 12.0.0.M3. M3Significa "hito 3". Una versión de hito es una versión disponible públicamente para probar nuevas funciones y precede a la versión final. Dado que no es común usar dependencias de hito en el código de producción, elegimos la versión más reciente.

En la Figura 4.14 , bajo la advertencia sobre la versión posterior, se muestran pestañas para varios sistemas de compilación. Seleccione su sistema de compilación, copie la información de dependencia y péguela en su archivo de compilación POM o Gradle.

SUGERENCIA  En la figura, las pestañas SBT, Ivy y Grape son otros sistemas de compilación especializados que no se tratan en este libro.


FIGURA 4.14 :Encontrar dependencias

INTEGRACIÓN CON JENKINS
Jenkins se autodenomina un "servidor de automatización de código abierto" y, de hecho, puede automatizar prácticamente todo. Sin embargo, la mayoría de la gente lo considera un servidor de integración/despliegue continuo (CI/CD), ya que se centra en la compilación y el despliegue.

Jenkins es de código abierto y gratuito. Cloudbees vende una versión con contenido y soporte propietarios, pero está disponible en el sitio web de Cloudbees, no en el de Jenkins, por lo que no hay riesgo de confusión.

En esta sección, aprenderá cómo instalar Jenkins, qué complementos comunes instalar y cómo ejecutar una compilación.

Instalación de Jenkins
Para instalar Jenkins, puedes ir a la página de descarga en "Referencias adicionales". Verás que hay muchas opciones en esa página.

Primero, decide si prefieres la versión estable o la versión semanal. Los paquetes estables se publican mensualmente y Jenkins les aplica correcciones de seguridad y errores durante un tiempo. Cada tres meses, una de las versiones estables se convierte en la versión de soporte a largo plazo (LTS). Para entornos domésticos, cualquier versión es válida. Las empresas suelen optar por una versión LTS o una versión con soporte del proveedor. En nuestro ejemplo, usaremos la última versión estable.

A continuación, debe decidir el formato de descarga de Jenkins. Una opción es obtenerlo como archivo web (WAR) para ejecutarlo en un servidor de aplicaciones web como Tomcat. También puede obtenerlo como paquete del sistema operativo para instalarlo como binario o como imagen de Docker. En este capítulo, usaremos la imagen de Docker como ejemplo. El enlace para descargar Docker también se encuentra en la sección "Referencias adicionales". Cualquiera de estas opciones es válida para probar Jenkins en su equipo personal.

Para Docker, abra la aplicación "Docker Desktop" para asegurarse de que Docker se esté ejecutando en su equipo. A continuación, abra una línea de comandos y ejecute el siguiente comando para descargar la última versión estable de Jenkins:

docker pull jenkins/jenkins
La salida se verá así, donde se descarga cada una de las capas de la imagen de Docker:

Using default tag: latest
latest: Pulling from jenkins/jenkins
60bdaf986dbe: Pull complete 
dfad4ee37376: Pull complete 
206558d801c7: Pull complete 
a5c2ffb5ffef: Pull complete 
f0c0bc8bfcc6: Pull complete 
064531224ab4: Pull complete 
96aa304ced3c: Pull complete 
056f1f47a471: Pull complete 
ac5fc7f80726: Pull complete 
8a59881e61b3: Pull complete 
361281efe43a: Pull complete 
aa0d9cfb3420: Pull complete 
Digest: sha256:d4f805f9c225ee72c6ac8684d635eb8ec236569977f4cd6f9acd7c24a5d56985
Status: Downloaded newer image for jenkins/jenkins:latest
docker.io/jenkins/jenkins:latest
A continuación, ejecuta el contenedor Docker:

docker run --name jenkins -p 8080:8080 jenkins/jenkins
Este comando le asigna a tu contenedor Docker el nombre "jenkins" para que puedas consultarlo más adelante. También expone el puerto 8080 para que puedas acceder a él desde un navegador web. Si ese puerto está en uso en tu equipo, puedes usar cualquier puerto disponible.

NOTA:  Solo se usa el run comando la primera vez. Después, inicia Jenkins llamándolo docker start jenkins .

La salida de la consola incluirá un mensaje como este:

Jenkins initial setup is required. 
An admin user has been created and a password generated.
Please use the following password to proceed to installation:
 
4ab39e58b99e4519b3edbf7e4df21d51
 
This may also be found at: /var/jenkins_home/secrets/initialAdminPassword
Anota esta contraseña inicial para poder iniciar sesión. A continuación, abre un navegador y ve a http://localhost:8080. Jenkins te pedirá que introduzcas la contraseña que acabas de anotar. Pégala y haz clic en Continuar.

Jenkins te preguntará si quieres "Instalar plugins sugeridos" o "Seleccionar plugins para instalar". Elige los plugins sugeridos para empezar rápidamente. Si observas la pantalla durante la instalación del plugin, notarás que Jenkins descarga más que solo los plugins que aparecen en pantalla. Al igual que las dependencias de Maven y Gradle, los plugins de Jenkins dependen de otros plugins de Jenkins. Por lo tanto, Jenkins también descargará esas dependencias transitivas.

A continuación, Jenkins te pide que configures tu primer usuario administrador. Recuerda el nombre de usuario y la contraseña que elegiste, ya que los necesitarás para volver a acceder. ¡Pero ya no necesitas la larga contraseña inicial de la instalación!

Finalmente, Jenkins te pide que confirmes la URL. Usar la URL predeterminada http://localhost:8080es suficiente. Jenkins mostrará la pantalla "¡Jenkins está listo!". Simplemente haz clic en "Comenzar a usar Jenkins".

Aprendiendo la terminología de Jenkins
El vocabulario de Jenkins incluye palabras que quizás no conozcas. En esta sección, aprenderás este vocabulario para comprender lo que sucede.

Jenkins tiene un controlador que administra los agentes . Un agente es un proceso que ejecuta las tareas de Jenkins. Puede tener uno o más agentes. El término " nodo" se usa como sinónimo de agente. De forma predeterminada, se obtiene un agente en la misma máquina que el controlador. Puede configurar agentes adicionales en la misma máquina o en diferentes máquinas. Puede eliminar los agentes en la máquina del controlador para tener una mayor separación de tareas. Anteriormente, el controlador se llamaba maestro y el agente esclavo . Puede consultar el vocabulario antiguo en la documentación.

Un trabajo de Jenkins se refiere a la configuración de lo que se desea ejecutar. Una compilación es una ejecución específica de ese trabajo. Un paso de compilación es una operación individual dentro de una compilación. Jenkins limita el número de trabajos simultáneos que se ejecutan en un agente al mismo tiempo, permitiéndole especificar el número de ranuras o ejecutores . Cada agente puede tener uno o más ejecutores. Esto permite ejecutar varios trabajos simultáneamente en un solo agente.

Existen varias opciones para configurar trabajos. Por ejemplo, se pueden configurar como trabajos de estilo libre o trabajos de canalización . Un trabajo de estilo libre utiliza una interfaz de usuario para especificar la configuración. Una canalización utiliza código para proporcionar los detalles.

Los trabajos se inician mediante activadores . Un tipo popular de activador es una confirmación de código fuente. Después de todo, la integración continua solo funciona si se automatizan las compilaciones para que se inicien cada vez que algo cambie. También se pueden usar activadores basados ​​en tiempo, que se inician según una programación específica. Por ejemplo, podría querer ejecutar pruebas lentas durante la noche. Se puede hacer que un trabajo active otro, una estrategia útil para encadenar tipos de trabajos. Finalmente, se pueden hacer que eventos externos a Jenkins activen un trabajo mediante una API.

El panel muestra todos tus trabajos. Puedes organizarlos en carpetas . De hecho, puedes anidar tantos niveles de carpetas como quieras. También puedes crear vistas para controlar lo que ves.

Jenkins almacena los archivos de compilación en un espacio de trabajo . Algunos ejemplos de archivos de compilación son los archivos extraídos de Git y el directorio de destino o compilación de tu compilación de Maven o Gradle. Los elementos creados por una compilación se denominan artefactos . Los artefactos se pueden archivar para que puedas verlos en Jenkins incluso después de eliminar el espacio de trabajo.

Creación de empleos
En las siguientes secciones, aprenderá cómo crear tres tipos de trabajos.

Un trabajo sencillo de estilo libre
Un trabajo que ejecuta Maven
Uno que ejecuta Gradle y una canalización
Los trabajos de estilo libre requieren que especifiques tu configuración de compilación mediante la interfaz de usuario de Jenkins. Este enfoque tiene una curva de aprendizaje más sencilla que las canalizaciones y funciona en la mayoría de los casos. Los trabajos de estilo libre te permiten ver el espacio de trabajo mediante un enlace en el panel de navegación izquierdo.

Las canalizaciones te permiten expresar tu compilación mediante código. También te permiten dividirla en etapas.

Existen dos tipos de pipelines: con scripts y declarativos. En este libro, utilizamos el pipeline con scripts para Maven y el pipeline declarativo para Gradle para que puedas ver un ejemplo de cada uno. Los trabajos de pipeline proporcionan un enlace a espacios de trabajo en compilaciones específicas, en lugar de a nivel de trabajo.

Creando un trabajo simple de estilo libre
Para crear un trabajo, siga estos pasos:

Haga clic en Nuevo elemento en la navegación izquierda.
Asígnele un nombre (freestyle-timer en nuestro ejemplo).
Seleccione el tipo de trabajo Proyecto Freestyle.
Haga clic en Aceptar.
Jenkins creará el trabajo y te llevará automáticamente a la pantalla de configuración. Un trabajo consta de varias secciones de configuración, como se muestra en la Figura 4.15 .


FIGURA 4.15 :Secciones de estilo libre de Jenkins

General contiene casillas de verificación para que selecciones tus opciones. Por ejemplo, puedes controlar cuántas compilaciones antiguas guarda Jenkins o si se ejecuta otra compilación si la actual está en ejecución.

La gestión del código fuente te permite especificar el sistema de control de versiones que utilizas. Git se incluye con los plugins recomendados. Si utilizas un VCS diferente, puedes instalar un plugin para él desde la página del Administrador de plugins de Jenkins. También hay campos para la URL del repositorio y las credenciales necesarias para conectarte.

Los disparadores de compilación te permiten elegir qué inicia tu compilación. En este ejemplo, usaremos "Compilación periódica" para mostrar cómo se usa una programación. También hay opciones para un disparador de confirmación de GitHub y para sondear el repositorio. El disparador que indica a GitHub que inicie una compilación se llama " push" . Por el contrario, el sondeo solicita al repositorio que compruebe periódicamente si ha habido cambios y, de ser así, ejecute la compilación.

El entorno de compilación permite configurar el comportamiento de Jenkins. Por ejemplo, se puede configurar Jenkins para que agregue marcas de tiempo a cada entrada del registro o para definir cuándo se debe finalizar una compilación de larga duración.

Los pasos de compilación son la compilación propiamente dicha, donde se configura la ejecución de uno o más pasos. Por ejemplo, puedes hacer que Jenkins ejecute un comando desde la línea de comandos o configurar una compilación de Maven aquí.

Las acciones posteriores a la compilación permiten gestionar el resultado de una compilación. Por ejemplo, se puede enviar una notificación por correo electrónico o publicar un informe.

Ahora que comprendes lo que puede hacer una tarea de estilo libre, creemos una sencilla que muestre "hola" cada hora. Primero, debes configurar el disparador de compilación para que se compile periódicamente. Puedes usar una sintaxis similar a la de cron (cron es el planificador integrado de Unix).

# MINUTE HOUR DOM MONTH DOW
* * * * *
Jenkins le recomendará que puede utilizar H, en lugar de especificar un tiempo preciso. Hcalcula un hash basado en el nombre del trabajo para distribuir trabajos en diferentes momentos, como se muestra aquí:

H * * * *
Sin embargo, existe una mejor manera. Jenkins proporciona un alias para cada una de las frecuencias comunes, como @hourly, @daily, @weeklyy @monthly. Esto significa que solo necesitas escribir esto:

@hourly
Al salir del área de texto de programación, Jenkins muestra cuándo se ejecutó el trabajo por última vez y cuándo se ejecutará próximamente. Esta es una forma práctica de comprobar que la expresión cumple con lo esperado.

Ahora es el momento de añadir un paso de compilación. Si usa Linux/Mac, seleccione "Ejecutar Shell"; si usa Windows, seleccione "Ejecutar comando por lotes de Windows". En cualquier caso, introduzca el siguiente comando:

echo "hello"
La figura 4.16 muestra la configuración para este trabajo cuando se ejecuta en Mac.


FIGURA 4.16 :Configuración del trabajo del temporizador de estilo libre

Ahora guarde su configuración. Puede esperar a que se ejecute el trabajo cada hora para que se ejecute automáticamente. O bien, puede seleccionar "Construir ahora" en el menú de navegación izquierdo para que se ejecute inmediatamente. La Figura 4.17 muestra el historial de compilación después de varias ejecuciones.

Hay un icono verde junto a cada ejecución, ya que la compilación se realizó correctamente. Será amarillo si la compilación es inestable o rojo si falló. Al hacer clic en ese icono, accederás a la salida de consola de tu compilación. En una Mac, muestra lo siguiente:

Started by user admin
Running as SYSTEM
Building in workspace /var/jenkins_home/workspace/freestyle-timer
[freestyle-timer] $ /bin/sh -xe /tmp/jenkins14515196753987574989.sh
+ echo hello
hello
Finished: SUCCESS

FIGURA 4.17 :Historial de compilación de Jenkins

CONSEJO:  Quizás hayas notado que las horas están en Tiempo Universal Coordinado (UTC). Puedes ir a tu perfil de usuario para cambiarlas. O puedes configurarlas por defecto pasando un parámetro a Docker.

docker run --name jenkins -p 8080:8080 \
-e JAVA_OPTS=-Duser.timezone=America/New_York jenkins/jenkins
Creación de un trabajo Maven Freestyle
Antes de crear tu primer trabajo de Maven, debes configurar Maven para que se ejecute en Jenkins. Para ello, sigue estos pasos:

Haga clic en Administrar Jenkins en la navegación izquierda.
Seleccione Herramientas.
Haga clic en Agregar Maven en la sección Instalaciones de Maven.
Escriba un nombre como Maven 3.9 .
Deje las opciones predeterminadas, que descargarán la última versión disponible de Maven 3.9 de Internet la primera vez que lo compile. La Figura 4.18 muestra la configuración.
Haga clic en Guardar.
Ahora que Maven está configurado, puedes crear un nuevo trabajo de estilo libre. El siguiente paso es extraer el código de GitHub. Jenkins cuenta con una sección de Gestión de Código Fuente que ofrece un botón de opción para Git. Introduce la URL del repositorio del código que deseas. Por ejemplo, este capítulo usa https://github.com/realworldjava/Ch04-CICD.

Dado que este repositorio está disponible en internet, Jenkins aceptará la URL. Si fuera un repositorio privado o hubieras escrito mal la URL, recibirías un mensaje como este:

Failed to connect to repository : Command "git ls-remote -h –
https://github.com/realworldjava/Ch04-CICD HEAD" returned status code 128:

FIGURA 4.18 :Configuración de la herramienta Maven

Los repositorios en la empresa requerirán autenticación.

CONFIGURACIÓN DE CREDENCIALES EN JENKINS
En la empresa, su repositorio siempre requerirá credenciales. La instancia de Jenkins usará un token asociado a una cuenta de servicio (es decir, una cuenta no humana) para que quede claro que la actividad se originó en un sistema automatizado. En este libro, le mostraremos cómo usar un token de acceso personal de GitHub con su cuenta.

GitHub podría recomendarte usar tokens de granularidad fina. Puedes ver si su funcionalidad ha cambiado. Usamos tokens clásicos porque, al momento de escribir esto, solo el propietario del repositorio puede crear tokens de granularidad fina y no siempre eres el propietario de los repositorios que usas.

Para generar un token, siga estos pasos:

En GitHub, haz clic en tu imagen en la parte superior derecha.
Haga clic en Configuración.
En la navegación de la izquierda, seleccione Configuración del desarrollador.
Haga clic en Tokens de acceso personal en la navegación izquierda.
Haga clic en Tokens (clásico) en la navegación izquierda.
Haga clic en Generar nuevo token en la parte superior derecha y elija clásico nuevamente.
Escribe un nombre para tu token para recordar su propósito. Por ejemplo, Jenkins.
Seleccione el número de días de vencimiento. Muchas empresas tienen reglas sobre cuánto tiempo puede existir un token antes de su ciclo.
Generar el token.
Ahora que tienes un token, puedes configurarlo como credencial en Jenkins:

Haga clic en Administrar Jenkins en la navegación izquierda.
Seleccione Credenciales.
Haga clic en (global) para que la credencial esté disponible para todo Jenkins.
Haga clic en Agregar credenciales.
Ingrese su ID de GitHub como usuario.
Introduzca el token como contraseña.
Para el Id elija un nombre descriptivo como GitHub.
Haga clic en Crear.
Vaya a su trabajo Freestyle y elija la credencial que ingresó en el menú desplegable de credenciales debajo de la URL del repositorio.
Además de especificar el repositorio, debes especificar la rama. El campo especificador de rama tiene como valor predeterminado */master, que es el nombre que las versiones anteriores de Git usaban para la rama predeterminada antes de cambiarlo a main. Cámbialo a */maino al nombre de tu rama principal.

El siguiente paso es indicarle al trabajo de estilo libre que ejecute Maven. Para ello, cree un paso de compilación del tipo "Invocar objetivos de nivel superior de Maven". Seleccione la versión de Maven que creó anteriormente en el menú desplegable y escriba clean verifylos objetivos. Este repositorio usa subcarpetas en lugar de tener el pom.xmlnombre del archivo en la raíz; haga clic en "Avanzado" y pulse Intro maven/with-dependency/pom.xmlpara el POM. La Figura 4.19 muestra la configuración de este trabajo.


FIGURA 4.19 :Configuración del trabajo de estilo libre de Maven

Creación de un trabajo de Gradle Freestyle
A diferencia de Maven, no necesitas configurar la herramienta Gradle para empezar. El ejecutable de Gradle ya está en el repositorio de tu proyecto Gradle.

Al igual que en Maven, se crea un trabajo de estilo libre y se configura la gestión del código fuente. Se usa la misma URL y rama que en el ejemplo de Maven. El siguiente paso es indicarle al trabajo de estilo libre que ejecute Gradle. Se crea un paso de compilación de tipo Invocar script de Gradle. Se selecciona Gradle Wrapper y se establece la ubicación del wrapper en gradle/groovy/with-dependency.

Luego, ingrese buildla tarea. Finalmente, haga clic en "Avanzado" e ingrese gradle/groovy/with-dependencyla tarea "Script de compilación raíz". La Figura 4.20 muestra la configuración de Gradle para esta tarea.


FIGURA 4.20 :Configuración del trabajo de estilo libre de Gradle

Creación de una canalización de Maven
El complemento Pipeline Maven Integration facilita la escritura de una canalización que utiliza Maven, así que instálelo antes de crear la canalización:

Haga clic en Administrar Jenkins en la navegación izquierda.
Haga clic en Complementos.
Haga clic en Complementos disponibles en la navegación izquierda.
Escriba Pipeline Maven en la barra de búsqueda para filtrar la lista de complementos disponibles.
Haga clic en la casilla de verificación a la izquierda del nombre de ese complemento.
Haga clic en Instalar.
Haga clic en la casilla de verificación a la izquierda de Reiniciar Jenkins cuando se complete la instalación y no haya trabajos en ejecución.
Esto hará que Jenkins se reinicie. Ahora que tienes el complemento, estás listo para crear una canalización. Selecciona "Canalización" en lugar de "Proyecto Freestyle" al crear el trabajo.

Los trabajos de pipeline permiten incluir el pipeline directamente en la configuración del trabajo u obtenerlo de un repositorio. Para la primera opción, seleccione "Script de Pipeline" en la etiqueta "Definición". Luego, en el área de texto debajo, pegue el pipeline como se muestra en la Figura 4.21 .


FIGURA 4.21 :Script de canalización de Maven

node {
   stage('Source Control') {
      git branch: 'main', url: 'https://github.com/realworldjava/Ch04-CICD'
   }
   stage('Build') {
      withMaven(maven: 'Maven 3.9') {
         sh "\$MVN_CMD -f maven/with-dependency clean verify"
      }
   }
}
Esta canalización con script consta de dos etapas: Source Controlla Buildprimera extrae la rama principal del repositorio y la segunda utiliza la funcionalidad de [nombre del withMavenentorno] para configurar un entorno Maven. En ese contexto, invoca el comando Maven en el shell del sistema operativo. Si se ejecuta en un equipo Windows, utilice [nombre del entorno] baten lugar de [nombre del shentorno].

Como alternativa, puede almacenar la propia canalización en el control de origen siguiendo estos pasos, como se muestra en la Figura 4.22 :

Seleccione el script de Pipeline de SCM en la etiqueta Definición.
Elija Git para el SCM.
Introduzca una URL de repositorio, por ejemplo, https://github.com/realworldjava/Ch04-CICD.
Cambie el especificador de rama a */main.
Cambiar la ruta del script a maven/using-jenkinsfile/Jenkinsfile.
ESCRIBIR CÓDIGO DE TUBERÍA
Al abrir cualquier trabajo de pipeline en Jenkins, encontrará un enlace a la sintaxis de pipeline en el panel de navegación izquierdo. Este enlace le lleva a un asistente para generar código tanto para pipelines con script como declarativos. Complete los valores de configuración y Jenkins le proporcionará el código correspondiente. Si bien esto no escribe el pipeline completo, es un excelente punto de partida.


FIGURA 4.22 :Tubería de Maven desde SCM

Creación de una canalización de Gradle
Para Gradle, utilizamos la sintaxis de pipeline declarativa. La configuración del trabajo es la misma que para Maven. El código en el área de texto es diferente, por supuesto, ya que utiliza la sintaxis de Gradle.

pipeline {
   agent any
 
   stages {
      stage('Source Control') {
         steps {
           git branch: 'main', 
              url: 'https://github.com/realworldjava/Ch04-CICD'
        }
     }
     stage('Build') {
        steps {
          sh "gradle/groovy/with-dependency/gradlew " 
             + "-p gradle/groovy/with-dependency build"
        }
      }
   }
}
Esta vez, rootse usa "is" pipelineen lugar de node". La pipelinepalabra clave indica que el código se puede ejecutar en cualquier agente. En este caso, solo tenemos un agente. También hay más niveles, por ejemplo, " stepslevel". La idea es la misma en todos los formatos de pipeline, y cualquiera de ellos es válido. Al igual que en el trabajo de estilo libre de Gradle, " gradlewfrom the repository" se usa para ejecutar la compilación.

Los pipelines TIP  tienen muchas funciones avanzadas, incluida la capacidad de ejecutar pasos en paralelo, controlar cuándo fallar la compilación o incluso agregar pausas.

Aprendiendo sobre los complementos comunes
Jenkins ofrece una amplia selección de complementos descargables. Algunos son específicos para la tarea en cuestión, como los complementos de AWS. Muchos son útiles independientemente de lo que estés desarrollando.

Jenkins cuenta con un índice de plugins https://plugins.jenkins.iocon más de 1900 plugins de la comunidad. La documentación de los distintos plugins varía considerablemente en cuanto a su contenido.

Buscar "Tema Oscuro" te dará un ejemplo de un plugin popular. La documentación ofrece información sobre cómo configurarlo y capturas de pantalla del aspecto de Jenkins con el plugin. También indica que el 19,2 % de los controladores lo utilizan. Si bien esto es una aproximación, ya que no se incluyen las instalaciones de empresas privadas, sugiere que muchas personas consideran el plugin útil. Algunos plugins útiles son los siguientes:

Océano azul: ofrece funciones que facilitan el uso de pipelines, incluida una interfaz de usuario tabular para ver los resultados y la duración de cada etapa.
Analizador de errores de compilación: destaca los motivos comunes que se configuran para errores de compilación para que sea más fácil ver la causa
Afirmación: Ofrece a los usuarios la posibilidad de indicar que están trabajando para solucionar un trabajo fallido.
Vista del panel: vistas personalizables que incluyen información de resumen
Javadoc: Agrega una opción para publicar Javadoc
Jira: incluye enlaces a Jira y opciones para generar notas de lanzamiento
Estrategia de autorización basada en roles: proporciona la capacidad de definir roles y derechos de Jenkins para los usuarios.
Comprensión de otras capacidades de Jenkins
A medida que trabaje con Jenkins, descubrirá que hay mucho por explorar. En esta sección, encontrará una breve descripción general de las funciones que Jenkins puede realizar.

Organización de trabajos
Al seleccionar "Nuevo elemento", no se limita a los trabajos. También puede crear una carpeta. Las carpetas en Jenkins funcionan igual que las de su computadora. Puede anidar carpetas dentro de otras para mantener sus trabajos organizados.

También puede crear vistas como una forma alternativa de visualizar sus trabajos. Haga clic en el signo más ( +) sobre su lista de trabajos para crear una nueva vista. Por defecto, está disponible una vista de lista configurable . Puede seleccionar manualmente los trabajos que se incluyen en una vista o proporcionar una expresión regular para especificar un patrón. El capítulo 10 , «Coincidencia de patrones con expresiones regulares», explicará cómo usar expresiones regulares en general. Una vista de lista también le permite controlar las columnas que aparecen. Las vistas también pueden navegar por las carpetas.

El complemento Dashboard View ofrece un tipo de vista mucho más potente. Permite seleccionar portlets para anclarlos en la parte superior, inferior, izquierda y derecha de la pantalla de Jenkins. Puedes tener tantos portlets como desees en cada área, lo que facilita el control del diseño. Los portlets incluyen numerosas estadísticas, como compilaciones, trabajos y pruebas. Incluso puedes configurar tu panel de control para que se vea a pantalla completa, ocultando la navegación integrada de Jenkins.

Notificar a los usuarios
¡Un trabajo fallido no se solucionará si nadie lo sabe! Por defecto, Jenkins proporciona notificaciones por correo electrónico sobre fallos de compilación. Puedes proporcionar una o más direcciones de correo electrónico y especificar si quieres recibir un correo electrónico por cada compilación fallida o solo por la primera. Además, puedes incluir a quien realizó la confirmación que falló la compilación.

La notificación por correo electrónico editable ofrece mucho más control. Puedes especificar campos para el correo electrónico, el asunto y la plantilla de contenido. También puedes adjuntar el archivo de registro de compilación. Una de las principales funciones de este plugin es que te proporciona un control preciso sobre cuándo se envían los correos electrónicos. Puedes elegir cualquier combinación de éxitos y fracasos, e incluso enviar notificaciones a diferentes personas para distintos casos.

Además de las notificaciones por correo electrónico, Jenkins admite muchos otros tipos de notificaciones mediante plugins. Por ejemplo, el plugin SMS puede enviar un mensaje de texto cuando se produce un fallo. El plugin Notify-Events es compatible con Skype, Telegram, llamadas de voz y más. Existen notificadores especializados para temas de Slack o Amazon SNS.

Si estos notificadores activos/push no satisfacen sus necesidades, puede usar un enfoque pasivo/pull. Jenkins admite RSS a través de los feeds /rssAll, /rssFailedy /rssLatest.

Sea cual sea el notificador que elijas, asegúrate de que llame la atención. Al fin y al cabo, arreglar una compilación es prioritario, y eso no ocurrirá a menos que alguien sepa que está dañada.

Cambios en la lectura
Cada trabajo de Jenkins tiene un enlace "Cambios" en el panel de navegación izquierdo. Este enlace te indica qué ha cambiado en el repositorio desde la última compilación. Aquí tienes un ejemplo:

#8 (May 7, 2024, 9:36:22 PM)
 
add jenkinsfile — jeanne / githubweb
Este mensaje indica que la compilación 8 de este trabajo se ejecutó el 7 de mayo. Incluye el comentario de la confirmación, el ID de usuario y un enlace a la confirmación de Git donde puede consultar los detalles. Esta función es útil cuando la compilación falla, ya que permite ver exactamente qué cambió.

ESCANEO CON SONAR
Jenkins es el centro de tu compilación de CI/CD, pero otras herramientas suelen integrarse con él. Las etapas de control de código fuente, compilación y pruebas unitarias se realizan completamente en Jenkins. En cambio, Jenkins realiza comprobaciones de calidad, que suelen utilizar SonarQube, como se describe a continuación. Se utilizan otras herramientas para comprobar las dependencias.

Analicemos SonarQube con más detalle. SonarQube es desarrollado por un proveedor llamado SonarSource. Existe una versión comercial y una versión gratuita de código abierto. Es una herramienta de análisis estático, lo que significa que SonarQube identifica problemas en el código sin ejecutarlo. Además, un análisis estático de SonarQube se convierte en un paso más en el trabajo de estilo libre.

SonarQube incluye numerosas reglas para prácticamente cualquier lenguaje de programación imaginable. ¡Incluso incluye herramientas para verificar XML y JSON (véase el apéndice )! Estas reglas detectan todo tipo de problemas, como errores comunes, problemas de rendimiento y problemas de seguridad.

SonarQube también permite configurar un control de calidad. Si las reglas de alta prioridad se aprueban o las pruebas fallan, el control de calidad fallará. También se pueden configurar condiciones sobre los porcentajes de cobertura de código y más. Si se revisan los informes de SonarQube generados durante las compilaciones de Jenkins, se observará una mejora sustancial en el código del proyecto.

SonarQube realiza análisis estáticos y no ejecuta el código. Sin embargo, sí procesa pruebas JUnit e informes de cobertura de código de la compilación de Jenkins, lo que permite a SonarQube generar un excelente informe que muestra la calidad y la cobertura del código.

SUGERENCIA  SonarLint es la versión IDE de Sonar, por lo que puede descubrir problemas incluso antes de enviar su código al control de versiones.

EXPLICANDO LAS PRÁCTICAS DE CI/CD
Jenkins es una herramienta CI/CD, por lo que debe conocer una serie de prácticas de CI/CD para utilizarla de manera efectiva.

Control de versiones: todos los miembros de su equipo deben comprometerse con el mismo repositorio y deben hacerlo periódicamente.
Compilación automatizada: La compilación debe ser completamente automatizada y reproducible. No basta con trabajar en la máquina de un solo desarrollador.
Activación: cada confirmación debe activar una compilación y ejecutar las pruebas automatizadas para descubrir fallas rápidamente.
Reparar compilaciones rotas es la máxima prioridad: las compilaciones rotas deben repararse antes de realizar más cambios.
Cambios incrementales: Realice cambios pequeños y comprométase con frecuencia.
Mantenga la compilación de CI funcionando rápidamente: La compilación debe ejecutarse lo más rápido posible. Pasos más lentos como Sonar pueden ejecutarse en una secuencia de comandos que no ocurre en cada confirmación. Por ejemplo, podría ejecutarse durante la noche.
Visibilidad: todos los miembros del equipo y todas las partes interesadas deben poder ver el estado de la compilación.
Pruebas automatizadas: las pruebas siempre deben aprobarse para garantizar que el código esté listo para su implementación.
Implementación automatizada: la implementación no puede requerir intervención manual.
REFERENCIAS ADICIONALES
Entrega continua: lanzamientos de software confiables mediante la automatización de la compilación, las pruebas y la implementación (Addison-Wesley, 2020)
https://maven.apache.org/guides/index.html

Documentación de Maven
https://maven.apache.org/download.cgi

Descargar Maven para usar fuera del IDE
https://maven.apache.org/ref/3.9.6/maven-model-builder/super-pom.html

Super POM de Maven
https:docs.gradle.org/current/userguide/userguide.html

Documentación de Gradle
https://docs.gradle.org/current/userguide/java_plugin.html

Complemento de Java para Gradle
https://gradle.org/install

Descargar Gradle para usarlo fuera del IDE
https://docs.docker.com/engine/install

Descargar Docker
https://www.jenkins.io/download

Descargar Jenkins
https://www.jenkins.io/doc/book/pipeline

Documentación de Jenkins Pipeline
https://plugins.jenkins.io

Complementos de Jenkins
https://www.sonarsource.com

SonarQube
RESUMEN
En este capítulo, aprendió sobre CI/CD. Los conceptos clave incluyen los siguientes:

Construyendo con un Mavenpom.xml
Construir con un Gradle build.gradleen Groovy
Construir con un Gradle build.gradle.ktsen Kotlin
Creación de trabajos de canalización y estilo libre de Jenkins
El propósito de SonarQube, una herramienta de análisis estático
Principios clave de CI/CD
