# 2 Creación e implementación de su primera página web

Este capítulo cubre

* Comprender el proceso de creación y despliegue de una página web
* Uso de un prompt de ChatGPT para generar una página web completa
* Copiar el código de la página web generada
* Guardar el código en un archivo HTML
* Obtener su archivo de página web en la web

Puede que todavía parezca demasiado bueno para ser verdad que ChatGPT te ayude a crear un sitio web completamente funcional sin tener que aprender ningún código de desarrollo web. Si sigues siendo escéptico, te entiendo: incluso sabiendo un poco sobre cómo funciona ChatGPT, todavía hay un innegable tufillo a magia en toda la empresa. Después de todo, no es como si le estuvieras pidiendo a ChatGPT que te cuente un chiste o que escriba un haiku ensalzando el valor nutricional del colinabo. No, estamos hablando de todo el código necesario para crear una página web que realmente haga algo semi-útil. Es una petición compleja desde cualquier punto de vista, por lo que cualquier escepticismo restante que tengas está totalmente justificado.

En este capítulo, mi objetivo es mostrarte que es posible crear una página web con la ayuda de ChatGPT. No voy a hacerlo explorando más la teoría de ChatGPT. No, ya hemos hablado bastante de eso. En su lugar, te mostraré un ejemplo completo en el que convenzo a ChatGPT para que cree el código para una página web funcional que, al final del capítulo, tendrá su propio hogar en la web. Para lograrlo en un solo capítulo, la página web será, necesariamente, extremadamente simple, pero funcionará e incluso proporcionará un poco de diversión (dependiendo, como verás, de tu gusto por los juegos de palabras).

## 2.1 Comprender el proceso

Para crear la página web funcional de este capítulo, voy a utilizar el ciclo prompt-copy-save-deploy(solicitar-copiar-guardar-implementar) que presenté en el capítulo 1 (consulte la figura 2.1):

1. Prompt ChatGPT para que genere el código de la página web.
2. Copiar el código resultante.
3. Pegue el código en un editor de texto y luego guárdelo como un archivo HTML.
4. Deploy el archivo HTML en un servidor web.

<img width="921" alt="image" src="https://github.com/user-attachments/assets/214d7c7a-9c5b-467e-9554-95e911d06a9d">

**Figura 2.1 El ciclo de prompt-copy-save-deploy que utilizará en este capítulo**

Las secciones del resto de este capítulo amplían cada uno de estos pasos.

## 2.2 Cómo solicitar a ChatGPT que genere el código de su página web

Para comenzar, primero debe tener ChatGPT en pantalla. Tiene las siguientes opciones:

* Si no tiene una cuenta OpenAI, vaya a https://chat.openai.com para usar GPT-3.5 como modelo.
* Si tiene una cuenta OpenAI pero no tiene una suscripción a ChatGPT Plus, vaya a https://chat.openai.com para usar GPT-3.5 como modelo.
* Si tiene una suscripción a ChatGPT Plus, vaya a https://chat.openai.com y luego haga clic en el botón GPT-4.
* Si prefiere utilizar Bing Copilot, vaya a https://bing.com, haga clic en Copilot y luego haga clic en el estilo de conversación Preciso.
* Si tiene una cuenta Microsoft, vaya a https://copilot.microsoft.com y haga clic en el estilo de conversación preciso.

Para mi propia inspiración, utilicé la aplicación ChatGPT con GPT-4 como modelo, como se muestra en la figura 2.2.

<img width="919" alt="image" src="https://github.com/user-attachments/assets/7be52624-e945-4f7f-b8a3-647511cc065b">

**Figura 2.2 La aplicación ChatGPT con GPT-4 seleccionado como modelo de lenguaje**

Ahora que ChatGPT está listo para hacer lo que le pides, el siguiente paso es darle al modelo un mensaje para que genere algún código de página web. Uno de los puntos que quiero destacar en este capítulo es que es posible lograr que ChatGPT muestre el código para una página web funcional con un solo mensaje. Para lograrlo, tenemos que simplificar mucho las cosas, por lo que no puede ser una página complicada y multifunción con un montón de funciones.

Sin embargo, no tiene por qué ser una página de “¡Hola mundo!” de mala calidad. En general, si tienes una idea para una página sencilla, solo tienes que pedirle a ChatGPT que genere el código para la página e incluya una descripción de lo que quieres. Esa descripción variará según la idea, pero es posible que quieras incluir algunos o todos los siguientes elementos:

* **Goal - Objetivo**: lo que desea que ChatGPT genere (en este caso, una página web)
* **Data - Datos**: los datos que desea que ChatGPT utilice, si corresponde
* **Action - Acción**: lo que desea que haga la página web, en general o con los datos que especificó
* **Interface - Interfaz**: cómo desea que el usuario inicie la acción o interactúe de otro modo con la página

Aquí está el mensaje para la página que quiero (consulte la figura 2.3):

<img width="905" alt="image" src="https://github.com/user-attachments/assets/decc3980-0bce-4752-8481-f190a9369537">

```text
Create web page code that stores 50 puns and displays a random pun each time the user clicks a button.
```

```text
Crea un código de página web que almacene 50 juegos de palabras y muestre un juego de palabras aleatorio cada vez que el usuario haga clic en un botón.
```

<img width="911" alt="image" src="https://github.com/user-attachments/assets/7480b7ef-c7e7-467f-a0be-84ad759ee75f">

**Figura 2.3 La aplicación ChatGPT con mi mensaje listo para enviar**

Así es como este mensaje encaja en el esquema goal-data-action-interface(objetivo-datos-acción-interfaz):

* **Create web page code**: Esta parte del mensaje le dice a ChatGPT que genere el código para una página web completa.

* **that stores 50 puns**: Le dice a ChatGPT que cree 50 juegos de palabras para usar como datos de la página.

* **and displays a random pun**: Le dice a ChatGPT que seleccione un juego de palabras al azar de los datos.

* **each time the user clicks a button**: Le dice a ChatGPT que proporcione un botón que, cuando se hace clic, muestre otro juego de palabras aleatorio.

Ingrese el mensaje en el cuadro de texto de ChatGPT, haga clic en el ícono ***Send Message*** y espere el resultado.

### 2.2.1 Examen del resultado

El siguiente código muestra la primera respuesta que recibí de ChatGPT (el código que ChatGPT genera para usted puede ser diferente):

```html
<!DOCTYPE html>
<html>
<head>
    <title>Pun Generator</title>                                                    ①   
    <style>
        body {                                                                      ②
            font-family: Arial, sans-serif;                                         ②
        }                                                                           ②
        #displayPun {                                                               ③
            font-size: 24px;                                                        ③
            margin-top: 20px;                                                       ③
        }                                                                           ③
    </style>
</head>
<body>
    <h1>Welcome to Pun Generator!</h1>                                              ④
    
    <button id="generatePun">Generate Pun</button>                                  ⑤
    
    <p id="displayPun"></p>                                                         ⑥
    <script>
        var puns = [                                                                ⑦
            "Time flies like an arrow; fruit flies like a banana.",                 ⑦
            "I used to be a baker because I kneaded dough.",                        ⑦
            "I used to play piano by ear, but now I use my hands.",                 ⑦
            // Add the rest of the 50 puns here...                                  ⑦
        ];    
        document.getElementById("generatePun").
addEventListener("click", function() {                                              ⑧
            var randomPunIndex = Math.floor(Math.random() * puns.length);           ⑧
            document.getElementById("displayPun").innerText = puns[randomPunIndex]; ⑧
        });                                                                         ⑧
    </script>
</body>
</html>
```

① Título de la página

② Aplica la tipografía Arial a la página.

③ Muestra cada juego de palabras en una fuente de 24 píxeles con un margen de 20 píxeles en la parte superior.

④ Encabezado principal de la página

⑤ Botón en el que el usuario hace clic para obtener un nuevo juego de palabras aleatorio

⑥ Sección de la página donde aparece cada juego de palabras aleatorio

⑦ Datos de página (parciales), que son una colección de juegos de palabras

⑧ Código JavaScript que extrae un juego de palabras aleatorio de los datos

Hay tres cosas que tener en cuenta aquí:

* Aunque se trata de una página sencilla, el código en sí es bastante complejo, así que no te preocupes si todo te parece un lenguaje extraño. No necesitas saber cómo funciona este código, solo que funciona (teniendo en cuenta mi tercer punto de esta lista).

* Recuerda que ChatGPT no es determinista, lo que significa que no generará el mismo código cada vez, incluso cuando uses el mismo mensaje. Por lo tanto, si ejecutas mi mensaje en ChatGPT, es muy probable que termines con un código diferente al que ves en el listado 2.1.

* En lugar de crear 50 juegos de palabras, ChatGPT creó solo tres juegos de palabras y luego pasó la pelota:

<img width="886" alt="image" src="https://github.com/user-attachments/assets/c9b97b88-74e7-451e-bbc5-d50fa6aa7ea4">

```text
// Add the rest of the 50 puns here...
```

```text
// Añade el resto de los 50 juegos de palabras aquí...
```

Esto no sucede siempre, pero debes saber que es un comportamiento muy común en ChatGPT. Afortunadamente, no significa que estés estancado. Logré que ChatGPT completara su misión con un simple mensaje:

<img width="909" alt="image" src="https://github.com/user-attachments/assets/99635356-dba0-417f-ad47-35d793eead01">

```text
Can you fill in the rest of the puns for me?
```

```text
¿Puedes completarme el resto de los juegos de palabras?
```

ChatGPT regeneró el código con el conjunto completo de juegos de palabras (aunque tuve que hacer clic en el botón Continuar generando (consulte la figura 2.4) una vez cuando ChatGPT se quedó bloqueado). Esa es una cantidad considerable de datos para generar, por lo que tardó un par de minutos en aparecer el código completo.

<img width="810" alt="image" src="https://github.com/user-attachments/assets/bacf015a-e27f-4b14-ab8a-fa7f39bf3cd3">

**Figura 2.4 Si ChatGPT se bloquea, es posible que tengas que hacer clic en Continuar generando para desbloquearlo.**

### Comprender y personalizar el código (opcional)

Si deseas comprender y/o personalizar el código generado por ChatGPT (esto es totalmente opcional), aquí te dejamos algunas notas:

* **HTML** consta de una colección de elementos denominados etiquetas para especificar objetos de página, como párrafos, encabezados, listas con viñetas y enlaces. La mayoría de las etiquetas HTML son códigos alfabéticos rodeados de corchetes angulares ( `<` y `>`). Por ejemplo, se designa el inicio de un párrafo con la etiqueta `<p>` y el final del párrafo con la etiqueta `</p>`. Como otro ejemplo, el código HTML generado por ChatGPT de la sección anterior incluía la siguiente línea:

<img width="873" alt="image" src="https://github.com/user-attachments/assets/369ebb8f-b927-486c-9e4b-837c4da70bec">

Las etiquetas `<h1>` y `</h1>` marcan un encabezado de primer nivel (consulte el capítulo 3 para obtener más información sobre los encabezados), por lo que, en este caso, el texto `Welcome to Pun Generator!` aparece en la página como dicho encabezado.

* **CSS** consta de una colección de elementos denominados ***properties*** para especificar el estilo aplicado a los objetos de la página. Por ejemplo, la propiedad `font-size` determina el tamaño del texto de un objeto específico, por lo que para establecer el tamaño en `24px`(24 píxeles), se utiliza la siguiente declaración CSS:

<img width="874" alt="image" src="https://github.com/user-attachments/assets/e51ae179-7e2b-4c4e-afa1-ac600ef66f90">

Tenga en cuenta los dos puntos (`:`) después del nombre de la propiedad y el punto y coma (`;`) al final. Las declaraciones CSS se agrupan en reglas, que consisten en el objeto al que se aplican las declaraciones y con esas declaraciones rodeadas por llaves ( `{` y `}` ), como en este ejemplo del código generado por ChatGPT que se mostró anteriormente:

<img width="869" alt="image" src="https://github.com/user-attachments/assets/64a9f702-952a-470b-b3b8-bb5e62589d51">
 
En este ejemplo, `#displayPun` hay una referencia al siguiente elemento en el código HTML:

<img width="869" alt="image" src="https://github.com/user-attachments/assets/c8131a6f-3131-421f-913d-cd4bc1133d18">

* El texto entre las etiquetas `<title>` y `</title>` es el título de la página que aparece en la pestaña del navegador. Puedes editar este texto (pero no alteres las etiquetas).

* Puedes cambiar el tamaño del texto del juego de palabras modificando el valor `font-size`. Sea cual sea el valor que uses, asegúrate de que esté acompañado de `px`(para píxeles).

* El texto entre las etiquetas `<h1>` y `</h1>` es el encabezado de la página principal. Puedes editar este texto (pero no toques las etiquetas).

* El botón en el que hace clic el usuario se especifica mediante la etiqueta `<button>`. El texto que aparece entre esa etiqueta y la etiqueta `</button>` es lo que aparece en el botón. Puedes editar este texto si lo deseas.

* ChatGPT almacena los datos de la página en un objeto de datos especial llamado ***array***. En este caso, cada elemento del array es texto (específicamente, un juego de palabras) rodeado de comillas dobles (`""`) y seguido de una coma. Puede editar, agregar o eliminar elementos del array según sea necesario; solo asegúrese de que cuando haya terminado, cada elemento del array esté rodeado de comillas dobles y seguido de una coma. Además, no elimine los corchetes (`[` y `]`) que inician y finalizan el array.

Antes de pasar al siguiente paso, voy a tomarme un momento para darte algunas otras sugerencias para un sitio web simple de una sola página.

### 2.2.2 Eche un vistazo a algunas otras indicaciones para sitios web de una sola página

Si estás siguiendo este tutorial y quieres crear tu propio sitio web de una sola página con la ayuda de ChatGPT, puedes usar mi sugerencia de la sección anterior o puedes usar tu propia sugerencia si tienes una idea que siempre quisiste probar. Si no estás seguro de qué hacer, aquí tienes algunas sugerencias:

**ADVERTENCIA** ChatGPT tiene una especie de "memoria" para lo que solicitaste y para lo que generó anteriormente en la misma sesión de chat. Antes de intentar cualquiera de las siguientes solicitudes, asegúrate de iniciar un nuevo chat para que los resultados de ChatGPT no se vean afectados por nada anterior en la sesión.

* “Crear un código de página web que muestre una lista de diez X cosas para hacer en Y” (donde X es un adjetivo, como divertido o interesante, e Y es el nombre de una ciudad o un barrio). Ejemplo:

<img width="883" alt="image" src="https://github.com/user-attachments/assets/f3e5e2b6-911e-43a0-9d28-386fb2ec73e0">

```text
Create web page code that displays a list of ten entertaining things to do in Miami’s South Beach area.
```

```text
Crea un código de página web que muestre una lista de diez cosas entretenidas para hacer en el área de South Beach de Miami.
```

* “Generar el código para una página web que proporcione una receta para preparar X” (donde X es una cena, postre u otro tipo de plato que se pueda cocinar desde cero). Ejemplo:

<img width="889" alt="image" src="https://github.com/user-attachments/assets/fc825199-ada4-4c77-96eb-935ce556e668">

```text
Generate the code for a web page that provides a recipe for making panna cotta.
```

```text
Generar el código para una página web que proporcione una receta para hacer panna cotta.
```

* “Proporcionar un código de página web que enumere los pasos necesarios para X” (donde X es un proyecto, un trabajo de reparación, una tarea de mantenimiento u otra tarea). Ejemplo:

<img width="884" alt="image" src="https://github.com/user-attachments/assets/c0f5251d-3a2f-41c3-b691-4a1c4d8ebd69">

```text
Provide web page code that lists the steps required to replace a bathroom faucet.
```

```text
Proporciona el código de la página web que enumera los pasos necesarios para reemplazar un grifo del baño.
```

* “Crear código de página web que explique cómo funciona X” (donde X es una máquina, un dispositivo, un principio científico o, en realidad, cualquier cosa). Ejemplo:

<img width="881" alt="image" src="https://github.com/user-attachments/assets/c72e6b61-ac44-4a8e-affc-3bc61c528686">

```text
Create web page code that explains how a hologram works.
```

```text
Crear código de página web que explique cómo funciona un holograma.
```

* “Generar el código para una página web que almacena X y muestra una Y aleatoria cuando el usuario hace clic en un botón” (donde X son algunos datos e Y son los datos combinados de alguna manera). Ejemplo:

<img width="889" alt="image" src="https://github.com/user-attachments/assets/67d80f11-4d18-4de0-a9fe-4fe202215724">

```text
Generate the code for a web page that stores a dozen each of the following: names, verbs, colors, adjectives, and nouns. When the user clicks a button, the code should assemble and display a random sentence that uses the template "Name verb the color, adjective noun."
```

```text
Generar el código para una página web que almacene una docena de cada uno de los siguientes: nombres, verbos, colores, adjetivos y sustantivos. Cuando el usuario haga clic en un botón, el código debe ensamblar y mostrar una oración aleatoria que utilice la plantilla "Nombre verbo el color, adjetivo sustantivo".
```

* “Proporcione un código de página web que muestre X en una lista y almacene una Y asociada con cada X. Cuando el usuario elige X de la lista, la página muestra la Y asociada” (donde X podría ser una palabra, persona u objeto e Y podría ser un poema, una biografía o una descripción).

<img width="881" alt="image" src="https://github.com/user-attachments/assets/6cf78e0b-c8f0-4a96-ad55-d39c8f77d5a8">

```text
Provide web page code that displays six rarely used adjectives in a dropdown list and stores a limerick associated with each adjective. When the user chooses an adjective from the list, the page displays the associated limerick.
```

```text
Proporcionar un código de página web que muestre seis adjetivos poco utilizados en una lista desplegable y almacene un poema asociado con cada adjetivo. Cuando el usuario elige un adjetivo de la lista, la página muestra el poema asociado.
```

Siéntete libre de utilizar los mensajes de ejemplo tal como están o personalizándolos para adaptarlos a la página que desees.

## 2.3 Copiar el código de la página web de ChatGPT

Una vez que ChatGPT haya terminado de generar el código, el siguiente paso es copiarlo. La forma de copiar el código generado depende de si estás usando la aplicación ChatGPT, Bing Copilot o la barra lateral de Copilot en Microsoft Edge. Cada interfaz ofrece una función Copiar código en forma de icono o botón. Para conocer todos los detalles sobre cómo copiar código en cada interfaz, consulta el apéndice A. Si, como yo, estás usando la aplicación ChatGPT, el código aparece en una ventana de código HTML independiente que tiene un botón Copiar código en la esquina superior derecha, como se muestra en la figura 2.5.

<img width="786" alt="image" src="https://github.com/user-attachments/assets/2fb23cfc-94be-4f58-a221-3d545ff510d2">

**Figura 2.5 Para copiar el código generado en la aplicación ChatGPT, haga clic en Copiar código en la esquina superior derecha de la ventana de código.**

El código copiado ahora se encuentra en el Portapapeles de su computadora, que es un área de memoria especial que almacena los datos copiados más recientemente. Para evitar que el código copiado se sobrescriba en el Portapapeles, asegúrese de pasar al siguiente paso antes de hacer cualquier otra cosa en su computadora (especialmente copiar o cortar cualquier otro dato).

### 2.3.1 Guardar el código de la página web en un archivo HTML

Ahora que ha copiado el código de la página web generada por ChatGPT, el siguiente paso es pegar el código copiado en un archivo de texto y luego guardar ese documento como un archivo HTML. Antes de comenzar, utilice el Explorador de archivos (Windows) o Finder (macOS) para crear una subcarpeta para almacenar todos sus proyectos web. Por ejemplo, puede crear una carpeta llamada `sites` o `public_html` en la carpeta `Documentos` de su cuenta de usuario.

Una vez hecho esto, estos son los pasos a seguir para guardar el código ChatGPT copiado en un archivo HTML:

1. Abra su editor de texto.

2. Inicia un nuevo archivo de texto. En la mayoría de los editores de texto, elige ***File > New*** (o, según la aplicación, es posible que tengas que elegir un comando diferente, como ***New File***, ***New Text File+** o ***New Document***). También puedes presionar `Ctrl-N` (en Windows) o `Cmd-N` (macOS).

3. Seleccione ***Edit > Paste*** para pegar el código copiado en el nuevo archivo de texto. También puede presionar `Ctrl+V` (en Windows) o `Cmd+V` (macOS).

4. Seleccione ***File > Save***. También puede presionar `Ctrl+S` (en Windows) o `Cmd+S` (macOS). La aplicación muestra el cuadro de diálogo **Save As**.

5. Navega a la carpeta que creaste anteriormente (la que se llama `sites` o `public_html` o como sea) para almacenar tus proyectos web.

6. Haga clic en el botón ***New Folder*** y, a continuación, introduzca un nombre para la carpeta. En la siguiente sección, subirá esta carpeta a la Web, por lo que el nombre que utilice debe constar únicamente de letras minúsculas, números, guiones (-) y/o guiones bajos (_). No se permiten espacios.

7. Para el nombre del archivo, escriba `index.html`.

8. Haga clic en ***Save***. La aplicación guarda su archivo HTML. La figura 2.6 muestra mi código Pun Generator guardado como archivo HTML.

<img width="907" alt="image" src="https://github.com/user-attachments/assets/647d0d3b-fead-4ef3-ae0d-27583be187f1">

**Figura 2.6 El código generado por ChatGPT guardado como un archivo HTML**

Cerca de la parte superior de la figura 2.6, observe que mi editor de texto muestra la ruta del archivo HTML:

<img width="910" alt="image" src="https://github.com/user-attachments/assets/8df2ac69-6611-469c-889d-58afcdcdf113">

Esta ruta significa que en la carpeta Documentos de mi cuenta de usuario, creé una subcarpeta llamada `public_html` para almacenar todos mis sitios web. Siguiendo los pasos anteriores, primero navegué hasta `public_html`, creé la nueva subcarpeta `pun-generator` y luego guardé el código como `index.html` en esa nueva carpeta.

Ahora está listo para probar su página en un navegador web.

## 2.4 Probar su página web en el navegador

Una vez que el código de su página web esté guardado en un archivo en su computadora, siempre es una buena idea realizar una revisión rápida de la página antes de implementarla. La forma más fácil de probar una página web es abrir el archivo HTML en su navegador web favorito. Estos son los pasos a seguir:

1. En su navegador web, muestre el cuadro de diálogo Open:

   1. Navegador web de Windows: presione `Ctrl-O`.

   2. Navegador web de Mac: seleccione ***File > Open File*** o presione `Cmd-O`.

2. En el cuadro de diálogo Open, navegue hasta la carpeta donde almacenó el archivo HTML en la sección anterior.

3. Seleccione el archivo HTML.

4. Haga clic en Open.

El navegador web abre el archivo HTML y muestra la página web de acuerdo con las etiquetas HTML y las propiedades CSS.

Abrir la página web desde tu computadora es una excelente opción para probarla, pero si quieres verla en la web, debes deplegarlo.

## 2.5 Despliegue de su página web

Para desplegar su página, debe cargar el archivo HTML en su servidor web. La forma de hacerlo depende del servidor, por lo que debe consultar las páginas de soporte del servidor para conocer el procedimiento específico. Estos son los pasos generales que debe seguir en la mayoría de los servidores web:

   1. Inicie sesión en su proveedor de alojamiento web.

   2. Navega a la página donde cargas los archivos de tu página web.

   3. Sube la subcarpeta que creaste en la sección anterior, incluyendo la carpeta que contiene el archivo `index.html`.

Para este ejemplo, voy a desplegar mi Pun Generator en Cloudflare siguiendo estos pasos (aunque consulte el apéndice B para obtener instrucciones más específicas):

   4. En la barra lateral de navegación del panel de Cloudflare, en Workers & Pages, haga clic en Overview.

   5. Haga clic en el botón Create Application, que se muestra en la figura 2.7. (Si esta es su primera implementación de Cloudflare, no tendrá el botón Create Application en pantalla. En ese caso, omita este paso).

<img width="905" alt="image" src="https://github.com/user-attachments/assets/763fd20d-066e-417c-b6cf-a6e5b77da266">

**Figura 2.7 En la página Overview, haga clic en Create Application.**

   6. Haga clic en la pestaña Pages.

   7. Desplácese hacia abajo hasta la sección Create Using Direct Upload y luego haga clic en Upload Assets.

   8. Escriba un nombre para su proyecto y luego haga clic en Create Project, como se muestra en la figura 2.8.

<img width="900" alt="image" src="https://github.com/user-attachments/assets/1d2e9a42-9f8b-4630-afce-caf347595bff">

**Figura 2.8 Escriba un nombre para el proyecto y luego haga clic en Create Project.**

   9. Cargue la carpeta de su sitio utilizando uno de los siguientes métodos:

      a) Arrastre la carpeta de su sitio web y suéltela en el área de carga.

      b) Haga clic en Select desde el equipo y, a continuación, haga clic en Upload Folder. En el cuadro de diálogo que aparece, navegue hasta la carpeta del proyecto y, a continuación, haga clic en Upload.

  10. Si su navegador web le pide que confirme la operación, haga clic en Upload.

  11. Haga clic en Deploy Site.

  12. Haga clic en el enlace para ver el sitio implementado en el navegador web. La Figura 2.9 muestra mi Pun Generator desplegado en https://pun-generator.pages.dev .

<img width="911" alt="image" src="https://github.com/user-attachments/assets/eeb955c8-97d4-4baf-ade7-457d345ef299">

**Figura 2.9 El sitio web Pun Generator implementado en Cloudflare Pages.**

Ahí lo tienes: una página web creada con la ayuda de ChatGPT y desplegada en la web en tan solo unos pocos pasos. Sí, la página que creaste fue sencilla, pero el resto de este libro está dedicado a mostrarte cómo lograr que ChatGPT te ayude a crear sitios web mucho más sofisticados y útiles.

## Resumen

* El proceso básico para obtener la ayuda de ChatGPT para crear una página web es el ciclo prompt-copy-save-deploy(solicitar-copiar-guardar-implementar).

* Al solicitar ChatGPT, incluya un objetivo, los datos que necesita, la acción que desea que realice la página y la interfaz con la que el usuario inicia la acción.

* Si ChatGPT no le brinda todo lo que solicita, ejecute un segundo mensaje para solicitar la información faltante.

* Copie el código generado haciendo clic en el icono o botón Copiar código.

* Utilice la aplicación de administración de archivos de su sistema operativo para crear una carpeta en la que almacenará todos sus proyectos web.

* En su editor de texto, pegue el código copiado en un nuevo archivo de texto y luego guarde ese archivo como `index.html` en una nueva subcarpeta creada para el proyecto.

* Implemente el sitio web cargando los datos del proyecto en su proveedor de alojamiento web.

## 💻 Proyectos

### `01-puns.html`

```text
Create web page code that stores 50 puns and displays a random pun each time the user clicks a button.
```

<img width="1509" alt="image" src="https://github.com/user-attachments/assets/3c69e045-8730-4eae-8a1a-516a0a231efc" />

Certainly! Here's a simple HTML, CSS, and JavaScript implementation for a web page that stores 50 puns and displays a random pun each time the user clicks a button.

### HTML, CSS, and JavaScript Code

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Random Pun Generator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .container {
            text-align: center;
            padding: 20px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 400px;
        }
        h1 {
            font-size: 2rem;
            margin-bottom: 20px;
            color: #333;
        }
        #punDisplay {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: #444;
        }
        #generateBtn {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            font-size: 1.2rem;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        #generateBtn:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Random Pun Generator</h1>
        <p id="punDisplay">Click the button for a pun!</p>
        <button id="generateBtn">Get a Pun!</button>
    </div>

    <script>
        const puns = [
            "I’m reading a book on anti-gravity. It’s impossible to put down.",
            "I used to play piano by ear, but now I use my hands.",
            "I’m friends with all electricians because they’re so current.",
            "Why don’t skeletons fight each other? They don’t have the guts.",
            "I got a job at a bakery because I kneaded dough.",
            "I don’t trust stairs because they’re always up to something.",
            "What do you call fake spaghetti? An impasta.",
            "I couldn’t figure out how to put my seatbelt on. Then it clicked.",
            "I’m a big fan of whiteboards. They’re re-markable.",
            "I once told a joke about a pencil. It had no point.",
            "I can’t believe I got fired from the calendar factory. All I did was take a day off.",
            "Why do cows wear bells? Because their horns don’t work.",
            "I’m on a whiskey diet. I’ve lost three days already.",
            "The man who survived both mustard gas and pepper spray is a seasoned veteran now.",
            "I told my wife she was drawing her eyebrows too high. She looked surprised.",
            "I would tell you a joke about an elevator, but it’s an uplifting experience.",
            "I’m reading a book on the history of glue. I just can’t seem to put it down.",
            "I would avoid the sushi if I were you. It’s a little fishy.",
            "I used to be a baker, but I couldn't make enough dough.",
            "I don’t trust people who do acupuncture. They’re back stabbers.",
            "The scarecrow won an award because he was outstanding in his field.",
            "I’m afraid for the calendar. Its days are numbered.",
            "Parallel lines have so much in common. It’s a shame they’ll never meet.",
            "I couldn’t quite remember how to throw a boomerang, but eventually, it came back to me.",
            "I don’t really understand electricity, but I’m shocked by it every time.",
            "I can’t believe I got fired from the fire department. I guess I just couldn’t put out the right impression.",
            "What’s orange and sounds like a parrot? A carrot.",
            "I wasn’t originally going to get a brain transplant, but then I changed my mind.",
            "I’m terrified of elevators, so I’m going to start taking steps to avoid them.",
            "I only know 25 letters of the alphabet. I don’t know y.",
            "I’d tell you a chemistry joke, but I know I wouldn’t get a reaction.",
            "I made a pun about the wind, but it blew.",
            "The problem with candy jokes is they’re either too sweet or too corny.",
            "I don’t have a pun about vegetables, but it’s corny.",
            "A termite walks into the bar and asks, ‘Is the bartender here?’",
            "What’s a skeleton’s least favorite room? The living room.",
            "I told my computer I needed a break, and now it won’t stop sending me Kit-Kats.",
            "I can’t trust these computers anymore. They keep going on and off at random.",
            "I used to be a librarian, but I lost my place.",
            "Why was the math book sad? Because it had too many problems.",
            "I want to be a monk, but I don’t think I’m cut out for it.",
            "I thought about going on an all-almond diet. But that’s just nuts.",
            "I had a joke about a broken pencil, but it was pointless.",
            "What do you call a belt made of watches? A waist of time.",
            "I don’t play soccer because I enjoy the pun, but because I can’t resist a kick.",
            "I don’t know why I bought a pencil sharpener. It was a pointless purchase.",
            "I wanted to be a baker, but I couldn’t make enough dough.",
            "Why did the golfer bring two pairs of pants? In case he got a hole in one.",
            "I tried to catch some fog earlier. I mist.",
            "I told my wife she was drawing her eyebrows too high. She seemed surprised.",
            "I can’t believe I didn’t get a pun about a broken pencil.",
            "If you don’t pay your exorcist, do you get repossessed?",
            "I’d tell you a joke about a broken pencil, but it’s pointless."
        ];

        const punDisplay = document.getElementById('punDisplay');
        const generateBtn = document.getElementById('generateBtn');

        generateBtn.addEventListener('click', () => {
            const randomPun = puns[Math.floor(Math.random() * puns.length)];
            punDisplay.textContent = randomPun;
        });
    </script>
</body>
</html>
```

### Explanation:

- **HTML Structure**: This contains a heading (`h1`) to display the title of the page, a paragraph (`#punDisplay`) where the random pun will be shown, and a button (`#generateBtn`) to trigger the pun change.
  
- **CSS Styling**: 
  - The `body` is styled to center the content vertically and horizontally using Flexbox.
  - The `.container` class wraps the content, adding some padding, background color, and shadow to create a clean, centered box.
  - The `#generateBtn` changes its background color slightly on hover for a better user experience.

- **JavaScript**:
  - An array `puns` holds 50 different puns.
  - The `generateBtn` listens for clicks, and every time it is clicked, a random pun is selected from the `puns` array using `Math.random()` and displayed in the `#punDisplay` paragraph.

You can copy this code into a `.html` file and open it in your browser to see the pun generator in action!

<img width="1511" alt="image" src="https://github.com/user-attachments/assets/712c8bc0-45b3-40d1-80b2-fae0b9ac6009" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/9933ea98-8b96-461f-9476-88990645ede5" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/f8228ca6-5dc7-4ca0-b9c6-bc452503f5d1" />

### `02-chistes.html`

```text
Crea un código de página web que almacene 50 chistes y muestre un chiste aleatorio cada vez que el usuario haga clic en un botón.
```

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/7fca9295-5056-4022-a608-44894abc8618" />

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chistes Aleatorios</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
            color: #333;
        }

        #joke-container {
            margin: 50px auto;
            padding: 20px;
            max-width: 600px;
            background: #fff;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            border-radius: 10px;
        }

        button {
            background-color: #007BFF;
            color: white;
            border: none;
            padding: 10px 20px;
            margin-top: 20px;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
        }

        button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <div id="joke-container">
        <h1>Chistes Aleatorios</h1>
        <p id="joke">¡Haz clic en el botón para leer un chiste!</p>
        <button onclick="showRandomJoke()">Mostrar Chiste</button>
    </div>

    <script>
        const jokes = [
            "¿Por qué los pájaros no usan Facebook? Porque ya tienen Twitter.",
            "¿Qué hace una abeja en el gimnasio? Zum-ba.",
            "¿Cómo se despiden los químicos? Ácido un placer.",
            "¿Qué hace un pez en tierra? Nada.",
            "¿Qué le dice una iguana a su hermana gemela? Iguanita.",
            "¿Por qué la computadora fue al médico? Porque tenía un virus.",
            "¿Qué le dijo el café al azúcar? Sin ti, mi vida es amarga.",
            "¿Qué hace un perro con un taladro? ¡Taladrando!",
            "¿Qué le dice una impresora a otra? Ese papel es tuyo o es mi impresión.",
            "¿Qué hace un lápiz en el gimnasio? Sacar punta.",
            "¿Cómo se llama un boomerang que no regresa? Palo.",
            "¿Por qué los esqueletos no pelean? Porque no tienen agallas.",
            "¿Por qué el libro de matemáticas estaba triste? Porque tenía muchos problemas.",
            "¿Qué hace una vaca en el espacio? ¡Vacunar!",
            "¿Cómo se despide un vaquero? ¡Hasta la vista, vaquero!",
            "¿Qué hace un tomate en un baño? Ketchup.",
            "¿Qué le dijo una pared a otra? Nos vemos en la esquina.",
            "¿Por qué las bicicletas no pueden pararse solas? Porque están dos-tadas.",
            "¿Qué hace un elefante con gafas? Ver mejor.",
            "¿Por qué no puedes confiar en los átomos? Porque lo forman todo.",
            "¿Qué le dice un jardinero a otro? Disfrutemos el momento porque este césped es el único que tenemos.",
            "¿Por qué la escoba está feliz? Porque va a barrer la competencia.",
            "¿Qué hace un pez mago? Nada por aquí, nada por allá.",
            "¿Cómo se llama el café más peligroso? El ex-preso.",
            "¿Qué dijo el cero al ocho? Bonito cinturón.",
            "¿Qué hace una cereza en el baño? Espera a que cerezca el pelo.",
            "¿Qué hace un pato en el tráfico? ¡Pato, pato, pato!",
            "¿Qué hace una abeja en la peluquería? Se está peinando las alas.",
            "¿Qué le dice el agua al hielo? ¡Qué frío estás!",
            "¿Cómo se llama una fila de hombres levantando carne? Una barbacoa.",
            "¿Qué hace un matemático perdido? Busca su punto de referencia.",
            "¿Qué hace una tortilla hablando? Cuenta sus problemas de forma enrollada.",
            "¿Qué dijo el timbre al teléfono? Eres un sonador.",
            "¿Por qué el león siempre pierde en los juegos de mesa? Porque siempre se enfoca en rugir.",
            "¿Cómo se despide un músico? A-do-ré verte.",
            "¿Qué hace un cocodrilo trabajando en una oficina? Crocumentos.",
            "¿Por qué el reloj estaba emocionado? Porque estaba a punto de dar las 12.",
            "¿Qué hace un loro viendo la tele? Un lorograma.",
            "¿Por qué los tenistas no usan reloj? Porque siempre están pendientes del tiempo.",
            "¿Cómo se despide un espejo? Refleja sobre eso.",
            "¿Por qué los fantasmas no mienten? Porque siempre son transparentes.",
            "¿Qué hace un caballo en la computadora? Navega en caballo de troya.",
            "¿Qué hace una pizza haciendo ejercicio? Se estira.",
            "¿Qué hace un perro con una calculadora? Saca cuentas perronas.",
            "¿Qué hace un plátano en un concierto? Da la nota.",
            "¿Por qué el panadero está feliz? Porque está amasando su fortuna.",
            "¿Cómo se llama un oso sin dientes? ¡Gominola!",
            "¿Qué le dice un zapato a otro? ¡Zapateémonos de aquí!",
            "¿Por qué el sol nunca está triste? Porque siempre brilla."
        ];

        function showRandomJoke() {
            const randomIndex = Math.floor(Math.random() * jokes.length);
            document.getElementById("joke").innerText = jokes[randomIndex];
        }
    </script>
</body>
</html>
```


<img width="1512" alt="image" src="https://github.com/user-attachments/assets/8b582c8b-51d8-4b47-9940-b9c3983865de" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/ee1f5ee7-7f12-456c-93a1-23c6ff139e3c" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/fb3d5234-8e12-47f3-9830-e0368dd6c09f" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/2c080509-1e24-438e-b014-d9a6f379f87b" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/4b60f511-80c9-401f-a3ef-d37499ecfdf0" />
