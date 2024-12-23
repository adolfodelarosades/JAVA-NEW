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

## 9. Clase de Modelo y la interface Repositorio

La Clase de Modelo representa los datos de la tabla, la tabla Producto con sus atributos:

<img width="774" alt="image" src="https://github.com/user-attachments/assets/136aab1d-7866-416d-a545-222a0b37386c">

Mapearemos cada atributo con cada campo de la tabla, lo que nos permitira en ver de trabajar con registros, con el ResultSet, nos permitira trabajar más orientado a objetos. Una clase con métodos getters y setters, constructores, etc.

Existe el patron de diseño **DAO Data Access Object - Objeto de Acceso a Datos**, el que se encarga de acceder a los datos, implementar un CRUD. El DAO se refiere a una abstracción de los datos de la percistencia, es decir a todo lo que es la BD, tablas, campos, etc.

Alternativamente al uso de los DAOs existen los **Repository** el cual es una semantica, es una abstracción de una colección de objetos, como si fuera el API Collection por ejemplo para añadir, buscar, eliminar objetos en la lista. Nos permite implementar, Altas, Bajas, Modificaciones de una colección de objetos.

El acceso a los datos por lo tanto lo podemos implementar a través del patrón DAO o del patrón Repository.

#### 💻

#### Clase del Modelo - Producto 

<img width="404" alt="image" src="https://github.com/user-attachments/assets/7e207f26-87cf-4ae9-b896-f5352f650953">

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/8452e34f-3780-41d4-ac76-60a6773f6450">

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/e9b29a60-b67c-4412-a507-efa1aa60f30e">


**```Producto.java```**

```java
package org.example.model;

import java.util.Date;

public class Producto {

    private Long id;
    private String nombre;
    private Integer precio;
    private Date fechaRegistro;

    public Producto() {
    }

    public Producto(Long id, String nombre, Integer precio, Date fechaRegistro) {
        this.id = id;
        this.nombre = nombre;
        this.precio = precio;
        this.fechaRegistro = fechaRegistro;
    }

    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public Integer getPrecio() {
        return precio;
    }

    public void setPrecio(Integer precio) {
        this.precio = precio;
    }

    public Date getFechaRegistro() {
        return fechaRegistro;
    }

    public void setFechaRegistro(Date fechaRegistro) {
        this.fechaRegistro = fechaRegistro;
    }
}
```

#### Repository

<img width="401" alt="image" src="https://github.com/user-attachments/assets/8699c8c9-6447-4d2d-8bb4-0ca77973c7f2">

Un repositorio consta de la Interface y su implementación. En la Interface solo defimos la firma de los métodos y en la implementación justo hacemos eso, implementar cada método.

En nuestro caso podemos tener un Repositorio para Producto, pero lo que vamos hacer es generar una Interface Generica para ver si más adelante la podemos reutilzar.

<img width="1034" alt="image" src="https://github.com/user-attachments/assets/158b799c-2eae-4617-845a-e48ded973cbc">

Contamos con cuatro métodos que nos van a permitir:

* Recuperar todos los registros
* Recuperar un registro por su ID
* Crear o Modificar un nuevo registro
* Eliminar un registro.

**```Repositorio.java```**

```java
package org.example.repository;

import java.util.List;

public interface Repositorio<T> {

    List<T> getFindAll();

    T getById(Long id);

    void save(T t);

    void delete(Long id);
}
```

Existe otro patrón de diseño llamado **DTO Data Transfer Object** se utiliza mucho en aplicaciones distribuidas, con EJBs, con API Rest, son clases con atributos y métodos getters y setters, cuando necesitamos distribuir un API Rest podemos hacerlo sin transferir todos los campos del DTO, podemos colocar solo los que nos importe transferir, lo que nos permite aligerar la respuesta. Para eso usamos los DTOs para transferir los datos del Entity o del POJO según los requerimientos, según la implementación, pero también podriamos distribuir el objeto completo con todas sus relaciones.

## 10. Implementando la clase Repositorio

#### 💻

En la siguiente clase vamos a implementar cada uno de los métodos de la interface. 

Lo primero que hacemos es crear un método privado que nos permite generar una conexión a la BD.

A continuación vamos a implementar el primer método de la interface `getFindAll()`. En este método solo definimos en el try con recursos las sentencias `Statement` y `ResultSet` que se autocerraran cuando termine el try, la conexión no la pasamos ya que se necesita abierta para su uso en los 3 restantes métodos. La conexión se debe cerrar al final de la aplicación, al final del método `main`, pero también podríamos añadirla en el try con recursos y lo que estaríamos haciendo es abrir y cerrar una conexión en cada uno de nuestros métodos, depende de como queramos hacer la implementación.

Nota: Un `java.sql.Date` es un `java.util.Date` por eso se puede settear en la propiedad `setFechaRegistro`.

<img width="1134" alt="image" src="https://github.com/user-attachments/assets/c991ea8a-aec4-4884-8492-b326a5144104">

**```ProductoRepositirioImpl.java```**

```java
package org.example.repository;

import org.example.model.Producto;
import org.example.util.ConexionBD;

import java.sql.Connection;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.ArrayList;
import java.util.List;

public class ProductoRepositirioImpl implements Repositorio<Producto>{

    private Connection getConnection() throws SQLException {
        return ConexionBD.getInstance();
    }

    @Override
    public List<Producto> getFindAll() {
        List<Producto> productos = new ArrayList<>();

        try(
                Statement stmt = getConnection().createStatement();
                ResultSet rs = stmt.executeQuery("SELECT * FROM productos")
                ){
            while (rs.next()){
                Producto p = new Producto();
                p.setId(rs.getLong("id"));
                p.setNombre(rs.getString("nombre"));
                p.setPrecio(rs.getInt("precio"));
                p.setFechaRegistro(rs.getDate("fecha_registro"));
                productos.add(p);
            }

        } catch (SQLException e) {
            throw new RuntimeException(e);
        }
        return productos;
    }

    @Override
    public Producto getById(Long id) {
        return null;
    }

    @Override
    public void save(Producto producto) {

    }

    @Override
    public void delete(Long id) {

    }
}
```

Vamos a usar el método `getFindAll()` en la siguiente clase principal:

**```EjemploJDBC_06_Repositorio.java```**

Observese que aquí si que metemos en el try con recursos la conexión, esto lo hacemos para que al terminar la aplicación se autocierre dicha conexión.

<img width="1122" alt="image" src="https://github.com/user-attachments/assets/8b4c66ff-e3ab-48b8-82b6-e96264cf3529">

**`EjemploJDBC_06_Repositorio.java`**

```java
package org.example;

import org.example.model.Producto;
import org.example.repository.ProductoRepositirioImpl;
import org.example.repository.Repositorio;
import org.example.util.ConexionBD;

import java.sql.Connection;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

public class EjemploJDBC_06_Repositorio {

    public static void main(String[] args) {

        try (Connection conn = ConexionBD.getInstance()){
            Repositorio<Producto> repositorio = new ProductoRepositirioImpl();
            repositorio.getFindAll().forEach(p -> System.out.println(p.getNombre()));
        } catch (SQLException e) {
            throw new RuntimeException(e);
        }
    }
}
```


<img width="422" alt="image" src="https://github.com/user-attachments/assets/9eea1020-4f90-40e6-9608-955b7737c8b3">

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/52751500-b74e-4a15-b916-fef1f0f97300">

## 11. Implementando la clase Repositorio parte 2

Vamos a implementar el método `getById(Long id)`, el cual regresa un Producto si lo encuentra de acuerdo al id que se le pase y si no lo encuentra retornara un nulo.

En este caso no usaremos un `Statement` sino un `PreparedStatement` una sentencia preparada ya que necesita un `WHERE` y el paso de un parámetro. Para pasar el parametro necesitamos settear el valor del parámetro indicando un indice y el valor que queremos pasar. Una vez hecho esto necesitamos ejecutar el `PreparedStatement`. Al ejecutar el `PreparedStatement` retorna un cursor, el `ResultSet`. En teoría el `ResultSet` solo retornara un valor por eso usamos un `if` en lugar de un `while`. Dentro del `if` setteamos lo que que nos regresa el `ResultSet` dentro del `Producto`, que es lo que retornara nuestro método.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/19880196-9a10-4ebd-9fbe-b10b8dcd3b80">

**`ProductoRepositirioImpl.java`**

```java
package org.example.repository;

import org.example.model.Producto;
import org.example.util.ConexionBD;

import java.sql.*;
import java.util.ArrayList;
import java.util.List;

public class ProductoRepositirioImpl implements Repositorio<Producto>{

    private Connection getConnection() throws SQLException {
        return ConexionBD.getInstance();
    }

    @Override
    public List<Producto> getFindAll() {
        List<Producto> productos = new ArrayList<>();

        try(
                Statement stmt = getConnection().createStatement();
                ResultSet rs = stmt.executeQuery("SELECT * FROM productos")
                ){
            while (rs.next()){
                Producto p = new Producto();
                p.setId(rs.getLong("id"));
                p.setNombre(rs.getString("nombre"));
                p.setPrecio(rs.getInt("precio"));
                p.setFechaRegistro(rs.getDate("fecha_registro"));
                productos.add(p);
            }

        } catch (SQLException e) {
            throw new RuntimeException(e);
        }
        return productos;
    }

    @Override
    public Producto getById(Long id) {
        Producto producto = null;

        try(PreparedStatement prStmt = getConnection()
                .prepareStatement("SELECT * FROM productos WHERE id = ?")) {
            prStmt.setLong(1, id);
            ResultSet rs = prStmt.executeQuery();
            if(rs.next()){
                producto= new Producto();
                producto.setId(rs.getLong("id"));
                producto.setNombre(rs.getString("nombre"));
                producto.setPrecio(rs.getInt("precio"));
                producto.setFechaRegistro(rs.getDate("fecha_registro"));
            }
            rs.close();
        } catch (SQLException e) {
            throw new RuntimeException(e);
        }

        return producto;
    }

    @Override
    public void save(Producto producto) {

    }

    @Override
    public void delete(Long id) {

    }
}

```

Vamos a crear la clase **`EjemploJDBC_06_Repositorio_02.java`** para usar el método `getById(Long id)`.

<img width="1074" alt="image" src="https://github.com/user-attachments/assets/63844002-fd51-4d9e-922f-2f545066ab3b">

**`EjemploJDBC_06_Repositorio_02.java`**

```java
package org.example;

import org.example.model.Producto;
import org.example.repository.ProductoRepositirioImpl;
import org.example.repository.Repositorio;
import org.example.util.ConexionBD;

import java.sql.Connection;
import java.sql.SQLException;

public class EjemploJDBC_06_Repositorio_02 {

    public static void main(String[] args) {

        try (Connection conn = ConexionBD.getInstance()){
            Repositorio<Producto> repositorio = new ProductoRepositirioImpl();
            Producto producto = repositorio.getById(2L);
            System.out.println(producto.getId() + " | "
                             + producto.getNombre() + " | "
                             + producto.getPrecio() + " | "
                             + producto.getFechaRegistro());
        } catch (SQLException e) {
            throw new RuntimeException(e);
        }
    }
}
```

Al ejecutar la clase tenemos:

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/9441201b-93cc-4cff-98b6-2d8d52396755">

Hay varias cosas a observar en estas clases:

* En el método `getById(Long id)` en el try con recursos que usamos no estamos incluyendo el `ResultSet` solo tenemos el `PreparedStatement`, esto es por que necesitamos indicarle el valor del parámetro que necesita el `PreparedStatement` y posteriormente ejecutarlo y asignar el resultado al `ResultSet`, como no se ha incluido en el try con recursos debemos cerrarlo manualmente.
* Por otro lado estamos duplicando un grupo de sentencias, en los dos métodos implementados hasta ahora. Es la parte donde setteamos los resultados del `ResultSet` al `Producto`, podemos refactorizar el código para optimizarlo. Podemos crear un método para mappear del `ResultSet` al `Producto`. Podemos usar la potencia de IntelliJ IDEA para crear un método a partir de las sentencias marcadas.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/3f56ea1c-15da-41f0-becd-76923a7428de">

<img width="1455" alt="image" src="https://github.com/user-attachments/assets/a9e0b15d-615f-4d0b-892b-845d53afffc8">

Vamos a cambiar el nombre del método y moverlo al final de la clase. Y 






  



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

