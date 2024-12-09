# Apéndice A. Preparación para crear páginas web con ChatGPT
Además del material introductorio del capítulo 1, el objetivo de este libro es mostrarle cómo convencer a ChatGPT para que lo ayude a crear páginas web sin tener que aprender a codificarlas usted mismo. Espero que las ideas para páginas web del libro y las indicaciones que se utilizan para generarlas le resulten útiles, ya sea directamente o como puntos de partida para explorar por su cuenta.

Usar ChatGPT como asistente de codificación web no es tan complejo como aprender a codificar páginas por tu cuenta, pero sí requiere un poco de configuración y un mínimo de infraestructura. Este apéndice trata sobre las pocas cosas que necesitas saber y las pocas tareas que necesitas hacer antes de que puedas lograr que ChatGPT te ayude a convertir tus ideas de sitio web en algo real. Después de revisar una lista de requisitos afortunadamente corta, aprenderás a configurar una cuenta opcional de ChatGPT o Microsoft. También aprenderás a probar tu código antes de implementarlo y a trabajar con HTML y otros archivos de páginas web.

## A.1 Qué necesitas para empezar

Una de las mejores cosas de usar ChatGPT para ayudarte a crear páginas web es que puedes empezar con muy pocos requisitos y sin gastar ni un céntimo de tu dinero ganado con tanto esfuerzo (a menos que quieras hacerlo). De hecho, puedo resumir todo lo que necesitas para empezar a trabajar en una lista de tan solo cuatro elementos:

* **Acceso a Internet**: aunque puede usar la aplicación móvil ChatGPT sin conexión, la aplicación OpenAI ( https://chat.openai.com ), Bing Copilot ( https://bing.com y luego haga clic en Copilot) y Microsoft Copilot ( https://copilot.microsoft.com ), cualquiera de las cuales necesita para acceder fácilmente al código generado por ChatGPT, son solo en línea, por lo que necesita acceso a Internet.

* **Navegador web**: puedes acceder a la aplicación OpenAI y a Bing Copilot usando cualquier versión reciente de un navegador importante (como Chrome, Safari, Edge o Firefox). Pero para usar Microsoft Copilot, necesitas usar Chrome o Microsoft Edge. Mientras escribo esto, estamos trabajando en la compatibilidad con Firefox y Safari.

* **Editor de texto**: después de copiar el código generado por ChatGPT, debes pegarlo en algún lugar, y ese lugar casi siempre es un archivo abierto en un editor de texto. Sí, puedes usar el editor de texto predeterminado que viene con tu computadora (Bloc de notas para Windows o TextEdit para macOS), pero aquí hay algunos editores compatibles con código que puedes considerar:

   * **Notepad++**: disponible solo para Windows y es gratuito: https://notepad-plus-plus.org

   * **Nova**: disponible para Mac por $99, pero hay una versión de prueba gratuita disponible: https://nova.app

   * **Sublime Text**: disponible para Windows y Mac por $99, pero hay una versión de prueba gratuita disponible: www.sublimetext.com

   * **Visual Studio Code**: disponible para Windows y Mac, y también gratuito: https://code.visualstudio.com

* **Cuenta de alojamiento web**: una vez que hayas guardado el código generado por ChatGPT en un archivo de página web, el paso final es implementar el archivo en la web. Para ello, necesitas una cuenta con un proveedor de alojamiento web. Hablo sobre la configuración de cuentas de alojamiento web y la implementación de tu código web con más detalle en el apéndice B. Si no tienes un proveedor de alojamiento web, puedes ver tus páginas localmente usando el comando `File > Open` de tu navegador web para abrir el archivo HTML guardado de cada página.

**NOTA**: si va a utilizar sus propias fotografías en sus páginas web (consulte el capítulo 10), es posible que necesite una aplicación de edición de fotografías para tareas como recortar, mejorar los colores y cambiar el tamaño de la imagen y el formato de archivo. Las aplicaciones de Fotos que se incluyen con Windows y macOS pueden realizar estas operaciones sencillas, pero para tareas más complejas, necesitará un software de gama alta como Adobe Photoshop ( www.adobe.com/products/photoshop.html ) o GIMP ( www.gimp.org ), que es gratuito.

Sí, eso es todo lo que necesitas y ninguno de estos elementos tiene por qué costarte dinero extra (suponiendo que pagarías por el acceso a Internet incluso si no usaras ChatGPT para crear páginas web). La única excepción que podrías querer hacer es pagar una suscripción a ChatGPT, que analizo en la siguiente sección.

## A.2 Comprensión del acceso a la cuenta ChatGPT

ChatGPT es un producto de OpenAI, que cuenta con el respaldo de Microsoft. Por lo tanto, parecería razonable esperar que necesites una cuenta de OpenAI o una cuenta de Microsoft para conversar con ChatGPT. ¿Es eso cierto? Sorprendentemente, la respuesta es no, a menos que quieras una. Entonces, ¿deberías obtener una cuenta para acceder a ChatGPT? Estos son los escenarios que debes considerar:

* **Maximizar la privacidad (sin cuenta)**: Muchas personas se resisten a enviar datos privados a grandes corporaciones (como OpenAI y Microsoft), por lo que acceder a ChatGPT sin una cuenta hace que todo el proceso sea un poco más privado. Puedes acceder a la aplicación Open AI ChatGPT sin una cuenta, pero estás restringido a usar GPT 3.5. Para usar ChatGPT sin una cuenta Microsoft, necesitas acceder a Copilot a través de Bing. Sin embargo, ten en cuenta que sin una cuenta Microsoft, estás restringido a solo 10 respuestas de ChatGPT por sesión (en comparación con las 30 respuestas por sesión que obtienes cuando inicias sesión con una cuenta Microsoft).

* **Obtener acceso gratuito a GPT-4 (cuenta Microsoft)**: GPT-4 es (al menos mientras escribo esto) el último y mejor modelo de lenguaje grande (LLM) de OpenAI, por lo que es el que la mayoría de las personas quieren usar, especialmente para generar código web. Puede pagar a OpenAI para obtener acceso a GPT-4 (como explico en la última de estas viñetas), pero una alternativa es navegar a Microsoft Copilot, que usa GPT-4 como su LLM. Para aprovechar al máximo Bing Copilot (y para acceder al sitio independiente de Microsoft Copilot), cree una cuenta Microsoft y úsela para iniciar sesión, o use su cuenta Microsoft existente si es un usuario de Windows. Para crear una cuenta Microsoft, vaya a https://account.microsoft.com, haga clic en Iniciar sesión y luego siga los pasos.

* **Cómo obtener acceso gratuito a GPT-3.5 (cuenta gratuita de OpenAI)**: GPT-3.5 es un fantástico modelo de IA que produce código de páginas web útil y confiable. Si desea obtener acceso gratuito a GPT-3.5 y por alguna razón no puede (o no quiere) usar Copilot para obtener acceso gratuito a GPT-4 (como se describe en el punto anterior), puede configurar una cuenta gratuita de OpenAI. Tener una cuenta le da acceso a algunas funciones adicionales de ChatGPT que no están disponibles para las personas que usan ChatGPT sin una cuenta (como se describe en el primer punto). Para crear una cuenta gratuita de OpenAI, vaya a https://openai.com, haga clic en Registrarse y luego siga los pasos.

* **Obtener acceso pago a GPT-4 (suscripción a ChatGPT Plus)**: si desea utilizar GPT-4 y por alguna razón no puede (o no quiere) utilizar Bing Copilot o Microsoft Copilot para obtener acceso gratuito a GPT-4 (como se describe en un punto anterior), debe configurar una suscripción a ChatGPT Plus, que, mientras escribo esto, le costará US$ 20 por mes. Para configurar una suscripción a ChatGPT Plus, cree una cuenta gratuita de OpenAI (como se describe en el punto anterior), acceda a la aplicación ChatGPT ( https://chat.openai.com), haga clic en Actualizar en la esquina inferior izquierda (consulte la figura A.1) y luego siga las instrucciones.

<img width="838" alt="image" src="https://github.com/user-attachments/assets/6847f439-76a6-46df-ab4f-0b13a91b544e">

**Figura A.1 Para configurar una suscripción a ChatGPT Plus, haga clic en Actualizar en la barra lateral de la aplicación ChatGPT.**

## A.3 Probar su código

ChatGPT ha sido entrenado con una cantidad inimaginable de código de programación, por lo que (normalmente) es tan bueno generando las funcionalidades de las páginas web que solicitas. Pero ChatGPT no es infalible, lo que significa que a veces producirá código HTML, CSS o JavaScript que no hace lo que solicitaste o que está roto de alguna manera. Un programador profesional normalmente puede examinar el código generado y entender no solo que el código es incorrecto, sino también por qué lo es. Estás leyendo este libro porque no eres un programador profesional, así que ¿cómo sabrás si ChatGPT ha generado algún código erróneo?

La respuesta es que se consigue que un navegador web represente el código y luego se examina el resultado para ver si el código funciona como se supone que debe hacerlo (o si funciona en absoluto). Una forma de conseguir que un navegador web represente el código de ChatGPT es ejecutar el ciclo completo de solicitud-copia-guardado-implementación. Ese proceso no es particularmente oneroso, pero tampoco es trivial, por lo que parece excesivo si solo se quiere saber, por ejemplo, si el código generado por ChatGPT para un formulario funciona como se espera.

Un método mejor y más rápido es probar únicamente el código generado por ChatGPT, lo que se hace copiando el código y pegándolo en uno de los espacios de programación en línea disponibles. Las dos secciones siguientes brindan los detalles.

### A.3.1 Copiar datos desde ChatGPT

Una vez que ChatGPT haya terminado de generar el código, el primer paso es copiarlo al portapapeles de su computadora. (El portapapeles es un área de memoria especial que su computadora utiliza para almacenar el elemento más reciente que ha copiado). La forma de hacerlo depende del método que esté utilizando para acceder a ChatGPT:

* **Aplicación OpenAI ChatGPT**: haga clic en el botón Copiar código en la esquina superior derecha de la ventana de código (como se muestra en la figura A.2).

<img width="678" alt="image" src="https://github.com/user-attachments/assets/e452782c-8d89-4477-b743-8edb5bb149d5">

**Figura A.2 En la aplicación OpenAI ChatGPT, haga clic en el botón Copiar código de la ventana de código para copiar el código generado.**

* **Microsoft Copilot**: haga clic en el botón Copiar que aparece arriba y a la derecha del código (como se muestra en la figura A.3).

<img width="677" alt="image" src="https://github.com/user-attachments/assets/f17b757b-fb83-498d-bbbb-670346b82678">

**Figura A.3 En Copilot, haga clic en el botón Copiar para copiar el código generado.**

**ADVERTENCIA** El portapapeles de su computadora solo puede almacenar un elemento copiado a la vez. Si copia algo más antes de pegar su código ChatGPT (como describo en la siguiente sección), ese código se borrará de la memoria y deberá copiarlo todo nuevamente.

### A.3.2 Pegar datos en un espacio de programación en línea

Una vez que hayas copiado el código generado por ChatGPT en el portapapeles de tu computadora, el siguiente (y último) paso es pegar el código en un web coding playground en línea. Un *playground* es un sitio web que acepta código HTML, CSS y, a menudo, JavaScript, y luego muestra cómo se mostrará ese código en el navegador web. Al usar un playground para probar tu código, evitas la molestia de guardar el código en un archivo y luego implementar el archivo en un servidor web, lo cual es demasiado trabajo cuando solo quieres ver si una sección o un componente de la página funciona correctamente.

A continuación se muestran algunos web coding playgrounds que puedes consultar:

* **Web Design Playground**: este es un sitio web complementario de mi libro ***Web Design Playground***, que enseña HTML y CSS para principiantes. Como se muestra en la figura A.4, el sitio web ofrece un “sandbox” que incluye editores HTML y CSS en los que puedes pegar código HTML y CSS generado por ChatGPT. Haz clic en Ejecutar código y el área de resultados inferior muestra cómo se ve el código en el navegador. Navega a https://webdesignplayground.io/new para probarlo.

<img width="824" alt="image" src="https://github.com/user-attachments/assets/7bfaba77-f7a8-4956-b401-21654b5f91b7">

**Figura A.4 Web Design Playground ofrece editores HTML y CSS en los que puede pegar código HTML y CSS para realizar pruebas.**

* **WebDev Workbench**: este es un entorno de pruebas que creé para ayudar a los desarrolladores web a probar código HTML, CSS y JavaScript. Como se muestra en la figura A.5, el entorno de pruebas ofrece pestañas HTML, CSS y JavaScript en las que puedes pegar código HTML, CSS y JavaScript proporcionado por ChatGPT. Haz clic en Ejecutar y el área de resultados inferior muestra cómo se ve el código en el navegador. Navega a https://webdevworkshop.io/wb para comprobarlo.

<img width="741" alt="image" src="https://github.com/user-attachments/assets/78c4486f-c211-4845-b767-b88727380ca5">

**Figura A.5 WebDev Workbench ofrece pestañas para HTML, CSS y JavaScript en las que puede pegar el código ChatGPT para realizar pruebas.**

* **CodePen**: este es un sitio popular para probar el código de páginas web. Crea un “pen” que incluye editores para código HTML, CSS y JavaScript, como se muestra en la figura A.6. Unos segundos después de pegar, el resultado generado aparece automáticamente en el marco inferior. Navega a https://codepen.io y luego haz clic en Comenzar a codificar para probarlo.

<img width="832" alt="image" src="https://github.com/user-attachments/assets/14dec310-9486-4c28-87ae-f477849e15e4">

**Figura A.6 CodePen ofrece editores para HTML, CSS y JavaScript. Pegue el código de ChatGPT en el editor adecuado para probar el código.**

Todos estos playgrounds funcionan más o menos de la misma manera:

1. Copia tu código ChatGPT.
2. Navega hasta el playgrounds.
3. Haga clic dentro del editor que corresponde al tipo de código que está probando (por ejemplo, utilice el editor HTML para el código HTML).
4. Haga clic en el botón que ejecuta el código (o, en el caso de CodePen, simplemente espere unos segundos).

**NOTA**: si ChatGPT genera código HTML que también incluye código CSS (entre las etiquetas `<style>` y `</style>`), es mejor copiar el CSS por separado (ignorando las etiquetas `<style>` y `</style>`) y pegarlo en el editor CSS del playground. De manera similar, si ChatGPT genera código HTML que también incluye código JavaScript (entre las etiquetas `<script>` y `</script>`), copie el código JavaScript por separado (omita las etiquetas `<script>` y `</script>`) y péguelo en el editor JavaScript. Para evitar el trabajo adicional de extraer CSS y JavaScript del código HTML generado, incluya en su mensaje que desea que ChatGPT muestre el HTML, CSS y JavaScript por separado. ChatGPT debe colocar el código HTML en una ventana HTML, el código CSS en una ventana CSS separada y el código JavaScript en una ventana JavaScript separada.

Mientras trabajas con ChatGPT, es una buena idea mantener tu playground favorita abierta en su propia pestaña del navegador. De esa manera, tan pronto como ChatGPT genere un nuevo código para ti, puedes copiar y pegar el código inmediatamente en la playground para comprobar que funciona.

## A.4 Trabajar con archivos de páginas web

Aunque pasará la mayor parte de su tiempo solicitando a ChatGPT que produzca el código y el texto de la página web que desea publicar, en algún momento deberá incluir ese código en uno o más archivos que pueda implementar. Para ayudar con esta parte de "guardar" del ciclo de solicitud-copia-guardar-implementar, el resto de este apéndice le indica lo que necesita saber.

### A.4.1 Comprensión de los diferentes tipos de archivos de páginas web

Una de las cosas sorprendentes y asombrosas de la web es que todo lo que vemos, desde la página de inicio más humilde hasta el sitio web de la megacorporación más poderosa, no tiene nada más que texto subyacente. ¿Cómo lo sé? Porque cada página web consta de uno o más archivos, y todos los tipos de archivos que admite la web son variaciones del tema de los archivos de texto. (Aquí estoy ignorando los archivos de imagen, video y audio, que se entregan por separado). De hecho, la mayoría de las páginas web constan de alguna combinación de los siguientes tres tipos de archivos:

* **HTML**: estos archivos utilizan la extensión `.html` (o, en ocasiones, `.htm`) y proporcionan la estructura básica de una página web. Todos los sitios web incluyen al menos un archivo HTML (que suele llamarse `index.html`).

* **CSS**: estos archivos utilizan la extensión `.css` y proporcionan la apariencia general de una página web al definir reglas de estilo para cosas como fuentes, colores, bordes y diseño.

* **JavaScript**: estos archivos utilizan la extensión `.js` y agregan interactividad a una página web.

Cuando utilices archivos separados de esta manera, tendrás que hacer referencia a ellos desde tu archivo HTML, algo que aprenderás a hacer en breve. Sin embargo, por ahora, tendrás que aprender a pegar el código generado por ChatGPT en un archivo de página web.

### A.4.2 Pegar datos de ChatGPT en un archivo HTML

Una página web sencilla puede utilizar un único archivo HTML que incluya código CSS y JavaScript. El código CSS va entre las etiquetas `<style>` y `</style>` en una sección de encabezado especial de la página, y el código JavaScript va entre las etiquetas `<script>` y `</script>`, normalmente cerca de la parte inferior del archivo HTML. A continuación, se muestra el diseño general de un archivo HTML de este tipo:

<img width="830" alt="image" src="https://github.com/user-attachments/assets/6da1930d-144b-47e5-947a-a5c376bd2ff4">

① El código CSS va aquí.

② Las etiquetas HTML y el texto van aquí.

③ El código JavaScript va aquí.

Utilice este código como punto de partida para todos sus proyectos de páginas web sencillas. (Aprenderá a hacer que ChatGPT genere una plantilla similar en el capítulo 6). Con esta plantilla en su lugar, aquí es donde pega el código generado por ChatGPT:

* **CSS**: Pegue el código debajo de la etiqueta `<style>` pero encima de la etiqueta `</style>`.

* **HTML**: pegue el código debajo de la etiqueta `<body>` pero encima de `<script>`. Los distintos componentes de la página deben aparecer en el archivo en el mismo orden en que desea que aparezcan en la página. Le daré instrucciones de ubicación más específicas en los capítulos en los que se generan los componentes de la página.

* **JavaScript**: pegue el código debajo de la etiqueta `<script>` pero encima de la etiqueta `</script>`.

Sin embargo, recuerda que este enfoque de todo el código en un solo archivo solo es adecuado para las páginas web más simples. Cuando tus páginas se vuelvan un poco más complejas, deberás crear archivos separados para el CSS y el JavaScript, como describo a continuación.

### A.4.3 Referenciar archivos CSS y JavaScript en un archivo HTML

Colocar el código CSS y JavaScript en archivos separados simplifica y ordena el archivo HTML y también te permite aplicar el mismo código CSS y JavaScript a varias páginas web, lo que puede suponer un gran ahorro de tiempo. Suponiendo que ya hayas guardado el código CSS y JavaScript en archivos `.css` y `.js` separados, respectivamente, agrega referencias a los archivos en cualquier archivo HTML en el que quieras usar el código CSS o JavaScript:

<img width="829" alt="image" src="https://github.com/user-attachments/assets/abff29d1-896d-4da7-b8c5-33427f3955df">

① Utilice la etiqueta <link> para hacer referencia a un archivo CSS.

② Utilice la etiqueta <script> para hacer referencia a un archivo JavaScript.

Aquí están los detalles:

* **CSS**: entre la etiqueta `<head>` y la etiqueta `</head>`, agregue una etiqueta `<link>` y establezca el atributo `href` igual al nombre del archivo CSS rodeado de comillas.

* **JavaScript**: justo encima de la etiqueta `</body>`, agregue una etiqueta `<script>` con su atributo `src` establecido en el nombre del archivo JavaScript rodeado de comillas y luego agregue una tag `</script>`.

Para reutilizar un archivo CSS o JavaScript en varios archivos HTML, incluya la misma etiqueta `<link>` o rótulo `<script>` en esos archivos.

### A.4.4 Guardar su trabajo

Una vez que hayas realizado cambios en un archivo HTML, CSS o JavaScript, debes guardarlos inmediatamente para evitar perder tu trabajo. A continuación, se incluyen algunas notas que debes tener en cuenta al guardar archivos nuevos por primera vez:

* Asegúrese de utilizar la extensión de archivo correcta: `.html` para archivos HTML, `.css` para archivos CSS y `.js` para archivos JavaScript.

* Si su sitio consta de una sola página HTML, nómbrela `index.html`. Si su sitio consta de varias páginas, nómbrela `index.html` para la página principal.

* No utilice espacios ni símbolos inusuales en los nombres de archivo. Utilice únicamente caracteres alfanuméricos, guiones(-) o guiones bajos(_).

* En la mayoría de los servidores web, los nombres de archivo distinguen entre mayúsculas y minúsculas, lo que significa que, por ejemplo, `index.html`, `Index.html` e `INDEX.html` se tratarían como archivos independientes. Lo mejor es utilizar todas las letras en minúscula en los nombres de archivo.

* Mantenga los nombres de archivo lo más breves posible sin que resulten confusos. El nombre `about.html` es mejor que `a-few-words-about-this-project.html`, pero `nlsup.html` es peor que `newsletter-signup.html`.

* Asegúrate de guardar todos los archivos asociados a un único sitio web (es decir, no solo todos los archivos HTML, CSS y JavaScript, sino también todos los archivos de imagen, vídeo y audio) en una única carpeta. Esto te facilita mucho la tarea de implementar tu sitio, como describo en el apéndice B.
