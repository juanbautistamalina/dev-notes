# HTML Y CSS

---

# HTML

## ***Etiquetas básicas***

- **`<h1></h1>, h2, h3, h4, h5, h6`**: Encabezados
- **`<p></p>`**: Párrafos
- **`<ol></ol>`**: Listas Ordenadas
- **`<ul></ul>`**: Listas Desordenadas
- **`<li></li>`**: Elementos de las listas
- **`<a href="https://enlace.com" title=”titulo”></a>`**: Enlaces
- **`<img src=”ruta”  alt=”texto alternativo”>`**: Colocar una imagen

## *Normalize*

- Es una hoja de estilos CSS creada para hacer que los navegadores presenten los elementos de manera más consistente y uniforme.
- [https://cdnjs.com/libraries/normalize](https://cdnjs.com/libraries/normalize)
- [https://necolas.github.io/normalize.css/](https://necolas.github.io/normalize.css/)

## ***Formularios***

- **`<form></form>`**: Crea un bloque de formulario (raíz del formulario)
- **`<label></label>`**: Es una forma de etiquetar individualmente cada input. Un dato importante de los label es que *no se puede modificar su margin ni su padding* debido a que son elementos en línea. Es por ello que es recomendable modificar el margin de los otros elementos, o modificar su line-height.
- **`<input type="…">`**: Sirve para que el usuario introduzca sus datos (**type** permite diferentes tipos de datos)
- **`<textarea></textarea>`**: Es una especie de input, pero con espacio para más texto
- **`resize (textarea)`**: Esta propiedad se utiliza en CSS y sirve para modificar la forma en la que se modifica el tamaño del textarea. Si se  coloca en none, no se puede modificar el tamaño del textarea.
- **`<select name="…"></select>`**: Son un tipo de campo de entrada que permite seleccionar una opción de varias.
- **`<option value=”…”></option>`**: Se utiliza para crear opciones dentro del select. *No se le puede dar padding ni margin*.
- **`<datalist list=”…“></datalist>`**: Es un input que se autocompleta con opciones predefinidas (similar al select). Utiliza la etiqueta option para las opciones. *Para usarlo se debe colocar primero un input con el atributo list y un contenido, luego la etiqueta datalist con el mismo id que list* y finalmente, dentro de la etiqueta datalist, los options.
- **`<fieldset></fieldset>`**: Sirve para encasillar o agrupar por tipo de dato que se pide.
- **`<legend></legend>`**:  Es una especie de título que se utiliza dentro del fieldset.

### ***Atributos de Formulario***:

- **`required`**: Obliga al usuario a completar un campo.
- **`disabled`**: Deshabilita el campo del formulario.
- **`readonly`**: Sólo se permite la lectura del campo y no su edición
- **`name`**: Sirve para identificar o nombrar  los datos, los campos, al recibirlos cuando se envía el formulario.
- **`placeholder`**: Texto de ejemplo
- **`minlength`**: Establece una longitud mínima para un campo del formulario
- **`maxlength`**: Establece una longitud máxima para un campo del formulario
- **`for`**: Este atributo se utiliza en label. *Para relacionar un label con un input*, hay que colocarle un id a un input y posteriormente colocar el mismo nombre del id en el for del label.  Otra forma de relacionar ambos es colocar el input dentro del label y ahorrarse el usar el id y el for.

---

## *Metaetiquetas, Comentarios e Íconos*

- **`<!— contenido —>`**: Comentario HTML
- **Ícono**: Se necesita una imagen de 32x32 o 64x64
    
    ```html
    <link rel="icon" href="favicon.ico" type="image/png">
    ```
    

- **Metatags**: Proporcionan información sobre la web
    - **`<meta charset="UTF-8">`**: Configura la codificación universal
    - **`<meta name="viewport" content="width=device-width, initial-scale=1.0">`**: Hace que todos los dispositivos se adapten a la página
    - **`<meta name="description" content="">`**: Colocar una descripción a la página web
    - `<meta name="keywords" content="">`: Colocar palabras clave
    - `<meta name="author" content="">`: Colocar el nombre del autor
    
    - **Metatags OG**: Preview de la página al compartirla en otras redes .
        
        *Link*: [https://metatags.io/](https://metatags.io/) 
        
        ```html
         		<meta name="OG:title" content="...">
            <meta name="OG:image" content="...">
            <meta name="OG:description" content="...">
            <meta name="OG:url" content="...">
        ```
        

## *Details y Summary*

- Proporcionan una funcionalidad para crear un menú desplegable.
- **`<details></details>`**: Esta etiqueta es un contenedor que posee  una flecha desplegable, en la cual, si se hace click, se mostrarán los valores escritos en summary.
- **`<summary></summary>`**: Esta etiqueta sirve para escribir en ella, de modo que será lo primero que aparecerá en el menú desplegable.

## *Enlaces*

- **Mandar un mail**: **`<a href=”mailto:ejemplo@gmail.com”></a>`**
- **Anclar un enlace con una sección de la página**: Para hacerlo, hay que colocarle un id a la sección o apartado de la página, y posteriormente colocar # y el nombre del id, dentro del atributo href de la etiqueta `<a>`. Por ejemplo: `<a href=”#inicio”></a>`
- **Descargar un archivo mediante un enlace**: Para hacerlo, primero hay que colocar en la etiqueta de enlace, el archivo que se quiere descargar y posteriormente colocar el atributo *download*.
- **Proteger privacidad de usuario (window.opener)**: Hay 2 formas
    - Utilizar el atributo `**rel=”noopener”**`
    - Utilizar el atributo **`rel=”noreferrer”`**
    
    Es recomendable usar el siguiente ejemplo: 
    
    ```html
    <a href="..." rel="noopener noreferrer nofollow"></a>
    ```
    

## *Tablas*

- **`<table></table>`**: Definir una tabla
- **`<thead></thead>`**: Define el encabezado de la tabla (dentro va el tr con sus th correspondientes)
- **`<tbody></tbody>`**: Define el cuerpo de la tabla (tr con td)
- **`<tfoot></tfoot>`**: Define el pie de la tabla
- **`<tr></tr>`**: Define filas dentro de la tabla
- **`<td></td>`**: Define celdas dentro de la fila
- **`<th></th>`**: Define una celda de encabezado

### ***Atributos***

- **`colspan=”…”`**: Sirve para expandir una celda (que ocupe más).

## *Audio y Video*

- **`<video controls autoplay muted src="…"></video>`**: Etiqueta para colocar un video. Dentro de la etiqueta, se puede colocar un texto en caso de que el navegador no soporte el video.

### ***Atributos***

- **`autoplay`**: Sirve para que el video se auto reproduzca
- **`controls`**: Habilita controles para el video
- **`muted`**: Mutea el video y permite que autoplay funcione
- **`loop`**: Reproduce el video en bucle

## *Carga Diferida - Lazy Loading*

- **`<img src="…" loading=”lazy”>`**: Este atributo permite que los archivos de una página web, como imágenes, por ejemplo, carguen cuando el usuario haga scroll y llegue a esa sección de la página, para que de esta forma, la página pueda funcionar con un mayor rendimiento.

## *HTML Semántico*

- **`<header></header>`**: Encabezado de la página. Normalmente contiene imágenes, logotipos, barras de navegación.
- **`<nav></nav>`**: Sirve para crear una barra de navegación
- **`<main></main>`**: Es el contenido principal de la página (similar a section)
- **`<aside></aside>`**: Sección secundaria, relacionada con el contenido principal pero no tanto
- **`<section></section>`**: Hace referencia a una sección de contenido
- **`<footer></footer>`**: Pie de página (derechos de autor)

## *Accesibilidad*

### **Atributos**

- **`aria-label="…"`**: Atributo que se coloca en las etiquetas. Dentro de este atributo, se escribe una descripción de lo que es un elemento, o a dónde te lleva un determinado elemento o etiqueta. Esto sirve para los lectores de pantalla.
- **`role=""`**: Asigna un rol a un elemento.
    - [https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles)

---

# CSS

## ***Integrar CSS en HTML***

```html
<link rel="stylesheet" href="style.css">
```

## ***Selectores***

- **Universal** *
- **De Tipo** (por etiqueta)
- **Clase** (.class)
- **ID** (#id)
- **Atributo** ( [nombre-atributo = valor] )
- **Descendiente**: EJ: h1 p{ … }
- **Pseudo-clases**: h1:hover {…}
- **Hermano siguiente**: p ~ span
- **Hermano directo**: p + span

## ***Propiedades***

- **`color`**: modifica el color del texto
- **`font-family`**: tipografía de la letra
- **`font-size`**: tamaño de la letra
- **`font-weight`**: grosor de la letra
- **`font-style`**: aspecto de la letra
- **`text-align`**: alinea texto dentro de su contenedor (left, right, center)
- **`text-decoration`**: subraya al texto
- `line-height`: interlineado. Está formado por el tamaño asignado al font-size + el line-height que se aplique.
- **`letter-spacing`**: espaciado entre letras
- **`text-transform`**: modifica al texto (uppercase, lowercase, capitalize)

## ***Importar Fuentes***

- **Opción 1**: etiqueta `<link>` o `@import`

```html
<!-- OPCIÓN 1: EN HTML  -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap" rel="stylesheet">

<!-- OPCIÓN 2: EN CSS-->
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');
```

- **Opción 2**: Crear tipografías
    - *Paso 1*: Crear un nuevo archivo llamado `fonts.css`.
    - *Paso 2*: Crear una carpeta llamada `fonts`, y dentro colocar los archivos de la fuente, que deben ser descargados en primer lugar.
    - Paso 3: Utilizar la etiqueta link para vincular el nuevo archivo css en el html
    - Paso 4: En el nuevo archivo, crear las fuentes

```css
/*ESTRUCTURA*/
@font-face{
	font-family: (nombre de la fuente);
	src: url(ruta local donde se descargó la fuente) format(”truetype”);
	font-weight: (...)
}

/*EJEMPLO*/
@font-face{
	font-family: "Roboto";
	src: url(fonts/Roboto-Regular.ttf) format("truetype");
	font-weight: 400;
}
```

## ***Modelo de Caja - Box Model***

- **`content`**: área donde se muestra el texto.
- **`padding`**: espacio entre el contenido y el borde del elemento (top right bottom left).
- **`border`:** línea que rodea tanto al contenido como al padding.
- **`margin`**: distancia entre caja y otras cajas o elementos. Espacio alrededor de la caja, que está fuera del borde. Separa el elemento de otros elementos. NO forma parte de la caja. (top right bottom left)

![Box Model](./imagenes/HTML%20y%20CSS/box-model.png)

### ¿Cómo centrar horizontalmente los elementos?

- Utilizando `margin: auto`

## ***Bordes***

- **`border-width`**: tamaño del borde (**top, right, bottom, left**)
- **`border-style`**: estilo del borde (**solid, dashed, double, groove, dotted, hidden**)
- **`border-color`**: color del borde
- **`border-radius`**: redondear bordes (porcentaje o pixeles)
- **`border`**: (width)  (style)  (color)
- **`(border-top, border-bottom, border-left, border-right)`**: Modificar border individuales
- **`(border-top-left-radius, border-top-right-radius, border-bottom-left-radius, border-bottom-right-radius)`**: Modificar el redondeo de cada borde individualmente

## ***Box-Sizing - Tamaño de Caja***

- Se utiliza para afectar el modelo de caja predeterminado. Determina como se calcula el tamaño de un elemento
    - **`box-sizing: content-box`:** El tamaño de la caja está formado por el contenido, padding y border  →  **width + padding + border** (valor por defecto).
    - **`box-sizing: border-box`:** El tamaño de la caja incluye el contenido, el padding y el borde.  → **width - padding - border**. En resumen, *el padding y el border pasan a formar parte del width total y se respeta el width colocado por el programador*.

## ***Colorización***

- **`RGB (red, green, blue)`**: Cada uno de los 3 colores abarca de 0 a 255. Donde todos en 0 es el color negro, y todos en 255 es el color blanco.
- **`RGBA (red, green ,blue, alpha)`**: Es una variación de rgb. Pero en el último parámetro, se añade la opacidad, la cual va de 0 a 1, y se usan valores entre esos dos valores. (0 es transparente y 1 es opaco).

- **`Hexadecimal`**: Usa valores de 0 a 9 y de a hasta f, para cada color.
    
    [https://htmlcolorcodes.com/color-picker/](https://htmlcolorcodes.com/color-picker/)
    
    ![Hexadecimal](./imagenes/HTML%20y%20CSS/hexadecimal-color.png)
    

- **`HSL`**: **(hue, saturation, lightness)**
    
    ![HSL Colores](./imagenes/HTML%20y%20CSS/hsl-color.png)
    


## ***Unidades de Medida***

- **`px`**: Píxeles
- **`em`**: 1em = font-size del elemento padre. Por defecto 1 em = 16px
- `rem`: 1rem = font-size del elemento raíz (html)
- **`vw`**: viewport width. Ancho total de la página (visible)
- **`vh`**: viewport height. Largo total de la página (visible)
- `mm`: Milímetros
- `cm`: Centímetros
- `%`: Porcentaje respecto al contenedor del elemento

### ***¿Cuándo usar cada unidad de medida?***

- Tamaños de Fuente, espaciados y tipografía en general: **`em y rem`**
- Layouts o dimensiones de elementos: **`Porcentajes, em, rem, vw o vh`**

## ***Fondos***

- **`background-color`**: color de fondo
- **`background-image: url()`**: colocar una imagen de fondo
- **`background-size`**: especifica el tamaño de las imágenes de fondo. **(%, px)**
    - **`100%`**: Se ajusta a lo ancho
    - **`contain`**: obliga al contenedor a que la imagen entre por lo menos una vez.
    - **`cover`**:  No importa la resolución, la imagen se va a adaptar
- **`background-position`**: especifica la posición de las imágenes de fondo **(center, left, right, top, bottom)**
- **`background-repeat`**: especifica si la imagen de fondo de repite o no **(repeat, no-repeat, repeat-x. repeat-y)**
- **`background-attachment`**: determina si la posición de la imagen de fondo será fija dentro de la pantalla o se desplazará con su bloque contenedor. Es un efecto **(scroll, fixed)**

## ***Gradientes***

- *Lineal - Linear*:
    - **`background: linear-gradient(color-1, color2)`**: Gradiente que va de un color a otro.
    - **`background: linear-gradient(to right, color-1, color2)`**: Gradiente que va de izquierda a derecha.
    - **`background: linear-gradient(to left, color-1, color2)`**: Gradiente que va de derecha a izquierda.
    - **`background: linear-gradient(to bottom, color-1, color2)`**: Gradiente que va de arriba hacia abajo.
    - **`background: linear-gradient(to top, color-1, color2)`**: Gradiente que va de abajo hacia arriba.

- *Otros Gradientes*:
- **`background: radial-gradient(color1, color2)`**: Gradiente que parte del centro hacia los alrededores.
- **`background: conic-gradient(color1, color2)`**: Gradiente en forma de cono.

## ***Sombras***

- **`box-shadow: horizontal-px  vertical-px  desenfoque-px  expansión-px  color`**: Se utiliza para colocarle sombras a los elementos (cajas). El primer parámetro es el movimiento horizontal de la sombra (izquierda o derecha), el segundo es el movimiento vertical (arriba o abajo). *Recomendación: Únicamente modificar el desenfoque y el color*.
    - ***horizontal***: Los valores negativos desplazan hacia la izquierda, y los valores positivos hacia la derecha.
    - ***vertical***: Los valores positivos desplazan hacia abajo y los valores negativos hacia arriba.
- **`text-shadow: horizontal-px    vertical-px   desenfoque-px   color`**: Se utiliza para colocarle sombras al texto
- **`filter: drop-shadow(horizontal-px   vertical-px  desenfoque-px  color)`**: Se utiliza específicamente para darle sombra a imágenes png sin fondo.

## ***Selectores Avanzados***

- **`img[src = "…"]`**: ***Selector por atributo.*** Para hacerlo se coloca, en primer lugar el elemento, posteriormente y entre corchetes el atributo seguido de su valor.
- **`ul > strong`**: ***Selector por hijo directo***. Esto significa que se van a seleccionar todos aquellos elementos que sean hijos directos del elemento padre (diferente de ul strong).
- **`h1 + p`**: ***Selector de hermano adyacente***. Selecciona al elemento que está inmediatamente a continuación de otro elemento, o en otras palabras, que es hermano de otro elemento.
- **`elemento ~ elemento`**: ***Selector de hermano general***. Selecciona a todos los elementos (iguales) que están a continuación de un primer elemento.

## *Herencia, **Cascada y Especificidad***

- **`propiedad: inherit`**: Hace que herede una determinada propiedad de su padre, es decir, el elemento que lo contiene.
- **`propiedad: initial`**: Hace que utilice el valor por defecto, para esa propiedad y que no herede la propiedad trabajada.
- Cuando la especificidad es exactamente igual, el valor resultante va a ser la última aplicada.
    
    ![Especificidad](./imagenes/HTML%20y%20CSS/especificidad.png)
    

## ***Pseudoclases***

- Link: [https://developer.mozilla.org/es/docs/Web/CSS/Pseudo-classes](https://developer.mozilla.org/es/docs/Web/CSS/Pseudo-classes)

### ***Enlaces***

- **`elemento:hover`**: cambiar los estilos de un elemento cuando está el mouse encima.
- **`elemento:link`**: cambiar los estilos de un link que no fue visitado.
- **`elemento:visited`**: cambiar los estilos de un link ya visitado.
- **`elemento:active`**: cambiar los estilos de un elemento que se mantiene presionado.

### ***Otros***

- **`elemento:first-child`**: Seleccionar el primer elemento de varios iguales.
- **`elemento:last-child`**: Seleccionar el último elemento de varios iguales.
- **`elemento:nth-child(n)`**: Seleccionar un elemento determinado de varios hijos. Donde n es el número de elemento.
- **`elemento:nth-child(num n)`**: Seleccionar un varios elementos de un conjunto de hijos, siguiendo un patron de x. Donde num es el número de elemento. (num y n juntos, sin espacios).
- **`elemento:nth-of-type(n)`**: Seleccionar varios elemento de un conjunto iguales, del mismo tipo.
- **`elemento:not(…)`**: Seleccionar elementos que no cumplen con una determinada consigna. Por ejemplo, seleccionar a todos los elementos que no tienen una determinada clase.
- **`elemento:focus`**: Se aplica a los inputs. cambia los estilos de un elemento cuando está enfocado.
- **`elemento:empty`**: Seleccionar elementos vacíos.
- **`:root`**: Selecciona al elemento raíz.
- **`elemento:valid`**: Selecciona elementos que son válidos. Por ejemplo, un input de tipo email, que posee escrito un email que es válido.
- **`elemento:invalid`**: Selecciona elementos que no son válidos. Por ejemplo, un input de tipo email que posee un email escrito incorrectamente (no válido)
- **`elemento:is(…, …, …)`**: Permite agrupar varios selectores en uno solo.
    
    ```css
    /*Modificando los elementos 1, 2 y 3 (clases) que están dentro de algún section*/
    section:is(.elemento1, .elemento2, .elemento3){
    	...
    }
    ```
    
- **`elemento:where(…, …, …)`**: Igual a is, pero tiene menos especificidad.
- **`elemento:has(…)`**: Se le da al elemento padre, el contenedor, por lo que será modificado el contenedor y no el contneido. Verifica si el elemento padre tiene algo (dentro).
    
    ```css
    /*En caso de que a ul le siga un div, se modifica UL. */
    ul:has(+div){
    	...
    }
    ```
    

## *Pseudoelementos*

- **`elemento::first-letter`**: Sirve para modificar alguna propiedad de la primera letra de un texto. Solo elementos en bloque.
- **`elemento::first-line`**: Funciona solamente en elementos de bloque. Sirve para modificar alguna propiedad de la primera línea de un texto (ya sea block o inline-block)
- **`elemento::selection`**: Sirve para modificar las propiedades de cuando seleccionamos algo con el mouse al mantener click izquierdo.
- **`elemento::placeholder`**: Sirve para modificar las propiedades de los elementos que posean placeholder.
- **`elemento::before`**: No existe en el DOM. Necesita del atributo content. Sirve para añadir contenido antes de algo.
- **`elemento::after`**: No existe en el DOM. Necesita del atributo content. Sirve para añadir contenido después de algo.
- **`li:marker`**: Modifica los puntos que tienen los elementos li.

## *Metodología BEM*

- Se separa en 3 partes: Bloque - Elemento - Modificador.
    - ***Bloque***: Componente independiente que no depende de nadie para existir.
    - ***Elemento***: Hace referencia a una parte de un bloque, que por sí solo no tiene sentido.
    - ***Modificadores***: Una forma de modificar un bloque o un elemento

Los bloques se tienen que nombrar con la funcionalidad que tienen. Para nombrar los elementos se coloca primero en nombre del bloque y, suponiendo que dentro de ese bloque haya otros elementos se colocan 2 guiones bajos seguidos del nombre del elemento.

*Por Ejemplo*: 

```css
<ul class="lista">
        <li class="lista__item"></li>
        <li class="lista__item"></li>
        <li class="lista__item"></li>
        <li class="lista__item"></li>
        <li class="lista__item"></li>
</ul>
```

![Metodología BEM](./imagenes/HTML%20y%20CSS/metodologia-bem.png)

En caso de querer modificar un elemento en específico, lo que se hace es, dentro de el nombre de la clase, colocar un espacio seguido de el nombre del elemento, luego dos guiones medios y el nombre de la modificación.

Por ejemplo:

```css
<ul class="lista">
        <li class="lista__item item--importante"></li>
</ul>
```

## ***Display***

- **`block`**: ocupa toda la línea. → Se puede modificar su tamaño (width y height)
- **`inline`**: ocupa solo lo que tiene de contenido. NO se puede modificar su tamaño
- **`inline-block`**: Permite modificar el tamaño (width y height) y se comporta como inline.
- **`none`**: El elemento no ocupa espacio en la página, ni se ve visualmente. Los demás elementos se comportan como si el elemento con display none no estuviera.

## ***Position***

- **`z-index`**: Esta propiedad determina la superposición de elementos (elementos encima de otros) (más es más)
- **`inset`**: Es un atajo para top, right, bottom y left en uno solo.
- **`static`**: valor por defecto. No funcionan top, right, bottom y left
- **`relative`**: El elemento mantiene su posición original, es decir que el hueco que ocupa la caja realmente se mantiene, pero permite mover el elemento. Otro dato importante es que prevalece top y left. El punto de referencia que tiene el elemento es su posición original.
- **`absolute`**: El elemento no ocupa lugar en la página. El punto de referencia que tiene el elemento con position absolute por defecto, es la etiqueta html. Para cambiar el punto de referencia hay que posicionar a su contenedor de forma relativa. Cuando se posiciona un elemento ya sea con top, bottom, left o right, por ejemplo, quiere decir que el elemento se posiciona en x medida (por ejemplo 10px) desde la posición indicada, partiendo de esa posición.
- **`fixed`**: El elemento no ocupa lugar en la página, además se mantiene fijo en la pantalla, a la hora de hacer scroll. Siempre se va a posicionar respecto a la ventana (viewport)
- **`sticky`**: Se utiliza en elementos que se encuentran dentro de un contenedor. Su comportamiento es como  fixed a partir de una cantidad definida de px.

## ***Transiciones***

- Permiten cambiar un elemento que transicione de un estado inicial a un estado objetivo.
- **`transition-duration`**: Permite modificar la duración de una transición
- **`transition-property`**: Permite establecer las propiedades a las que se le van a aplicar la transición (por defecto: all)
- **`transition-timing-function`**: Permite establecer las velocidades (inicio, medio y final) de la animación. Algunos de sus posibles valores son: ease, ease-in, ease-out, ease-in-out, step(), cubic-bezier().
- **`transition-delay`**: Permite establecer un delay al elemento.
- **`transition`**: Esta propiedad contiene a transition-duration, transition-property, transition-timing-function y transition-delay. La forma más utilizada de pasarle los valores es la siguiente: `transition: propiedad duración animación delay`

- **Ejemplo de transición sencillo**

```css
.elemento{
	transition: background .3s linear 
}
```

- **Ejemplo de transición con hover y al quitar el mouse por encima**

```css
.elemento{
	width: 50px;
	height: 50px;
	background: #09f;
	border-radius: 50%;
	transition: all 300ms ease-in-out /* la segunda animación */
}

.elemento:hover{
	scale: 2;
	background: red;
	box-shadow: 0 0 10px red;
	transition-duration: 1s /* la primera animación*/
}
```

## ***Overflow***

- Se utiliza cuando el contenido de una caja sobrepasa la caja)
- **`overflow: visible`**: valor por defecto. El contenido sobrepasa la caja.
- **`overflow: hidden`**: Oculta todo aquello que sobrepase la caja.
- **`overflow: scroll`**: Obligatoriamente coloca la barra de scroll a pesar de que no haga falta.
- **`overflow-x`**: Controla el desbordamiento en el eje X.
- **`overflow-y`**: Controla el desbordamiento en el eje Y.
- **`overflow: auto`**: Detecta automáticamente si el contenido sobrepasa la caja, en dicho caso permite hacer scroll dentro de ella.

### ***Control de flujo de texto***

- **`white-space: normal`**: Valor por defecto, el contenido se adapta a la caja.
- **`white-space: nowrap`**: El contenido se mantiene en una sola línea, sin saltos de línea.
- **`white-space: pre`**: El contenido detecta cómo el desarrollador escribió el html y lo ajusta de la misma forma en la que el desarrollador lo haya escrito (incluyendo los saltos de línea).
- **`white-space: pre-wrap`**: Es similar a pre, con la diferencia de que si hay desbordamiento, lo corrige.
- **`text-overflow: elipsis`**: Muestra 3 puntos a modo de continuación, cuando el texto se desborda. Se utiliza en conjunto con las propiedades white-space y overflow.
- **Resumen**: Si se está desbordando algo, usar: **white-space: nowrap**, **text-overflow: elipsis** y **overflow: hidden**. 
Para balancear textos usar **text-wrap: balance**, y para balancear párrafos usar **text-wrap: pretty**.

## ***Object Fit y Object Position***

- **Object Fit**: Se utiliza cuando se le da un tamaño a una imagen y esta se deforma.
- **`object-fit: fill`**: Valor por defecto. La imagen se adapta. NO mantiene la relación de aspecto.
- **`object-fit: contain`**: Hace que la imagen entre al menos una vez en la resolución dada.
- **`object-fit: cover`**: La imagen se adapta al contenedor (ocupa todo el contenedor).

- **Object-Position**: Se utiliza en conjunto con **object-fit**.
- **`top`**: Coloca la imagen más sobre la parte de arriba
- **`bottom`**: Coloca la imagen más sobre la parte de abajo
- **`left`**: Coloca la imagen más sobre la parte izquierda
- **`right`**: Coloca la imagen más sobre la parte derecha

## ***Outline***

- **`outline: (width) (style) (color)`**: Borde por fuera de la caja. Esta propiedad no mueve al elemento en caso de que se aumente el tamaño del borde del outline, como sí ocurre con border. Tiene las mismas propiedades que **border**. No afecta al DOM.
- **`outline-offset`**: Define cuanto se va a separar el outline (contorno) del borde
- **Diferencia entre border y outline**: El borde afecta al contenido, mientras que el contorno o outline es algo que se dibuja encima del contenido y no lo afecta.
- **Desactivar bordes de los input**:
    
    ```css
    input:focus-visible{
        outline: none;
    }
    ```
    

---

## *Flexbox*

```css
/* RESUMEN DE LAS PROPIEDADES MÁS USADAS DE FLEXBOX*/

.container{
	display: flex; 
	flex-flow: row wrap; /* flex-direction y flex-wrap */
	flex-direction: row; /* Dirección de items: row, row-reverse, column, column-reverse. */
	flex-wrap: wrap; /* wrap, nowrap. Comportamiento de los items*/
	justify-content: center; /* alinear los items en el eje principal (main axis) */
	align-items: center; /* alinear los items en el eje cruzado (cross axis) */
	gap: 5px; /* Dejar espacios de separación entre los items*/
}

.item{
	flex: 1; /* Los elementos pueden crecer, reducir su tamaño y los items tienen el mismo tamaño*/
	flex-grow: 1; /* 0: Los elementos no crecen. 1: Los elementos se adecuan al contenedor */
	flex-shrink: 1; /* Los elementos reducen su tamaño más pequeño que su flex basis*/
}
```

- **`display: flex`**: Esta propiedad se aplica a un caja contenedora. Dicha propiedad hace que las cajas que se encuentren dentro del contenedor adquieran diferentes comportamientos.
- **`gap`**: Sirve para dejar espacios entre elementos flex. Solo afecta la distancia *entre* elementos, no en los laterales.
- **`main-axis`**: De izquierda a derecha (por defecto)
- **`cross-axis`**: De arriba hacia abajo (por defecto)
- Los **flex items**, ocupan el cross axis al completo en caso de que no tengan un width o height definido.

![Flex-Row](./imagenes/HTML%20y%20CSS/flex-row.png)

![Flex Row-Reverse](./imagenes/HTML%20y%20CSS/flex-row-reverse.png)

![Flex-Column](./imagenes/HTML%20y%20CSS/flex-column.png)

![Flex-Column-Reverse](./imagenes/HTML%20y%20CSS/flex-column-reverse.png)

![Ejes en Row](./imagenes/HTML%20y%20CSS/row-ejes.png)

![Ejes en Row-Reverse](./imagenes/HTML%20y%20CSS/row-reverse-ejes.png)

![Ejes en Column](./imagenes/HTML%20y%20CSS/column-ejes.png)

![Ejes en Column-Reverse](./imagenes/HTML%20y%20CSS/column-reverse-ejes.png)

### Propiedades del flex-container

**`flex-direction`:** Modifica la dirección de los elementos (**main axis**). 

- **`flex-direction: row`**: Los elementos se mostrarán en fila
- **`flex-direction: column`**: Los elementos se mostrarán en columnas
- **`flex-direction: row-reverse`**: Los elementos se muestran en filas pero al revés (el primer elemento es el último y el último es el primero)
- **`flex-direction: column-reverse`**: Los elementos se muestran en columna pero al revés (el primer elemento es el último y el último es el primero)

**`flex-wrap`:** Permite controlar el comportamiento de los flex items, una vez que el espacio en contenedor es insuficiente para abarcar a esos elementos.

- **`flex-wrap: nowrap`**: Valor por defecto. El contenido se ajusta al contenedor. Si no hay suficiente espacio en el contenedor, los elementos se van a desbordar. Los elementos que estén dentro del contenedor, van a disminuir su tamaño para respetar el tamaño especificado del contenedor.
- **`flex-wrap: wrap`**: Si no hay suficiente espacio en el contenedor, en el caso de que los elementos no quepan en la primera fila,  los elementos pasan a la siguiente línea.

**`flex-flow`:** 

- **`flex-flow: direction wrap`**: Permite definir la dirección y el wrap en una sola. Es un atajo que junta flex-direction y flex-wrap.

**`justify-content`**: Alinea los ítems en el *eje principal*. (MAIN AXIS) → Depende del flex-direction

- **`justify-content: start`**: Valor por defecto. Los elementos están alineados en la misma dirección que el texto.
- **`justify-content: flex-end`**: Coloca los elementos al final del contenedor.
- **`justify-content: center`**: Centra los elementos en el contenedor, sin dejar espacios entre elementos.
- **`justify-content: space-between`**: Coloca el primer elemento y el último contra los bordes y los que estén en el medio los separa con la misma distancia. A los laterales no deja espacios, pero entre elementos deja espacio.
- **`justify-content: space-around`**: Hay espacio entre elementos. A los laterales es el mismo espacio, pero entre elementos hay un poco más, ya que es la suma de un elemento y el de al lado.
- **`justify-content: space-evenly`**: El espacio que hay entre elementos es el mismo.

**`align-items`**: Alinea los ítems en el eje cruzado (CROSS AXIS) → Depende del flex-direction. 

- **`align-items: stretch`**: Valor por defecto. Los ítems se estiran para llenar el cross axis (en caso de que no tengan un height definido)
- **`align-items: start`**: Los ítems ocupan solamente el contenido de lo que tienen dentro y los posiciona al principio del cross axis.
- **`align-items: end`**: Los ítems ocupan solamente el contenido de lo que tienen dentro y los posiciona al final del cross axis.
- **`align-items: center`**: Centra los elementos en el contenedor.
- **`align-items: baseline`**: Alinea los ítems teniendo en cuenta la dirección del texto.

`align-content`: Funciona igual que align-items, solo que se utiliza cuando hay 2 o más líneas. Cuando hay solo una línea, **align-content** no tiene efecto. 

- **`align-content: start`**: Coloca los elementos en el comienzo del contenedor
- **`align-content: end`**: Coloca los elementos al final del contenedor
- **`align-content: center`**: Centra los elementos en el contenedor.

---

### *Diferencia entre align-items y align-content*

**Align-items** funciona bien sólo cuando se trabaja con 1 sola fila, mientras que para 2 o más filas hay que usar **align-content**. 

Si sólo usamos align-items y tenemos más de una fila de elementos, el conjunto de ítems no se centrará respecto del contenido sino que se repartirá entre el espacio disponible

Por esa razón es recomendable usar ambos, de forma que si sólo ocupa una línea, sea align-items el que se encargue y si hay múltiples, se encargue align-content.

![align-items](./imagenes/HTML%20y%20CSS/align-items.png)

![align-content](./imagenes/HTML%20y%20CSS/align-content.png)

---

### *Centrar elementos con Flexbox*

- En caso de tener un solo elemento, hay que colocarlo en un contenedor. A ese contenedor se le coloca un display flexbox, y al ítem se le coloca un margin auto.

---

### Propiedades de los flex-items

**`align-self`**: Posicionar o alinear elementos individuales en el eje cruzado (cross axis). *Esta propiedad solamente funciona si se está utilizando la propiedad align-items en el contenedor*. 

- **`align-self: center`**: Centra el elemento en el contenedor, en forma de columna
- **`align-self: flex-start`**: Coloca el elemento al inicio de la columna
- **`align-self: flex-end`**: Coloca el elemento al final de la columna

**`order`**: Esta propiedad sirve para modificar el orden en el que se representan los elementos visualmente en la pantalla (los elementos no cambian su posición en el DOM). 

Por defecto, todos los elementos tienen un order de 0. **Se ordena de menor valor a mayor valor**.

**`flex-grow`**: Sirve para rellenar el espacio sobrante, por ejemplo en un contenedor en el que los elementos ocupan solo una parte. 

- **`flex-grow: 0`**: (valor por defecto) Los elementos no crecen.
- **`flex-grow: 1`**: Los elementos crecen.

**`flex-shrink`**: Determina la capacidad para encogerse. 

- **`flex-shrink: 0`** : Los elementos no van a reducir su tamaño.
- **`flex-shrink: 1`**:  (valor por defecto) Los elementos pueden reducir su tamaño a un tamaño más pequeño que su flex-basis (por defecto, el flex-basis es auto)

**`flex-basis`**: En los flex items, no se usa el width, se usa el flex-basis, para establecer el tamaño base.

- **`flex-basis: auto`**: Valor por defecto.
- **`flex-basis: ...px`**: Defien el tamaño base del flex item. Por lo general va acompañado de min-width.
- **`flex-basis: 0`**: El tamaño base de los flex items es de 0.

**`flex`**: 

- **`flex: flex-grow  flex-whrink  flex-basis`**: Permite definir la capacidad de agrandarse, encogerse y el tamaño base de un flex item en una sola. Es un atajo que junta flex-grow, flex-shrink y flex-basis.

---

## *Responsive Design*

- **`width`**: establece la anchura de un elemento. El problema con width ocurre cuando la ventana del navegador es más pequeña que el ancho que se le da al elemento. Cuando eso ocurre, el navegador agrega una barra de desplazamiento horizontal a la página
- **`max-width`**:  Se utiliza para establecer el ancho máximo de un elemento especificado. Si el tamaño es menor al especificado en esta propiedad, el elemento se adapta.
- **`min-width`**:  Se utiliza para establecer un ancho mínimo de un elemento especificado. Se utiliza en conjunto con **max-width** para darle al elemento un rango en el cual mantenerse.

- **`height`**: Establece la altura de un elemento. No es recomendable utilizar esta propiedad ya que el contenido de los elementos se desborda en caso de colocar una medida menor al contenido.
- **`min-height`**: Se recomienda el uso de esta propiedad para darle un alto a los elementos. Al utilizar esta propiedad el elemento va a medir lo establecido como mínimo. Si se añade contenido, el contenedor se va a adaptar pero nunca va a ser más pequeño que lo establecido.

### **Atributos (HTML) srcset y sizes**

Son atributos de HTML que trabajan en conjunto para poder cargar imágenes responsivas. Permiten al navegador elegir cuál debería ser la imagen adecuada según una determinada condición. 

**Ejemplo**: 

```html
<img src="img-small.png"
    srcset="img-small.png 400w, img-medium.png 600w, img-big.png 1000w"
    sizes="(max-width: 400px) 300px,
    (max-width: 600px) 500px, 900px">
```

- `sizes`: Si la pantalla tiene una resolución de 400px de ancho o menos, carga imágenes de hasta 300 píxeles. Si tiene menos de 600 va a cargar imágenes de 500px. Y en caso de que ninguno de los casos anteriores ocurra, es decir, en caso que sea superior a 600px, va a cargar imágenes de 900px.

**Picture, Source, Media**

- **<picture></picture>**: Funciona para especificar múltiples fuentes para una imagen.
    
    *Ejemplo*: (primero colocar las resoluciones más pequeñas)
    
    ```html
    <picture>
    	<source media="(max-width: 400px)" srcset="img-small.png">
    	<source media="(max-width: 600px)" srcset="img-medium.png">
    	<img src="img-original.png">
    </picture>
    ```
    

---

## ***Media Queries***

- Su objetivo es adaptar una página web a diferentes resoluciones. Para ello se definen estilos distintos según la resolución.

![Media Queries](./imagenes/HTML%20y%20CSS/media-queries.png)

- **`@media`**: Inicia la media querie.
- **`not|only`**: Son operadores opcionales. ***not*** excluye al los dispositivos que cumplen con la consulta *(no aplicar un estilo a determinados dispositivos)*, mientras que ***only*** se usa para que navegadores antiguos que no soportan media queries apliquen los estilos definidos en la consulta.
- **`mediatype`**: Indica el tipo de medio al que se dirige la consulta.
- **`and`**: Es opcional. Se utiliza para combinar varias expresiones en una consulta
- **`expressions`**: Evalúan características específicas del dispositivo.

**Mobile First**: Consiste en crear la página web primero adaptada a dispositivos móviles y a partir de ahí adaptarla a resoluciones más grandes. 

---

### ***Grid***

- ***Grid Container***: Es el elemento padre que se define con **display:grid**.
- **Grid Items**: Son los hijos directos del grid container.
- Al definir un contenedor como grid, los hijos (si no hay nada definido), pasan a ser filas (por defecto).
- ***GRID ITEM ES DISTINTO DE GRID CELL:*** Un grid item es un hijo directo de un grid container, mientras que un grid cell es el espacio real almacenado en la que va a ser colocado el elemento.

![Grid Cell](./imagenes/HTML%20y%20CSS/grid-cell.png)

![Grid Item](./imagenes/HTML%20y%20CSS/grid-item.png)

***Las siguientes propiedades se aplican al CONTENEDOR***: 

- **display: grid**: Esta propiedad se aplica a un caja contenedora.

- **grid-template-columns:** Definir la cantidad de columnas y su width. Se coloca una unidad de medida para hacer referencia a una columna. Cada vez que se añada una medida, hará referencia a una nueva columna.
- **grid-template-rows**: Definir la cantidad de filas y su height. Se coloca una unidad de medida para hacer referencia a cada fila.

- Tanto a grid-template-columns como a grid-template-rows se le puede establecer un tamaño de auto. Esto hará que la celda ocupe el tamaño restante. Hace que el tamaño de la columna o fila sea automático, es decir, se adapta al contenido y al espacio disponible dentro del contenedor.

**Medidas**: 

- **1fr** = 100%. No tiene en cuenta el contenido. Se utiliza para que cada columna o fila mida lo mismo.  Una fracción del espacio disponible en el contenido de la cuadrícula. *Por ejemplo, si se le dan a todas las columnas o filas 1fr, funcionan igual que flex-grow*.

**Propiedades**: 

- **repeat**(cantidad-de-veces, medida): Sirve para repetir una determinada cantidad de veces la misma medida para crear columnas o filas.
    
    ```css
    /*Crea 4 columnas de 1fr cada una.*/
    grid-template-columns: repeat(4, 1fr)
    ```
    

- **minmax(mínimo, máximo)**: Permite establecer un tamaño mínimo y un tamaño máximo para las columnas o filas de la cuadrícula *grid. Se coloca ya sea en grid-template-columns o en grid-template-rows. (Es similar a darle un max-width y un min-width).*
    
    ```css
    grid-template-columns: repeat(2, minmax(100px, 200px)) 1fr;
    ```
    

**Grid Explícito e Implícito**: 

- Grid Explícito es cuando se establecen la cantidad de columnas y/o filas de forma explícita, es decir, escritas en el código.
- Grid Implícito es todo aquello que se realiza de manera automática. Abarca la forma en que los elementos que no fueron tratados, se comportan y se muestran.

- **grid-auto-rows**: Sirve para colocarle un tamaño específico a las filas creadas automáticamente por grid.

- **grid-auto-flow**: Sirve para establecer el flujo de creación de nuevos elementos. Estos pueden crearse en forma de filas, por defecto, o en forma de columnas (row, column).

- **column-gap**: Es el espacio que hay entre cada columna. Similar al margin.
- **row-gap**: Es el espacio que hay entre cada fila. Similar al margin.
- **gap**: **filas columnas:** (es el atajo de column-gap y row-gap)
- Para añadir una *distancia entre los grid-items y los border del contenedor,* hay que añadir un padding de la misma medida que se le dio al gap.

**Grid Dinámico (y Responsive)**: 

- **auto-fill**: Le dice al navegador que inserte el número de columnas o filas que sea necesario para rellenar el espacio.
- **auto-fit**: Estira el contenido hasta los límites del contenedor.  Ajusta las columnas para ocupar todo el espacio disponible, sin dejar espacio restante

***Las siguientes propiedades se aplican a los FLEX ITEMS (hijos directos de un contenedor flex)***: 

**Grid Column y Grid Row**: 

- **grid-column-start**: Define la línea a partir de la cual va a comenzar el elemento, en forma de columna.
- **grid-column-end**: Define la línea en la que va a terminar el elemento, en forma de columna.
- **grid-column-end: span n**: Donde n es un número que indica cuántas columnas más va a ocupar partiendo de su posición inicial.
- **grid-column: n1/n2**: Es un atajo de grid-column-start y grid-column-end. El primer valor es el start y el segundo es el end.

- **grid-row-star**t: Define la línea a partir de la cual va a comenzar el elemento, en forma de fila.
- **grid-row-end**: Define la línea a partir de la cual va a terminar el elemento, en forma de fila.
- **grid-row-end: span n**: Donde n es un número que indica cuántas filas más va a ocupar partiendo de su posición inicial.
- **grid-row: n1/n2**: Es un atajo de grid-row-start y grid-row-end. El primer valor es el start y el segundo es el end.

**Grid Areas:** Permite crear una especie de layout. 

- **grid-template-areas**: Se aplica al contenedor grid.
- grid-area: Sirve para nombrar a cada elemento y luego trabajar de forma “gráfica” (ELEMENTOS)
- grid-template-areas: Sirve para posicionar los elementos gráficamente. (CONTENEDOR)

```css
grid-template-areas:
    "header header header"
    "main main aside"
    "footer footer footer";
```
---

## Grid (explicado de otra manera)

- **Lenguaje CSS (Explicaciones)**: [https://lenguajecss.com/](https://lenguajecss.com/)
- **Curso de Google**: [https://web.dev/learn/css?hl=es](https://web.dev/learn/css?hl=es)
- **Documentación**: [https://developer.mozilla.org/es/docs/Web/CSS](https://developer.mozilla.org/es/docs/Web/CSS)

## **Propiedades**

- **display: grid**: Convierte al contenedor en una cuadrícula
- **grid-template-column**: Permite modificar la cantidad de columnas que tendrá la cuadrícula, y su medida.
- **grid-template-rows**: Permite modificar la cantidad de filas que tendrá la cuadrícula, y su medida.
- **justify-items**: Permite alinear dentro de la celda (de izquierda a derecha) los grid items. Algunos de sus valores son: start, end, center. *Se aplica al contenedor padre*.
- **justify-self**: Permite alinear un ítem dentro de la celda (de izquierda a derecha). Se aplica a un grid item.
- **align-items**: Permite alinear dentro de la celda (de arriba hacia abajo) los grid items. Se aplica al contenedor padre.
- **align-self**: Permite alinear dentro de la celda (de arriba hacia abajo) un grid item. Se aplica a un grid item.
- **justify-content**: Permite alinear todo el contenido de la cuadrícula de forma horizontal
- **align-content**: Permite alinear todo el contenido de la cuadrícula de forma vertical.
- **place-content**: Es un *atajo de justify-content y align-content.* Su valor más común es center.

### Columnas

- **grid-column-start**: Permite establecer desde donde inicia una columna.
- **grid-column-end**: Permite establecer donde termina una columna (no incluye el último).

### Filas

- **grid-auto-rows**: Permite establecer el tamaño de las filas que se crean por defecto.
- **grid-row-start**: Permite establecer desde donde inicia una fila.
- **grid-row-end**: Permite establecer donde termina una fila (no incluye el último).

## **Funciones**

- **repeat(cant_repeticiones, medida)**: Función que permite repetir x cantidad de veces una determinada medida, generalmente utilizada para crear varias filas o columnas de la misma medida. Esta función recibe 2 parámetros: La cantidad de veces que debe repetirse y la medida. Por ejemplo: **repeat(5, 1fr) = 1fr 1fr 1fr 1fr 1fr**
- **minmax(valor_minimo, valor_máximo)**: Función que permite establecer un valor mínimo y máximo ya sea a una columna o fila. Por ejemplo: **minmax(100px, 1fr)** → En este ejemplo el valor mínimo de la columna va a ser de 100px, pero cuando pueda ser mayor se va a comportar como si fuese una fracción.

## Grid áreas

- grid-area: Esta propiedad se le coloca a los ítems grids, y sirve para colocarle un nombre a cada ítem, para luego posicionarlo “visualmente” en el grid template.
- grid-template-areas: Propiedad que se le coloca al contenedor grid. Sirve para posicionar los ítems de forma visual (es un reemplazo más efectivo que utilizar grid-column-start y sus variantes en cada ítem).

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: 35px 1fr 100px;
  height: 100vh;
  grid-template-areas:
    "header header"
    "aside content"
    "footer footer";
}

.container header {
  background: #09f;
  grid-area: header;
}

.container aside {
  background: #62e;
  grid-area: aside;
}

.container main {
  background: #af2;
  grid-area: content;
}

.container footer {
  background: #444;
  grid-area: footer;
}
```

## Ejemplo Responsive en Grid

- En el siguiente ejemplo se utiliza un contenedor grid con 6 imágenes, de modo que mediante **grid-template-colums** y haciendo uso de las funciones **repeat** y **minmax**, el contenido sea responsivo. Esto funciona por la valor auto-fill.
    - **auto-fill**: Ubica el número de columnas que sean, que ocupan en el ancho, mientras su ancho mínimo sea de 200px, en el caso del ejemplo. En pocas palabras, en cuanto tiene la oportunidad de que otra se coloque al lado de la otra, lo hará.
    - **auto-fit**: Se utiliza en pocos casos, cuando hay pocos elementos lo que hace es estirarlos para completar el espacio sobrante.
    
    ```css
    img{
        width: 100%;
        height: auto;
    }
    
    div{
        display: grid;
        gap: 16px;
        grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
        
    }
    ```
    

---

# Animaciones y Transiciones

## Transiciones

- Permiten cambiar un elemento que transicione de un estado inicial a un estado objetivo.
- **transition-duration**: Permite modificar la duración de una transición
- **transition-property**: Permite establecer las propiedades a las que se le van a aplicar la transición (por defecto: all)
- **transition-timing-function**: Permite establecer las velocidades (inicio, medio y final) de la animación. Algunos de sus posibles valores son: ease, ease-in, ease-out, ease-in-out, step(), cubic-bezier().
- **transition-delay**: Permite establecer un delay al elemento.
- **transition**: Esta propiedad contiene a transition-duration, transition-property, transition-timing-function y transition-delay. La forma más utilizada de pasarle los valores es la siguiente: `transition: propiedad duración animación delay`

- **Ejemplo de transición sencillo**

```css
.elemento{
	transition: background .3s linear 
}
```

- Ejemplo de transición con hover y al quitar el mouse por encima

```css
.elemento{
	width: 50px;
	height: 50px;
	background: #09f;
	border-radius: 50%;
	transition: all 300ms ease-in-out /* la segunda animación */
}

.elemento:hover{
	scale: 2;
	background: red;
	box-shadow: 0 0 10px red;
	transition-duration: 1s /* la primera animación*/
}
```

## Animaciones

- **`keyframes animation-name { … }`**: Estructura para crear una animación. Dentro de las llaves se deben colocar los diferentes bloques, que serían algo así como fotogramas de la animación
- **animation-name**: Propiedad aplicada a un elemento. Hay que colocarle el nombre de la animación creada.
- **animation-duration**: Permite establecer la duración de la animación.
- **animation-timing-function**: Permite establecer las velocidades (inicio, medio y final) de la animación.
- **animation-iteration-count**: Permite establecer la cantidad de veces que va a repetirse la animación.
- **animation-delay**: Permite establecer un delay al comienzo de la animación.
- **animation-direction**: Permite establecer si la animación va a reproducirse hacia adelante, hacia atrás o en ciclos alternos. Algunos de sus valores son: *normal, reverse y alternate*.
- **animation-fill-mode**: Define cómo debe aplicarse una animación a los elementos cuando esta no se está ejecutando activamente (después de que termine y antes de que comience). Esto permite que el estilo de la animación se mantenga en el elemento una vez que la animación ha terminado. Algunos de sus valores son:
    - **none** (valor por defecto)
    - **forwards**: Cuando la animación termina, el elemento mantiene el estilo (o posición) que corresponde al último fotograma de la animación. Este efecto se mantiene después de la animación.
    
- **animation**: Esta propiedad contiene a animation-name, animation-duration, animation-timing-function, animation-delay, animation-iteration-count, etc. *Por ejemplo*:
`animation: nombre duración timing-function delay(opcional) iteration-count(opcional)`
    
    ```css
    .elemento{ 
    	 	animation-name: mi-animacion;
    	  animation-duration: 2s;
    	  animation-timing-function: ease-in-out;
    	  animation-iteration-count: infinite;
    	  animation-direction: alternate;
      }
    
    @keyframes mi-animacion{
    	...
    }
    ```
    

### Animación con scroll

```html
<div id="progress"></div>
...
...
...
```

```css
#progress {
	position: fixed;
	top: 0;
	width: 0%;
	background: #48e;
	height: 1em;
	animation: progress-grow auto linear;
	animation-timeline: scroll(root block);
}

@keyframes progress-grow{
	0%{ width: 0% }
	100%{ width: 100% }
}
```