# 13 Codificación de un catálogo de cursos interactivo

Este capítulo cubre

* Cómo preparar los datos de Excel para su uso en la Web
* Aprendiendo sobre el formato de datos JSON
* Cómo usar ChatGPT para convertir datos de Excel a JSON
* Uso de datos JSON para hacer que una página web sea interactiva
* Cómo crear un mensaje de ChatGPT para una página del catálogo de cursos
* Examinar y personalizar el código generado por ChatGPT

Los proyectos que has visto hasta ahora en este libro han producido páginas web útiles y razonablemente atractivas. Sin embargo, es posible que hayas notado algo que es común a las páginas que has creado con la ayuda de ChatGPT: es cierto, simplemente están ahí. Es cierto que no hay nada de malo en una página que no hace mucho, si esa página ofrece información que es útil, informativa o divertida. Sin embargo, puede aumentar mucho el atractivo de una página si la página es interactiva de alguna manera. Y por "interactiva", me refiero a que los lectores pueden manipular la página para cambiar los datos que se muestran. Por ejemplo, en una página con muchos datos, puedes incluir controles que permitan a los usuarios mostrar solo un subconjunto de los datos o buscarlos.

En este capítulo, aprenderá primero cómo obtener datos en una página web sin tener que configurar un servidor web, una tarea tremendamente compleja que agradecerá poder omitir. En particular, este capítulo le muestra cómo tomar datos de un archivo de Excel y convertirlos a un formato que se pueda cargar en una página. Los datos de ejemplo son un conjunto de cursos universitarios y el objetivo es una página que permita a los visitantes buscar, ordenar y filtrar estos datos. Luego, pondrá todo esto en funcionamiento para crear un mensaje detallado para que ChatGPT genere el código para una página web de catálogo de cursos.

En este capítulo se ofrecen versiones comentadas del código HTML, CSS y JavaScript generados por ChatGPT para ayudarle a comprender cómo funciona el catálogo de cursos. También obtendrá algunos consejos útiles para personalizar el código.

## 13.1 Revisando el proyecto de este capítulo

Como mencioné en la introducción, el proyecto de este capítulo es un catálogo de cursos de una sola página para una universidad ficticia. La página final incluirá los siguientes componentes:

* Un elemento de header que incluye el logotipo y el título del sitio web.

* Un elemento main que comienza con los controles para filtrar, ordenar y buscar en el catálogo.

* Para cada curso, un elemento vertical, a veces llamado *tile-mosaico*, que muestra la imagen del curso, el título, la identificación, el instructor, el departamento, el semestre y la descripción.

* Un elemento de footer que incluye un aviso de derechos de autor

La figura 13.1 muestra un ejemplo de catálogo de cursos creado con el código proporcionado por ChatGPT. La página de ejemplo es una colección de tiles-mosaicos, cada uno de los cuales contiene la información de un curso universitario. Este tipo de diseño se puede utilizar para otros tipos de contenido, como un catálogo de productos, una lista de servicios disponibles, pedidos de clientes o prácticamente cualquier tipo de datos estructurados. El denominador común en todos estos proyectos es que los datos de la página web subyacente residen originalmente en un archivo de hoja de cálculo de Excel, por lo que necesita saber cómo obtener datos de Excel en un formato que el navegador web pueda comprender.

![image](https://github.com/user-attachments/assets/1a9604eb-3b47-4b55-bf87-5527a5e131cf)

**Figura 13.1 Un catálogo de cursos generado por ChatGPT**

## 13.2 Obtención de datos de Excel

Cuando se desea mostrar datos en una página web, uno de los problemas más comunes es que los datos estén en un formato que no es compatible con la web. Los datos pueden estar en una tabla de un documento de procesamiento de texto, una presentación, texto en un archivo de texto o notas dispersas en una aplicación para tomar notas. En este proyecto, supongo que los datos están en un archivo de Excel y la preparación de esos datos es el tema de la siguiente sección.

### 13.2.1 Cómo preparar los datos de Excel

Excel es una aplicación muy común para las necesidades de bases de datos livianas porque resulta familiar para la mayoría de las personas, la entrada de datos es relativamente sencilla y el formato de filas y columnas de una hoja de cálculo refleja el formato de filas y columnas que requieren la mayoría de los datos. Para utilizar datos de Excel en la Web, debe convertirlos a un formato adecuado. Pronto abordaré esa conversión, pero por ahora, debe asegurarse de que sus datos de Excel estén listos. Aquí, "listos" significa que los datos de Excel deben tener las siguientes características:

* Los datos son un rango o un rango que se ha convertido en una tabla.

* Si los datos son un rango (es decir, no una tabla), se debe cumplir una de las siguientes condiciones:

   * No hay otros datos en la hoja de trabajo.

   * Los datos residen en un rango con nombre.

* Cada columna de datos tiene un encabezado único.

La figura 13.2 muestra los datos de Excel que utilizaré como ejemplo para este proyecto. Los datos son una colección de cursos universitarios y almacenan lo siguiente para cada curso:

* El ID del curso

* El título del curso

* Una descripción del curso

* El nombre del instructor del curso

* El nombre del departamento que ofrece el curso.

* El semestre en el que se ofrece el curso.

Los datos residen en un rango regular de Excel; no hay otros datos en la hoja de cálculo y cada columna tiene un encabezado único.

Antes de aprender cómo convertir dichos datos de Excel a un formato utilizable, debe comprender ese formato, que es el tema de la siguiente sección.

![image](https://github.com/user-attachments/assets/9aa47bad-9f73-4ae7-912d-b29ce80c7b4d)

**Figura 13.2 Los datos de Excel que utilizaré en este proyecto**

### 13.2.2 Conozca el formato de datos JSON

Más adelante en este capítulo verás que el motor detrás de una página web basada en datos es JavaScript, que puede capturar el contenido de un archivo, procesar los datos que contiene el archivo, mostrar esos datos en la página web y permitirte configurar controles para realizar búsquedas, filtros y otras manipulaciones de datos. El punto de partida de todo esto es el archivo que lee JavaScript. JavaScript puede trabajar con múltiples tipos de archivos, pero el más fácil y conveniente para nuestros propósitos es el formato JSON (JavaScript Object Notation). JSON (se pronuncia como el nombre *Jason* ) es una de las formas más comunes en que se manejan los datos en las páginas web.

Una de las principales razones por las que JSON es tan popular es que los datos son texto sin formato, por lo que se pueden crear y editar con un editor de texto o código común y corriente. En las dos secciones siguientes, aprenderá a convencer a ChatGPT para que cree automáticamente datos JSON a partir de un archivo de Excel, de modo que no tenga que ensuciarse las manos con código JSON para este proyecto. Sin embargo, si desea saber cómo trabajar con datos JSON directamente, el resto de esta sección le brinda los detalles.

Como mencioné, los datos JSON son texto sin formato. Sin embargo, ese texto debe configurarse utilizando la sintaxis JSON correcta. A continuación, se muestra una descripción general de la sintaxis de los datos JSON:

```json
{
    "property1": value1,
    "property2": value2,
    ...
    "propertyX": valueX
}
```

Lo que tienes aquí es un conjunto de uno o más pares de propiedades y valores. Para este proyecto, los pares de propiedades y valores provienen de los datos originales de Excel, como se muestra a continuación:

* El nombre de cada propiedad proviene del encabezado de una columna en el rango de datos de Excel.

* Los valores asignados a las propiedades provienen de una sola fila en el rango de Excel.

* Cada nombre de propiedad está rodeado por comillas dobles (`"`).

* Cada valor suele ser una cadena rodeada de comillas dobles, pero también puede ser un número o cualquier otro tipo de datos de JavaScript.

* Los pares propiedad-valor están separados por comas.

* El bloque de pares propiedad-valor está rodeado por llaves ( `{` y `}` ).

A continuación se muestran algunos datos JSON de ejemplo, que corresponden a la primera fila de los datos de Excel mostrados anteriormente en la figura 13.2:

```json
{
    "Course ID": "AI101",
    "Title": "The Art of Chatting: Building Conversational AIs",
    "Description": "Dive into the quirky world of chatbots and virtual companions. Learn how to design AIs that can outwit humans in a battle of banter, negotiate pizza toppings, and philosophically ponder the existence of the internet.",
    "Instructor": "Prof. Kaitlyn Wong",
    "Department": "Artificial Intelligence",
    "Semester": 1
}
```

Esta es solo una fila del rango original de Excel. Para los rangos que tienen varias filas, ChatGPT generará un array de objetos JSON: una coma separa cada objeto JSON y todo el conjunto de datos está rodeado por corchetes ( `[` y `]` ). A continuación, se muestra un ejemplo parcial:

```json
[
    {
        "Course ID": "AI101",
        "Title": "The Art of Chatting: Building Conversational AIs",
        "Description": "Dive into the quirky world of chatbots and virtual companions. Learn how to design AIs that can outwit humans in a battle of banter, negotiate pizza toppings, and philosophically ponder the existence of the internet.",
        "Instructor": "Prof. Kaitlyn Wong",
        "Department": "Artificial Intelligence",
        "Semester": 1
    },
    {
        "Course ID": "AI102",
        "Title": "Robot Overlords 101: An Introduction to AI Ethics",
        "Description": "Explore the moral dilemmas of our future robot overlords. From deciding who gets the last piece of cake to governing a small island, this course tackles the hard ethical questions.",
        "Instructor": "Prof. Thiago Silva",
        "Department": "Artificial Intelligence",
        "Semester": 2
    },
    {
        "Course ID": "AI103",
        "Title": "Dreaming in Code: AI for Creative Minds",
        "Description": "Unleash the power of AI to create art, music, and literature. Learn how algorithms can be inspired by dreams and how to interpret the surreal artworks produced by silicon brains.",
        "Instructor": "Prof. Anika Singh",
        "Department": "Artificial Intelligence",
        "Semester": 3
    },
...
    {
        "Course ID": "AI402",
        "Title": "Ghost in the Machine: AI and Paranormal Research",
        "Description": "Investigate the uncanny valley with AI. Learn how artificial intelligence is used to explore paranormal activities, communicate with spirits, and debunk or prove age-old myths.",
        "Instructor": "Prof. Sven Eriksson",
        "Department": "Artificial Intelligence",
        "Semester": 1
    }
]
```

ChatGPT necesita algunos datos para trabajar, por supuesto, por lo que cargar los datos de Excel es el tema de la siguiente sección.

### 13.2.3 Subir su archivo Excel a ChatGPT

El primer paso para convertir sus datos de Excel al formato JSON es cargar el archivo de hoja de cálculo de Excel en ChatGPT.

**NOTA**: mientras escribo esto, la capacidad de cargar archivos solo está disponible para los suscriptores de ChatGPT Plus.

Estos son los pasos a seguir:

   1. Inicie sesión en su cuenta ChatGPT Plus.

   2. Inicie una nueva sesión de chat de ChatGPT 4.

   3. En el lado izquierdo del cuadro de texto del mensaje, haga clic en el ícono Adjuntar archivos (el clip; consulte la figura 13.3) para mostrar el cuadro de diálogo Abrir - Open dialog.

![image](https://github.com/user-attachments/assets/2fd33fdb-006b-48d7-a26d-0e8565d32a78)

**Figura 13.3 Haga clic en Adjuntar archivos (el clip) para cargar su archivo de Excel.**

   4. Busque y seleccione el archivo de Excel que contiene los datos que desea convertir.

   5. Haga clic en Abrir. ChatGPT cargará el archivo y aparecerá un ícono del archivo en el chat, como se muestra en la figura 13.4.

![image](https://github.com/user-attachments/assets/11f5201b-5a8d-4c05-ab24-a98cd7d81e06)

**Figura 13.4 El archivo Excel cargado aparece como un ícono en la transcripción del chat.**

Con el archivo Excel adjunto al chat, está listo para solicitarle a ChatGPT que convierta sus datos al formato JSON.

### 13.2.4 Cómo solicitarle a ChatGPT que convierta sus datos de Excel a JSON

ChatGPT (o al menos, la versión del chatbot que obtienes con una suscripción a ChatGPT Plus) tiene capacidades de procesamiento de datos excelentes y sólidas. Estas incluyen:

* Extraer datos de un archivo de hoja de cálculo de Excel

* Convirtiendo esos datos al formato JSON

* Escribir los datos convertidos en un archivo JSON (que utiliza la extensión de archivo `.json`)

Al igual que con todo lo relacionado con ChatGPT, estas funciones se habilitan mediante un prompt. Cuando esté listo para escribir el prompt, tenga en cuenta que existen varios escenarios comunes que se deben tener en cuenta:

* *The Excel data you want to convert to JSON resides either in a named range or in a named table - Los datos de Excel que desea convertir a JSON se encuentran en un rango o una tabla con nombre*. En este caso, puede utilizar el nombre del rango o de la tabla en tu prompt:

```text
In the uploaded Excel file, please convert the range named "Crypto" to JSON format and output the result as a JSON file.
```

```text
En el archivo Excel cargado, convierta el rango llamado "Crypto" al formato JSON y genere el resultado como un archivo JSON.
```

* *The Excel file contains a single worksheet, and that worksheet contains nothing but the range of data you want to convert to JSON - El archivo de Excel contiene una sola hoja de cálculo, y esa hoja de cálculo no contiene nada más que el rango de datos que desea convertir a JSON*. En este caso, un mensaje como el siguiente debería ser suficiente:

```text
In the uploaded Excel file, please convert the range to JSON format and output the result as a JSON file.
```

```text
En el archivo Excel cargado, convierta el rango al formato JSON y genere el resultado como un archivo JSON.
```

Este es el mensaje que puede utilizar para el archivo Excel de ejemplo incluido con los archivos de muestra de este capítulo.

* *The Excel file contains multiple worksheets, but the range you want to convert is in the first worksheet.  - El archivo de Excel contiene varias hojas de cálculo, pero el rango que desea convertir se encuentra en la primera*. Si no especifica una hoja de cálculo, ChatGPT convierte automáticamente un rango en la primera, por lo que puede usar un mensaje como el siguiente:

```text
In the uploaded Excel file, please convert the range to JSON format and output the result as a JSON file.
```

```text
En el archivo Excel cargado, convierta el rango al formato JSON y genere el resultado como un archivo JSON.
```


* *The Excel file contains multiple worksheets, and your range is not in the first worksheet - El archivo de Excel contiene varias hojas de cálculo y el rango no se encuentra en la primera*. En este caso, la solicitud debe especificar el nombre de la hoja de cálculo que contiene los datos:

```text
In the uploaded Excel file, please convert the range in the worksheet named "My Data" to JSON format and output the result as a JSON file.
```

```text
En el archivo Excel cargado, convierta el rango en la hoja de trabajo denominada "Mis datos" al formato JSON y genere el resultado como un archivo JSON.
```

Cuando envías tu prompt, ChatGPT comienza a analizar el archivo de Excel, extraer los datos y convertirlos al formato JSON. Cuando este trabajo está completo, ChatGPT te informa y te ofrece un enlace de descarga para el archivo JSON resultante, como se muestra en la figura 13.5. Haz clic en el enlace para descargar el archivo JSON a tu computadora.

![image](https://github.com/user-attachments/assets/c8766fe1-2a4a-4acf-b0fd-d6fb43316bb6)

**Figura 13.5 Cuando ChatGPT haya convertido sus datos de Excel a JSON, ofrecerá un enlace para descargar el archivo JSON.**

En este punto, es una buena idea echar un vistazo rápido al archivo JSON descargado para asegurarse de que ChatGPT haya hecho todo correctamente. Haga doble clic en el archivo para cargarlo en la aplicación predeterminada de su computadora para este tipo de archivo. Debería ver sus datos en formato JSON; la figura 13.6 muestra un ejemplo.

![image](https://github.com/user-attachments/assets/19a97466-53a8-4773-b5f9-99fba32a7fbf)

**Figura 13.6 Es una buena idea ver los datos JSON para asegurarse de que ChatGPT lo hizo correctamente.**

Si el archivo JSON contiene datos incorrectos, lo más probable es que el problema sea que ChatGPT haya procesado el rango incorrecto en su archivo de Excel. Cree un nuevo mensaje que utilice información de identificación más específica para los datos, como el nombre de la hoja de cálculo o el nombre del rango o la tabla. Si eso no funciona, abra el archivo de la hoja de cálculo en Excel, defina un nombre para el rango, cargue el archivo de Excel revisado en el chat de ChatGPT y luego cree un mensaje que haga referencia al nombre del rango que definió. Una vez que tenga su archivo de datos JSON, es hora de aprender a extraer esos datos y mostrarlos en la página web que va a crear.

## 13.3 Obtención y visualización de datos JSON

En este momento tienes un archivo JSON y más adelante tendrás una página web creada por ChatGPT. ¿Cómo se obtienen esos datos JSON en esa página web? Esa es una tarea de JavaScript, por lo que cuando llega el momento de solicitarle a ChatGPT el código JavaScript de tu página, comienzas con la siguiente solicitud:

```text
Fetch the contents of the file filename.
```

```text
Obtener el contenido del archivo nombre_archivo.
```

Esto le indica a ChatGPT que genere código que extraiga el contenido de lo que esté en el archivo llamado `filename`. Por ejemplo, para el archivo `college_courses.json` de este proyecto, el mensaje se vería así:

```text
Fetch the contents of the file college_courses.json.
```

```text
Obtenga el contenido del archivo college_courses.json.
```

**NOTA**: El método JavaScript que extrae el contenido de un archivo se llama `fetch`, por lo que el uso del verbo ***fetch*** en la solicitud es deliberado.

El código JavaScript resultante carga todos los datos JSON en la memoria, por lo que el siguiente paso es pedirle a ChatGPT que genere código JavaScript para escribir esos datos en la página web. Por ejemplo, supongamos que el código de su página web incluye un elemento `article` vacío y desea que todos los datos aparezcan en ese elemento. Un escenario común es mostrar cada registro de los datos separados como un elemento `section`. Por lo tanto, su prompt comenzaría así:

```text
For each record fetched from the JSON file, add a section element to the article element and populate the section element with the following:
```

```text
Para cada registro obtenido del archivo JSON, agregue un elemento de sección al elemento de artículo y complete el elemento de sección con lo siguiente:
```

A continuación, deberá especificar los elementos que desea utilizar para mostrar los datos. Por ejemplo, puede utilizar un encabezado de tercer nivel para el título de un registro, si lo tuviera. De manera similar, puede utilizar un elemento de párrafo si el registro tuviera un elemento de texto largo.

Aquí está el mensaje para el proyecto de este capítulo:

```text
For each record fetched from the JSON file, add a section 
element to the article element and populate the section 
element with the following three elements:
 * A third-level heading that includes the record's "Title" text.
 * A div element with the text "Course ID: ", the record's "Course ID" value, a line break, the text "Instructor: ", the record's "Instructor" value, a line break, the text "Department: ", the record's "Department" value, a line break, the text "Semester: ", the record's "Semester" value, and a line break.
 * A paragraph element that includes the record's "Description" value.
```

```text
Para cada registro obtenido del archivo JSON, agregue una sección
elemento al elemento del artículo y rellenar la sección
elemento con los tres elementos siguientes:
 * Un encabezado de tercer nivel que incluye el texto "Título" del registro.
 * Un elemento div con el texto "ID del curso: ", el valor "ID del curso" del registro, un salto de línea, el texto "Instructor: ", el valor "Instructor" del registro, un salto de línea, el texto "Departamento: ", el valor "Departamento" del registro, un salto de línea, el texto "Semestre: ", el valor "Semestre" del registro y un salto de línea.
 * Un elemento de párrafo que incluye el valor "Descripción" del registro.
```

El código JavaScript resultante recorrerá todos los registros JSON recuperados y escribirá cada uno de ellos en la página.

Una vez que haya obtenido y mostrado sus datos JSON, es momento de aprender a manipular todos esos datos en la página web que va a crear.

## 13.4 Búsqueda, ordenación y filtrado del catálogo de cursos

Es muy posible que desees mostrar tus datos JSON en la página web y dejarlo así. Probablemente sea así si tu base de datos es relativamente pequeña, digamos un par de docenas de elementos o menos. Pero si tus datos constan de docenas, cientos o incluso miles de registros, simplemente arrojar toda esa información en una página web no será suficiente. ¿Por qué? Porque es muy poco probable que sea útil (y muy probable que sea frustrante) para cualquiera que intente verla.

Si tiene una gran cantidad de datos, debe tener compasión de sus visitantes y ofrecerles una o más de las siguientes formas de manipularlos: búsqueda, clasificación y filtrado. Las siguientes tres secciones le explicarán los detalles.

### 13.4.1 Búsqueda de datos

Al realizar una búsqueda, el usuario escribe una palabra o frase que representa los datos que desea ver. Al enviar el texto de búsqueda, se reemplaza la base de datos completa únicamente con aquellos registros que contienen texto que coincide con la palabra o frase de búsqueda.

Un componente de búsqueda de una página web es casi siempre un cuadro de texto. Por lo tanto, en el mensaje de ChatGPT para el código HTML, debe incluir dicho cuadro de texto. A continuación, se muestra un ejemplo:


```text
A text box with the ID "Search" and the placeholder "Search".
```

```text
Un cuadro de texto con el ID "Buscar" y el marcador de posición "Buscar".
```

Aquí, un *placeholder* es una palabra o frase que aparece en el text box - cuadro de texto para que el usuario sepa lo que debe ingresar. Tan pronto como el usuario comienza a escribir texto en el cuadro, el placeholder desaparece. Tenga en cuenta también que incluir un valor de ID para el componente hace que el código JavaScript sea más fácil de leer.

Cuando le pides a ChatGPT el código JavaScript, debes incluir cómo quieres que el código maneje el texto de búsqueda. Generalmente, le pides a JavaScript que monitoree el campo de búsqueda y, cuando el usuario comienza a escribir, reemplace los registros JSON que se muestran solo con aquellos que coinciden con el texto escrito. Aquí hay un ejemplo de solicitud:

```text
When the user types text in the "Search" text box, 
repopulate the article element with just the records 
that include the search text in any field.
```

```text
Cuando el usuario escribe texto en el cuadro de texto "Buscar",
Vuelva a llenar el elemento del artículo solo con los registros
que incluyan el texto de búsqueda en cualquier campo.
```

En este ejemplo se supone que desea aplicar el texto de búsqueda a todos los campos de sus datos JSON. Es posible que desee considerar un par de excepciones:

* Si hay uno o más campos que no desea incluir en la búsqueda (como un campo que contiene datos numéricos), agrégue `except the X` y `Y fields` al final del prompt (donde `X` y `Y` son los nombres de los campos que desea excluir).

* Si solo desea aplicar la búsqueda a uno o más campos, reemplace `any field` en el prompt `the` `A` `and` `B` `fields`, donde `A` y `B` son los nombres de los campos que desea buscar.

La búsqueda es probablemente la función de manipulación de datos más común (y posiblemente la más útil), pero es necesario conocer otras dos, la primera de las cuales es el filtrado.

### 13.4.2 Filtrado de datos

Con el filtrado, el usuario muestra un subconjunto de los datos JSON, generalmente eligiendo uno de los valores únicos que aparecen en un campo en particular. Por ejemplo, en el proyecto de este capítulo, los usuarios pueden filtrar los datos del curso en función de los valores únicos en los campos `Department` y `Instructor`.

Un componente de filtro de página web suele ser una *drop-down list - lista desplegable* que contiene los elementos únicos de un campo en particular, por lo que en la solicitud del código HTML debe solicitar dicho componente. A continuación, se muestran los dos prompts utilizadas en el proyecto de este capítulo:

```text
A drop-down list with the ID "Department" and the initial value "Department (All)".
A drop-down list with the ID "Instructor" and the initial value "Instructor (All)".
```

```text
Una lista desplegable con el ID "Departamento" y el valor inicial "Departamento (Todos)".
Una lista desplegable con el ID "Instructor" y el valor inicial "Instructor (Todos)".
```

Tenga en cuenta que el mensaje aplica valores de identificación a cada lista y también rellena cada lista con un valor inicial. En ambos casos, al seleccionar este valor inicial de la lista, se vuelve a rellenar la página web con la base de datos completa.

Cuando le pides a ChatGPT que genere tu código JavaScript, primero debes incluir que quieres que tus listas desplegables se completen con los valores únicos en los campos de datos correspondientes. Por ejemplo, aquí hay un mensaje que completa la lista desplegable Departamento con los valores únicos del campo `Department`:

```text
Extract all the unique "Department" values and use them to populate the "Department" drop-down list.
```

```text
Extraiga todos los valores únicos de "Departamento" y utilícelos para completar la lista desplegable "Departamento".
```

A continuación, especifica cómo quieres que el código gestione la selección de un elemento de una lista por parte del usuario. La idea general es que JavaScript monitoree la lista y, cuando el usuario seleccione un elemento, el código reemplace los registros JSON mostrados únicamente por aquellos que coincidan con el elemento de la lista seleccionado. A continuación, se muestra un ejemplo de solicitud para el Departmentcampo:

Cuando el usuario selecciona un elemento de la lista "Departamento", vuelva a llenar el elemento del artículo solo con los registros que coincidan con el departamento seleccionado. Si el usuario selecciona el primer elemento de la lista, vuelva a llenar el elemento del artículo con todos los registros importados desde el archivo JSON.
La última técnica de manipulación de datos es la clasificación, que se trata en la siguiente sección.

### 13.4.3 Ordenar los datos

Con la ordenación, el usuario controla el orden de los registros que se muestran, generalmente especificando un campo de alguna manera. Luego, la página reordena los registros alfabéticamente (si el campo contiene texto) o numéricamente (si el campo contiene números). En este proyecto, los usuarios pueden ordenar el catálogo de cursos en los campos Departmenty Title.

Un componente de ordenación de páginas web suele ser una lista desplegable que contiene los nombres de los campos ordenables. Cuando le pides a ChatGPT que genere el código HTML de tu página, debes solicitar dicho componente. A continuación, se incluye un ejemplo del proyecto de este capítulo:

Una lista desplegable con el ID "Ordenar" y los valores: "Ordenar por departamento" y "Ordenar por título".
Cuando le solicitas a ChatGPT el código JavaScript, debes incluir cómo quieres que el código gestione la selección de un elemento de esta lista por parte del usuario. La idea general es que JavaScript determine qué elemento se seleccionó, ordene los registros en función de ese campo y luego vuelva a mostrar los registros ordenados en la página. A continuación, se muestra un ejemplo de solicitud de nuestro proyecto:

Cuando el usuario selecciona "Ordenar por título" en la lista "Ordenar", ordena los registros mostrados en el campo "Título" y luego vuelve a llenar el elemento del artículo con los registros ordenados. Cuando el usuario selecciona "Ordenar por departamento" en la lista "Ordenar", ordena los registros mostrados en el campo "Departamento" y luego vuelve a llenar el elemento del artículo con los registros ordenados.
En este punto, ya sabes todo lo que se necesita para que ChatGPT cree un catálogo de cursos. La siguiente sección te guiará a través del proceso.

## 13.5 Elaboración del mensaje para el catálogo de cursos

El proyecto de este capítulo es una página de catálogo de cursos que obtiene y luego muestra todos los datos en un archivo JSON independiente. La página incluye controles para filtrar, ordenar y buscar los datos. Este proyecto supone que ya tienes un título, un subtítulo y un logotipo; sabes qué fuentes quieres usar para los encabezados y el texto de la página; y tienes un esquema de colores listo para aplicar. Vuelve al capítulo 3 para aprender a solicitarle a ChatGPT sugerencias de título, tipografía y color.

Para iniciar su solicitud, dígale a ChatGPT que desea construir una página web y que desea que genere el código por usted:

Quiero crear una página web para un catálogo de cursos. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
Ahora describa el contenido de la página, elemento por elemento, incluyendo lo siguiente (consulte la figura 13.7):

Un encabezado que incluye una imagen a la izquierda, un logotipo a la derecha y un título y subtítulo en el medio.

Un elemento de navegación que contiene dos listas desplegables para filtrar, otra lista desplegable para ordenar y un cuadro de texto para buscar.

Un elemento principal que contiene un elemento de artículo vacío

Un pie de página que incluye un aviso de derechos de autor



**Figura 13.7 Los elementos de la página del catálogo de cursos antes de que se representen los datos**

La Figura 13.7 no muestra datos porque, como explicaré brevemente, el articleelemento vacío solo se completa a través del código JavaScript que le pide a ChatGPT que genere.

A continuación, solicite a ChatGPT que genere el CSS:

En segundo lugar, en un archivo separado, escriba el código CSS para lo siguiente:
A continuación, especifique el formato de la página, incluido lo siguiente:

El color de fondo de la página y el color del texto.

Los tamaños de fuente que desea utilizar para los encabezados y el texto de la página.

Las fuentes a utilizar para los encabezados y el texto de la página normal.

¿Qué elementos deben ser contenedores de Flexbox? En este proyecto, estos serán el encabezado, el elemento de navegación, el elemento de artículo y cada elemento de sección.

Finalmente, le indica a ChatGPT que proporcione el código JavaScript:

En tercer lugar, en un archivo separado, escriba el código JavaScript para lo siguiente:
A continuación, explica lo que quieres que haga JavaScript, incluido lo siguiente:

Obtener el contenido del archivo JSON.

Complete las listas desplegables que requieren valores únicos de un campo en particular.

Escriba todos los datos JSON en la página web utilizando los componentes de texto y HTML que especifique.

Manejar una selección de una lista desplegable de filtrado.

Manejar una selección de la lista desplegable de clasificación.

Manejar cuándo se escribe texto en el cuadro de búsqueda.

Utilicé la aplicación ChatGPT de OpenAI para enviar mi mensaje a GPT-4. El código generado generó la página que se muestra en la figura 13.8.



**Figura 13.8 Mi catálogo de cursos**

Si le gusta el aspecto de su página, puede omitir el resto de este capítulo e implementar el código en la web (consulte el apéndice B para obtener instrucciones de implementación). Sin embargo, si desea comprender el código de la página web generada, siga leyendo para obtener más información.

## 13.6 Examinar el código del catálogo de cursos

Si desea tener al menos alguna idea de lo que ChatGPT generó en su nombre, las siguientes tres secciones le brindan una breve mirada al código HTML y CSS que sustenta la página del catálogo de cursos que se muestra en la figura 13.8, así como el código JavaScript que llena los datos de la página y maneja los diversos controles de manipulación de datos.

**NOTA**: El código HTML y CSS generado para mi catálogo de cursos está disponible en el sitio web de este libro ( www.manning.com/books/build-a-website-with-chatgpt ) y en el repositorio de GitHub del libro: https://github.com/paulmcfe/websites-with-chatgpt .

Las anotaciones de código que siguen deberían ayudarle a comprender cómo funciona el catálogo de cursos y pueden facilitar la modificación o personalización de su propio código.

### 13.6.1 Examinar el HTML

Aquí hay una versión anotada del código HTML que ChatGPT produjo para mi catálogo de cursos:

```html
```

① Ayuda a que la página se muestre correctamente en dispositivos móviles

② Carga la fuente Roboto desde Google Fonts

③ Le dice al navegador web dónde encontrar el código CSS

④ Encabezado de página

⑤ Imagen del encabezado del sitio

⑥ Título del sitio

⑦ Título de la página

⑧ Logotipo del sitio

⑨ Elemento de navegación

⑩ Lista desplegable de filtros de departamento

⑪ Lista desplegable del filtro del instructor

⑫ Ordenar lista desplegable

⑬ Cuadro de texto de búsqueda

⑭ Elemento de artículo vacío

⑮ Pie de página

⑯ Le dice al navegador web dónde encontrar el código JavaScript

Tenga en cuenta que el código HTML incluye la siguiente línea:

```html
```

Esta etiqueta le dice al navegador web dónde encontrar el código CSS, que describo en la siguiente sección.

### 13.6.2 Examinar el CSS

Aquí hay una versión anotada del código CSS que ChatGPT produjo para mi catálogo de cursos:

```css
```
                                      ⑪
① Diseña el color de fondo de la página, el margen y el tamaño, color y fuente del texto.

② Aplica estilo al encabezado como un contenedor Flexbox

③ La imagen del encabezado izquierdo ocupa toda la altura del encabezado.

④ Establece la altura máxima de la imagen del encabezado derecho

⑤ Diseña el tamaño de fuente, el estilo y la alineación del título de la página.

⑥ Diseña el tamaño de fuente, el estilo y la alineación de los subtítulos de la página.

⑦ Aplica estilo al elemento de navegación como un contenedor Flexbox

⑧ Aplica estilo al elemento del artículo como un contenedor Flexbox

⑨ Aplica estilo a los elementos de la sección como contenedores Flexbox

⑩ Establece el tamaño de fuente de los títulos de los cursos

⑪ Da estilo al pie de página

En la lista de códigos HTML de antes en este capítulo, observe la siguiente línea cerca de la parte inferior:

```html
```

Esta etiqueta le dice al navegador web dónde encontrar el código JavaScript, que anoto en la siguiente sección.

### 13.6.3 Examinando el JavaScript

Si tienes cuidado, está bien hacer pequeños ajustes al código HTML y CSS. Sin embargo, te recomiendo encarecidamente que no modifiques el código JavaScript de ChatGPT. El código es complejo y una edición imprudente podría hacer que el catálogo de cursos quede inutilizable.

Sin embargo, si conoces un poco de JavaScript, quizás te interese saber cómo ChatGPT codificó la obtención, visualización y manipulación de los datos JSON. Aquí tienes una versión anotada del código JavaScript que ChatGPT generó para mi catálogo de cursos:

```js
```
                                                                                       ⑮
① Ejecuta el código de función que sigue una vez que se ha cargado la página

② Obtiene los datos del archivo JSON

③ Ejecuta la función que llena las listas desplegables

④ Ejecuta la función que rellena el artículo.

⑤ Escucha los cambios en el menú desplegable del Departamento.

⑥ Escucha los cambios en el menú desplegable del Instructor.

⑦ Escucha los cambios en el menú desplegable Ordenar

⑧ Escucha la entrada de texto en el cuadro de texto de búsqueda

⑨ Ejecuta el código de función que sigue una vez que se ha cargado la página

⑩ Rellena los menús desplegables de Departamento e Instructor con los valores únicos de esos campos

⑪ Rellena el elemento de artículo con datos del curso.

⑫ Filtra los datos cuando el usuario selecciona un elemento en la lista de Departamento o Instructor

⑬ Filtra los datos cuando el usuario selecciona un elemento en la lista de Departamento o Instructor

⑭ Ordena los datos cuando el usuario selecciona un elemento en la lista de ordenamiento

⑮ Busca los datos cuando el usuario escribe algo en el cuadro de texto Buscar

Si lo desea, puede utilizar las anotaciones HTML y CSS de las dos secciones anteriores para ayudar a personalizar el código de su página web, como describo en la siguiente sección.

## 13.7 Personalización del catálogo de cursos

Usando las anotaciones de la sección anterior como guía, aquí te mostraré algunas personalizaciones de código relativamente simples que puedes hacer abriendo los archivos HTML y CSS en tu editor de texto. Sin embargo, si tu página no se parece en nada a lo que quieres, es mejor que reescribas tu mensaje y lo envíes a ChatGPT en una nueva sesión.

El código HTML de este proyecto es mínimo porque la mayor parte de la página se genera mediante JavaScript. Por eso, tengo un par de sugerencias:

Siéntete libre de agregar más campos de ordenación agregando nuevos elementos a la lista desplegable Ordenar. Solo recuerda solicitarle a ChatGPT que genere el código JavaScript para manejar la ordenación en los nuevos campos.

En la sección de pie de página del código HTML, puedes agregar enlaces a tus cuentas de redes sociales, como describo en el capítulo 4.

A continuación se muestran algunas ideas de personalización para el código CSS:

Para utilizar otro color de fondo de página, especifique una palabra clave de color diferente para la propiedad bodydel elemento background-color.

Para utilizar otro color de fondo para el encabezado y el pie de página, especifique una nueva palabra clave de color para la propiedad de los elementos headery .footerbackground-color

Para utilizar un color diferente para el texto de la página, especifique una palabra clave de color diferente para la propiedad bodydel elemento color.

Para cualquier valor de tamaño de fuente, puede cambiar el número para aumentar o disminuir el tamaño de la fuente. Solo asegúrese de dejar la pxunidad en su lugar.

Para cualquier valor de margen o relleno, puede cambiar el número para aumentar o disminuir el relleno o los márgenes. En cada caso, asegúrese de dejar la pxunidad en su lugar.

Para que el código de tu página sea más accesible, considera convertir todas las medidas en px a medidas en rem. 1 rem equivale de manera predeterminada a 16 px, por lo que 20 px son 1,25 rem, 24 px son 1,5 rem, 32 px son 2 rem, 48 px son 3 rem, y así sucesivamente. La unidad rem es más accesible porque mide los tamaños de fuente en relación con el tamaño de fuente predeterminado que el usuario del navegador ha definido en la configuración de su navegador.

## 13.8 ¿A dónde ir desde aquí?

Mi objetivo en este libro ha sido mostrarte que, aunque parezca mágico que ChatGPT pueda generar código sofisticado para páginas web a pedido, el verdadero secreto es convertir la visión de tu página web en un mensaje específico y detallado que le diga a ChatGPT exactamente lo que quieres. Has visto muchos ejemplos de mensajes de este tipo en este libro y, a lo largo del camino, has aprendido todo lo que necesitas saber sobre la construcción y el diseño de páginas web. Esa es una gran noticia porque significa que ahora tienes el conocimiento y la experiencia para crear casi cualquier cosa que quieras en la web. Cuando estés listo para crear algo audaz y hermoso, ChatGPT estará allí para que conviertas ese sueño en realidad. Todo está a solo un mensaje de distancia.

## Resumen

* Para convertir datos de Excel a JSON, asegúrese de que los datos residan en un rango o tabla y que cada columna tenga un encabezado único.

* JSON es un conjunto de uno o más pares de propiedades y valores separados por comas y rodeados por llaves ( {y }), donde los nombres de las propiedades están entre comillas dobles. Los valores de texto también están entre comillas dobles.

* Si tiene una cuenta ChatGPT Plus, puede cargar su archivo Excel en un chat y luego solicitarle a ChatGPT que convierta sus datos a JSON y genere el resultado como un archivo que puede descargar.

* Le pide a ChatGPT que genere el código de su página web con un elemento vacío (como un articleelemento); luego usa JavaScript para completarlo con los datos JSON.

* Las técnicas de manipulación de datos más comunes en las páginas web son la búsqueda, el filtrado y la clasificación. Puedes solicitarle a ChatGPT que genere el código JavaScript para implementar cada técnica.

* Para obtener los mejores resultados, el mensaje de su página debe ser lo más específico posible, incluidos colores, tamaños de fuente y niveles de encabezado.

* Guarde el HTML generado en el archivo index.html, el CSS generado en el nombre de archivo sugerido por ChatGPT en el código HTML, generalmente styles.css, y el código JavaScript generado en el nombre de archivo sugerido por ChatGPT en el código HTML, generalmente script.js.
