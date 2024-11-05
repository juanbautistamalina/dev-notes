# Meta Front-End Developer

# Curso 1: Introducción al desarrollo front-end

## Cómo funciona la web

### ¿Qué es un servidor web y cómo funciona?

- **Red**: Cuando dos dispositivos se conectan y se comunican a través de una conexión con cable o inalámbrica, forman lo que se denomina una red.
- **Modelo Cliente-Servidor**: Cuando se utilizan sitios web o servicios de streaming de video en Internet, estos son proporcionados por computadoras llamadas **Servidores**. Nuestros dispositivos (los que acceden a internet) se conocen como **Clientes**.
- **Servidor**: Es un ordenador que ejecuta aplicaciones y servicios. Se llama servidor porque proporciona un servicio a otro ordenador, y su usuario se conoce como cliente.
- **Servidor Web**: Estos servidores tienen muchas funciones que incluyen almacenamiento del sitio web, administración, almacenamiento de datos, seguridad y gestión del correo electrónico. Otra de sus funciones principales es manejar lo que se conoce como solicitud web (**web request**)

### ¿Qué son los sitios y las páginas web?

- **Página Web**: Es un documento que muestra imágenes, textos, videos y otros contenidos en el navegador web. En su forma más básica, una página web es un documento de texto
- **Sitio Web**: Es una colección de páginas web que se enlazan entre sí.
- Cuando se envía una copia de una página web, desde el servidor web hacia un navegador, cada línea de código se procesa en orden secuencial del primero al último. A medida que se interpreta cada línea, el navegador crea los bloques de construcción que son la representación visual que pueden verse en pantalla. Este proceso de creación se conoce como Representación de páginas (**Page Rendering**).

### ¿Qué es un navegador web y cómo funciona?

- **Navegador Web**: Es una aplicación de software que se utiliza para navegar por la World Wide Web (WWW). Su funcionamiento consiste en enviar una solicitud a un servidor web y luego recibir una respuesta que incluye el contenido que  debe aparecer en la pantalla del dispositivo.
    
    Al abrir un navegador, se visualizará la barra de direcciones en la que se introduce la dirección (url) del sitio web que se desee visitar. *La URL contiene el Protocolo (Protocol), el Nombre de Dominio (Domain Name) y la Ruta del archivo (File path)*. 
    
    En primer lugar se abre el navegador web, a continuación se introduce una URL, por lo que el navegador web envía una solicitud a través de una red que se conecta a otra computadora en Internet llamada Servidor Web. Este, es un tipo especial de computadora que les permite a otras computadoras hacer solicitudes de datos. El Servidor web responde enviando una página web al navegador. Una vez que el navegador recibe toda la información de respuesta, la página web buscada se hace visible a través de un proceso llamado renderización. 
    
- **URL**: [http://www.example.com/index.html](http://www.example.com/index.html):
- **Protocol**: http
- **Domain name**: example.com
- **File path**: [index.html](http://index.ht)

**Alojamiento web**: Es un servicio mediante el cual es posible colocar un sitio web y sus archivos en en servidor web de las empresas de alojamiento. Básicamente uno aloja el espacio a cambio de un almacenamiento estable y seguro.

- **Alojamiento Compartido (Shared Hosting)**: Uno paga por una ubicación en un servidor web que contiene muchas cuentas de alojamiento web con alojamiento compartido. Esto significa que se comparte la potencia de procesamiento del servicio, memoria y ancho de banda con otros sitios web que podrían ralentizar su rendimiento. Esta es la mejor opción para un sitio web pequeño con un reducido número de visitantes.
- **Alojamiento Privado Virtual (Virtual Private Hosting)**: Es un servidor virtual con recursos de CPU dedicada, memoria y ancho de banda. Se ejecutará en un servidor de hardware con otras instancias de VPS, pero como los recursos son fijos por instancia de VPS, es poco probable que su sitio web se vea afectado por el rendimiento de las otras instancias.
- **Alojamiento Dedicado (Dedicated Hosting)**: Se trata de un servidor que está dedicado solo a una persona. Puede utilizar todos los recursos del hardware, CPU, memoria y ancho de banda.
- **Alojamiento en la Nube (Cloud Hosting)**: El sitio web se ejecuta en un espacio denominado entorno de nube, que se extiende a través de múltiples servidores físicos y virtuales. Si falla un servidor físico o virtual, su sitio web funcionará en un servidor diferente y permanecerá en línea

### Recursos Adicionales  - La Web

- **¿Qué es un servidor web? (NGINX):** [https://www.nginx.com/resources/glossary/web-server/](https://www.nginx.com/resources/glossary/web-server/)
- **¿Qué es un navegador web? (Mozilla):** [https://www.mozilla.org/en-US/firefox/browsers/what-is-a-browser/](https://www.mozilla.org/en-US/firefox/browsers/what-is-a-browser/)
- **¿Quién inventó Internet? ¿Y por qué? (Kurzgesagt):** [https://youtu.be/21eFwbb48sE](https://youtu.be/21eFwbb48sE)
- **¿Qué es la computación en nube? (Amazon):** [https://youtu.be/mxT233EdY5c](https://youtu.be/mxT233EdY5c)
- **Motores de navegación (Wikipedia):** [https://en.wikipedia.org/wiki/Browser_engine](https://en.wikipedia.org/wiki/Browser_engine)

---

## Tecnologías principales de Internet

### Introducción a los protocolos de Internet

- **Transmission Control Protocol (TCP)**: Este protocolo se utiliza para enviar los datos que deben llegar correctamente y en orden, como los archivos de texto o imagen. Este protocolo puede hacer frente a los paquetes de datos que llegan fuera de servicio, se dañan o se corrompen, o se caen o se pierden, aunque con un pequeño retraso

- **User Datagram Protocol (UDP)**: Este protocolo se utiliza para enviar datos que pueden tolerar cierta pérdida de información o que requieren velocidad sobre fiabilidad, como las transmisiones de video en vivo, juegos en línea, y llamadas de voz o videollamadas. UDP no garantiza la entrega de paquetes en orden ni su corrección, ya que carece de los mecanismos de verificación y reenvío de TCP. Esto lo hace más rápido, pero menos fiable, ya que no verifica la llegada ni el orden de los datos.

### Introducción a HTTP

- **HTTP (HyperText Transfer Protocol)**: Es un protocolo operativo básico de la Web. Es lo que permite al navegador comunicarse con un servidor que aloja un sitio web. Es un protocolo utilizado para transferir recursos web como documentos HTML, imágenes, estilos y otros archivos. Es un protocolo basado en solicitud-respuesta
    - Una solicitud HTTP consiste en un método, una ruta, una versión y cabeceras.
    
     ![HTTP Request 1](imagenes/Meta%20Front-End%20Developer/http-request-2.png)
    ![HTTP Request 2](imagenes/Meta%20Front-End%20Developer/http-request-1.png)
    
   
    

### Métodos HTTP

- Los métodos HTTP indican la acción que el cliente desea realizar sobre el recurso del servidor web. Los métodos HTTP más comunes son:

| **Método HTTP** | **Descripción** |
| --- | --- |
| GET | El cliente solicita un recurso en el servidor web. |
| POST | El cliente envía datos a un recurso en el servidor web. |
| PUT | El cliente sustituye un recurso en el servidor web. |
| DELETE | El cliente borra un recurso en el servidor web. |
| PATCH | El cliente actualiza parcialmente un recurso en el servidor web. |

***Ruta:*** Es la representación de dónde se almacena el recurso en el servidor web

***Cabeceras o Headers***: Una cabecera es un nombre que no distingue entre mayúsculas y minúsculas, seguido de **:** (dos puntos) y, a continuación, de un valor. Contienen información adicional sobre la solicitud y el cliente que realiza la petición. 

Las cabeceras más comunes son:

```json
Host: example.com
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.9; rv:50.0) Gecko/20100101 Firefox/50.0
Accept: */*
Accept-Language: en
Content-type: text/json
```

- La cabecera **`Host`** especifica el host del servidor e indica desde dónde se solicita el recurso.
- La cabecera **`User-Agent`** informa al servidor web de la aplicación que está realizando la solicitud. Suele incluir el sistema operativo (Windows, Mac, Linux), la versión y el proveedor de la aplicación.
- La cabecera **`Accept`** informa al servidor web del tipo de contenido que el cliente aceptará como respuesta.
- La cabecera **`Accept-Language`** indica el idioma y, opcionalmente, la configuración regional que prefiere el cliente.
- La cabecera **`Content-type`** indica el tipo de contenido que se transmite en el cuerpo de la solicitud.

***Códigos de estado***: 

- Informativos: 100-199
- Respuestas Exitosas: 200-299
- Redirección: 300-399
- Error en el cliente: 400-499
- Error en el servidor: 500-599

![Códigos de Estado](imagenes/Meta%20Front-End%20Developer/codigos-de-estado.png)

**Encabezados de respuesta HTTP**:

De forma similar a las cabeceras de solicitud, existen muchas cabeceras HTTP posibles que pueden incluirse en la respuesta HTTP.

```json
Date: Fri, 11 Feb 2022 15:00:00 GMT+2
Server: Apache/2.2.14 (Linux)
Content-Length: 84
Content-Type: text/html
```

- La cabecera **`Date`** especifica la fecha y hora en que se generó la respuesta HTTP.
- La cabecera **`Server`** describe el software del servidor web utilizado para generar la respuesta.
- La cabecera **`Content-Length`** describe la longitud de la respuesta.
- La cabecera **`Content-Type`** describe el tipo de medio del recurso devuelto (por ejemplo, documento HTML, imagen, vídeo).

**Cuerpo de la respuesta HTTP:**

A continuación de las cabeceras de respuesta HTTP se encuentra el cuerpo de la respuesta HTTP. Este es el contenido principal de la respuesta HTTP.

Puede contener imágenes, vídeo, documentos HTML y otros tipos de medios

```json
HTTP/1.1 200 OK
Date: Fri, 11 Feb 2022 15:00:00 GMT+2
Server: Apache/2.2.14 (Linux)
Content-Length: 84
Content-Type: text/html

<html>
  <head><title>Test</title></head>
  <body>Test HTML page.</body>
</html>
```

### Otros protocolos de Internet

- **Protocolo de configuración dinámica de host (DHCP)**: Ha aprendido que los ordenadores necesitan direcciones IP para comunicarse entre sí. Cuando su ordenador se conecta a una red, se utiliza el Protocolo de configuración dinámica de host o DHCP, como se conoce comúnmente, para asignar a su ordenador una dirección IP.
Su ordenador se comunica a través del Protocolo de Datagramas de Usuario (UDP) utilizando el protocolo con un tipo de servidor llamado servidor DHCP. El servidor lleva un registro de los ordenadores de la red y de sus direcciones IP. Asignará a su ordenador una dirección IP y responderá a través del protocolo para hacerle saber qué dirección IP debe utilizar. Una vez que su ordenador tenga una dirección IP, podrá comunicarse con otros ordenadores de la red.
- **Protocolo del sistema de nombres de dominio (DNS)**: Su ordenador necesita una forma de saber con qué dirección IP debe comunicarse cuando visita un sitio web en su navegador, por ejemplo, **meta.com**. El Protocolo del Sistema de Nombres de Dominio, comúnmente conocido como DNS, proporciona esta función. Su ordenador realiza una comprobación con el servidor DNS asociado al nombre de dominio y le devuelve la dirección IP correcta.
- **Protocolo de acceso a mensajes de Internet (IMAP)**: ¿Consulta sus correos electrónicos en su dispositivo móvil o tableta? ¿O tal vez utiliza una aplicación de correo electrónico en su ordenador?
Su dispositivo necesita una forma de descargar los correos electrónicos y gestionar su buzón en el servidor que los almacena. Este es el propósito del Protocolo de Acceso a Mensajes de Internet o IMAP.
- **Protocolo simple de transferencia de correo (SMTP)**: Ahora que sus correos electrónicos están en su dispositivo, necesita una forma de enviarlos. Para ello se utiliza el Protocolo simple de transferencia de correo o SMTP. Permite a los clientes de correo electrónico enviar correos electrónicos a través de un servidor SMTP.
- **Protocolo de oficina de correos (POP)**: El Post Office Protocol (POP) es un protocolo más antiguo utilizado para descargar correos electrónicos a un cliente de correo electrónico. La principal diferencia de utilizar POP en lugar de IMAP es que POP borrará los correos electrónicos del servidor una vez que se hayan descargado en su dispositivo local. Aunque ya no se utiliza habitualmente en los clientes de correo electrónico, los desarrolladores suelen utilizarlo para implementar la automatización del correo electrónico, ya que es un protocolo más sencillo que IMAP.

- **Protocolo de transferencia de archivos (FTP)**: Cuando ejecute sus sitios y aplicaciones web en Internet, necesitará una forma de transferir los archivos desde su ordenador local al servidor en el que se ejecutarán. El protocolo estándar utilizado para ello es el Protocolo de Transferencia de Archivos o FTP. El FTP le permite listar, enviar, recibir y borrar archivos en un servidor. Su servidor debe ejecutar un Servidor FTP y usted necesitará un Cliente FTP en su máquina local. Aprenderá más sobre estos en un curso posterior.
- **Protocolo Secure Shell (SSH)**: Cuando empiece a trabajar con servidores, también necesitará una forma de iniciar sesión e interactuar con el ordenador de forma remota. El método más común de hacerlo es utilizando el Protocolo Secure Shell, comúnmente conocido como SSH. El uso de un cliente SSH le permite conectarse a un servidor SSH que se ejecuta en un servidor para realizar comandos en el ordenador remoto.
Todos los datos enviados a través de SSH están encriptados. Esto significa que terceras partes no pueden entender los datos transmitidos. Sólo los ordenadores emisor y receptor pueden entender los datos.
- **Protocolo de transferencia de archivos SSH (SFTP)**: Los datos se transmiten de forma insegura cuando se utiliza el Protocolo de Transferencia de Archivos. Esto significa que terceras partes pueden entender los datos que usted está enviando. Esto no es correcto si transmite archivos de empresa como software y bases de datos. Para solucionar esto, se puede utilizar el Protocolo de Transferencia de Archivos SSH, también llamado Protocolo Seguro de Transferencia de Archivos, para transferir archivos a través del protocolo SSH. Esto garantiza que los datos se transmiten de forma segura. La mayoría de los clientes FTP también son compatibles con el protocolo SFTP.

### Frameworks y Librerías

- Las **librerías o bibliotecas** son piezas reutilizables de código que se pueden reutilizar en una aplicación. Están especialmente diseñadas para proporcionar una funcionalidad específica.
- Los frameworks proporcionan una estructura a partir de la cual los desarrolladores pueden crear un proyecto. Funcionan como una estructura en la que el desarrollador proporciona su propio código con el que el framerowk interactúa

### API y servicios

- Una API (Application Programming Interface) es un conjunto de funciones y procedimientos para la creación de aplicaciones que acceden a las características o los datos de un SO, una aplicación u otro servicio.
    
    Algunas de las API más usadas comúnmente son:
    
    - **Browser API**: Son interfaces que los navegadores web proporcionan para que los desarrolladores interactúen directamente con las funciones del navegador o con el dispositivo en el que se ejecuta. *Por ejemplo*: La API del DOM y la API de fetch.
    - **REST API**: Es un servidor web que proporciona respuestas a solicitudes
    - **Sensor-Based API**:  Estas APIs permiten que las aplicaciones accedan a los datos de los sensores en un dispositivo, como los sensores de movimiento, de luz, o de proximidad en un smartphone.

### Recursos Adicionales - HTTP

**Visión general de HTTP (Mozilla):** [https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)

**Introducción a las redes por el Dr.Charles R Severance:** [https://www.amazon.com/Introduction-Networking-How-Internet-Works/dp/1511654945/](https://www.amazon.com/Introduction-Networking-How-Internet-Works/dp/1511654945/)

**Visión general de las herramientas para desarrolladores de Chrome (Google):** [https://developer.chrome.com/docs/devtools/overview/](https://developer.chrome.com/docs/devtools/overview/)

**Documentos de usuario de las herramientas para desarrolladores de Firefox (Mozilla):** [https://firefox-source-docs.mozilla.org/devtools-user/index.html](https://firefox-source-docs.mozilla.org/devtools-user/index.html)

**Introducción a Visual Studio Code (Microsoft):** [https://code.visualstudio.com/docs](https://code.visualstudio.com/docs)

---

## HTML

### Recursos Adicionales - HTML

- **Referencia de elementos HTML (Mozilla):** [https://developer.mozilla.org/en-US/docs/Web/HTML/Element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
- **El elemento formulario (Mozilla):** [https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)
- **¿Qué es el modelo de objetos del documento? (W3C):** [https://www.w3.org/TR/WD-DOM/introduction.html](https://www.w3.org/TR/WD-DOM/introduction.html)
- **ARIA en HTML (W3C vía Github):** [https://w3c.github.io/html-aria/](https://w3c.github.io/html-aria/)
- **Prácticas de autoría ARIA (W3C):** [https://www.w3.org/TR/wai-aria-practices-1.2/](https://www.w3.org/TR/wai-aria-practices-1.2/)

---

## Introducción a los frameworks y las librerías de la interfaz de usuario

### Trabajar con bibliotecas

- **Gestor de paquetes**: Es una herramienta que descarga automáticamente las dependencias y las instala. También nos referimos a las dependencias como paquetes. Un gestor de paquetes también proporciona la capacidad de publicar sus propios paquetes.
El gestor de paquetes más común para el desarrollo front-end es el Node Package Manager o npm.

- **Herramienta de agrupación (Bundling tool)**: Su objetivo es  combinar todas las dependencias de forma automática en un solo archivo. ***Ejemplos***: Gulp y Webpack

### Primeros pasos con Bootstrap

- Es una biblioteca de código CSS y JavaScript para construir rápidamente sitios web visualmente atractivos. El desarrollo web moderno gira en torno a **los componentes**. Pequeñas piezas de código reutilizable que le permiten construir sitios web rápidamente. Bootstrap viene con múltiples componentes para una construcción muy rápida de múltiples componentes, o partes de componentes.

- Modificadores (color)
    - Primary
    - Secondary
    - Success
    - Info
    - Warning

- **Grid Bootstrap**: Utiliza un sistema de cuadrícula de 12 columnas. Siempre incluye un contenedor, filas y columnas. El contenedor es el elemento raíz de la cuadrícula. Dentro del contenedor se puede añadir filas y dentro de cada fila pueden añadirse columnas.

### Recursos Adicionales - Bootstrap

- **Bootstrap Official Website:** [https://getbootstrap.com/](https://getbootstrap.com/)
- **Bootstrap 5 Foundations by Daniel Foreman:** [https://www.amazon.com/Bootstrap-Foundations-Mr-Daniel-Foreman/dp/B0948GRS8W/](https://www.amazon.com/Bootstrap-Foundations-Mr-Daniel-Foreman/dp/B0948GRS8W/)
- **Responsive Web Design with HTML5 and CSS  by Ben Frain:** [https://www.amazon.com/Responsive-Web-Design-HTML5-CSS/dp/1839211563/](https://www.amazon.com/Responsive-Web-Design-HTML5-CSS/dp/1839211563/)
- **Bootstrap Themes:** [https://themes.getbootstrap.com/](https://themes.getbootstrap.com/)

---

## Introducción a React

### Contenidos estáticos y dinámicos

- **Contenido estático**: Consiste en archivos que el servidor transfiere tal como están almacenados en el servidor web, como videos o imágenes.
- **Contenido dinámico**: Se genera cuando se realiza la solicitud HTTP. Por ejemplo, el contenido se puede generar en función de la entrada de un usuario, o cuando se visita un sitio web de noticias se basaría en la fecha actual. Lo que en realidad sucede es que el servidor web se comunica con otro tipo de servidor, llamado servidor de aplicaciones o back-end. El servidor de aplicaciones genera el contenido dinámico que el servidor web devuelve al navegador del usuario

### Aplicaciones de una sola página (SPA)

- **Sitio web Tradicional**: Anteriormente la mayoría de los sitios webs se implementaban como aplicaciones de varias páginas. Pero esto hace que las aplicaciones tradicionales demanden un uso intensivo de recursos a los servidores web, ya que el envío de páginas web completas para cada solicitud consume demasiado ancho de banda y utiliza tiempo de CPU para generar páginas dinámicas.
- **SPA**: Las SPA tienen solo una página HTML que se envía desde el servidor al navegador, pero esa página actualizará su contenido a medida que sus usuarios interactúen con el sitio web. Una SPA permite al usuario interactuar con el sitio web sin que la aplicación tenga que descargar nuevas páginas web enteras. En cambio, reescribe la página web actual a medida que el usuario interactúa con ella.

### ¿Qué es Bootstrap?

- React es una librería de código abierto. Los desarrolladores usan React para desarrollar aplicaciones SPA, aunque también se pueden desarrollar aplicaciones móviles con React Native.
- **Componente**: Es una pequeña parte de una interfaz de usuario, como un reproductor de música o una galería de fotos.
- **DOM Virtual**: React construye una representación del Modelo de Objetos del Documento o DOM del navegador en la memoria denominada DOM virtual. A medida que se actualizan los componentes, React comprueba si el código HTML del componente en el DOM virtual coincide con el DOM del navegador. Si se requiere un cambio, se actualiza el DOM del navegador. Si no ha cambiado nada, no se realiza ninguna actualización.

### Recursos Adicionales - React

- **Sitio web oficial de React:** [https://reactjs.org/](https://reactjs.org/)
- **Elegir entre Web Apps tradicionales y Single Page Apps (Microsoft):** [https://docs.microsoft.com/en-us/dotnet/architecture/modern-web-apps-azure/choose-between-traditional-web-and-single-page-apps](https://docs.microsoft.com/en-us/dotnet/architecture/modern-web-apps-azure/choose-between-traditional-web-and-single-page-apps)
- **Código fuente de React (Github):** [https://github.com/facebook/react](https://github.com/facebook/react)
- **Introducción a React.js:** [*https://youtu.be/XxVg_s8xAms*](https://youtu.be/XxVg_s8xAms)

---

#