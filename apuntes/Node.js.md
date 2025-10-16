# Node.JS

# ¿Qué es Node.js?

Node.js NO es un lenguaje de programación, un framework ni tampoco una librería. Es un entorno de ejecución de JavaScript, orientado a eventos asíncronos. Permite ejecutar JS fuera del navegador (backend, terminal, dispositivos).

- Basado en el motor V8 de Chrome
- **Multiplataforma**: Funciona en servidores, terminal, dispositivos IoT, etc.
- **Monohilo**: Usa un solo hilo principal, pero maneja operaciones asíncronas mediante el *event loop*.
- **NPM integrado**: Viene con el gestor de paquetes más grande del mundo

**Link (LTS Recomendado)**: [https://nodejs.org/es/download](https://nodejs.org/es/download)

---

## Conceptos básicos

- **REPL** (*Read-Eval-Print Loop*): Consola interactiva de Node para ejecutar JS línea por línea.
- **globalThis**: Variable global en cualquier entorno.
    - En navegador → `window`
    - En Node.js → `global`
    - Documentación: [https://nodejs.org/dist/latest/docs/api/globals.html#global](https://nodejs.org/dist/latest/docs/api/globals.html#global)

---

# Módulos en Node.js

- Un módulo es una pieza de funcionalidad contenida en uno o varios archivos JavaScript que puede ser reutilizada dentro de una aplicación. En Node.js, todo archivo `.js` es considerado un módulo.

## Sistemas de Módulos

Existen **dos sistemas principales** para trabajar con módulos en Node.js:

### 1. CommonJS (CJS)

- Es el sistema de módulos **clásico de Node.js**. Se utiliza principalmente en proyectos existentes o antiguos.

```jsx
// Exportar una sola cosa
const nombre = "Juan"
module.exports = nombre

// Exportar varias cosas
function sumar(a, b) { return a + b }
function restar(a, b) { return a - b }
module.exports = { sumar, restar }

// Importar
const nombre = require("./archivo.js")
const { sumar, restar } = require("./operaciones.js")
```

### 2. ECMAScript Modules (ESM)

- Es el estándar oficial de JavaScript, soportado también en Node.js (requiere usar extensión `.mjs` o `"type": "module"` en `package.json`). Se recomienda en proyectos modernos.

```jsx
// Exportar una variable
export const nombre = "Juan"

// Exportar varias funciones
export function sumar(a, b) { return a + b }
export function restar(a, b) { return a - b }

// Importar
import { nombre, sumar } from "./archivo.js"
```

---

## Módulos Built-in (incorporados)

Node.js incluye varios módulos listos para usar, sin necesidad de instalar nada:

- `http` → crear servidores web.
- `https` → trabajar con servidores seguros (SSL).
- `fs` → manipular archivos y directorios.
- `os` → obtener info del sistema operativo.
- `path` → manejar rutas de archivos de forma segura.

## Módulo process

Provee información sobre el proceso de Node.js que se está ejecutando.

- `process.argv` → argumentos de la terminal (array).
- `process.memoryUsage()` → uso de memoria.
- `process.cwd()` → ruta del directorio actual.
- `process.exit(codigo)` → terminar el proceso. 0 (éxito) y 1 (error).
- **`process.stdout.write(data)`** → escribe directamente en la salida estándar (similar a console.log, pero sin salto de línea automático).
- `process.stdin.on("data", callback)` → lee datos ingresados por el usuario desde la entrada estándar.

```jsx
// Mostrar los argumentos de la terminal
console.log(process.argv); // ["node", "app.js", "arg1", "arg2"]

// Leer datos del usuario
process.stdout.write("\nIngrese su nombre: ");
process.stdin.on("data", (data) => {
  console.log(`Hola ${data.toString().trim()}!`);
  process.exit(0);
});
```

## Módulo os

Permite obtener información sobre el sistema operativo.

- `os.type()` → sistema operativo del usuario.
- `os.homedir()` → directorio principal del usuario.
- `os.uptime()` → tiempo encendido en segundos.
- `os.userInfo()` → información del usuario.

## Módulo timers

Contiene funciones que ejecutan código luego de un cierto período de tiempo.

- `setTimeout(funcion, retraso, arg1, arg2)` → ejecuta después de cierto tiempo.
- `setImmediate(funcion, arg1, arg2)` → ejecuta al final de la fase actual del event loop (después de todo el código síncrono).
- `setInterval(funcion, intervalo, arg1, arg2)` → repite indefinidamente cada cierto tiempo.

## Módulo fs

Permite trabajar con el sistema de archivos.

- Todos los métodos son **asíncronos** por defecto, pero existen versiones síncronas con `Sync`.
    - `fs.readFileSync("./index.html", "utf-8")` *→ l*eer un archivo de manera síncrona
    - `fs.readFile("rutaArchivo", "codificación", (err, content) ⇒ {})` → lectura asíncrona
    - `fs.renameSync(oldName, newName)` *→* renombrar un archivo de manera síncrona
    - `fs.rename(oldName, newName, (err) => {...})` *→* renombrar un archivo
    - `fs.appendFile("rutaArchivo", "contenido", () => {...})` → agregar contenido al final del archivo

---

# npm (Node Package Manager)

**npm** es el gestor de paquetes oficial de Node.js. Permite instalar, compartir y administrar paquetes (librerías, herramientas, frameworks, etc.).

## Conceptos clave

- **Paquete** → archivo o conjunto de archivos almacenados en una carpeta y descritos por un `package.json`.
- **Módulo** → cualquier archivo o directorio dentro de `node_modules` que puede ser importado con `require()` o `import`.
- **Dependencia** → paquete que otro paquete necesita para funcionar correctamente.

## Dependencias de Desarrollo y Producción

- Dependencias de producción
    - El proyecto las necesita para funcionar
    - npm i nombreDependencia

- Dependencias de desarrollo
    - 

### Crear un paquete con npm

1. Crear una carpeta con el nombre del proyecto.
2. Inicializar el proyecto:
    - `npm init` → crea un `package.json` configurable paso a paso.
    - `npm init -y` → crea un `package.json` con valores por defecto.

📌 El archivo `package.json` contiene:

- Nombre del proyecto
- Versión
- Dependencias (`dependencies`)
- Dependencias de desarrollo (`devDependencies`)
- Scripts personalizados (`npm run script`)

### JSON

JSON (**JavaScript Object Notation**) es un formato de texto ligero para almacenar y transportar información. Representa datos como pares clave-valor.

```jsx
// JSON a JavaScript (string → objeto)
const obj = JSON.parse(jsonString)

// JavaScript a JSON (objeto → string)
const json = JSON.stringify(obj)
```

### Instalar y desinstalar paquetes

```bash
# Instalar un paquete
npm install nombrePaquete
npm i nombrePaquete

# Desinstalar un paquete
npm uninstall nombrePaquete

# Instalar todas las dependencias listadas en package.json
npm install
npm i

# Instalar dependencias como desarrollador (devDependencies)
npm i nombrePaquete --save-dev
```

### package-lock.json

- Se genera automáticamente cuando npm modifica el árbol de `node_modules` o `package.json`. Describe el árbol generado para que futuras instalaciones puedan generar exactamente el mismo árbol (otros desarrolladores pueden instalar exactamente las mismas dependencias).

---

# Eventos

Un **evento** es una acción o suceso que ocurre dentro de la aplicación, al cual se puede reaccionar ejecutando código.

- **Eventos Asíncronos**: Eventos que se ejecutan independientemente del proceso principal de la aplicación (no bloquean la aplicación y continúan su ejecución en paralelo) .
- **Eventos Síncronos**: Eventos que se ejecutan como parte del proceso principal de la aplicación (bloquean la aplicación).

## Módulo events

El módulo `events` proporciona la clase `EventEmitter` y métodos principales:

- **`emitter.on("evento", callback)`** → registra un listener para un evento.
- **`emitter.once("evento", callback)`** → registra un listener que se ejecuta **solo una vez**.
- **`emitter.emit("evento", [...args])`** → emite el evento, ejecutando los listeners asociados.
- **`emitter.removeListener("evento", callback)`** → elimina un listener específico.
- **`emitter.removeAllListeners("evento")`** → elimina todos los listeners de un evento.

- EventEmitter (emisores) → Un **emisor de eventos** es un objeto que puede **emitir** y **escuchar** eventos. En Node.js, los emisores son instancias de la clase `EventEmitter`.

```jsx
const events = require("node:events")

// Emisor de eventos
const emitter = new events.EventEmitter()

// Definir un listener
emisor.on("saludo", (nombre) => {
  console.log(`Hola, ${nombre}!`)
})

// Emitir el evento
emisor.emit("saludo", "Juan") 
```

---

# HTTP y Rutas en Node.js

## Conceptos básicos

- **Cliente** → generalmente el navegador o cualquier aplicación que realiza solicitudes al servidor.
- **Servidor** → programa que corre en un sistema y responde a las solicitudes del cliente.

La comunicación se hace mediante el **protocolo HTTP** (HyperText Transfer Protocol).

### Solicitud HTTP (cliente → servidor)

Una solicitud HTTP está compuesta por:

- **Método HTTP** → indica la intención de la solicitud.
- **Ruta (path)** → identifica el recurso solicitado (ej. `/home`, `/about`).
- **Versión HTTP** → ejemplo: `HTTP/1.1`.
- **Cabeceras (headers)** → información adicional (tipo de contenido, cookies, etc.).
- **Cuerpo (body)** → datos enviados (solo en métodos como `POST` o `PUT`).

### Métodos HTTP principales

- **GET** → obtener un recurso (ej. HTML, CSS, imágenes).
- **POST** → crear un recurso nuevo (ej. usuario en una base de datos).
- **PUT** → actualizar un recurso existente.
- **DELETE** → eliminar un recurso.

### Respuesta HTTP (servidor → cliente)

- **Código de estado** → resultado de la solicitud.
- **Texto de estado** → descripción del código.
- **Versión HTTP**.
- **Cabeceras**.
- **Cuerpo** → la información solicitada o un mensaje de error.

### Clases de códigos de estado

1. **100 - 199** → Respuestas informativas.
2. **200 - 299** → Respuestas exitosas.
3. **300 - 399** → Redirecciones.
4. **400 - 499** → Errores del cliente.
5. **500 - 599** → Errores del servidor.

### Códigos comunes

- **200 OK** → éxito.
- **400 Bad Request** → solicitud incorrecta.
- **404 Not Found** → recurso no encontrado.
- **500 Internal Server Error** → error en el servidor.

### Módulo http

El módulo `http` permite crear servidores que reciben solicitudes y responden con datos.

```jsx
const http = require("node:http");

const host = "127.0.0.1";
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200; // 200 OK
  res.setHeader("Content-Type", "text/plain");
  res.end("Hello"); 
});

server.listen(port, host, () => {
  console.log(`Servidor corriendo en http://${host}:${port}`);
});
```

### Conceptos relacionados

- **Puerto** → ubicación virtual en el sistema operativo que permite acceder a una aplicación o proceso (ej. `:3000`).
- **Estructura de una URL** (ejemplo: `https://www.google.com/search`):
    - **Protocolo** → `https`
    - **Subdominio** → `www`
    - **Dominio** → `google`
    - **TLD** → `.com`
    - **Ruta** → `/search`

## Módulo url

```jsx
const url = require("node:url");
const myUrl = new url.URL("https://www.ejemplo.com/cursos/programacion?lenguaje=nodejs&nivel=basico");

console.log("hostname:", myUrl.hostname); // www.ejemplo.org
console.log("path:", myUrl.pathname) // /cursos/programacion

// URLSearchParams { 'lenguaje' => 'nodejs', 'nivel' => 'basico' }
console.log("search params:", myUrl.searchParams); 
console.log(myUrl.searchParams.get("lenguaje")); 
console.log(myUrl.searchParams.get("nivel")); 
```

---

## Routing

El routing (enrutamiento) consiste en manejar las solicitudes HTTP del cliente en base a ciertos criterios y devolver la respuesta adecuada.

### Criterios

- **Método de la solicitud HTTP** (GET, POST, PUT, DELETE, etc.)
- **Path de la solicitud HTTP** (ejemplo: `/`, `/users`, `/movies`)

```jsx
const http = require("node:http");

const HOST = "127.0.0.1";
const PORT = 3000;

const server = http.createServer((req, res) => {
  const { method } = req; // GET, POST, PUT o DELETE

  switch (method) {
    case "GET":
      return manejarSolicitudGet(req, res);

    case "POST":
      return manejarSolicitudPost(req, res);

    default:
      res.statusCode = 501;
      res.end(`El método usado no puede ser manejado por el servidor: ${method}`);
  }
});

function manejarSolicitudGet(req, res) {
  const path = req.url;

  if (path === "/") {
    res.writeHead(200, { "Content-Type": "text/plain; charset=utf-8" });
    return res.end("Bienvenido a la página de inicio");
  } else if (path === "/about") {
    res.writeHead(200, { "Content-Type": "text/plain; charset=utf-8" });
    return res.end("Acerca de nosotros");
  }

  res.statusCode = 404;
  res.end("El recurso solicitado no existe");
}

function manejarSolicitudPost(req, res) {
  const path = req.url;

  if (path === "/contact") {
    res.writeHead(200, { "Content-Type": "text/plain; charset=utf-8" });
    return res.end("Has enviado un mensaje de contacto");
  }

  res.statusCode = 404;
  res.end("El recurso solicitado no existe");
}

server.listen(PORT, HOST, () => {
  console.log(`Servidor escuchando en http://${HOST}:${PORT}/`);
});
```

### Notas importantes

- `req.method` → devuelve el método HTTP (`GET`, `POST`, etc.).
- `req.url` → devuelve la ruta solicitada (`/`, `/about`, etc.).
- Siempre conviene setear el header `Content-Type` para evitar problemas de codificación (ejemplo con `utf-8`).
- Si la ruta o método no coincide con ninguno definido → responder con `404`.

---

## Recarga automática y monitorización de cambios

Durante el desarrollo con Node.js, es común modificar archivos del proyecto y tener que reiniciar el servidor manualmente para aplicar los cambios.

Para evitar esto, existen herramientas que recargan automáticamente la aplicación al detectar modificaciones en el código fuente.

### —watch

Desde Node.js v18+, se puede usar el flag `--watch` para que el proceso **monitoree los cambios** en los archivos del proyecto y reinicie la aplicación automáticamente.

- ejecutar: `node —watch <aplicacion>`

### Nodemon

Es una herramienta que facilita el desarrollo con Node.js. Su función principal es reiniciar automáticamente la aplicación cuando detecta cambios en los archivos del proyecto.

- instalación global → `npm install -g nodemon`
- instalación → `npm i nodemon -D` → agregar como script en `package.json`
- ejecutar → `nodemon <aplicacion>`
- **Documentación**: [https://www.npmjs.com/package/nodemon](https://www.npmjs.com/package/nodemon)

---

# Express

Express es el framework web más popular de Node.js. Es una herramienta **minimalista y flexible** que proporciona una estructura para desarrollar servidores y APIs de una manera más sencilla.

- **Documentación (npm)**: [https://www.npmjs.com/package/express](https://www.npmjs.com/package/express)

## Diferencias entre Nativo y Express

- Express a diferencia de Node.JS nativo, detecta automáticamente cual es el `Content-Type` que tiene que utilizar dependiendo de la `response` que se utilice.

## Conceptos básicos

- **CRUD** → operaciones básicas sobre datos:
    - **Create** → `POST`
    - **Read** → `GET`
    - **Update** → `PUT` / `PATCH`
    - **Delete** → `DELETE`
- **API** → interfaz que permite la comunicación entre dos programas. No está pensada para el usuario final, sino para que otros programas consuman sus servicios.
    - Ejemplo: una API REST para obtener información de libros.

## Primeros Pasos

```jsx
// 1. Inicializar un paquete: npm init
// 2. Instalar express: npm i express
// 3. Crear un servidor básico

const express = require("express");
const app = express(); // Crea la aplicación/servidor

// Ruta de inicio
app.get("/", (req, res) => {
  res.send("Inicio");
});

// Configuración del servidor
const host = "localhost";
const port = process.env.PORT || 3000;

app.listen(port, host, () => {
  console.log(`Servidor escuchando en http://${host}:${port}`);
});
```

## Parámetros en Express

### 1. Parámetros de ruta (Route Params)

Los **parámetros de ruta** son partes dinámicas dentro de la URL. Se definen con `:` y permiten capturar valores enviados directamente en la ruta.

```jsx
app.get("/api/example/:value", (req, res) => {
  const valor = req.params.value; // acceder al parámetro de la URL
  res.send(`Valor recibido: ${valor}`);
});

// http://localhost:3000/api/example/123
```

### 2. Parámetros de consulta (Query Params)

Los **query params** son pares clave-valor que se agregan a la URL después de un `?`.

Se accede a ellos mediante `req.query` y son útiles para **filtrar, ordenar o paginar** resultados.

```jsx
app.get("/api/autores", (req, res) => {
  let resultado = autores;

  // Filtrar por año de nacimiento
  if (req.query.year) {
    resultado = resultado.filter(a => a.year == req.query.year);
  }

  // Ordenar alfabéticamente
  if (req.query.ordenar === "true") {
    resultado = [...resultado].sort((a, b) => a.name.localeCompare(b.name));
  }

  res.json(resultado);
});

// http://localhost:3000/api/autores?year=1828&ordenar=true
```

### Middlewares

Es una función que se ejecuta entre la petición y la respuesta

```jsx
const express = require("express");
const app = express();

// Middleware
app.use((req, res, next) => {
	
})

// Rutas
app.get("/", (req, res) => {
  // express detecta automáticamente el content-type, dependiendo de la respuesta
  res.send("<h1>Inicio</h1>");
});

app.listen(3000, () => {
  console.log(`server listening on port http://localhost:3000`);
});
```