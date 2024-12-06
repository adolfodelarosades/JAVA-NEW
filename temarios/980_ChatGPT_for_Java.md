# ChatGPT for Java: A Hands-on Developer's Guide to ChatGPT and Open AI APIs

By Bruce Hopkins

![image](https://github.com/user-attachments/assets/a38ef840-00ce-4ed0-9f18-44066f080ac2)

* TIEMPO PARA COMPLETAR: 3h 35min
* NIVEL: Intermedio a avanzado
* HABILIDADES: GPT
* PUBLICADO POR: Apress
* FECHA DE PUBLICACIÓN: Febrero de 2024
* LONGITUD DE IMPRESIÓN: 243 páginas

¡Adopte el futuro del desarrollo de software! ChatGPT para Java  es el punto de partida perfecto para que los desarrolladores de Java aprendan a crear aplicaciones inteligentes utilizando ChatGPT y API de Open AI.

Este libro te muestra cómo usar ChatGPT de forma programática desde cero. Aprenderás los conceptos básicos de las API de ChatGPT y OpenAI, incluidos cómo autenticar, enviar mensajes, generar respuestas, realizar pruebas en Playground y manejar errores. Cada capítulo incluye ejercicios prácticos que demuestran diferentes funcionalidades de API y dan vida a tus conceptos. Aprenderás a habilitar la IA en tus propias aplicaciones utilizando modelos como GPT-4, GPT-3.5, Whisper, DALL-E y muchos más. 

Como resultado, los desarrolladores comprenderán que las herramientas de IA generativa no reemplazarán los trabajos de desarrollo de software. En cambio, aprovecharán ChatGPT como su programador de pares de IA de Java para aumentar la velocidad y la productividad. También aprenderán cómo ChatGPT puede proporcionar potentes capacidades de procesamiento del lenguaje natural (PLN) a sus aplicaciones Java para comprender varios formatos de texto no estructurado. Paso a paso, aplicarán los conceptos cubiertos para crear sus propios chatbots inteligentes que pueden procesar automáticamente mensajes de Slack o Discord. 

Con este libro, los desarrolladores de Java podrán llevar sus aplicaciones a nuevas alturas aprovechando el poder de la IA a medida que este apasionante campo continúa evolucionando y transformándose.



### Lo que aprenderás

* Autentíquese con las API ChatGPT y OpenAI y aprenda a diseñar y enviar mensajes
* Pon a prueba tus indicaciones en el Playground de ChatGPT
* Cómo utilizar múltiples modelos de inteligencia artificial 
* Aproveche el poder de la temperatura, top_p y otros parámetros a los que SÓLO pueden acceder los desarrolladores para crear respuestas más exclusivas y atractivas desde ChatGPT
* Crea bots inteligentes para servidores de Slack o Discord
* Incorpore contexto a las indicaciones para obtener mejores respuestas y aplique funciones avanzadas de las API.
* Explorar futuras direcciones para ChatGPT y OpenAI 

#### Para quién es este libro

Desarrolladores Java principiantes e intermedios que tengan conocimientos básicos de los conceptos de programación Java y estén interesados ​​en aprender a agregar inteligencia a sus aplicaciones mediante el uso de ChatGPT de manera programática. No se requiere experiencia previa con ChatGPT ni con las API de OpenAI.


## Table of Contents

* [Introduction](https://github.com/adolfodelarosades/JAVA-NEW/blob/main/temarios/980_ChatGPT_for_Java/Introduction.md)
  
### [Chapter 1:​ Introducing ChatGPT for Java Developers](https://github.com/adolfodelarosades/JAVA-NEW/blob/main/temarios/980_ChatGPT_for_Java/Capitulo-01.md)

* Who Is This Book For?​
* Chapter Overview
* Download the Code Now!
* So, What Exactly Is ChatGPT and Why Do I Need to Use the OpenAI APIs?​
* Regex vs.​ ChatGPT:​ Fight!
* Analysis Question #1:​ Who Didn’t Get Any Ice Cream and Why?​
* Analysis Question #2:​ Which Kid Was Probably Left Sad?​
* Let’s Unlearn Some Words in Order to Learn More About the ChatGPT API
* Models.​ Models?​ Models!!!
* When We Talk About Tokens, Think About the StringTokenizer and Not Access Tokens
* Temperature Is All About Creativity
* Getting Started with the OpenAI Playground
* 1.​ System
* 2.​ User
* 3.​ Assistant (Optional)
* 4.​ Add Message (Optional)
* 5.​ View Code (Optional)
* 6.​ Model (Optional)
* 7.​ Temperature (Optional)
* 8.​ Maximum Length (Optional)
* Try It Now! Experimenting with the “System” Role
* Conclusion

### [Chapter 2:​ Using ChatGPT As Your Java Pair-Programmer](https://github.com/adolfodelarosades/JAVA-NEW/blob/main/temarios/980_ChatGPT_for_Java/Capitulo-02.md)

* Creating Your First Java ChatGPT App:​ ListModels.​java
* List Models Endpoint
* Creating the Request
* Handling the JSON Response
* Model (JSON)
* Chat Endpoint
* Creating the Request
* Chat (JSON)
* Handling the Response
* Chat Completion (JSON)
* Wait, How Many Tokens Are in My Prompt?​
* ChatGPT Token Counter
* Creating the Next Java App:​ ChatGPTClient.​java
* Conclusion

### Chapter 3:​ Using AI in the Enterprise! Creating a Text Summarizer for Slack Messages

* So, What Is Prompt Engineering?​
* Updating ChatGPTClient.​java (and Related Classes) with the Builder Pattern
* ChatGPT Is Here to Take Away Everyone’s Jobs (Not Really)
* Examining a Real World Problem:​ Customer Support for a Software Company
* Prompt Engineering 101:​ Text Summarization
* Prompt #1:​ “tl;dr”
* Prompt #2:​ “Explain This in 3 Sentences or Less”
* Prompt #3:​ “I’m a Manager.​ Explain to Me What Happened”
* Prompt #4:​ “Give Me Suggestions on Next Steps”
* Let’s Talk About Real Prompt Engineering
* Registering a Slack Bot App
* Specifying What Your Bot Can (and Can’t) Do By Setting the Scope
* Confirming Your Settings
* Viewing the OAuth and Permissions Page
* Installing Your Slack Bot App to Your Workspace
* Getting Your Slack Bot (Access) Token
* Inviting Your Bot to Your Channel
* Finding the Channel ID of Your Channel
* Using Your Slack Bot App to Automatically Grab Messages from a Channel
* Setting Up Your Dependencies
* Programmatically​ Reading Messages from Slack with ChannelReaderSla​ckBot.​java
* Exercises Left for the Reader
* Conclusion

### Chapter 4:​ Multimodal AI:​ Creating a Podcast Visualizer with Whisper and DALL·E 3

* Introducing the Whisper Model by OpenAI
* Features and Limitations of the Whisper Model
* Transcriptions Endpoint
* Creating the Request
* Request Body (Multipart Form Data)
* Creating a Utility App to Split Audio Files:​ AudioSplitter.​java
* Creating the Audio Transcriber:​ WhisperClient.​java
* Having a Little Fun and Trying Things Out with a Podcast
* Going Meta:​ Prompt Engineering GPT-4 to Write a Prompt for DALL·E
* Create Image Endpoint
* Creating the Request
* Create Image (JSON)
* Handling the Response
* Image (JSON)
* Creating the Image Generator:​ DALLEClient.​java
* DALL·E Prompt Engineering and Best Practices
* DALL·E Golden Rule #1:​ Get Familiar with the Types of Images that DALL·E Can Generate
* DALL·E Golden Rule #2:​ Be Descriptive with What You Want in the Foreground and Background
* Conclusion
* Exercises Left for the Reader

### Chapter 5:​ Creating an Automated Community Manager Bot with Discord and Java

* Choosing Discord as Your Community Platform
* Creating a More Advanced Bot Than Our Slack Bot
* Creating a More Advanced Bot Than Any Typical Discord Bot
* Understanding the Roles for the Bots
* Our Example Bank:​ Crook’s Bank
* First Things First:​ Create Your Own Discord Server
* Create the Q&​A Channel
* Registering a New Discord Bot App with Discord
* Specifying General Info for the Bot
* Specifying OAuth2 Parameters for the Bot
* Invite Your Bot to Your Server
* Getting the Discord ID Token for Your Bot and Setting the Gateway Intents
* Creating a Q&​A Bot App in Java to Answer Questions from a Channel
* Setting Up Your Dependencies
* Creating The First Discord Bot:​ TechSupportBotDu​mb.​java
* Loving the Lambda Expression to Simplify Code
* Handling Messages Sent to the Discord Server
* Success! Running Your First Discord Bot:​ TechSupportBotDu​mb.​java
* Streamlining the Process of Registering Our Next Discord Bot App with Discord
* Registering a New Discord Bot App with Discord
* Specifying General Info for the Bot
* Specifying OAuth2 Parameters for the Bot
* Invite Your Bot to Your Server
* Getting the Discord ID Token for Your Bot and Setting the Gateway Intents
* Creating the Next Discord Bot:​ ContentModerator​BotDumb.​java
* Handling Messages Sent to the Discord Server
* Success Again! Running Your Second Discord Bot:​ ContentModerator​BotDumb.​java
* Conclusion
* Exercises Left for the Reader

### Chapter 6:​ Adding Intelligence to Our Discord Bots, Part 1:​ Using the Chat Endpoint for Q&​A

* Making TechSupportBot.​java More Intelligent
* Important Changes to Note from the Previous Version of the Tech Support Bot
* Updates to the onMessageReceive​d() Method
* Analyzing ChatGPTClientFor​QAandModeration.​java
* Using JSONPath in Order to Extract Content Quickly in JSON Files
* Running Our Intelligent Q&​A Bot:​ TechSupportBot.​java
* We Have a Monumental Achievement… With One Slight Flaw
* Update the System Message to ChatGPT and Let’s Try Again
* Conclusion

### Chapter 7:​ Adding Intelligence to Our Discord Bots, Part 2:​ Using the Chat and Moderation Endpoints for Moderation

* Moderations Endpoint
* Creating the Request
* Create Moderation (JSON)
* Handling the JSON Response
* Moderation (JSON)
* Creating Our Client for the Moderations Endpoint:​ ModerationClient​.​java
* Making ContentModerator​Bot.​java More Intelligent
* Important Changes to Note from the Previous Version of the Content Moderator Bot
* Updates to the onMessageReceive​d( ) Method
* Running Our Intelligent Content Moderator Bot:​ ContentModerator​Bot.​java
* Conclusion
* Exercises Left for the Reader

#### Appendix 1:​ List of OpenAI Models
#### Index
