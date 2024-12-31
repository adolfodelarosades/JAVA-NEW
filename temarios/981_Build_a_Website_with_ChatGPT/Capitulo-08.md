# 8 Generación de formularios del sitio

Este capítulo cubre

* Cómo manejar text boxes y text areas
* Trabajar con check boxes y radio buttons
* Cómo agregar selection lists y buttons a un form
* Cómo utilizar el servicio gratuito Getform para que le envíen datos de formulario
* Elaboración de un prompt de ChatGPT para crear una página de sign-up
* Examinar y personalizar el código generado por ChatGPT

La mayoría de las páginas web (y todos los proyectos web incluidos en este libro hasta ahora) son medios de solo lectura, lo que significa que su propósito es presentar a cada visitante información relacionada con el tema principal de la página. Estas páginas no requieren nada del visitante excepto su tiempo y atención (¡lo cual es una gran exigencia en estos tiempos de tanta actividad!).

Sin embargo, hay muchos escenarios en los que querrás que tu página sea más interactiva, es decir, que pidas a los usuarios que te proporcionen alguna información. Tal vez quieras obtener comentarios sobre tu sitio web. Tal vez quieras presentarles a tus visitantes una encuesta o un cuestionario. O tal vez quieras ofrecerles a las personas una forma de suscribirse a un boletín informativo o registrarse para un próximo evento. Cualquiera sea el motivo, solicitas dicha información ofreciendo un formulario , que es un objeto especial de la página web que tiene campos que el visitante completa y luego envía.

En este capítulo, aprenderá cómo funcionan los formularios, qué tipos de campos puede utilizar y cómo recibir los datos del formulario por correo electrónico. Luego, utilizará esta información para crear un prompt detallado para que ChatGPT genere el código necesario para una página de registro de eventos. Este capítulo también proporciona una explicación detallada del código generado por ChatGPT y sugerencias para personalizar el código.

## 8.1 Revisando el proyecto de este capítulo

El proyecto de este capítulo es una página web sencilla que incluye un formulario que permite a los visitantes de la página registrarse para un próximo evento. La página final incluirá los siguientes componentes:

* Un elemento de encabezado que incluye el logotipo, el título y el eslogan del sitio web.
* Un elemento principal que incluye el título del evento, algo de información y un formulario para registrarse en el evento.
* Un elemento de pie de página que incluye un aviso de derechos de autor

La figura 8.1 muestra un ejemplo del tipo de página que creará con la ayuda de ChatGPT en este capítulo..

![image](https://github.com/user-attachments/assets/82a9769d-0aef-408b-a3d2-1bf59d73026b)

**Figura 8.1 Una página de registro de eventos generada por ChatGPT**

El formulario de ejemplo incluye todos los tipos principales de controles de formulario, lo que significa que puede modificarlo fácilmente para recopilar otros tipos de información, como comentarios sobre el sitio o una encuesta o cuestionario. Para hacer cualquiera de estas cosas, necesita saber un poco sobre cada tipo de control de formulario. Sin embargo, primero debe aprender cómo recibir los datos del formulario.

## 8.2 Cómo recibir los datos del formulario que le enviamos

Lamentablemente, no hay ningún método integrado en HTML para que te envíen los datos de un formulario. Para obtener los datos del formulario que envía un usuario, debes crear una cuenta en una empresa que proporcione este servicio. Hay bastantes empresas de este tipo, pero para este proyecto, voy a utilizar Getform ( https://getform.io ). Esta empresa te permite crear un *endpoint* gratuito , que es una dirección a la que tu formulario envía sus datos.

Aunque Getform tiene planes de suscripción, es posible que no necesites uno porque el servicio también ofrece un nivel gratuito que tiene las siguientes restricciones:

* Un solo endpoint.
* Un máximo de 50 envíos de formularios por mes.
* La marca Getform se agrega a cada mensaje de correo electrónico de envío de formulario que recibe.

Si alguna de estas restricciones es un factor decisivo para usted, consulte los planes pagos de Getform en https://getform.io/pricing (los planes comienzan en US$19 por mes).

## 8.2.1 Configuración de una cuenta Getform

Primero, siga estos pasos para configurar una cuenta Getform:

1. Vaya a la página de inicio de Getform ( https://getform.io ).
2. Haga clic en el Generate Endpoint for Free button. (Si no ve ese botón, haga clic en Account, Sign Up, o navegue directamente a https://app.getform.io/register ).
3. Ingrese su nombre, correo electrónico y contraseña y luego haga clic en Sign Up.
4. Vaya a su bandeja de entrada de correo electrónico, abra el mensaje de correo electrónico de Getform y luego haga clic en el enlace para verificar su cuenta.

### 8.2.2 Creación de un endpoint Getform

Con su cuenta verificada, inicie sesión en su cuenta de Getform y luego siga estos pasos para configurar su endpoint de envío de formulario:

1. Haga clic en Create en la barra lateral izquierda. Getform muestra el cuadro de diálogo Create, que se muestra (completamente) en la figura 8.2.
2. Asegúrese de que la pestaña Form esté seleccionada.
3. Utilice el cuadro de texto Form Endpoint Name para escribir un nombre breve pero descriptivo para su formulario.
4. Utilice la lista Time Zone para seleccionar su zona horaria.
5. Haga clic en Create.

![image](https://github.com/user-attachments/assets/5b532639-233f-4a9e-94b5-5253ccc69e40)

**Figura 8.2 Complete este formulario para crear su punto final Getform.**

Getform crea el nuevo endpoint (punto de conexión) y luego muestra la home page del endpoint, un ejemplo de la cual se muestra en la figura 8.3. Hay varias cosas que se deben tener en cuenta en esta página:

* Necesitará la dirección del endpoint cuando solicite a ChatGPT que cree su formulario. Para evitar errores, haga clic en el botón Copy a la derecha de la dirección y luego péguela en el prompt.

* Para evitar el spam, el formulario de ejemplo incluye el siguiente código:

   ```html
   <input type="hidden" name="_gotcha" style="display:none !important">
   ```

   Este es un ejemplo de un *honeypot*, que es un campo oculto que los usuarios no verán (y por lo tanto no completarán), pero que un robot de spam completará y enviará. (Se llama *honeypot* porque el robot de spam no puede resistirlo). Un campo honeypot completo le indica al servidor Getform que el envío debe ser spam. Cuando cree su mensaje de ChatGPT más adelante, le pedirá a ChatGPT que incluya este código en su formulario.

* Puede hacer clic en Inbox en la parte superior de esta página para controlar los envíos de formularios. Pero recuerde que Getform también envía cada envío de formulario a su dirección de correo electrónico.

   ![image](https://github.com/user-attachments/assets/2ccf1fb4-256a-42eb-bd9a-6005a9cc8bae)


   **Figura 8.3 Cuando se crea el endpoint en Getform, verá su home page.**

## 8.3 Construyendo un form - formulario

Un formulario es una colección especial de elementos HTML que le permite recopilar información de un usuario y luego enviarla a algún lugar. Cada uno de estos elementos HTML especiales se denomina control y, en las siguientes secciones, aprenderá sobre la media docena de controles de formulario más comunes y útiles. Saber qué hace cada control y qué tipo de información está diseñado para recopilar le permitirá configurar un mensaje para que ChatGPT pueda crear el formulario que necesita.

A lo largo del camino, le proporcionaré ejemplos de prompts de ChatGPT para cada tipo de control. En cada ejemplo, suponga que se incluyó anteriormente en el prompt una instrucción similar a la siguiente:

```text
Include the code for an HTML form that has the following specifications:
```

```text
Incluya el código para un formulario HTML que tenga las siguientes especificaciones:
```

### 8.3.1 Especificación del endpoint del formulario

En el ejemplo de este capítulo, aprenderá a recibir los datos de un formulario mediante un servicio llamado Getform. Este servicio le proporciona una dirección única llamada endpoint , que es un script remoto que procesa los datos del formulario. Cuando le indica a ChatGPT que cree un formulario HTML, la primera especificación es esta dirección de endpoint. (Consulte la sección 8.2 para aprender a generar una dirección de endpoint única para usar con su formulario). A continuación, se incluye una instrucción de ejemplo:

```text
In the form element, set the action attribute to "endpoint" and the method attribute to "POST".
```

```text
En el elemento de formulario, establezca el atributo de acción en " endpoint " y el atributo de método en "POST".
```

En este mensaje, reemplace `endpoint` con la dirección que le proporcionó el servicio Getform. El atributo `method` al que se hace referencia en la instrucción le indica al navegador cómo enviar los datos del formulario.

Ahora que ya nos hemos aclarado este punto, es hora de analizar en detalle los controles de formulario más comunes. El primer tipo de control es el **text box - cuadro de texto**, que analizaremos a continuación.

### 8.3.2 Recopilación de texto con text box - cuadros de texto

El tipo más común de control de formulario es el text box - cuadro de texto, que es un área rectangular diseñada para contener el texto escrito por el usuario. HTML ofrece una gran colección de tipos de entrada de cuadros de texto, cada uno diseñado para contener un tipo particular de información. Estos son los cuatro tipos de entrada más comunes:

* ***Text***: Contiene cualquier tipo de texto, que puede ser cualquier combinación de letras, números y símbolos. A continuación, se incluye un ejemplo de instrucción para incluir en el prompt del formulario:

   ```text
   A text box.
   ```

   ```text
   Un cuadro de texto.
   ```

* ***Number***: Contiene solo datos numéricos. Ejemplo de instrucción:

   ```text
   A text box for numeric data.
   ```

   ```text
   Un cuadro de texto para datos numéricos.
   ```

* ***Email***: Contiene únicamente una dirección de correo electrónico. El control también verifica si el usuario ingresó una dirección de correo electrónico válida. A continuación, se muestra un ejemplo de instrucción para ChatGPT:

   ```text
   A text box for an email address.
   ```

   ```text
   Un cuadro de texto para una dirección de correo electrónico.
   ```


* ***URL***: Contiene una dirección web. Ejemplo de instrucción:

   ```text
   A text box for a web address.
   ```

   ```text
   Un cuadro de texto para una dirección web.
   ```

La figura 8.4 muestra un ejemplo de cada tipo de entrada. Observe que el campo Número incluye flechas hacia arriba y hacia abajo en las que el usuario puede hacer clic para incrementar y decrementar (respectivamente) el valor del campo actual.

![image](https://github.com/user-attachments/assets/86789302-0b48-473c-b513-309c226fd0a0)

**Figura 8.4 Los cuatro tipos principales de entrada del cuadro de texto**

**TIP** Para lograr que ChatGPT genere código que configure su formulario con el texto a la izquierda y los cuadros de texto a la derecha, incluya lo siguiente en su mensaje: “Make the form a two-column grid container with the labels in the first column and the controls in the second column.” - “Convierta el formulario en un contenedor de cuadrícula de dos columnas con las etiquetas en la primera columna y los controles en la segunda columna”.

Al solicitarle a ChatGPT que incluya cuadros de texto en un formulario, usted tiene control sobre lo siguiente para cada cuadro de texto:

* Puede establecer el ancho del cuadro especificando un tamaño en caracteres. En la figura 8.4, por ejemplo, cada cuadro de texto tiene 30 caracteres de ancho. Ejemplo de mensaje:

   ```text
   A text box that is 25 characters wide.
   ```

   ```text
   Un cuadro de texto de 25 caracteres de ancho.
   ```
* Puede especificar un valor inicial. Este valor aparece de forma predeterminada en el cuadro de texto, aunque el usuario puede editarlo o reemplazarlo. Ejemplo de mensaje:

   ```text
   A numeric text box with the initial value 42.
   ```

   ```text
   Un cuadro de texto numérico con el valor inicial 42.
   ```

* Puede especificar un *placeholder*, que es un texto que aparece temporalmente en el cuadro de texto y que le indica brevemente al usuario qué escribir en el cuadro de texto. Tan pronto como el usuario comienza a escribir, el texto del placeholder desaparece. Ejemplo de mensaje:

   ```text
   An email text box with the placeholder text "Type your email address".
   ```

   ```text
   Un cuadro de texto de correo electrónico con el texto de placeholder "Escriba su dirección de correo electrónico".
   ```

* Puede especificar una longitud máxima y/o mínima en caracteres:

   ```text
   A text box with a minimum length of 3 and a maximum length of 10.
   ```

   ```text
   Un cuadro de texto con una longitud mínima de 3 y una longitud máxima de 10.
   ```

* Puede especificar que un cuadro de texto sea “obligatorio” si el usuario debe completar un valor antes de enviar el formulario:

   ```text
   An email text box that is required.
   ```

   ```text
   Un cuadro de texto de correo electrónico que es obligatorio.
   ```

Quizás se esté preguntando cómo hacer que ChatGPT nombre cada control (como los nombres que se muestran a la izquierda de cada control en la figura 8.4). Si no especifica un nombre, ChatGPT creará uno por usted. La siguiente sección se ocupa de especificar sus propios nombres de control.

### 8.3.3 Agregar labels - etiquetas a cada control

Si examina la figura 8.4 de la sección anterior, podrá ver que los elementos están divididos en dos columnas: los controles están en la columna de la derecha y la columna de la izquierda contiene fragmentos de texto breves que describen cada control. Estos fragmentos de texto breves se denominan *labels - etiquetas* y, con la excepción del control de botón (que se analiza a continuación), debe incluir una etiqueta para cada campo. Las etiquetas deben ser lo suficientemente breves como para que no ocupen demasiado espacio en la página, pero lo suficientemente descriptivas como para que el usuario sepa lo que debe escribir en cada campo.

Cuando crea el prompt de ChatGPT para su formulario, es mejor indicar la etiqueta que desea al mismo tiempo que indica el resto de las especificaciones de control:

```text
An email address text box. Make the text box 30 characters wide and give it the label "Email address".
```

```text
Un cuadro de texto para la dirección de correo electrónico. Haz que el cuadro de texto tenga 30 caracteres de ancho y etiquétalo como "Dirección de correo electrónico".
```

### 8.3.4 Cómo manejar más texto con text areas - áreas de texto

Un text areas - cuadro de texto es útil para recopilar información relativamente breve del usuario, como su nombre, dirección de correo electrónico o número favorito. Sin embargo, en ocasiones, es posible que su formulario deba solicitar entradas de texto más largas, como comentarios, sugerencias, preguntas o incluso la biografía del usuario. Para estas entradas más largas, puede agregar un área de texto, que es un campo de formulario que admite entradas de varias líneas. La Figura 8.5 muestra un ejemplo de un área de texto.

![image](https://github.com/user-attachments/assets/04919366-ef27-4061-ada9-5a340667bac3)

**Figura 8.5 Un ejemplo de un  text area - área de texto**

Al solicitarle a ChatGPT que incluya un text area en un formulario, puede personalizar el área de texto de las siguientes maneras:

* Puede establecer la altura del cuadro del área de texto especificando el número de filas. En la figura 8.5, por ejemplo, la altura del área de texto es de seis filas. Ejemplo de instrucción para ChatGPT:

   ```text
   A text area with the label "Suggestions" and a height of six rows.
   ``` 

   ```text
   Un área de texto con la etiqueta "Sugerencias" y una altura de seis filas.
   ``` 

**NOTA**: Independientemente de la altura del text area, el usuario puede introducir texto que supere la cantidad de líneas especificada. Si la cantidad de texto es mayor que la altura del área de texto, el usuario puede desplazarse por el área de texto verticalmente o cambiar su tamaño arrastrando la esquina inferior derecha del cuadro.

* Puede establecer el ancho del cuadro del text area especificando el número de columnas:

   ```text
   A text area with a width of 30 columns.
   ```

   ```text
   Un área de texto con un ancho de 30 columnas.
   ```   

* Un text area permite al usuario escribir la longitud de entrada que desee. Sin embargo, si le preocupa que le inunden con demasiado texto, puede especificar un tamaño máximo de entrada en caracteres:

   ```text
   A text area with a maximum length of 240 characters.
   ```

   ```text
   Un área de texto con una longitud máxima de 240 caracteres.
   ```  

* Si es necesario, también puede especificar un tamaño de entrada mínimo en caracteres:

   ```text
   A text area with a minimum length of 20 characters.
   ```

   ```text
   Un área de texto con una longitud mínima de 20 caracteres.
   ``` 

* Puede establecer un text area como “obligatoria” si el usuario debe completar un valor antes de enviar el formulario:

   ```text
   A text area that is required.
   ```

   ```text
   Un área de texto que es obligatoria.
   ```
   
En cierto sentido, lo opuesto de un text area con mucho texto es cuando se necesita que el usuario elija entre sólo dos posibilidades simples: sí o no, activado o desactivado, etc. No utilice un text area ni siquiera un text box - cuadro de texto para esto: HTML ofrece un control especial para manejar estas opciones de una u otra, que es el tema de la siguiente sección.

### 8.3.5 Obtener información de sí o no con check boxes - casillas de verificación

Una situación habitual de recopilación de información es cuando se le da al usuario una opción y este la acepta o la rechaza. De manera similar, según la redacción y la intención de la opción, el usuario puede decir sí o no, o puede activarla o desactivarla. Para todos estos escenarios (aceptar/rechazar, sí/no, activar/desactivar), puede incluir en su formulario un control llamado *check boxes - casilla de verificación*. Este es un control que muestra un pequeño cuadrado. Si el usuario desea enviar una respuesta positiva para la check boxes (aceptar o sí o activar), hace clic en la casilla de verificación para agregar una marca de verificación dentro de ella; si, en cambio, el usuario desea enviar una respuesta negativa para la casilla de verificación (rechazar o no o desactivar), hace clic en la check boxes para quitar su marca de verificación.

La figura 8.6 muestra un par de ejemplos de check boxes. La check box superior no está marcada, lo que significa (en este caso) que el usuario no desea recibir notificaciones sobre eventos futuros. La check box inferior está marcada, lo que significa (nuevamente, en este caso) que el usuario desea suscribirse al boletín informativo del sitio. A continuación, se muestra un ejemplo de instrucción para incluir en el prompt del formulario:

```text
A checkbox with the label "Get notified about future events".
```

```text
Una casilla de verificación con la etiqueta "Recibir notificaciones sobre eventos futuros".
```

![image](https://github.com/user-attachments/assets/a6316b09-8561-4160-9910-2ecd36fb4dfb)

**Figura 8.6 Algunos ejemplos de casillas de verificación**

Al solicitarle a ChatGPT que incluya una check box en un formulario, puede personalizar la check box especificando si está marcada inicialmente, como en este ejemplo:


```text
A checkbox with the label "Subscribe to our newsletter" that is initially checked.
```

```text
Una casilla de verificación con la etiqueta "Suscríbete a nuestra newsletter" que está inicialmente marcada.
```

Si desea que sus usuarios elijan entre más de dos opciones, HTML ofrece un par de soluciones, empezando por los radio buttons - botones de opción, que analizamos a continuación.

### 8.3.6 Elección de una de varias opciones con radio buttons - botones de opción

En la sección anterior, aprendiste a permitir que tus usuarios elijan entre dos estados ofreciendo una casilla de verificación. Sin embargo, a menudo sucede que deseas que un usuario elija una de tres o cuatro posibilidades. Por ejemplo, si un evento ocurre el viernes, sábado y domingo, es posible que desees que el usuario elija solo uno de esos días. De manera similar, para regalar una camiseta gratis, puedes pedirle al usuario que elija la talla de camiseta que desea: pequeña, mediana, grande o extra grande.

Cuando necesitas que tus visitantes elijan sólo una de tres o cuatro opciones, puedes añadir a tu formulario un grupo de *radio buttons - botones de opción*, que es un conjunto de elementos HTML con las siguientes características:

* Cada botón es un pequeño círculo.

* Sólo se puede seleccionar un botón a la vez.

* El círculo del botón actualmente seleccionado se rellena.

* Todos los botones no seleccionados tienen círculos vacíos.

* Cuando el usuario hace clic en un botón no seleccionado, el círculo de ese botón se rellena y el círculo del botón previamente seleccionado queda vacío.

La figura 8.7 muestra un ejemplo de un grupo de radio buttons. El botón de opción Medio está seleccionado actualmente.


**Figura 8.7 Un grupo de botones de opción**

Cuando llegue el momento de crear el prompt ChatGPT para un formulario, puede utilizar una instrucción como la siguiente:

```text
A group of radio buttons with the following options: "Small", "Medium", "Large", and "Extra Large".
```

```text
Un grupo de botones de opción con las siguientes opciones: "Pequeño", "Mediano", "Grande" y "Extra grande".
```

Puede personalizar sus botones de opción de la siguiente manera:

* Puede especificar qué botón de opción se selecciona inicialmente:

   ```text
   A group of radio buttons with the following options: "Small", "Medium", "Large", and "Extra Large". The "Medium" radio button is initially selected.
   ```

   ```text
   Un grupo de botones de opción con las siguientes opciones: "Pequeño", "Mediano", "Grande" y "Extragrande". El botón de opción "Mediano" es el seleccionado inicialmente.
   ```

* Puede rodear su grupo de botones de opción con un elemento de “leyenda” y especificar un “título” para esa leyenda. El grupo de botones de opción de la figura 8.7 tiene una leyenda de este tipo con el título `Choose a t-shirt size`. ChatGPT tiende a incluir un elemento de leyenda automáticamente, pero puede usar una instrucción como la siguiente para especificar el título que desea:

   ```text
   A group of radio buttons with the following options: "Small", "Medium", "Large", and "Extra Large". Include a legend element with the caption "Choose a t-shirt size".
   ```

   ```text
   Un grupo de botones de opción con las siguientes opciones: "Pequeño", "Mediano", "Grande" y "Extragrande". Incluye un elemento de leyenda con el texto "Selecciona una talla de camiseta".
   ```

Si necesita que sus usuarios elijan entre más de cuatro opciones, debe colocar esas opciones en una lista de selección, como describo en la siguiente sección.

### 8.3.7 Ofrecer más selecciones con listas

En teoría, no existe un límite razonable en la cantidad de botones de opción que puede ofrecer a sus usuarios. Sin embargo, en la práctica, tener una gran cantidad de radio buttons puede resultar confuso para el usuario y ocupar demasiado espacio en la página. La regla general es tener como máximo cuatro opciones en cualquier grupo de radio buttons.

Sin embargo, no es nada inusual tener cinco o más opciones para presentarles a los usuarios. Tal vez desee que el usuario elija un día de los siete días de la semana (de lunes a domingo). O puede pedirle a un visitante que elija un estado o país (como parte de, por ejemplo, recopilar la dirección de correo del usuario).

Para estas colecciones más grandes de opciones, puede colocar todas las opciones que desea presentar al usuario en una *selection list - lista de selección*, que de manera predeterminada se muestra como una lista desplegable, como se muestra en la figura 8.8. Al hacer clic en la lista, se muestra un menú de las opciones que ha puesto a disposición del usuario, como se muestra en la figura 8.9.

![image](https://github.com/user-attachments/assets/652983e9-fba4-403e-8f4f-3f835ba21d5e)

**Figura 8.8 Una lista de selección aparece inicialmente como una lista desplegable.**

![image](https://github.com/user-attachments/assets/707e46b1-23f0-4451-9dc5-451d0cadadac)

**Figura 8.9 Al hacer clic en la lista de selección se muestran las opciones disponibles.**

A continuación se muestra un ejemplo de instrucción que puede incluir en el prompt del formulario:

```text
A selection list that includes the following items: "None", "Cat", "Dog", "Ferret", "Fish", "Hamster", "Parrot", "Peeve", and "Snake".
```

```text
Una lista de selección que incluye los siguientes elementos: "Ninguno", "Gato", "Perro", "Hurón", "Pez", "Hámster", "Loro", "Molesto" y "Serpiente".
```

Al crear su prompt de formulario ChatGPT, puede personalizar sus selection lists - listas de selección de la siguiente manera:

* Puede especificar qué elemento de la lista se selecciona inicialmente:

   ```text
   A selection list with the following options: "Happy", "Content", "Neutral", "Melancholy", and "Sad." Make "Neutral" the initially selected option. 
   ```

   ```text
   Una lista de selección con las siguientes opciones: “Feliz”, “Contento”, “Neutral”, “Melancólico” y “Triste”. Seleccione “Neutral” como la opción seleccionada inicialmente. 
   ```

* Puede especificar que el usuario pueda seleccionar varios elementos de la lista (manteniendo presionada la tecla Ctrl (Windows) o Cmd (macOS) y haciendo clic en cada elemento):

   ```text
   A selection list with the label "Philosophers You've Read" and the following options: "Plato", "Aristotle", "Blaise Pascal", "Friedrich Nietzsche", and "Jean-Paul Sartre." Allow the user to make multiple selections. 
   ```

   ```text
   Una lista de selección con la etiqueta "Filósofos que ha leído" y las siguientes opciones: "Platón", "Aristóteles", "Blaise Pascal", "Friedrich Nietzsche" y "Jean-Paul Sartre". Permite al usuario realizar múltiples selecciones.
   ```
   

* Puede especificar un tamaño en filas. Esto convierte la lista desplegable en un cuadro de lista normal que muestra la cantidad de filas que especificó. Si la cantidad de filas mostradas es menor que la cantidad de elementos en la lista, el usuario puede desplazarse por el cuadro de lista verticalmente. A continuación, se muestra una instrucción de ejemplo:

   ```text
   A selection list with the label "Dream Vacation" and the options "Beach getaway", "Long-distance hike", "Mountain resort", "Urban exploration", and "Staycation". Give the list a height of five rows.
   ```

   ```text
   Una lista de selección con la etiqueta "Vacaciones de ensueño" y las opciones "Escapada a la playa", "Caminata de larga distancia", "Resort de montaña", "Exploración urbana" y "Estadía en casa". Dale a la lista una altura de cinco filas.
   ```

Ahora que está familiarizado con todos los controles básicos del formulario, está listo para descubrir cómo sus usuarios pueden enviar el formulario.

### 8.3.8 Enviar el formulario con un botón

Cuando trabajas con un cuadro de diálogo en tu computadora, completas los campos (si los hay) y luego haces clic en un botón (generalmente etiquetado como Aceptar) para indicarle a tu aplicación o sistema operativo que ya terminaste con el cuadro de diálogo y que debe procesar los datos del mismo. En cierto sentido, un formulario HTML es el equivalente en una página web de un cuadro de diálogo, lo que significa que tu formulario necesita alguna forma para que el usuario le diga al navegador web que ya terminó con el formulario y que el navegador debe procesarlo. El usuario hace esto haciendo clic en un botón, que es un elemento HTML que se ve y actúa como un botón Aceptar en un cuadro de diálogo de computadora. La Figura 8.10 muestra un ejemplo de un formulario con un botón.

![image](https://github.com/user-attachments/assets/2d366372-28b0-4299-a4fe-fc9a30a51a77)

**Figura 8.10 Un formulario con un botón Enviar**

ChatGPT siempre incluirá un botón llamado Submit - Enviar cuando le solicites que genere el código del formulario. Para especificar el nombre del botón que prefieras, aquí tienes un ejemplo de instrucción para ChatGPT que puedes incluir en el mensaje general del formulario:

```text
A submit button element with the name "Send It".
```

```text
Un elemento de botón de envío con el nombre "Enviarlo".
```

Hacer clic en un botón en un elemento de formulario se denomina *submitting - enviar* el formulario y en la siguiente sección aprenderá cómo recibir los datos del formulario.

Bien, ahora ya sabes todo lo que necesitas saber para solicitarle a ChatGPT que cree un formulario funcional, como describo en la siguiente sección.

## 8.4 Elaboración del prompt para la página de inscripción al evento(event sign-up page)

El proyecto de este capítulo es una página única que contiene un formulario que permite a los usuarios registrarse para participar en un evento local de construcción de graneros. El formulario en sí utilizará los seis tipos de controles que he mencionado anteriormente en este capítulo: un cuadro de texto, un campo de correo electrónico, un área de texto, una casilla de verificación, un grupo de botones de opción, una lista de selección y un botón para enviar el formulario (a text box, an email field, a text area, a check box, a radio button group, a selection list, and a button to submit the form).

Antes de continuar, ya deberías tener un título para el sitio, un eslogan y un título para la página. También deberías saber qué tipografías de Google Fonts quieres para el texto de la página y el esquema de colores que quieres aplicar. Consulta el capítulo 3 para saber cómo obtener ayuda de ChatGPT con títulos, fuentes y colores.

Tu prompt comienza diciéndole a ChatGPT que quieres que te ayude a crear una página web y que no sabes cómo codificar, por lo que tendrá que generar el código por ti:

```text
I want to build a web page that enables page visitors to use a form to sign up for an event. I don't know how to code, so I need you to provide the code for me.
  
First, write the HTML code for a web page that includes the following:
```

```text
Quiero crear una página web que permita a los visitantes de la página utilizar un formulario para registrarse en un evento. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
```

A continuación, especifique el contenido de su página, incluidos los siguientes elementos (consulte la figura 8.11):

* Un header que incluye su logotipo, título del sitio y eslogan.

* Un elemento main que comienza con el título de la página y es seguido por un texto introductorio.

* El formulario que los usuarios pueden enviar para registrarse en su evento.

* Un footer que incluye un aviso de derechos de autor

A continuación, le indica a ChatGPT que genere el CSS para el formato de la página:

```text
Second, in a separate file please write the CSS code for the following:
```

```text
En segundo lugar, en un archivo separado, escriba el código CSS para lo siguiente:
```

A continuación, especifique el formato, incluido lo siguiente:

* El color de fondo de la página y el color del texto.
* Los tamaños de fuente que desea utilizar para el título del sitio, el eslogan, el título de la página, el texto de la página y los controles del formulario.
* Las fuentes a utilizar para los encabezados y el texto de la página normal.
* Un ancho máximo para la página. Esto evita que las líneas de texto sean demasiado largas. Una longitud máxima de 800 px funciona para esta página.

![image](https://github.com/user-attachments/assets/76aee8ca-6a5a-4698-92d9-ef5513aab784)

**Figura 8.11 Los elementos de la página de registro del evento**

A continuación se muestra un ejemplo de solicitud para mi propia página de registro de eventos:

```text
I want to build a web page for an event sign-up page. I don't know how to code, so I need you to provide the code for me.
  
First, write the HTML code for a web page that includes the following:
 * A header element that includes an image named barn.png, the title "Barnstormers!", and the tagline "Building old-fashioned barns the new-fangled way".
 * A main section with the heading "Our Next Barn-Raising".
 * A paragraph with the text "We're looking for volunteers to help with our next barn-raising, which takes place Saturday August 23 and Sunday August 24. If you want to help, please fill out and submit the form below.".
  * Include the code for an HTML form that has the following specifications:
    * In the form element, set the action attribute to "https://getform.io/f/dbb986ea-ee50-42ba-abe7-5c304a087444" and the method attribute to "POST".
    * A text box with the label "Name", a width of 30 characters, and the placeholder "Your name".
    * An email field with the label "Email", a width of 30 characters, and the placeholder "Your email address".
    * A text area with the label "Skills", 3 rows, and 30 columns.
    * A checkbox with the label "Get notified about future barn-raisings".
    * A radio button group with the options "Saturday", "Sunday", and "Both". Select the "Saturday" option. Add a legend element with the caption "Day(s) you can attend".
    * A selection list with the label "Select your free gift" and the options "None", "Baseball cap", "Coffee mug",  "Poster", "T-shirt", and "Tote bag".
    * The following code: <input type="hidden" name="_gotcha" sty1e="display:none !important">
    * A button element with the name "Sign Me Up!".
    * Use paragraphs to separate each form control, except for the radio buttons, which should be separated by line breaks.
  * A footer element that includes the Copyright symbol, followed by the current year, followed by "Barnstormers!".
 * In the page head section, include the tag <meta charset="utf-8">.
 * In the page head section, include the tag <meta name="viewport" content="width=device-width, initial-scale=1">.
  
Second, in a separate file write the CSS code for the following:
 * The page has a 24px margin.
 * The page background color is cornsilk. 
 * The page text color is saddlebrown.
 * Make the header image a maximum width of 150px and floated to the left.
 * The title is 48px, aligned to the right, and with no bottom margin.
 * The tagline is 26px, formatted as italic and small caps, aligned to the right, and with no top margin.
 * The main section has a top margin of 75px.
 * The main section heading font size is 30px.
 * The main section font size is 20px.
 * The form width is 400px and the left margin is 32px.
 * The form, input, textarea, select, and button font size is 20px.
 * The button text color is saddlebrown.
 * For all the page text, use the Bitter font from Google Fonts.
 * The footer has 5px padding all around, 50px top margin, and a saddlebrown top border.
 * Give the page a maximum width of 800px.
```

```text
Quiero crear una página web para una página de inscripción a un evento. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
 * Un elemento de encabezado que incluye una imagen llamada barn.png, el título "Barnstormers!" y el lema "Construyendo graneros antiguos a la manera moderna".
 * Una sección principal con el título "Nuestra próxima construcción de granero".
 * Un párrafo con el texto "Estamos buscando voluntarios que nos ayuden con la próxima construcción del granero, que tendrá lugar el sábado 23 y el domingo 24 de agosto. Si desea ayudar, complete y envíe el formulario a continuación".
  * Incluya el código para un formulario HTML que tenga las siguientes especificaciones:
    * En el elemento de formulario, establezca el atributo de acción en "https://getform.io/f/dbb986ea-ee50-42ba-abe7-5c304a087444" y el atributo de método en "POST".
    * Un cuadro de texto con la etiqueta "Nombre", un ancho de 30 caracteres y el marcador de posición "Su nombre".
    * Un campo de correo electrónico con la etiqueta "Correo electrónico", un ancho de 30 caracteres y el marcador de posición "Su dirección de correo electrónico".
    * Un área de texto con la etiqueta "Habilidades", 3 filas y 30 columnas.
    * Una casilla de verificación con la etiqueta "Recibir notificaciones sobre futuras construcciones de graneros".
    * Un grupo de botones de opción con las opciones "Sábado", "Domingo" y "Ambos". Seleccione la opción "Sábado". Agregue un elemento de leyenda con el título "Día(s) en los que puede asistir".
    * Una lista de selección con la etiqueta "Selecciona tu regalo gratis" y las opciones "Ninguno", "Gorra de béisbol", "Taza de café", "Póster", "Camiseta" y "Bolsa de mano".
    * El siguiente código: <input type="hidden" name="_gotcha" sty1e="display:none !important">
    * Un elemento de botón con el nombre "¡Regístrate!".
    * Utilice párrafos para separar cada control de formulario, excepto los botones de opción, que deben estar separados por saltos de línea.
  * Un elemento de pie de página que incluye el símbolo de Copyright, seguido del año actual, seguido de "¡Barnstormers!".
 * En la sección del encabezado de la página, incluya la etiqueta <meta charset="utf-8">.
 * En la sección del encabezado de la página, incluya la etiqueta <meta name="viewport" content="width=device-width, initial-scale=1">.
  
En segundo lugar, en un archivo separado escriba el código CSS para lo siguiente:
 *La página tiene un margen de 24px.
 *El color de fondo de la página es seda de maíz.
 *El color del texto de la página es marrón silla de montar.
 * Hacer que la imagen del encabezado tenga un ancho máximo de 150 px y flote hacia la izquierda.
 * El título es de 48px, alineado a la derecha y sin margen inferior.
 * El lema mide 26 px, está formateado en cursiva y mayúsculas pequeñas, alineado a la derecha y sin margen superior.
 *La sección principal tiene un margen superior de 75px.
 * El tamaño de fuente del encabezado de la sección principal es 30px.
 *El tamaño de fuente de la sección principal es 20px.
 * El ancho del formulario es de 400 px y el margen izquierdo es de 32 px.
 * El tamaño de fuente del formulario, la entrada, el área de texto, la selección y el botón es 20px.
 * El color del texto del botón es marrón silla de montar.
 * Para todo el texto de la página, utilice la fuente Bitter de Google Fonts.
 * El pie de página tiene un relleno de 5 px alrededor, un margen superior de 50 px y un borde superior de color marrón silla de montar.
 * Dale a la página un ancho máximo de 800px.
```

ChatGPT generará primero el código HTML, que puedes copiar y pegar y guardar en un archivo llamado `index.html`. En ese código, deberías ver una línea cerca de la parte superior similar a la siguiente:

```html
<link rel="stylesheet" type="text/css" href="styles.css">
```

Este código le indica al navegador web que busque el código CSS en un archivo llamado `styles.css`, por lo que la siguiente tarea es copiar el código CSS generado y luego pegarlo y guardarlo en un archivo llamado `styles.css` (o cualquier nombre que vea en la etiqueta `<link>`). Asegúrese de guardar el archivo `styles.css` en la misma carpeta que su archivo `index.html`. También debe copiar su archivo de imagen de encabezado en la misma carpeta. Consulte el apéndice A para obtener más información sobre cómo trabajar con archivos de páginas web.

Utilicé la aplicación ChatGPT de OpenAI para enviar mi prompt a GPT-4. El código generado produjo el resultado, la página que se muestra en la figura 8.12.

![image](https://github.com/user-attachments/assets/84fafe7a-797e-4a3d-a7bf-b036a312b970)


**Figura 8.12 Mi página de registro de eventos - event sign-up page**

Si está satisfecho con la página y el formulario generados por ChatGPT, puede omitir el resto de este capítulo e implementar el código en la web (consulte el apéndice B para obtener más detalles). Sin embargo, si tiene curiosidad por saber más sobre el código de la página web generada, continúe con la siguiente sección para analizarlo en profundidad.

## 8.5 Examinar el código de la página de registro del evento - event sign-up page

No es necesario que sepas cómo funciona el código de la página web generado por ChatGPT. Sin embargo, si quieres profundizar un poco más, las siguientes secciones ofrecen una descripción breve y no demasiado técnica del código de la página de registro de eventos que surgió a partir de mi mensaje de la sección anterior (esa página se muestra en la figura 8.12).

**NOTA**: El código HTML y CSS generado para mi página de registro de eventos están disponibles en el sitio web de este libro ( www.manning.com/books/build-a-website-with-chatgpt ) y en el repositorio de GitHub del libro: https://github.com/paulmcfe/websites-with-chatgpt .

Espero que mis anotaciones de código te ayuden a comprender lo que sucede bajo el capó y te ayuden a ajustar o personalizar tu propio código.

### 8.5.1 Examinar el HTML

Aquí está el código HTML que ChatGPT generó para mi página de registro de eventos:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <meta name="viewport" 
          content="width=device-width, initial-scale=1">         ①
    <title>Barnstormers!</title>
    <link rel="stylesheet" 
          type="text/css" href="styles.css">                     ②
</head>
<body>
    <header>                                                     ⑥
        <img src="barn.png" alt="Barnstormers logo">             ③⑥
        <h1>Barnstormers!</h1>                                   ④⑥
        <p>Building old-fashioned barns the new-fangled way</p>  ⑤⑥
    </header>                                                    ⑥
    <main>
        <h2>Our Next Barn-Raising</h2>
        <p>We're looking for volunteers to help with our next 
           barn-raising, which takes place Saturday August 23 
           and Sunday August 24. If you want to help, please 
           fill out and submit the form below.</p>
        <form action="https://getform.io/f/                      ⑦
              dbb986ea-ee50-42ba-abe7-5c304a087444"              ⑦
              method="POST">                                     ⑦
            <p>
                <label>Name:                                     ⑧
                <input type="text"                               ⑧
                       name="name"                               ⑧
                       size="30"                                 ⑧
                       placeholder="Your name">                  ⑧
                </label>                                         ⑧
            </p>
            <p>
                <label>Email:                                    ⑨
                <input type="email"                              ⑨
                       name="email"                              ⑨
                       size="30"                                 ⑨
                       placeholder="Your email address">         ⑨
                </label>                                         ⑨
            </p>
            <p>
                <label>Skills:                                   ⑩
                <textarea name="skills"                          ⑩
                          rows="3"                               ⑩
                          cols="30">                             ⑩
                </textarea>                                      ⑩
                </label>                                         ⑩
            </p>
            <p>
                <label>                                          ⑪
                <input type="checkbox"                           ⑪
                       name="notify">                            ⑪
                Get notified about future barn-raisings          ⑪
                </label>                                         ⑪
            </p>
            <fieldset>                                           ⑫
                <legend>Day(s) you can attend</legend>           ⑫
                <label>                                          ⑫
                <input type="radio"                              ⑫
                       name="day"                                ⑫
                       value="Saturday"                          ⑫
                       checked>                                  ⑫
                Saturday                                         ⑫
                </label>                                         ⑫
                <br>                                             ⑫
                <label>                                          ⑫
                <input type="radio"                              ⑫
                       name="day"                                ⑫
                       value="Sunday">                           ⑫
                Sunday                                           ⑫
                </label>                                         ⑫
                <br>                                             ⑫
                <label>                                          ⑫
                <input type="radio"                              ⑫
                       name="day"                                ⑫
                       value="Both">                             ⑫
                Both                                             ⑫
                </label>                                         ⑫
            </fieldset>                                          ⑫
            <p>
                <label>Select your free gift:                    ⑬
                <select name="gift">                             ⑬
                    <option value="">None</option>               ⑬
                    <option value="cap">Baseball cap</option>    ⑬
                    <option value="mug">Coffee mug</option>      ⑬
                    <option value="poster">Poster</option>       ⑬
                    <option value="shirt">T-shirt</option>       ⑬
                    <option value="bag">Tote bag</option>        ⑬
                </select>                                        ⑬
                </label>                                         ⑬
            </p>
            <input type="hidden"                                 ⑭
                   name="_gotcha"                                ⑭
                   style="display:none !important">              ⑭
            <p>
                <button type="submit">Sign Me Up!</button>       ⑮
            </p>
        </form>
    </main>
    <footer>© 2023 Barnstormers!</footer>                        ⑯
</body>
</html>
```

① Ayuda a que la página se muestre correctamente en dispositivos móviles

② Le dice al navegador web dónde encontrar el código CSS

③ Logotipo del sitio

④ Título del sitio

⑤ Lema del sitio

⑥ Encabezado de página

⑦ El elemento de formulario especifica el punto final

⑧ Cuadro de texto de nombre

⑨ Cuadro de texto de correo electrónico

⑩ Área de texto de habilidades

⑪ Casilla de verificación

⑫ Cuadro de texto del grupo de botones de opción

⑬ Lista de selección

⑭ Campo oculto de “honeypot”

⑮ Botón Enviar

⑯ Pie de página

A continuación se muestran algunas notas a tener en cuenta al leer el código HTML:

* En el elemento `form `, observe que el atributo `action` está configurado como la dirección del endpoint de Getform. (Tenga en cuenta que he modificado la dirección real, por lo que no intente usar esta dirección en sus propios formularios porque no funcionará).

* Observe que ChatGPT también incluye un atributo `name` para cada control de formulario (excepto el botón). El navegador web utiliza estos valores del atributo `name` para identificar cada campo cuando envía el formulario. La Figura 8.13 muestra un ejemplo de envío. Observe que los nombres de cada campo — `name`, `email`, `skills`, `day`, `gift` y `notify` — coinciden con los valores del atributo `name` del formulario.

![image](https://github.com/user-attachments/assets/0bfaa730-92df-402d-88c6-160fad666f98)

**Figura 8.13 Los envíos de formulario aparecen en su página Getform.**

* Tenga en cuenta también que cada radio button y selection list tiene su propio atributo `value`. Cuando el navegador envía el formulario, envía el valor del radio button y list item seleccionados actualmente. En la figura 8.13, por ejemplo, el valor enviado para el campo `day` (el grupo de radio button) es `Saturday`, y el valor enviado para el campo `gift` (la lista de selección) es `shirt` (es decir, el elemento de camiseta en la lista).

* Justo antes del elemento `button` hay un elemento `input` con su atributo `type` establecido en `hidden` y su atributo `name` establecido en `_gotcha`. Este campo se utiliza para detectar robots de spam, que, cuando envían este formulario, están programados para completar cada campo, incluido este campo oculto. Si el servicio Getform recibe un envío de formulario en el que se completa este campo oculto, sabe que se trata de spam y descarta el envío.

Por último, tenga en cuenta que el código HTML incluye la siguiente línea:

```html
<link rel="stylesheet" href="styles.css">
```

Esta etiqueta le dice al navegador web dónde encontrar el código CSS, que describo en la siguiente sección.

### 8.5.2 Examinando el CSS

Aquí está el código CSS que ChatGPT generó para mi página de registro de eventos:

```css
@import url('https://fonts.googleapis.com/css2?
    family=Bitter:ital, wght@0,400;0,700;1,400
    display=swap');                                  ①
  
body {
    margin: 24px;
    background-color: cornsilk;                      ②
    color: saddlebrown;                              ②
    font-family: 'Bitter', serif;                    ②
    max-width: 800px;                                ③
    margin-left: auto;                               ④
    margin-right: auto;                              ④
}
  
header img {
    max-width: 150px;                                ⑤
    float: left;                                     ⑤
}
  
header h1 {
    font-size: 48px;                                 ⑥
    text-align: right;                               ⑥
    margin-bottom: 0;
}
  
header p {
    font-size: 26px;                                 ⑦
    font-style: italic;                              ⑦
    font-variant-caps: small-caps;                   ⑦
    text-align: right;    
    margin-top: 0;
}
 
main {
    margin-top: 75px;                                ⑧
}
  
main h2 {
    font-size: 30px;                                 ⑨
}
  
main p, form {
    font-size: 20px;                                 ⑩
}
  
form {
    width: 400px;                                    ⑪
    margin-left: 32px;
}
  
form input, form textarea, form select, form button {
    font-size: 20px;                                 ⑫
}
  
form button {
    color: saddlebrown;                              ⑬
}
  
footer {
    padding: 5px;
    margin-top: 50px;
    border-top: solid saddlebrown;
}
```

① Carga la fuente Bitter desde Google Fonts

② Establece el color de fondo de la página, el color del texto y la fuente.

③ Establece el ancho máximo de página en 800 px

④ Centra la página

⑤ Establece un ancho máximo para el logotipo y lo desplaza hacia la izquierda.

⑥ Establece el tamaño de fuente del título de la página a 48 px y lo alinea a la derecha.

⑦ Aplica estilo al eslogan con tamaño de fuente de 26 px, cursiva, mayúsculas pequeñas y alineación a la derecha.

⑧ Agrega un margen en la parte superior del elemento principal

⑨ Establece el tamaño de fuente del encabezado principal

⑩ Diseña el tamaño de fuente del texto de la página normal

⑪ Establece un ancho para el formulario

⑫ Aplica estilo al tamaño de fuente del texto del control del formulario

⑬ Aplica el color del texto al botón.

Si lo desea, puede utilizar estas anotaciones para ayudar a personalizar el código de su página web, como describo en la siguiente sección.

## 8.6 Personalización de la página de registro del evento - event sign-up page

Si el código de formulario generado por ChatGPT no se parece en nada a lo que desea, es mejor iniciar una nueva sesión de chat y enviar un mensaje revisado. Sin embargo, si el código de formulario se parece a lo que buscaba, puede resultar más fácil modificarlo usted mismo.

Primero, aquí hay algunas sugerencias de personalización para el código HTML:

* Siéntete libre de editar cualquier texto de la página, como el título, el eslogan, el texto introductorio o cualquiera de las etiquetas del formulario. Ten cuidado de no editar ni eliminar las etiquetas HTML que rodean cada fragmento de texto (como las etiquetas `<label>` y `</label>` que enmarcan una etiqueta de formulario).

* Si desea incluir un segundo párrafo introductorio, coloque el cursor de edición después de la etiqueta `</p>` que finaliza el párrafo introductorio existente. Presione Enter o Return para comenzar una nueva línea, escriba una etiqueta `<p>`, escriba el texto del párrafo y finalice con una etiqueta `</p>`.

* En el código del formulario, puede editar algunos de los valores de los atributos de las etiquetas. Por ejemplo, con un cuadro de texto, puede modificar los valores de los atributos `size` y `placeholder`; con un área de texto, puede modificar los valores de los atributos `rows` y `cols`; y puede modificar cualquier cadena del atributos `value`. En todos estos casos, asegúrese de modificar únicamente el texto entre las comillas dobles. Además, no cambie los valores de ningún atributo `type` o `name` en el formulario.

* En la sección de footer del código HTML, puedes agregar enlaces a tus cuentas de redes sociales, como describo en el capítulo 4.

A continuación se muestran algunas ideas de personalización para el código CSS:

* Para darle a su página un color de fondo diferente, utilice una palabra clave de color diferente del elemento `body` para la propiedad `background-color`.

* Para utilizar un color diferente para el texto de la página, especifique una palabra clave de color diferente del elemento `body` para la propiedad `color`.

* El código CSS utiliza el color del texto de la página en otros dos lugares: del elemento `form button` y la propiedad `color` y del elemento `footer` la propiedad `border-top`. Para mantener la armonía de los colores, debes reemplazar estos valores de color con la palabra clave de color que hayas utilizado en el elemento anterior.

* Si desea que su página tenga un ancho máximo diferente, cambie el valor `max-width` a algo distinto de `800px`.

* Si prefieres tener el logotipo del encabezado a la derecha y el texto y el eslogan alineados a la izquierda, debes realizar tres cambios:

   * En el elemento `header img`, cambie el valor `float` a `right`.

   * En el elemento `header h1`, cambie el valor `text-align` a `left`.

   * En el elemento `header p`, cambie el valor `text-align` a `left`.

* Para cualquier valor de tamaño de fuente, puede cambiar el número para aumentar o disminuir el tamaño de la fuente. Solo asegúrese de dejar la unidad `px` en su lugar.

* Para cualquier valor de margen o padding, puede cambiar el número para aumentar o disminuir el padding o los márgenes. En cada caso, asegúrese de dejar la unidad `px` en su lugar.

* Para que el código de tu página sea más accesible, considera convertir todas las medidas en px a medidas en rem. 1 rem equivale de manera predeterminada a 16 px, por lo que 20 px son 1,25 rem, 24 px son 1,5 rem, 32 px son 2 rem, 48 px son 3 rem, y así sucesivamente. La unidad rem es más accesible porque mide los tamaños de fuente en relación con el tamaño de fuente predeterminado que el usuario del navegador ha definido en la configuración de su navegador.

## Resumen

* Un formulario es una colección especial de elementos HTML que le permiten recopilar información y luego enviarla a algún lugar (como su dirección de correo electrónico).
* El endpoint de un formulario es la dirección a la que el navegador web envía los datos del formulario cuando el usuario lo envía.
* Un text box - cuadro de texto es un área rectangular diseñada para contener texto escrito por el usuario. Puede configurar cuadros de texto para que contengan tipos de datos especiales, como direcciones de correo electrónico, números y URL.
* Una label  - etiqueta es un texto que describe un control particular.
* Un text area - área de texto es un campo de formulario que admite entradas de texto más largas y de varias líneas.
* Para los tipos de datos sí/no o activado/desactivado, utilice una check box - casilla de verificación.
* Para permitir que el usuario elija una de tres o cuatro opciones, utilice un grupo de radio button - botones de opción.
* Para permitir al usuario elegir entre cinco o más opciones, utilice una selection list - lista de selección.
* Incluya un botón en el formulario para que el usuario pueda enviar los datos del formulario.
* Para obtener mejores resultados, el prompt de su página debe ser lo más específico posible, incluidos colores, tamaños de fuente y niveles de encabezado.
