# 1. Cómo llegamos hasta aquí: la historia de Java en pocas palabras

#### ¿QUÉ HAY EN ESTE CAPÍTULO?

* Entendiendo la administración de Java
* Diferenciación de las principales versiones de Java
* Trabajar con depreciación y jubilación
* Identificación de cambios de nombre
* Comprender los principios del cambio

## INTRODUCCIÓN

Ya aprendiste Java y estás listo para comenzar a usarlo en el trabajo. O ya lo estás usando en el trabajo, pero has descubierto el intimidante ecosistema que nunca te enseñaron en la escuela. Este libro es para aquellos que ya aprendieron a codificar en Java y están buscando el siguiente paso. Ya seas estudiante, un programador profesional que cambia de lenguaje o que está cambiando de carrera, esta es tu oportunidad de aprender sobre el ecosistema de Java.

Este libro no pretende ser una guía completa del ecosistema Java; eso requeriría muchos tomos de miles de páginas. Si recién está aprendiendo Java, le recomendamos *Head First Java*, 3.ª edición (O'Reilly Media, 2022) o *Java For Dummies* (For Dummies, 2025). Luego, vuelva a leer este libro. El objetivo de este libro es exponer al lector a algunos de los frameworks, herramientas y técnicas más comunes que se utilizan en los talleres de desarrollo empresarial de Java, con suficientes antecedentes y ejemplos para sumergirse en ellos.

En este capítulo, cubriremos información general sobre Java antes de abordar temas especializados en los capítulos posteriores. Si bien los capítulos se pueden leer sin seguir el orden establecido, recomendamos leer los capítulos 1 a 4 antes de saltearlos.

<hr>

**DESCARGAS DE CÓDIGOS PARA ESTE CAPÍTULO**

El código fuente de este capítulo está disponible en la página del libro en www.wiley.com. Haga clic en el enlace Descargas. El código también se puede encontrar en https://github.com/realworldjava/Ch01-History. Consulte el archivo **README.md** en ese repositorio para obtener más detalles.

<hr>

## COMPRENDIENDO LA ADMINISTRACIÓN DE JAVA

Java fue creado por **James Gosling** en Sun Microsystems y lanzado al mundo en 1995.

Según cuenta la leyenda, Java comenzó como **“Oak”**, un nuevo lenguaje para crear software integrado en dispositivos inteligentes. La idea era novedosa: en lugar de escribir software para cada sistema operativo integrado, diseñar un lenguaje compilado, orientado a objetos, que se escribiera una vez y se ejecutara en cualquier lugar y que produjera código de bytes, y diseñar un intérprete de código de bytes para cada plataforma que pudiera ejecutarlo.

Mientras tanto, incluían frameworks integrados que, en otros lenguajes, eran complementos, como diseñadores de UI o de concurrencia. Luego, completaban todo esto con la gestión de memoria en forma de recolección de basura y la optimizaban mediante compilación en tiempo real (just-in-time JIT) y listo, tenían todo lo necesario para una plataforma de lenguaje integrado.

Pero, por desgracia, pronto se descubrió que ya se estaba gestando una plataforma llamada Oak. Una larga noche en una cafetería tomando un café caliente y el resto es historia.

Muchos años después, *en 2009, Oracle adquirió Sun* y la propiedad de Java pasó a manos de Oracle. Hasta el día de hoy, Oracle sigue siendo el administrador o custodio de Java.

El compromiso de la comunidad Java de garantizar que Java sea compatible con versiones anteriores y su sólida serie de miles de pruebas Technology Compatibility Kit (TCK) que deben aprobarse para cada característica proporcionan la estabilidad y confiabilidad que han colocado a Java en su lugar como uno de los lenguajes de programación más exitosos de la historia.

Oracle reconoce que su gestión es una responsabilidad fundamental, dada la gran cantidad de personas y empresas que utilizan Java de forma intensiva. El JCP (Java Community Process) tiene un Comité Ejecutivo (básicamente, la junta directiva de Java) con muchas organizaciones como miembros para garantizar que la comunidad esté representada. Algunos miembros pasados/futuros son competidores con sus propios JDK (Java Development Kits), por ejemplo, Amazon, Azul y Microsoft. Otros son complementarios, en particular los proveedores de entornos de desarrollo integrados (IDE) como Eclipse y JetBrains. Otros son simplemente fuertes defensores de Java como BellSoft y Fujitsu. Por último, hay miembros de la comunidad como SouJava (Brazilian Java User Group) y Ken Fogel (miembro individual).

Uno de los cambios introducidos bajo la dirección de Oracle fue un cronograma de lanzamientos más frecuente y predecible. Observe en la Figura 1.1 que los lanzamientos han variado tanto en frecuencia como en mes. En un caso, los usuarios de Java tuvieron que esperar más de cinco años para obtener una nueva versión.

![image](https://github.com/user-attachments/assets/d071c757-9e85-4372-b788-e1cba98e3c47)

**FIGURA 1.1: Versiones de Java**

Con el nuevo ritmo de lanzamiento, cada seis meses sale una nueva versión de Java. Puede que pienses que muchas empresas no quieren actualizar cada seis meses, ¡y tienes razón! También hay lanzamientos menos frecuentes llamados lanzamientos de soporte a largo plazo (**Long-Term Support - LTS**). Cuando comenzó el nuevo ciclo de lanzamiento, los lanzamientos de LTS se hacían cada tres años. Ahora se hacen cada dos años.

La Tabla 1.1 muestra los lanzamientos desde el inicio de la nueva cadencia de lanzamientos hasta la publicación de este libro. Como puede ver, ahora hay lanzamientos regulares y predecibles. Este libro utiliza Java 21, que era la última versión de larga duración en el momento de la impresión.

La figura 1.2 muestra el cronograma de lanzamiento de LTS. Ahora que existe un patrón, es posible predecir las fechas de lanzamiento de LTS en el futuro, lo que ayuda a las empresas a planificar.

Muchas empresas ejecutan sus programas Java de forma remota, por ejemplo, a través de un sitio web. Hasta 2020, esto se hacía a menudo a través de Spring o Java EE (Enterprise Edition). Consulte el Capítulo 6 , “Conocimiento del Spring Framework” y el Capítulo 14 , “Conocimiento más sobre el ecosistema”, para obtener más detalles. En 2020, Oracle entregó la administración de Java EE a una fundación de código abierto. Dado que “Java” es una marca comercial, el marco Java EE pasó a llamarse **“Jakarta EE”** en ese momento.

**TABLA 1.1: Versiones de Java**

![image](https://github.com/user-attachments/assets/124cb8e2-a339-46dc-b031-f8e949fa1ade)

![image](https://github.com/user-attachments/assets/7c5a01f3-19b5-43e0-a378-f5bf5a404901)

**FIGURA 1.2: Calendario de lanzamiento de LTS, con predicciones futuras**

## Diferenciación de versiones clave de Java

El lenguaje Java ha evolucionado bastante con el tiempo. Si observa las características clave que se agregaron con el tiempo, podrá tener una idea de esta evolución y de la expectativa de que el lenguaje seguirá mejorando. Además, sabrá qué esperar si su proyecto de trabajo no está en la última versión.

Tenga en cuenta que esta sección no es ni de lejos una lista completa de funciones. Hemos seleccionado las funciones más importantes de cada versión analizada.

Quizás se pregunte por qué no incluimos la inferencia de tipos con la palabra clave **`var`** en esta sección. Si bien ambos autores de este libro utilizan **`var`** en algunos casos en nuestro código de trabajo, pensamos que sería más claro en este libro especificar cuáles son los tipos y asegurarnos de que se representen todas las importaciones.

### Codificación de genéricos en Java 5

Antes de Java 5, el compilador no tenía forma de saber qué se quería incluir en una lista. Java 5 introdujo los genéricos, que permiten especificar el tipo; en el caso del siguiente ejemplo, un **`String`**:

```java
1:  import java.util.ArrayList;
2:  import java.util.List;
3:
4:  public class Java5Generics {
5:
6:     private static List<String> createList() {
7:        List<String> buildingNames = new ArrayList<String>();
8:        buildingNames.add("Firehouse");
9:        return buildingNames;
10:    }
11:
12:    public static void main(String[] args) {
13:       List<String> buildingNames = createList();
14:
15:       System.out.println(buildingNames);  // [Firehouse]
16:    }
17: }
```

Ahora que hemos informado al compilador sobre nuestra intención, es nuestro asistente. El compilador producirá un error si intentamos agregar un **`Integer`** o **`LocalDate`** o cualquier otra cosa a **`buildingNames`**.

Quizás te preguntes por qué la línea 7 no lo dice **`new ArrayList<>()`** y, en su lugar, utiliza una versión más larga. El operador de diamante ( **`<>`** ) se agregó en Java 7 y este ejemplo es para Java 5. ¡Pero incluso esto muestra la evolución del lenguaje!

### Codificación con programación funcional desde Java 8

La programación funcional es una forma de escribir código de forma más declarativa. Se especifica lo que se quiere hacer en lugar de ocuparse del estado de los objetos. Se presta más atención a las expresiones que a los bucles.

Java 8 introdujo lambdas y referencias a métodos para facilitar la escritura de código con *ejecución diferida - deferred execution*, también conocido como “código que se ejecuta más tarde”. Ambos permiten pasar fácilmente código ejecutable a un método. En el siguiente código, puedes ver dos lambdas y una referencia a un método:

```java
1:  import java.util.Arrays;
2:  import java.util.List;
3:
4:  public class Java8FunctionalProgramming {
5:
6:     public static void main(String[] args) {
7:
8:        List<String> computerCompanies = Arrays.asList(
9:           "Dell", "Acer", "Microsoft", "IBM", "Lenovo");
10:       computerCompanies.stream()
11:          .filter(n -> n.length() > 5)
12:          .map(n -> "*" + n)
13:          .sorted()
14:          .forEach(System.out::println);
15:    }
16: }
```

Este código genera estas dos líneas:

```text
*Lenovo
*Microsoft
```

La línea 10 inicia la secuencia de comandos. Las líneas 11 y 12 utilizan lambdas para especificar lo que debe suceder en cada paso. Esto **`->`** te da una pista de que estás viendo una lambda. La línea 11 solo permite nombres con al menos cinco caracteres a través de la secuencia de comandos. La línea 12 agrega un asterisco al comienzo de cada línea de la secuencia de comandos. Ten en cuenta que no cambia el **`computerCompanies`** contenido original.

Luego, en la línea 14, puede ver la primera referencia de método. **`::`** Le indica que es una referencia de método y, en este caso, imprime los valores. Una referencia de método es una versión más compacta de una lambda. Escribirla **`n -> System.out.println(n)`** hubiera sido equivalente.

Quizás hayas notado que no llamamos **`List.of()`** en lugar de **`Arrays.asList()`** en la línea 8. **`List.of()`** ¡se agregó en Java 9!

### Módulos de codificación de Java 11

El sistema de módulos de la plataforma Java ( Java Platform Module System - JPMS) agrupa el código en un nivel superior al de los paquetes. El objetivo principal de un módulo es proporcionar grupos de paquetes relacionados para ofrecer un conjunto particular de funciones a los desarrolladores. Es como un archivo JAR, excepto que el desarrollador elige qué paquetes son accesibles fuera del módulo. Muchas empresas optan por no utilizar módulos y, de hecho, su uso es opcional.

Los módulos de Java se introdujeron en Java 9, no en Java 11. Los incluimos en Java 11 porque esa fue la primera versión LTS de Java que admitió módulos. Todos los proyectos en una versión de Java anterior a la 8 se actualizarán a Java 11, 17, 21, etc. No pasarán a la 9, ya que el soporte para Java 9 finalizó en marzo de 2018 (seis meses después de su lanzamiento en septiembre de 2017).

Un módulo es un archivo Java ( Java Archive - JAR ) que consta de un archivo **`module-info.java`** en la raíz del proyecto y uno o más paquetes Java. Por ejemplo, aquí hay un módulo con dos paquetes que contienen una clase cada uno:

![image](https://github.com/user-attachments/assets/2309c235-9e4c-4bb1-a6fd-6a47e53fc6d1)

Este ejemplo muestra archivos **`.class`** en lugar de archivos **`.java`** porque el archivo JAR contiene código de bytes ejecutable. Pero espere. No desea que quienes llaman a su módulo hagan referencia a **`PrivateHelper`**. Ahí es donde **`module-info`** entra en juego el archivo:

```java
module com.wiley.realworldjava.modulecode {
   exports com.wiley.realworldjava.modulecode.utils;
   requires java.sql;
}
```

La palabra clave **`module`** permite que Java sepa que estamos especificando un módulo aquí en lugar de un **`class`** o **`interface`** u otro tipo de nivel superior de Java. La directiva **`exports`** le dice a Java que los callers pueden hacer referencia al paquete **`utils`** directamente desde su código. Dado que el paquete **`internal`** no se menciona en el archivo **`module-info`**, los callers no pueden usarlo directamente, solo a través de **`BookUtils`**. Finalmente, la directiva **`requires`** especifica que usamos el módulo **`java.sql`**, que es proporcionado por Oracle con el JDK. Hay otro módulo que usamos llamado **`java.base`**, pero ese se proporciona automáticamente sin tener que especificarlo. Contiene clases comunes como **`String`** y **`List`**.

### Codificación de Text Blocks y Records desde Java 17

Fue difícil elegir un favorito de Java 17, por lo que elegimos dos. Los bloques de texto también se conocen como *multiline strings - cadenas multilínea*. Los bloques de texto se agregaron en Java 15. Al igual que los módulos, los enumeramos en la primera versión LTS que los puso a disposición. Puede ver un bloque de texto aquí rodeado por tres comillas dobles ( **`"`** ):

```java
1:  public class Java17TextBlocks {
2:
3:     public static void main(String[] args) {
4:
5:        String data = """
6:           Apple,Fruit
7:            Banana,Fruit
8:           Potato,Vegetable
9:           """;
10:
11:       String formatted = String.format("*%s*", data);
12:       System.out.println(formatted);
13:    }
14: }
```

Esto genera estas cuatro líneas:

```text
*Apple,Fruit
 Banana,Fruit
Potato,Vegetable
*
```

Tenga en cuenta que la sangría de nuestro bloque de texto se conserva y el espacio en blanco incidental utilizado para el formato IDE no. Tenga en cuenta también que las comillas triples en la línea 9 introducirán una línea en blanco en la cadena. Si desea omitir el salto de línea final, coloque las tres comillas dobles de cierre ( **`"`** ) al final de la línea 8.

Los registros se introdujeron en Java 17 y eliminaron una gran cantidad de código repetitivo al crear una clase inmutable. En este ejemplo se utiliza un registro simple:

```java
1:  public class Java17Records {
2:
3:     record Coordinate(double x, double y) {}
4:
5:     public static void main(String[] args) {
6:
7:        Coordinate coord = new Coordinate(1.2, 5.9);
8:        System.out.println(coord.x());
9:        System.out.println(coord);
10:    }
11: }
```

Esto produce el siguiente resultado:

```text
1.2
Coordinate[x=1.2, y=5.9]
```

La línea 3 crea un registro con dos campos. Un registro es como una clase inmutable que incluye lo siguiente:

* Una variable de instancia para cada parámetro enumerado
* Getters (sin el prefijo **`get`**/**`is`**)
* Un constructor que toma un parámetro para cada variable de instancia
* Los métodos **` equals()`** y **`hashCode()`** que incluyen el valor de cada variable de instancia
* Un método **`toString()`** que imprime cada campo del registro en un formato conveniente y fácil de leer.

La línea 8 demuestra que el método getter es **`x()`** en lugar de **`getX()`**. Finalmente, la línea 9 llama implícitamente a, **`toString()`** lo que demuestra que se puede obtener una implementación útil sin escribir ningún código.

Los registros son convenientes cuando se necesita una clase inmutable simple. Puede anular métodos en el cuerpo del registro o agregar sus propios métodos. Cuando necesita más poder de personalización o establecedores, como para entidades de Java Persistence API (JPA), Project Lombok puede satisfacer mejor sus necesidades. Consulte el Capítulo 8, “Código basado en anotaciones con Project Lombok”, para obtener más detalles.

### Aprendiendo sobre subprocesos virtuales desde Java 21

Hace mucho tiempo, Java utilizaba la clase **`Thread`** sin procesar para la concurrencia. Aunque esta sigue siendo la unidad de concurrencia de bajo nivel, el lenguaje luego agregó la clase **`Executors`** y técnicas de concurrencia más poderosas, como fork join y **`parallelStream()`**. Sin embargo, la paralelización no es gratuita; existen costos de configuración y coordinación además de los recursos de memoria de los propios subprocesos.

A medida que las computadoras cuentan con más unidades centrales de procesamiento (CPU), la paralelización se vuelve más importante. Java 21 introdujo hilos virtuales para reducir en gran medida el costo de la concurrencia. Consulte el Capítulo 9, “Paralelización de su aplicación mediante la concurrencia de Java”, para obtener una explicación más detallada y un ejemplo de hilos virtuales.

## TRABAJAR CON LA DEPRECACIÓN Y LA JUBILACIÓN(DEPRECATION AND RETIREMENT)

A medida que se agregan más y más elementos al lenguaje Java, es posible que se pregunte cómo se eliminan. Primero, los desarrolladores identifican las clases o métodos como *deprecated-obsoletos*, lo que significa que se desaconseja su uso posterior, pero aún se permite. Suponga que desea que los usuarios dejen de pasar un parámetro a **`magicNumber()`**.

```java
1:  public class DeprecationExample {
2:     /**
3:      * Returns a number
4:      * @deprecated Use {@link #getNumber()} instead
5:      * @param num number
6:      * @return number based on num
7:     */
8:     @Deprecated(forRemoval = true)
9:     public int getNumber(int num) {
10:       return num % 2;
11:    }
12:
13:    public int getNumber() {
14:       return 42;
15:    }
16: }
```

La línea 4 utiliza una etiqueta Javadoc, **`@deprecated`**, para incluir en la documentación que no se recomienda utilizar este método. La etiqueta **`@link`** se utiliza para explicar que se prefiere la llamada **`magicNumber()`** sin un parámetro.

La línea 8 muestra la anotación que marca el método como **`@Deprecated`**. Los IDE muestran el uso de código obsoleto como advertencia para llamar su atención sobre él. Consulte el Capítulo 2 , “Conociendo su IDE: el secreto del éxito”, para obtener más información sobre los IDE.

La línea 8 también muestra el atributo **`forRemoval`**, que se agregó en Java 9. Esto se utiliza para indicar si la intención es eliminar el código obsoleto en el futuro o simplemente fomentar interfaces de programación de aplicaciones ( Application Programming Interfaces - API) alternativas. Esto permite a los desarrolladores tomar decisiones inteligentes sobre si migrar el código.

Oracle mantiene una lista de las API que se eliminaron en https://docs.oracle.com/en/java/javase/21/migrate/removed-apis.html. Esta página muestra lo que se eliminó en cada versión entre Java 9 y Java 21. Por ejemplo, en Java 21, esta fue una de las dos API que se eliminaron:

```java
java.lang.ThreadGroup.allowThreadSuspension(boolean)
```
 
Es poco probable que haya utilizado este método. Oracle valora la compatibilidad con versiones anteriores y no elimina el código de uso generalizado. De hecho, algunos de los métodos **`java.util.Date`** han quedado obsoletos desde Java 1.1.

## IDENTIFICACIÓN DE CAMBIOS DE NOMBRE

Dada la evolución del ecosistema Java a lo largo de los años, hay algunos cambios de nombre que debería conocer. Esta sección le ayudará a identificar si las guías o la documentación antiguas son equivalentes o están obsoletas.

### Cambiar a Jakarta EE

Como se mencionó, en 2020, Oracle anunció la migración de Java EE a Jakarta EE. Como no fue hace tanto tiempo, la documentación que menciona Java EE sigue siendo relativamente útil. Después de todo, un tutorial de Java EE sobre *servlets*, que se usan comúnmente para ofrecer páginas web, es en su mayoría lo mismo que sobre servlets de Jakarta EE, y todos los conceptos descritos en buenos tutoriales se aplicarán.

La diferencia clave es que Jakarta EE 9 cambió el nombre del prefijo del nombre del paquete de **`javax`** a, **`jakarta`** ya que Java es una marca registrada de Oracle. Además, las nuevas funciones solo se tratan en la documentación de Jakarta EE.

### Cambio de nombre de las certificaciones

Oracle ofrecía una serie de certificaciones, entre ellas, **Sun Certified Java Associate (SCJA)**, **Sun Certified Java Professional (SCJP)** y **Sun Certified Master Java Developer (SCMJD)**, que se podían obtener. Todas estas certificaciones se renombraron para comenzar con “O”, de Oracle, lo que nos dio certificaciones como **OCJA**, **OCJP** y **OCMJD**. Cuando mires tu currículum, recuerda que todas estas certificaciones son equivalentes.

Muchas de estas certificaciones ya no existen o han cambiado significativamente desde el cambio de nombre, por lo que aprender de sitios web con los antiguos nombres de certificados de Sun probablemente no sea útil.

## COMPRENDIENDO LOS PRINCIPIOS DEL CAMBIO

El cambio es constante en Java y mantiene el lenguaje actualizado y útil. Algunos cambios están inspirados en otros lenguajes. Es de esperar que el lenguaje siga evolucionando a medida que se publiquen más versiones. Estos cambios incluirán mejoras en el lenguaje y nuevas API.

Los cambios en el ecosistema Java provienen de tres lugares principales.

* **Bug fixes-Corrección de errores**: Java proporciona correcciones a los errores que se informan en la base de datos de errores. 
   Es poco probable que se produzcan estos cambios, pero es importante tener en cuenta que Java se compromete a corregir los errores informados.
* **Java Enhancement Proposals (JEPs) Propuestas de mejora de Java**: Por ejemplo, los subprocesos virtuales son JEP 444. Algunas características de Java se lanzan como versiones preliminares antes de que se confirmen como definitivas. Los subprocesos virtuales tuvieron su primera versión preliminar en Java 19 como JEP 425 y su segunda versión preliminar en Java 20 como JEP 436 antes de su lanzamiento completo en Java 21.
* **Java Specification Requests (JSRs) Solicitudes de especificación de Java**: Las JSR son más grandes y tienen mayor impacto que las JEP. Por ejemplo, las lambdas eran JSR 335.
  
Si bien Java se ha comprometido a implementar un ciclo de lanzamiento de seis meses, valora mucho la compatibilidad con versiones anteriores tanto del lenguaje como de las API. El uso de una versión posterior de Java no debería impedir que el código se compile o ejecute. La compatibilidad con versiones anteriores no siempre se cumple, pero Oracle intenta minimizar el cambio tanto como sea posible.

Las funciones de vista previa ayudan a lograr este objetivo, ya que aún no están limitadas a la compatibilidad con versiones anteriores. Por eso, no deberías usar funciones de vista previa en producción, ya que podrían cambiar de cualquier manera. La compatibilidad con versiones anteriores es la razón por la que se eliminan tan pocas API obsoletas.

## REFERENCIAS ADICIONALES

* https://docs.oracle.com/en/java/javase/15/text-blocks/index.html
   Guía de bloques de texto de Oracle

* https://docs.oracle.com/en/java/javase/14/language/records.html
   Guía de registros de Oracle

* *OCP Certified Professional Java SE 17 Developer Study Guide (Sybex, 2022)*
   Guía de estudio de certificación de Jeanne para obtener más detalles sobre todas las funciones

* *The Java Module System (Manning, 2019)*
   Libro sobre módulos con gran detalle

## RESUMEN

Las siguientes son las conclusiones clave del capítulo:

* Java es propiedad de Oracle y otros ayudan a guiar el proceso.
* Cada seis meses se lanzan nuevas versiones de Java, y con menor frecuencia se lanzan versiones LTS.
* Continuamente se añaden nuevas funciones.
* Las API cuyo uso ya no se recomienda quedan obsoletas y, opcionalmente, se etiquetan para su eliminación.
* La compatibilidad con versiones anteriores es un principio central de la evolución de Java y garantiza que las aplicaciones Java existentes se ejecutarán sin problemas sin necesidad de realizar modificaciones importantes cuando se lance una nueva versión de Java.
