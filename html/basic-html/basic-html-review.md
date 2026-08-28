# Basic HTML

Resumen del módulo **Basic HTML** del curso **Responsive Web Design v9** de freeCodeCamp.

## 1. Fundamentos de HTML

### Rol de HTML

**HTML (HyperText Markup Language)** define el **contenido y la estructura** de una página web. Se utiliza para representar elementos como títulos, párrafos, enlaces, imágenes, listas y contenido multimedia.

### Elementos HTML

Los elementos son los bloques fundamentales de un documento HTML. La mayoría están formados por:

- una etiqueta de apertura;
- contenido;
- una etiqueta de cierre.

```html
<elemento>Contenido</elemento>
```

Por ejemplo:

```html
<p>Este es un párrafo.</p>
```

### Void elements

Los **void elements** no pueden contener contenido y no tienen etiqueta de cierre.

Algunos ejemplos son:

```html
<img>
<meta>
```

También puede aparecer una `/` al final:

```html
<img />
```

Ambas formas son válidas en HTML.

### Atributos

Los **atributos** agregan información a un elemento o modifican su comportamiento. Se escriben dentro de la etiqueta de apertura.

```html
<elemento atributo="valor">Contenido</elemento>
```

Por ejemplo:

```html
<a href="https://www.freecodecamp.org">freeCodeCamp</a>
```

#### Atributos booleanos

Un **boolean attribute** representa una condición verdadera o falsa mediante su presencia:

- si el atributo está presente, se considera `true`;
- si está ausente, se considera `false`.

Ejemplos:

```html
<input disabled>
<input readonly>
<input required>
```

### Comentarios

Los comentarios permiten dejar notas dentro del código sin que formen parte del contenido visible de la página.

```html
<!-- Este es un comentario HTML -->
```

---

## 2. Elementos HTML comunes

### Encabezados

HTML posee seis niveles de encabezados:

```html
<h1>Encabezado principal</h1>
<h2>Segundo nivel</h2>
<h3>Tercer nivel</h3>
<h4>Cuarto nivel</h4>
<h5>Quinto nivel</h5>
<h6>Sexto nivel</h6>
```

`h1` representa el nivel de mayor importancia y `h6` el de menor importancia.

### Párrafos

El elemento `p` representa un párrafo.

```html
<p>Este es un párrafo.</p>
```

### Imágenes

El elemento `img` permite insertar imágenes.

Sus atributos más importantes son:

- `src`: ubicación de la imagen;
- `alt`: texto alternativo que describe la imagen.

```html
<img src="cat.jpg" alt="Un gato durmiendo">
```

El atributo `alt` es especialmente importante para accesibilidad y también sirve como alternativa cuando la imagen no puede mostrarse.

### `body`

El elemento `body` contiene el contenido principal visible del documento HTML.

```html
<body>
  <h1>Mi página</h1>
  <p>Contenido de la página.</p>
</body>
```

### `section`

`section` divide el contenido en secciones relacionadas semánticamente.

```html
<section>
  <h2>Sobre mí</h2>
  <p>Contenido de la sección.</p>
</section>
```

### `div`

`div` es un contenedor genérico sin significado semántico propio. Se utiliza para agrupar otros elementos.

```html
<div>
  <h2>Título</h2>
  <p>Contenido.</p>
</div>
```

### Enlaces

El elemento `a` crea enlaces.

El atributo `href` indica el destino.

```html
<a href="https://www.freecodecamp.org">freeCodeCamp</a>
```

### Listas

#### Lista no ordenada

`ul` representa una lista en la que el orden de los elementos no es significativo.

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ul>
```

#### Lista ordenada

`ol` representa una lista cuyo orden sí es significativo.

```html
<ol>
  <li>Primer paso</li>
  <li>Segundo paso</li>
  <li>Tercer paso</li>
</ol>
```

Los elementos de ambas listas se representan con `li`.

### Énfasis

`em` indica énfasis sobre una parte del texto.

```html
<p>Esto es <em>importante</em>.</p>
```

### Importancia fuerte

`strong` indica una importancia, urgencia o seriedad mayor.

```html
<p><strong>Importante:</strong> guardá tus cambios.</p>
```

### `figure` y `figcaption`

`figure` agrupa contenido independiente, como imágenes o diagramas.

`figcaption` proporciona una descripción o título para ese contenido.

```html
<figure>
  <img src="diagram.png" alt="Diagrama del sistema">
  <figcaption>Arquitectura general del sistema.</figcaption>
</figure>
```

### `main`

`main` representa el contenido principal de la página.

```html
<main>
  <h1>Contenido principal</h1>
</main>
```

### `footer`

`footer` suele contener información ubicada al final de una página o sección, como:

- copyright;
- enlaces importantes;
- información de contacto.

```html
<footer>
  <p>© 2026 Mi sitio</p>
</footer>
```

### `button`

El elemento `button` crea un botón interactivo.

```html
<button>Enviar</button>
```

---

## 3. Identificadores y agrupación

### IDs

El atributo `id` identifica de forma única a un elemento dentro de un documento HTML.

```html
<h1 id="title">Título</h1>
```

Un mismo `id` no debería reutilizarse en varios elementos de la misma página.

Los valores de `id`:

- no pueden contener espacios;
- pueden utilizar letras, números, guiones (`-`) y guiones bajos (`_`).

```html
<div id="red-box"></div>
<div id="red_box"></div>
```

### Clases

El atributo `class` permite agrupar elementos para aplicar estilos o comportamiento común.

```html
<div class="box"></div>
```

A diferencia de un `id`, una clase puede reutilizarse en muchos elementos.

Un elemento también puede pertenecer a varias clases separándolas con espacios:

```html
<div class="box red-box"></div>
<div class="box blue-box"></div>
```

---

## 4. Caracteres especiales y recursos externos

### HTML entities

Algunos caracteres tienen un significado especial dentro de HTML. Para representarlos como texto se pueden utilizar **HTML entities** o **character references**.

Ejemplos:

| Carácter | Entity |
| --- | --- |
| `&` | `&amp;` |
| `<` | `&lt;` |
| `>` | `&gt;` |

```html
<p>El elemento &lt;img&gt; muestra una imagen.</p>
```

### Elemento `link`

`link` conecta el documento HTML con recursos externos, como hojas de estilo o iconos.

```html
<link rel="stylesheet" href="./styles.css">
```

Atributos importantes:

- `rel`: relación entre el recurso y el documento;
- `href`: ubicación del recurso.

### Elemento `script`

`script` permite incluir código ejecutable, normalmente JavaScript.

Puede escribirse directamente:

```html
<script>
  console.log("Hola");
</script>
```

Sin embargo, normalmente se utiliza un archivo JavaScript externo:

```html
<script src="./script.js"></script>
```

El atributo `src` indica su ubicación.

---

## 5. Boilerplate y codificación

### Estructura básica de un documento HTML

Un documento HTML suele comenzar con una estructura similar a esta:

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8">
    <title>Mi página</title>
  </head>

  <body>
    <h1>Contenido</h1>
  </body>
</html>
```

### `DOCTYPE`

```html
<!DOCTYPE html>
```

Indica al navegador la versión o modo de HTML que debe interpretar. En HTML moderno se utiliza `<!DOCTYPE html>`.

### Elemento `html`

Es el elemento raíz del documento.

```html
<html lang="es">
```

El atributo `lang` especifica el idioma principal del contenido.

### Elemento `head`

`head` contiene **metadata** e información necesaria para navegadores, buscadores y otros servicios.

Normalmente incluye elementos como:

- `meta`;
- `title`;
- `link`;
- otros datos de configuración.

### Elemento `meta`

`meta` proporciona metadata sobre el documento, como:

- codificación de caracteres;
- descripción de la página;
- información para redes sociales.

### Elemento `title`

`title` define el texto que aparece en la pestaña o ventana del navegador.

```html
<title>Mi sitio web</title>
```

### UTF-8

**UTF-8 (UCS Transformation Format 8)** es uno de los sistemas de codificación de caracteres más utilizados en la web.

```html
<meta charset="UTF-8">
```

La codificación determina cómo se representan y almacenan caracteres como letras, símbolos y caracteres de distintos idiomas.

---

## 6. SEO y redes sociales

### SEO

**SEO (Search Engine Optimization)** reúne técnicas destinadas a mejorar la visibilidad y posicionamiento de una página en motores de búsqueda.

### Meta description

Una descripción breve de la página puede indicarse mediante:

```html
<meta
  name="description"
  content="Descripción breve del contenido de la página."
>
```

La **meta description** ayuda a describir el contenido de la página y puede influir en cómo se presenta en resultados de búsqueda.

### Open Graph

El protocolo **Open Graph** permite controlar cómo se presenta una página cuando se comparte en plataformas sociales.

Se configura mediante elementos `meta` dentro de `head`.

Propiedades frecuentes:

#### `og:title`

Título utilizado al compartir el contenido.

```html
<meta property="og:title" content="Mi página">
```

#### `og:type`

Tipo de contenido.

```html
<meta property="og:type" content="website">
```

Puede representar, por ejemplo:

- websites;
- articles;
- videos;
- music.

#### `og:image`

Imagen utilizada en la vista previa.

```html
<meta property="og:image" content="https://example.com/image.jpg">
```

#### `og:url`

URL asociada al contenido compartido.

```html
<meta property="og:url" content="https://example.com">
```

---

## 7. Medios y optimización

### Replaced elements

Un **replaced element** es un elemento cuyo contenido visual proviene de un recurso externo en lugar de estar generado directamente por CSS.

Algunos ejemplos son:

- `iframe`;
- `video`;
- `embed`;
- ciertos tipos de `input`.

### `iframe`

`iframe` significa **inline frame** y permite incrustar otro documento HTML dentro de una página.

```html
<iframe
  src="https://example.com"
  title="Example site"
></iframe>
```

Puede utilizarse, por ejemplo, para insertar videos de servicios como YouTube o Vimeo.

El atributo booleano `allowfullscreen` permite que el contenido pueda mostrarse a pantalla completa.

```html
<iframe
  src="video-url"
  allowfullscreen
></iframe>
```

### Optimización de medios

Al trabajar con imágenes y otros archivos multimedia conviene considerar tres factores:

1. **tamaño**;
2. **formato**;
3. **compresión**.

La compresión reduce el tamaño de los archivos o datos, lo que normalmente mejora los tiempos de carga.

### Formatos de imagen

Formatos tradicionales:

- PNG;
- JPG/JPEG.

Formatos modernos más optimizados:

- WebP;
- AVIF.

Cuando no es necesario soportar navegadores antiguos, WebP o AVIF suelen ser mejores opciones para servir imágenes en la web.

### Licencias de imágenes

No todas las imágenes disponibles en Internet pueden utilizarse libremente.

Algunos conceptos importantes:

- **Public domain**: no posee restricciones de copyright aplicables.
- **CC0 (Creative Commons Zero)**: permite dedicar una obra al dominio público.
- **Creative Commons**: conjunto de licencias con distintas condiciones de uso.
- **Permissive licenses**: permiten reutilización bajo determinadas condiciones.

Siempre debe verificarse la licencia antes de reutilizar un recurso.

### SVG

**SVG (Scalable Vector Graphics)** describe gráficos mediante formas, coordenadas, trayectorias y ecuaciones.

Su principal ventaja es que puede escalarse a distintos tamaños sin perder calidad.

Es especialmente útil para:

- iconos;
- logos;
- ilustraciones;
- gráficos vectoriales.

---

## 8. Audio y video

HTML incluye elementos nativos para reproducir contenido multimedia:

```html
<audio src="audio.mp3"></audio>
<video src="video.mp4"></video>
```

Formatos habituales:

- audio: MP3, WAV, OGG;
- video: MP4, OGG, WebM.

### `controls`

Muestra los controles de reproducción proporcionados por el navegador.

```html
<audio src="audio.mp3" controls></audio>
```

Permite realizar acciones como:

- reproducir;
- pausar;
- modificar el volumen.

Es un atributo booleano.

### `autoplay`

Hace que el audio o video intente comenzar automáticamente cuando sea posible.

```html
<video src="video.mp4" autoplay></video>
```

Es un atributo booleano.

Los navegadores pueden aplicar restricciones al autoplay, especialmente cuando el contenido tiene sonido.

### `loop`

Reproduce el archivo nuevamente cuando termina.

```html
<audio src="audio.mp3" loop></audio>
```

### `muted`

Inicia el contenido multimedia silenciado.

```html
<video src="video.mp4" muted></video>
```

### Elemento `source`

Permite ofrecer varias versiones del mismo recurso. El navegador utiliza la primera que pueda reproducir.

```html
<audio controls>
  <source src="audio.ogg" type="audio/ogg">
  <source src="audio.wav" type="audio/wav">
  <source src="audio.mp3" type="audio/mpeg">
</audio>
```

También puede utilizarse dentro de `video`.

### `poster`

El atributo `poster` es exclusivo de `video` y permite mostrar una imagen antes de que el video empiece a reproducirse o mientras se carga.

```html
<video
  src="video.mp4"
  controls
  poster="preview.jpg"
></video>
```

---

## 9. Atributo `target`

En un enlace, `target` determina **en qué browsing context se abrirá el destino**.

```html
<a href="https://example.com" target="_blank">Abrir enlace</a>
```

### `_self`

Es el valor por defecto. Abre el enlace en el contexto actual, normalmente la pestaña actual.

```html
<a href="page.html" target="_self">Abrir</a>
```

### `_blank`

Abre el enlace en un nuevo contexto de navegación, normalmente una nueva pestaña.

```html
<a href="page.html" target="_blank">Abrir</a>
```

### `_parent`

Abre el enlace en el contexto padre.

Es especialmente relevante cuando el documento actual está dentro de un `iframe`.

### `_top`

Abre el enlace en el contexto de navegación de nivel superior, ignorando posibles `iframe` anidados.

### `_unfencedTop`

Existe además `_unfencedTop`, relacionado con la API experimental **FencedFrame**. No es un valor de uso habitual en desarrollo web básico.

---

## 10. Rutas absolutas y relativas

### Path

Un **path** es una cadena que indica la ubicación de un archivo o directorio.

En desarrollo web se utiliza para localizar recursos como:

- páginas;
- imágenes;
- hojas de estilo;
- scripts.

### Sintaxis básica

Ejemplos:

```text
public/index.html
./favicon.ico
../src/index.css
```

- `/`: separa partes de una ruta.
- `.`: hace referencia al directorio actual.
- `..`: hace referencia al directorio padre.

### Absolute path

Un **absolute path** describe la ruta completa hacia un recurso dentro de un sistema de archivos, comenzando desde su directorio raíz.

### Absolute URL

Una **absolute URL** identifica completamente un recurso en la web e incluye información como:

- protocolo;
- dominio;
- ruta.

```text
https://example.com/images/logo.svg
```

Donde:

- `https` es el protocolo;
- `example.com` es el dominio;
- `/images/logo.svg` es la ruta al recurso.

### Relative path

Una **relative path** indica la ubicación de un recurso en relación con el archivo actual.

```html
<a href="about.html">About</a>
```

Otro ejemplo:

```html
<link rel="stylesheet" href="../css/styles.css">
```

Las rutas relativas son especialmente útiles para recursos internos de un mismo sitio porque no necesitan incluir protocolo ni dominio.

---

## 11. Estados de los enlaces

CSS permite representar distintos estados de un enlace mediante pseudo-clases.

### `:link`

Representa un enlace que todavía no fue visitado.

```css
a:link {
  /* estilos */
}
```

### `:visited`

Se aplica cuando el usuario ya visitó el destino del enlace.

```css
a:visited {
  /* estilos */
}
```

### `:hover`

Se aplica cuando el cursor se encuentra sobre el enlace.

```css
a:hover {
  /* estilos */
}
```

### `:focus`

Se aplica cuando el enlace recibe foco, por ejemplo al navegar mediante teclado.

```css
a:focus {
  /* estilos */
}
```

### `:active`

Se aplica mientras el enlace está siendo activado por el usuario, normalmente durante el clic.

```css
a:active {
  /* estilos */
}
```

Estos estados permiten proporcionar feedback visual y mejorar la interacción y accesibilidad de los enlaces.

---

## Resumen rápido

Los conceptos fundamentales de **Basic HTML** son:

- HTML estructura y representa el contenido de una página.
- Los elementos se construyen mediante etiquetas y pueden incluir atributos.
- Los void elements no contienen contenido ni etiqueta de cierre.
- `id` identifica elementos únicos y `class` permite agrupar múltiples elementos.
- El boilerplate define la estructura mínima del documento HTML.
- `head` contiene metadata; `body`, el contenido visible.
- HTML incorpora elementos para imágenes, enlaces, listas, audio, video e iframes.
- Los metadatos pueden utilizarse para SEO y para controlar previews en redes sociales.
- Los medios deberían optimizarse considerando tamaño, formato y compresión.
- Las rutas pueden ser absolutas o relativas.
- `target` determina dónde se abre un enlace.
- Los enlaces poseen estados como `:link`, `:visited`, `:hover`, `:focus` y `:active`.
