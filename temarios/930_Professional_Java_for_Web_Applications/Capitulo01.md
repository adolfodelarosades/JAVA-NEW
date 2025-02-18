# Capítulo 1: Introducción a la plataforma Java, Enterprise Edition

1. Cronología de las plataformas Java
2. Comprender la estructura básica de una aplicación web
3. Resumen

#### EN ESTE CAPÍTULO

* Cronología de las versiones de Java SE y Java EE
* Presentación de servlets, filters, listeners y JSP
* Comprender los archivos WAR y EAR y la jerarquía del cargador de clases

#### DESCARGAS DE CÓDIGOS DE WROX.COM PARA ESTE CAPÍTULO

No hay descargas de códigos para este capítulo.

#### NUEVAS DEPENDENCIAS DE MAVEN PARA ESTE CAPÍTULO

No hay dependencias de Maven para este capítulo.

## CRONOLOGÍA DE LAS PLATAFORMAS JAVA

El lenguaje Java y sus plataformas tienen una larga historia. Desde su invención a mediados de los años 90 hasta una sequía de evolución desde 2007 hasta casi 2012, Java ha pasado por muchos cambios y se ha encontrado con su cuota de controversia. En sus inicios, Java, conocido como **Java Development Kit** o **JDK**, era un lenguaje estrechamente acoplado a una plataforma compuesta por un pequeño conjunto de interfaces de programación de aplicaciones ( **API** ) esenciales. Sun Microsystems presentó las primeras versiones alfa y beta en 1995 y, aunque Java era extremadamente lento y primitivo para los estándares actuales, inició una revolución en el desarrollo de software.

### Al principio

La historia de Java se resume en la Figura 1-1, una cronología de las plataformas Java. En el momento de la publicación de este libro, el lenguaje Java y la plataforma Java SE siempre han evolucionado juntos: las nuevas versiones de cada una de ellas siempre se lanzan al mismo tiempo y están estrechamente relacionadas entre sí. La plataforma se denominó JDK hasta la versión 1.1 en 1997, pero en la versión 1.2 quedó claro que el JDK y la plataforma no eran sinónimos. A partir de la versión 1.2 a finales de 1998, la pila de tecnología Java se dividió en los siguientes componentes clave:

![image](https://github.com/user-attachments/assets/8a3e7f26-eed4-4d52-aa3b-1911ab7e7d7b)

**FIGURA 1-1**: Línea de tiempo que muestra la correlación de la evolución de la Java Platform, Standard Edition y Java Platform, Enterprise Edition. Los eventos en la parte superior de la línea de tiempo representan hitos de Java SE, mientras que los eventos en la parte inferior representan hitos de Java EE.

* ***Java*** es un lenguaje que incluye una sintaxis estricta y fuertemente tipada con la que ya deberías estar muy familiarizado.
* ***Java 2 Platform, Standard Edition***, también conocida como **J2SE**, hacía referencia a la plataforma e incluía las clases de los paquetes `java.lang` y `java.io`, entre otros. Era el elemento básico sobre el que se creaban las aplicaciones Java.
* Una ***Java Virtual Machine***, o **JVM**, es una máquina virtual de software que ejecuta código Java compilado. Debido a que el código Java compilado es simplemente código de bytes, la JVM es responsable de compilar ese código de bytes en código de máquina antes de ejecutarlo. (Esto a menudo se denomina *Just In Time Compiler* o *JIT Compiler* ). La JVM también se encarga de la gestión de la memoria para que el código de la aplicación no tenga que hacerlo.
* El ***Java Development Kit***, o **JDK**, fue y sigue siendo el software que utilizan los desarrolladores de Java para crear aplicaciones Java. Contiene un compilador de lenguaje Java, un generador de documentación, herramientas para trabajar con código nativo y (normalmente) el código fuente de Java para la plataforma, que permite depurar las clases de la plataforma.
* El ***Java Runtime Environment*** o **JRE** fue y sigue siendo el software que los usuarios finales descargan para ejecutar aplicaciones Java compiladas. Incluye una JVM, pero no contiene ninguna de las herramientas de desarrollo incluidas en el JDK. Sin embargo, el JDK sí contiene un JRE.

Históricamente, estos cinco componentes han sido especificaciones, no implementaciones. Cualquier empresa puede crear su propia implementación de esta pila de tecnología Java, y muchas empresas lo han hecho. Aunque Sun ofrecía una implementación estándar de **Java**, **J2SE**, **JVM**, **JDK** y **JRE**, **IBM**, **Oracle** y **Apple** también crearon implementaciones competitivas que ofrecían características diferentes.

La implementación de IBM nació de una necesidad: Sun no ofrecía binarios capaces de ejecutarse en sistemas operativos IBM, por lo que IBM creó los suyos propios. La situación era similar para el sistema operativo Mac OS de Apple, por lo que Apple también desarrolló su propia implementación. Aunque las implementaciones ofrecidas por estas empresas eran todas gratuitas, no lo eran en el sentido de libertad, por lo que no se consideraban software de código abierto. Por ello, la comunidad de código abierto formó rápidamente el proyecto **OpenJDK**, que proporcionaba una implementación de código abierto de la pila Java.

Aún más empresas crearon implementaciones menos populares, algunas de las cuales compilaban la aplicación en código de máquina para una arquitectura de destino con el fin de mejorar el rendimiento evitando la compilación JIT. Para la gran mayoría de usuarios y desarrolladores, la implementación de Sun Java era suficiente y preferida. Después de que Oracle comprara Sun, las implementaciones de Sun y Oracle se convirtieron en una sola.

En la Figura 1-1 no se muestra el desarrollo de otros lenguajes capaces de utilizar J2SE y ejecutarse en la JVM. A lo largo de los años, han aparecido docenas de lenguajes que pueden compilarse en código de bytes de Java (o código de máquina, en algunos casos) y ejecutarse en la JVM. Los más destacados son **Clojure** (un dialecto de Lisp), **Groovy**, **JRuby** (una implementación de Ruby basada en Java), **Jython** (una implementación de Python basada en Java), **Rhino** y **Scala**.

### El nacimiento de Enterprise Java

Esta breve lección de historia puede parecer innecesaria (como desarrollador de Java, probablemente ya haya oído la mayor parte de esto antes). Sin embargo, es importante incluir el contexto de la historia de la **Java Platform, Standard Edition**, porque está estrechamente entrelazada con el nacimiento y la evolución de la **Java Platform, Enterprise Edition**. Sun ya era consciente de la necesidad de herramientas más avanzadas para el desarrollo de aplicaciones, en particular en el ámbito de la creciente Internet y la popularidad de las aplicaciones web. En 1998, poco antes del lanzamiento de **J2SE 1.2**, Sun anunció que estaba trabajando en un producto llamado **Java Professional Edition**, o **JPE**. Ya se había comenzado a trabajar en una tecnología conocida como ***Servlets***, que son aplicaciones en miniatura capaces de responder a solicitudes HTTP. En 1997, **Java Servlets 1.0** se lanzó junto con **Java Web Server** con poca fanfarria porque carecía de muchas características que la comunidad Java quería.

Después de varias iteraciones internas de Servlets y JPE, Sun lanzó ** Java 2 Platform, Enterprise Edition** (o **J2EE**) versión 1.2 el 12 de diciembre de 1999. El número de versión correspondía con la versión actual de Java y J2SE en ese momento, y la especificación incluía:

* Servlets 2.2
* JDBC Extension API 2.0
* Java Naming and Directory Interface (JNDI) 1.0
* JavaServer Pages (JSP) 1.2
* Enterprise JavaBeans (EJB) 1.1
* Java Message Service (JMS) 1.0
* Java Transaction API (JTA) 1.0
* JavaMail API 1.1
* JavaBeans Activation Framework (JAF) 1.0.

Al igual que **J2SE**, **J2EE** era una mera especificación. Sun proporcionaba una implementación de referencia de los componentes de la especificación, pero las empresas también tenían libertad para crear los suyos propios. Se desarrollaron muchas implementaciones, y en el próximo capítulo aprenderá sobre algunas de ellas. Estas implementaciones incluían y aún incluyen soluciones comerciales y de código abierto. J2EE se convirtió rápidamente en un complemento exitoso de J2SE y, con el paso de los años, algunos componentes se consideraron tan indispensables que migraron de J2EE a J2SE.

### Java SE y Java EE evolucionan juntos

**J2EE 1.3** se lanzó en septiembre de 2001, poco más de un año después de Java y J2SE 1.3 y antes de Java/J2SE 1.4. La mayoría de sus componentes recibieron actualizaciones menores y se agregaron nuevas características. Los siguientes se unieron a la especificación J2EE y la gama de implementaciones se expandió y mejoró:

* Java API for XML Processing (JAXP) 1.1
* JavaServer Pages Standard Tag Library (JSTL) 1.0
* J2EE Connector Architecture 1.0
* Java Authentication and Authorization Service (JAAS) 1.0

En ese momento la tecnología estaba madurando considerablemente, pero todavía tenía mucho margen de mejora.

**J2EE 1.4** representó un gran salto en la evolución de la Java Platform, Enterprise Edition. Lanzada en noviembre de 2003 (aproximadamente un año antes que Java/J2SE 5.0 y dos años después de Java/J2SE 1.4), incluía **Servlet 2.4** y **JSP 2.0**. Fue en esta versión en la que se eliminaron las especificaciones de la API de extensión JDBC, JNDI y JAAS porque se habían considerado esenciales para Java y se trasladaron a Java/J2SE 1.4. Esta versión también representó el punto en el que los componentes J2EE se dividieron en varias categorías de nivel superior:

* **Web Services Technologies**: incluye JAXP 1.2 y los nuevos servicios web para J2EE 1.1, Java API para RPC basado en XML (JAX-RPC) 1.1 y Java API para registros XML (JAXR) 1.0
* **Web Application Technologies**: Se incluyen los componentes Servlet, JSP y JSTL 1.1, así como el nuevo Java Server Faces (JSF) 1.1
* **Enterprise Application Technologies**: incluidas EJB 2.1, Connector Architecture 1.5, JMS 1.1, JTA, JavaMail 1.3 y JAF
* **Management and Security Technologies**: Contrato de proveedor de servicios de autorización de Java para contenedores (JACC) 1.0, extensiones de administración de Java (JMX) 1.2, API de administración de Enterprise Edition 1.0 y API de implementación de Enterprise Edition 1.1 incluidos


### La era de los cambios de nombre

Entramos en la era de los cambios de nombre, que suelen ser una fuente de confusión para los desarrolladores de Java. Se destacan aquí para que comprendas completamente las convenciones de nombres utilizadas en este libro y cómo se relacionan con las convenciones de nombres anteriores con las que quizás ya estés familiarizado. **Java** y **J2SE 5.0** se lanzaron en septiembre de 2004 e incluyeron genéricos, anotaciones y enumeraciones, tres de los cambios de sintaxis de lenguaje más radicales en la historia de Java. Este número de versión se apartó de los patrones anteriores, y se volvió más confuso por el hecho de que las API de J2SE y la herramienta `java` de línea de comandos informaban que el número de versión era 1.5. Sun había tomado la decisión de eliminar el 1 del número de versión publicado y utilizar en su lugar la versión menor. Reconoció rápidamente que el "dot-oh" al final del número de versión era una fuente de confusión y rápidamente comenzó a referirse a él simplemente como la versión 5.

Casi al mismo tiempo, se tomó la decisión de retirar el nombre **Java 2 Platform, Standard Edition** en favor de **Java Platform, Standard Edition** y abreviar este nuevo nombre como **Java SE**. Los cambios se hicieron formales con **Java SE 6**, lanzado en diciembre de 2006, y hasta el día de hoy el nombre y la convención de la versión se han mantenido sin cambios. **Java SE 6** es internamente **1.6**, **Java SE 7** es internamente **1.7** y **Java SE 8** es internamente **1.8**.

Las mismas decisiones de cambio de nombre y número se aplicaron a J2EE, pero como J2EE 1.5 se iba a lanzar entre J2SE 5.0 y Java SE 6, los cambios se aplicaron una versión anterior. **Java Platform, Enterprise Edition 5**, o **Java EE 5**, se lanzó en mayo de 2006, aproximadamente 18 meses después de J2SE 5.0 y 7 meses antes de Java SE 6. Internamente, **Java EE 5** es **1.5**, **Java EE 6** es **1.6** y **Java EE 7** es **1.7**. Siempre que vea los términos **J2SE** o **Java SE**, son intercambiables, y el nombre preferido y aceptado hoy es **Java EE**. Del mismo modo, **J2EE** y **Java EE** son intercambiables, pero Java EE es el preferido hoy. El resto de este libro se refiere a ellos exclusivamente como **Java SE** y **Java EE**.

Java EE 5 creció e incluyó numerosos cambios y mejoras nuevamente, y hoy en día sigue siendo una de las versiones de Java EE más ampliamente implementadas. Incluyó los siguientes cambios y adiciones:

* JAXP y JMX se trasladaron a J2SE 5.0 y no se incluyeron en Java EE 5.
* Se agregaron a la tecnología de servicios web la API de Java para servicios web basados ​​en XML (JAX-WS) 2.0, la arquitectura Java para enlace XML (JAXB) 2.0, los metadatos de servicios web para la plataforma Java 2.0, la API de SOAP con archivos adjuntos para Java (SAAJ) 1.2 y la API de transmisión para XML (StAX) 1.0.
* Se agregaron Java Persistence API (JPA) 1.0 y Common Annotations API 1.0 a la Tecnología de Aplicaciones Empresariales.


### La sequía de Java SE y EE

El lanzamiento de **Java SE 6 en diciembre de 2006** marcó el comienzo de una sequía de lanzamientos de Java SE que *duró aproximadamente 5 años*. Esta vez fue un período de frustración e incluso enojo para muchos en la comunidad Java. Sun continuó prometiendo nuevas características del lenguaje y API para Java SE 7, pero el cronograma continuó demorándose año tras año sin un final a la vista. Mientras tanto, otras tecnologías, como el lenguaje C# y la plataforma .NET, alcanzaron y superaron a Java en características del lenguaje y API de la plataforma, lo que provocó que algunos especularan sobre si Java había llegado al final de su vida útil. Para empeorar las cosas, Java EE entró en su propio período de sequía y para 2009, más de 3 años después, Java SE 7 ya había sido lanzado. Habían pasado muchos años desde que se lanzó Java EE 5. Sin embargo, no todo estaba perdido. El desarrollo de **Java EE 6** se reanudó a principios de 2009 y se lanzó en diciembre de 2009, 3 años y 7 meses después de Java EE 5 y 3 años casi al día después de Java SE 6.

En ese momento, Java Enterprise Edition ya se había convertido en algo enorme:

* SAAJ, StAX y JAF se trasladaron a Java SE 6.
* Se agregaron las especificaciones de la API de Java para servicios web RESTful (JAX-RS) 1.1 y de las API de Java para mensajería XML (JAXM) 1.3 a Tecnologías de servicios web.
* El lenguaje de expresión unificado Java (JUEL o simplemente EL) 2.0 se agregó a Tecnologías de aplicaciones web.
* Las tecnologías de administración y seguridad vieron la incorporación de la Interfaz de proveedor de servicios de autenticación de Java para contenedores (JASPIC) 1.0.
* Enterprise Application Technologies logró el aumento más espectacular en funciones, incluidos Contexts and Dependency Injection para Java (CDI) 1.0, Dependency Injection para Java 1.0, Bean Validation 1.0, Managed Beans 1.0 e Interceptors 1.1, además de actualizaciones de todos sus demás componentes.

Java EE 6 también representó un punto de inflexión importante en la arquitectura de Java EE en dos frentes:

* Esta versión introdujo una configuración de aplicaciones programática y basada en anotaciones para complementar la configuración XML tradicional utilizada durante más de una década.
* Esta versión marcó la introducción del perfil web Java EE.

Para tener en cuenta el hecho de que Java EE se había vuelto tan grande (y el mantenimiento y la actualización de las implementaciones certificadas se estaba volviendo cada vez más difícil), el programa de certificación Web Profile ofreció la oportunidad de certificar implementaciones de Java EE que incluían solo un subconjunto de toda la plataforma Java EE. Este subconjunto incluía las características consideradas más críticas para una gran cantidad de aplicaciones y excluía las especificaciones que solo se utilizan en una pequeña minoría de aplicaciones. A partir de Java EE 6:

* Ninguno de los componentes de Servicios Web o Administración y Seguridad son parte del Perfil Web Java EE.
* El perfil web incluye todo lo relacionado con las tecnologías de aplicaciones web y todo lo relacionado con las tecnologías de aplicaciones empresariales, excepto la arquitectura del conector Java EE, JMS y JavaMail.

Fue durante la sequía de cinco años de Java que Oracle Corporation compró Sun Microsystems en enero de 2010. Esto, unido a la sequía de Java SE, trajo consigo toda una serie de nuevas preocupaciones para la comunidad Java. Oracle nunca fue conocida por su agilidad o su voluntad de cooperar con proyectos de código abierto, y mucha gente temía que Oracle hubiera comprado Sun para acabar con Java. Sin embargo, resultó que no fue así.

Desde el principio, Oracle comenzó a reorganizar el equipo de Java, creando canales de comunicación con la comunidad de código abierto y publicando planes para futuras versiones de Java SE y Java EE que eran más realistas que todo lo que Sun había prometido. Se comenzó a trabajar de nuevo en **Java SE 7**, que se publicó el 1 de junio. El calendario (de Oracle) se fijó en junio de 2011, casi 5 años después de Java SE 6. Una segunda sequía de Java EE terminó con el lanzamiento de **Java EE 7** en junio de 2013, 3 años y 7 meses después de Java EE 6. Oracle ahora dice que está en camino de comenzar a lanzar nuevas versiones de ambas plataformas cada 2 años, en años alternos. Queda por ver si eso sucederá.

### Comprender las características más recientes de la plataforma

Java SE 7 y 8 y Java EE 7 han introducido importantes cambios en el lenguaje y las API que lo respaldan, lo que ha dado lugar a un rejuvenecimiento de las tecnologías Java. En este libro se utilizan estas nuevas funciones, por lo que en esta sección se ofrece una descripción general de ellas.

#### Java SE 7

En un principio, Java SE 7 tenía una lista de características muy ambiciosa, pero después de adquirir Sun, Oracle admitió rápidamente que alcanzar los objetivos de Java SE 7 llevaría muchos, muchos años. Cada característica era la más importante para algún grupo de usuarios, por lo que se tomó la decisión de posponer algunas de ellas para versiones futuras. La alternativa era retrasar el lanzamiento de Java SE 7 hasta 2015 o más tarde, una opción que no era aceptable.

Java SE 7 incluía compatibilidad con lenguajes dinámicos, así como punteros comprimidos de 64 bits (para mejorar el rendimiento en JVM de 64 bits). También agregó varias características del lenguaje que hicieron que el desarrollo de aplicaciones Java fuera más productivo. Quizás uno de los cambios más útiles fue ***diamonds***, un atajo para la instanciación genérica. Antes de Java 7, tanto la declaración de variable como la asignación de variable para tipos genéricos tenían que incluir los argumentos de tipo genérico. Por ejemplo, aquí hay una declaración y asignación para una variable muy compleja **`java.util.Map`**:

```java
Map<String, Map<String, Map<Integer, List<MyBean>>>> map =
            new Hashtable<String, Map<String, Map<Integer, List<MyBean>>>>();
```
  
Por supuesto, esta declaración contiene mucha información redundante. Asignar cualquier cosa que no sea **`Map<String, Map<String, Map<Integer, List<MyBean>>>>`** a esta variable sería ilegal, entonces, ¿por qué debería especificar todos esos argumentos de tipo nuevamente? Al usar los diamantes de Java 7, esta declaración y asignación se vuelven mucho más simples. El compilador infiere los argumentos de tipo para la instancia **`java.util.Hashtable`**.

```java
Map<String, Map<String, Map<Integer, List<MyBean>>>> map = new Hashtable<>();
```

Otra queja común sobre Java anterior a Java 7 es la gestión de recursos cerrables en relación con los bloques **`try-catch-finally`**. En particular, considere este desagradable fragmento de código JDBC:

```java
    Connection connection = null;
    PreparedStatement statement = null;
    ResultSet resultSet = null;
    try
    {
        connection = dataSource.getConnection();
        statement = connection.prepareStatement(...);
        // set up statement
        resultSet = statement.executeQuery();
        // do something with result set
    }
    catch(SQLException e)
    {
        // do something with exception
    }
    finally
    {
        if(resultSet != null) {
            try {
                resultSet.close();
            } catch(SQLException ignore) { }
        }
 
        if(statement != null) {
            try {
                statement.close();
            } catch(SQLException ignore) { }
        }
 
        if(connection != null && !connection.isClosed()) {
            try {
                connection.close();
            } catch(SQLException ignore) { }
        }
    }
```
    
La función ***try-with-resources*** de Java 7 ha simplificado drásticamente esta tarea. Cualquier clase que implemente **`java.lang.AutoCloseable`** es elegible para usarse en una construcción try-with-resources. Las interfaces JDBC **`Connection`**, **`PreparedStatement`** y **`ResultSet`** extienden esta interfaz. Cuando se utiliza try-with-resources como se muestra en el siguiente ejemplo, los recursos que se declaran dentro de los paréntesis de la palabra clave **`try`** se cierran automáticamente en un bloque implícito **`finally`**. Cualquier excepción lanzada durante esta limpieza se agrega a las excepciones suprimidas de una excepción existente o, si no existe ninguna excepción, se lanza después de que se hayan cerrado todos los recursos.

```java
    try(Connection connection = dataSource.getConnection();
        PreparedStatement statement = connection.prepareStatement(...))
    {
        // set up statement
        try(ResultSet resultSet = statement.executeQuery())
        {
            // do something with result set
        }
    }
    catch(SQLException e)
    {
        // do something with exception
    }
```

Otra mejora que se hizo en try-catch-finally es la incorporación de ***multi-catch***. A partir de Java 7, ahora es posible capturar varias excepciones dentro de un solo bloque **`catch`**, separando los tipos de excepción con una sola barra vertical. Por ejemplo:


```java
    try
    {
        // do something
    }
    catch(MyException | YourException e)
    {
        // handle these exceptions the same way
    }
```

Una advertencia que se debe tener en cuenta es que no se pueden capturar dos o más excepciones de forma múltiple de modo que una herede de la otra. Por ejemplo, lo siguiente está prohibido porque **`FileNotFoundExceptionse`** extiende **`IOException`**:


```java
    try {
        // do something
    } catch(IOException | FileNotFoundException e) {
        // handle these exceptions the same way
    }
```

Por supuesto, esto puede considerarse fácilmente una cuestión de sentido común. En este caso, simplemente capturarías **`IOException`**, lo que detectaría ambos tipos de excepciones.

Algunas otras características diversas del lenguaje Java 7 incluyen literales binarios para bytes y números enteros (puede escribir el literal **`1928`** como **`0b11110001000`**) y guiones bajos en literales numéricos (puede escribir los mismos literales como **`1_928`** y **`0b111_1000_1000`**, si lo desea). Además, puede usar **`Strings`** como argumento en un **`switch`** .

#### Java EE 7

**Java EE 7, publicado el 12 de junio de 2013**, contiene una serie de cambios y nuevas funciones. Muchas de estas nuevas funciones se tratarán a lo largo de este libro, por lo que no se detallarán aquí. En resumen, los cambios de Java EE 7 son los siguientes:

* JAXB se agregó a Java SE 7 y ya no está incluido en Java EE.
* Se agregaron aplicaciones por lotes para la plataforma Java 1.0 y utilidades de concurrencia para Java EE 1.0 a Tecnologías de aplicaciones empresariales.
* Web Application Technologies adoptó la API de Java para WebSockets 1.0 (que conocerá en el Capítulo 10) y la API de Java para procesamiento JSON 1.0.
* El lenguaje de expresión unificado de Java se ha ampliado significativamente para incluir expresiones lambda y un análogo de la API de flujo de colecciones de Java SE 8. (Obtendrá más información sobre esto en el Capítulo 6).
* El perfil web se amplió ligeramente para incluir especificaciones que probablemente sean más necesarias en aplicaciones web comunes: JAX-RS, API de Java para WebSockets y API de Java para procesamiento JSON.

#### Java SE 8

Las nuevas características de Java SE 8 pueden resultar muy útiles a medida que trabaja con los ejemplos de este libro. Quizás la más visible sea la incorporación de expresiones lambda (conocidas extraoficialmente como ***closures-cierres*** ). Las expresiones lambda son funciones anónimas que se definen y posiblemente se invocan sin ser asignadas, un nombre de tipo o vinculado a un identificador. Las expresiones Lambda son particularmente útiles para implementar de forma anónima las interfaces de un solo método que son tan comunes en las aplicaciones Java. Por ejemplo, una **`Thread`** que se instanciaba previamente con un anónimo **`Runnable`** como este:

    
```java
    public String doSomethingInThread(String someArgument)
    {
        ...
        Thread thread = new Thread(new Runnable() {
            @Override
            public void run()
            {
                // do something
            }
        });
        ...
    }
```

Ahora se puede simplificar con una expresión lambda:

    
```java
    public String doSomethingInThread(String someArgument)
    {
        ...
        Thread thread = new Thread(() -> {
            // do something
        });
        ...
    }
```

Las expresiones lambda pueden tener argumentos, tipos de retorno y genéricos. Y, cuando lo desee, puede utilizar una ***method reference - referencia de método*** en lugar de una expresión lambda para pasar una referencia a un método que coincida con la interfaz. El siguiente código también es equivalente a las dos instancias anteriores de **`Thread`**. También puede asignar referencias de método y expresiones lambda a variables.

    
```java
    public String doSomethingInThread(String someArgument)
    {
        ...
        Thread thread = new Thread(this::doSomething);
        ...
    }
 
    public void doSomething()
    {
        // do something
    }
```

Una de las mayores quejas entre los usuarios de Java desde sus inicios es la falta de una API de fecha y hora decente. **`java.util.Date`** siempre ha estado plagada de problemas, y la adición de **`java.util.Calendar`** solo empeoró muchos de ellos. Java SE 8 finalmente aborda eso con **JSR 310**, una nueva API de fecha y hora. Esta API se basa en gran medida en **Joda Time**, pero con mejoras en la arquitectura subyacente para solucionar los problemas que señaló el inventor de Joda Time. Esta API es una adición revolucionaria a las API de la plataforma Java SE y finalmente trae una API de fecha y hora poderosa y bien diseñada a Java.

#### Una evolución continua

Como puede ver, las plataformas Java SE y EE nacieron juntas y han evolucionado de la mano durante casi dos décadas. Es probable que sigan evolucionando juntas durante muchos años o décadas más. Debería estar bastante familiarizado con Java SE, pero es posible que no sepa absolutamente nada sobre el uso de Java EE. También es posible que esté familiarizado con versiones anteriores de Java EE, pero desee aprender más sobre las nuevas características de Java EE.

La Parte I de este libro le enseña las características más importantes de Java EE, incluidas:

* Servidores de aplicaciones y contenedores web (Capítulo 2)
* Servlets (Capítulo 3)
* JSP (Capítulos 4, 6, 7 y 8)
* Sesiones HTTP (Capítulo 5)
* Filtros (Capítulo 9)
* WebSockets (Capítulo 10).

### COMPRENDER LA ESTRUCTURA BÁSICA DE LA APLICACIÓN WEB

Para crear una aplicación web Java EE se necesitan muchos componentes. En primer lugar, tienes el código y las bibliotecas de terceros de las que depende. Luego tienes el descriptor de implementación(deployment descriptor), que incluye instrucciones para deploying e iniciar tu aplicación. También tienes **`ClassLoadere`**s, responsables de aislar tu aplicación de otras aplicaciones web en el mismo servidor. Por último, debes empaquetar tu aplicación de alguna manera y para eso tienes los archivos **WAR** y **EAR**.

### Servlets, Filters, Listeners y JSPs

Los **servlets** son un componente clave de cualquier aplicación web Java EE. Los servlets, sobre los que aprenderá en el Capítulo 3, ***son clases Java responsables de aceptar y responder a las solicitudes HTTP***. Casi todas las requests a su aplicación pasan por un servlet de algún tipo, excepto aquellas requests que son erróneas o que son interceptadas por algún otro componente. Un **filter** ***es uno de esos componentes que puede interceptar las solicitudes a sus servlets***. Puede utilizar filtros para satisfacer una variedad de necesidades, desde el formato de datos hasta la compresión de respuestas, pasando por la autenticación y la autorización. Explorará los diversos usos de los filtros en el Capítulo 9.

Al igual que muchos otros tipos de aplicaciones, las aplicaciones web tienen un ciclo de vida. Existen procesos de startup y shutdown, y durante estas etapas ocurren muchas cosas diferentes. Las aplicaciones web Java EE admiten varios tipos de **listeners**, sobre los que aprenderá en las Partes I y II. Estos listeners pueden notificar a su código sobre varios eventos, como el inicio de la aplicación, el cierre de la aplicación, la creación de una sesión HTTP y la destrucción de la sesión.

Quizás una de las herramientas Java EE más potentes a su disposición es la tecnología **JavaServer Pages** o **JSP**. Las JSP le proporcionan los medios para crear fácilmente interfaces gráficas de usuario dinámicas basadas en HTML para sus aplicaciones web sin tener que escribir manualmente **`String`** en HTML a un **`OutputStream`** o **`PrintWriter`**. El tema de las JSP abarca muchas facetas diferentes, incluidas **JavaServer Pages Standard Tag Library**, **Java Unified Expression Language**, **custom tags**, **internationalization** y **localization**. Dedicará mucho tiempo a estas funciones en el capítulo 4 y en los capítulos 6 a 9.

Por supuesto, Java EE tiene muchas más funciones que Servlets, filters, listeners, y JSPs. En este libro, cubrirá muchas de ellas, pero no todas.

### Estructura de directorios y archivos WAR

Las aplicaciones web estándar de Java EE se implementan como **archivos WAR** o “exploded” (unarchived) Web Application Directories. Ya debería estar familiarizado con los **archivos JAR** o **Java Archive**. Recuerde que ***un archivo JAR es simplemente un archivo con formato ZIP con una estructura de directorio estándar reconocida por las JVM***. No hay nada propietario sobre el formato de archivo JAR, y cualquier aplicación de archivo ZIP puede crear y leer archivos JAR. Un archivo **WAR** o **Web Application Archive** es el archivo de almacenamiento equivalente para las aplicaciones web Java EE.

Todos los servidores de aplicaciones web Java EE admiten archivos de aplicación WAR. La mayoría también admiten directorios de aplicaciones expandidos. Ya sea que estén archivados o expandidos, la convención de estructura de directorios, como se muestra en la Figura 1-2, es la misma. Al igual que un archivo JAR, esta estructura contiene clases y otros recursos de la aplicación, pero esas clases no se almacenan en relación con la raíz de la aplicación como en un archivo JAR. En cambio, ***los archivos de clase se encuentran en `/WEB-INF/classes`***. El directorio **`WEB-INF`** almacena archivos informativos e instructivos que los servidores de aplicaciones web Java EE utilizan para determinar cómo implementar y ejecutar la aplicación. Su directorio **`classes`** actúa como la raíz del paquete. Todos los archivos de clase de aplicación compilados y otros recursos se encuentran dentro de este directorio.

![image](https://github.com/user-attachments/assets/f0287478-ddfe-4c6b-9df0-ad03bd6a6b33)

**FIGURA 1-2**

A diferencia de los archivos JAR estándar, los archivos WAR pueden contener archivos JAR agrupados, que se encuentran en **`/WEB-INF/lib`**. Todas las clases de los archivos JAR de este directorio también están disponibles para la aplicación en la ruta de clases de la aplicación. Los directorios **`/WEB-INF/tags`** y **`/WEB-INF/tld`** están reservados para almacenar JSP tag files y tag library descriptors, respectivamente. Explorará el tema de los tag files y tag libraries en profundidad en el Capítulo 8. El  directorio **`i18n`** no es en realidad parte de las especificaciones de Java EE, pero es una convención que la mayoría de los desarrolladores de aplicaciones siguen para almacenar archivos de internacionalización (**i18n**) y localización (**L10n**).

Probablemente también haya notado la presencia de dos directorios **`META-INF`** diferentes. Esto puede ser una fuente de confusión para algunos desarrolladores, pero si recuerda las reglas de ruta de clases simples, puede diferenciarlos fácilmente. Al igual que los directorios **`META-INF`** de archivos JAR, el directorio de nivel raíz **`/META-INF`** contiene el archivo de manifiesto de la aplicación. También puede contener recursos para contenedores web o servidores de aplicaciones específicos. Por ejemplo, Apache Tomcat (sobre el que aprenderá en el Capítulo 2) busca y usa un archivo **`context.xml`** en este directorio para ayudar a personalizar cómo se implementa la aplicación en Tomcat. Ninguno de estos archivos son parte de la especificación Java EE, y los archivos compatibles pueden variar de un servidor de aplicaciones o contenedor web a otro.

A diferencia de los archivos JAR, el directorio **`/META-INF`** de nivel raíz no está en la ruta de clases de la aplicación. No puede utilizar **`ClassLoader`** para obtener recursos en este directorio. **`/WEB-INF/classes/META-INF`**, sin embargo, está en la ruta de clases. Puede colocar cualquier recurso de aplicación que desee en este directorio y se puede acceder a ellos a través de **`ClassLoader`**. Algunos componentes de Java EE especifican archivos que pertenecen a este directorio. Por ejemplo, la API de persistencia de Java (que aprenderá en la Parte III de este libro) especifica dos archivos, uno con nombre **`persistence.xml`** y otro **`orm.xml`**, que se encuentran en **`/WEB-INF/classes/META-INF`**.

La mayoría de los archivos contenidos en un archivo WAR o en un directorio de aplicación web expandido son recursos a los que se puede acceder directamente a través de una URL. Por ejemplo, el archivo **`/bar.html`** relativo a la raíz de una aplicación implementada en http://example.org/foo es accesible desde http://example.org/foo/bar.html . En ausencia de cualquier filtro o regla de seguridad que indique lo contrario, esto es válido para todos los recursos de su aplicación, excepto aquellos recursos que se encuentran en los directorios **`/WEB-INF`** y **`/META-INF`**. Los archivos de estos directorios son recursos protegidos a los que no se puede acceder a través de una URL.

### El Deployment Descriptor - Descriptor de Implementación

El Deployment Descriptor son los metadatos que describen la aplicación web y brindan instrucciones al servidor de aplicaciones web Java EE para implementar y ejecutar la aplicación web. Tradicionalmente, todos estos metadatos provenían del archivo descriptor de implementación, **`/WEB-INF/web.xml`**. Este archivo contiene definiciones para Servlets, listeners y filters, y opciones de configuración para sesiones HTTP, JSP y la aplicación en general. **Servlet 3.0** en Java EE 6 agregó la capacidad de configurar aplicaciones web mediante anotaciones y una API de configuración de Java. También agregó la noción de fragmentos web: los archivos JAR dentro de su aplicación pueden contener Servlets, filters, y listeners configurados en **`/META-INF/web-fragment.xml`** descriptores de implementación dentro de los archivos JAR necesarios. Los fragmentos web también pueden usar anotaciones y la API de configuración de Java.

Este cambio en la implementación de aplicaciones web en Java EE 6 agregó una complejidad significativa a la tarea de organizar este proceso. Para facilitar esta complejidad, puede configurar el orden de los fragmentos web para que se analicen y activen en una secuencia específica. Esto sucede de dos maneras:

* El archivo de cada fragmento web **`web-fragment.xml`** puede contener un elemento **`<ordering>`** que utiliza etiquetas **`<before>`** y anidadas **`<after>`** para controlar si el fragmento web se activa antes o después de otros fragmentos web. Estas etiquetas contienen elementos **`<name>`** anidados para especificar el nombre de otro fragmento en relación con el cual se debe ordenar el fragmento actual **`<before>`** y, **`<after>`** alternativamente, pueden contener elementos **`<others>`** anidados para indicar que el fragmento debe activarse antes o después de cualquier otro fragmento que no tenga un nombre específico.

* Si no ha creado un fragmento web en particular y no tiene control sobre su contenido, puede controlar el orden de los fragmentos web dentro del descriptor de implementación de su aplicación. El elemento **`<absolute-ordering>`** en **`/WEB-INF/web.xml`**, junto con sus elementos anidados **`<name>`** y **`<others>`**, configura un orden absoluto para los fragmentos web agrupados que anula cualquier instrucción de orden que venga con los fragmentos web.

De forma predeterminada, los entornos Servlet 3.0 y posteriores escanean las aplicaciones web y los fragmentos web en busca de anotaciones de aplicaciones web Java EE para configurar Servlets, listeners, filters, y más. Puede deshabilitar este escaneo y deshabilitar la configuración de anotaciones agregando el atributo **`metadata-complete="true"`** a la raíz **`<web-app>`** o a los elementos **`<web-fragment>`** según sea necesario. También puede deshabilitar todos los fragmentos web de su aplicación agregando **`<absolute-ordering />`** (sin ningún elemento anidado) a su descriptor de implementación.

En la Parte I del libro, aprenderá más sobre el descriptor de implementación de aplicaciones web y la configuración de anotaciones. En la Parte II, explorará el container initializer - inicializador de contenedores y la programmatic configuration - configuración programática con la API de Java, y verá cómo puede hacer que el arranque de Spring Framework sea más fácil y comprobable.

### Class Loader Architecture - Arquitectura del cargador de clases

Al trabajar con aplicaciones web Java EE, es fundamental comprender la arquitectura **`ClassLoader`**, ya que difiere de la arquitectura a la que está acostumbrado en las aplicaciones estándar de Java SE. En una aplicación típica, las clases **`java.*`** que vienen con la plataforma Java SE se cargan en una raíz especial **`ClassLoader`** que no se puede anular. Esta es una medida de seguridad que evita que el código malicioso, por ejemplo, reemplace la clase **`String`** o redefina **`Boolean.TRUE`** y **`Boolean.FALSE`**.

Después de esto **`ClassLoader`** viene la extensión **`ClassLoader`**, que carga clases desde los JAR de extensiones en el directorio de instalación de JRE. Finalmente, la aplicación **`ClassLoader`** carga todas las demás clases en la aplicación. Esto forma una jerarquía de **`ClassLoader`**s, con la raíz sirviendo como el ancestro más antiguo para todos los **`ClassLoader`**s. Cuando se le pide a un nivel inferior **`ClassLoader`** que cargue una clase, siempre delega a su padre **`ClassLoader`** primero. Esto continúa hasta que **`ClassLoader`** se verifica la raíz. Con la excepción de la raíz **`ClassLoader`**, a **`ClassLoader`** carga una clase desde su colección de JAR y directorios solo si su padre **`ClassLoader`** primero no puede encontrar la clase.

Este método de carga de clases se denomina modelo de delegación de cargador de clases *parent-first padre-primero* y, aunque funciona muy bien para muchos tipos de aplicaciones, no es ideal para la mayoría de las aplicaciones web Java EE. Un servidor que ejecuta aplicaciones web Java EE suele ser extraordinariamente complejo y varios proveedores podrían proporcionar su implementación. El servidor podría utilizar algunas de las mismas bibliotecas de terceros que utiliza su aplicación, pero es posible que sean de versiones conflictivas. Además, diferentes aplicaciones web también podrían proporcionar versiones conflictivas de las mismas bibliotecas de terceros, lo que genera aún más problemas. Para resolver estos problemas, necesita un *parent-last class loader delegation model*.

En los servidores de aplicaciones web Java EE, a cada aplicación web se le asigna su propia clase aislada **`ClassLoader`** que hereda del servidor común **`ClassLoader`**. Al aislar las aplicaciones entre sí, no pueden acceder a las clases de las demás. Esto no solo elimina el riesgo de clases conflictivas, sino que también sirve como medida de seguridad para evitar que las aplicaciones web interfieran con otras aplicaciones web o las dañen. Además, una aplicación web **`ClassLoader`**(normalmente) le pide a su padre que cargue una clase solo si no puede cargar la clase en sí primero. De esta manera, la carga de la clase se delega al padre en último lugar en lugar de al padre primero, y las clases y bibliotecas de la aplicación web se prefieren a las que proporciona el servidor. Para mantener el estado protegido de las clases Java SE agrupadas, las aplicaciones web **`ClassLoader`** aún comprueban la raíz **`ClassLoader`** antes de intentar cargar cualquier clase. Aunque este modelo de delegación es más preferible para las aplicaciones web en casi todos los casos. En cualquier caso, existen circunstancias excepcionales en las que no es adecuado. Por este motivo, los servidores compatibles con Java EE ofrecen la posibilidad de cambiar el modelo de delegación de padre-último a padre-primero(parent-last back to parent-first).

### Enterprise Archives - Archivos empresariales

Ya aprendió acerca de los archivos WAR, pero hay otro tipo de archivo Java EE que debería conocer: los archivos **EAR** . Un ***Enterprise Archive*** es una colección de archivos JAR, archivos WAR y archivos de configuración comprimidos en un único archivo implementable (en formato ZIP, al igual que los archivos JAR y WAR).

La Figura 1-3 muestra un archivo EAR de ejemplo. Al igual que con un archivo WAR, el directorio raíz **`/META-INF`** contiene el manifiesto del archivo y no está disponible para la ruta de clases de la aplicación. El archivo **`/META-INF/application.xml`** es un descriptor de implementación especial que describe cómo implementar los diversos componentes incluidos en el archivo EAR. En el nivel raíz de un archivo EAR se encuentran todos los módulos de la aplicación web incluidos en él: un archivo WAR para cada módulo. No hay nada especial en estos archivos WAR; pueden tener el mismo contenido y las mismas características que un archivo WAR normal e independiente. El archivo EAR también puede contener bibliotecas JAR, que pueden servir para muchos propósitos. Los archivos JAR pueden contener Enterprise JavaBeans declarados en el descriptor de implementación **`/META-INF/application.xml`**, o pueden ser bibliotecas de terceros simples que dos o más módulos WAR comparten dentro del archivo empresarial.

![image](https://github.com/user-attachments/assets/d69fc860-2141-4265-a70a-ab0a342a105b)

**FIGURA 1-3**

Como habrás imaginado, los archivos empresariales también tienen su propia arquitectura **`ClassLoader`**. Normalmente, **`ClassLoader`** se inserta un módulo adicional en la jerarquía entre el servidor **`ClassLoader`** y la aplicación web **`ClassLoader`** asignada a cada módulo. Esto **`ClassLoader`** aísla la aplicación empresarial de otras aplicaciones empresariales, pero permite que varios módulos de un único EAR compartan bibliotecas comunes contenidas en el EAR. Este nuevo modelo **`ClassLoader`** puede utilizar los modelos de delegación padre-último (predeterminado) o padre-primero. Las aplicaciones web **`ClassLoader`** pueden delegar entonces padre-primero (permitiendo que las clases de biblioteca EAR tengan prioridad) o padre-último (permitiendo que las clases WAR tengan prioridad).

Si bien es útil comprender los archivos empresariales, son una característica de la especificación completa de Java EE y la mayoría de los servidores que solo admiten contenedores web (como Apache Tomcat) no los admiten. Por lo tanto, no se tratan más en este libro.

***WARNING** Los **`ClassLoader`** ejemplos descritos en esta sección son solo eso: ejemplos. Aunque las especificaciones de Java EE describen la carga de clases padre-primero y padre-último, las diferentes implementaciones logran estos modelos de diferentes maneras y cada servidor podría tener ciertos matices que podrían causar problemas según sus necesidades. Siempre debe leer la documentación del servidor que elija para poder determinar si la **`ClassLoader`** arquitectura de ese servidor en particular es apropiada para usted.*

## RESUMEN

En este capítulo, exploró las historias de la Plataforma Java, Edición Estándar y la Plataforma Java, Edición Empresarial, y aprendió cómo las dos plataformas evolucionaron juntas durante los últimos 19 años. Se le presentaron brevemente algunos de los temas tratados en este libro (Servlets, filters, listeners, JSPs y más) y vio cómo se estructuran las aplicaciones Java EE, tanto internamente como en el sistema de archivos. Luego, aprendió sobre los archivos de aplicaciones web y los archivos empresariales y cómo sirven como vehículos para transportar e implementar aplicaciones Java EE.

El resto del libro explora estos temas con mucho más detalle y responde a las muchas preguntas que probablemente tenga después de leer las últimas páginas. En el Capítulo 2, analizará en profundidad los servidores de aplicaciones y los contenedores web, qué son y cómo elegir uno para sus propósitos. También aprenderá a instalar y utilizar Tomcat para los ejemplos de este libro.
