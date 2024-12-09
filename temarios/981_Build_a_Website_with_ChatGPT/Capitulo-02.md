# 2 Creación e implementación de su primera página web
Este capítulo cubre

Comprender el proceso de creación e implementación de una página web
Uso de un mensaje de ChatGPT para generar una página web completa
Copiar el código de la página web generada
Guardar el código en un archivo HTML
Obtener su archivo de página web en la web
Puede que todavía parezca demasiado bueno para ser verdad que ChatGPT te ayude a crear un sitio web completamente funcional sin tener que aprender ningún código de desarrollo web. Si sigues siendo escéptico, te entiendo: incluso sabiendo un poco sobre cómo funciona ChatGPT, todavía hay un innegable tufillo a magia en toda la empresa. Después de todo, no es como si le estuvieras pidiendo a ChatGPT que te cuente un chiste o que escriba un haiku ensalzando el valor nutricional del colinabo. No, estamos hablando de todo el código necesario para crear una página web que realmente haga algo semi-útil. Es una petición compleja desde cualquier punto de vista, por lo que cualquier escepticismo restante que tengas está totalmente justificado.

En este capítulo, mi objetivo es mostrarte que es posible crear una página web con la ayuda de ChatGPT. No voy a hacerlo explorando más la teoría de ChatGPT. No, ya hemos hablado bastante de eso. En su lugar, te mostraré un ejemplo completo en el que convenzo a ChatGPT para que cree el código para una página web funcional que, al final del capítulo, tendrá su propio hogar en la web. Para lograrlo en un solo capítulo, la página web será, necesariamente, extremadamente simple, pero funcionará e incluso proporcionará un poco de diversión (dependiendo, como verás, de tu gusto por los juegos de palabras).

2.1 Comprender el proceso
Para crear la página web funcional de este capítulo, voy a utilizar el ciclo solicitar-copiar-guardar-implementar que presenté en el capítulo 1 (consulte la figura 2.1):

Pida a ChatGPT que genere el código de la página web.

Copiar el código resultante.

Pegue el código en un editor de texto y luego guárdelo como un archivo HTML.

Implemente el archivo HTML en un servidor web.



Figura 2.1 El ciclo de solicitud-copia-guardado-implementación que utilizará en este capítulo

Las secciones del resto de este capítulo amplían cada uno de estos pasos.

2.2 Cómo solicitar a ChatGPT que genere el código de su página web
Para comenzar, primero debe tener ChatGPT en pantalla. Tiene las siguientes opciones:

Si no tiene una cuenta OpenAI, vaya a https://chat.openai.com para usar GPT-3.5 como modelo.

Si tiene una cuenta OpenAI pero no tiene una suscripción a ChatGPT Plus, vaya a https://chat.openai.com para usar GPT-3.5 como modelo.

Si tiene una suscripción a ChatGPT Plus, vaya a https://chat.openai.com y luego haga clic en el botón GPT-4.

Si prefiere utilizar Bing Copilot, vaya a https://bing.com , haga clic en Copilot y luego haga clic en el estilo de conversación Preciso.

Si tiene una cuenta Microsoft, vaya a https://copilot.microsoft.com y haga clic en el estilo de conversación preciso.

Para mi propia inspiración, utilicé la aplicación ChatGPT con GPT-4 como modelo, como se muestra en la figura 2.2.



Figura 2.2 La aplicación ChatGPT con GPT-4 seleccionado como modelo de lenguaje

Ahora que ChatGPT está listo para hacer lo que le pides, el siguiente paso es darle al modelo un mensaje para que genere algún código de página web. Uno de los puntos que quiero destacar en este capítulo es que es posible lograr que ChatGPT muestre el código para una página web funcional con un solo mensaje. Para lograrlo, tenemos que simplificar mucho las cosas, por lo que no puede ser una página complicada y multifunción con un montón de funciones.

Sin embargo, no tiene por qué ser una página de “¡Hola mundo!” de mala calidad. En general, si tienes una idea para una página sencilla, solo tienes que pedirle a ChatGPT que genere el código para la página e incluya una descripción de lo que quieres. Esa descripción variará según la idea, pero es posible que quieras incluir algunos o todos los siguientes elementos:

Objetivo : lo que desea que ChatGPT genere (en este caso, una página web)

Datos : los datos que desea que ChatGPT utilice, si corresponde

Acción : lo que desea que haga la página web, en general o con los datos que especificó

Interfaz : cómo desea que el usuario inicie la acción o interactúe de otro modo con la página

Aquí está el mensaje para la página que quiero (consulte la figura 2.3):

Crea un código de página web que almacene 50 juegos de palabras y muestre un juego de palabras aleatorio cada vez que el usuario haga clic en un botón.


Figura 2.3 La aplicación ChatGPT con mi mensaje listo para enviar

Así es como este mensaje encaja en el esquema objetivo-datos-acción-interfaz:

Create web page code—Esta parte del mensaje le dice a ChatGPT que genere el código para una página web completa.

that stores 50 puns—Le dice a ChatGPT que cree 50 juegos de palabras para usar como datos de la página.

and displays a random pun—Le dice a ChatGPT que seleccione un juego de palabras al azar de los datos.

each time the user clicks a button—Le dice a ChatGPT que proporcione un botón que, cuando se hace clic, muestre otro juego de palabras aleatorio.

Ingrese el mensaje en el cuadro de texto de ChatGPT, haga clic en el ícono Enviar mensaje y espere el resultado.

2.2.1 Examen del resultado
El siguiente código muestra la primera respuesta que recibí de ChatGPT (el código que ChatGPT genera para usted puede ser diferente):

<!DOCTYPE html>
<html>
<cabeza>
    <title>Generador de juegos de palabras</title>                                                     ①   
    <estilo>
        cuerpo {                                                                       ② 
            familia de fuentes: Arial, sans-serif;                                          ② 
        }                                                                            ② 
        #displayPun {                                                                ③ 
            tamaño de fuente: 24px;                                                         ③ 
            margen superior: 20px;                                                        ③ 
        }                                                                            ③
    </estilo>
</cabeza>
<cuerpo>
    <h1>¡Bienvenido a Pun Generator!</h1>                                               ④
    
    <button id="generatePun">Generar juego de palabras</button>                                   ⑤
    
    ⑥                                                         ​
    <guión>
        var puns = [                                                                 ⑦ 
            "El tiempo vuela como una flecha; la fruta vuela como un plátano.",                  ⑦ 
            "Solía ​​ser panadero porque amasaba.",                         ⑦ 
            "Solía ​​tocar el piano de oído, pero ahora uso mis manos.",                  ⑦ 
            // Agrega el resto de los 50 juegos de palabras aquí...                                   ⑦
        ];    
        documento.getElementById("generatePun").
addEventListener("clic", función() {                                               ⑧ 
            var randomPunIndex = Math.floor(Math.random() * puns.length);            ⑧ 
            document.getElementById("displayPun").innerText = puns[randomPunIndex]; ⑧ 
        });                                                                          ⑧
    </script>
</cuerpo>
</html>
① Título de la página

② Aplica la tipografía Arial a la página.

③ Muestra cada juego de palabras en una fuente de 24 píxeles con un margen de 20 píxeles en la parte superior.

④ Encabezado principal de la página

⑤ Botón en el que el usuario hace clic para obtener un nuevo juego de palabras aleatorio

⑥ Sección de la página donde aparece cada juego de palabras aleatorio

⑦ Datos de página (parciales), que son una colección de juegos de palabras

⑧ Código JavaScript que extrae un juego de palabras aleatorio de los datos

Hay tres cosas que tener en cuenta aquí:

Aunque se trata de una página sencilla, el código en sí es bastante complejo, así que no te preocupes si todo te parece un lenguaje extraño. No necesitas saber cómo funciona este código, solo que funciona (teniendo en cuenta mi tercer punto de esta lista).

Recuerda que ChatGPT no es determinista, lo que significa que no generará el mismo código cada vez, incluso cuando uses el mismo mensaje. Por lo tanto, si ejecutas mi mensaje en ChatGPT, es muy probable que termines con un código diferente al que ves en el listado 2.1.

En lugar de crear 50 juegos de palabras, ChatGPT creó solo tres juegos de palabras y luego pasó la pelota:

// Añade el resto de los 50 juegos de palabras aquí...
Esto no sucede siempre, pero debes saber que es un comportamiento muy común en ChatGPT. Afortunadamente, no significa que estés estancado. Logré que ChatGPT completara su misión con un simple mensaje:

¿Puedes completarme el resto de los juegos de palabras?
ChatGPT regeneró el código con el conjunto completo de juegos de palabras (aunque tuve que hacer clic en el botón Continuar generando (consulte la figura 2.4) una vez cuando ChatGPT se quedó bloqueado). Esa es una cantidad considerable de datos para generar, por lo que tardó un par de minutos en aparecer el código completo.a.



Figura 2.4 Si ChatGPT se bloquea, es posible que tengas que hacer clic en Continuar generando para desbloquearlo.

Comprender y personalizar el código (opcional)

Si deseas comprender y/o personalizar el código generado por ChatGPT (esto es totalmente opcional), aquí te dejamos algunas notas:

HTML consta de una colección de elementos denominados etiquetas para especificar objetos de página, como párrafos, encabezados, listas con viñetas y enlaces. La mayoría de las etiquetas HTML son códigos alfabéticos rodeados de corchetes angulares ( <y >). Por ejemplo, se designa el inicio de un párrafo con la <p>etiqueta y el final del párrafo con la </p>etiqueta . Como otro ejemplo, el código HTML generado por ChatGPT de la sección anterior incluía la siguiente línea:

¡Bienvenido a Pun Generator!
Las etiquetas <h1>y </h1>marcan un encabezado de primer nivel (consulte el capítulo 3 para obtener más información sobre los encabezados), por lo que, en este caso, el texto Welcome to Pun Generator!aparece en la página como dicho encabezado.

CSS consta de una colección de elementos denominados propiedades para especificar el estilo aplicado a los objetos de la página. Por ejemplo, la font-sizepropiedad determina el tamaño del texto de un objeto específico, por lo que para establecer el tamaño en 24px(24 píxeles), se utiliza la siguiente declaración CSS:

tamaño de fuente: 24px;
Tenga en cuenta los dos puntos ( :) después del nombre de la propiedad y el punto y coma ( ;) al final. Las declaraciones CSS se agrupan en reglas , que consisten en el objeto al que se aplican las declaraciones y con esas declaraciones rodeadas por llaves ( {y }), como en este ejemplo del código generado por ChatGPT que se mostró anteriormente:

#mostrarPun {
    tamaño de fuente: 24px;
    margen superior: 20px;
}    
En este ejemplo, #displayPunhay una referencia al siguiente elemento en el código HTML:

<p id="displayPun"></p>
El texto entre las <title>etiquetas </title>y es el título de la página que aparece en la pestaña del navegador. Puedes editar este texto (pero no alteres las etiquetas).

Puedes cambiar el tamaño del texto del juego de palabras modificando el font-sizevalor. Sea cual sea el valor que uses, asegúrate de que esté acompañado de px(para píxeles).

El texto entre las etiquetas <h1>y </h1>es el encabezado de la página principal. Puedes editar este texto (pero no toques las etiquetas).

El botón en el que hace clic el usuario se especifica mediante la <button>etiqueta. El texto que aparece entre esa etiqueta y la </button>etiqueta es lo que aparece en el botón. Puedes editar este texto si lo deseas.

ChatGPT almacena los datos de la página en un objeto de datos especial llamado matriz . En este caso, cada elemento de la matriz es texto (específicamente, un juego de palabras) rodeado de comillas dobles ( "") y seguido de una coma. Puede editar, agregar o eliminar elementos de la matriz según sea necesario; solo asegúrese de que cuando haya terminado, cada elemento de la matriz esté rodeado de comillas dobles y seguido de una coma. Además, no elimine los corchetes ( [y ]) que inician y finalizan la matriz.

Antes de pasar al siguiente paso, voy a tomarme un momento para darte algunas otras sugerencias para un sitio web simple de una sola página.

2.2.2 Eche un vistazo a algunas otras indicaciones para sitios web de una sola página
Si estás siguiendo este tutorial y quieres crear tu propio sitio web de una sola página con la ayuda de ChatGPT, puedes usar mi sugerencia de la sección anterior o puedes usar tu propia sugerencia si tienes una idea que siempre quisiste probar. Si no estás seguro de qué hacer, aquí tienes algunas sugerencias:

ADVERTENCIA ChatGPT tiene una especie de "memoria" para lo que solicitaste y para lo que generó anteriormente en la misma sesión de chat. Antes de intentar cualquiera de las siguientes solicitudes, asegúrate de iniciar un nuevo chat para que los resultados de ChatGPT no se vean afectados por nada anterior en la sesión.

“Crear un código de página web que muestre una lista de diez X cosas para hacer en Y ” (donde X es un adjetivo, como divertido o interesante , e Y es el nombre de una ciudad o un barrio). Ejemplo:

Crea un código de página web que muestre una lista de diez cosas entretenidas para hacer en el área de South Beach de Miami.
“Generar el código para una página web que proporcione una receta para preparar X ” (donde X es una cena, postre u otro tipo de plato que se pueda cocinar desde cero). Ejemplo:

Generar el código para una página web que proporcione una receta para hacer panna cotta.
“Proporcionar un código de página web que enumere los pasos necesarios para X ” (donde X es un proyecto, un trabajo de reparación, una tarea de mantenimiento u otra tarea). Ejemplo:

Proporciona el código de la página web que enumera los pasos necesarios para reemplazar un grifo del baño.
“Crear código de página web que explique cómo funciona X ” (donde X es una máquina, un dispositivo, un principio científico o, en realidad, cualquier cosa). Ejemplo:

Crear código de página web que explique cómo funciona un holograma.
“Generar el código para una página web que almacena X y muestra una Y aleatoria cuando el usuario hace clic en un botón” (donde X son algunos datos e Y son los datos combinados de alguna manera). Ejemplo:

Generar el código para una página web que almacene una docena de cada uno de los siguientes: nombres, verbos, colores, adjetivos y sustantivos. Cuando el usuario haga clic en un botón, el código debe ensamblar y mostrar una oración aleatoria que utilice la plantilla "Nombre verbo el color, adjetivo sustantivo".
“Proporcione un código de página web que muestre X en una lista y almacene una Y asociada con cada X. Cuando el usuario elige X de la lista, la página muestra la Y asociada ” (donde X podría ser una palabra, persona u objeto e Y podría ser un poema, una biografía o una descripción).

Proporcionar un código de página web que muestre seis adjetivos poco utilizados en una lista desplegable y almacene un poema asociado con cada adjetivo. Cuando el usuario elige un adjetivo de la lista, la página muestra el poema asociado.
Siéntete libre de utilizar los mensajes de ejemplo tal como están o personalizándolos para adaptarlos a la página que desees.

2.3 Copiar el código de la página web de ChatGPT
Una vez que ChatGPT haya terminado de generar el código, el siguiente paso es copiarlo. La forma de copiar el código generado depende de si estás usando la aplicación ChatGPT, Bing Copilot o la barra lateral de Copilot en Microsoft Edge. Cada interfaz ofrece una función Copiar código en forma de icono o botón. Para conocer todos los detalles sobre cómo copiar código en cada interfaz, consulta el apéndice A. Si, como yo, estás usando la aplicación ChatGPT, el código aparece en una ventana de código HTML independiente que tiene un botón Copiar código en la esquina superior derecha, como se muestra en la figura 2.5.



Figura 2.5 Para copiar el código generado en la aplicación ChatGPT, haga clic en Copiar código en la esquina superior derecha de la ventana de código.

El código copiado ahora se encuentra en el Portapapeles de su computadora, que es un área de memoria especial que almacena los datos copiados más recientemente. Para evitar que el código copiado se sobrescriba en el Portapapeles, asegúrese de pasar al siguiente paso antes de hacer cualquier otra cosa en su computadora (especialmente copiar o cortar cualquier otro dato).

2.3.1 Guardar el código de la página web en un archivo HTML
Ahora que ha copiado el código de la página web generada por ChatGPT, el siguiente paso es pegar el código copiado en un archivo de texto y luego guardar ese documento como un archivo HTML. Antes de comenzar, utilice el Explorador de archivos (Windows) o Finder (macOS) para crear una subcarpeta para almacenar todos sus proyectos web. Por ejemplo, puede crear una carpeta llamada sites o public_html en la carpeta Documentos de su cuenta de usuario.

Una vez hecho esto, estos son los pasos a seguir para guardar el código ChatGPT copiado en un archivo HTML:

Abra su editor de texto.

Inicia un nuevo archivo de texto. En la mayoría de los editores de texto, elige Archivo > Nuevo (o, según la aplicación, es posible que tengas que elegir un comando diferente, como Nuevo archivo, Nuevo archivo de texto o Nuevo documento). También puedes presionar Ctrl-N (en Windows) o Cmd-N (macOS).

Seleccione Editar > Pegar para pegar el código copiado en el nuevo archivo de texto. También puede presionar Ctrl+V (en Windows) o Cmd+V (macOS).

Seleccione Archivo > Guardar. También puede presionar Ctrl+S (en Windows) o Cmd+S (macOS). La aplicación muestra el cuadro de diálogo Guardar como.

Navega a la carpeta que creaste anteriormente (la que se llama sites o public_html o como sea) para almacenar tus proyectos web.

Haga clic en el botón Nueva carpeta y, a continuación, introduzca un nombre para la carpeta. En la siguiente sección, subirá esta carpeta a la Web, por lo que el nombre que utilice debe constar únicamente de letras minúsculas, números, guiones (-) y/o guiones bajos (_). No se permiten espacios.

Para el nombre del archivo, escriba index.html.

Haga clic en Guardar. La aplicación guarda su archivo HTML. La figura 2.6 muestra mi generador de juegos de palabras.de guardado como archivo HTML.



Figura 2.6 El código generado por ChatGPT guardado como un archivo HTML

Cerca de la parte superior de la figura 2.6, observe que mi editor de texto muestra la ruta del archivo HTML:

paul/Documentos/public_html/pun-generator/index.html
Esta ruta significa que en la carpeta Documentos de mi cuenta de usuario, creé una subcarpeta llamada public_html para almacenar todos mis sitios web. Siguiendo los pasos anteriores, primero navegué hasta public_html, creé la nueva subcarpeta pun-generator y luego guardé el código como index.html en esa nueva carpeta.

Ahora está listo para probar su página en un navegador web.

2.4 Probar su página web en el navegador
Una vez que el código de su página web esté guardado en un archivo en su computadora, siempre es una buena idea realizar una revisión rápida de la página antes de implementarla. La forma más fácil de probar una página web es abrir el archivo HTML en su navegador web favorito. Estos son los pasos a seguir:

En su navegador web, muestre el cuadro de diálogo Abrir:

Navegador web de Windows: presione Ctrl-O.

Navegador web de Mac: seleccione Archivo > Abrir archivo o presione Cmd-O.

En el cuadro de diálogo Abrir, navegue hasta la carpeta donde almacenó el archivo HTML en la sección anterior.

Seleccione el archivo HTML.

Haga clic en Abrir.

El navegador web abre el archivo HTML y muestra la página web de acuerdo con las etiquetas HTML y las propiedades CSS.

Abrir la página web desde tu computadora es una excelente opción para probarla, pero si quieres verla en la web, debes implementarla.

2.5 Despliegue de su página web
Para implementar su página, debe cargar el archivo HTML en su servidor web. La forma de hacerlo depende del servidor, por lo que debe consultar las páginas de soporte del servidor para conocer el procedimiento específico. Estos son los pasos generales que debe seguir en la mayoría de los servidores web:

   1. Inicie sesión en su proveedor de alojamiento web.

   2. Navega a la página donde cargas los archivos de tu página web.

   3. Sube la subcarpeta que creaste en la sección anterior, incluyendo el archivo .archivo de la carpeta del sombrero index.html.

Para este ejemplo, voy a implementar mi generador de juegos de palabras en Cloudflare siguiendo estos pasos (aunque consulte el apéndice B para obtener instrucciones más específicas):

   4. En la barra lateral de navegación del panel de Cloudflare, en Trabajadores y páginas, haga clic en Descripción general.

   5. Haga clic en el botón Crear aplicación, que se muestra en la figura 2.7. (Si esta es su primera implementación de Cloudflare, no tendrá el botón Crear aplicación en pantalla. En ese caso, omita este paso).



Figura 2.7 En la página Descripción general, haga clic en Crear aplicación.

   6. Haga clic en la pestaña Páginas.

   7. Desplácese hacia abajo hasta la sección Crear usando carga directa y luego haga clic en Cargar activos.

   8. Escriba un nombre para su proyecto y luego haga clic en Crear proyecto, como se muestra en la figura 2.8.



Figura 2.8 Escriba un nombre para el proyecto y luego haga clic en Crear proyecto.

   9. Cargue la carpeta de su sitio utilizando uno de los siguientes métodos:

  a) Arrastre la carpeta de su sitio web y suéltela en el área de carga.

  b) Haga clic en Seleccionar desde el equipo y, a continuación, haga clic en Cargar carpeta. En el cuadro de diálogo que aparece, navegue hasta la carpeta del proyecto y, a continuación, haga clic en Cargar.

  10. Si su navegador web le pide que confirme la operación, haga clic en Cargar.

  11. Haga clic en Implementar sitio.

  12. Haga clic en el enlace para ver el sitio implementado en el navegador web. La Figura 2.9 muestra mi Generador de juegos de palabras implementado en https://pun-generator.pages.dev .



Figura 2.9 El sitio web Pun Generator implementado en Cloudflare Pages.

Ahí lo tienes: una página web creada con la ayuda de ChatGPT y desplegada en la web en tan solo unos pocos pasos. Sí, la página que creaste fue sencilla, pero el resto de este libro está dedicado a mostrarte cómo lograr que ChatGPT te ayude a crear sitios web mucho más sofisticados y útiles.

Resumen
El proceso básico para obtener la ayuda de ChatGPT para crear una página web es el ciclo solicitar-copiar-guardar-implementar.

Al solicitar ChatGPT, incluya un objetivo, los datos que necesita, la acción que desea que realice la página y la interfaz con la que el usuario inicia la acción.

Si ChatGPT no le brinda todo lo que solicita, ejecute un segundo mensaje para solicitar la información faltante.

Copie el código generado haciendo clic en el icono o botón Copiar código.

Utilice la aplicación de administración de archivos de su sistema operativo para crear una carpeta en la que almacenará todos sus proyectos web.

En su editor de texto, pegue el código copiado en un nuevo archivo de texto y luego guarde ese archivo como index.html en una nueva subcarpeta creada para el proyecto.

Implemente el sitio web cargando los datos del proyecto en su proveedor de alojamiento web.
