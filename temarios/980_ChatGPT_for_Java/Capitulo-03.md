# 3. ¡Uso de IA en la empresa! Creación de un resumen de texto para mensajes de Slack

Bruce Hopkins 1  
(1)
Beaverton, Oregón, Estados Unidos
https://doi.org/10.1007/979-8-8688-0116-7_3
<hr>
 
En el mundo corporativo actual, es muy común que las empresas tengan una instancia de Slack (o Microsoft Teams) para organizarse y la utilicen como un lugar central de comunicación para todos en la empresa. Ahora bien, si alguna vez has utilizado Slack, creo que sabes con qué facilidad un canal puede inundarse con un montón de mensajes porque ALGUNA cosa importante sucedió EN ALGÚN LUGAR de la empresa o del mundo.

Por supuesto, cuanto mayor sea la responsabilidad que tengas dentro de la empresa (es decir, gerente, líder de equipo, arquitecto, etc.), más canales se espera que utilices. En mi opinión, Slack es un arma de doble filo. Debes usarlo para hacer tu trabajo, pero como desarrollador, definitivamente no puedes asistir a una reunión diaria y decir: "Ayer, eh, pasé todo el día leyendo Slack. No hay obstáculos".

Además, si trabajas para una empresa con clientes en distintas zonas horarias (lo cual es bastante común hoy en día), es bastante desalentador abrir Slack por la mañana y ver un montón de mensajes que se publicaron mientras estabas lejos del teclado.

En este capítulo, aplicaremos la IA en la empresa para que Slack sea más útil. Aprovecharemos el código del capítulo anterior y crearemos un bot de Slack en Java que resumirá las conversaciones importantes en un canal de Slack. Utilizaremos las capacidades de ChatGPT para el resumen de texto y nos centraremos un poco más en Prompt Engineering .

Entonces, ¿qué es la ingeniería rápida?
En pocas palabras, Prompt Engineeringes el proceso de crear y refinar cuidadosamente las indicaciones y los parámetros de entrada para indicar y guiar el comportamiento de ChatGPT y otros modelos de IA. Básicamente, es el término que se usa en toda la industria para crear la entrada correcta para obtener el resultado que estás buscando.

Sin embargo, antes de continuar, hagamos un poco de limpieza y mejoremos nuestro ChatGPTClient.java del capítulo anterior.

Actualización de ChatGPTClient.java (y clases relacionadas) con el patrón Builder
Entonces, en el capítulo anterior, creamos ChatGPTClient.javacomo una aplicación básica para enviar nuestras indicaciones al punto final del chat. Fue un buen comienzo, pero definitivamente había margen de mejora.

Veamos primero el constructor del objeto Chat, que modela el objeto Chat JSON que se envía al punto final de chat como se ve en el Listado 3-1 .
