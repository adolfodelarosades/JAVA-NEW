# Professional Java for Web Applications
By Nicholas S. Williams

![image](https://github.com/user-attachments/assets/3e10f8c5-5279-4384-95a6-61a7b5049a57)

* TIME TO COMPLETE: **29h 2m**
* LEVEL: **Intermediate to advanced**
* SKILLS: **Java**
* PUBLISHED BY: **Wrox**
* PUBLICATION DATE: **March 2014**
* PRINT LENGTH: **936 pages**

### La guía completa de Wrox para crear aplicaciones web Java para la empresa

Esta guía muestra a los desarrolladores de software Java y a los ingenieros de software cómo crear aplicaciones web complejas en un entorno empresarial. Comenzará con una introducción a Java Enterprise Edition y a la aplicación web básica, luego configurará un entorno de servidor de aplicaciones de desarrollo, aprenderá sobre las herramientas utilizadas en el proceso de desarrollo y explorará numerosas tecnologías y prácticas de Java. El libro cubre herramientas y tecnologías estándar de la industria, tecnologías específicas y conceptos de programación subyacentes.

Java es un lenguaje de programación esencial utilizado en todo el mundo tanto para el desarrollo de aplicaciones de Android como para soluciones corporativas de nivel empresarial.

Como guía paso a paso o referencia general, este libro proporciona una solución de desarrollo Java todo en uno.

Explica Java Enterprise Edition 7 y la aplicación web básica, cómo configurar un entorno de servidor de aplicaciones de desarrollo, qué herramientas se necesitan durante el proceso de desarrollo y cómo aplicar varias tecnologías Java.

Cubre nuevas características del lenguaje Java 8, como expresiones Lambda y la nueva API de fecha y hora de Java 8 introducida como parte de JSR 310, que reemplaza las API de fecha y calendario heredadas.

Demuestra la nueva tecnología de conexión web WebSocket totalmente dúplex y su compatibilidad con Java EE 7, lo que permite al lector crear aplicaciones web ricas y verdaderamente interactivas que pueden enviar datos actualizados al cliente automáticamente.

Instruye al lector en la configuración y el uso de Log4j 2.0, Spring Framework 4 (incluido Spring Web MVC), Hibernate Validator, RabbitMQ, Hibernate ORM, Spring Data, Hibernate Search y Spring Security.

Cubre el registro de aplicaciones, JSR 340 Servlet API 3.1, JSR 245 JavaServer Pages (JSP) 2.3 (incluidas bibliotecas de etiquetas personalizadas), JSR 341 Expression Language 3.0, JSR 356 WebSocket API 1.0, JSR 303/349 Bean Validation 1.1, JSR 317/338 Java Persistence API (JPA) 2.1, búsqueda de texto completo con JPA, servicios web RESTful y SOAP, Advanced Message Queuing Protocol (AMQP) y OAuth.

Professional Java for Web Applications es la guía completa de Wrox para desarrolladores de software que están familiarizados con Java y que están listos para crear aplicaciones web Java empresariales de alto nivel.

## Contenido

### Parte I: Creación de aplicaciones empresariales

#### Capítulo 1: Introducción a la plataforma Java, Enterprise Edition
1. Cronología de las plataformas Java
2. Comprender la estructura básica de una aplicación web
3. Resumen
   
#### Capítulo 2: Uso de contenedores web
1. Elección de un contenedor web
2. Instalación de Tomcat en su máquina
3. Implementación y anulación de la implementación de aplicaciones en Tomcat
4. Depuración de Tomcat desde su IDE
5. Resumen
   
#### Capítulo 3: Cómo escribir tu primer servlet
1. Creando una clase Servlet
2. Configuración de un servlet para su implementación
3. Comprender `doGet()`, `doPost()` y otros métodos
4. Uso de parámetros y aceptación de envíos de formularios
5. Configuración de su aplicación mediante parámetros de inicialización
6. Subir archivos desde un formulario
7. Cómo hacer que su aplicación sea segura para subprocesos múltiples
8. Resumen

#### Capítulo 4: Uso de JSP para mostrar contenido
1. `<br/>` Es más fácil que `output.println(“<br/>”)`
2. Creando tu primer JSP
3. Usar Java dentro de un JSP (¡y por qué no deberías hacerlo!)
4. Combinando Servlets y JSP
5. Una nota sobre los documentos JSP (JSPX)
6. Resumen

#### Capítulo 5: Mantenimiento del estado mediante sesiones
1. Entendiendo por qué son necesarias las sesiones
2. Uso de cookies de sesión y reescritura de URL
3. Almacenamiento de datos en una sesión
4. Cómo aplicar las sesiones de manera útil
5. Agrupamiento de una aplicación que utiliza sesiones
6. Resumen

#### Capítulo 6: Uso del lenguaje de expresión en JSP
1. Comprender el lenguaje de expresión
2. Escribir con la sintaxis EL
3. Uso de variables con ámbito en expresiones EL
4. Acceder a colecciones con la API Stream
5. Reemplazar código Java por lenguaje de expresión
6. Resumen

#### Capítulo 7: Uso de la biblioteca de etiquetas estándar de Java
1. Presentación de las etiquetas JSP y JSTL
2. Uso de la biblioteca de etiquetas principal (espacio de nombres C)
3. Uso de la biblioteca de etiquetas de internacionalización y formato (espacio de nombres FMT)
4. Uso de la biblioteca de etiquetas de acceso a bases de datos (espacio de nombres SQL)
5. Uso de la biblioteca de etiquetas de procesamiento XML (espacio de nombres X)
6. Reemplazo de código Java con etiquetas JSP
7. Resumen

#### Capítulo 8: Escritura de bibliotecas de etiquetas y funciones personalizadas
1. Descripción de los TLD, los archivos de etiquetas y los controladores de etiquetas
2. Cómo crear su primer archivo de etiqueta para que sirva como plantilla HTML
3. Creación de un controlador de etiquetas de formato de fecha más útil
4. Creación de una función EL para abreviar cadenas
5. Reemplazo de código Java con etiquetas JSP personalizadas
6. Resumen

#### Capítulo 9: Cómo mejorar su aplicación mediante filtros
1. Entendiendo el propósito de los filtros
2. Creación, declaración y asignación de filtros
3. Cómo ordenar sus filtros correctamente
4. Investigación de usos prácticos de los filtros
5. Simplificando la autenticación con un filtro
6. Resumen

#### Capítulo 10: Cómo hacer que su aplicación sea interactiva con WebSockets
1. Evolución: de Ajax a WebSockets
2. Comprensión de las API de WebSocket
3. Creación de juegos multijugador con WebSockets
4. Uso de WebSockets para comunicarse en un clúster
5. Agregar “Chat con soporte” a la aplicación de soporte al cliente
6. Resumen

#### Capítulo 11: Uso del registro para supervisar su aplicación
1. Comprender los conceptos de registro
2. Uso de niveles y categorías de registro
3. Elección de un marco de registro
4. Integración del inicio de sesión en su aplicación
5. Resumen

### Parte II: Incorporación de Spring Framework a la mezcla

#### Capítulo 12: Introducción a Spring Framework
1. ¿Qué es Spring Framework?
2. ¿Por qué Spring Framework?
3. Comprensión de los contextos de aplicación
4. Arranque del marco Spring
5. Configuración de Spring Framework
6. Utilización de perfiles de definición de Bean
7. Resumen

#### Capítulo 13: Reemplazar sus servlets por controladores
1. Entendiendo `@RequestMapping`
2. Uso del patrón de modelo y vista de Spring Framework
3. Simplifique su vida con objetos de formulario
4. Actualización de la aplicación de atención al cliente
5. Resumen

#### Capítulo 14: Uso de servicios y repositorios para respaldar sus controladores
1. Comprensión de la relación Modelo-Vista-Controlador más Controlador-Servicio-Repositorio
2. Uso del contexto de aplicación raíz en lugar de un contexto de aplicación web
3. Mejorar los servicios con ejecución asincrónica y programada
4. Aplicación de la separación de capas lógicas a WebSockets
5. Resumen

#### Capítulo 15: Internacionalización de su aplicación con Spring Framework i18n
1. ¿Por qué necesitas Spring Framework i18n?
2. Uso de las API básicas de internacionalización y localización
3. Configuración de la internacionalización en Spring Framework
4. Internacionalizando su código
5. Resumen

#### Capítulo 16: Uso de JSR 349, Spring Framework y Hibernate Validator para la validación de beans
1. ¿Qué es la validación de Bean?
2. Configuración de la validación en el contenedor de Spring Framework
3. Cómo agregar anotaciones de validación de restricciones a sus beans
4. Configuración de Spring Beans para la validación de métodos
5. Cómo escribir sus propias restricciones de validación
6. Integración de la validación en la aplicación de soporte al cliente
7. Resumen

#### Capítulo 17: Creación de servicios web RESTful y SOAP
1. Comprensión de los servicios web
2. Configuración de servicios web RESTful con Spring MVC
3. Prueba de los puntos finales de su servicio web
4. Uso de Spring Web Services para SOAP
5. Resumen

#### Capítulo 18: Uso de mensajería y agrupamiento para lograr flexibilidad y confiabilidad
1. Cómo reconocer cuándo se necesitan mensajería y agrupación
2. Cómo agregar compatibilidad con mensajería a su aplicación
3. Cómo hacer que su mensajería sea distribuible en un clúster
4. Distribución de eventos con AMQP
5. Resumen

### Parte III: Conservación de datos con JPA y ORM de Hibernate

#### Capítulo 19: Introducción a la API de persistencia de Java y ORM de Hibernate
1. ¿Qué es la persistencia de datos?
2. ¿Qué es un mapeador objeto-relacional?
3. Una breve mirada a Hibernate ORM
4. Preparación de una base de datos relacional
5. Una nota sobre las dependencias de Maven
6. Resumen

#### Capítulo 20: Asignación de entidades a tablas con anotaciones JPA
1. Introducción a las entidades simples
2. Creación y uso de una unidad de persistencia
3. Mapeo de tipos de datos complejos
4. Resumen

#### Capítulo 21: Uso de JPA en repositorios de Spring Framework
1. Uso de repositorios y transacciones de Spring
2. Configuración de la persistencia en Spring Framework
3. Creación y uso de repositorios JPA
4. Conversión de datos con DTO y entidades
5. Resumen

#### Capítulo 22: Eliminación de repositorios repetitivos con Spring Data JPA
1. Comprender el acceso unificado a los datos de Spring Data
2. Configuración y creación de repositorios Spring Data JPA
3. Refactorización de la aplicación de soporte al cliente
4. Resumen

#### Capítulo 23: Búsqueda de datos con JPA y Hibernate Search
1. Introducción a la búsqueda
2. Uso de criterios avanzados para localizar objetos
3. Aprovechar los índices de texto completo con JPA
4. Cómo indexar cualquier dato con Apache Lucene y Hibernate Search
5. Resumen

#### Capítulo 24: Creación de asignaciones avanzadas y tipos de datos personalizados
1. ¿Que queda?
2. Conversión de tipos de datos no estándar
3. Incorporación de POJO dentro de entidades
4. Definición de relaciones entre entidades
5. Cómo abordar otras situaciones comunes
6. Creación de activadores programáticos
7. Refinando la aplicación de soporte al cliente
8. Resumen

### Parte IV: Cómo proteger su aplicación con Spring Security

#### Capítulo 25: Introducción a Spring Security
1. ¿Qué es la autenticación?
2. ¿Por qué Spring Security?
3. Resumen

#### Capítulo 26: Autenticación de usuarios con Spring Security
1. Elección y configuración de un proveedor de autenticación
2. Cómo escribir su propio proveedor de autenticación
3. Resumen

#### Capítulo 27: Uso de etiquetas de autorización y anotaciones
1. Autorización por Declaración
2. Comprensión de las decisiones de autorización
3. Creación de listas de control de acceso para la seguridad de objetos
4. Agregar autorización a la atención al cliente
5. Resumen

#### Capítulo 28: Protección de servicios web RESTful con OAuth
1. Comprensión de la seguridad de los servicios web
2. Presentando OAuth
3. Uso de OAuth de Spring Security
4. Finalización de la solicitud de soporte al cliente
5. Creación de una aplicación cliente OAuth
6. Resumen

### Introducción
### Anuncios
### Acuerdo de licencia de usuario final
