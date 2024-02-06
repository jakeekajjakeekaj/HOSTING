Para este caso, se abarcarán mayormente lo que son conceptos.

--

TIPOS DE HOSTING:

- HOTING COMPARTIDO: Un solo servidor, tiene muchas páginas web, compartiendo sus recursos; ideal para tienda en linea pequeña o página web personal, algo que tenga poco tráfico

- VPS: Hace lo mismo que el hosting compartido, sin embargo separa al mismo servidor como en múltiples partes, es decir que aunque comparten las características a nivel hardware, se separan como si fueran servidores diferentes; garantiza que el rendimiento de uno, no se vea afectado por otro, ya que en el caso anterior si uno consumía muchos recursos, el rendimiento se iba a ver afectado para los demás, mientras que en este caso ya no sería así; es como si fuera una mpaquina virtual al final; ideal para empresas medianas que lleven un poco más de tráfico o que requieran ejecutar un determinado tipo de aplicación con necesidad específica

- Hosting dedicado: Esto lo que realiza es que se ocupa un servidor entero para tu alojamiento; ideal para páginas web grandes que mueven muchos datos

- Cloud Hosting: Utiliza una red entera de servidores para poder usarse, esto ya sería para cosas que necesitan demasiado fluijo de datos, por ejemplo en el black friday que puede haber mucho tránsito de información, pues estos son ideales para eso

--

CÓMO ELEGIR UN PLAN ADECUADO PARA EL PROYECTO

- Para la mayoría de los casos un hosting compratido basta, ya sea como páginas de restaurantes o ese tipo de cosas; ya si se preveé un mayor servicio con un gran tráfico de gente, la mejor opción debería ser un hosting dedicado o un cloud hosting

--

CÓMO ELEGIR EL PROVEEDOR DE HOSTING

- Tiene que tener soporte 24/7
- ALto rendimiento
- Confiabilidad
- Diversidad y Flexibilidad (poder avanzar cambiando de planes que sea de manera sencilla)

--

* Es necesario indicar que de vez en cuando al realizarse cambios dentro de nuestra página web, la información puede llegar a quedar guardada en el caché, como es el caso de por ejemplo hostinger, y esta se debe eliminar, para esto se puede limiar presionando shift + f5 ó ctrl + shift + r

* Se puede subir la página web desde un administrador de archivos, sin embargo existe algo llamado:

-- FTP

El FTP ayuda a subir tu página de manera remota, es bastante usado.
File Transfer Protocol, y básicamente transfiere los archivos desde la computadora hacia un servidor, sus componentes son:
- Cliente FTP: Se puede ver como un software que se puede instalar en la computadora y se encarga de comunicarse con nuestro servidor, el más famoso vendría siendo "File Zilla"
- Servidor FTP: Esta sería la otra punta de la ocnexión y es donde se encuentran alojados los archivos de la página web
- Credenciales: Estas serían las de acceso y se necesita un nombre se usuario y una contraseña, estas credenciales las suele otorgar el proveedor de hosting

La ventaja de trabajar de esta manera, es que los archivos se pueden ver como si fueran de nuestra computadora de forma nativa, de esta manera no hay necesidad de entrar a la página web del hosting desde nuestro navegador.
Existen 2 tipos de FTP con su respectiva seguridad:
- FTP Puro: Es el más básico y no es seguro ya que el protocolo intenta transmitir la información entre 2 partes, pero no se encuentra cifrado, es decir que al comunicación cliente servidor no se encuentra cifrada
- SFTP: Esto sería FTP + SSH
- FTPS: Esto sería FTP + SSL Estos son los seguros y se encargan de proteger las credenciales y cifrar la información

Pasos: 
(Suponiendo que se quiere conectar a Hostinger)
1. Descarga FileZilla
2. Descarga el FileZilla CLiente
3. Se puede elegir cualquier plan, sin embargo el primero es más que suficiente
4. Finalizar Instalación
5. Desde Hostinger seleccionar archivos/cuenta FTP
6. Se cambia la contraseña de FTP
7. Se copia la IP del FTP desde hostinger y se pega en la sección de servidor de FileZilla
8. Se copia el Nombre de Usuario desde hostinger y se pega en la sección de Nombre de Usuario de FileZilla
9. Se coloca la contraseña en FileZilla
10. Se indica el puerto, para el caso del video es el 21
11. Se hace click en conexión rápida, no guardar contraseñas y aceptar
12. Si todo salió correcto, ya se debería de poder visualizar los archivos
13. Una vez finalziado esto, si nosotros nos dirigimos a "gestor de sitios", podemos agregar un sitio, y en las opciones seleccionamos que queremos SFTP en vez de FTP, se copia el servidor, usurario, dejar en preguntar la contraseña para que no se quede almacenada y existan errores de seguridad. Aceptamos todo, conectamos y escribimos la contraseña

-- BASES DE DATOS

Una base de datos sencilla de crear para el sitio web sería una base mysql, se tiene un código con la información de la tabla, de esta manera nosotros podemos hacer conexiones con lo que sería FTP; no se deben tener lineas para eliminar o crear cualquir base de datos, tampoco debe tener ocmandos que requieran privilegios super, no deben de haber lineas con procedure, definer o trider.

Dentro de Hostinger nos dirigimos a la sección de bases de datos, y escribimos el nombre de la base de datos mysql y el nombre del usuario mysql con una contraseña, se selecciona crear y ya nos aparece en la zona inferior a la base de datos; si seleccionamos esto nos abre la interfaz de php myAdmin, una vez que se tenga esto, se crea la base de datos, o si ya se tiene en forma de código de manera local, nos dirigimos a importa y lo importamos

Si nos dirigimos a la sección de avanzado/configuración de PHP lo dejamos de la siguiente manera:
- allowUrlFopen: SI
- exposePhp: SI
- logErrors: NO
- session.useStrictMode: NO
- shortOpenTag: NO  Acorta las etiquetas de PHP
- displayErrors: NO Muestra los errores en pantalla, la desventaja es que tiende a revelar información del código provocando inseguridades
- fileUploads: SI
- session.cookieSecure: NO  Es para mostrar si las cookies se muetran a través de conexiones seguras
- session.cookieHttponly: NO
- zlib.outputCompression: NO

--  Instalar WORDPRESS con el plus de la IA (opcinal, solo para mas conocimiento)

Si dentro de hostinger nos dirigimos a la sección de auto instalador, nos dirigimos a wordpress.
Dentro del histing/núcleo, habilitamos Forzar https para que siempre nos diriga al https

-- SSH y CRON JOBS

Debemos descargar PUTTY, esta ya viene instalada en LINUX y MAC, pero no en WINDOWS, es por esto que si se tiene WINDOWS debemos instalarla.

Nos dirigimos a Hostinger/avanzado/Acceso SSH habilitamos SSH desde hostinger y abrimos PUTTY, posterior a esto copiamos el HostName para pegarlo dentro de PUTTY, después copiamos el puerto y lo pegamos en la sección del puerto, le damos en OPEN y se nos abrirá como una terminal, dentro de esta debemos copiar y pegar el usuario; así mismo se debe generar la contraseña en hostinger para escribirla en PUTTY.
- Dentro se puede escribir pwd para obtener la ruta actual, ESTA RUTA SIRVE PARA LOS CRON JOBS, los cuales son tareas automatizadas.
Un ejemplo de los CRON JOBS, es que son tareas que se programan para que pasen en determinado tiempo, ejemplo: YT suele pagarle a sus creadores, sin embargo no te dice en tiempo real cuánto van generando, la información la tienen, sin embargo esta no la van actualizando cada segundo, por su contra parte tienen CRON JOBS que se ejecutan a las 00:00 UTC para que así ahora sí se refleje el pago a los creadores.

-- Aumentar la seguridad dentro de las páginas web

Los 4 ataques más comunes dentro de la creación de páginas web son:
- MALWARE: Es software malicioso que se mete dentro de la página web con la intención de robar datos o distribuir malware a nuestros usuarios
- INYECCIÓN SQL: Se hace lo posible para ejecutar consultas que no deberían sr posible ejecutarse para un usuario y de esta manera visualizar, eliminar, modificar información de nuestra base
- DDOS: Solicitudes generadas en enorme cantidad
- LIBERACIÓN DE DATOS: Se intenta acceder a la información como lo que son las credenciales de acceso

Para umentar la seguridad ante estos atques se tiene:
- SSL: Cifra la información que viaja entre el navegador web y el usuario, como dato curioso los SSL se tiene que estar cambiando contantemente, sin embargo en servicios de hosting como Hostinger, ellos los van cambiando sin que nosotros tengamos que hacr ninguna acción.

- WAF (FIREWALL DE APLICACIONES): Filtran y supervisan el tráfico entre una aplicación e internet, así mismo las colitudes sospechosas las bloquea y genera alertas para que el administrador las pueda visualizar (inyección sql, xcss, crossites victim, CRF)

- Existen como antivirus para las páginas web

- Plugins para seguridad con los CMS

Cosas menos técnicas, pero que son buenas prácticas a realizar:

- Mantenimiento regular: Mantener actualizado el software ya que de estar desactualizado muchos ataques se pueden aprovechar de las vulnerabilidades del software desactualizado (CMS puede configurar versiones automáticas)

- Contraseñas seguras y gestión de accesos: Respetar contraseñas con caracteres especiales y longitudes

- Autenticación en 2 pasos

- Regulares copias de seguridad

- Tomar un curso de ciberseguridad

* Se puede activar el ESTADO DE SEGURIDAD, (al menos en lo que es Hostinger de manera simple), y de esta manera salen las preguntas de "desmuestra que no eres un robot", esto no es recomendable tenerlo siempre activo ya que aruina la UX, pero si se esperan ciertos ataques es bueno activarlo durante un tiempo, o si recitneemnte se fue atacado es bueno tenerlo activo durante un tiempo y posteriormente desactivarlo

* Se pueden bloquear IP

* Se puede solicitar el acceso para cierto apartado

* Hotling, sirve para no mandar a llmar las imagenes de nuestro sitio a otro sitio, esto ayuda al ancho de banda, ya que cada que se cargue la imagen comienza a consumir nuestro recurso, sin embargo si se hace esto se pierde posicionamiento ya que se pierde la oportunidad de que otro sitio mencione nuestros complementos de nuestra página web, por lo que se debe encontrar un equilibrio, algo que se podría hacer es no prmitir que las páginas llamen nuestros formatos de video (.avi, .mov, .mpeg, etc)

-- OPTIMIZACIÓN

- CDN: Distribuyen copias de contenido en diferentes servidores. Aparte de la ventaja de estar en múltiples servidores, también se guarda en caché la información.
Dentro de Hostigner se puede visualizar la optimiación, y esto sería:
Hits: La información recuprada del caché
Miss: La información no obtenida del cachpe y que se tuvo que acceder al servidor
Dinámico: La información que no puede ser almacenada en caché ya que se encuentra cambiando
Bypass: Está hecho para saltarse el caché
Revalidated: Solicitudes que se deben de hacer del servidor al caché para verificar que la infroamción se encuentre actualizada

- BLOQUEAR PAISES QUE QUIERAN ENTRAR A TU PÁGINA WEB, LA RAZÓN DE ESTO ES QUE ES INSERVIBLE QUE ESTOS PAISES TENGAN ACCESO  NUESTRA PÁGINA WEB