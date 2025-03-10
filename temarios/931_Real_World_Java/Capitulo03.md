# 3 Colaboración en toda la empresa con Git, Jira y Confluence

**¿QUÉ HAY EN ESTE CAPÍTULO?**

* Colaborando con Git
* Uso de Jira para la colaboración en procesos empresariales
* Trabajar con Confluence, el sistema de gestión del conocimiento empresarial

Cuando un equipo de desarrolladores está trabajando en una aplicación, la colaboración es absolutamente fundamental para que nadie se meta con el código de los demás. La situación se agrava cuando los equipos están distribuidos por todo el mundo, desde la India hasta los Estados Unidos, donde el desarrollo activo se lleva a cabo en un continente mientras los desarrolladores de otro continente duermen profundamente. ¿Cómo se avanza al unísono? ¿Cómo se da marcha atrás cuando surge la necesidad? Además, se deben publicar estándares y respetarlos. Sin una buena coordinación y colaboración, se perdería mucho tiempo entregando código y arreglando cosas.

Existen muchas herramientas populares que se utilizan en las empresas modernas para facilitar la colaboración. Para el control de versiones, es posible que encuentre empresas que utilicen **Git**, **Mercurial**, **SVN** o **ClearCase**. Para la gestión de requisitos, **Jira** se ha convertido en sinónimo de seguimiento de problemas, aunque **GitHub**, **Gitlab** y otros también ofrecen capacidades de seguimiento de problemas. Para compartir conocimientos, **Confluence** se ha vuelto muy popular, pero también hay equipos que utilizan **Twiki** o **Jive**, entre muchos otros.

En este capítulo, nos centramos en algunas de las herramientas más populares para compartir código, hacer un seguimiento de problemas y gestionar el conocimiento, a saber, **Git**, **Jira** y **Confluence**. Pero si su equipo utiliza otras soluciones, el conocimiento es fácilmente transferible.

<hr>

**DESCARGAS DE CÓDIGOS PARA ESTE CAPÍTULO**

El código fuente de este capítulo está disponible en la página del libro en www.wiley.com. Haga clic en el enlace Descargas. El código también se puede encontrar en https://github.com/realworldjava/Ch03-Collaboration. Consulte el archivo **`README.md`** en ese repositorio para obtener más detalles.

<hr>

## COLABORANDO CON GIT

Historia real: cuando yo (Victor) era un muchacho joven, estaba trabajando en una aplicación de interfaz de usuario de tres niveles en Java y me costaba mucho hacer que algunos códigos funcionaran. Era bastante nuevo en programación y, después de luchar con ella durante unos días, finalmente pude crear una versión funcional.

El código necesitaba algo de limpieza, así que pasé un día haciendo ajustes aquí y extrayendo métodos allá, hasta que finalmente se vio limpio.

Pero, para mi horror, cuando fui a ejecutarlo, descubrí que mi nuevo código estaba roto. Intenté deshacerlo, pero en aquellos tiempos, solo se podían deshacer unas pocas capas hacia atrás, y cuanto más deshacía y rehacía, peor se ponía. Intenté reproducir lo que había hecho, pero fue inútil: después de días de codificación, estaba roto sin posibilidad de reparación.

La historia tuvo un final feliz. Empecé desde cero y, después de unos días, tenía una versión bonita, brillante y funcional, mejor que la original. Pero rápidamente aprendí a las malas cómo usar el control de versiones. Y aquí va una reflexión: esto le puede pasar a cualquiera.

Los **Version control systems (VCSs) Sistemas de Control de Versiones** actuales son mucho más maduros que en aquel entonces. En el siglo XX, el control de versiones se realizaba en un servidor de middleware. Se invocaba un bloqueo en un archivo, se extraía, se trabajaba en él y, a continuación, se volvía a introducir y se liberaba el bloqueo.

El proceso era extremadamente lento. Había que esperar a que llegaran los archivos; luego, cuando se realizaba el check-in, había que esperar a que los archivos llegaran al servidor y a que este hiciera lo suyo para integrar los cambios y, finalmente, se liberara el bloqueo.

Si fuiste a almorzar o te fuiste temprano y olvidaste desbloquear, entonces tu equipo quedaría bloqueado durante el día porque tú mantuviste el candado.

Ése era el modelo operativo de los sistemas de control de versiones como **RCS**, **CVS** y, en cierta medida, el siempre popular **Subversion (SVN)**. Luego, cuando se acercaba el siglo XXI, **Linus Torvalds (el inventor de Linux) creó Git**, con un nuevo y revolucionario modelo operativo.

En cambio, ***Git es un sistema de control de versiones descentralizado. No hay bloqueos y muchas operaciones de control de versiones se realizan en el equipo local, por lo que es increíblemente rápido***.

### Introducción a los conceptos básicos de Git

Veamos un día en la vida de un desarrollador que usa Git. Supongamos que desea realizar un cambio en algunos archivos. Primero, ***clona*** el repositorio remoto, que coloca una copia de él, incluido todo el historial, en su computadora. A continuación, realiza el cambio deseado en el archivo.

Una vez que estés satisfecho con los cambios, puedes hacer un ***pull(actualizar)*** para actualizar localmente cualquier código que otros hayan modificado mientras tanto. Si un compañero de equipo ha realizado algún cambio, Git determinará si puede conciliar automáticamente o si necesitas hacer un ***merge*(fusionar)** manualmente los cambios. Por último, es hora de hacer un ***commit(confirmar)*** para confirmar los cambios. Haz un ***push(inserción)*** para que los cambios estén disponibles para tus compañeros de equipo.

### Aprendiendo conceptos clave

Git mantiene tres áreas clave en cada instalación:

* **Working area**: Donde viven y evolucionan sus archivos
* **Staging area**: Donde se preparan los archivos para ser ***committed***
* **Repository**: Donde se guardan los commits
  
Además, puedes acceder a repositorios de Git en otras máquinas remotas (siempre que tengas los permisos adecuados). De hecho, técnicamente cualquier instancia de Git puede actuar como un servidor remoto de Git, aunque en la mayoría de las empresas todos comparten un servidor remoto centralizado que usa **GitHub**, **GitLab**, **Bitbucket** o similares.

Para descargar los archivos de un proyecto remoto a su computadora local, debe ***clonar*** el repositorio del proyecto. Luego, todos los archivos se descargan y se incluyen automáticamente en su working area - área de trabajo, donde Git realiza un seguimiento de ellos.

Si estás creando un nuevo proyecto desde cero y quieres añadirlo a Git, debes inicializar el proyecto ejecutando **`git init`** en la raíz del directorio del proyecto. Luego, para cualquier archivo que quieras que Git rastree(track), debes ejecutar **`git add <file1> <file2>`** especificando el nombre de cada archivo (o un patrón de nombres de archivo con comodines **`*`**) o ejecutar **`git add .`** para añadir todo lo que se encuentre en ese directorio y debajo.

De manera similar, cuando cambias archivos, deseas ejecutar **`git add`** para preparar(to stage) los cambios. Puedes preparar(to stage) y confirmar(commit) en una sola operación usando **`git commit -am "some meaningful log message."`**.

Una vez que haya preparado los cambios y esté conforme con ellos, deberá guardarlos en su repositorio. El proceso para ello consiste en confirmarlos.

### Diferenciación de Commits

La palabra *commit* es tanto un verbo como un sustantivo. Como verbo, *commit* se refiere a la acción de mover los cambios a tu repositorio Git local. Como sustantivo, un *commit* se refiere a todos los archivos y la información de contexto incluidos en esa acción de commit. Se aplica un algoritmo amplio a los archivos, sus commits anteriores, el nombre de usuario del commiter, el log message y otra información para producir un *commit ID* hexadecimal único de 40 caracteres, también conocido como *commit hash*.

### Visualización del Git Status

El comando **`git status`** es una herramienta útil para visualizar el estado de sus archivos. Le mostrará una lista de archivos modificados, untracked(no rastreados) y staged files(almacenados), así como la current branch(rama actual) y una lista de comandos específicos que puede ejecutar para cambiar el estado.

Si hay archivos que no quieres que Git rastree(to track) en absoluto (como archivos de configuración IDE o archivos locales que nunca quieres confirmar(commit)), puedes agregar sus nombres (o directorios o un patrón de nombre) a un archivo llamado **`.gitignore`** en la raíz de tu working area(área de trabajo) (más sobre esto más adelante).

Git no realiza un seguimiento de los archivos ignorados, no se muestran en el estado y sus cambios no se incluyen al comprobar si hay modificaciones. Puedes cambiarlos y usarlos, pero en lo que respecta a Git, no existen.

### Branching

Todos los Git commits residen en una branch. Una *branch* es un pointer con nombre a un conjunto de commits; o, más precisamente, es un pointer a un particular *HEAD* commit, que incluye todos la s históricas de commits que produjeron ese commit. A medida que realiza más commits en esa branch, el branch pointer se mueve hacia adelante para apuntar al último commit.

Puedes crear una branch a partir de una rama seleccionada, trabajar en la nueva rama, luego comparar esa rama con la rama original para revisar los cambios y, finalmente, fusionar(merge) tu rama con la rama original. Tradicionalmente, Git asignaba una rama predeterminada llamada ***master***. Pero recientemente han estado haciendo la transición para usar el nombre ***main*** en lugar de ***master*** para promover la inclusión. Dependiendo de tu proveedor y versión de Git, verás uno u otro.

### Tagging

Los ***Tags*** son como branches, excepto que son estáticas. Mientras que un puntero de rama(branch pointer) se mueve continuamente al último commit, un tag pointer nunca se mueve y, por lo tanto, captura el estado de su base de código en un momento dado. Un tag es como un nombre legible para el commit hash.

<hr>

**TIP**: Si bien el commit hash al que hace referencia el tag pointer es inmutable, el nombre de tag en sí se puede eliminar y volver a crear.

<hr>

### Merging

***Merging(La fusión)*** se refiere a la actividad de integrar los cambios de una rama en otra rama. Este es un paso en un flujo de trabajo común en Git - comienzas con una rama existente, generalmente la rama común que todos usan, que puede tener cualquier nombre, pero tradicionalmente se llama ***develop***. Creas tu rama a partir de esa rama existente en una nueva rama con tu propio nombre, por ejemplo, ***feature-123***. Tú, y quizás otros miembros de tu equipo, trabajan en *feature-123*, ejecutas tus pruebas, todo pasa y estás listo para publicar el código. Debes fusionar *feature-123* en *develop* y luego enviarlo al servidor remoto.

<hr>

**TIP**: En las empresas, es habitual nombrar la feature branch(rama de funciones) utilizando el número de ticket de JIRA para facilitar el seguimiento. Veremos un ejemplo de esto en la sección “Uso de Jira para la colaboración en procesos empresariales”, más adelante en este capítulo.

<hr>

### Reading Git Logs

Git te brinda la posibilidad de ver un ***log(registro)*** de tu historial de commits en niveles de detalle configurables. **`git log`** muestra una lista bastante detallada de todo tu historial de commits.

A continuación se muestra la ejecución de un **`git log`** reciente:

```sh
commit f162588e53d536dd0738968e952adf7e86740a8f (refactoring1)
Author: vgrazi <vgrazi@gmail.com>
Date:   Mon Feb 19 19:54:05 2024 -0500
 
    added a display
```

Aquí se muestra commit ID, branch, author, commit date, y commit message.

<hr>

**TIP**: Si ve dos puntos al final del log, eso indica un salto de página; presione la barra espaciadora para ver más opciones o escriba `q` para salir y volver a la línea de comandos.

<hr>

### Staging sus cambios

Como se mencionó, Git mantiene un área de almacenamiento local(staging area); todos los archivos que desee rastrear(to track) deben agregarse al área de almacenamiento(staging area) mediante el comando **`git add`**. Puede almacenar archivos específicos mediante lo siguiente:

```java
git add <file1> <file2> <file3> <etc>
```

o puedes organizar(stage) cada archivo modificado usando un punto para indicarlos todos.

```java
git add .
```

La operación **`git add`** prepara(stages) los archivos nuevos, modificados y eliminados. Cuando se utiliza **`git add .`**, la preparación(staging) es recursiva y recoge los archivos modificados del directorio actual y de los directorios inferiores. ¿Qué sucede con los archivos movidos? Git hará todo lo posible por reconocer los archivos y directorios movidos y conservar su historial de versiones.

Para anular la etapa de preparación(unstage) de un archivo que ya se agregó, utilice lo siguiente:

```java
git rm –cached <file>
```

que es esencialmente el inverso de **`add`**.

Después de ejecutar **`git add`**, el siguiente paso generalmente será confirmar el área de ensayo en el repositorio local(commit the staging area to the local repo). Deberá agregar un mensaje de confirmación usando el interruptor **`-m`** (por “message”).

```java
git commit -m "Some meaningful commit message"
```

Cuando estés conforme con los cambios, *agrégalos-add* al staging area(área de ensayo), nuevamente usando el comando **`git add`**. Luego, *envías-commit* el staging area - área de ensayo (con todos los archivos agregados) al repositorio Git (que se encuentra en tu computadora local) usando el comando **`git commit -m "Some meaningful commit message"`** y, finalmente, envías tu repositorio a un servidor remoto usando el comando **`git push`**.

Puedes agregar y confirmar(add and commit) en un solo comando **`git commit -am`**. Por ejemplo:

```java
git commit -am "Some meaningful commit message"
```

En resumen, Git es un sistema de colaboración de código fundamental que se utiliza en la mayoría de los talleres de desarrollo y es conveniente familiarizarse con él desde el principio.

Practiquemos un poco, pero primero, instale Git y luego siga las instrucciones.

### Instalación de Git

Para instalar Git, dirígete a https://git-scm.com/downloads. Encontrarás instrucciones de instalación para Windows, macOS y Linux.

Git para Windows generalmente funciona desde el shell de comandos normal de Windows, pero muchos desarrolladores prefieren usar Git Bash, que se instala con Git para Windows. Git Bash es una implementación para Windows del popular shell bash de Unix/Linux , que reconoce todos los comandos de Linux, como **`grep`**, **`ls`**, y **`ps`**, y es ideal para desarrolladores con experiencia en Unix/Linux.

Una vez instalado Git, configure su correo electrónico y nombre.

```sh
git config --global user.name "Your Name"
git config --global user.email you@example.com
```

El nombre se utilizará para anotar todas tus commits. El proveedor de Git puede utilizar la dirección de correo electrónico para comunicarse contigo.

Este libro utiliza GitHub, por lo que si aún no tiene una cuenta configurada, le recomendamos que visite github.com y cree una cuenta gratuita.

### Comprender el flujo de trabajo de Git con ejemplos

Vamos a sumergirnos directamente en el proceso siguiendo la secuencia de comandos típica. Le recomendamos que siga escribiendo todos los comandos; la experiencia le ayudará a adquirir una comprensión visceral del flujo de trabajo de Git.

En primer lugar, bifurca(fork) el repositorio del libro. La bifurcación(Forking) es el proceso de crear una copia personal de un repositorio existente. En teoría, podrías usar el repositorio original sin bifurcarlo(forking); sin embargo, el repositorio es de solo lectura, por lo que no podrás enviar cambios. Una copia bifurcada(forked copy) se convierte en tuya para que puedas hacer lo que quieras.

Dirígete al repositorio del proyecto en https://github.com/realworldjava/Ch03-Collaboration. Como se muestra en la Figura 3.1, bifurca(fork) el repositorio del proyecto. Esto crea un nuevo repositorio con tu ID de usuario, como **`https://github.com/<your git id>/Ch03-Collaboration`**.

Haga clic en el botón Fork. En la pantalla fork, conserve todos los valores predeterminados y haga clic en el botón Create Fork, como se muestra en la Figura 3.2 .

<img width="907" alt="image" src="https://github.com/user-attachments/assets/4cba38bb-2be3-42aa-b883-2f36c11644ee" />

**FIGURA 3.1: Bifurcación de un proyecto de GitHub**

<img width="910" alt="image" src="https://github.com/user-attachments/assets/fe2c92d0-8101-479e-a3e5-9b7f7e64337f" />

**FIGURA 3.2: Completando la bifurcación**

Ahora clone el fork de nuestro repositorio de proyectos. La clonación es la operación de llevar el proyecto Git a tu máquina de desarrollo para verlo y editarlo.

Para clonar el repositorio, abra un shell de comandos, **`cd`** en un directorio vacío y clone su fork de nuestro proyecto de libro usando lo siguiente:

```sh
git clone https://github.com/<your git id>/Ch03-Collaboration
```

Esto clonará e inicializará el repositorio en el directorio actual, lo que te permitirá trabajar en él. (Git clone moverá todos los archivos directamente al directorio actual, por lo que siempre querrás comenzar desde un directorio vacío). La operación de clonación solo traerá la rama predeterminada y descargará la lista de ramas remotas. Si quieres extraer otras ramas, debes extraerlas explícitamente.

<hr>

**CLONACIÓN VÍA SSH**

El Uniform Resource Indicator (URI) que usamos en la operación de clonación de Git anterior era simplemente la URL HTTPS de nuestro repositorio de GitHub. Esta es una práctica de clonación común para los repositorios públicos de GitHub y puedes seguir usando ese enfoque para este libro. Sin embargo, en las empresas, a veces te pedirán que uses un URI SSH seguro, lo que significa que debes generar y agregar claves SSH a tu repositorio. Eso no es tan aterrador como parece.

Desde un shell de Linux o macOS o desde Git Bash, genere las claves usando esto:

**`ssh-keygen -t rsa -b 4096 -f ~/.ssh/id_rsa -C "github keys"`**

O desde un shell estándar de Windows, use esto:

**`ssh-keygen -t rsa -b 4096 -f %USERPROFILE%\.ssh\id_rsa1 -C "github keys"`**

Puedes usar la clave generada con todos tus repositorios de GitHub. Deberás enviar la clave a GitHub. A continuación, te indicamos cómo hacerlo:

1. Copie el contenido del archivo **`~/.ssh/id_rsa`** que acaba de generar al portapapeles.
2. Haz clic en tu foto de perfil en la esquina superior derecha y elige la opción Settings.
3. En la navegación izquierda, seleccione la entrada para las claves SSH y GPG, como se muestra en la Figura 3.3 .
4. Seleccione SSH Keys y New SSH Key.

<img width="832" alt="image" src="https://github.com/user-attachments/assets/ae9dac87-7694-42a6-8aac-a88b12b71e0f" />

**FIGURA 3.3: Cómo agregar claves SSH a su repositorio de GitHub**

Pegue el contenido del archivo **`id_rsa`** que copió en el paso 1 y haga clic en Add SSH Key. En unos segundos, debería recibir un correo electrónico que le anunciará que su clave se ha configurado, como se muestra en la Figura 3.4 .

<img width="834" alt="image" src="https://github.com/user-attachments/assets/a344bf34-7678-46c3-87b0-d568187c977b" />

**FIGURA 3.4: Agregar nuevas claves SSH**

A continuación veremos un ejemplo de los comandos **`checkout`** y **`switch`**.

1. Por favor **`cd`** al directorio **`main/java/com/wiley/realworldjava/gitplay`**.
2. Hay un archivo allí (ver Listado 3.1 ).

**LISTADO 3.1: ARCHIVO ORIGINAL**

```java
1:  package com.wiley.realworldjava.gitplay;
2:
3:  public class GitDemo {
4:     private String description;
5:
6:     public GitDemo(String description) {
7:        this.description = description;
8:     }
9:
10:    public void displayDescription() {
11:       System.out.println("Description: " + description);
12:    }
  13:
14:    public static void main(String[] args) {
15:       GitDemo demo = new GitDemo("Hello, Git!");
16:
17:       // Display the initial description
18:       demo.displayDescription();
19:    }
20: }
```

Para facilitar la edición y la compilación, cree un nuevo proyecto en su IDE desde el control de versiones. Consulte el Capítulo 2 , “Conozca su IDE: el secreto del éxito”, para aprender a crear un proyecto desde el control de versiones.

El comando **`git status`** te tomará de la mano, mostrando tu estado actual y mostrándote las opciones disponibles sobre qué hacer a continuación.

```sh
git status
```

Para mi entorno, esto muestra lo siguiente:

```sh
Your branch is up to date with 'origin/main'.
 
Untracked files:
  (use "git add <file>…" to include in what will be committed)
        .idea/
```

Ahora no desea realizar el check-in en su directorio **`.idea`** (después de todo, no desea dictar su estado dinámico **`.idea`** a otros o incluso a su yo futuro), y ciertamente no desea realizar el check-in en su directorio de salida de compilación; Git es para código fuente, no para salida compilada.

¿No sería fantástico si pudieras indicarle a Git que ignore por completo esos archivos? Afortunadamente, Git ofrece una función para ignorar archivos y directorios seleccionados. Para ello, crea un archivo con el nombre **`.gitignore`** en la raíz del proyecto e incluye los nombres de los archivos y directorios que deseas ignorar. Puedes incluir el nombre de archivo exacto (**`temp.txt`**), un comodín (**`temp*.*`**) o directorios. Puedes ignorar directorios enteros especificando los nombres de los directorios. Por ejemplo:

* **`/logs/`** ignorará el directorio **`logs`** en la raíz.
* **`logs/`** ignorará cualquier directorio nombrado **`logs`** en cualquier nivel.
* **`logs`** Sin un separador de ruta coincidirá con el directorio **`logs/`** y cualquier archivo llamado **`logs`**.

Si desea que la recursión sea explícita, puede decir **`**/logs`**, lo que ignorará todo lo que se encuentre en cualquier directorio llamado **`logs`**. Puede agregar comentarios al archivo **`.gitignore`** comenzando con **`#`**. Las líneas en blanco se ignoran.

No puedes ignorar los archivos que ya están rastreados(tracked). Para dejar de rastrear un archivo rastreado(untrack a tracked file), puedes hacer lo siguiente:

```sh
git rm --cached -r com/wiley/realworldjava/gitplay/
```

En nuestro caso utilizaremos el siguiente archivo **`.gitignore`**:

```sh
# Ignore the entire .idea directory
.idea
 
# Ignore the output directory. 
out/
```

Recuerde preparar(stage) y confirmar(commit) esto para que Git lo rastree(track it).

```sh
git add .gitignore
git commit -m "Added .gitignore"
```

El comando **`add`** sirve para preparar(to stage) el archivo. El comando **`commit`** sirve para registrarlo(to check it in). La bandera(flag) **`-m`** especifica un mensaje de registro(log) que se asociará con ese commit.

***Como todos los buenos desarrolladores, no queremos enviar nuestro código hasta que esté terminado y probado***. Sin embargo, queremos hacer un seguimiento de nuestro código a medida que evoluciona. ¿Cómo podemos enviar nuestros cambios al repositorio remoto sin afectar a otros desarrolladores? La respuesta es crear una rama y realizar los cambios en ella. Luego, puede realizar cambios en esa rama, o incluso colaborar con otros en esa rama, sin afectar a la rama principal.

Llamemos a esta rama **`refactoring1`**. El comando para ello se muestra aquí:

```sh
git branch refactoring1
```

Esto creará una nueva rama llamada **`refactoring1`** a partir del commit actual. Si desea eliminar una rama, puede hacer lo siguiente (pero por ahora, no la elimine):

```sh
git branch -d refactoring1
```

Luego, para verificar la rama(check out the branch), haga lo siguiente:

```sh
git checkout refactoring1
```

Puedes crear y extraer la rama(create and check out) en una sola instrucción usando esto:

```sh
git checkout -b refactoring1
```

La bandera **`-b`** indica la instrucción **`checkout`** para crear la rama y luego verificarla. Más tarde, Git agregó una instrucción **`switch`** con un nombre quizás más indicativo.

Para cambiar a una rama existente mediante el switch, utilice lo siguiente:

```sh
git switch refactoring1
```

Usando **`switch`**, la sintaxis para crear y extraer una nueva rama es la siguiente:

```sh
git switch -c refactoring1
```

Para listar los nombres de todas las ramas conocidas en su computadora (la rama actual aparece resaltada con un **` *`** y un color), utilice lo siguiente:

```sh
git branch
```

muestra:

```sh
* refactoring1
  main
```

Si también desea listar las ramas remotas, utilice esto:

```sh
git branch -a
```

A continuación, debe realizar algunos cambios y modificar algunos archivos. Modifiquemos nuestro método principal agregando las líneas 19 a 22 como se muestra en el Listado 3.2 .

**LISTADO 3.2: ARCHIVO MODIFICADO**

```java
14: public static void main(String[] args) {
15:    GitDemo demo = new GitDemo("Hello, Git!");
16:
17:    // Display the initial description
18:    demo.displayDescription();      // Make some changes and commit
19:
20:    // Make more changes and commit
21:    demo.description = "Version control with Git is fun and easy.";
22:    demo.displayDescription();
23: }
```

Ahora, confirme esos cambios. Para mayor comodidad, primero vayamos **`cd`** al directorio que contiene el archivo.

```sh
cd ./main/java/com/wiley/realworldjava/gitplay
```

Luego, preparemos(stage) nuestros cambios usando esto:

```sh
git add GitDemo.java
```

Observa el **`git status`**, que muestra lo siguiente:

```sh
On branch refactoring1
 
Changes to be committed:
  (use "git restore --staged <file>…" to unstage)
        modified:   GitDemo.java
```

y confirmamos nuestros cambios en la rama actual:

```sh
git commit -m "Added a line to GitDemo"
```

Esos cambios ahora están committed en tu repositorio local, y puedes ver los commits, junto con los archivos que contienen y sus mensajes de commit, usando cualquier variación del comando **`git log`** (¡permanece atento!).

Por supuesto, desea compartir esos cambios con el resto del equipo de desarrollo. El proceso para ello es enviarlos al repositorio remoto. (Puede haber cero o más repositorios remotos con nombre y, de manera predeterminada, el repositorio remoto se llama **`origin`** ).

```sh
git push origin refactoring1
```

Esto significa ***enviar(push)*** cualquier commits desde su repositorio local a la máquina remota ( ***origin*** por defecto) a la rama llamada ***main***. (Más información sobre ramificaciones próximamente).

Para enviar(push) el código a la rama actual y al origen desde el que lo clonaste, puedes prescindir de la formalidad y simplemente llamar a lo siguiente:

```sh
git push
```

Para ver la URL del origen, utiliza esto:

```sh
git remote get-url origin
```

Para establecer la URL o el origen o nombrar un nuevo control remoto, como **`other-machine`**, simplemente use esto:

```sh
git remote add other-machine <url>
```

También puede obtener una lista de los current remotes actuales y las URL asociadas a través de esto:

```sh
git remote -v
```

Esto mostrará una lista de URL de ***fetch*** y ***push*** para cada repositorio remoto. Las URL de ***fetch*** y ***push*** pueden ser las mismas, pero no tienen por qué serlo. Por ejemplo, si su red requiere protocolos diferentes para enviar y buscar(pushing and fetching), serán diferentes. O si tiene repositorios reflejados(mirrored repos), donde envía(push) a un repositorio "central"(hub) pero extrae(pull) de un nodo "radial"(spoke) en su región, las URL de búsqueda y envío serán diferentes.

### Fetching, Merging y Pulling

El comando **`git fetch`** obtendrá(fetch) la rama especificada del servidor remoto especificado. Esto la hace disponible en su máquina local, pero no la integra con el código extraído(checked-out), donde el origen(origin ) y el nombre de la rama son opcionales.

```sh
git fetch origin my-branch
```

El comando **`git merge`** fusionará(merge) una source branch especificada de un branch remota especificada en la rama actualmente extraída(checked-out branch). Esto tiene el efecto de combinar todos los commits de la source branch en la rama actualmente extraída(checked-out branch). En el siguiente ejemplo, estás ordenando a Git que fusione una rama llamada **`my-branch`** que se encuentra en el remote origin con la rama extraída actualmente(currently checked-out branch) en tu máquina.

```sh
git merge origin my-branch
```

Puedes omitir **`origin`** y Git fusionará la rama especificada del repositorio local en la rama actualmente extraída(currently checked-out branch).

Es común tener una rama de *integración*, también conocida como rama de desarrollo ***develop***, que es esencialmente una rama general compartida por todo el equipo de desarrollo. Esta rama se usa generalmente para preparar funciones que se planea incluir en la próxima versión. (Consulta la sección “Uso de Gitflow para colaboración” más adelante en este capítulo para obtener una explicación detallada).

Al fusionarse con **`develop`** otras ramas compartidas, es una buena práctica utilizar el switch “no fast-forward” (**`no-ff`**) 

```sh
git checkout develop
git merge –no-ff my-branch
```

De forma predeterminada, los merges se realizan con ***fast-forwarded - avance rápido***. Eso significa que Git analiza todos los commits de la source branch entre el momento en que se creó esa rama y ahora. Si no hay conflictos con el estado actual de la rama, esos commits se moverán al final de la rama de destino(target). Por el contrario, si realiza un merge sin ***no-ff - avance rápido***, la rama en la que ha estado realizando sus commits permanecerá como una rama paralela separada, con un único merge commit para unirlas(to join). Esto facilita la identificación de los commits que comprenden una característica determinada. La Figura 3.5 ilustra este flujo.

<img width="814" alt="image" src="https://github.com/user-attachments/assets/15a3ddca-a74c-4ee2-b6cb-f60f36b2b020" />

**FIGURA 3.5: Fusión de Git sin y con avance rápido**

El comando **`git pull`** combina **`git fetch`** y **`git merge`** en un solo comando, extrayendo(pulling) la rama del servidor remoto y fusionándola(merging) con la rama actual.

```sh
git pull origin my-branch
```

El switch **`--no-ff`** no se puede usar directamente en una operación pull(extracción), pero puedes indicarle a Git que lo use de manera predeterminada **`no-ff`** en pulls(extracciones) configurando la variable global **`pull-ff`**.

```sh
git config --global pull.ff only
```

### Jugando con Branches

A esta altura, ya has modificado la clase **`GitDemo`** y has confirmado(committed) los cambios. Ahora viene la magia de Git.

Volviendo a la línea de comandos, volvamos a la main branch.

```sh
git switch main
```

Ahora mira la clase **`GitDemo`**, pero no te asustes. El código nuevo que agregaste antes ya no está allí, porque esos cambios de código están en la rama **`refactoring1`**, pero tú estás en la main branch.

Vamos a crear una nueva rama llamada ***refactoring2***.

```sh
git switch -c refactoring2
```

Ahora es una réplica de ***main***. Ahora modifique la clase **`GitDemo`** en una parte diferente del código agregando el método **`setAndDisplayDescription`**.

```java
10: public void displayDescription() {
11:    System.out.println("Description: " + description);
12: }
13:
14: public void setAndDisplayDescription(String description) {
15:    this.description = description;
16:    System.out.println("Description: " + description);
17: }
```

Ahora commit.

```sh
git commit -am "added setAndDisplayDescription"
```

Aquí viene la parte divertida. ¿Qué sucede cuando fusionamos(merge) los cambios de la primera rama con los cambios de la segunda rama? (Puede aparecer una ventana de Git con un mensaje de confirmación predeterminado; puedes dejar ese mensaje y escribir **`:q`** como antes).

```sh
git merge refactoring1 
```

Git hace un trabajo fabuloso al fusionar(merging) la rama **`refactoring1`** en **`refactoring2`**, produciendo una clase híbrida:

```java
1:  package com.wiley.realworldjava.gitplay;
2:
3:  public class GitDemo {
4:     private String description;
5:
6:     public GitDemo(String description) {
7:        this.description = description;
8:     }
9:
10:    public void displayDescription() {
11:       System.out.println("Description: " + description);
12:    }
13:
14:    public void setAndDisplayDescription(String description) {
15:       this.description = description;
16:       System.out.println("Description: " + description);
17:    }
18:
19:    public static void main(String[] args) {
20:       GitDemo demo = new GitDemo("Hello, Git!");
21:
22:       // Display the initial description
23:       demo.displayDescription();
24:
25:       // Make more changes and commit
26:       demo.description = "Version control with Git is fun and easy.";
27:       demo.displayDescription();
28:    }
29: }
```

### Resolución Merge Conflicts

Ese es el camino correcto, donde varios desarrolladores trabajan en el mismo conjunto de archivos y tú haces cambios en un lugar de un archivo, mientras que otra persona hizo cambios en otro lugar del mismo archivo o incluso en archivos diferentes. Cuando intentas fusionar sus cambios con los tuyos, Git hace un gran trabajo al producir un resultado híbrido.

Pero habrá ocasiones (especialmente cuando dejes pasar muchos días antes de merging) en las que tú y ellos hayan realizado cambios en la misma área general del archivo, y Git no pueda resolver el merge. En tales casos, se produce un ***merge-conflict***. Cuando eso sucede, Git le pedirá a la persona que realizó la fusión que resuelva el conflicto manualmente y continúe. La resolución de un conflicto se puede hacer manualmente, pero es mucho más fácil contar con la ayuda del IDE. Todos los IDE principales tienen un gran soporte para la resolución manual de conflictos en paralelo; más sobre esto más adelante.

Vamos a crear una nueva rama de la rama principal, llamada **`refactoring3`**.

```sh
git switch main
git switch -c refactoring3
```

La nueva rama **`refactoring3`** contiene la versión original de **`GitDemo`** Listado 3.1 . Agreguemos algo de código nuevo (líneas 19 a 22).

```java
14: public static void main(String[] args) {
15:    GitDemo demo = new GitDemo("Hello, Git!");
16:
17:    // Display the initial description
18:    demo.displayDescription();
19:
20:    // Make more changes and commit
21:    demo.description = "Git is powerful.";
22:    demo.displayDescription();
23: }
```

Y hacer commit.

```sh
git add GitDemo.java
git commit -m "added conflicting code"
```

Ahora intentemos mergear **`refactoring1`** ( Listado 3.2 ) en nuestra rama recientemente modificada **`refactoring3`**:

```sh
git merge refactoring1
```

El resultado es un mensaje:

```sh
Automatic merge failed; fix conflicts and then commit the result.
```

Mirando el código, encontramos esta horrible mezcla:

```java
14: public static void main(String[] args) {
15:    GitDemo demo = new GitDemo("Hello, Git!");
16:
17:    // Display the initial description
18:    demo.displayDescription();
19: <<<<<<< HEAD
20:    // Make more changes and commit
21:    demo.description = "Git is powerful.";
22: =======
23:
24:    // Make more changes and commit
25:    demo.description = "Version control with Git is fun and easy.";
26: >>>>>>> refactoring1
27:    demo.displayDescription();
28: }
```

Puede ver que el código que sigue a **`<<<<<<< HEAD`** y hasta **`=======`** es el código de la rama actual, y el código que sigue a ese, hasta **`>>>>>>> refactoring1`**, es de la rama **`refactoring1`**.

Cuando se produce un merge conflict como este, hay dos opciones: cancelar el merge o solucionarlo. Para cancelar un merge después de un conflicto y restaurar todo a como estaba antes del merge, utilice lo siguiente:

```sh
git merge --abort
```

Inténtalo y, ¡listo!, ¡se restaurará el código original! Por otro lado, puedes optar por solucionarlo: elimina las líneas **`<<<<<<< HEAD`**, **`=======`** y **`>>>>>>> refactoring1`** y ajusta el código a tu gusto.

```java
14: public static void main(String[] args) {
15:    GitDemo demo = new GitDemo("Hello, Git!");
16:
17:    // Display the initial description
18:    demo.displayDescription();
19:  
20:    // Make more changes and commit
21:    demo.description = "Git is fun and easy, and very powerful.";
22:    demo.displayDescription();
23: }
```

Luego, llame **`git add`** para marcar el conflicto como resuelto y llame **`git commit`** para indicarle a Git que continúe con el merge.

```sh
git add GitDemo.java
git commit -m "resolved conflict"
```

¡Viva la paz en la Tierra!

### Uso de Pull/Merge Requests

Cuando se trabaja en un entorno colaborativo, especialmente en un gran proyecto de código abierto, las empresas asignarán acceso de lectura al equipo más grande y reservarán el acceso de escritura solo para los "colaboradores - committers". En tales casos, el equipo podría tener la capacidad de crear ramas, pero podría no tener la capacidad de fusionarse en las ramas principales compartidas, como **`main`** y **`development`**. O en casos más extremos, el equipo tendría que clonar el repositorio y realizar todos los cambios en el clon.

En este tipo de empresas, cuando se quieren incorporar los cambios a las ramas principales del repositorio principal, es necesario solicitarlo a un administrador mediante un ***pull request - solicitud de incorporación*** de cambios. Para crear un pull request de cambios, se debe iniciar sesión en el proveedor y elegir la opción para crear una nueva pull request de cambios (o una  merge request en GitLab).

<hr>

**TIP**: Los Pull requests y merge requests son simplemente nombres diferentes para, en esencia, lo mismo. GitHub y Bitbucket utilizan el término pull request, mientras que GitLab utiliza el término merge request. Para los fines de este libro, utilizaremos el término pull request, a menudo abreviado como ***PR***.

### Uso del Git Log

Vimos que el comando **`git log`** lista todos los commits en la rama actual.

Puedes agregar varias opciones al comando **`git log`** para controlar aspectos como el range of commits, formatting options, graphing options, etc. No entraremos en detalles aquí; consulta la documentación de Git en https://git-scm.com/docs/git-log.

Una opción que mencionaremos aquí es la opción apropiadamente nombrada **`--oneline`**, que muestra una vista concisa del one-commit-per-line por línea. Cuando agrega la opción **`--graph`**, también muestra una vista gráfica de sus ramas.

```sh
git log --graph --oneline
```

A continuación se muestra un historial de confirmaciones para la rama actual:

```sh
*   00cdd10 (HEAD -> refactoring3) Merge branch 'refactoring1' into refactoring3
|\
| * f162588 (refactoring1) added a display
* | b635ca1 Whitespace
* | 51d31a6 added conflicting display message
|/
* 822d223 (main) Formatting
* 55de6c6 (origin/main, origin/HEAD) added detail
* 53753a2 renaming
* ed46f26 Initial commit
```

También puede mostrar el historial de commit de cualquier rama específica agregando el nombre de la rama.

```sh
git log --graph --oneline refactoring1 
* f162588 (refactoring1) added a display
* 822d223 (main) Formatting
* 55de6c6 (origin/main, origin/HEAD) added detail
* 53753a2 renaming
* ed46f26 Initial commit
* 283d86f Initial commit
```

Para ver todas las ramas, utilice la opción **`--all`**. También puede formatear la salida, como en el siguiente ejemplo:

```sh
git log --graph --oneline --all --pretty=format:'%h %an %ar - %s'
*   00cdd10 vgrazi 2 days ago - Merge branch 'refactoring1' into refactoring3
|\
* | b635ca1 vgrazi 2 days ago - Whitespace
* | 51d31a6 vgrazi 2 days ago - added conflicting display message
| | *   d0f9078 vgrazi 2 days ago - Merge branch 'feature/refactoring1' into feature/refactoring2
| | |\
| | |/
| |/|
| * | f162588 vgrazi 2 days ago - added a display
|/ /
| * 640faec vgrazi 2 days ago - added method
|/
* 822d223 vgrazi 2 days ago - Formatting
* 55de6c6 vgrazi 2 days ago – added detail
| * 80dbc6d vgrazi 2 days ago - Added .gitignore
| * 22fe224 vgrazi 2 days ago - Typo
|/
* 53753a2 vgrazi 2 days ago - renaming
* ed46f26 vgrazi 2 days ago - Initial commit
* 283d86f realworldjava 7 days ago - Initial commit
```

Estas son las definiciones placeholder que puedes pasar al formateador. Se reemplazarán con información de cada commit.

* **`%h`**: Abbreviated commit hash
* **`%an`**: Author name
* **`%ar`**: Author date, relative
* **`%s`**: Commit subject

### Rebasing

Cuando fusionas ramas(merge branches), Git crea un extra “merge” commit (confirmación de “fusión”) adicional que contiene los resultados del merge. Esto es útil en situaciones en las que quieres destacar los commits que dieron lugar a esta branch. Por otro lado, esto tiende a saturar el historial de commits con commits adicionales.

Si desea omitir esa extra merge commit, existe una solución alternativa en algunas situaciones: realizar un ***rebase*** en lugar de un merge. Un rebase es como un merge, excepto que mueve sus commits al final de la target branch, en lugar de crear una rama paralela y crear un merge commit.

Para comprenderlo, es necesario experimentarlo, así que vamos a crear un ejemplo. Vamos a crear una feature branch, realizar algunos commits y comparar los resultados de una merge versus a rebase.

1. Crea una feature branch desde **`refactoring3`** y llámala **`feature`**.

   ```sh
   git switch -c feature
   ```
   
2. Realice algunos commits en la rama **`feature`**: agregue las líneas 23 a 26 y luego commit.

```java
20: // Make more changes and commit
21: demo.description = "Git is fun and easy, and very powerful.";
22: demo.displayDescription();
23:
24: // Make another change
25: demo.description = "Changes for rebase";
26: demo.displayDescription();
```

y luego commit.

```sh
git commit -am "changes to feature for rebase"
```

Realice algunos cambios más agregando las líneas 27 a 30.

```java
24:    // Make another change
25:    demo.description = "Change1 for rebase";
26:    demo.displayDescription();
27:
28:    // And yet another change
29:    demo.description = "Change2 for rebase";
30:    demo.displayDescription();
31:}
```

y luego commit:

```sh
git commit -am "more changes to feature for rebase"
```

4. Volver a **`refactoring3`**:

```sh
git switch refactoring3
```

5. Realice algunas commits en la rama **`refactoring3`** y agregue las líneas 17 a 19.

```java
14: public static void main(String[] args) {
15:    GitDemo demo = new GitDemo("Hello, Git!");
16:
17:    demo.description = "Continuing on branch";
18:    demo.displayDescription();
19:
```

y luego commit:

```sh
git commit -am "more changes to refactoring3"
```

<hr>

**TIP** Si no incluye un commit message **`-m`**, aparecerá una ventana del editor VI y le solicitará un mensaje de confirmación. Si eso sucede, presione **`i`** para ingresar al modo de edición y escriba su mensaje; luego presione Enter para comenzar una nueva línea. Cuando haya terminado, presione Esc para salir del modo de edición, escriba **`:w`** para escribir su mensaje en el commit y escriba **`:q`** para salir. Esa es la edición VI básica, con la que los usuarios de Unix/Linux están íntimamente familiarizados.

<hr>

6. Copiar la rama **`refactoring3`** a **`refactoring3a`**.

   ```sh
   git branch -c refactoring3a
   ```

7. Merge **`feature`** en**`refactoring3a`**(como en la última fusión, puede aparecer una ventana de Git con un mensaje de confirmación predeterminado; puedes dejar ese mensaje y escribir :qcomo antes).
git merge feature
Cambiar a refactoring3.
git switch refactoring3
Rebasar la función en refactoring3.
git rebase feature
Compara los registros refactoring3ade la parte superior (fusión) y de refactoring3 en la parte inferior (rebase). Puedes ver que rebase movió el historial de confirmaciones al final de la rama de destino, mientras que la fusión creó una nueva confirmación de fusión .
git log --graph --oneline refactoring3
Esto incluye lo siguiente:

* 019f4f7 (HEAD -> refactoring3) more changes to refactoring3
* 4954034 (feature) more changes to feature for rebase
* 607d6bb changes to feature for rebase
* 502f3b3 resolved conflict
 
git log --graph --oneline refactoring3a
que incluye lo siguiente:

*   7f5c82c (refactoring3a) Merge branch 'feature' into refactoring3a
|\
| * 4954034 (feature) more changes to feature for rebase
| * 607d6bb changes to feature for rebase
* | 4821d9c more changes to refactoring3
|/
* 502f3b3 resolved conflict
 
De cualquier manera, el código es idéntico, pero la rebase produce un historial mucho más limpio. Entonces, ¿cuál es la desventaja? ¿Por qué usaríamos la combinación y no la rebase?

La respuesta es que la rebase reescribe el historial de confirmaciones. Recuerda que dijimos que el ID de la confirmación incluye la versión anterior. Bueno, dado que estamos moviendo el historial de confirmaciones al final de la rama, la versión anterior es diferente y, por lo tanto, el ID de la confirmación es diferente. ¿Por qué es malo eso? Bueno, no es malo si estás trabajando solo en la rama y si no has fusionado tu trabajo en ninguna otra rama. Pero si estás colaborando o si has fusionado esta rama en cualquier otra rama compartida, entonces cualquiera que comparta ese trabajo tendrá problemas para fusionarlo nuevamente en su propio código.

Como puede ver en la Figura 3.6 , ambas ramas refactoring3tienen refactoring3aexactamente la misma versión del código, pero refactoring3a(la rama fusionada) consta de dos ramas paralelas que se fusionan en una única confirmación, mientras que refactoring3(la rama rebasada) es una rama recta.

<img width="827" alt="image" src="https://github.com/user-attachments/assets/076bffc5-ec06-4d09-9cda-f3e317246529" />

**FIGURA 3.6: Fusión versus rebase**

<hr>

**LA REGLA DE ORO DEL REBASING**

La regla de oro del rebase dice que nunca se debe rebasear una rama que se comparte con otros desarrolladores o que se ha enviado o fusionado a un repositorio remoto. En lugar de eso, solo se deben rebasear ramas locales o privadas a su propio repositorio.

Lo que esto significa en la práctica es no volver a basar nada que ya se haya enviado al control remoto, ni nada que se haya fusionado en otra rama que se enviará en el futuro.

<hr>

### Cherry-Picking

Aprendió a desarrollar sus cambios en una rama y luego fusionar o reorganizar esos cambios en otras ramas. Pero ¿qué sucede si desea integrar de forma selectiva algunos cambios, pero no todos, de una rama a otra?

Git ofrece una solución a este problema en forma de cherry-picking . Cherry-picking es la capacidad de aplicar commits específicos de una rama a otra. Para ello, cambia a la rama de destino, localiza el ID de commit del commit que quieres seleccionar y luego llama al git cherry-pickcomando. No necesitas especificar el ID de commit completo; basta con los primeros caracteres que identifican el commit de forma única. Por ejemplo, para seleccionar el ID de commit 4954034c… en la rama refactoring1 , haz lo siguiente:

git switch refactoring1
git cherry-pick 4954
Recuerda que tendrás diferentes ID de confirmación si estás siguiendo el proceso, así que usa git logpara encontrar una que puedas elegir. Ten cuidado: en muchos casos, la selección de la información adecuada dará lugar a un conflicto de fusión que tendrás que resolver, así que ten cuidado. En este caso, tenemos un conflicto; resuélvelo manualmente como antes y, para continuar, llama a esto:

git commit -am "Cherry picked and then resolved conflict"
Git responde amablemente con esto:

1 file changed, 8 insertions(+)
Revertir y restablecer
¿Cómo se deshace una confirmación? Hay dos formas: git reverty git reset.

git revert <commit id>crea una nueva confirmación para cambiar los archivos al estado en el que estaban en el momento de ese ID de confirmación.

git reset <commit id>es más intrusivo; en realidad, cambia el historial y descarta las confirmaciones que siguieron al ID de confirmación. Este comando viene en tres versiones:

git reset --soft <commit id>Restablece el puntero de la rama actual para que apunte a la confirmación especificada. Sin embargo, conserva los cambios que haya realizado en el directorio de trabajo y el área de preparación. Esto tiene el efecto de "desconfirmar" sus cambios.

git reset –hard <commit id>También restablece el puntero de la rama para que apunte a la confirmación especificada. Sin embargo, descarta todos los cambios tanto en el directorio de trabajo como en el área de preparación, y restablece la rama a la confirmación especificada. Con un restablecimiento completo, se pierden todos los cambios.

git reset <commit id>sin especificar --softo --hardes un “reinicio mixto”. Como con todos los reinicios, restablece el puntero de la rama a la confirmación especificada. Al igual que un reinicio suave, conserva los cambios, pero los desorganiza. Esto es útil cuando desea comenzar su preparación desde el principio y reevaluar qué preparar y qué no preparar para la próxima confirmación.

En lugar de especificar una confirmación, puedes especificar la cantidad de confirmaciones de las que debes deshacerte mediante la sintaxis HEAD~. Por ejemplo, git reset HEAD~1hará un reinicio mixto, estableciendo el puntero de la rama en una confirmación antes de la última. HEAD~2lo establecerá en dos confirmaciones antes de la última, y ​​así sucesivamente. Se puede usar cualquier número entero positivo después de HEAD~.

Para comprender mejor las diferencias semánticas, consulte la comparación en la Tabla 3.1 .

**TABLA 3.1: Revertir y restablecer**

<img width="825" alt="image" src="https://github.com/user-attachments/assets/ffd17bd6-dd24-4dcb-97a0-9d187e11c3e2" />

### Optimización con soporte IDE

Todos los IDE más importantes ofrecen compatibilidad de primer nivel con Git. En esta sección, abordaremos la compatibilidad con IntelliJ IDEA.

Un archivo sin seguimiento aparecerá en color marrón. IntelliJ le ofrecerá comenzar a realizar el seguimiento, como se muestra en la Figura 3.7 .

<img width="913" alt="image" src="https://github.com/user-attachments/assets/72d6a845-8e2b-4bfe-8fac-a581994d960e" />

**FIGURA 3.7: Seguimiento de un nuevo archivo**

La primera vez que se realiza un seguimiento de un archivo, se lo coloreará en verde para indicar que se trata de un archivo recién rastreado que nunca se ha confirmado, según la Figura 3.8 . (La HelloWorldclase que está en un círculo está coloreada en una fuente verde).

Si ya se creó un archivo de forma externa (quizás se lo movió al proyecto desde el sistema de archivos), aún puede rastrearlo; simplemente haga clic derecho en el archivo y seleccione Git y luego Agregar. Esto lo agregará al área de preparación, como se muestra en la Figura 3.9 .

<img width="900" alt="image" src="https://github.com/user-attachments/assets/764386f0-f5dc-4dcd-a789-04d7a30ef2e8" />

**FIGURA 3.8: Codificación de colores para un archivo recién rastreado**

<img width="747" alt="image" src="https://github.com/user-attachments/assets/f16fd39f-0880-4ec9-bf4f-02a1de4c5ca9" />

**FIGURA 3.9: Seguimiento de un archivo externo**

Mirando la ventana de confirmación
La creación de cambios es una operación habitual, por lo que, para mayor comodidad, configuramos Ctrl+Alt+A como el acceso directo del mapa de teclas de Windows para esta operación. Consulte el Capítulo 2 para crear accesos directos del mapa de teclas.

Para confirmar los cambios, seleccione la opción de menú Git/Commit (el atajo de teclado en Windows es Ctrl+K; el atajo de teclado en Mac es Cmd+K). Esto abrirá la ventana de confirmación donde podrá ver todos los archivos preparados.

CONSEJO  Ctrl+K (o Cmd+K) también es útil cuando solo quieres ver qué ha cambiado. Abre la ventana de confirmación, que muestra todos los cambios. Usa F7 y Shift+F7 para navegar hacia adelante y hacia atrás a través de todos los cambios.

Los cambios a los archivos rastreados se preparan automáticamente y aparecerán en la ventana de confirmación, pero si aún no está listo para confirmar, puede deshacer la preparación de los mismos desmarcando la casilla de verificación junto al nombre del archivo en la ventana de confirmación.

Al hacer clic derecho en la ventana de confirmación, aparecerá una ventana de contexto. La mayoría de las opciones se explican por sí solas, pero llame su atención sobre la opción Nueva lista de cambios (consulte la Figura 3.10 ). IntelliJ garantiza que solo pueda confirmar una lista de cambios a la vez, por lo que si desea mantener algunos archivos fuera de su confirmación por ahora, puede crear una nueva lista de cambios y mover esos archivos a esa lista de cambios para separar sus confirmaciones.

<img width="638" alt="image" src="https://github.com/user-attachments/assets/30a59e97-c429-4bb6-912c-9e8f3e370554" />

**FIGURA 3.10: Ventana de contexto de confirmación**

Uso de la ventana Diff-Viewer
Si hace doble clic en los archivos en la ventana de confirmación, aparecerá la ventana del visor de diferencias, donde se muestran las versiones anterior y actual una al lado de la otra. Puede realizar modificaciones directamente en la ventana del visor de diferencias. Puede elegir desde el selector en la parte superior de la ventana del visor de diferencias si desea ignorar los cambios de espacios en blanco, cambios de líneas en blanco, etc.

CONSEJO  Es una buena práctica hacer doble clic en los archivos en la ventana de confirmación para abrir la ventana del visor de diferencias, donde puede revisar los cambios. Esto le permite echar un último vistazo antes de confirmar el código. Al hacerlo, invariablemente encontrará oportunidades para eliminar código duplicado, corregir errores tipográficos y realizar limpiezas similares.

F7 es un atajo conveniente para navegar de un cambio al siguiente. Shift+F7 te llevará de regreso al cambio anterior. Cuando llegues al final del archivo y hagas clic en F7 nuevamente, IntelliJ te indicará que pases al siguiente archivo.

Las líneas modificadas aparecerán en la ventana del visor de diferencias, como se muestra en la Figura 3.11 , con un resaltado azul claro y una casilla de verificación en el margen. Puede elegir qué cambios confirmar marcando o desmarcando la casilla de verificación junto a cada cambio en la ventana del visor de diferencias. Solo se confirmarán los cambios seleccionados. Si hace clic derecho en un cambio, puede elegir enviar ese cambio a otra lista de cambios para que las confirmaciones en ese archivo no incluyan esos cambios.

<img width="831" alt="image" src="https://github.com/user-attachments/assets/35a6ff7b-a3e5-4768-84bd-e26cc10d4ddf" />

**FIGURA 3.11: Ventana del visor de diferencias**

Para estar seguro, si tiene una gran cantidad de cambios, es fácil desmarcar algo que realmente quería confirmar o marcar algo que no quería.

Cuando tienes código que no quieres confirmar, es bueno rodearlo de algo muy visible, como lo siguiente. ¡Esto hará que sea difícil confirmarlo por accidente!

///////// Don't Commit ///////////
someCodeToNotCommit();
someMoreCodeToNotCommit();
///////// Don't Commit ///////////
El menú Git proporciona todos los comandos descritos y más, como puede ver en la Figura 3.12 .

<img width="786" alt="image" src="https://github.com/user-attachments/assets/f37c289c-d72b-494b-8e58-1d85bd099dc6" />

**FIGURA 3.12: Menú Git de IntelliJ**

Confirmar: confirma los cambios en todos los archivos rastreados en el repositorio local.
Push: envía los cambios al servidor remoto.
Actualizar proyecto: obtiene del servidor remoto las últimas versiones de todos los archivos en la rama actualmente extraída; use Git ➪ Actualizar proyecto o Ctrl+T (Cmd+T en Mac).
Pull: actualiza una rama específica desde el control remoto seleccionado.
Obtener: actualiza una rama específica del servidor sin realmente extraerla. En caso de que haya un conflicto que el IDE no pueda resolver, abortará la obtención. En este caso, puede archivar o guardar sus cambios, realizar la obtención y luego desarchivar sus cambios y resolver manualmente los conflictos. (Más información sobre archivar cambios más adelante en este capítulo).
Fusionar: fusiona la rama especificada en la rama actual.
Rebase: rebase la rama especificada en la rama actual.
Ramas: Un submenú para todas las operaciones de ramificación, incluida la creación de una nueva rama o el cambio a otra rama.
Nueva rama: un menú dedicado para crear ramas.
Nueva etiqueta: crea una nueva etiqueta en la rama actual.
Restablecer HEAD: le permite volver a una versión anterior mediante restablecimientos completos, suaves o mixtos.
Mostrar registro de Git: proporciona una representación gráfica del registro de confirmaciones y ramas de Git.
Parche: Herramientas para crear un parche , que puede aplicarse posteriormente para reproducir un determinado estado.
SUGERENCIA  Un parche es un archivo que contiene las diferencias entre los conjuntos de archivos modificados y la versión original. Puede aplicar un parche a un conjunto de archivos de origen para producir una versión de destino que contenga los cambios capturados en el archivo de parche. También puede compartir archivos de parche con otras personas para que produzcan el estado de destino de los cambios.

Cambios no confirmados: Vale la pena analizar este tema en todos sus submenús; la Figura 3.13 muestra las opciones del submenú Cambios no confirmados.

<img width="701" alt="image" src="https://github.com/user-attachments/assets/fcfc6188-205b-4bf9-b54e-360e90be32ad" />

**FIGURA 3.13: Submenú de cambios no confirmados de IntelliJ**

Archivar cambios: le permite dejar de lado o archivar temporalmente los cambios actuales en el repositorio de IntelliJ, donde puede inspeccionarlos y recuperarlos más tarde.
Mostrar estante: muestra todos los cambios archivados y proporciona herramientas de selección para recuperar algunas o todas las líneas de cambio.
Cambios en Stash: como el almacenamiento, pero utiliza herramientas Git en segundo plano. Si usa el IDE, la función de almacenamiento de IntelliJ es conveniente, pero si prefiere ejecutar cosas desde la línea de comandos, es posible que prefiera el almacenamiento.
Deshacer cambios guardados: le permite volver a aplicar los cambios guardados.
Revertir: selecciona archivos para restaurarlos al estado original.
Mostrar cambios locales como UML: dibuja un diagrama de clases UML que contiene las clases y métodos que contienen cambios locales.
Archivo actual: Este también merece una exploración de sus submenús; consulte la Figura 3.14 .

<img width="739" alt="image" src="https://github.com/user-attachments/assets/b093f288-49d4-4c09-aea1-e854c6f5bb6a" />

**FIGURA 3.14:S ubmenú Archivo actual de IntelliJ**

Archivo de confirmación: abre la ventana de confirmación, donde puede seleccionar los cambios que desea confirmar.
Agregar: le dice a Git que rastree un nuevo archivo.
Anotar con Git Blame: muestra en el margen el nombre de la persona que actualizó por última vez cada línea del archivo actual.
Mostrar diferencias: muestra en paralelo la ventana del visor de diferencias del archivo actual tal como está ahora y cómo estaba cuando se extrajo.
Comparar con revisión: proporciona una lista de confirmaciones recientes para que pueda comparar con el estado local.
Comparar con sucursal: proporciona una lista de sucursales para que pueda comparar con el estado local.
Mostrar historial: muestra una lista de todas las confirmaciones para este archivo y le permite compararlo con estados anteriores.
Mostrar historial del método: muestra una lista de todas las confirmaciones para el método actual y le permite comparar con estados anteriores.
Mostrar historial de la selección: aparece solo cuando se ha seleccionado algo. Este elemento del menú muestra una lista de todas las confirmaciones de esa selección y permite compararlas con estados anteriores.
Puede obtener una lista más amplia de opciones de Git haciendo clic derecho en un archivo en el editor y eligiendo Git, como se muestra en la Figura 3.15 .

<img width="663" alt="image" src="https://github.com/user-attachments/assets/f9afc8c7-7e0e-44d3-9971-fe2ff28ab3a5" />

**FIGURA 3.15: Menú contextual de Git**

IntelliJ tiene una ventana de registro de Git que se puede abrir haciendo clic en el icono de Git en la parte inferior izquierda. Incluye una pantalla de registro gráfica que permite seleccionar una rama, un ID de confirmación, etc., y muestra un árbol que ilustra las ramas. Esto es mucho más fácil de usar que escribir comandos de registro, como se puede ver en la Figura 3.16 .

<img width="676" alt="image" src="https://github.com/user-attachments/assets/485bdf42-dd07-448d-877f-a7f654f2670b" />

**FIGURA 3.16: Ventana de registro de Git de IntelliJ**

Puede seleccionar ramas locales o remotas, pero tenga en cuenta que la lista de ramas y el contenido de las ramas serán los de la última actualización. Seleccione Git ➪ Actualizar para ver una lista actualizada de ramas y para actualizar la rama que se encuentra actualmente extraída del servidor. Para actualizar otras ramas, puede seleccionarlas individualmente desde el menú Git ➪ Extraer.

Otra característica que debes conocer es la función Git ➪ Historial. Puedes hacer clic derecho en cualquier archivo administrado y elegir Git ➪ Historial para obtener una lista de todas las versiones de ese archivo. Es un salvavidas cuando descubres que algo está roto y quieres encontrar la última versión buena conocida. Puedes obtener el historial de un archivo completo o puedes hacer una selección y ver el historial solo de esa selección.

En noticias relacionadas, IntelliJ también ofrece una función de historial local , donde puedes obtener un historial de versiones rápido sin Git, e incluso para archivos que no son rastreados por Git.

Creación de archivos README con lenguaje Markdown
Cuando navegues a la página de inicio de un proyecto de Git en GitHub o en uno de los otros proveedores de Git, generalmente verás una descripción del proyecto, quizás algunas instrucciones de uso y enlaces útiles. Como ejemplo, dirígete al repositorio de capítulos de este capítulo en https://github.com/realworldjava/Ch03-Collaboration. Puedes crear dicha documentación en tus propios proyectos incluyendo un archivo llamado README.mden la raíz de tu proyecto. La .mdextensión significa Markdown, un lenguaje de marcado ligero que se utiliza en la documentación de Git.

SUGERENCIA:  Si bien cualquier .md archivo se considerará Markdown en GitHub, solo el README.md archivo se muestra automáticamente en la página de inicio del repositorio.

Markdown admite texto simple, así como encabezados, énfasis, listas, enlaces y bloques de código. El lenguaje es bastante simple y solo hay unos pocos elementos de sintaxis que necesitarás aprender. IntelliJ y VS Code son lo suficientemente buenos como para mostrarte una vista en paralelo de tu código de marcado y su representación visual, por lo que te recomendamos que experimentes con el README.docrepositorio de este capítulo. Eclipse no tiene una vista en paralelo, pero sí tiene una pestaña de vista previa.

Se puede introducir texto directamente. Las líneas de texto contiguas se fusionarán en una sola línea, a menos que estén seguidas de una línea en blanco, en cuyo caso se iniciará un nuevo párrafo. Si desea anular este comportamiento y comenzar una nueva línea, simplemente agregue dos espacios al final de la línea, lo que hará que la siguiente línea comience en una nueva línea.

Markdown admite seis niveles de encabezados. Para designar un encabezado de nivel uno, comience la línea con #seguido de un espacio. Un encabezado de nivel dos comienza con ##y un espacio, y así sucesivamente.

Para agregar cursiva, rodee el texto con *. A continuación, se muestra un ejemplo:

*This is italicized*
Asegúrese de no incluir un espacio después del primer asterisco.

Para poner en negrita el texto seleccionado, rodéelo con **. A continuación, se muestra un ejemplo:

**This is bold**
Nuevamente, no hay espacios después del primer **.

Las listas se presentan en versiones ordenadas y desordenadas. Para crear una lista desordenada, coloque un *como primer carácter en la línea, seguido de un espacio. A continuación, se muestra un ejemplo:

* This is the first item
* This is the second item
* Etc.
Para crear una lista ordenada, comience la línea con un número de elemento, seguido de un punto y un espacio. A continuación, se muestra un ejemplo:

1. This is the first item
2. This is the second item
3. Etc.
Independientemente de los números que escribas, Markdown los mostrará en el orden natural. Nos gusta numerar cada elemento de la lista 1.para que, si cambiamos los elementos, Markdown se encargue de la numeración adecuada para que no tengamos que hacerlo nosotros.

Para especificar un enlace, simplemente comience con http://o https://y Markdown lo representará como un enlace. Si desea proporcionar texto para el enlace, utilice esta sintaxis:

[This is the text](https://www.some-link.com)
Se mostrará el texto entre corchetes y el texto entre corchetes será el enlace.

Para especificar el código, puede especificar el idioma y el código mediante la sintaxis de “tres comillas invertidas”. Markdown reconoce las muchas etiquetas de idioma, incluidas las siguientes:

java
python
javascript
html
css
markdown(para bloques de código anidados)
bash
sql
He aquí un ejemplo:

```java
public class HelloMarkdown {
    public static void main(String[] args) {
        System.out.println("Hello, Markdown!");
    }
}
```
Nuevamente, te animamos a que juegues con todos ellos para familiarizarte con el uso de Markdown.

Uso de Gitflow para la colaboración
Como has visto, Git es una gran herramienta para mantener versiones en evolución de tu código base de software. ¡Pero este capítulo trata sobre la colaboración ! ¿Cómo podemos aprovechar las capacidades de Git para colaborar en un entorno dinámico y en constante cambio?

Existen algunas metodologías populares. Por ejemplo, el desarrollo basado en trunk es un proceso en el que el código se fusiona frecuentemente con la rama principal (también conocida como trunk) y se ejecutan pruebas unitarias automatizadas en cada confirmación. Si el trunk se compila, está listo para su lanzamiento. En algunos casos, los desarrolladores realizan confirmaciones directamente en main . En otros, utilizan ramas de corta duración y una solicitud de incorporación de cambios cuando la rama está lista para fusionarse con main .

En entornos grandes y altamente regulados, como los bancos y otras instituciones financieras, las publicaciones deben estar mucho más controladas. Para esos requisitos, Gitflow es una metodología común.

En pocas palabras, Gitflow es un proceso que permite a un equipo de desarrolladores dividirse en grupos más pequeños de uno o más desarrolladores. Cada grupo trabaja en alguna característica y todo el equipo comparte una base de código común.

Con esta estrategia, cada característica obtiene una rama de características , que se confirma periódicamente, se crea y se prueba y, cuando se termina, la rama de características se fusiona con la rama común, normalmente denominada desarrollo . Finalmente, cuando se planifica un lanzamiento, las ramas de características se fusionan en una nueva rama de lanzamiento , que se crea, se prueba y se prepara para el lanzamiento. Esta estrategia permite que todos colaboren y recuperen características que podrían haberse preparado prematuramente para el lanzamiento.

La figura 3.17 muestra los pasos.

<img width="855" alt="image" src="https://github.com/user-attachments/assets/33930ac8-e570-4724-9d90-908f03de1137" />

**FIGURA 3.17: Flujo de trabajo de Gitflow**

El primer paso es crear una nueva rama llamada desarrollo a partir de la rama principal . Esta es una tarea que se realiza una sola vez. La rama desarrollo es una rama que recopila todo, pero nada se asigna directamente a desarrollo . La rama desarrollo solo recibe fusiones de otras ramas. Una vez que se crea desarrollo , permanece durante la vida útil del proyecto.
Cuando se acuerda una característica, se crea una rama de características para esa característica. Normalmente, la empresa definirá un requisito para esa característica y lo rastreará en algún sistema de seguimiento como Jira (que abordaremos en la siguiente sección). El sistema de seguimiento asignará una clave a este requisito y, aunque el nombre de la rama de características es flexible, es común darle un nombre que comience con feature/ seguido de la clave y una descripción extremadamente breve pero explicativa (no se permiten espacios, así que use guiones). Un ejemplo de nombre de rama de características podría ser algo como feature/RWJ-1234-add-ui-login , donde RWJ-1234 es la clave de Jira para esta nueva característica de "agregar un inicio de sesión de UI".
A medida que los equipos trabajan en sus ramas de funciones, continúan desarrollando código y confirmando. El servidor de compilación ejecuta una compilación en cada confirmación. Consulte el Capítulo 4 , “Automatización de sus compilaciones de CI/CD con Maven, Gradle y Jenkins”, para obtener más detalles.
Cuando se considera que una característica está completa, se vuelve a fusionar con la rama de desarrollo . Recuerde que la developrama ha estado evolucionando en paralelo mientras usted trabajaba, ya que otros miembros del equipo estaban escribiendo su propio código. Por lo tanto, se verá diferente a cuando originalmente ramificó la rama de la característica. Por lo tanto, se requiere nuevamente un nuevo ciclo de compilación y prueba, y eso es exactamente lo que hace el servidor de compilación.
La rama de desarrollo está lista para su lanzamiento. Cree una nueva rama de lanzamiento a partir de la rama de desarrollo denominada release / seguida de una versión de lanzamiento. Pero el proceso no termina aquí. Ahora que se ha cortado la rama de lanzamiento, el desarrollo puede seguir evolucionando en la rama de desarrollo para futuros lanzamientos, y solo este lanzamiento se mantiene en la rama de lanzamiento .
La rama de lanzamiento ahora está probada, posiblemente por un equipo de control de calidad (QA).
Se informan los errores, se corrigen y se vuelven a fusionar para desarrollarlos.
Cuando se certifica que la rama de lanzamiento está lista para su lanzamiento, se fusiona con la rama principal y se corta una etiqueta de lanzamiento en la rama principal . La rama principal realiza un seguimiento de todos los lanzamientos históricos y es fácil reproducir un lanzamiento anterior consultando la etiqueta de lanzamiento de cualquier lanzamiento.
Hemos publicado el código en producción, pero aún no hemos terminado. Alguien descubre un error en producción, se crea una rama de revisión, se trabaja para solucionar el error y repetimos el proceso desde el paso 5.
Al igual que con los cambios en cualquier rama, los cambios realizados en la rama de revisión deben fusionarse nuevamente con la rama de desarrollo .
Cuando esté lista, la rama de revisión se fusionará con la principal y se etiquetará para su lanzamiento.
Algunos de los beneficios de Gitflow:

Las características están aisladas, lo que facilita la gestión de sus propios cambios de características de forma aislada.
Fácil mantenimiento de diferentes versiones.
Las características están separadas, lo que le permite decidir qué características incluir en la versión.
CONSEJO  Una desventaja: si está descargando las compilaciones de instantáneas, puede encontrar conflictos de versiones cuando diferentes equipos compilan sus funciones. Cuando eso sucede, los binarios generados tendrán todos el mismo -SNAPSHOT número de versión para conjuntos de funciones completamente diferentes. Esto no es un impedimento, porque si está implementando instantáneas, los equipos pueden coordinarse entre sí para decidir qué publicar.

## USO DE JIRA PARA LA COLABORACIÓN DE PROCESOS EMPRESARIALES

Antiguamente, el software se desarrollaba siguiendo un método en cascada, es decir, un proceso secuencial por fases en el que el progreso fluía hacia abajo, como una cascada.

Primero se prepararon y aprobaron los requisitos funcionales. Luego vino la fase de diseño seguida de la implementación, que duraría algún tiempo. Finalmente, se probaría, implementaría y entregaría al cliente. El proceso completo podría llevar meses o años y, al final, el cliente podría haber quedado satisfecho o no, y era difícil asignar recursos porque las fases eran secuenciales y requerían analistas de negocios (BA) al principio, arquitectos y desarrolladores en el medio, y probadores y personal de lanzamiento al final.

En 2001, nació el Manifiesto Ágil, que presentó al mundo un enfoque en capas para el desarrollo de software. Escucharás procesos ágiles con nombres como Scrum y Programación Extrema . Cada dos o tres semanas comenzaría un nuevo sprint , encargado de la entrega de un subconjunto completo de requisitos. Las tareas se asignarían al sprint y progresarían a través de un flujo de trabajo. Todos los roles estaban involucrados en cada sprint, incluidos el negocio, los diseñadores, los desarrolladores, el control de calidad, etc. Los requisitos eran dinámicos, potencialmente evolucionaban con cada sprint, y cada pocos ciclos se entregaba algún producto al negocio. Otro enfoque ágil llamado Kanban observó que los trabajos no siempre están limitados en el tiempo, e incluso si lo estuvieran, no necesariamente eran las mismas ventanas de tiempo. Kanban eliminó los sprints y, en su lugar, pidió a los equipos que analizaran su proceso y lo dividieran en una secuencia de columnas como diseño, desarrollo, prueba, lanzamiento. Imponían límites de trabajo en proceso (WIP) en cada columna y utilizaban un sistema de extracción en el que los tickets de trabajo comenzaban en la izquierda y se extraían hacia la derecha a medida que avanzaban. A medida que los desarrolladores terminaban el trabajo en su columna, extraían más trabajo de la columna anterior.

Jira de Atlassian es una de las herramientas de software más populares para gestionar todo lo relacionado con Agile. Puedes seleccionar un tablero Scrum donde el trabajo se divide en sprints de tamaño configurable o un tablero Kanban con límites de trabajo en progreso.

Jira tiene integración con GitHub y muchos otros sistemas de control de versiones, por lo que cuando realiza confirmaciones, puede incluir una clave de problema y luego puede ver las confirmaciones asociadas con cualquier ticket de Jira.

Introducción a Jira
La mayoría de las empresas ya tienen Jira instalado, pero le recomendamos que lo pruebe por su cuenta. Puede utilizar la versión gratuita en la nube de Jira en https://www.atlassian.com/software/jira. La instalación local que se utiliza en la empresa puede tener un aspecto ligeramente diferente, pero los conceptos son idénticos.

Jira es una interfaz de usuario basada en web que ha evolucionado mucho a lo largo de los años. Comenzó como un complicado programa de gestión de tickets y evolucionó hasta convertirse en una herramienta completa para la planificación y el mantenimiento de sprints, la creación y edición de problemas, la búsqueda, la administración de usuarios, la generación de informes, etc.

Independientemente del tipo de tablero que utilice su proyecto, los tickets de Jira representan una parte del trabajo. Jira comenzó como un sistema de seguimiento de errores; por lo tanto, los tickets se denominan issues , pero muchas personas se refieren a ellos con cariño simplemente como jiras . Los issues vienen en muchos sabores, como epic , story , bug , task , subtask , etc. También puede crear sus propios tipos de issues.

Generalmente, las epopeyas se utilizan como padre de un grupo de historias, errores y tareas más pequeños y relacionados.

Estos problemas más pequeños pueden contener sus propios problemas, que se denominan subtareas. Se pueden crear en cualquier orden, pero en el desarrollo empresarial una práctica común es adjuntar la mayoría de los problemas a una epopeya. Además, cada subtarea pertenece a un problema principal, como en la Figura 3.18 .

<img width="859" alt="image" src="https://github.com/user-attachments/assets/b80fb3bc-83df-45b7-8f4d-e86db7cb2f53" />

**FIGURA 3.18: Jerarquía de problemas de Jira**

Jira utiliza esta jerarquía para proporcionar una vista de arriba hacia abajo a la gerencia, que podría estar interesada solo en las epopeyas más grandes, y una vista de abajo hacia arriba a los colaboradores individuales, que se preocupan más por los detalles de implementación. Si bien está bien tener un pequeño porcentaje de tareas o errores "sueltos" que no estén en una epopeya, estos no son los que más le interesan a la gerencia.

Creando un proyecto
Los problemas se asignan a los proyectos. Si se incorpora a un equipo existente, normalmente habrá uno o más proyectos configurados. Si necesita crear un nuevo proyecto, vaya a la pestaña Proyectos y seleccione Crear proyecto, seleccione una plantilla adecuada y siga las instrucciones que aparecen allí, como se muestra en la Figura 3.19 .

<img width="837" alt="image" src="https://github.com/user-attachments/assets/b8997124-3e06-4241-ad16-9aaca614beca" />

**FIGURA 3.19: Creación de un nuevo proyecto**

Existen tipos de tableros estándar para cada plantilla. Por ejemplo, para el desarrollo de software, puede seleccionar Kanban, Scrum, etc. Elegiremos Scrum para nuestro proyecto de ejemplo. Scrum le permite administrar sus entregas en sprints con límites de tiempo, que duran dos semanas de manera predeterminada. Kanban no tiene límites de tiempo, pero divide el tablero en columnas que representan tareas generales o equipos, y hay un límite de trabajo en proceso para cada columna del tablero, como en la Figura 3.20 .

<img width="833" alt="image" src="https://github.com/user-attachments/assets/4a51b39a-4395-4948-9178-fe96a50596b9" />

**FIGURA 3.20: Selección de una plantilla de proyecto**

Creando un problema
Para crear un nuevo problema en Jira, haga clic en el botón Crear, como en la Figura 3.21 .

<img width="829" alt="image" src="https://github.com/user-attachments/assets/f8de3626-0136-42e1-9b50-fbd08d2090b7" />

**FIGURA 3.21: Creación de un nuevo problema**

Seleccione el tipo de problema y complete todos los detalles. Como todo lo relacionado con Jira, la pantalla se puede personalizar (y normalmente lo hace), por lo que la suya puede tener un aspecto diferente. Cada equipo tendrá sus propios campos, algunos obligatorios. A fines de la década de 1990, se introdujo una metodología ágil temprana llamada Programación extrema (XP) para proporcionar una forma fácil de usar de administrar los requisitos de manera ágil. Muchas organizaciones han adoptado la práctica XP de expresar problemas de tipo Historia en la forma “Como usuario de <rol>, quiero realizar <alguna actividad> para poder lograr <algún beneficio>”.

Ingrese un resumen, una descripción, un cesionario (si se conoce) y otros campos según lo requiera su equipo, como en la Figura 3.22 .

<img width="655" alt="image" src="https://github.com/user-attachments/assets/823cad34-7246-4c81-b861-fdb264b4e226" />

**FIGURA 3.22: Completar el nuevo número**

Vinculación a una epopeya
Como práctica recomendada, la mayoría de los equipos tendrán una política de asignar la mayoría de los problemas a una épica principal. Puede vincular un problema a una épica cuando crea el problema, o puede agregar o cambiar el vínculo de la épica más tarde. Luego puede obtener una vista general de todo el proyecto al ver las épicas en el tablero del proyecto como en la Figura 3.23 .

<img width="663" alt="image" src="https://github.com/user-attachments/assets/b089a967-4287-4fb2-8dfd-705f99de324f" />

**FIGURA 3.23: Asignación de una epopeya a un problema**

Trabajando con tableros
El verdadero beneficio de Jira comienza con el tablero . Nuestro proyecto de muestra es un sitio web basado en microservicios llamado Value Mark, que guía a los usuarios en la elección de empresas en las que invertir. Un usuario inicia sesión, el back end autentica al usuario y el navegador muestra marcos de interfaz de usuario relevantes para su función.

De forma predeterminada, Jira lanza un tablero Scrum con tres columnas predeterminadas: To Do (Por hacer) , In Progress (En progreso ) y Done (Hecho) . También hay un área de backlog (que se puede mostrar como la primera columna) donde se recopila el trabajo y luego se puede asignar a un sprint adecuado. Arrastras jiras de una columna a otra para proporcionar una visualización del estado actual del proyecto y todos sus problemas. Cada columna se asigna a un estado y cada Jira tiene un campo llamado Status (Estado). Siempre que haces la transición de un jira a una nueva columna, el campo Status de ese Jira se actualiza con el estado de la columna de destino.

Existe un rol conocido como Administrador del tablero. Los administradores del tablero tienen la capacidad de agregar, eliminar y secuenciar columnas, de acuerdo con el flujo de trabajo del proyecto .

El flujo de trabajo del proyecto, como se muestra en la Figura 3.24 , define todas las opciones de estado del proyecto y sus transiciones. Puede ver por el flujo de flechas que un problema ABIERTO puede pasar a EN PROGRESO, RESUELTO o CERRADO.

<img width="678" alt="image" src="https://github.com/user-attachments/assets/eb1219f2-5d1a-4988-b2fd-26f9f0a3539d" />

**FIGURA 3.24: Diseño de un flujo de trabajo**

Creando un Sprint
Ahora que ha creado algunos problemas de Jira, es hora de asignar el trabajo. El trabajo que el equipo debe realizar se divide en sprints. Un sprint es un período con nombre (por ejemplo, VM Sprint 4 Aug 12-Aug 23), delimitado en el tiempo (por ejemplo, dos semanas), en el que se asigna trabajo al equipo.

A partir de la pestaña de backlog en la Figura 3.25 , encontrará todos sus problemas en la parte inferior de la página, en la sección Backlog. Su primer sprint aparecerá con un nombre predeterminado y sin fechas, pero puede hacer clic en el ícono Agregar fechas para administrar el sprint. También puede crear sprints futuros, utilizando el mismo método que se muestra en la Figura 3.26 .

<img width="750" alt="image" src="https://github.com/user-attachments/assets/b4c5cd37-1019-4938-aca0-ce32ab3edb3a" />

**FIGURA 3.25: Pestaña de cartera de pedidos**

<img width="749" alt="image" src="https://github.com/user-attachments/assets/cd1245ee-fecc-4f74-92ca-66f387cdcd58" />

**FIGURA 3.26: Creación de un sprint**

Ahora que se han creado uno o más sprints, puedes arrastrar y soltar problemas en el sprint apropiado, como en la Figura 3.27 .

Una vez asignado el sprint, se puede iniciar haciendo clic en el botón Iniciar sprint en la parte superior izquierda.

<img width="746" alt="image" src="https://github.com/user-attachments/assets/be17cc1d-1859-4a1a-9f97-005d189881df" />

**FIGURA 3.27: Asignación de jiras a un sprint**

Agregar usuarios
Un administrador de proyecto puede agregar y mantener usuarios y asignar roles. Haga clic en el ícono de engranaje en la parte inferior izquierda y haga clic en Acceso. Agregue sus usuarios y asígneles un rol.

Una vez que se hayan agregado usuarios al proyecto, haga clic en Volver al proyecto a la izquierda. Ahora puede asignar usuarios a los problemas, como se muestra en la Figura 3.28 .

Agregar columnas
Para agregar, eliminar o volver a secuenciar columnas, un administrador del tablero debe hacer clic en Columnas y estados en el lado izquierdo para iniciar la pantalla de mantenimiento de columnas.

<img width="910" alt="image" src="https://github.com/user-attachments/assets/fc3568da-aaf0-446c-bd2b-a860396ff44d" />

**FIGURA 3.28: Adición de usuarios**

Haga clic en el botón Crear columna + signo en el lado derecho para agregar columnas, como en la Figura 3.29 .

<img width="912" alt="image" src="https://github.com/user-attachments/assets/fb0b09bd-a74a-474c-bc74-76306cab9119" />

**FIGURA 3.29: Adición de nuevas columnas**

Ahora el administrador del tablero puede agregar nuevas columnas, renombrar las existentes, volver a secuenciarlas y asignar un estado del flujo de trabajo a cada columna, como en la Figura 3.30 .

<img width="908" alt="image" src="https://github.com/user-attachments/assets/69fbf131-acb3-4b68-b100-6556248ba0a2" />

**FIGURA 3.30: Mantenimiento de la columna**

Uso de filtros
A medida que más y más Jiras llenan el tablero, puede resultar difícil separar los problemas. Por ejemplo, durante las reuniones de pie, los equipos pueden pasar de una persona a otra para preguntar qué logró ayer, en qué trabajará hoy y si hay algún obstáculo. Cuando llegue su turno, ¿no sería conveniente mostrar el tablero solo con sus Jiras y ocultar todos los demás? Ese es el propósito de los filtros.

Los filtros se pueden configurar para filtrar por usuarios o de hecho por cualquier otra propiedad o propiedades de tus jiras, usando JQL, como veremos en los siguientes apartados.

Viendo mis problemas
Puede ver todos sus problemas, en todos los tableros y en la lista de trabajos pendientes, seleccionando Filtros/Mis problemas abiertos según la Figura 3.31 .

Desde la misma pantalla, puede ingresar consultas en JQL haciendo clic en Cambiar a JQL.

<img width="910" alt="image" src="https://github.com/user-attachments/assets/9725ccb2-7d1b-4e2a-a42a-fdea1fb13475" />

**FIGURA 3.31: Visualización de mis problemas**

Consultas con JQL
El lenguaje de consulta de Jira ( JQL ) ofrece a cualquier usuario la posibilidad de seleccionar Jira en función de criterios de selección. Es un lenguaje sencillo: se especifican uno o más campos y valores para esos campos y una order bycláusula.

Una consulta JQL consta de una o más cláusulas de selección de campo seguidas de una order bycláusula. Las cláusulas de selección de campo están separadas por ANDo ORy se pueden agrupar mediante paréntesis.

Una cláusula de selección de campo consta de un campo seguido de un operador y un valor. Las tablas 3.2 , 3.3 y 3.4 muestran los operadores válidos.

**TABLA 3.2: Operadores de comparación**

<img width="348" alt="image" src="https://github.com/user-attachments/assets/ab46e46d-a727-47a0-b84c-ee120d650daa" />

OPERADOR	DESCRIPCIÓN
=	El valor del campo es igual al valor especificado
!=	No es igual
<	Menos que
>	Más que
<=	Menor o igual a
>=	Mayor o igual a
IN	En una lista de valores
NOT IN	No está en una lista de valores
IS	Es un valor especificado
IS NOT	No es un valor especificado
WAS	Tenía un valor específico en el pasado
WAS IN	Estaba en una lista de valores en el pasado.
WAS NOT IN	No estaba en una lista de valores en el pasado
CHANGED	El campo fue cambiado a un valor especificado
BY	El campo fue cambiado por un usuario específico
AFTER	El campo de fecha cayó después de una fecha u hora especificada
BEFORE	El campo de fecha cayó antes de una fecha u hora especificada
DURING	El campo de fecha se produjo durante un rango de fechas específico

**TABLA 3.3 :Operadores lógicos**

<img width="382" alt="image" src="https://github.com/user-attachments/assets/41159c12-4feb-4a3e-9dd7-167429c4e419" />


OPERADOR	DESCRIPCIÓN
AND	Y lógico
OR	OR lógico
NOT	NO lógico
Las cláusulas se pueden separar con las palabras clave AND, OR, y NOT. Para ordenar por uno o más campos, puede finalizar la consulta con ORDER BYy un nombre de campo. Puede controlar el orden de clasificación con ASC(predeterminado) o DESC.

**TABLA 3.4: Operadores especiales**

<img width="765" alt="image" src="https://github.com/user-attachments/assets/4764d427-1c5e-45d2-ab8f-07eaf54959f7" />

OPERADOR	DESCRIPCIÓN
EMPTY	El valor del campo está vacío.
NOT EMPTY	El valor del campo no está vacío.
NULL	El campo tiene un valor nulo.
NOT NULL	El campo no es nulo.
~	Coincide con una expresión regular.
~*	Coincide con una expresión regular, sin distinguir entre mayúsculas y minúsculas.
!~	No coincide con una expresión regular.
!~*	No coincide con una expresión regular, no distingue entre mayúsculas y minúsculas.
CURRENTUSER	Usuario actual.
currentUser	Igual que CURRENTUSER, pero sin distinguir entre mayúsculas y minúsculas.
También puede utilizar caracteres comodín ( *) para coincidencias parciales. Por ejemplo, esta consulta busca todos los jira con un resumen que comience con improvement:

summary ~* "improvement*
Puede utilizar los caracteres especiales dpara días, hhoras, etc., como se muestra en esta consulta para encontrar todos los jiras resueltos en los últimos tres días:

status = resolved AND resolved>= -3d
Los paréntesis se pueden utilizar para agrupar cláusulas y controlar a qué se aplican los operadores lógicos. Esta consulta busca los jiras en el proyecto Value Mark que se encuentran en estado Sin resolver, asignados al usuario que ha iniciado sesión actualmente, con prioridad Alta o Crítica:

project = "Value Mark" and assignee = currentUser() AND resolution = Unresolved AND priority in (High, Critical) order by updated DESC
Realizar cambios masivos
Puede modificar una selección de Jiras en función de una consulta JQL. Desde la pantalla JQL, puede hacer clic en el botón Cambio masivo y luego hacer clic en la casilla de verificación junto a cada problema que desee cambiar, como en la Figura 3.32 .

<img width="827" alt="image" src="https://github.com/user-attachments/assets/3da57064-9a47-43ce-8f8d-a64454f379cb" />

**FIGURA 3.32: Edición masiva**

Luego puede elegir editar los problemas seleccionados, moverlos a un nuevo proyecto, realizar la transición, etc., como en la Figura 3.33 y la Figura 3.34 .

<img width="907" alt="image" src="https://github.com/user-attachments/assets/b2194ff5-2495-47bb-a09e-93889a77a6a4" />

**FIGURA 3.33: Edición masiva, Elegir acción masiva**

<img width="909" alt="image" src="https://github.com/user-attachments/assets/9f0aa76e-6eac-4b6b-82ea-283b6346678c" />

**FIGURA 3.34: Edición masiva, detalles de la operación**

Conectarse a Git
Tu administrador de Jira puede conectar tu proyecto de Jira a tu proveedor de Git. Una vez que el proveedor de Git esté conectado, incluye la clave de Jira en tus mensajes de confirmación para adjuntar tu confirmación al Jira asociado.

He aquí un ejemplo:

git commit -m "Implemented credentials validation. VM-8"
Luego, podrá ver una lista de confirmaciones asociadas con cualquier Jira dentro del propio ticket de Jira.

TRABAJANDO CON CONFLUENCE, EL SISTEMA DE GESTIÓN DEL CONOCIMIENTO EMPRESARIAL
Hemos hablado sobre cómo colaborar con código usando Git y cómo colaborar en procesos usando Jira. Terminaremos nuestro capítulo sobre colaboración con un análisis de Atlassian Confluence, la popular herramienta de documentación.

Confluence es una encarnación omnipresente del concepto wiki, una herramienta genérica para compartir conocimientos. Aunque existen otras marcas de wiki que también son populares en el ámbito empresarial, son similares y elegimos Confluence, por ser una de las más extendidas.

Cada equipo tiene una misión declarada, que puede incluir su propósito, las tecnologías y procesos subyacentes, cómo se estructuran los equipos, el intercambio de conocimientos generales, etc.

Confluence representa la culminación de la evolución de las herramientas wiki a lo largo de los años. Incluye funciones wiki estándar, como la posibilidad de que varias personas editen al mismo tiempo, la visualización del historial de versiones y una impresionante colección de macros para funciones como tablas e imágenes.

Estos son algunos de los tipos de páginas compatibles con Confluence de manera predeterminada:

Página de documentación: se utiliza para crear documentación. Como todas las páginas, puede incluir encabezados, viñetas, listas numeradas, tablas y otros estilos que esperaría encontrar en la documentación técnica.
Notas de la reunión: diseñado específicamente para capturar actas de reuniones y cosas como elementos de acción, así como otra información discutida durante las reuniones.
Entrada de blog: generalmente se utiliza para aportar ideas informales en un formato similar a un blog.
Página en blanco: una página vacía donde puedes crear contenido utilizando las herramientas de edición de Confluence.
Para crear su propia versión en la nube de Confluence, diríjase a https://www.atlassian.com/software/confluence.

Confluence se divide en espacios que representan a los equipos. Los espacios pueden tener permisos para determinar quién puede ver, editar y crear páginas dentro de un espacio. Dentro de un espacio, las páginas individuales pueden tener restricciones más granulares, por lo que, por ejemplo, si estás colaborando en una página pero aún no estás listo para compartirla, puedes otorgar permisos solo al grupo de trabajo de la página y restringir a todos los demás.

Para crear una página nueva, haga clic en el botón Crear y seleccione una plantilla adecuada. Déle un título a la página y, a continuación, pase la tecla Tab o haga clic en el marco de contenido que se encuentra debajo del título.

Ahora puede escribir libremente en el marco de contenido o puede presionar la tecla / para seleccionar entre las muchas opciones, como Imagen, Tabla o Fragmento de código. Si otra persona está editando al mismo tiempo que usted, Confluence mostrará una pequeña bandera con sus iniciales, que marcará su ubicación.

Para insertar una imagen, puede arrastrar y soltar un archivo de imagen desde el sistema de archivos a su página de Confluence, o puede copiar y pegar imágenes desde el portapapeles, o puede hacer clic en / y seleccionar Imagen, Video o Archivo y luego seleccionar el archivo de imagen.

Puede cambiar el tamaño de la imagen arrastrando y soltando los bordes. Al hacer clic en la imagen, aparecen opciones de edición adicionales debajo de la imagen, como bordes, alineación de la imagen, etc. La figura 3.35 muestra cómo insertar una imagen.

Seleccione Tabla para insertar una nueva tabla. Puede seleccionar una celda, varias celdas, filas enteras, columnas enteras o la tabla completa. Cuando realiza una selección, aparece una pequeña flecha en la parte superior derecha de una celda. Haga clic en la flecha para abrir un menú contextual con opciones para cambiar el fondo o agregar o eliminar filas o columnas. La Figura 3.36 muestra cómo insertar una tabla.

<img width="912" alt="image" src="https://github.com/user-attachments/assets/215d8fbb-9cba-4ca6-9132-5ea77d93872a" />

**FIGURA 3.35: Inserción de una imagen**

<img width="908" alt="image" src="https://github.com/user-attachments/assets/449d956c-6f43-49bd-9c5b-a2e946bca314" />

**FIGURA 3.36: Inserción de una tabla**

La Tabla 3.5 muestra algunas macros útiles para que puedas hacerte una idea de su funcionalidad. Puedes experimentar con ellas cuando quieras.

A medida que use Confluence, aprenderá optimizaciones divertidas como escribir {note} para crear un cuadro de nota o pegar una URL de Jira para conectar automáticamente el ticket a la página, incluido el estado en el momento de la representación de la página.

**TABLA 3.5: Macros de Confluence seleccionadas**

<img width="904" alt="image" src="https://github.com/user-attachments/assets/2d5fefd5-883e-415b-a2e3-662273311ffe" />

OPERADOR	DESCRIPCIÓN
Mesa	Crea una tabla
Fragmento de código	Crea código formateado
Panel de notas/sugerencias/éxito/advertencia/error	Crea texto con un icono apropiado para marcar la atención.
Título 1, 2, 3, etc.	Crea un esquema
Tabla de contenido	Muestra los encabezados en una tabla de contenido para la navegación.
Expandir	Muestra un enlace que se puede expandir para mostrar más detalles.
Sobresalir	Incorpora una pestaña de hoja de cálculo
REFERENCIAS ADICIONALES
https://git-scm.com/docs
Documentación de referencia completa de Git

https://nvie.com/posts/a-successful-git-branching-model
Artículo original de Gitflow de Vincent Driessen

https://www.atlassian.com/software/jira
Documentación de Jira

https://www.atlassian.com/software/confluence
Documentación de Confluence

## RESUMEN

En este capítulo, analizamos algunas de las herramientas más utilizadas para la colaboración empresarial.

* Git para la colaboración de código
* Jira para la colaboración en procesos
* Confluence para la gestión del conocimiento empresarial
