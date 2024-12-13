# 02 Introducción a ChatGPT Gen AI

* ¿Qué es ChatGPT? 04:34
* IA generativa (Gen AI) para programadores 06:53
* Configurar una cuenta con ChatGPT 02:39
* Cómo utilizar ChatGPT Gen AI 06:08
* ChatGPT para tus tareas diarias 05:09

## ¿Qué es ChatGPT? 04:34

Bienvenidos a esta lección, aprenderán qué es ChatGPT.

<img width="1493" alt="image" src="https://github.com/user-attachments/assets/acbb3913-f143-4f72-a27a-ccebbb925353">

Intentaremos averiguarlo con Google. Simplemente haga clic en Google ChatGPT para saber qué es lo que nos gustaría saber.

<img width="1487" alt="image" src="https://github.com/user-attachments/assets/9d7bbaf4-3e5d-420a-842d-77eef9de99dc">

Chat GPT es un chatbot desarrollado por OpenAI y lanzado el 30 de noviembre de 2022.

<img width="480" alt="image" src="https://github.com/user-attachments/assets/08e3c8bc-8ad1-4f33-9b11-d8a4e0db8c57">

En pocas palabras, podemos decir que es un gran modelo de lenguaje.

Sí, es una ayuda para los desarrolladores, independientemente de lo que vean, me gustaría verificar la [introducción de GPT aquí](https://openai.com/index/chatgpt/).

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/31b31126-e51b-4105-9428-460bbeb39287">

Hemos entrenado un modelo llamado chat GPT que interactúa de forma conversacional. La forma conversacional es que el usuario utiliza esta herramienta de IA para hacer las consultas. También podemos decir que estas consultas son como una solicitud del requisito de la consulta. Tenemos que ingresar como un cuadro de chat.

Y estas herramientas de IA abiertas de chat GPT, también llamadas herramientas de IA generativas, nos brindarán soluciones complejas, desafiantes y a problemas que brindarán con respecto al texto. Entonces, al usar este chat GPT, podemos tener maravillas creativas como desarrolladores.

Entonces, en este curso, vamos a presentarles en detalle, les explicaré un proceso paso a paso para hacer un maestro en los fundamentos de Java. Entonces, usando este mensaje, vamos a llevar un nivel como un proceso paso a paso para hacer un aprendizaje de siguiente nivel. Entonces, la IA ayuda a construir un gran código y a conocer los fundamentos a fondo.

Sí, los desarrolladores deben comprender muy claramente un proceso paso a paso, cómo construir y cómo escribir un código fuente en Java.

Entonces, veamos cómo abrir la IA.

### Como probar GPT.

[Aquí está](https://chatgpt.com/), cómo usar ChatGPT **Try ChatGPT***

<img width="753" alt="image" src="https://github.com/user-attachments/assets/ac6cb753-196e-41f4-91bf-a645ba4c2a57">

<img width="1509" alt="image" src="https://github.com/user-attachments/assets/3c3083a4-b8c1-48c9-b8d7-ba5f952b816b">

Veamos si hago clic en Probar ChatGPT, que es como un resumen de los artículos.

Hay muchos ejemplos.

Les mostraré algunos y les demostraré cómo podemos interactuar con este chat, GPT y las actividades diarias y preparar currículums y crear programas asombrosos.

Por ejemplo, si desea aprender y escribir algo como, ya sabe, un programa de calculadora usando

Java, si especifica escribir un código fuente en Java para la calculadora, un programa de calculadora básico simple, o encontrar un patrón o algo así.

La serie de Fibonacci en Java.

Entonces, ¿qué lógica desea construir, cómo lo desea?

¿Qué piensa?

Sí, puede obtener un código fuente completo usando ChatGPT.

Entonces, cuándo utiliza y cuándo puede usar este código fuente en su misión informática o en su propio proyecto.

Si tiene conocimientos básicos, primero debe comprender los conceptos básicos para aprender y aplicar los conceptos básicos para preparar programas simples en Java.

Luego, ChatGPT creará un código fuente que podrás aplicar fácilmente a tus propios proyectos.

También me entusiasma más empezar a aplicar un proceso paso a paso, entendiendo qué es la IA generativa y creando una cuenta GPT y solicitando actividades.

En las próximas clases veremos un proceso paso a paso para obtener una respuesta de este GPT.

### Ejemplo usando ChatGPT

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/10ff3be7-d50a-4fda-83d3-811c37048148">

```java
import java.util.Scanner;

public class Calculadora {
    
    // Método para sumar
    public static double sumar(double num1, double num2) {
        return num1 + num2;
    }

    // Método para restar
    public static double restar(double num1, double num2) {
        return num1 - num2;
    }

    // Método para multiplicar
    public static double multiplicar(double num1, double num2) {
        return num1 * num2;
    }

    // Método para dividir
    public static double dividir(double num1, double num2) {
        if (num2 == 0) {
            System.out.println("Error: No se puede dividir entre cero.");
            return Double.NaN; // Retorna NaN si hay intento de dividir por cero
        }
        return num1 / num2;
    }

    // Método principal
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        while (true) {
            System.out.println("Calculadora en Java");
            System.out.println("Seleccione una operación:");
            System.out.println("1. Sumar");
            System.out.println("2. Restar");
            System.out.println("3. Multiplicar");
            System.out.println("4. Dividir");
            System.out.println("5. Salir");

            int opcion = scanner.nextInt();

            if (opcion == 5) {
                System.out.println("Gracias por usar la calculadora. ¡Hasta luego!");
                break; // Termina el programa
            }

            System.out.print("Introduce el primer número: ");
            double num1 = scanner.nextDouble();

            System.out.print("Introduce el segundo número: ");
            double num2 = scanner.nextDouble();

            double resultado = 0;

            switch (opcion) {
                case 1:
                    resultado = sumar(num1, num2);
                    System.out.println("Resultado: " + resultado);
                    break;
                case 2:
                    resultado = restar(num1, num2);
                    System.out.println("Resultado: " + resultado);
                    break;
                case 3:
                    resultado = multiplicar(num1, num2);
                    System.out.println("Resultado: " + resultado);
                    break;
                case 4:
                    resultado = dividir(num1, num2);
                    if (!Double.isNaN(resultado)) {
                        System.out.println("Resultado: " + resultado);
                    }
                    break;
                default:
                    System.out.println("Opción no válida. Por favor, elige una opción válida.");
                    break;
            }
        }

        scanner.close();
    }
}
```

¡Claro! A continuación, te proporcionaré un ejemplo sencillo de cómo crear una calculadora básica en Java que permita realizar operaciones como suma, resta, multiplicación y división.

### Código de la Calculadora en Java

```java
import java.util.Scanner;

public class Calculadora {
    
    // Método para sumar
    public static double sumar(double num1, double num2) {
        return num1 + num2;
    }

    // Método para restar
    public static double restar(double num1, double num2) {
        return num1 - num2;
    }

    // Método para multiplicar
    public static double multiplicar(double num1, double num2) {
        return num1 * num2;
    }

    // Método para dividir
    public static double dividir(double num1, double num2) {
        if (num2 == 0) {
            System.out.println("Error: No se puede dividir entre cero.");
            return Double.NaN; // Retorna NaN si hay intento de dividir por cero
        }
        return num1 / num2;
    }

    // Método principal
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        while (true) {
            System.out.println("Calculadora en Java");
            System.out.println("Seleccione una operación:");
            System.out.println("1. Sumar");
            System.out.println("2. Restar");
            System.out.println("3. Multiplicar");
            System.out.println("4. Dividir");
            System.out.println("5. Salir");

            int opcion = scanner.nextInt();

            if (opcion == 5) {
                System.out.println("Gracias por usar la calculadora. ¡Hasta luego!");
                break; // Termina el programa
            }

            System.out.print("Introduce el primer número: ");
            double num1 = scanner.nextDouble();

            System.out.print("Introduce el segundo número: ");
            double num2 = scanner.nextDouble();

            double resultado = 0;

            switch (opcion) {
                case 1:
                    resultado = sumar(num1, num2);
                    System.out.println("Resultado: " + resultado);
                    break;
                case 2:
                    resultado = restar(num1, num2);
                    System.out.println("Resultado: " + resultado);
                    break;
                case 3:
                    resultado = multiplicar(num1, num2);
                    System.out.println("Resultado: " + resultado);
                    break;
                case 4:
                    resultado = dividir(num1, num2);
                    if (!Double.isNaN(resultado)) {
                        System.out.println("Resultado: " + resultado);
                    }
                    break;
                default:
                    System.out.println("Opción no válida. Por favor, elige una opción válida.");
                    break;
            }
        }

        scanner.close();
    }
}
```

### Explicación del código:

1. **Métodos de operaciones**: 
   - `sumar()`, `restar()`, `multiplicar()` y `dividir()` realizan las operaciones correspondientes. La división incluye una comprobación de error para evitar la división por cero.
   
2. **Método `main`**:
   - Se utiliza un bucle `while(true)` que permite seguir usando la calculadora hasta que el usuario seleccione la opción de salir (opción 5).
   - El usuario selecciona la operación deseada e ingresa los dos números para realizar la operación.
   - Después de realizar la operación seleccionada, se muestra el resultado.

3. **Validación de entrada**: Si el usuario selecciona la opción de división por cero, se maneja el error mostrando un mensaje adecuado.

4. **Cierre del programa**: Cuando el usuario elige la opción "Salir", el programa termina.

### Ejemplo de ejecución:
```
Calculadora en Java
Seleccione una operación:
1. Sumar
2. Restar
3. Multiplicar
4. Dividir
5. Salir
1
Introduce el primer número: 5
Introduce el segundo número: 3
Resultado: 8.0
```

Este es un ejemplo básico de cómo puedes hacer una calculadora en Java. Si necesitas añadir más funcionalidades (como exponentes, raíces cuadradas, etc.), puedo ayudarte a expandir este código. ¿Te gustaría hacer alguna mejora o agregar algo más?

<img width="1504" alt="image" src="https://github.com/user-attachments/assets/f0b23e5f-2383-409d-b202-b9928e098611">

## IA generativa (Gen AI) para programadores 06:53
## Configurar una cuenta con ChatGPT 02:39
## Cómo utilizar ChatGPT Gen AI 06:08
## ChatGPT para tus tareas diarias 05:09
