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

## Prompts para single-page websites

### `03-Miami.html`

* “Crear un código de página web que muestre una lista de diez X cosas para hacer en Y ” (donde X es un adjetivo, como divertido o interesante , e Y es el nombre de una ciudad o un barrio). Ejemplo:

```text
Create web page code that displays a list of ten entertaining things to do in Miami’s South Beach area.
```

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/123d1961-8b4d-4e00-97cc-4a5e8b985a83" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/17c38196-ccc7-4be1-ab36-16ec8da1da4f" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/5958c962-c910-452a-bfb2-7e103c2a6458" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/3af1db11-efda-4ca3-b53c-81bbb7f562d3" />

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Top 10 Things to Do in Miami's South Beach</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
            color: #333;
        }
        header {
            background-color: #ff6f61;
            color: white;
            padding: 1em 0;
            text-align: center;
        }
        main {
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            background-color: white;
            margin: 10px 0;
            padding: 15px;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        li h2 {
            margin: 0 0 5px;
            color: #ff6f61;
        }
    </style>
</head>
<body>
    <header>
        <h1>Top 10 Things to Do in Miami's South Beach</h1>
    </header>
    <main>
        <ul>
            <li>
                <h2>1. Visit the Art Deco Historic District</h2>
                <p>Explore the colorful and iconic Art Deco architecture lining Ocean Drive and Collins Avenue.</p>
            </li>
            <li>
                <h2>2. Relax on South Beach</h2>
                <p>Enjoy the sun, sand, and turquoise waters of Miami's most famous beach.</p>
            </li>
            <li>
                <h2>3. Stroll Down Ocean Drive</h2>
                <p>Experience vibrant nightlife, restaurants, and bars along this iconic street.</p>
            </li>
            <li>
                <h2>4. Visit the Bass Museum of Art</h2>
                <p>Discover contemporary art exhibitions and programs in this renowned museum.</p>
            </li>
            <li>
                <h2>5. Experience Lincoln Road Mall</h2>
                <p>Shop, dine, and people-watch at this pedestrian-friendly outdoor mall.</p>
            </li>
            <li>
                <h2>6. Check Out South Pointe Park</h2>
                <p>Walk along the scenic paths, enjoy the pier, and take in stunning views of the Miami skyline.</p>
            </li>
            <li>
                <h2>7. Take a Guided Art Walk</h2>
                <p>Explore the local art scene with a tour through the galleries and street art in the area.</p>
            </li>
            <li>
                <h2>8. Indulge in Cuban Cuisine</h2>
                <p>Taste authentic Cuban dishes at local spots like Puerto Sagua or David's Cafe.</p>
            </li>
            <li>
                <h2>9. Dance the Night Away</h2>
                <p>Experience Miami’s world-famous nightlife at clubs like LIV or Story.</p>
            </li>
            <li>
                <h2>10. Rent a Bike and Explore</h2>
                <p>Cycle along the Miami Beach boardwalk and discover hidden gems along the way.</p>
            </li>
        </ul>
    </main>
</body>
</html>
```

### `04-Madrid.html`

```text
Crea un código de página web que muestre una lista de diez cosas entretenidas para hacer en Madrid España.
```

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/2b1bbe78-7956-4afc-8e89-21fa87ba7090" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/e1927b7a-17ad-420f-8e63-774b97a794b8" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/bc646be2-bc39-48a0-95e5-7bd9a79df858" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/e619507f-f3ab-4661-9a58-ea19a002be34" />

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cosas Entretenidas en Madrid</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
            color: #333;
        }
        header {
            background-color: #ff5733;
            color: white;
            padding: 1rem 0;
            text-align: center;
        }
        .container {
            max-width: 800px;
            margin: 2rem auto;
            padding: 1rem;
            background: white;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        h1 {
            font-size: 2rem;
            text-align: center;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            background: #ffebcc;
            margin: 0.5rem 0;
            padding: 1rem;
            border-radius: 5px;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
        }
        li:hover {
            background-color: #ffd9a1;
        }
    </style>
</head>
<body>
    <header>
        <h1>10 Cosas Entretenidas para Hacer en Madrid</h1>
    </header>
    <div class="container">
        <ul>
            <li>Explorar el Parque del Retiro y remar en el estanque.</li>
            <li>Visitar el Museo del Prado y admirar las obras maestras.</li>
            <li>Recorrer la Gran Vía para disfrutar de las tiendas y teatros.</li>
            <li>Probar las tapas en el Mercado de San Miguel.</li>
            <li>Contemplar el atardecer en el Templo de Debod.</li>
            <li>Conocer el estadio Santiago Bernabéu o el Wanda Metropolitano.</li>
            <li>Perderse en las calles del barrio de Malasaña y descubrir su vida nocturna.</li>
            <li>Visitar el Palacio Real y sus jardines.</li>
            <li>Participar en una clase de flamenco o disfrutar de un espectáculo.</li>
            <li>Hacer un tour gastronómico por los bares tradicionales de La Latina.</li>
        </ul>
    </div>
</body>
</html>
```

### `05-PannaCotta.html`

* “Generar el código para una página web que proporcione una receta para preparar X ” (donde X es una cena, postre u otro tipo de plato que se pueda cocinar desde cero). Ejemplo:

```text
Generate the code for a web page that provides a recipe for making panna cotta.
```

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/fa4fd854-0fd8-4cd7-a41f-a9997031debd" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/aa4a0846-bdb6-4c95-a466-68bd4ddebbf4" />

Como el título no se veía se pidio una segunda petición a ChatGPT.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/842a5cd0-4740-4af4-9633-4d35bf68ff48" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/23a7e6f8-b1a8-45a9-a2ff-a949a4ed01a5" />

Aquí se puede observar el cambio que realizo:

<img width="601" alt="image" src="https://github.com/user-attachments/assets/b582a4de-fdaf-4ad3-bc23-df1a3fc1ce81" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/74559b6a-6715-4843-8b31-3b7da7e038f6" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/2e005a73-5519-4d68-ab7e-6bc1d9953e0d" />

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Panna Cotta Recipe</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 0;
            background-color: #f9f9f9;
            color: #333;
        }
        header {
            background: #6c5ce7;
            color: white;
            padding: 1rem 0;
            text-align: center;
        }
        main {
            max-width: 800px;
            margin: 2rem auto;
            padding: 1rem;
            background: white;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }
        h1, h2 {
            color: #6c5ce7;
        }
        ul {
            padding-left: 20px;
        }
        footer {
            text-align: center;
            padding: 1rem;
            background: #333;
            color: white;
            margin-top: 2rem;
        }
    </style>
</head>
<body>
    <header>
        <h1 style="color: white;">Panna Cotta Recipe</h1>
    </header>
    <main>
        <section>
            <h2>Ingredients</h2>
            <ul>
                <li>2 cups (500 ml) heavy cream</li>
                <li>1/4 cup (50 g) granulated sugar</li>
                <li>1 teaspoon vanilla extract</li>
                <li>2 teaspoons powdered gelatin</li>
                <li>3 tablespoons (45 ml) cold water</li>
                <li>Fresh fruit or berry sauce for topping (optional)</li>
            </ul>
        </section>
        <section>
            <h2>Instructions</h2>
            <ol>
                <li>In a small bowl, sprinkle the powdered gelatin over the cold water and let it sit for 5 minutes to bloom.</li>
                <li>In a medium saucepan, combine the heavy cream and sugar. Heat over medium heat, stirring, until the sugar is dissolved and the mixture is hot but not boiling.</li>
                <li>Remove the saucepan from heat and stir in the vanilla extract.</li>
                <li>Stir the bloomed gelatin into the hot cream mixture until fully dissolved.</li>
                <li>Pour the mixture into serving glasses or molds, leaving space for toppings.</li>
                <li>Refrigerate for at least 4 hours or until set.</li>
                <li>Serve chilled, topped with fresh fruit or berry sauce if desired.</li>
            </ol>
        </section>
    </main>
    <footer>
        <p>&copy; 2024 Delicious Desserts</p>
    </footer>
</body>
</html>
```

### `06-CochinitaPibil.html`

```text
Generar el código para una página web que proporcione una receta para hacer cochinita pibil.
```

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/c436b34d-1524-45aa-b7ba-ef5110a941b8" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/abdc4471-9ca7-45b1-95b5-d9c821b16e29" />

Vuelve a pasar lo mismo con el título del header que no se ve, vamos a pedir que lo ponga en color blanco.

La primera petición no sirvio y se realizo una segunda petición más especifica, el resultado es más elegante a comparación de lo que se hizo en el ejercicio anterior, ya que se modifico el CSS para tener encuenta el cambio solicitado.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/1c1bd964-0d50-4b82-89ef-9840d40b8ee7" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/d3e63ffb-a1ef-4ed6-aedc-c73ae7c8d5df" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/30fc5491-172d-428d-b0c0-87cca33cbb6b" />

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Receta de Cochinita Pibil</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 0;
            background-color: #f8f8f8;
            color: #333;
        }
        header {
            background-color: #d35400;
            color: white;
            padding: 1em 0;
            text-align: center;
        }
        header h1 {
            color: white;
        }
        main {
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background: white;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }
        h1, h2 {
            color: #d35400;
        }
        ul {
            list-style-type: disc;
            margin: 10px 0 20px 20px;
        }
        footer {
            text-align: center;
            padding: 10px 0;
            background-color: #333;
            color: white;
            position: relative;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>
    <header>
        <h1>Receta Tradicional de Cochinita Pibil</h1>
    </header>
    <main>
        <section>
            <h2>Ingredientes</h2>
            <ul>
                <li>1.5 kg de carne de cerdo (preferiblemente pierna o lomo)</li>
                <li>100 g de achiote</li>
                <li>1 taza de jugo de naranja agria (o una mezcla de naranja dulce y limón)</li>
                <li>3 dientes de ajo</li>
                <li>1 cucharadita de orégano</li>
                <li>1 cucharadita de comino</li>
                <li>Sal al gusto</li>
                <li>Hojas de plátano</li>
                <li>Cebolla morada en rodajas</li>
                <li>Vinagre</li>
                <li>Chiles habaneros (opcional)</li>
            </ul>
        </section>
        <section>
            <h2>Instrucciones</h2>
            <ol>
                <li>Disolver el achiote en el jugo de naranja agria, agregando los ajos triturados, el orégano, el comino y sal al gusto.</li>
                <li>Marinar la carne de cerdo con la mezcla anterior, asegurándose de que quede bien impregnada. Dejar reposar en el refrigerador por al menos 4 horas, idealmente toda la noche.</li>
                <li>Envolver la carne marinada en hojas de plátano y colocarla en una bandeja para horno.</li>
                <li>Precalentar el horno a 180°C (350°F) y hornear la carne durante aproximadamente 3 horas, o hasta que esté muy tierna.</li>
                <li>Mientras tanto, preparar la cebolla morada encurtida mezclándola con vinagre, sal y, si se desea, rodajas de chile habanero.</li>
                <li>Desmenuzar la carne y servir con tortillas calientes, cebolla encurtida y salsas al gusto.</li>
            </ol>
        </section>
    </main>
    <footer>
        <p>&copy; 2024 Recetas Tradicionales. Todos los derechos reservados.</p>
    </footer>
</body>
</html>
```

### `07-Bathroom.html`

* “Proporcionar un código de página web que enumere los pasos necesarios para X ” (donde X es un proyecto, un trabajo de reparación, una tarea de mantenimiento u otra tarea). Ejemplo:

```text
Provide web page code that lists the steps required to replace a bathroom faucet.
```

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/a8794205-9c77-4aa2-9ae2-ea54aa5116a8" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/c64b3764-60ad-498e-9e9e-379085b7d5c6" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/d26a483e-7955-4e37-b0b2-9ceebae37c85" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/cd8e3240-8aa9-4d6c-aaa5-7cacd35224e6" />

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>How to Replace a Bathroom Faucet</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            line-height: 1.6;
        }
        h1 {
            color: #2c3e50;
        }
        ol {
            margin-left: 20px;
        }
        .step {
            margin-bottom: 10px;
        }
        .tools, .notes {
            margin-top: 20px;
            background: #f9f9f9;
            padding: 10px;
            border-left: 4px solid #2ecc71;
        }
    </style>
</head>
<body>
    <h1>How to Replace a Bathroom Faucet</h1>

    <div class="tools">
        <h2>Tools and Materials Needed:</h2>
        <ul>
            <li>New faucet</li>
            <li>Adjustable wrench</li>
            <li>Basin wrench</li>
            <li>Plumber's tape</li>
            <li>Bucket or towel</li>
            <li>Silicone caulk (optional)</li>
        </ul>
    </div>

    <h2>Steps to Replace the Faucet:</h2>
    <ol>
        <li class="step">
            <strong>Turn off the water supply:</strong> Locate the shut-off valves under the sink and turn them clockwise to close.
        </li>
        <li class="step">
            <strong>Drain the faucet:</strong> Open the faucet to release any remaining water in the lines.
        </li>
        <li class="step">
            <strong>Disconnect water supply lines:</strong> Use an adjustable wrench to unscrew the supply lines from the faucet.
        </li>
        <li class="step">
            <strong>Remove the old faucet:</strong> Use a basin wrench to loosen the mounting nuts underneath the sink, then lift the old faucet out.
        </li>
        <li class="step">
            <strong>Prepare the new faucet:</strong> Assemble the faucet according to the manufacturer’s instructions and apply plumber's tape to threaded connections if needed.
        </li>
        <li class="step">
            <strong>Install the new faucet:</strong> Place the new faucet into the mounting holes, and secure it from underneath using the provided hardware.
        </li>
        <li class="step">
            <strong>Reconnect water supply lines:</strong> Attach the supply lines to the new faucet and tighten with an adjustable wrench.
        </li>
        <li class="step">
            <strong>Test for leaks:</strong> Turn the water supply back on and check for leaks. Tighten connections as necessary.
        </li>
        <li class="step">
            <strong>Seal the base:</strong> If required, apply a thin bead of silicone caulk around the base of the faucet to prevent water seepage.
        </li>
    </ol>

    <div class="notes">
        <h2>Additional Notes:</h2>
        <p>Ensure you have the correct size and type of faucet for your sink. If you're unsure, consult the faucet's installation guide or contact a professional plumber.</p>
    </div>
</body>
</html>
```

### `08-Grifo.html`

```text
Proporciona el código de la página web que enumera los pasos necesarios para reemplazar un grifo del baño.
```

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/e0108aa8-e2fb-459e-bb88-2f6508a71378" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/ad3954aa-4221-464a-b3e3-02e4d558c5ad" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/fdce26c7-187d-47c1-af32-2d06f5cdd98f" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/a7254e5b-f9ce-4b4e-be76-7574bca0fab2" />

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cómo Reemplazar un Grifo del Baño</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            line-height: 1.6;
        }
        header {
            text-align: center;
            margin-bottom: 20px;
        }
        h1 {
            color: #333;
        }
        ol {
            padding-left: 20px;
        }
        .step {
            margin-bottom: 15px;
        }
        footer {
            text-align: center;
            margin-top: 30px;
            font-size: 0.9em;
            color: #555;
        }
    </style>
</head>
<body>
    <header>
        <h1>Cómo Reemplazar un Grifo del Baño</h1>
    </header>

    <main>
        <p>Reemplazar un grifo del baño puede ser una tarea sencilla si sigues estos pasos. Asegúrate de tener todas las herramientas necesarias antes de comenzar.</p>
        
        <ol>
            <li class="step">
                <strong>Apaga el suministro de agua:</strong> Localiza las válvulas de cierre debajo del lavabo y ciérralas girándolas en el sentido de las agujas del reloj.
            </li>
            <li class="step">
                <strong>Desconecta las líneas de suministro:</strong> Usa una llave inglesa para aflojar las tuercas que conectan las líneas de agua al grifo.
            </li>
            <li class="step">
                <strong>Retira el grifo viejo:</strong> Afloja y quita las tuercas o tornillos que sujetan el grifo al lavabo. Luego, levanta el grifo con cuidado.
            </li>
            <li class="step">
                <strong>Limpia el área:</strong> Limpia cualquier residuo de sellador o suciedad en la superficie del lavabo donde instalarás el nuevo grifo.
            </li>
            <li class="step">
                <strong>Instala el nuevo grifo:</strong> Coloca el nuevo grifo en su lugar y asegúralo con las tuercas o tornillos proporcionados. Sigue las instrucciones del fabricante.
            </li>
            <li class="step">
                <strong>Conecta las líneas de suministro:</strong> Vuelve a conectar las líneas de agua al grifo y ajusta las tuercas con una llave inglesa.
            </li>
            <li class="step">
                <strong>Abre el suministro de agua:</strong> Abre las válvulas de cierre y verifica si hay fugas. Si todo está en orden, prueba el grifo para asegurarte de que funcione correctamente.
            </li>
        </ol>
    </main>

    <footer>
        <p>&copy; 2024 Cómo Hacerlo Fácil. Todos los derechos reservados.</p>
    </footer>
</body>
</html>
```

### `09-Hologram.html`

* “Crear código de página web que explique cómo funciona X ” (donde X es una máquina, un dispositivo, un principio científico o, en realidad, prácticamente cualquier cosa). Ejemplo:

```text
Create web page code that explains how a hologram works.
```

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/ef91fed7-e006-4cc6-83b6-75de868249be" />

Observe que he llegado al limite de mis peticiones en ChatGPT.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/bdcfec39-bcb5-4bcf-927c-103815b55df0" />

Otra vez sale el título en español, podemos solicitar a ChatGPT que lo cambie o lo podemos hacer manualmente.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/076fda6b-95e9-4c9c-b8de-314e6ec99dbb" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/37875c7f-9ee3-43a7-8951-040c535b11ef" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/2fc87424-5942-4d25-9e6f-75942e6bbc62" />

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>How Holograms Work</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
        }
        header {
            background: #0073e6;
            color: #fff;
            padding: 1rem 0;
            text-align: center;
        }
        .container {
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background: #fff;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }
        header h1{
            color: white;
        }
        h1 {
            color: #0073e6;
        }
        h2 {
            color: #005bb5;
        }
    </style>
</head>
<body>
    <header>
        <h1>Understanding Holograms</h1>
    </header>
    <div class="container">
        <h2>What is a Hologram?</h2>
        <p>A hologram is a three-dimensional image formed by the interference of light beams from a laser or other coherent light source. Unlike conventional photographs or displays, holograms appear to have depth and can be viewed from different angles, as if the object is really there.</p>

        <h2>How Holograms Are Created</h2>
        <p>Holograms are created using a technique called holography, which records and reconstructs the light waves scattered from an object. The process involves two main steps:</p>
        <ol>
            <li>
                <strong>Recording:</strong> A laser beam is split into two parts: the reference beam and the object beam. The object beam illuminates the object, and the reflected light is captured on a recording medium. The reference beam interferes with the reflected light, creating an interference pattern.
            </li>
            <li>
                <strong>Reconstruction:</strong> When the recorded interference pattern is illuminated with the reference beam (or a similar light source), it recreates the original light waves, producing a three-dimensional image of the object.
            </li>
        </ol>

        <h2>Applications of Holograms</h2>
        <p>Holograms are used in various fields, including:</p>
        <ul>
            <li>Security: Holograms on credit cards and IDs to prevent counterfeiting.</li>
            <li>Entertainment: Holographic displays in concerts and movies.</li>
            <li>Medical: 3D imaging for detailed visualization in surgeries.</li>
            <li>Education: Interactive holographic teaching tools.</li>
        </ul>

        <h2>How Holography Works in Real-Time Displays</h2>
        <p>Recent advancements have enabled real-time holographic displays using advanced optics and computational power. These displays use dynamic projection systems to create the illusion of 3D objects in space, often employing augmented reality (AR) or virtual reality (VR) technologies.</p>

        <h2>Conclusion</h2>
        <p>Holography represents a fascinating blend of art and science, offering innovative solutions in many areas of life. As technology advances, holograms are becoming increasingly sophisticated and accessible, opening up new possibilities for communication, entertainment, and education.</p>
    </div>
</body>
</html>
```

### `10-Holograma.html`

```text
Crear código de página web que explique cómo funciona un holograma.
```

A pesar de que he llegado a limite de mis peticiones a ChatGPT me ha permitido haxcer una nueva petición, pero el formato en que muestra la respuesta es algo diferente a las anteriores.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/d29240f8-fc75-47cc-aaff-9e0a4db04695" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/09e66570-910f-4706-99ab-6d6962e53135" />

Aquí tienes un ejemplo de código HTML y CSS para una página web que explica cómo funciona un holograma. El contenido incluye una introducción, explicación, ejemplos visuales y un diseño básico. Puedes personalizarlo más según tus necesidades.

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¿Cómo Funciona un Holograma?</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>¿Cómo Funciona un Holograma?</h1>
        <nav>
            <ul>
                <li><a href="#introduccion">Introducción</a></li>
                <li><a href="#tecnica">Técnica</a></li>
                <li><a href="#ejemplo">Ejemplo Visual</a></li>
            </ul>
        </nav>
    </header>
    
    <section id="introduccion">
        <h2>Introducción</h2>
        <p>Un holograma es una imagen tridimensional creada mediante el uso de la luz. A diferencia de una fotografía convencional, que captura una imagen plana, un holograma presenta una representación tridimensional completa del objeto, que puede ser vista desde diferentes ángulos. Los hologramas no solo muestran una imagen visual, sino que pueden proporcionar una sensación de profundidad y movimiento.</p>
    </section>

    <section id="tecnica">
        <h2>Técnica</h2>
        <p>El proceso de creación de un holograma involucra dos componentes clave: la luz láser y la interferencia. Un láser se divide en dos haces de luz, uno ilumina el objeto y el otro se utiliza como referencia. La luz reflejada del objeto interactúa con el haz de referencia, y esta interacción se captura en un material fotosensible (como una placa fotográfica o una película especial). El patrón resultante crea la imagen tridimensional.</p>
    </section>

    <section id="ejemplo">
        <h2>Ejemplo Visual</h2>
        <p>A continuación se muestra un ejemplo de cómo se puede visualizar un holograma en un dispositivo especial o en una pantalla con efectos de 3D.</p>
        <div class="hologram-example">
            <img src="hologram-example.jpg" alt="Ejemplo de holograma">
        </div>
    </section>

    <footer>
        <p>&copy; 2024 Hologramas en la Ciencia</p>
    </footer>
</body>
</html>
```

**Código CSS (styles.css)**:


```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    color: #333;
}

header {
    background-color: #0044cc;
    color: white;
    padding: 20px;
    text-align: center;
}

header h1 {
    font-size: 2.5em;
}

nav ul {
    list-style-type: none;
    margin-top: 20px;
}

nav ul li {
    display: inline;
    margin-right: 15px;
}

nav ul li a {
    color: white;
    text-decoration: none;
    font-size: 1.2em;
}

section {
    padding: 20px;
    margin: 20px auto;
    max-width: 900px;
    background-color: white;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

section h2 {
    color: #0044cc;
    font-size: 2em;
    margin-bottom: 10px;
}

section p {
    line-height: 1.6;
    font-size: 1.1em;
}

.hologram-example {
    text-align: center;
    margin-top: 20px;
}

.hologram-example img {
    max-width: 100%;
    height: auto;
    border-radius: 10px;
}

footer {
    text-align: center;
    padding: 10px;
    background-color: #0044cc;
    color: white;
    margin-top: 40px;
}

footer p {
    font-size: 1em;
}
```

Aquí tienes un ejemplo de código HTML y CSS para una página web que explica cómo funciona un holograma. El contenido incluye una introducción, explicación, ejemplos visuales y un diseño básico. Puedes personalizarlo más según tus necesidades.

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/65a08e4d-36b5-4a3f-8ab4-acef269a20e0" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/dc9c369b-1151-47a1-ae54-37102009524c" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/8aab0a47-312a-4a0b-a9e1-55463efe3ed1" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/da76987e-de07-4fa0-9d27-2f58f427d49f" />

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/6114fab4-0a23-4720-9c25-3573bb7f06ad" />


### Código HTML:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¿Cómo Funciona un Holograma?</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>¿Cómo Funciona un Holograma?</h1>
        <nav>
            <ul>
                <li><a href="#introduccion">Introducción</a></li>
                <li><a href="#tecnica">Técnica</a></li>
                <li><a href="#ejemplo">Ejemplo Visual</a></li>
            </ul>
        </nav>
    </header>
    
    <section id="introduccion">
        <h2>Introducción</h2>
        <p>Un holograma es una imagen tridimensional creada mediante el uso de la luz. A diferencia de una fotografía convencional, que captura una imagen plana, un holograma presenta una representación tridimensional completa del objeto, que puede ser vista desde diferentes ángulos. Los hologramas no solo muestran una imagen visual, sino que pueden proporcionar una sensación de profundidad y movimiento.</p>
    </section>

    <section id="tecnica">
        <h2>Técnica</h2>
        <p>El proceso de creación de un holograma involucra dos componentes clave: la luz láser y la interferencia. Un láser se divide en dos haces de luz, uno ilumina el objeto y el otro se utiliza como referencia. La luz reflejada del objeto interactúa con el haz de referencia, y esta interacción se captura en un material fotosensible (como una placa fotográfica o una película especial). El patrón resultante crea la imagen tridimensional.</p>
    </section>

    <section id="ejemplo">
        <h2>Ejemplo Visual</h2>
        <p>A continuación se muestra un ejemplo de cómo se puede visualizar un holograma en un dispositivo especial o en una pantalla con efectos de 3D.</p>
        <div class="hologram-example">
            <img src="hologram-example.jpg" alt="Ejemplo de holograma">
        </div>
    </section>

    <footer>
        <p>&copy; 2024 Hologramas en la Ciencia</p>
    </footer>
</body>
</html>
```

### Código CSS (styles.css):

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    color: #333;
}

header {
    background-color: #0044cc;
    color: white;
    padding: 20px;
    text-align: center;
}

header h1 {
    font-size: 2.5em;
}

nav ul {
    list-style-type: none;
    margin-top: 20px;
}

nav ul li {
    display: inline;
    margin-right: 15px;
}

nav ul li a {
    color: white;
    text-decoration: none;
    font-size: 1.2em;
}

section {
    padding: 20px;
    margin: 20px auto;
    max-width: 900px;
    background-color: white;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

section h2 {
    color: #0044cc;
    font-size: 2em;
    margin-bottom: 10px;
}

section p {
    line-height: 1.6;
    font-size: 1.1em;
}

.hologram-example {
    text-align: center;
    margin-top: 20px;
}

.hologram-example img {
    max-width: 100%;
    height: auto;
    border-radius: 10px;
}

footer {
    text-align: center;
    padding: 10px;
    background-color: #0044cc;
    color: white;
    margin-top: 40px;
}

footer p {
    font-size: 1em;
}
```

### Explicación de los elementos:

1. **Estructura HTML**: 
   - Utiliza una estructura básica de página con un encabezado (header), varias secciones (section) que explican qué es un holograma, cómo funciona y un ejemplo visual, además de un pie de página (footer).
   - En el `<nav>`, hay enlaces que permiten navegar a las distintas secciones de la página.

2. **CSS**:
   - El diseño es sencillo y limpio, con un esquema de colores basado en azul y blanco.
   - Hay sombras suaves en las secciones y un diseño centralizado para mejorar la legibilidad.
   - El uso de la propiedad `max-width` en las imágenes asegura que se vean bien en diferentes tamaños de pantalla.

3. **Imagen del ejemplo visual**: 
   - Para ilustrar cómo se vería un holograma, debes tener una imagen llamada `hologram-example.jpg` en la misma carpeta que el archivo HTML o proporcionar una URL a una imagen de ejemplo de un holograma.

Este código es solo un punto de partida. Puedes expandirlo agregando más detalles interactivos o gráficos, o incluso simulaciones de hologramas usando JavaScript o imágenes en 3D.

Vamos a meter todo esto en nuestro VSC, es posible que cambiemos el nombre del CSS para asociarlo a nuestro archivo HTML.




```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¿Cómo Funciona un Holograma?</title>
    <link rel="stylesheet" href="10-styles.css">
</head>
<body>
    <header>
        <h1>¿Cómo Funciona un Holograma?</h1>
        <nav>
            <ul>
                <li><a href="#introduccion">Introducción</a></li>
                <li><a href="#tecnica">Técnica</a></li>
                <li><a href="#ejemplo">Ejemplo Visual</a></li>
            </ul>
        </nav>
    </header>
    
    <section id="introduccion">
        <h2>Introducción</h2>
        <p>Un holograma es una imagen tridimensional creada mediante el uso de la luz. A diferencia de una fotografía convencional, que captura una imagen plana, un holograma presenta una representación tridimensional completa del objeto, que puede ser vista desde diferentes ángulos. Los hologramas no solo muestran una imagen visual, sino que pueden proporcionar una sensación de profundidad y movimiento.</p>
    </section>

    <section id="tecnica">
        <h2>Técnica</h2>
        <p>El proceso de creación de un holograma involucra dos componentes clave: la luz láser y la interferencia. Un láser se divide en dos haces de luz, uno ilumina el objeto y el otro se utiliza como referencia. La luz reflejada del objeto interactúa con el haz de referencia, y esta interacción se captura en un material fotosensible (como una placa fotográfica o una película especial). El patrón resultante crea la imagen tridimensional.</p>
    </section>

    <section id="ejemplo">
        <h2>Ejemplo Visual</h2>
        <p>A continuación se muestra un ejemplo de cómo se puede visualizar un holograma en un dispositivo especial o en una pantalla con efectos de 3D.</p>
        <div class="hologram-example">
            <img src="10-hologram-example.jpg" alt="Ejemplo de holograma">
        </div>
    </section>

    <footer>
        <p>&copy; 2024 Hologramas en la Ciencia</p>
    </footer>
</body>
</html>
```

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    color: #333;
}

header {
    background-color: #0044cc;
    color: white;
    padding: 20px;
    text-align: center;
}

header h1 {
    font-size: 2.5em;
}

nav ul {
    list-style-type: none;
    margin-top: 20px;
}

nav ul li {
    display: inline;
    margin-right: 15px;
}

nav ul li a {
    color: white;
    text-decoration: none;
    font-size: 1.2em;
}

section {
    padding: 20px;
    margin: 20px auto;
    max-width: 900px;
    background-color: white;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

section h2 {
    color: #0044cc;
    font-size: 2em;
    margin-bottom: 10px;
}

section p {
    line-height: 1.6;
    font-size: 1.1em;
}

.hologram-example {
    text-align: center;
    margin-top: 20px;
}

.hologram-example img {
    max-width: 100%;
    height: auto;
    border-radius: 10px;
}

footer {
    text-align: center;
    padding: 10px;
    background-color: #0044cc;
    color: white;
    margin-top: 40px;
}

footer p {
    font-size: 1em;
}
```

### `11-Sentences.html`

* “Generar el código para una página web que almacena X y muestra una Y aleatoria cuando el usuario hace clic en un botón” (donde X son algunos datos e Y son los datos combinados de alguna manera). Ejemplo:

```text
Generate the code for a web page that stores a dozen each of the following: names, verbs, colors, adjectives, and nouns. When the user clicks a button, the code should assemble and display a random sentence that uses the template "Name verb the color, adjective noun."
```

### `11-Oraciones.html`

```text
Generar el código para una página web que almacene una docena de cada uno de los siguientes: nombres, verbos, colores, adjetivos y sustantivos. Cuando el usuario haga clic en un botón, el código debe ensamblar y mostrar una oración aleatoria que utilice la plantilla "Nombre verbo el color, adjetivo sustantivo".
```

### `12-Adjectives.html`

* “Proporcione un código de página web que muestre X en una lista y almacene una Y asociada con cada X. Cuando el usuario elige X de la lista, la página muestra la Y asociada ” (donde X podría ser una palabra, persona u objeto e Y podría ser un poema, una biografía o una descripción).

```text
Provide web page code that displays six rarely used adjectives in a dropdown list and stores a limerick associated with each adjective. When the user chooses an adjective from the list, the page displays the associated limerick.
```

### `12-Adjetivos.html`

```text
Proporcionar un código de página web que muestre seis adjetivos poco utilizados en una lista desplegable y almacene un poema asociado con cada adjetivo. Cuando el usuario elige un adjetivo de la lista, la página muestra el poema asociado.
```


