# Tailwind CSS

# Instalación

- **Link**: [https://tailwindcss.com/](https://tailwindcss.com/)
- **Cheat Sheet**: [https://www.creative-tim.com/twcomponents/cheatsheet](https://www.creative-tim.com/twcomponents/cheatsheet)
- **Components**: [https://flowbite.com/docs/getting-started/introduction/](https://flowbite.com/docs/getting-started/introduction/)
- **Templates**: [https://www.creative-tim.com/templates/tailwind](https://www.creative-tim.com/templates/tailwind)

## CDN

```html
<script src="https://cdn.tailwindcss.com"></script>
```

## npm (vite)

```bash
# Crear proyecto
npm create vite
cd my-project

# Instalar Tailwind CSS
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

```jsx
// Configurar archivo 'tailwind.config.js'

/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

```css
/* Añadir a index.css*/
@tailwind base;
@tailwind components;
@tailwind utilities;
```

```jsx
// Comenzar a utilizar Tailwind
<h1 className="text-3xl font-bold underline">Hello world!</h1>
```

# ¿Qué es Tailwind CSS?

Tailwind CSS es un **framework** de utilidades para **CSS** que permite construir diseños personalizados de manera rápida y eficiente. A diferencia de otros frameworks que proporcionan componentes predefinidos, **Tailwind se centra en clases de utilidad** que puedes combinar para crear tu propio diseño.

## ¿Cómo funciona?

En lugar de escribir CSS personalizado, utilizas clases utilitarias directamente en el HTML. Cada clase realiza una tarea específica, como aplicar colores, márgenes, tipografía, tamaños y otros estilos visuales. Esto permite un control preciso sobre el diseño sin necesidad de escribir estilos CSS complicados.

***Ejemplo***: 

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ejemplo con Tailwind CSS</title>
  <!-- Enlace al CDN de Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-900 font-sans">

  <!-- Contenedor principal -->
  <div class="max-w-md mx-auto mt-10 p-6 bg-white rounded-lg shadow-lg">
    <h1 class="text-3xl font-bold text-center text-blue-600 mb-4">Bienvenido a Tailwind CSS</h1>
    
    <p class="text-gray-700 text-base mb-6">
      Tailwind CSS es un framework de utilidades que te permite diseñar de manera rápida y flexible.
    </p>
    
    <button class="w-full py-2 px-4 bg-blue-500 text-white font-semibold rounded hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-500">
      ¡Comienza ahora!
    </button>
  </div>

</body>
</html>
```