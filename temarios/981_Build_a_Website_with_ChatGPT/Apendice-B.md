# Apéndice B. Implementación de su sitio
No estoy revelando ningún gran secreto ni promoviendo ningún conocimiento esotérico cuando digo que la característica clave de un sitio web es la parte "web" de la palabra. Es decir, aunque eres libre de crear y previsualizar tantos archivos HTML como quieras en tu computadora, esos archivos no suman para formar un sitio web genuino hasta que se implementan en la web para que tus amigos, familiares e incluso completos desconocidos los vean. Llevar HTML, CSS, JavaScript, imágenes y otros archivos desde tu computadora a un servidor web se conoce como implementar tu sitio.

La gran noticia sobre los tipos de sitios web que aprenderá a crear en este libro (es decir, sitios web que utilizan únicamente archivos HTML estáticos que no requieren acceso a un servidor web completo) es que la simplicidad de estos archivos significa que existen proveedores de alojamiento web que implementarán su sitio de forma gratuita. Estos sitios obtienen su dinero de grandes corporaciones y desarrolladores web profesionales, por lo que no les supone ningún esfuerzo alojar un sitio web personal básico. En este apéndice, aprenderá a implementar su sitio web en dos de estos proveedores de alojamiento web: Netlify y Cloudflare. Por si fuera poco, también le daré instrucciones generales para implementar sus archivos en otros proveedores de alojamiento web.

B.1 Implementación en Netlify
Netlify es una empresa que ofrece a las grandes empresas y a los desarrolladores profesionales una plataforma de desarrollo basada en la nube para crear e implementar aplicaciones web. Afortunadamente, Netlify también apoya a particulares y aficionados al ofrecer un nivel gratuito que permite a cualquiera crear una o tres páginas sin problemas. Las únicas restricciones son que está limitado a un máximo de 500 sitios web y 100 GB de ancho de banda. ( El ancho de banda es la cantidad de datos por mes que sus sitios transfieren a los navegadores web. Y 100 GB es mucho ancho de banda).

B.1.1 Configuración de una cuenta Netlify
Para empezar a utilizar Netlify, necesitas una cuenta. Estos son los pasos a seguir:

Envía tu navegador web favorito a https://netlify.com .

Haga clic en Registrarse.

Haga clic en Registrarse con correo electrónico.

Escribe tu dirección de correo electrónico, escribe la contraseña que deseas utilizar y haz clic en Registrarse. Netlify envía un mensaje de verificación a tu dirección de correo electrónico.

Abra su aplicación de correo electrónico, haga clic en el mensaje de verificación de Netlify y luego en el enlace de verificación. Netlify verifica su cuenta y luego muestra una serie de preguntas.

Ejecute las preguntas, haga clic en Continuar con la implementación y luego haga clic en Omitir este paso por ahora.

Netlify te lleva a la página de descripción general del equipo. Desde aquí, puedes cargar tus archivos mediante uno de dos métodos: arrastrar y soltar o un cuadro de diálogo. Las siguientes dos secciones te guiarán por ambos métodos.

B.1.2 Subir sus archivos mediante arrastrar y soltar
Por lo general, la forma más rápida de llevar los archivos de su sitio web a Netlify es usar el mouse para arrastrar la carpeta del sitio web al área de carga. Estos son los pasos a seguir:

   1. En su computadora, abra el Explorador de archivos (Windows) o Finder (macOS).

   2. Navegue hasta la carpeta que contiene la subcarpeta que desea cargar.

   3. Inicie sesión en Netlify (si aún no lo ha hecho) y haga clic en Sitios en la barra lateral izquierda.

   4. Organice la ventana del navegador y la ventana del Explorador de archivos (o Finder) de modo que queden una al lado de la otra (o al menos de modo que pueda ver el área de carga en el navegador y la subcarpeta que desea cargar en el Explorador de archivos o Finder).

   5. Arrastre la subcarpeta desde el Explorador de archivos (o Finder), mueva el puntero del mouse hacia la ventana del navegador y sobre el área de carga (como se muestra en la figura B.1) y suelte la subcarpeta. Netlify carga la subcarpeta y su contenido y luego implementa el sitio.



Figura B.1 Arrastre la carpeta del sitio web al área de carga de Netlify.

   6. En el cuadro de diálogo ¡Implementación exitosa! (que se muestra en la figura B.2), haga clic en Comenzar. Netlify muestra la página de descripción general de su cuenta.



La Figura B.2 Netlify muestra el cuadro de diálogo ¡Implementación exitosa! una vez que se haya implementado su sitio web.

   7. En la sección Sitios de la página, haz clic en tu nuevo sitio. Netlify muestra la página Descripción general del sitio.

   8. Haga clic en el enlace para ver el sitio implementado en el navegador web.

B.1.3 Cargar sus archivos mediante un cuadro de diálogo
El método de arrastrar y soltar no es ideal si tienes una pantalla relativamente pequeña o si no tienes la habilidad necesaria con el mouse. No hay problema, porque Netlify también te permite cargar la carpeta de tu sitio web mediante un cuadro de diálogo. Estos son los pasos a seguir:

Inicie sesión en Netlify (si aún no lo ha hecho) y haga clic en Sitios en la barra lateral izquierda.

Haga clic en Explorar para cargar.

En el cuadro de diálogo que aparece, seleccione la carpeta del proyecto y luego haga clic en Cargar.

Si su navegador web le solicita que confirme la operación, haga clic en Cargar. Netlify cargará la subcarpeta y su contenido.

En el cuadro de diálogo ¡Implementación exitosa!, haga clic en Comenzar. Netlify muestra la página de descripción general de su cuenta.

En la sección Sitios de la página, haz clic en tu nuevo sitio. Netlify muestra la página Descripción general del sitio.

Haga clic en el enlace para ver el sitio implementado en el navegador web.

B.1.4 Cambiar el subdominio o nombre de dominio de su sitio
De forma predeterminada, Netlify le otorga a su sitio web implementado un nombre de dominio personalizado con el formato wacky-name-a1b2c3 .netlify.app (la figura B.3 muestra un ejemplo). El nombre de su sitio se puede ver en la página Descripción general del sitio. Para acceder a ella desde cualquier página de Netlify, haga clic en Sitios en la barra lateral izquierda y luego haga clic en el sitio.



Figura B.3 La página Descripción general del sitio muestra el nombre que Netlify asignó a su sitio.

Es posible que le guste el nombre extraño proporcionado aleatoriamente por Netlify, pero si prefiere un nombre de dominio que refleje el contenido de su sitio, debe utilizar uno de los siguientes métodos para cambiar el nombre de dominio:

Cambiar el nombre del subdominio : si desea conservar el nombre de dominio netlify.app y solo cambiar el subdominio (la parte wacky-name-a1b2c3), abra la página Descripción general del sitio, haga clic en Configuración del dominio, haga clic en Opciones en la sección Dominios de producción y luego haga clic en Editar nombre del sitio. Escriba el subdominio que prefiera y luego haga clic en Guardar. Si Netlify le indica que el nombre del sitio ya está en uso, intente nuevamente con un nombre diferente.

Cambiar el nombre de dominio : si ya tiene un nombre de dominio o desea comprar uno nuevo con Netlify, abra la página Descripción general del sitio, haga clic en Configuración de dominio y, luego, haga clic en Agregar un dominio en la sección Dominios de producción. Escriba su dominio existente o nuevo, haga clic en Verificar y, luego, siga las instrucciones que aparecen.

B.2 Implementación en Cloudflare
Cloudflare es más conocida como una empresa de redes que se especializa en ayudar a sitios web grandes a evitar o salir airosos de ciberataques, como ataques de denegación de servicio distribuido (DDOS) que bombardean un sitio web con cantidades masivas de datos basura. Pero Cloudflare también ofrece alojamiento web a través de un servicio llamado Pages. Este servicio está aparentemente dirigido a desarrolladores web, pero también está disponible para personas como tú y yo. Lo mejor de todo es que una cuenta de Pages es gratuita y no ofrece restricciones en cuanto a la cantidad de sitios y la cantidad de ancho de banda que utilizan.

B.2.1 Configuración de una cuenta de Cloudflare Pages
Para comenzar a utilizar Cloudflare Pages, primero debe seguir estos pasos para configurar una cuenta:

Vaya a https://pages.cloudflare.com .

Haga clic en Registrarse.

Escribe tu dirección de correo electrónico, escribe la contraseña que deseas utilizar y haz clic en Registrarse. Cloudflare envía un correo electrónico de verificación a tu dirección de correo electrónico.

Abra su aplicación de correo electrónico, haga clic en el mensaje de verificación de Cloudflare y haga clic en el enlace de verificación.

Cloudflare verifica tu cuenta y luego muestra tu panel de control de Cloudflare. Estás listo para crear una nueva aplicación de Cloudflare para tu sitio web, como se describe en la siguiente sección.

B.2.2 Creación de una nueva aplicación de Cloudflare
En Cloudflare, un sitio web de Pages se denomina aplicación y se implementa como parte de la función Pages de Cloudflare. Para comenzar la implementación, cree una nueva aplicación Pages, como se describe en los siguientes pasos:

   1. Inicie sesión en Cloudflare si aún no lo ha hecho.

   2. En el menú de navegación de la izquierda, en Trabajadores y páginas, haga clic en Descripción general. Aparecerá la página Descripción general. Si aún no ha implementado un proyecto de páginas, salte al paso 4; de lo contrario, continúe con el paso 3.

   3. Haga clic en el botón Crear aplicación, que se muestra en la figura B.4. Aparecerá la página Crear una aplicación.



Figura B.4 En la página Descripción general de trabajadores y páginas de Cloudflare, haga clic en Crear aplicación.

   4. Haga clic en la pestaña Páginas, como se muestra en la figura B.5.



Figura B.5 En la página Crear una aplicación, haga clic en la pestaña Páginas.

   5. Desplácese hacia abajo hasta la sección Crear mediante carga directa y, a continuación, haga clic en Cargar activos (consulte la figura B.6). Aparecerá la página Implementar un sitio mediante la carga de su proyecto.



Figura B.6 Haga clic en Cargar activos.

   6. Escriba un nombre para su proyecto y luego haga clic en Crear proyecto (consulte la figura B.7). Cuando su proyecto esté listo (tarda unos minutos), Cloudflare mostrará un área de carga.



Figura B.7 Nombre su proyecto y luego haga clic en Crear proyecto.

Desde aquí, puede cargar sus archivos mediante uno de dos métodos: arrastrar y soltar o un cuadro de diálogo. Las siguientes dos secciones lo guiarán a través degh ambos métodos.

B.2.3 Carga de sus archivos mediante arrastrar y soltar
A menudo, la forma más sencilla de pasar los archivos de su ordenador a Cloudflare es utilizar el ratón para arrastrar la carpeta del sitio web hasta el área de carga. Estos son los pasos a seguir:

   1. En su computadora, abra el Explorador de archivos (Windows) o Finder (macOS).

   2. Navegue hasta la carpeta que contiene la subcarpeta que desea cargar.

   3. Organice la ventana del navegador y la ventana del Explorador de archivos (o Finder) de modo que queden una al lado de la otra (o al menos de modo que pueda ver el área de carga en el navegador y la subcarpeta que desea cargar en el Explorador de archivos o Finder).

   4. Arrastre la subcarpeta desde el Explorador de archivos (o Finder), mueva el puntero del mouse hacia la ventana del navegador y sobre el área de carga, y luego suelte la subcarpeta. Cloudflare cargará la subcarpeta y su contenido.

El paso final es implementar el sitio, como se describe en la sección B.2.5.

B.2.4 Cargar sus archivos mediante un cuadro de diálogo
Si trabaja con una pantalla pequeña o no sabe usar el mouse, es posible que prefiera cargar sus archivos a Cloudflare mediante un cuadro de diálogo. A continuación, le indicamos cómo hacerlo:

   1. En el área de carga de Cloudflare, haga clic en Seleccionar desde la computadora.

   2. Haga clic en Cargar carpeta.

   3. En el cuadro de diálogo que aparece, seleccione la carpeta del proyecto, como se muestra en la figura B.8, yLuego haga clic en Cargar.



Figura B.8 Seleccione la carpeta del sitio web.

   4. Si su navegador web le solicita que confirme la operación, haga clic en Cargar. Cloudflare cargará la subcarpeta y su contenido.

El paso final es implementar el sitio, como se describe en la siguiente sección.

B.2.5 Implementación del sitio
Una vez cargados los archivos, ya está listo para implementar el nuevo sitio. Para ello, haga clic en el botón Implementar sitio. Cloudflare implementa el sitio y, a continuación, muestra el mensaje ¡Éxito!, como se muestra en la figura B.9. Haga clic en el vínculo para ver el sitio implementado en el navegador web.



Figura B.9 Cloudflare muestra el mensaje ¡Éxito! cuando se implementa su sitio.

B.2.6 Cambiar el nombre de dominio de su sitio
Cloudflare le otorga a su sitio web implementado un nombre de dominio personalizado con el formato nombre-de-carpeta - a1b2 .pages.dev (donde nombre-de-carpeta proviene del nombre de la carpeta del sitio web que cargó). Puede cambiar este nombre por su propio nombre de dominio de la siguiente manera:

Nombre de dominio adquirido en Cloudflare : en la barra lateral izquierda, haz clic en Registro de dominio, luego en Registrar dominios, escribe el nuevo nombre de dominio que deseas usar, haz clic en Buscar y luego sigue las instrucciones. Una vez que hayas completado la compra, sigue las instrucciones del siguiente punto para asignar el nuevo dominio a un sitio web de Pages.

Nombre de dominio que ya posee : en la página Descripción general de Worker & Pages, haga clic en el sitio web con el que desea trabajar, haga clic en la pestaña Dominios personalizados, haga clic en Configurar un dominio personalizado, escriba el nombre de dominio que posee (si compró un dominio con Cloudflare, escriba ese nombre de dominio), haga clic en Continuar y luego siga las instrucciones.

B.3 Implementación en otros servidores web
Otros servicios pueden alojar su sitio web; almacenan sus archivos en una computadora especial llamada servidor web , que acepta y responde a las solicitudes del navegador web para la página y sus archivos asociados. Para utilizar un servicio de este tipo, debe registrarse en uno que ofrezca espacio en su servidor. Debido a que el servicio en realidad aloja sus archivos, se lo denomina proveedor de alojamiento web o host web .

B.3.1 Qué buscar en un proveedor de alojamiento web
¿Qué criterios deberías utilizar al evaluar un proveedor de alojamiento web? La respuesta depende del tipo de sitio web que quieras crear, pero los siguientes criterios son los más comunes:

Ancho de banda máximo : la cantidad máxima de datos que el servidor transferirá por mes a los navegadores web. En la mayoría de los casos, deberá pagar un adicional por los datos que excedan el máximo mensual. Algunos servidores web ofrecen ancho de banda ilimitado.

Espacio total en disco : la cantidad de espacio de almacenamiento en disco duro que obtiene en el servidor web. Como mínimo, el espacio total en disco suele ser de unos pocos cientos de megabytes, lo cual es más que suficiente para un sitio simple.

Número de sitios web : la cantidad de carpetas raíz que puede configurar.

Número de direcciones de correo electrónico : la cantidad de direcciones de correo electrónico incluidas con el servicio de alojamiento.

Alojamiento de nombres de dominio : si el servidor web también aloja nombres de dominio que hayas comprado previamente a un registrador de nombres de dominio. Algunos servidores venden nombres de dominio y otros ofrecen nombres de subdominio gratuitos con el formato yourdomain . webhostdomain .com.

Compatibilidad con FTP : compatibilidad con el protocolo de transferencia de archivos (FTP), que es el servicio de Internet que utiliza para transferir sus archivos al servidor web. Casi todos los servidores web admiten FTP, pero algunos solo ofrecen servicios de transferencia de archivos exclusivos.

Por regla general, cuanto más barato sea el proveedor de alojamiento web, menos de estas funciones tendrás. Antes de empezar a buscar un proveedor de alojamiento web, haz una lista de estas funciones y decide qué necesitas y qué es opcional. Esto puede resultar difícil en el caso de algo como el ancho de banda máximo, ya que el ancho de banda se determina en parte por la popularidad de tu sitio, pero haz lo posible por conseguir cada una de ellas por ahora. Cuando busques un proveedor de alojamiento web, tienes tres opciones principales:

Su proveedor de servicios de Internet (ISP): la empresa o institución que utiliza para acceder a Internet también puede ofrecer un servicio de alojamiento web. Muchos ISP ofrecen alojamiento web gratuito para sitios web personales sencillos, y algunas redes de organizaciones incluyen un servidor web que puede utilizar. En la mayoría de los casos, el alojamiento incluye características como ancho de banda y espacio en disco en el extremo inferior de la escala.

Proveedor de alojamiento web gratuito: muchos servicios alojarán sus páginas web sin cargo. El problema es que, por lo general, tendrá restricciones bastante severas en la mayoría de las funciones de alojamiento, en particular el ancho de banda y el espacio en disco, y casi siempre obtendrá un solo sitio web. Algunos proveedores de alojamiento web gratuitos también muestran anuncios, aunque esto es cada vez menos frecuente en estos días.

Proveedor de alojamiento web comercial : si desea un conjunto razonable de funciones para su presencia en la web, debe desembolsar dinero para alquilar espacio con un proveedor de alojamiento web comercial. Tenga en cuenta que no estoy hablando de mucho dinero. Los proveedores populares como Bluehost ( www.bluehost.com ), GoDaddy ( www.godaddy.com ) y HostGator ( www.hostgator.com ) ofrecen alojamiento repleto de funciones, generalmente por menos de $5 por mes. Si cree que se dedicará al diseño web más allá de crear una página de inicio básica, debería considerar un proveedor de alojamiento web comercial.

Cuando te registras en un proveedor de alojamiento web, normalmente tarda entre unos minutos y unas horas hasta que todo está listo. Cuando tu servicio de alojamiento esté listo, será el momento de poner tu contenido en línea.

B.3.2 Subir sus archivos
Una vez que haya codificado y validado sus archivos HTML y CSS, los archivos de soporte (como las imágenes) estén en su lugar, las carpetas configuradas y su servidor web esté listo para ofrecer su contenido a un mundo que lo espera, todo lo que queda es enviar sus archivos desde su computadora al servidor del servidor web, un proceso conocido como carga . La forma en que carga sus archivos depende del servidor web, pero los tres métodos siguientes son, con diferencia, los más comunes:

FTP : la mayoría de los servidores ofrecen soporte para cargas FTP. Primero, necesitas conseguir un cliente FTP , que es un programa de software que se conecta al servidor FTP de tu servidor web y ofrece una interfaz para tareas básicas de archivos, como navegar y crear carpetas, cargar archivos y eliminar y renombrar archivos. Los clientes populares de Windows son CuteFTP ( www.globalscape.com/cuteftp ) y Cyberduck ( https://cyberduck.io ). Para Mac, prueba Transmit ( https://panic.com/transmit ) o ​​FileZilla ( https://filezilla-project.org ). Cuando hayas descargado el software, consulta las páginas de soporte de tu servidor web para obtener información sobre cómo conectarte al servidor FTP del servidor.

cPanel : muchos proveedores de alojamiento web ofrecen una herramienta de administración llamada cPanel que presenta una interfaz sencilla para tareas de alojamiento como la gestión de correo electrónico y dominio. cPanel también ofrece un componente de Administrador de archivos que puede utilizar para cargar archivos y realizar otras tareas de administración de archivos.

Propietario : algunos servidores web ofrecen su propia interfaz para cargar y trabajar con archivos. Consulta la página de soporte de tu servidor para obtener instrucciones.

Cualquiera sea el método disponible, cargue todos los archivos y carpetas de su sitio web en la carpeta raíz de su servidor. Luego, cargue su sitio en su navegador web favorito para asegurarse de que todo funcione correctamente. No estaría de más probar su sitio en varios navegadores y dispositivos diferentes para asegurarse de que funcione correctamente para una amplia variedad de usuarios.
