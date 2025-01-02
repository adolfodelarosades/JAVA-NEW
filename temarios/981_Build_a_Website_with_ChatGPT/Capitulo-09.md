# 9 Cómo agregar listas a tus páginas

Este capítulo cubre

* Cómo solicitar a ChatGPT que cree una lista con viñetas
* Solicitar a ChatGPT que genere una lista numerada
* Personalizando tus listas
* Elaboración de un mensaje de ChatGPT para crear una página de recetas
* Examinar y personalizar el código generado por ChatGPT

“El contenido es el rey - Content is king” es un viejo (y, por desgracia, sexista) dicho de los primeros tiempos de la web. Significaba que lo más importante de cada página web era el contenido que contenía. En otras palabras, si publicabas un contenido excelente, todo el mundo iría a tu sitio web.

Puede que esto fuera cierto en los años 90, cuando la gente no esperaba demasiado de cada página web que visitaba. Sin embargo, hoy en día, tener un contenido excelente no sirve de nada si lo presentas mal. Si has pasado por alguno de los proyectos web de los capítulos anteriores, es posible que te hayas sorprendido (pero espero que no te hayas desanimado) por lo específicos que han sido todos mis prompts de ChatGPT. Ese nivel de detalle es necesario porque, de lo contrario, ChatGPT generará código para páginas que son decididamente poco atractivas: aburridas, estrechas y mal diseñadas. Sí, tienes un contenido increíble que quieres compartir, pero para evitar que los visitantes se vayan segundos después de llegar, necesitas presentar ese contenido de forma atractiva.

En este capítulo, aprenderá dos técnicas para hacer que su contenido sea más fácil de leer, más fácil de entender y más atractivo para el lector. Las dos técnicas son listas con viñetas y listas numeradas(bulleted lists and numbered lists), que se encuentran entre los patrones más comunes utilizados en las páginas web modernas y forman la base de algunos de los sitios más populares de la actualidad. Luego, pondrá en práctica su nuevo conocimiento sobre listas para crear un mensaje detallado para que ChatGPT genere el código para una página de recetas. Este capítulo también proporciona una explicación de alto nivel del código generado por ChatGPT y sugerencias para personalizarlo.

## 9.1 Revisando el proyecto de este capítulo

El proyecto que ChatGPT creará para usted en este capítulo es una página web básica que guía al lector a través de una receta para hacer barras de nueces. La página final incluirá los siguientes componentes:

* Un elemento de header que incluye el logotipo, el título y el eslogan del sitio web.
* Un elemento main que comienza con el título de la receta y la introducción.
* Un par de listas con viñetas(bulleted lists) que contienen los ingredientes de la receta.
* Una lista numerada(numbered list) de los pasos de la receta.
* Un elemento de footer que incluye un aviso de derechos de autor

La Figura 9.1 muestra un ejemplo del tipo de página que convencerás a ChatGPT que genere para ti en este capítulo.

![image](https://github.com/user-attachments/assets/a39f824d-f24a-4d7e-8694-fb6c90a84e45)

**Figura 9.1 Una página de recetas generada por ChatGPT**

La página de ejemplo incluye dos listas con viñetas y una única lista numerada (con una sublista numerada), pero puedes modificar fácilmente este proyecto para incluir solo una lista con viñetas, solo una lista numerada o varias listas de ambos tipos. Esto significa que puedes crear páginas que incluyan contenido como listas de los 10 mejores, tutoriales, documentación, guías de viaje, reseñas de productos y listas de tus libros, películas, programas de televisión, juegos, sabores de helado, autores de libros de informática y más favoritos. Antes de llegar a todo eso, necesitas saber un poco sobre cada tipo de lista.

## 9.2 Crear una bulleted list - lista con viñetas

Una lista con viñetas es una colección de elementos HTML que presentan varios elementos como una lista vertical, donde cada elemento tiene una sangría leve desde el margen izquierdo y está precedido por un pequeño círculo negro llamado *viñeta - bullet*. Se utiliza una lista con viñetas cuando se quieren presentar varios elementos, pero el orden de esos elementos no es un componente esencial de la lista. La Figura 9.2 muestra un ejemplo de una lista con viñetas.

![image](https://github.com/user-attachments/assets/4d113758-a641-44ea-ba20-ecf021c5bd44)

**Figura 9.2 Un ejemplo de una lista con viñetas**

A continuación se explica cómo indicarle a ChatGPT que genere el código para dicha lista:

```text
Generate the HTML code for a bulleted list that includes the following items: "Francis", "Haden", "Honey", "Keitt", "Kent", and "Tommy Atkins".
```

```text
Genere el código HTML para una lista con viñetas que incluya los siguientes elementos: "Francis", "Haden", "Honey", "Keitt", "Kent" y "Tommy Atkins".
```

Aquí está el código resultante:

```html
<ul>
    <li>Francis</li>
    <li>Haden</li>
    <li>Honey</li>
    <li>Keitt</li>
    <li>Kent</li>
    <li>Tommy Atkins</li>
</ul>
```

Este código tiene dos componentes principales:

* Todo está rodeado por las etiquetas `<ul>` y `</ul>` (donde `ul` es la abreviatura de *unnumbered list -lista sin numerar* ).
* Cada elemento de la lista está rodeado por las etiquetas `<li>` y `</li>`(donde `li` es la abreviatura de *list item - elemento de lista*).

En el caso de elementos breves (una palabra o una frase corta), está bien encerrar cada elemento entre comillas. Si su lista contiene elementos con un texto mucho más largo, deberá utilizar el método que analizo en la siguiente sección.

### 9.2.1 Manejo de list items - elementos de listas más largas

Los elementos de una lista con viñetas no tienen por qué ser palabras individuales o frases cortas. Tienes la libertad de incluir tanto texto como necesites en cada elemento. (Dicho esto, si haces que el contenido de tus elementos sea demasiado largo (por ejemplo, más de unas pocas oraciones), tu lista será más difícil de leer y escanear). Para elementos más largos, tu mensaje debe separar los elementos claramente para que ChatGPT no se confunda. Aquí tienes un ejemplo de instrucción:

```text
Generate the HTML code for a bulleted list that includes the following items:
- "Sailing Alone Around the Room," by Billy Collins. The former U.S. poet laureate at the top of his game.
- "Blue Horses," by Mary Oliver. Each poem in this collection is a gem.
- "Human Wishes," by Robert Hass. If prose poetry is more your thing, you owe yourself these stunning examples of the form.
- "The Carrying," by Ada Limón. The current U.S. poet laureate at the top of *her* game.
- "All of Us," by Raymond Carver. The complete poetical works of the master of quiet desperation.
- "What the Living Do," by Marie Howe. A searingly honest search for hope amidst overwhelming grief. Highly recommended.
```

```text
Genere el código HTML para una lista con viñetas que incluya los siguientes elementos:
- "Navegando solo por la habitación", de Billy Collins. El ex poeta laureado estadounidense en la cima de su carrera.
- "Blue Horses", de Mary Oliver. Cada poema de esta colección es una joya.
- "Deseos humanos", de Robert Hass. Si la poesía en prosa es lo tuyo, te mereces estos ejemplos impresionantes de esta forma.
- "The Carrying", de Ada Limón. La actual poeta laureada estadounidense en la cima de *su* carrera.
- "All of Us", de Raymond Carver. Obra poética completa del maestro de la desesperación silenciosa.
- "Lo que hacen los vivos", de Marie Howe. Una búsqueda de esperanza desgarradora y sincera en medio de un dolor abrumador. Muy recomendable.
```

Observe que la instrucción precede cada elemento de la lista con un guión (`-`). ChatGPT entiende que un guión representa un nuevo elemento de la lista (el signo más (`+`) también funciona). La Figura 9.3 muestra cómo aparece el código generado por ChatGPT a partir de esta instrucción en un navegador web.

![image](https://github.com/user-attachments/assets/f9a02044-ac60-4ec8-a5df-e82469cc6fed)

**Figura 9.3 Una lista con viñetas con elementos de lista más largos**

¿Es necesario que uno de los puntos de tu lista tenga una lista con viñetas? Eso se explica en la siguiente sección.

### 9.2.2 Anidación de bulleted lists - listas con viñetas

Un patrón común de lista con viñetas es que uno de los elementos contenga su propia lista con viñetas. Esto se conoce como lista con viñetas anidada y permite dividir la información de la página en varios niveles, lo que puede hacer que los datos complejos sean mucho más claros y fáciles de seguir para los lectores.

A continuación se muestra un ejemplo de instrucción que convence a ChatGPT de generar una lista con viñetas donde uno de los elementos es una lista con viñetas anidada:

```text
Generate the HTML code for a bulleted list with the following items:
- Bread
- Milk
- Fruit
 - Bananas
 - Oranges
 - Papayas
- Chocolate
```

```text
Genere el código HTML para una lista con viñetas con los siguientes elementos:

- Pan
- Leche
- Fruta
 - Plátanos
 - Naranjas
 - Papayas
- Chocolate
```

Observe que, debajo del elemento `Fruit`, los tres elementos tienen una sangría de un espacio. Esta sangría es suficiente para que ChatGPT sepa que desea que esos elementos se muestren como una lista con viñetas anidadas. La Figura 9.4 muestra el código generado por ChatGPT en el navegador web.

![image](https://github.com/user-attachments/assets/49aca1f3-b644-4a76-93ce-9fbddab25ad1)

**Figura 9.4 Una lista con viñetas con una lista con viñetas anidada**

Aquí está el código detrás de esta lista:

```html
<ul>
    <li>Bread</li>
    <li>Milk</li>
    <li>Fruit
        <ul>
            <li>Bananas</li>
            <li>Oranges</li>
            <li>Papayas</li>
        </ul>
    </li>
    <li>Chocolate</li>
</ul>
```

Para ayudar al lector a diferenciar la lista anidada de la lista principal, el navegador web hace dos cosas:

* Sangra los elementos de la lista anidada un poco más que los elementos de la lista principal
* Utiliza un círculo hueco en lugar de un círculo relleno como viñeta del elemento.

Ese círculo hueco te permite saber que hay distintos tipos de viñetas disponibles. La siguiente sección te muestra cómo especificar un tipo de viñeta diferente para tus listas.

### 9.2.3 Cambiar el tipo de viñeta - bullet 

De manera predeterminada, los navegadores web muestran una lista con viñetas con un círculo relleno (también llamado *disc-disco*) como viñeta. Sin embargo, ese tipo de viñeta predeterminado no está definido de manera definitiva. A continuación, se muestra un mensaje genérico que le indica a ChatGPT que use un tipo de viñeta diferente:

```text
Generate the HTML code for a bulleted list with the items below. Use a type as the bullet.
- Item 1
- Item 2
- etc.
```

```text
Genere el código HTML para una lista con viñetas con los elementos que se muestran a continuación. Utilice un tipo como viñeta.
- Artículo 1
- Artículo 2
- etc.
```

En su instrucción, reemplace `type` con uno de los siguientes:

* La palabra `circle` para utilizar un círculo sin relleno como viñeta.
* La palabra `square` para utilizar un cuadrado relleno como viñeta.
* El nombre de cualquier carácter emoji, como Check Mark, Star, Heart, Arrow, o Smiley Face.

El nombre de cualquier otro carácter Unicode, como such as Black Right-Pointing Triangle, Rightwards Arrow, o White Diamond. (Visite www.unicode.org/charts para ver los caracteres disponibles: ¡los 144 000 que hay!)

La Figura 9.5 muestra una lista con viñetas que utiliza caracteres emoji de marca de verificación en lugar de las viñetas normales.

![image](https://github.com/user-attachments/assets/9ea2fd7e-23d0-48cf-b9c2-3887cd220207)

**Figura 9.5 Una lista con viñetas que utiliza emojis de marca de verificación como viñetas**

Las listas con viñetas son algo común en Internet, pero no son las únicas. Las listas numeradas son el tema de la siguiente sección.

## 9.3 Construir una lista numerada - numbered list

Mencioné anteriormente que se usa una lista con viñetas cuando el orden de los elementos de la lista no es un componente esencial de la misma. Sin embargo, para muchas colecciones de elementos, el orden es importante y sus páginas web pueden mostrar esos elementos mediante una lista numerada.

Por ejemplo, si proporciona un conjunto de instrucciones paso a paso, es fundamental que el procedimiento comience con el primer paso y luego continúe secuencialmente hasta el paso final. De manera similar, para una clasificación de los 10 primeros, probablemente desee que el elemento que ocupa el puesto 10 aparezca primero, seguido del elemento que ocupa el puesto 9 y continúe hasta el elemento que ocupa el puesto más alto, que aparece en último lugar.

La figura 9.6 muestra un ejemplo de una lista numerada. A continuación, se muestra cómo indicarle a ChatGPT que genere el código correspondiente:

```text
Generate the HTML code for a numbered list with the following items:
-Inflatable Dartboard
-Water-Resistant Sponge
-Helium-Filled Paperweight
-Teflon Bath Mat
-Flame-Retardant Firewood
```

```text
Generar el código HTML para una lista numerada con los siguientes elementos:
-Diana inflable
-Esponja resistente al agua
-Pisapapeles lleno de helio
-Alfombrilla de baño de teflón
-Leña retardante al fuego
```

![image](https://github.com/user-attachments/assets/6cc3f574-f359-4842-b3ef-53567f21ad84)

**Figura 9.6 Un ejemplo de una lista numerada**

Ten en cuenta que debes anteponer un guion (`-`) a cada elemento de tu lista. También puedes utilizar un signo más (`+`), un asterisco (`*`) o incluso el número 1 seguido de un punto (`1.`). Este es el código resultante:

```html
<ol>
    <li>Inflatable Dartboard</li>
    <li>Water-Resistant Sponge</li>
    <li>Helium-Filled Paperweight</li>
    <li>Teflon Bath Mat</li>
    <li>Flame-Retardant Firewood</li>
</ol>
```

Este código tiene dos componentes principales:

* Todo está rodeado por las etiquetas `<ol>` y `</ol>`(donde `ol` es la abreviatura de *ordered list-lista ordenada* ).
* Cada elemento de la lista está rodeado por las etiquetas `<li>` y `</li>`(donde `li` es la abreviatura de *list item - elemento de lista*).

El navegador web siempre muestra listas numeradas que comienzan con el primer elemento como número 1, pero hay un par de formas de personalizar el orden de la lista. En primer lugar, en la siguiente sección aprenderá a invertir el orden de la lista.

### 9.3.1 Invertir el orden de la lista

Cuando se utiliza una lista numerada como parte de un tutorial, la documentación de un producto o una receta, se desea que el lector comience con el paso 1, continúe con el paso 2 y continúe en secuencia hasta el paso final. Sin embargo, no todas las listas numeradas se ajustan a este patrón. Por ejemplo, es tradicional que una lista de los 10 primeros comience en el número 10, presente el número 9 y así sucesivamente hasta el número 1.

Para convencer a ChatGPT de que cree dicha lista, indíquele que genere una *reversed numbered list - lista numerada invertida*, como en este ejemplo:

```text
Generate the HTML code for a reversed numbered list with the following items:
-U.C. Santa Cruz Banana Slugs
-Delta State Fighting Okra
-Kent State Golden Flashes
-Evergreen State College Geoducks
-New Mexico Tech Pygmies
-South Carolina Fighting Gamecocks
-Southern Illinois Salukis
-Whittier Poets
-Western Illinois Leathernecks
-Delaware Fightin' Blue Hens
```

```text
Genere el código HTML para una lista numerada invertida con los siguientes elementos:
-Babosas banana de la Universidad de California en Santa Cruz
-Okra de lucha contra el estado del Delta
-Destellos dorados del estado de Kent
-Geoducks del Evergreen State College
-Pigmeos tecnológicos de Nuevo México
-Gallos de pelea de Carolina del Sur
-Salukis del sur de Illinois
-Poetas de Whittier
-Cuellos de cuero del oeste de Illinois
-Gallinas azules luchadoras de Delaware
```

La Figura 9.7 muestra cómo se representa en el navegador web el código generado por ChatGPT a partir de esta instrucción.

![image](https://github.com/user-attachments/assets/f0a5e705-8676-40dc-a741-2e4e3002c070)

**Figura 9.7 Una lista numerada invertida**

El otro método que puede utilizar para cambiar el orden de una lista numerada es especificar el número inicial de la lista, que es el tema de la siguiente sección.

### 9.3.2 Cambiar el número de inicio de la lista

De manera predeterminada, una lista numerada normal comienza con el número 1, y una lista numerada invertida comienza con un valor igual al número de elementos de la lista. Sin embargo, usted es libre de especificar cualquier valor inicial que desee. ¿Por qué querría hacer algo así? Un ejemplo común es cuando presenta parte de una lista más grande (como un contrato). Si esa parte de la lista más grande comienza en el número 4, por ejemplo, también debería hacerlo la lista numerada que presenta al lector.

Otro ejemplo común es cuando se inicia una lista numerada, se tiene una sección de texto y luego se tiene una nueva lista numerada que pretende ser una continuación de la primera. La Figura 9.8 muestra lo que sucede en el navegador.

![image](https://github.com/user-attachments/assets/286ed1f1-8055-44fb-bc2c-fe1521f399b3)

**Figura 9.8 Una lista, interrumpida**

El problema aquí es que la segunda lista comienza de nuevo en el paso 1 cuando debería continuar con el paso 5. Afortunadamente, puedes indicarle a ChatGPT el valor inicial de una lista numerada incluyendo `starting at` X en tu mensaje, donde *X* es el valor inicial que deseas. Aquí tienes un ejemplo:

```text
Generate the HTML code for a numbered list starting at 5 with the following items:
-Wait for the water to boil: You'll know the water is boiling when you see bubbles rising to the surface rapidly. This could take anywhere from a few minutes to over ten minutes, depending on how much water you're boiling and how powerful your stove is.
-Turn off the stove: Once your water has reached a rolling boil (or once it's heated to your desired temperature), carefully turn off the stove.
```

```text
Generar el código HTML para una lista numerada que comienza en 5 con los siguientes elementos:

-Espera a que hierva el agua: sabrás que el agua está hirviendo cuando veas burbujas subiendo rápidamente a la superficie. Esto puede tardar desde unos minutos hasta más de diez minutos, según la cantidad de agua que estés hirviendo y la potencia de tu estufa.
- Apaga el fuego: una vez que el agua haya hervido (o se haya calentado a la temperatura deseada), apaga el fuego con cuidado.
```

La Figura 9.9 muestra que el código generado por ChatGPT a partir de esta instrucción ahora representa la segunda lista correctamente como una continuación de la primera.

![image](https://github.com/user-attachments/assets/0c09dba5-163f-4564-ba8c-744d0abb4ccd)

**Figura 9.9 La segunda lista es ahora una continuación adecuada de la primera lista.**

¿Necesita que uno de los elementos de una lista anidada tenga su propia lista numerada? La siguiente sección le indica todo lo que necesita saber.

### 9.3.3 Anidación de numbered lists - listas numeradas

En ocasiones, es necesario incluir "subpasos" en una lista numerada. En un tutorial, por ejemplo, es posible que desee dividir un elemento en particular en varios subelementos para lograr mayor claridad o precisión. De manera similar, es común que los textos legales tengan cláusulas y subcláusulas numeradas. Una colección de subpasos dentro de una lista numerada más grande se denomina lista numerada *anidada - nested*.

A continuación se muestra un ejemplo de mensaje que le pide a ChatGPT que genere una lista numerada donde cada uno de los dos pasos principales tiene múltiples subpasos:

```text
Generate the HTML code for a numbered list with the following items:
-Get into the starting position:
 -Place two balls in your dominant hand, one in front of the other.
 -Hold the third ball in your other hand.
 -Let your arms dangle naturally and bring your forearms parallel to the ground (as though you were holding a tray).
-Make the first toss:
 -Of the two balls in your dominant hand, toss the front one toward your left hand in a smooth arc.
 -Make sure the ball doesn't spin too much.
 -Make sure the ball goes no higher than about eye level.
```

```text
Generar el código HTML para una lista numerada con los siguientes elementos:
-Ponte en la posición inicial:
 -Coloca dos bolas en tu mano dominante, una delante de la otra.
 -Sujeta la tercera pelota con la otra mano.
 -Deja que tus brazos cuelguen naturalmente y lleva tus antebrazos paralelos al suelo (como si estuvieras sosteniendo una bandeja).
-Realizar el primer lanzamiento:
 -De las dos bolas que tienes en tu mano dominante, lanza la delantera hacia tu mano izquierda formando un arco suave.
 -Asegúrate de que la pelota no gire demasiado.
 -Asegúrese de que la pelota no suba más allá del nivel de los ojos.
```

Observe que, en cada caso, los tres subelementos tienen una sangría de un espacio. Esta sangría le indica a ChatGPT que desea que esos elementos se muestren como una lista numerada anidada. La Figura 9.10 muestra el código generado por ChatGPT en el navegador web.

![image](https://github.com/user-attachments/assets/6389549b-9027-4bbf-8bb2-fe0ab47bd7c0)

**Figura 9.10 Una lista numerada con dos listas numeradas anidadas**

Aquí está el código detrás de esta lista:

```html
<ol>
    <li>Get into the starting position:
        <ol style="list-style-type: lower-roman;">
            <li>Place two balls in your dominant hand, 
                one in front of the other.</li>
            <li>Hold the third ball in your other hand.</li>
            <li>Let your arms dangle naturally and bring 
                your forearms parallel to the ground (as 
                though you were holding a tray).</li>
        </ol>
    </li>
    <li>Make the first toss:
        <ol style="list-style-type: lower-roman;">
            <li>Of the two balls in your dominant hand, 
                toss the front one toward your left hand 
                in a smooth arc.</li>
            <li>Make sure the ball doesn't spin too much.</li>
            <li>Make sure the ball goes no higher than 
                about eye level.</li>
        </ol>
    </li>
</ol>
```

Para ayudar al lector a diferenciar la lista anidada de la lista principal, el navegador web sangra un poco más los elementos anidados que los elementos de la lista principal. Sin embargo, esta forma predeterminada de manejar las listas numeradas anidadas es un poco confusa porque los elementos anidados utilizan el mismo esquema de numeración (1, 2, 3, etc.) que la lista numerada principal. Afortunadamente, como aprenderá en la siguiente sección, puede especificar un estilo de numeración diferente.

### 9.3.4 Cambiar el estilo de numeración

De forma predeterminada, los navegadores web muestran una lista numerada con números decimales (1, 2, 3, etc.). Sin embargo, existen varios estilos de numeración diferentes que puedes usar, como los números romanos. A continuación, se incluye una instrucción genérica que le pide a ChatGPT que use un estilo de numeración diferente:

```text
Generate the HTML code for a numbered list with the items below. Use style as the numbering style.
- Item 1
- Item 2
- etc.
```

```text
Genere el código HTML para una lista numerada con los elementos que se muestran a continuación. Utilice estilo como estilo de numeración.
- Artículo 1
- Artículo 2
- etc.
```

En su instrucción, reemplace `style` con uno de los siguientes:

* La frase `decimal leading zero` para utilizar números decimales rellenados con ceros iniciales, según sea necesario (01, 02, 03, etc.)
* La frase `upper roman` para utilizar números romanos en mayúsculas (I, II, III, etc.)
* La frase `lower roman` para utilizar números romanos en minúscula (i, ii, iii, etc.)
* La frase `upper alpha` para utilizar letras mayúsculas (A, B, C, etc.)
* La frase `lower alpha` para utilizar letras minúsculas (a, b, c, etc.)

A continuación se muestra una versión revisada de la instrucción ChatGPT de la sección anterior, que solicita números romanos en minúscula en las listas numeradas anidadas:

```text
Generate the HTML code for a numbered list with items below. Use lower roman as the numbering style for the nested numbered lists.
-Get into the starting position:
 -Place two balls in your dominant hand, one in front of the other.
 -Hold the third ball in your other hand.
 -Let your arms dangle naturally and bring your forearms parallel to the ground (as though you were holding a tray).
-Make the first toss:
 -Of the two balls in your dominant hand, toss the front one toward your left hand in a smooth arc.
 -Make sure the ball doesn't spin too much.
 -Make sure the ball goes no higher than about eye level.
```

```text
Genere el código HTML para una lista numerada con los elementos que se muestran a continuación. Utilice minúsculas romanas como estilo de numeración para las listas numeradas anidadas.
-Ponte en la posición inicial:
 -Coloca dos bolas en tu mano dominante, una delante de la otra.
 -Sujeta la tercera pelota con la otra mano.
 -Deja que tus brazos cuelguen naturalmente y lleva tus antebrazos paralelos al suelo (como si estuvieras sosteniendo una bandeja).
-Realizar el primer lanzamiento:
 -De las dos bolas que tienes en tu mano dominante, lanza la delantera hacia tu mano izquierda formando un arco suave.
 -Asegúrate de que la pelota no gire demasiado.
 -Asegúrese de que la pelota no suba más allá del nivel de los ojos.
```

La Figura 9.11 muestra la lista numerada actualizada con las listas numeradas anidadas utilizando números romanos en minúscula.

![image](https://github.com/user-attachments/assets/8975a58f-6bdd-4261-a0eb-1ac26420338f)

**Figura 9.11 Las listas numeradas anidadas ahora utilizan números romanos en minúscula.**

En este punto, ya sabes todo lo que se necesita para que ChatGPT cree una página de recetas. La siguiente sección te guiará a través del proceso.

## 9.4 Elaboración del mensaje para la página de recetas

El proyecto de este capítulo es una página web que ofrece al lector una receta que utiliza varias listas:

* Dos listas con viñetas para dos conjuntos de ingredientes
* Una lista numerada (con una lista numerada anidada) para las instrucciones

En este punto, ya deberías tener un título para el sitio, un eslogan y un título para la página, que en este caso será el nombre de la receta. Será útil que sepas qué tipografías de Google Fonts quieres para el texto de la página y qué colores quieres usar. Consulta el capítulo 3 para aprender a solicitarle a ChatGPT títulos, fuentes y colores sugeridos.

Para iniciar su solicitud, dígale a ChatGPT que desea construir una página web y que desea que genere el código por usted:

```text
I want to build a web page for a recipe. I don't know how to code, so I need you to provide the code for me.
  
First, write the HTML code for a web page that includes the following:
```

```text
Quiero crear una página web para una receta. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
```

Ahora describa el contenido de la página, incluyendo lo siguiente (consulte la figura 9.12):

* Un header que incluye su logotipo, título del sitio y eslogan.
* Un elemento main que comienza con el título de la página y es seguido por un texto introductorio.
* Una o más listas con viñetas - bulleted lists que detallan los ingredientes de la receta.
* Una o más listas numeradas - numbered lists que guían al lector a través de los pasos de la receta.
* Un footer que incluye un aviso de derechos de autor.

![image](https://github.com/user-attachments/assets/48055ae2-1697-4a00-adcc-e9dbd783edd2)
![image](https://github.com/user-attachments/assets/ecbdbaf9-22f0-4bca-841c-86da3df1a433)

**Figura 9.12 Los elementos de la página de recetas**

A continuación, solicite a ChatGPT que genere el CSS:

En segundo lugar, en un archivo separado, escriba el código CSS para lo siguiente:
A continuación, especifique el formato de la página, incluido lo siguiente:

El color de fondo de la página y el color del texto.

Los tamaños de fuente que desea utilizar para el título del sitio, el eslogan, el título de la página y el texto de la página.

Las fuentes a utilizar para los encabezados y el texto de la página normal.

Un ancho máximo para la página. Esto evita que las líneas de texto sean demasiado largas. Una longitud máxima de 800 px funciona para esta página.

A continuación se muestra un ejemplo de solicitud para mi propia página de recetas:

```text
Quiero crear una página web para una receta. No sé programar, así que necesito que me proporciones el código.
  
Primero, escriba el código HTML para una página web que incluya lo siguiente:
 * Un elemento de encabezado que incluye una imagen llamada super-baker.png, el título "El superpanadero" y el eslogan "La guía definitiva para hornear con superpoderes. Aprenda a preparar delicias deliciosas que aumentarán su energía, fuerza y ​​velocidad".
 * Una sección principal con el título "Barritas de frutos secos súper energéticas".
 * Un párrafo con el texto "¿Buscas un aporte de energía, ya sea a primera hora de la mañana o durante la calma de media tarde? No busques más que estas sabrosas y nutritivas barritas de frutos secos, que elevan el nivel de energía al 11. Repletas de frutos secos y frutas deshidratadas deliciosas que te llevarán hasta la cena, todo ello combinado con un toque de miel y sirope de arce que te dará energía ahora, estas barritas podrían ser el refrigerio perfecto para los superhéroes".
  * Agregue el encabezado de tercer nivel “Ingredientes secos” seguido de una lista con viñetas con los siguientes elementos:
    -200g de avena en hojuelas
    -100g de cacahuetes
    -100g de almendras
    -50g de semillas de calabaza
    -50g de semillas de sésamo
    -100g de dátiles u otros frutos secos
  * Agregue el encabezado de tercer nivel “Ingredientes húmedos” seguido de una lista con viñetas con los siguientes elementos:
    -120g de miel
    -80g de jarabe de arce
    -1 cucharadita de extracto de vainilla
    -¼ cucharadita de sal marina
  * Añadir el encabezado de tercer nivel “Preparación” seguido de una lista numerada con los siguientes elementos:
    -Precaliente el horno a 350°F. Coloque una rejilla en el estante inferior y otra rejilla en el medio.
    -Cubre dos bandejas para hornear con papel pergamino.
    -Distribuye las nueces y las semillas de manera uniforme en una bandeja para hornear.
    -Extiende la avena arrollada de manera uniforme en la otra bandeja para hornear.
    -Coloque las nueces y las semillas en la rejilla inferior y la avena en la rejilla del medio.
    -Hornear durante 8 minutos, luego retirar las nueces y semillas; continuar horneando la avena durante otros 7 minutos.
    -Deja que la avena, las nueces y las semillas se enfríen. (No tires las hojas de papel pergamino).
    -Picar las nueces enfriadas.
    -Picar los dátiles.
    -Combine todos los ingredientes secos en un tazón grande.
    -Prepara un molde de 8x10 o 7x11:
     -Cubre el molde con una de las hojas de papel pergamino del molde para hornear.
     -Cubre el papel pergamino con aceite (como aceite de girasol).
     -Unte con aceite un lado de la otra hoja de papel pergamino.
    -Añade los ingredientes húmedos a una cacerola pequeña.
    -Cocine los ingredientes húmedos en la estufa, revolviendo constantemente, hasta que un termómetro de lectura rápida insertado en el líquido marque 260 °F.
    -Añadir el líquido cocido a los ingredientes secos y mezclar bien.
    -Añadir la mezcla al molde preparado.
    -Coloque el lado engrasado de la segunda hoja de papel pergamino hacia abajo sobre la mezcla y use una cuchara y/o un machacador de papas para presionar la mezcla en su lugar.
    -Dejar enfriar la mezcla en el frigorífico durante 30-60 minutos.
    -Retirar del refrigerador y dejar reposar durante 30 a 60 minutos. (La mezcla debe estar lo suficientemente tibia para que no se rompa cuando intentes cortarla).
    -Cortar en 24 trozos.
  * Un elemento de pie de página que incluye el símbolo de Copyright, seguido del año actual, seguido de "The Super Baker".
 * En la sección del encabezado de la página, incluya la etiqueta <meta charset="utf-8">.
 * En la sección del encabezado de la página, incluya la etiqueta <meta name="viewport" content="width=device-width, initial-scale=1">.
  
En segundo lugar, en un archivo separado escriba el código CSS para lo siguiente:
 * La página tiene un color de fondo azul, un margen de 24 px y una altura de línea de 1,5.
 * El encabezado tiene texto de color rojo oscuro y relleno de 12 px.
 * Hacer que la imagen del encabezado tenga un ancho máximo de 250 px y flote hacia la izquierda.
 * El título es de 48 px, centrado y sin margen inferior.
 * El lema mide 26 px, está en cursiva, centrado y sin margen superior.
 *La sección principal tiene un margen superior de 75px.
 * El tamaño de fuente del encabezado de la sección principal es 30px.
 *El tamaño de fuente de la sección principal es 20px.
 * Para los títulos de las páginas, utilice la fuente Merriweather Sans de Google Fonts. Para el texto de las páginas, utilice la fuente Merriweather de Google Fonts.
 * Para la lista numerada anidada, utilice números romanos minúsculos.
 * El pie de página tiene un relleno de 5 px alrededor, un margen superior de 50 px y un borde superior de color rojo oscuro.
 * Dale a la página un ancho máximo de 800px y centra el elemento del cuerpo dentro de la ventana del navegador.
```

ChatGPT primero genera el código HTML, que puedes copiar y pegar y guardar en un archivo llamado index.html. En ese código, deberías ver una línea cerca de la parte superior similar a la siguiente:

```html
```

Este código le indica al navegador web que busque el código CSS en un archivo llamado styles.css, por lo que tu próxima tarea es copiar el código CSS generado, pegarlo y guardarlo en un archivo llamado styles.css (o cualquier nombre que veas en la <link>etiqueta). Asegúrate de guardar styles.css en la misma carpeta que tu archivo index.html. También debes copiar el archivo de imagen de encabezado en la misma carpeta. Consulta el apéndice A para obtener más información sobre cómo trabajar con archivos de páginas web.

Utilicé la aplicación ChatGPT de OpenAI para enviar mi mensaje a GPT-4. El código generado generó la página que se muestra en la Figura 9.13.



**Figura 9.13 Mi página de recetas**

Si te gusta la página que creó ChatGPT, puedes saltarte el resto de este capítulo e implementar el código en la web (consulta el apéndice B para conocer los detalles de implementación). Sin embargo, si quieres entender el código de la página web generada, sigue leyendo para verlo más de cerca.

## 9.5 Examinar el código de la página de recetas

Una de las premisas principales de este libro es que ChatGPT es lo suficientemente bueno para publicar código de páginas web como para que incluso las personas que no quieren saber mucho sobre desarrollo web puedan publicar páginas en la web confiando en que ChatGPT hará la parte del código del trabajo. Dicho esto, no hay ninguna regla que prohíba intentar comprender lo que hace el código generado por ChatGPT. Con ese fin, las dos secciones siguientes dan un vistazo detrás de escena para examinar el código de la página de recetas que resultó de mi solicitud de la sección anterior (esa página se muestra en la figura 9.13).

**Nota**: El código HTML y CSS generado para mi página de recetas está disponible en el sitio web de este libro ( www.manning.com/books/build-a-website-with-chatgpt ) y en el repositorio de GitHub del libro: https://github.com/paulmcfe/websites-with-chatgpt .

Las anotaciones de código que siguen deberían ayudarle a comprender lo que sucede bajo el capó y a modificar o personalizar su propio código.

### 9.5.1 Examinar el HTML

Aquí está el código HTML generado por ChatGPT para mi página de recetas:

```html
```

① Ayuda a que la página se muestre correctamente en dispositivos móviles

② Carga las fuentes Merriweather y Merriweather Sans desde Google Fonts

③ Le dice al navegador web dónde encontrar el código CSS

④ Logotipo del sitio

⑤ Título del sitio

⑥ Lema del sitio

⑦ Encabezado de página

⑧ Título de la receta

⑨ Introducción de la receta

⑩ Lista con viñetas de los ingredientes secos

⑪ Lista con viñetas de los ingredientes húmedos

⑫ Lista numerada para la preparación de recetas

⑬ Lista numerada anidada

⑭ Pie de página

Tenga en cuenta que el código HTML incluye la siguiente línea:

```html
```

Esta etiqueta le dice al navegador web dónde encontrar el código CSS, que describo en la siguiente sección.

### 9.5.2 Examinar el CSS

Aquí está el código CSS generado por ChatGPT para mi página de recetas:

```css
```

① Establece el color de fondo de la página, el margen, la altura de la línea y la fuente.

② Establece el ancho máximo de página en 800 px

③ Centra la página

④ Establece el color, el relleno y la alineación del texto del encabezado

⑤ Establece un ancho máximo para el logotipo y lo desplaza hacia la izquierda.

⑥ Establece el tamaño de fuente del título de la página, el margen inferior y la fuente

⑦ Diseña el tamaño de fuente del eslogan, el margen superior y la cursiva.

⑧ Agrega un margen en la parte superior del elemento principal y establece el tamaño de fuente.

⑨ Establece el tamaño de fuente y la fuente del título de la receta.

⑩ Aplica estilo a la lista numerada anidada para utilizar números romanos en minúscula

⑪ Aplica estilo al relleno del pie de página, al margen superior y al borde superior

Si lo desea, puede utilizar estas anotaciones para ayudar a personalizar el código de su página web, como describo en la siguiente sección.

## 9.6 Personalización de la página de recetas

Si realmente no te gusta la página que ChatGPT creó para ti, intenta revisar tu mensaje y enviarlo en una nueva sesión de chat. Si la página se parece a lo que buscabas, considera modificar el código tú mismo.

Comenzaré con algunas sugerencias para modificar el HTML:

Es seguro editar cualquier texto de la página, incluido el título, el eslogan, los encabezados o el texto introductorio o cualquiera de los elementos de la lista numerada o con viñetas. Solo asegúrese de no editar o eliminar accidentalmente las etiquetas HTML a cada lado del texto (como las etiquetas <li>y </li>que rodean un elemento de la lista numerada o con viñetas).

Siéntete libre de agregar uno o más párrafos introductorios. Para cada nuevo párrafo, sigue este procedimiento:

   a) En su editor de texto, coloque el cursor inmediatamente después de la </p>etiqueta que finaliza el párrafo introductorio existente.

   b) Presione Enter o Retorno para iniciar una nueva línea.

   c) Escriba una <p>etiqueta y luego presione Enter o Return. La mayoría de los editores de texto insertan una </p>etiqueta automáticamente.

   d) Escribe el texto de tu párrafo.

   e) Si su editor de texto aún no lo hizo, escriba una </p>etiqueta para finalizar su elemento de párrafo.

Si estás creando un sitio sobre recetas (o algo similar), necesitarás un elemento de navegación para que los visitantes puedan encontrar fácilmente tus otras páginas. Consulta el capítulo 6 para aprender a solicitarle a ChatGPT enlaces y una barra de navegación.

En la sección de pie de página del código HTML, puedes agregar enlaces a tus cuentas de redes sociales, como describo en el capítulo 4.

Aquí hay algunas ideas de personalización para el código CSS:

Si prefiere otro esquema de numeración para la lista numerada anidada, cambie el valor de la propiedad oldel elemento list-style-typea una palabra clave diferente, como lower-alpha.

Para un color de fondo diferente, reemplace el valor de la propiedad bodydel elemento background-colorcon otra palabra clave de color.

Para obtener un color de texto de encabezado diferente, reemplace el valor de la propiedad headerdel elemento colorcon otra palabra clave de color.

Si desea que su página tenga un ancho máximo diferente, cambie el max-widthvalor a algo distinto de 800px.

Si prefiere tener el logotipo del encabezado a la derecha, en el header imgelemento, cambie el floatvalor a right.

Para cualquier valor de tamaño de fuente, puede cambiar el número para aumentar o disminuir el tamaño de la fuente. Solo asegúrese de dejar la pxunidad en su lugar.

Para cualquier valor de margen o relleno, puede cambiar el número para aumentar o disminuir el relleno o los márgenes. En cada caso, asegúrese de dejar la pxunidad en su lugar.

Para que el código de tu página sea más accesible, considera convertir todas las medidas en px a medidas en rem. 1 rem equivale de manera predeterminada a 16 px, por lo que 20 px son 1,25 rem, 24 px son 1,5 rem, 32 px son 2 rem, 48 px son 3 rem, y así sucesivamente. La unidad rem es más accesible porque mide los tamaños de fuente en relación con el tamaño de fuente predeterminado que el usuario del navegador ha definido en la configuración de su navegador.

## Resumen

* Una lista con viñetas es una colección de elementos HTML que presentan múltiples elementos como una lista vertical, donde cada elemento está ligeramente sangrado desde el margen izquierdo y precedido por un pequeño círculo negro llamado viñeta.

* Utilice una lista con viñetas cuando desee presentar varios elementos pero el orden de esos elementos no es un componente esencial de la lista.

* Una lista numerada es una colección de elementos HTML que presentan múltiples elementos como una lista vertical, donde cada elemento está sangrado ligeramente desde el margen izquierdo y precedido (generalmente) por un número.

* Utilice una lista numerada cuando desee presentar varios elementos y el orden de esos elementos es un componente esencial de la lista.

* Se dice que una lista numerada o con viñetas que se encuentra dentro de otra lista numerada o con viñetas está anidada dentro de esa lista.

* Para obtener mejores resultados, el mensaje de su página debe ser lo más específico posible, incluidos colores, tamaños de fuente y niveles de encabezado.

* Guarde el HTML generado en el archivo index.html y el CSS generado en el nombre de archivo sugerido por ChatGPT en el código HTML, generalmente styles.css.
