# Sección 2: Introducción a Base de Datos con JDBC


## 1. Introducción SQL 12 min

## 2. Instalación MySQL
## 3. Creando el esquema de base de datos

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/048a920e-6f2a-4c99-abe3-8504f4227126">

<img width="1330" alt="image" src="https://github.com/user-attachments/assets/66d6148d-f169-4ad1-ac68-2149d4f2c3d8">

<img width="938" alt="image" src="https://github.com/user-attachments/assets/9c5164ff-1fe1-4692-b360-d04de834fc48">

<img width="394" alt="image" src="https://github.com/user-attachments/assets/57463860-f120-4cd8-a4dd-359f3a28a5ad">

<img width="402" alt="image" src="https://github.com/user-attachments/assets/e46b5d09-c6c2-49f2-9d1f-1a88a1975407">

<img width="392" alt="image" src="https://github.com/user-attachments/assets/a97fe4d6-14c0-42af-a272-1bc66231027e">

<img width="361" alt="image" src="https://github.com/user-attachments/assets/305179fd-c105-41ef-8470-14c585e087ee">

<img width="937" alt="image" src="https://github.com/user-attachments/assets/fa0a87ba-9dca-4c3a-a557-3a1261fc0da2">

<img width="926" alt="image" src="https://github.com/user-attachments/assets/2cfb1edd-b366-4148-b0db-dfe037a161ab">

<img width="918" alt="image" src="https://github.com/user-attachments/assets/9f70e3b9-40ca-4a27-a2e8-b3d98b8c0a71">

<img width="390" alt="image" src="https://github.com/user-attachments/assets/edc25de1-2cf3-4df0-8715-d66cee45c1df">

<img width="385" alt="image" src="https://github.com/user-attachments/assets/07fca39a-4dab-49a2-8068-7e809966083c">

<img width="1008" alt="image" src="https://github.com/user-attachments/assets/4a0ada4f-fc80-4176-88ef-710f8c9bea38">

<img width="1020" alt="image" src="https://github.com/user-attachments/assets/b5c35b8a-ed54-4e4f-a48b-b319f3c9c040">

<img width="922" alt="image" src="https://github.com/user-attachments/assets/2b1973e5-76c2-4daa-9b5f-e9330576ce8a">

<img width="920" alt="image" src="https://github.com/user-attachments/assets/ff8f5787-3134-473c-aef2-b9a9c07255f3">

<img width="1012" alt="image" src="https://github.com/user-attachments/assets/78b072cc-7823-46db-83b8-d6b4978f118f">

## 4. Introducción al API JDBC



## 5. Actualización creando proyecto Maven en Intellij
## 6. Creando nuestro proyecto Java con JDBC

### 💻 Proyecto 101_Guia_Completa_Jakarta_EE_9

#### 💻 EjemploJDBC.java
<img width="1511" alt="image" src="https://github.com/user-attachments/assets/a153414c-6e73-4c9b-823d-a8fee7da6d8c">

<img width="826" alt="image" src="https://github.com/user-attachments/assets/95e06fcb-48c8-470f-a246-29758a842916">

<img width="1511" alt="image" src="https://github.com/user-attachments/assets/239ca117-6569-4bd9-9013-cdb5c6419970">

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/8af21b31-02b3-42e2-99db-6c18f1d513cf">

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/8e98e862-4d9a-4d14-9f66-8ef5718f8092">

<img width="1021" alt="image" src="https://github.com/user-attachments/assets/8ad05b96-67b9-4b57-bc58-0e355f203fac">

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/bec010b5-6f45-4894-b613-568e94fea8a4">

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/e30adbab-067f-4937-b15c-5217092cdfd3">

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/6b20b156-a9fd-421a-8f1e-9c8ce8110aa7">

<img width="514" alt="image" src="https://github.com/user-attachments/assets/04b2b4a9-ebd8-4a77-a7d9-fb1c2a104bd7">

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/5a0ee36c-bd67-4ac3-b293-df241aeae89a">

Crear clase EjemploJDBC.java

<img width="1137" alt="image" src="https://github.com/user-attachments/assets/4ebd7367-b3bd-4c83-97e2-9acbd3105bcd">

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/429340e4-e840-4954-af6d-820ae0708cf3">

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/51374bff-97c1-49b0-9aa9-94b5a52f75e7">

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/2d7c9e41-1729-4af0-859e-856e7c475fac">

ServerTimeZone

https://en.wikipedia.org/wiki/List_of_tz_database_time_zones

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/9827bea5-1b76-49a4-8b90-bcd8c91c1b85">

```String url = "jdbc:mysql://localhost:3306/101_JakartaEE9?serverTimezone=Europe/Madrid";```

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/3eab8b5a-c24c-4356-94e3-a6924a7c08eb">

**```EjemploJDBC.java```**
```java
package org.example;

import java.sql.*;

public class EjemploJDBC {

    public static void main(String[] args) {

        String url = "jdbc:mysql://localhost:3306/101_JakartaEE9?serverTimezone=Europe/Madrid";
        String username = "root";
        String password = "root";

        try {
            Connection conn = DriverManager.getConnection(url, username, password);
            Statement stmt = conn.createStatement();
            ResultSet rs = stmt.executeQuery("SELECT * FROM productos");

            while (rs.next()){
                System.out.println(rs.getString("nombre"));
            }
            rs.close();
            stmt.close();
            conn.close();
        } catch (SQLException e) {
            throw new RuntimeException(e);
        }
    }
}
```


## 7. Cerrando conexiones, recursos y manejo de errores

#### 💻 EjemploJDBC_02.java - Cerrando conexiones

¿Qué pasa si ocurre un error? Por ejemplo que no encuentre la tabla.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/08253ba2-4802-4723-9020-4d544a8af403">

El error indica que no encuentra la tabla ```productos2```, al ejecutar la sentencia del query y fallar se va al interior del ```catch```por lo que no ejecuta las sentencias de cierre del ```ResultSet```, ```Statement``` y ```Connection```, las conexiones se quedan abiertas.

Pasa solucionar esto se debe añadir ```finaly```

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/02490974-c4c9-44f4-b86f-5f8d9d6a4f33">

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/a2213f5b-2672-4480-80ae-909dd344ae1d">

Con este cambio hemos garantizado que si existe un error todas las conexiones se cierran.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/b403b3fc-f8b6-4f37-b2b6-d862ae14857f">

Si modificamos el error en el nombre de la tabla el código se ejecuta.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/c833248a-a677-4baf-a515-f0e056ea231e">

Como se puede apreciar el código crecio para asegurar el cierre de las conexiones se haga en caso de error.

**```EjemploJDBC_02.java```**
```java
package org.example;

import java.sql.*;

public class EjemploJDBC_02 {

    public static void main(String[] args) {

        String url = "jdbc:mysql://localhost:3306/101_JakartaEE9?serverTimezone=Europe/Madrid";
        String username = "root";
        String password = "root";

        Connection conn = null;
        Statement stmt = null;
        ResultSet rs = null;

        try {
            conn = DriverManager.getConnection(url, username, password);
            stmt = conn.createStatement();
            rs = stmt.executeQuery("SELECT * FROM productos");

            while (rs.next()){
                System.out.println(rs.getString("nombre"));
            }
        } catch (SQLException e) {
            throw new RuntimeException(e);
        } finally {
            try {
                if (rs != null){
                    rs.close();
                }
                if (stmt != null) {
                    stmt.close();
                }
                if (conn != null) {
                    conn.close();
                }
            } catch (SQLException throwables) {
                throwables.fillInStackTrace();
            }finally {

            }
        }
    }
}

```

#### 💻 EjemploJDBC_03.java - try con recursos

Existe una forma más sencilla de hacer esto usando los **try con recursos**.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/b4f825ef-373c-4e35-9aef-39b9a06711c6">

Como se puede observar el código queda mucho más compacto. Todo lo que se ponga como parámetros en el ```try```, se cerrara automaticamente al finalizar el try, independientemente de si ha existido error o no.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/a13dbc7d-82b7-429e-a5b3-b4d87e109df6">

Podríamos provocar otro error diferente por ejemplo un usuario inexistente o un password incorrecto.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/b42aeb90-f8f1-466b-a5cb-78d12bb4b6dc">

Si nuestra ejecución es correcta hemos garantizado que se cierre todo lo declarado en el **try con recursos**.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/ba66f1c9-73f5-4a41-8daf-061509c2ad13">

**```EjemploJDBC_03.java```**
```java
package org.example;

import java.sql.*;

public class EjemploJDBC_03 {

    public static void main(String[] args) {

        String url = "jdbc:mysql://localhost:3306/101_JakartaEE9?serverTimezone=Europe/Madrid";
        String username = "root";
        String password = "root";

        try (
                Connection conn = DriverManager.getConnection(url, username, password);
                Statement stmt = conn.createStatement();
                ResultSet rs = stmt.executeQuery("SELECT * FROM productos")
                )
        {
            while (rs.next()){
                System.out.println(rs.getString("nombre"));
            }
        } catch (SQLException e) {
            throw new RuntimeException(e);
        }
    }
}
```

#### 💻 EjemploJDBC_04.java - Imprimiendo todos los registros con todos sus campos

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/1db67c3c-65e4-4227-9778-76751b9c3d5a">

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/12a8f8a6-cc32-43eb-9da1-c821520fa40a">


**```EjemploJDBC_04.java```**

```java
package org.example;

import java.sql.*;

public class EjemploJDBC_04 {

    public static void main(String[] args) {

        String url = "jdbc:mysql://localhost:3306/101_JakartaEE9?serverTimezone=Europe/Madrid";
        String username = "root";
        String password = "root";

        try (
                Connection conn = DriverManager.getConnection(url, username, password);
                Statement stmt = conn.createStatement();
                ResultSet rs = stmt.executeQuery("SELECT * FROM productos")
                )
        {
            while (rs.next()){
                System.out.print(rs.getInt("id"));
                System.out.print(" | ");
                System.out.print(rs.getString("nombre"));
                System.out.print(" | ");
                System.out.print(rs.getInt("precio"));
                System.out.print(" | ");
                System.out.println(rs.getDate("fecha_registro"));
            }
        } catch (SQLException e) {
            throw new RuntimeException(e);
        }
    }
}
```

### Botón Maven

<img width="537" alt="image" src="https://github.com/user-attachments/assets/40b7ed52-22ed-4c34-85aa-5518e316cfe1">

<img width="362" alt="image" src="https://github.com/user-attachments/assets/be94d892-71ff-454e-97f7-c4788264d417">

<img width="707" alt="image" src="https://github.com/user-attachments/assets/26a78627-cabe-4a71-a645-8e0a194cc294">

<img width="701" alt="image" src="https://github.com/user-attachments/assets/3b1e2bdc-29bb-4608-9649-525971e26cfc">

**```clean```** : 

**```validate```** : 

**```compile```** : 

**```test```** : 

**```package```** : Empaqueta y crea JAR o WAR

**```verify```** : 

**```install```** : Crea JAR o WAR y lo copia en nuestro repositorio local de Maven, de esa forma podemos añadirlo como libreria en otros proyectos con una dependencia.

**```site```** : 

**```deploy```** : 

**JAR: Java ARchive** , Archivo comprimido de Java. Empaqueta la aplicación con el código compilado (.class), listo para ejecutarlo.

**WAR: Java Web Application ARchive** Archivo comprimido de Java para Web.


## 8. Añadiendo la clase singleton de conexión a la base de datos

Problemas actuales de nuestro código. 

La conexión a la BD esta muy acoplada en nuestra clase, donde definimos la conexión para su uso, podríamos tener más clases que realicen diferentes tareas sobre la BD como puede ser otras consultas, insertar registros, eliminar productos, etc. No deberíamos hacer una conexión a la BD en cada clase, ya que eso implicaria realizar una conexión nueva cada que queramos trabajar sobre la BD. Esto es incorrecto por varias razones:

* Debebos reutilizar el código.
* En el problema que ponemos encima de la mesa existiria duplicación de código, duplicando la conexión en varios sitios. 
* Duplicariamos los datos de la conexión a la BD y que pasa si estos cambian, tendríamos que ir a cada sitio donde se han definido, por lo que el mantenimiento sería muy engorrozo.
* Al usar el ```DriverManager``` estariamos creando una nueva conexión a la BD en cada lugar donde se use. La conexión a la BD es un recurso costoso que impacta directamente el rendimiento de nuestra aplicación.
* Necesitamos definir una sola conexión a la BD y reutilizarla en nuestro código, usando el patrón Singelton.

#### 💻 ConexionBD.java - Clase de Utilidad para conectarse a la BD.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/1faaae5b-d1a6-4ec3-807f-87000c786387">

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/559d0aa0-abf6-40ec-9e13-1470c7f5369c">

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/75b2e844-5f89-4578-8323-f6c785b535c0">

**```ConexionBD.java```**

```java
package org.example.util;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

public class ConexionBD {

    private static String url = "jdbc:mysql://localhost:3306/101_JakartaEE9?serverTimezone=Europe/Madrid";
    private static String username = "root";
    private static String password = "root";
    private static Connection connection;

    public static Connection getInstance() throws SQLException {
        if(connection == null){
            connection = DriverManager.getConnection(url, username, password);
        }
        return connection;
    }
}
```

**```EjemploJDBC_05_Conexion.java```**

```java
package org.example;

import org.example.util.ConexionBD;

import java.sql.*;

public class EjemploJDBC_05_Conexion {

    public static void main(String[] args) {

        try (
                Connection conn = ConexionBD.getInstance();
                Statement stmt = conn.createStatement();
                ResultSet rs = stmt.executeQuery("SELECT * FROM productos")
                )
        {
            while (rs.next()){
                System.out.print(rs.getInt("id"));
                System.out.print(" | ");
                System.out.print(rs.getString("nombre"));
                System.out.print(" | ");
                System.out.print(rs.getInt("precio"));
                System.out.print(" | ");
                System.out.println(rs.getDate("fecha_registro"));
            }
        } catch (SQLException e) {
            throw new RuntimeException(e);
        }
    }
}
```

## 9. La interface Repositorio

## 10. Implementando la clase Repositorio

## 11. Implementando la clase Repositorio parte 2

## 12. Implementando la clase Repositorio parte 3 el CRUD

## 13. La clase Repositorio parte 4 probando el CRUD

## 14. Relaciones de tablas creando esquema DDL

## 15. Relaciones de objetos del modelo o DTO

## 16. Una conexión por sentencia u operación

## 17. Introducción Pool de conexiones

## 18. Implementando pool de conexiones

## 19. Introducción Transacciones JDBC

## 20. Ejemplo Transacciones Singleton

## 21. Ejemplo Transacciones Singleton parte 2

## 22. Ejemplo Transacciones con pool de conexiones

## 23. Ejemplo Transacciones con pool de conexiones parte 2

## 24. Ejemplo Transacciones con pool de conexiones parte 3 (obtener último insert id)

## 25. Ejemplo Transacciones con pool de conexiones parte 4

## 26. Agregando la interface Service y su clase de implementación transaccional

## 27. Implementando los metodos de la clase Service

## 28. Utilizando la clase Service en la clase de ejemplo con el main

## 29. Descargar Código Fuente

