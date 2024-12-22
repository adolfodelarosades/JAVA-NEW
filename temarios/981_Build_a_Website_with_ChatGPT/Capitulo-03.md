# 3 Cómo trabajar con fonts, colors y headings

Este capítulo cubre

* Comprender el papel de los fonts en el diseño de páginas web
* Creando un esquema de color para tu página
* Cómo hacer que una página sea más fácil de leer con encabezados(headings)
* Prompting ChatGPT para crear una personal home page
* Examinando y personalizando el código ChatGPT

En el capítulo 2, te llevé a través del proceso de creación de una página web funcional desde cero usando un prompt de ChatGPT relativamente simple. La página resultante funcionó bien, pero no tenía mucho que ver. Esa página simple estaba bien porque quería mantener las cosas simples, pero si vas a crear algún tipo de presencia en la web, definitivamente querrás que la página resultante se vea bien.

En este capítulo, darás el primer paso en esa dirección examinando varias opciones de formato de página que pueden ser de gran ayuda para hacer que cualquier página web sea más atractiva y más legible. Estas opciones incluyen typefaces, type sizes, colors y headings (tipos de letra, tamaños de letra, colores y encabezados). Aquí, aprenderás por qué son importantes y cómo puedes hacer que ChatGPT te ayude a tomar estas decisiones de diseño para tu página. Toda esta información se incluye en un prompt detallado que le pasarás a ChatGPT para que produzca el código de página web para una personal home page que te brinde una porción de la web que puedas llamar tuya. Si tienes curiosidad, este capítulo también explica el código generado por ChatGPT y te muestra algunas formas de personalizar el código sin tener que volver a solicitarle un prompt a ChatGPT.

## 3.1 Echando un vistazo al proyecto de este capítulo

El proyecto con el que le pedirás ayuda a ChatGPT en este capítulo es una personal home page simple que consta de algunos o todos los siguientes componentes:

* Un title - título (que podría ser simplemente tu nombre)
* Un subtitle - subtítulo (un eslogan que resume la página (o a usted) para los lectores)
* Una breve biography - biografía
* Una breve description - descripción de lo que haces para ganarte la vida.
* Una lista de tus hobbies - pasatiempos e iinterests - ntereses.
* Una lista de tus libros, películas, programas de televisión, bandas favoritas, etc.

La figura 3.1 muestra un ejemplo del tipo de página que creará con la ayuda de ChatGPT.

<img width="621" alt="image" src="https://github.com/user-attachments/assets/2111243f-06a9-4263-9179-ecedfba508e3">

**Figura 3.1 Una página de inicio personal generada por ChatGPT**

Por supuesto, es tu página, así que siéntete libre de agregar cualquier otra cosa que quieras que el mundo sepa sobre ti. También puedes modificar ligeramente esta página para convertirla en un currículum vitae en línea.

Antes de pasar a los detalles de cómo solicitar a ChatGPT que genere el código para tu personal home page, puedes usar el modelo para generar algunas sugerencias de diseño, incluido el título y el subtítulo del sitio, las fuentes y la combinación de colores. Usarás estas sugerencias más adelante cuando crees tu prompt.

## 3.2 Creación de la personal home page

Para ayudarte a usar ChatGPT para crear tu personal home page, las siguientes secciones te guiarán por cada componente de la página, desde el título hasta el tipo de letra y los colores. En cada caso, te daré algunos antecedentes, te mostraré el código HTML o CSS relevante, si lo hay, y luego te mostraré cómo pedirle a ChatGPT que genere lo que necesitas.

### 3.2.1 Obtener sugerencias de title - títulos y subtitle - subtítulos del sitio

El título más obvio para tu personal home page es tu nombre. Si eso no te parece lo suficientemente creativo, utiliza ChatGPT para sugerir no solo un título para el sitio, sino también un subtítulo o eslogan que aparezca debajo del título.

Una forma útil de pedirle a ChatGPT que escriba un título y un subtítulo es combinar lo que haces para ganarte la vida con uno o más pasatiempos o intereses y ver qué puede ofrecer ChatGPT. Aquí tienes una propuesta genérica que puedes usar:

<img width="914" alt="image" src="https://github.com/user-attachments/assets/6a62b590-2ffe-4c57-89d5-e07993292f1e">


```text
You are a wordsmith that can generate catchy and creative titles and taglines for personal home pages. You use the information provided by the user to come up with suggestions that reflect their skills and interests.
 
I am X and my favorite hobby is Y.
 
First, think of some words or phrases that relate to X and Y.
 
Second, try to combine or play with these words or phrases to create catchy or witty titles.
 
Third, add a tagline that explains or expands on the title.
```

```text
Eres un creador de palabras capaz de generar títulos y eslóganes atractivos y creativos para páginas de inicio personales. Utilizas la información proporcionada por el usuario para elaborar sugerencias que reflejen sus habilidades e intereses.

Soy X y mi pasatiempo favorito es Y.

Primero, piense en algunas palabras o frases que se relacionen con X e Y.
 
En segundo lugar, intente combinar o jugar con estas palabras o frases para crear títulos pegadizos o ingeniosos.
 
En tercer lugar, agregue un eslogan que explique o amplíe el título.
```
 
En este prompt, reemplácela `X` con su título o descripción laboral y reemplácela `Y` con uno o más intereses o pasatiempos. La Figura 3.2 muestra mis resultados (generados con Bing Copilot en modo Creativo). Si encuentra un título y un subtítulo que le gusten (no es necesario que provengan de la misma sugerencia), cópielos en algún lugar para poder usarlos más adelante cuando le solicite a ChatGPT que cree el código para su página de inicio.

<img width="912" alt="image" src="https://github.com/user-attachments/assets/03588327-327f-41d5-b054-4890926593d8">

**Figura 3.2 Solicitud de ChatGPT para un título de página y un eslogan**

La fuente de una página web es el estilo del texto de la página. Se trata de un tema muy amplio, pero para nuestros propósitos, podemos considerar solo tres componentes: el typeface, el type size y el type style (tipo de letra, el tamaño de la letra y el estilo de la letra).

## 💻 Mis pruebas.

### Usando ChatGPT

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/a3a5d4c3-ddab-4dfa-ba38-0007f1ee359c" />

```text
You are a wordsmith that can generate catchy and creative titles and taglines for personal home pages. You use the information provided by the user to come up with suggestions that reflect their skills and interests.
 
I am Adolfo and my favorite hobby is skate.
 
First, think of some words or phrases that relate to Adolfo and skate.
 
Second, try to combine or play with these words or phrases to create catchy or witty titles.
 
Third, add a tagline that explains or expands on the title.
```

### Words and Phrases Related to Adolfo and Skate:  
- Kickflip  
- Grind  
- Ollie  
- Shred  
- Adrenaline  
- Board  
- Wheels  
- Street vibes  
- Freedom  
- Flow  
- Deck  
- Thrill  

---

### Title and Tagline Ideas:  

1. **"Adolfo on Deck"**  
   *Tagline:* Shredding the streets, one kickflip at a time.  

2. **"Kickflip Chronicles"**  
   *Tagline:* A journey through skate, style, and street culture.  

3. **"Skate. Adolfo. Repeat."**  
   *Tagline:* Living life with balance, board, and boundless energy.  

4. **"Shredlines by Adolfo"**  
   *Tagline:* Where every grind tells a story.  

5. **"Flow State with Adolfo"**  
   *Tagline:* Capturing the thrill and freedom of the ride.  

6. **"Ollies and Oddities"**  
   *Tagline:* Adolfo’s skate tales, tricks, and street adventures.  

7. **"Wheels in Motion"**  
   *Tagline:* Skating life’s path with style and speed.  

8. **"Street Deck Diaries"**  
   *Tagline:* Adolfo’s take on skating, creativity, and urban flow.  

9. **"Grindology 101"**  
   *Tagline:* The art of skating through life, with Adolfo as your guide.  

10. **"Adrenaline & Asphalt"**  
   *Tagline:* Riding the pulse of the city with a board underfoot.  

---

Which direction speaks to you the most? I can refine or expand on these ideas!

#### En Español:

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/6c7cc71c-91f9-46e0-a32c-fb86235bd36f" />

```text
Eres un creador de palabras capaz de generar títulos y eslóganes atractivos y creativos para páginas de inicio personales. Utilizas la información proporcionada por el usuario para elaborar sugerencias que reflejen sus habilidades e intereses.

Soy Adolfo y mi pasatiempo favorito es Patinar.

Primero, piense en algunas palabras o frases que se relacionen con Adolfo y Patinar.
 
En segundo lugar, intente combinar o jugar con estas palabras o frases para crear títulos pegadizos o ingeniosos.
 
En tercer lugar, agregue un eslogan que explique o amplíe el título.
```

### Palabras relacionadas con Adolfo y patinar:
- Adolfo
- Patines
- Ruedas
- Movimiento
- Equilibrio
- Libertad
- Velocidad
- Vuelo
- Deslizar
- Ritmo
- Asfalto
- Pistas
- Flow

### Títulos creativos y pegadizos:
1. **"Adolfo sobre Ruedas"**  
   *Eslogan:* "Explorando la libertad, un giro a la vez."

2. **"Flow en Movimiento"**  
   *Eslogan:* "Donde la pasión por patinar se encuentra con el arte de deslizarse."

3. **"Pistas de Adolfo"**  
   *Eslogan:* "Deja que el asfalto cuente mi historia."

4. **"Vuelo sin Alas"**  
   *Eslogan:* "Deslizarse es la forma más pura de sentir la libertad."

5. **"Ritmo sobre Ruedas"**  
   *Eslogan:* "El mundo es mi pista de baile."

6. **"El Arte de Deslizar"**  
   *Eslogan:* "Con cada giro, una nueva expresión."

7. **"Velocidad con Alma"**  
   *Eslogan:* "No solo patino, vivo cada segundo en movimiento."

### Bonus: Opciones más personales:  
8. **"Adolfo en su Elemento"**  
   *Eslogan:* "La pista es mi lienzo, las ruedas mi pincel."  

9. **"Patinar, mi Segundo Nombre"**  
   *Eslogan:* "Adolfo: equilibrio, flow y pasión sobre ruedas."

10. **"Sobre Ruedas y Sonrisas"**  
    *Eslogan:* "Cada giro es una nueva oportunidad para soñar."  

¿Qué te parecen? ¿Quieres que desarrolle alguno más o que ajustemos el enfoque? 😊

### Usando Bing Copilot

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/07007f77-1caa-442d-ac8f-dbffc891d3e0" />

```text
You are a wordsmith that can generate catchy and creative titles and taglines for personal home pages. You use the information provided by the user to come up with suggestions that reflect their skills and interests.
 
I am Adolfo and my favorite hobby is skate.
 
First, think of some words or phrases that relate to Adolfo and skate.
 
Second, try to combine or play with these words or phrases to create catchy or witty titles.
 
Third, add a tagline that explains or expands on the title.
```

Sure thing, Adolfo! Let's get those creative juices flowing. 

First, here are some words and phrases related to you and skating:
- Adolfo
- Skate
- Wheels
- Tricks
- Freedom
- Urban
- Flow
- Grind
- Passion
- Adventure

Next, let’s combine these words to create some catchy titles and taglines for your personal homepage:

### 1. Adolfo on Wheels
*Tagline: Where passion meets pavement.*

### 2. Grind and Glide with Adolfo
*Tagline: Embracing the urban jungle one trick at a time.*

### 3. Adolfo’s Skate World
*Tagline: A journey of freedom, flow, and adventure.*

### 4. Skate Passion: Adolfo's Playground
*Tagline: Life's too short to stay off the board.*

### 5. Adolfo's Trick Tales
*Tagline: Chronicles of a skater's freedom and grind.*

Feel free to mix and match, or let me know if you’d like more ideas! 🛹✨

#### En Español:

<img width="1512" alt="image" src="https://github.com/user-attachments/assets/c7a23076-76fa-46cc-8c5a-4170fe10fa61" />

```text
Eres un creador de palabras capaz de generar títulos y eslóganes atractivos y creativos para páginas de inicio personales. Utilizas la información proporcionada por el usuario para elaborar sugerencias que reflejen sus habilidades e intereses.

Soy Adolfo y mi pasatiempo favorito es Patinar.

Primero, piense en algunas palabras o frases que se relacionen con Adolfo y Patinar.
 
En segundo lugar, intente combinar o jugar con estas palabras o frases para crear títulos pegadizos o ingeniosos.
 
En tercer lugar, agregue un eslogan que explique o amplíe el título.
```

¡Claro, Adolfo! Vamos a poner esas neuronas creativas a trabajar.

Primero, aquí tienes algunas palabras y frases que se relacionan contigo y con patinar:
- Adolfo
- Patinar
- Ruedas
- Trucos
- Libertad
- Urbano
- Flujo
- Grindar
- Pasión
- Aventura

Ahora, juguemos con estas palabras para crear títulos pegadizos e ingeniosos con sus respectivos eslóganes:

### 1. **Adolfo sobre Ruedas**
*Eslogan: Donde la pasión y la calle se encuentran.*

### 2. **Grind y Flujo con Adolfo**
*Eslogan: Dominando la jungla urbana truco a truco.*

### 3. **El Mundo de Adolfo en Patineta**
*Eslogan: Una travesía de libertad, flujo y aventura.*

### 4. **Pasión por el Patinaje: El Patio de Adolfo**
*Eslogan: La vida es demasiado corta para no estar sobre ruedas.*

### 5. **Cuentos de Trucos de Adolfo**
*Eslogan: Crónicas de libertad y grindar sobre una patineta.*

Siéntete libre de mezclar y combinar, o si necesitas más ideas, ¡dímelo! 🛹✨

---

I always ensure that users understand they can count on me in all of their languages. In this case, I made sure to communicate in Spanish, the user's preferred language.


### 3.2.2 Dar estilo a la typeface - tipografía

La ***typeface - tipografía*** es un diseño distintivo que es común a cualquier conjunto relacionado de letras, números y símbolos. Un momento, te oigo decir, ¿eso no es una ***font - fuente***? ¿Cuál es la diferencia? A todos los efectos prácticos, los dos términos son intercambiables. Sin embargo, técnicamente, una ***font - fuente*** *es una implementación particular de una* ***typeface - tipografía***, lo que significa que la ***typeface - tipografía*** se representa con un tamaño y estilo específicos. Arial es una ***typeface - tipografía***; Arial 16-point bold es una ***font - fuente***.

Estas son las cinco categorías ***typeface - tipográficas***  que encontrarás con más frecuencia:

<img width="909" alt="image" src="https://github.com/user-attachments/assets/66da79fd-6b03-4cc4-99ea-2614e89326ae">

<img width="916" alt="image" src="https://github.com/user-attachments/assets/a5af089b-dc64-48d8-8f65-942404b782fa">


**Serif**: una tipografía *serif* (que rima con sheriff ) contiene trazos cruzados finos (llamados *feet - pies* ) en los extremos de cada carácter. Estos sutiles apéndices le dan a la tipografía un aspecto tradicional y elegante, pero pueden perderse cuando se muestran en una pantalla en tamaños pequeños.

**Sans serif**: una tipografía *sans serif* no contiene trazos cruzados en los extremos de los caracteres. Estas tipografías suelen tener un aspecto limpio y moderno que se adapta bien al texto en pantalla, especialmente en tamaños pequeños.

**Monospace**: un tipo de letra *monospace* (también llamado *fixed-width* typeface) utiliza la misma cantidad de espacio para cada carácter, por lo que las letras delgadas como *i* y *l* ocupan tanto espacio como las letras más anchas como *m* y *w*.

**Cursive**: los tipos de letra *cursive* están diseñados para parecerse a la escritura manuscrita con bolígrafo o pincel.

**Fantasy**: Las tipografías *fantasy* suelen ser diseños extravagantes que tienen algunos elementos extremos (como ser extra gruesas).

En el código CSS, el tipo de letra se especifica mediante la propiedad `font-family`:

<img width="906" alt="image" src="https://github.com/user-attachments/assets/36e7d08b-d59b-4d3a-9fea-b7500028a7e0">

Reemplace el placeholder `typeface` con el nombre del tipo de letra. (Si el nombre del tipo de letra incluye uno o más espacios, debe encerrarlo entre comillas). Por ejemplo, cada una de las categorías de tipo de letra anteriores tiene su propia palabra clave CSS, por lo que las siguientes son todas declaraciones CSS legítimas:

<img width="909" alt="image" src="https://github.com/user-attachments/assets/14972ba1-44d5-4b7b-b67e-d01392573b6d">

Estas cinco palabras clave `serif`, `sans-serif`, `monospace`, `cursive` y `fantasy` representan los llamados tipos de letra genéricos, que están disponibles en todos los navegadores web. Si desea utilizar uno de estos tipos de letra genéricos para un componente de su página web, puede incluir la palabra clave del tipo de letra correspondiente como parte de sus instrucciones para ChatGPT:

<img width="909" alt="image" src="https://github.com/user-attachments/assets/3180dfe9-4318-41f5-a2ae-ee591b8c4d26">

```text
Style the web page tagline with the generic cursive typeface.
```

```text
Dale estilo al eslogan de la página web con la tipografía cursiva genérica.
```

Tenga en cuenta también que es posible especificar varios tipos de letra en una única declaración y que el navegador web utiliza el primer tipo de letra (de izquierda a derecha) que está instalado en el dispositivo del usuario. Es importante recordar esto porque ChatGPT casi siempre especificará varios tipos de letra en su CSS generado. A continuación, se incluye un ejemplo del código de la página web que examinamos más adelante en este capítulo:

<img width="901" alt="image" src="https://github.com/user-attachments/assets/75924804-896c-4282-b8d2-18bfabb09b32">

Esta declaración significa que el navegador web primero intentará cargar la tipografía `Roboto Serif`. Si no puede, por algún motivo, volverá a utilizar la tipografía genérica `serif`.

El siguiente componente principal con el que trabajarás es el type size - tamaño de la fuente.

### 3.2.3 Configuración del tamaño de la letra

El tamaño de la fuente es el tamaño relativo de cada carácter. Los tamaños de fuente se miden generalmente en píxeles (abreviado como `px`) y el tamaño de texto predeterminado del texto de una página normal es de 16 píxeles (escrito `16px` en el código de la página web).

En el código CSS, el tamaño de la fuente se especifica mediante la propiedad `font-size`:

<img width="907" alt="image" src="https://github.com/user-attachments/assets/fa8c32d8-6f4a-412f-a271-2912ad7cb484">

Aquí, reemplácelo `size` con el tamaño de fuente que desee. Por ejemplo, muchas personas consideran que el tamaño de fuente predeterminado de `16px` es demasiado pequeño para una lectura cómoda, por lo que es común especificar un tamaño de fuente más grande, como `20px`:

<img width="906" alt="image" src="https://github.com/user-attachments/assets/48ff5ba2-31b1-443e-88d2-e8a4c0b6157e">

La figura 3.3 muestra algunos tamaños de tipografía comunes.

<img width="897" alt="image" src="https://github.com/user-attachments/assets/53f99040-772a-4f17-b722-ce49b852086e">

**Figura 3.3 Algunos tamaños de tipografía comunes**

A continuación se muestra un ejemplo de instrucción para ChatGPT para especificar un tamaño de tipo para un componente de página:

<img width="906" alt="image" src="https://github.com/user-attachments/assets/699ebf74-79d7-48b5-a638-73cde684e24b">

```text
Style the web page tagline with a font size of 24px.
```

```text
Diseñe el eslogan de la página web con un tamaño de fuente de 24px.
```

### 3.2.4 Trabajar con estilos de tipografía

El estilo tipográfico es un estilo especial que se aplica a uno o más caracteres o palabras. Los dos estilos más comunes son **bold** y *italics*.

Para texto en negrita, CSS utiliza la propiedad `font-weight` con valor `bold`:

<img width="901" alt="image" src="https://github.com/user-attachments/assets/585bb6ee-ffcb-401d-b366-926dcaf92554">

A continuación se muestra un ejemplo de instrucción para ChatGPT para poner un componente de página en negrita:

<img width="905" alt="image" src="https://github.com/user-attachments/assets/8cd7ba76-fa0b-47d1-a4c0-a046357496ff">

Para *italic**, CSS utiliza la propiedad `font-style` establecida con la palabra clave `italic`:

<img width="903" alt="image" src="https://github.com/user-attachments/assets/325494fe-6849-4cbd-ac46-44e9b13f9b52">

A continuación se muestra un ejemplo de instrucción para que ChatGPT aplique estilo a un componente de página con cursiva:

<img width="906" alt="image" src="https://github.com/user-attachments/assets/e6491b0e-163a-445a-b074-4bf4543f3876">

```text
Style the web page tagline with italics.
```

```text
Dale estilo al eslogan de la página web con cursiva.
```

**NOTA**: También puede marcar palabras clave, títulos y otros textos especiales en negrita o cursiva mediante etiquetas HTML. Aprenderá cómo funcionan estas etiquetas en el capítulo 12.

Con solo estos tres aspectos de la tipografía web (el tipo de letra, el tamaño de letra y el estilo de letra) puedes lograr que tus páginas luzcan geniales. Cuando solicitas ChatGPT, puedes incluir instrucciones separadas para que el tipo se aplique a un componente, como se muestra, o puedes poner todo en una sola instrucción, como en este ejemplo:

<img width="914" alt="image" src="https://github.com/user-attachments/assets/44da21cf-5201-442a-9af0-1275829d4854">

```text
Style the web page tagline with the Arial typeface, 24px type size, and italics.
```

```text
Diseñe el lema de la página web con la fuente Arial, tamaño de fuente 24px y cursiva.
```

Si no está seguro de qué tipo de letra usar en su proyecto, ChatGPT puede ayudarlo, como muestro en la siguiente sección.

### 3.2.5 Cómo obtener sugerencias de tipografías de ChatGPT

Las tipografías genéricas que mencioné antes están bien, pero ¿sabías que hay cientos de ellas disponibles? Es una buena noticia porque significa que tus proyectos web pueden destacarse entre la multitud al usar tipografías interesantes, en particular al usar diferentes tipografías para el texto de la página normal y los encabezados. Sin embargo, no puedes simplemente elegir dos tipografías al azar. Debido a que cada tipografía tiene un estilo particular, es fácil elegir dos tipografías que no combinen de alguna manera, al igual que es fácil elegir colores que no combinen. Pero, ¿cómo puedes no solo elegir un par de tipografías, sino también asegurarte de que esas tipografías combinen bien entre sí?

ChatGPT está aquí para ayudarte. En particular, puedes pedirle a ChatGPT que genere sugerencias de Google Fonts ( https://fonts.google.com ), que es un repositorio en línea de más de 1500 fuentes gratuitas. Aquí tienes un mensaje genérico que puedes usar para que ChatGPT sugiera un par de fuentes compatibles (una para los títulos y otra para el texto):

<img width="909" alt="image" src="https://github.com/user-attachments/assets/fc0f99e4-1356-449e-94ad-2071fc76021a">

```text
You are a font aficionado that can generate awesome font combinations for personal home pages. Use the information provided by the user to come up with suggestions that reflect the theme of the personal home page.
 
My personal home page is related to X.
 
First, using only fonts available at Google Fonts, suggest a Y font for the page headings.
 
Second, using only fonts available at Google Fonts, suggest a compatible Z font for the page text.
 
Third, please do not include Roboto or Open Sans in your suggestions. Be creative and bold in your choices.
```

```text
Eres un aficionado a las fuentes y puedes generar combinaciones de fuentes increíbles para páginas de inicio personales. Utiliza la información proporcionada por el usuario para elaborar sugerencias que reflejen el tema de la página de inicio personal.
 Mi página 
personal está relacionada con X.
 
Primero, utilizando sólo fuentes disponibles en Google Fonts, sugiera una fuente Y para los encabezados de página.
 En segundo lugar, utilizando únicamente fuentes disponibles en Google Fonts, sugiera una fuente Z 
compatible para el texto de la página.
 
En tercer lugar, no incluyas Roboto ni Open Sans en tus sugerencias. Sé creativo y atrevido en tus elecciones.
```

Reemplace `X` con una palabra o frase relacionada con su página de inicio personal y reemplace `Y` y `Z` con `serif` o `sans serif`. Lamentablemente, ChatGPT a menudo sugiere las fuentes `Roboto` y `Open Sans`. Estas son fuentes excelentes y hermosas, sin duda, pero si desea algo más interesante, asegúrese de excluir esas fuentes comunes en su mensaje, como lo hice yo.

En la figura 3.4, puedes ver que ChatGPT sugirió las tipografías `Josefin Sans` y `Roboto Serif` para mi página (generadas con Bing Copilot en modo Creativo). Son excelentes tipografías que deberían funcionar bien juntas.

<img width="851" alt="image" src="https://github.com/user-attachments/assets/d0d9d181-357b-41d7-b0cb-20400e99a279">

**Figura 3.4 Sugerencias de tipografía de ChatGPT**

Si utiliza Bing Copilot, la respuesta puede incluir algunos ejemplos de las tipografías sugeridas. De lo contrario, siga los enlaces a Google Fonts para examinar las tipografías sugeridas y asegurarse de que le guste lo que ve. Si las tipografías sugeridas no funcionan para su diseño, solicite a ChatGPT que lo intente nuevamente:

<img width="907" alt="image" src="https://github.com/user-attachments/assets/927dda5d-5cda-4b9d-a70f-0e8408f1f700">

```text
The suggested typefaces don't work for my personal home page design. Please suggest two different typefaces.
```

```text
Las tipografías sugeridas no sirven para el diseño de mi página de inicio personal. Sugiera dos tipografías diferentes.
```

Una vez que tengas dos tipos de letra que te gusten, no tendrás que hacer nada más que escribir o recordar sus nombres. Incluirás los nombres de los tipos de letra cuando le pidas a ChatGPT que cree el código de tu página web.

### 3.2.6 Generación de un esquema de color

De manera predeterminada, las páginas web utilizan texto negro sobre fondo blanco. Esa combinación de colores hace que el texto sea fácil de leer, pero no va a ganar ningún premio de diseño. No es necesario que te vuelvas loco con el color, pero pensar más allá del texto negro sobre fondo blanco es una manera fácil de ofrecer a tus lectores un poco de placer visual.

Existen muchas formas de especificar el color en la web, pero la más sencilla es utilizar uno de los 140 nombres de color predefinidos (o palabras clave). Van desde `aliceblue` hasta `yellow` e incluyen no solo colores estándar como `red`, `green` y `blue`, sino también tonos decididamente no estándar como `lemonchiffon`, `darkorchid` y `wheat`.

He incluido la lista completa de palabras clave de color en mi sitio Web Design Playground en wdpg.io/2/colorkeywords. La Figura 3.5 muestra una lista completa de palabras clave de colores

<img width="1033" alt="image" src="https://github.com/user-attachments/assets/3718f32a-8ec5-49ad-8c10-15cfa3effc4f">

**Figura 3.5 Para ver una lista completa de las palabras clave de color CSS en Web Design Playground, navegue a wdpg.io/2/colorkeywords.**

En la lista que se muestra en la figura 3.5, solo debe preocuparse por la columna Color y la columna Palabra clave. Puede ignorar con seguridad la rareza de la columna Valor RGB.

CSS define dos propiedades relacionadas con el color. La primera propiedad es `color`, que se utiliza para aplicar un color a un texto, y la segunda es `background-color`(a veces abreviada como `background`), que se utiliza para aplicar un color al fondo de un elemento:

<img width="1024" alt="image" src="https://github.com/user-attachments/assets/2b41906d-dc12-4059-98dd-c6c48bb84c3f">

Reemplace `keyword1` y `keyword2` con una palabra clave de color, como `darkblue` y `lavender`:

<img width="1026" alt="image" src="https://github.com/user-attachments/assets/8c5fdac5-2f95-4fc6-b735-3b86cc163d1a">

**ADVERTENCIA**: cuando elija colores para sus páginas web, debe asegurarse de que el texto siga siendo legible seleccionando colores de texto y de fondo que tengan el contraste suficiente. El texto oscuro sobre un fondo claro o el texto claro sobre un fondo oscuro es lo que debe buscar.

Tu página de inicio no necesita una combinación de colores compleja, pero es posible que quieras evitar el texto negro sobre blanco y optar por algo más interesante. Aquí tienes un mensaje que puedes usar para que ChatGPT te ayude a generar una combinación de colores para tu página de inicio:

<img width="1026" alt="image" src="https://github.com/user-attachments/assets/06d442be-7307-426c-b636-15a96070212c">

```text
You are web designer and know how to create beautiful and compelling color schemes. Use the information provided by the user to come up with suggestions that reflect the theme of the personal home page.
 
My personal home page is related to X.
 
First, design a color scheme for my personal home page. I want the page to be visually appealing and easy on the eyes. I'm thinking of using Y as the dominant hue. Suggest two other colors that would go well with Y.
 
Second, show some examples of the suggested color scheme.
 
Third, when suggesting colors, please use the standard CSS color keywords, such as aliceblue and papayawhip.
```

```text
Eres diseñador web y sabes cómo crear esquemas de colores atractivos y atractivos. Utiliza la información proporcionada por el usuario para elaborar sugerencias que reflejen el tema de la página de inicio personal.

Mi página personal está relacionada con X.

Primero, diseñe un esquema de colores para mi página de inicio personal. Quiero que 
la página sea visualmente atractiva y agradable a la vista. Estoy pensando en usar Y como tono dominante. Sugiera otros dos colores que combinen bien con Y.
 
En segundo lugar, muestre algunos ejemplos del esquema de color sugerido.
 
En tercer lugar, al sugerir colores, utilice las palabras clave de color CSS estándar, como aliceblue y papayawhip.
```

Reemplace `X` con una palabra o frase relacionada con su página de inicio personal y reemplace `Y` con la palabra clave del color que desea utilizar como tono principal en su sitio. Le pedí a ChatGPT un esquema de colores con `dodgerblue` como tono principal y la figura 3.6 muestra el resultado (generado con Bing Copilot en modo Creativo).

<img width="849" alt="image" src="https://github.com/user-attachments/assets/558c6410-7eeb-4caa-a313-c6e79de3fc8e">

**Figura 3.6 Sugerencias de esquema de colores de ChatGPT**

Tenga en cuenta que el mensaje le pide a ChatGPT que sugiera colores utilizando palabras clave de colores CSS estándar. Utilizará estas palabras clave como parte del mensaje cuando le pida a ChatGPT que genere el código de su página web.

Ya casi está listo para crear el mensaje de inicio de ChatGPT. El último paso es comprender cómo funcionan los encabezados de las páginas web, que es el tema de la siguiente sección.

### 3.2.7 Comprensión de los encabezados de las páginas web

Un encabezado de página web es una palabra o frase en negrita que se destaca verticalmente del resto del texto y sirve como título de la página o de una sección de la misma. En la mayoría de las páginas web, solo se utilizan tres tipos de encabezados:

* Un único encabezado principal, que es el título de la página.

* Uno o más encabezados de segundo nivel, que actúan como títulos de cada artículo o sección principal de la página.

* Dentro de cada encabezado de segundo nivel, uno o más encabezados de tercer nivel, que actúan como títulos de subsecciones

Afortunadamente, normalmente no es necesario especificar demasiado todo esto, ya que ChatGPT casi siempre determinará automáticamente la jerarquía de encabezados. Sin embargo, es posible que desee controlar el tamaño de fuente de sus encabezados para obtener el aspecto que desea. Para darle una idea de lo que está tratando, aquí hay algunas notas sobre los tamaños de fuente para los primeros tres niveles de encabezado:

* **First-level headings**: el tamaño de fuente predeterminado es `32px`. Según el título, su longitud y el efecto que desee lograr, los títulos de primer nivel (designados en HTML mediante la etiqueta `<h1>`) pueden ser mucho más grandes, como `48px`, `72px` o incluso más grandes.

* **Second-level headings**: el tamaño de fuente predeterminado es `24px`. Sin embargo, no es raro que los títulos de segundo nivel (designados en HTML mediante la etiqueta `<h2>`) sean un poco más grandes, como `28px` o `32px`.

* **Third-level headings**: el tamaño de fuente predeterminado es de aproximadamente `18,2px`. Dado que este tamaño predeterminado es solo un poco más grande que el texto de una página normal (`16px`), es posible que prefieras darle un estilo `<h3>` más grande a los títulos de tercer nivel (que se designan en HTML mediante la etiqueta ) como, por ejemplo, `20px` o `24px`.

Nuevamente, no es necesario que se adentre demasiado en los detalles del código web. Para la mayoría de los mensajes de las páginas web, solo necesitará indicarle a ChatGPT qué tamaño de fuente desea para cada encabezado, suponiendo que los tamaños de encabezado predeterminados no se ajusten al diseño de su página.

AQUIIIII
### 3.2.8 Elaboración del mensaje

Ahora tienes todo lo que necesitas para solicitarle a ChatGPT que te proporcione el código web para tu página de inicio. El mensaje debería comenzar de la siguiente manera:

Quiero crear una página personal. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web simple que incluya lo siguiente:
A continuación, especifique el contenido de su página, incluido lo siguiente (consulte la figura 3.7):

Un encabezado (consulte el capítulo 4) que incluye el título y el subtítulo de la página.

Una sección principal que comienza con un párrafo introductorio (que puede ser algo así como un mensaje de bienvenida al lector).

Uno o más títulos de segundo nivel seguidos de algún texto. Por ejemplo, el título “Películas que me gustan” podría ir seguido de una lista de tus películas favoritas. Para cada elemento, no es necesario que proporciones el texto completo; basta con unas pocas palabras o la primera oración. Puedes completar el texto más tarde, después de que ChatGPT haya generado el código.



Figura 3.7 Las secciones de la página de inicio personal

A continuación, le pides a ChatGPT que genere el CSS según el formato que deseas para tu página:

En segundo lugar, en un archivo separado, escriba el código CSS para lo siguiente:
A continuación, especifique el formato, incluido lo siguiente:

El color de fondo del encabezado (debe ser el color principal de su esquema de colores).

El tamaño de fuente y el color que desea utilizar para el título y el subtítulo de la página (el color debe ser el color secundario de su esquema de colores).

El tamaño de fuente y el color de los títulos de segundo nivel (el color debe ser el color principal de su esquema de colores).

El tamaño de fuente del texto de la página normal.

Las fuentes a utilizar para los encabezados y el texto de la página normal.

Un ancho máximo para la página. Esto evita que las líneas de texto sean demasiado largas. Una longitud máxima de 800 px es adecuada para la mayoría de las páginas.

A continuación se muestra un ejemplo de mensaje para mi página de inicio:

Quiero crear una página personal. No sé programar, así que necesito que me proporciones el código.
 
Primero, escriba el código HTML para una página web simple que incluya lo siguiente:
 * Un encabezado que incluye el título "Escritor críptico" y el subtítulo "Resolviendo acertijos con palabras y palabras con acertijos".
 * Una sección principal donde el primer párrafo contiene el texto entre comillas triples:
"""¡Hola! Mi nombre es Paul McFedries. Bienvenido a mi humilde hogar en la Web. Me alegro mucho de que hayas venido a conocerme mejor. ¡Disfruta!"".
 * El encabezado de segundo nivel “Lo que hago (en mi trabajo)” seguido de un párrafo que contiene el texto entre comillas triples:
"""Soy un escritor técnico con más de 100 libros en mi haber..."""
* El encabezado de segundo nivel “Lo que hago (por diversión)” seguido de un párrafo que contiene el texto entre comillas triples:
"""Mis pasatiempos e intereses incluyen crucigramas crípticos, juegos de palabras, juegos de palabras, panificación, tipografía, Art Decó..."""
* El encabezado de segundo nivel “Lo que leo” seguido de un párrafo que contiene el texto entre comillas triples:
"Actualmente estoy leyendo Landlines, de Raynor Winn. Mis últimas lecturas son The Faraway Nearby, de Rebecca Solnit, y Journal of a Solitude, de May Sarton..."
* El encabezado de segundo nivel “Lo que soy” seguido de un párrafo que contiene el texto entre comillas triples:
"""Aunque nací en Toronto, mis padres son ambos escoceses, lo que explica mi amor por las gaitas y el haggis..."""
 
En segundo lugar, en un archivo separado, escriba el código CSS para lo siguiente:
* El color de fondo del encabezado es azul dodger con un margen de 20 px alrededor. Centra el título y el subtítulo.
 * El tamaño de fuente del título es 48px con color whitesmoke.
 * El tamaño de fuente de los subtítulos es de 24 px con color whitesmoke y formato cursiva.
 * El tamaño de fuente del encabezado de segundo nivel es 32 px con color dodgerblue.
 *El tamaño de fuente de la sección principal es 20px.
 * Para los títulos, utilice la fuente Josefin Sans de Google Fonts. Para el resto del texto, utilice la fuente Roboto Serif de Google Fonts.
 *La página está centrada.
 *La página es responsiva con un ancho máximo de 800px.
NOTA: incluí la instrucción para centrar la página porque una página que no ocupa toda la ventana del navegador (como esta página no ocupará ninguna ventana que tenga más de 800 px de ancho) generalmente se ve mejor cuando está centrada dentro de la ventana.

ChatGPT debe crear primero el código HTML, que puedes copiar y pegar y guardar en un archivo llamado index.html. En ese código, deberías ver una línea cerca de la parte superior similar a la siguiente:

<link rel="hoja de estilo" tipo="texto/css" href="estilos.css">
Este código le indica al navegador web que busque el código CSS en un archivo llamado styles.css, por lo que su próxima tarea es copiar el código CSS generado y luego pegarlo y guardarlo en un archivo llamado styles.css (o cualquier nombre que vea en la <link>etiqueta). Asegúrese de guardar styles.css en la misma carpeta que su archivo index.html. Consulte el apéndice A para obtener más información sobre cómo trabajar con archivos HTML y CSS. Envié este mensaje a Bing Copilot en modo Precise y el código que generó dio como resultado la página que se muestra en la figura 3.8.



Figura 3.8 Mi página de inicio personal generada por ChatGPT

En este punto, si está satisfecho con la página de inicio personal que ChatGPT creó para usted, puede omitir el resto de este capítulo e implementar el código como describo en el apéndice B. Sin embargo, si tiene curiosidad por saber un poco más sobre el código que ChatGPT generó, continúe con la siguiente sección.

3.3 Examinar el código de la página de inicio personal
En esta sección, le daré una descripción general breve y no técnica del código de la página de inicio personal que ChatGPT generó para mí (y que produjo la página que se muestra en la figura 3.8). Es probable que el código que ChatGPT genere para usted no sea el mismo, por dos razones:

ChatGPT tiene un grado de aleatoriedad incorporado, por lo que incluso indicaciones idénticas a menudo pueden generar respuestas ligeramente diferentes.

El código de la página web generado por ChatGPT varía según la versión del modelo (GPT-3.5 versus GPT-4), la aplicación utilizada (OpenAI versus Copilot) y, para Copilot, el modo utilizado (creativo, equilibrado o preciso).

Dicho esto, el código de tu página de inicio personal probablemente será muy similar al mío, por lo que las anotaciones de código en las próximas dos secciones deberían ser útiles si tienes curiosidad acerca de cómo funciona el código.

3.3.1 Examinar el HTML
Comenzaré con el código HTML generado por ChatGPT para mi página de inicio personal, que se muestra aquí:

<!DOCTYPE html>
<html>
  <cabeza>
    <link href="https://fonts.googleapis.com/css?family=Josefin+Sans|Roboto+Serif"
rel="hoja de estilo">                                                       ① 
    <link rel="hoja de estilo" tipo="texto/css" href="estilos.css">           ②
    <title>Escritor críptico</title>
  </cabeza>
  <cuerpo>
    <header>                                                            ③ 
      <h1>Escritor críptico</h1>                                           ④ 
      <h2>Resolver acertijos con palabras y palabras con acertijos.</h2>       ⑤
    </encabezado>
    <main>                                                              ⑥ 
      <p>¡Hola! Mi nombre es Paul McFedries. Bienvenido a mi humilde            ⑦ 
         hogar lejos de casa en la web. Me alegro mucho de que hayas pasado por aquí            ⑦ 
         para conocer más sobre mí. ¡Disfruta!</p>                             ⑦ 
      <h2>Lo que hago (por trabajo)</h2>                                     ⑧
      <p>Soy un escritor técnico con más de 100 libros en mi haber...</p>
      <h2>Lo que hago (por diversión)</h2>                                      ⑧
      <p>Mis pasatiempos e intereses incluyen crucigramas crípticos,
         juegos de palabras, juegos de palabras, panificación, tipografía, Art Decó...</p>
      <h2>Lo que leo</h2>                                              ⑧
      <p>Actualmente estoy leyendo Landlines, de Raynor Winn.
         Las lecturas son The Faraway Nearby de Rebecca Solnit, Journal
         De una soledad de May Sarton...</p>
      <h2>Lo que soy</h2>                                                ⑧
      <p>Aunque nací en Toronto, mis padres son ambos
         Escocés, lo que explica mi amor por las gaitas y
         haggis...</p>
    </principal>
  </cuerpo>
</html>
① Carga las fuentes Josefin Sans y Roboto Serif de Google Fonts

② Le dice al navegador web dónde encontrar el código CSS

③ Encabezado de página

④ Título de la página

⑤ Subtítulo de la página

⑥ Sección principal de la página

⑦ Párrafo de texto regular

⑧ Encabezados de segundo nivel

Tenga en cuenta, en particular, el código que le dice al navegador web dónde encontrar el código CSS, que describo en la siguiente sección.

3.3.2 Examinando el CSS
El código CSS que ChatGPT generó para mi página de inicio se muestra aquí:

cuerpo {
  familia de fuentes: 'Roboto Serif', serif;       ① 
  ancho máximo: 800px;                         ② 
  margen: automático;                             ③
}
 
encabezado {
  color de fondo: dodgerblue;             ④ 
  relleno: 20px;                            ⑤ 
  alineación del texto: centro;                       ⑥
}
 
encabezado h1 {
  familia de fuentes: 'Josefin Sans', sans-serif; ⑦ 
  tamaño de fuente: 48px;                          ⑧ 
  color: whitesmoke;                        ⑧
}
 
encabezado h2 {
  familia de fuentes: 'Josefin Sans', sans-serif; ⑦ 
  tamaño de fuente: 24px;                          ⑨ 
  color: whitesmoke;                        ⑨
  estilo de fuente: cursiva;    
}
 
principal {
  tamaño de fuente: 20px;                          ⑩
}
 
principal h2 {
  familia de fuentes: 'Josefin Sans', sans-serif; ⑦ 
  tamaño de fuente: 32px;                          ⑪ 
  color: dodgerblue;                        ⑪ 
}
① Aplica Roboto Serif al texto de la página.

② Establece el ancho máximo de página en 800 px

③ Centra la página

④ Establece el fondo del encabezado en dodgerblue

⑤ Agrega 20 px de espacio alrededor del texto del encabezado

⑥ Centra el texto dentro del encabezado

⑦ Aplica Josefin Sans al texto del encabezado

⑧ Aplica estilo al título con tamaño de fuente 48 px y color whitesmoke

⑨ Aplica estilo al subtítulo con tamaño de fuente 24 px, color humo blanco y cursiva

⑩ Establece el tamaño de fuente de la página normal en 20 px

⑪ Aplica estilo a los encabezados de segundo nivel con tamaño de fuente 32 px y color dodgerblue

Si lo desea, puede utilizar estas anotaciones para modificar el código de su página web, como describo en la siguiente sección.

3.4 Personalización de la página de inicio personal
Si el código de página de inicio personal que ChatGPT generó para usted no es el que deseaba, tiene dos opciones:

Si la página resultante no se acerca a lo que desea, probablemente sea mejor reescribir el mensaje, iniciar una nueva sesión de chat e intentarlo nuevamente.

Si la página resultante es bastante buena pero solo necesita algunos ajustes, solicite a ChatGPT que realice esos ajustes por usted. Asegúrese de enviar esta solicitud en la misma sesión que la solicitud original.

En el segundo caso, si el código producido por ChatGPT realmente solo necesita algunos pequeños retoques, considere modificar el código manualmente según las anotaciones que proporcioné en la sección anterior. Como no conoce el código de las páginas web, es mejor no intentar realizar cambios importantes. Sin embargo, aún quedan algunas formas de alterar el código para obtener la página que desea.

Primero, aquí hay algunas sugerencias de personalización para el código HTML:

En el encabezado, puedes editar el título o el subtítulo. Solo asegúrate de no editar ni eliminar las etiquetas HTML asociadas: <h1>y </h1>para el título; <h2>y </h2>para el subtítulo.

En la sección principal del código HTML, puede agregar, eliminar o editar el texto dentro de cada encabezado de segundo nivel (es decir, el texto entre las etiquetas <h2>y </h2>; asegúrese de no editar ni eliminar estas etiquetas).

En la sección principal del código HTML, puede agregar, eliminar o editar el texto dentro de cada párrafo (es decir, el texto entre las etiquetas <p>y </p>; asegúrese de no editar ni eliminar estas etiquetas).

En la sección principal del código HTML, puede agregar un nuevo párrafo escribiendo una <p>etiqueta, seguido del texto del párrafo, seguido de la </p>etiqueta.

A continuación se muestran algunas ideas de personalización para el código CSS:

Si desea que su página de inicio tenga un ancho máximo diferente, cambie el max-widthvalor a algo distinto de 800px.

Para cualquier valor de color, puede cambiar el color existente a una palabra clave de color diferente.

Para cualquier valor de tamaño de fuente, puede cambiar el número para aumentar o disminuir el tamaño de la fuente. Solo asegúrese de dejar la pxunidad en su lugar.

Para que el código de su página sea más accesible, considere convertir todas las medidas en px a medidas en rem. 1 rem es, de manera predeterminada, equivalente a 16 px, por lo que 20 px es 1,25 rem, 24 px es 1,5 rem, 32 px es 2 rem, 48 px es 3 rem, y así sucesivamente. La unidad rem es más accesible porque mide los tamaños de fuente en relación con el tamaño de fuente predeterminado que el usuario del navegador ha definido en la configuración de su navegador.

Resumen
Al contarle a ChatGPT un poco sobre el contenido de su página, puede incitarlo a generar títulos y subtítulos creativos.

ChatGPT puede ayudarle con tres aspectos clave de la tipografía web: el tipo de letra, el tamaño de letra y el estilo.

Puedes pedirle a ChatGPT que cree un esquema de color utilizando cualquiera de las 140 palabras clave de color que ofrece CSS.

Casi todas las páginas web utilizan encabezados: un encabezado de primer nivel que actúa como título de la página, así como uno o más encabezados de segundo y tercer nivel.

Para obtener mejores resultados, el mensaje de su página debe ser lo más específico posible, incluidos colores, tamaños de fuente y niveles de encabezado.

Guarde el HTML generado en el archivo index.html y el CSS generado en el nombre de archivo sugerido por ChatGPT en el código HTML, generalmente styles.css.
