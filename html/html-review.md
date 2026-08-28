# HTML Review

Resumen integrador de la sección **HTML** del curso **Responsive Web Design v9** de freeCodeCamp.

Este review reúne los conceptos principales de:

1. **Basic HTML**;
2. **Semantic HTML**;
3. **HTML Tables and Forms**;
4. **HTML Accessibility**.

El objetivo de este archivo es funcionar como **repaso global**, por lo que prioriza relaciones entre conceptos y puntos clave en lugar de repetir literalmente cada review individual.

---

# 1. Fundamentos de HTML

## Rol de HTML

**HTML (HyperText Markup Language)** define la estructura y el significado del contenido de una página web.

HTML representa elementos como:

- encabezados;
- párrafos;
- imágenes;
- enlaces;
- listas;
- formularios;
- tablas;
- multimedia.

CSS se encarga principalmente de la presentación visual y JavaScript del comportamiento dinámico.

---

## Elementos y etiquetas

La mayoría de los elementos poseen una etiqueta de apertura y una de cierre:

```html
<p>Paragraph</p>
```

Los **void elements** no contienen contenido ni poseen closing tag:

```html
<img>
<input>
<meta>
<link>
```

---

## Atributos

Los atributos proporcionan información adicional o modifican el comportamiento del elemento.

```html
<a href="https://example.com">Example</a>
```

Ejemplos frecuentes:

```text
id
class
href
src
alt
name
value
type
```

Los atributos booleanos representan `true` mediante su presencia:

```html
<input required>
<input disabled>
<video controls></video>
```

---

# 2. Estructura del documento

Una estructura básica de HTML es:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Page title</title>
  </head>

  <body>
    <h1>Page content</h1>
  </body>
</html>
```

## Elementos fundamentales

### `<!DOCTYPE html>`

Indica al navegador que debe interpretar el documento como HTML moderno.

### `html`

Es el elemento raíz.

```html
<html lang="en">
```

`lang` comunica el idioma principal del documento.

### `head`

Contiene metadata y recursos asociados.

### `body`

Contiene el contenido principal que forma parte de la página.

### `title`

Define el título mostrado en la pestaña del navegador.

### `meta`

Permite especificar metadata como codificación y descripción.

```html
<meta charset="UTF-8">
```

---

# 3. IDs y clases

## `id`

Identifica un elemento de manera única dentro del documento.

```html
<section id="about">
```

Puede utilizarse para:

- estilos;
- JavaScript;
- enlaces internos;
- referencias ARIA.

## `class`

Agrupa varios elementos bajo una misma categoría.

```html
<div class="card featured"></div>
```

Un elemento puede poseer varias clases separadas por espacios.

---

# 4. Enlaces, rutas y recursos

## Enlaces

```html
<a href="https://example.com">Example</a>
```

### Enlaces internos

```html
<a href="#about">About</a>

<section id="about">
  ...
</section>
```

## `target`

Controla dónde se abre el recurso.

Valores importantes:

```text
_self
_blank
_parent
_top
```

## Rutas

### Relative path

```text
./image.png
../css/styles.css
about.html
```

### Absolute URL

```text
https://example.com/assets/image.png
```

Símbolos importantes:

```text
/   separación de directorios
./  directorio actual
../ directorio padre
```

---

# 5. Recursos externos

## CSS

```html
<link rel="stylesheet" href="./styles.css">
```

## JavaScript

```html
<script src="./script.js"></script>
```

---

# 6. HTML entities

Permiten representar caracteres con significado especial dentro de HTML.

| Carácter | Entity |
| --- | --- |
| `&` | `&amp;` |
| `<` | `&lt;` |
| `>` | `&gt;` |

Ejemplo:

```html
<p>Use &lt;p&gt; for a paragraph.</p>
```

---

# 7. SEO y social sharing

## Meta description

```html
<meta
  name="description"
  content="Short description of the page."
>
```

Describe brevemente el contenido y puede utilizarse en motores de búsqueda.

## Open Graph

Permite configurar cómo se presenta el contenido al compartirlo.

Propiedades frecuentes:

```html
<meta property="og:title" content="Page title">
<meta property="og:type" content="website">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:url" content="https://example.com">
```

---

# 8. Multimedia

## Imágenes

```html
<img
  src="cat.jpg"
  alt="A cat sleeping on a couch"
>
```

`src` indica el recurso y `alt` proporciona una alternativa textual.

## Audio

```html
<audio controls>
  <source src="audio.mp3" type="audio/mpeg">
</audio>
```

## Video

```html
<video controls poster="preview.jpg">
  <source src="video.mp4" type="video/mp4">
</video>
```

Atributos frecuentes:

```text
controls
autoplay
loop
muted
poster
```

## `iframe`

Incrusta otro documento dentro de la página.

```html
<iframe
  src="https://example.com"
  title="Example site"
></iframe>
```

## Optimización

Para medios deben considerarse:

- tamaño;
- formato;
- compresión.

Formatos de imagen habituales:

```text
PNG
JPEG
WebP
AVIF
SVG
```

WebP y AVIF suelen ofrecer buena compresión moderna.

SVG representa gráficos vectoriales escalables.

---

# 9. HTML semántico

HTML semántico utiliza elementos que describen el propósito del contenido.

Elementos estructurales principales:

```html
<header>
<nav>
<main>
<section>
<article>
<aside>
<footer>
```

### `header`

Contenido introductorio.

### `nav`

Navegación principal o relevante.

### `main`

Contenido principal.

### `section`

Agrupación temática.

### `article`

Contenido independiente y autocontenido.

### `aside`

Contenido relacionado indirectamente.

### `footer`

Información de cierre de una sección o documento.

---

# 10. Jerarquía de encabezados

Los niveles:

```html
<h1>
<h2>
<h3>
<h4>
<h5>
<h6>
```

deben representar una jerarquía lógica.

No deben elegirse por tamaño visual. La apariencia se controla con CSS.

Saltar niveles puede dificultar la comprensión de la estructura, especialmente para usuarios de screen readers.

---

# 11. Semántica de texto

Distintos elementos aportan significados diferentes.

| Elemento | Significado principal |
| --- | --- |
| `em` | énfasis |
| `strong` | importancia fuerte |
| `i` | voz o término alternativo |
| `b` | atención sin importancia semántica |
| `s` | contenido ya no válido/relevante |
| `u` | anotación no textual |
| `sup` | superíndice |
| `sub` | subíndice |
| `code` | fragmento de código |
| `abbr` | abreviatura |
| `time` | fecha/hora |

Si sólo se busca una apariencia visual, debe preferirse CSS.

---

# 12. Citas y referencias

## `blockquote`

Cita extensa:

```html
<blockquote cite="https://example.com/source">
  Quoted text.
</blockquote>
```

## `q`

Cita breve inline:

```html
<p>She said <q>Keep learning.</q></p>
```

## `cite`

Título de una obra referenciada:

```html
<cite>Cosmos</cite>
```

---

# 13. Listas de descripción

```html
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language</dd>
</dl>
```

- `dl`: lista;
- `dt`: término;
- `dd`: descripción.

---

# 14. Formularios

## Estructura

```html
<form action="/submit" method="POST">
  ...
</form>
```

- `action`: destino;
- `method`: método HTTP.

## Inputs

```html
<input
  type="email"
  id="email"
  name="email"
  required
>
```

Atributos importantes:

```text
type
name
value
placeholder
min
max
minlength
maxlength
required
disabled
readonly
```

### Radio buttons

Comparten `name` para formar un grupo exclusivo:

```html
<input type="radio" name="plan" value="basic">
<input type="radio" name="plan" value="pro">
```

### Checkboxes

Representan opciones independientes:

```html
<input type="checkbox" name="newsletter">
```

---

# 15. Labels y grupos de controles

## Asociación explícita

```html
<label for="email">Email:</label>
<input id="email" type="email">
```

## Asociación implícita

```html
<label>
  Name:
  <input type="text">
</label>
```

## `fieldset` y `legend`

```html
<fieldset>
  <legend>Choose a plan</legend>
  ...
</fieldset>
```

Agrupan y describen controles relacionados.

---

# 16. Botones

```html
<button type="submit">Submit</button>
<button type="reset">Reset</button>
<button type="button">Open</button>
```

Tipos principales:

- `submit`;
- `reset`;
- `button`.

---

# 17. Tablas

Una tabla utiliza:

```text
table
caption
thead
tbody
tfoot
tr
th
td
```

Ejemplo:

```html
<table>
  <caption>Exam Grades</caption>

  <thead>
    <tr>
      <th>Name</th>
      <th>Grade</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>Alex</td>
      <td>92</td>
    </tr>
  </tbody>
</table>
```

## `colspan`

Hace que una celda abarque varias columnas:

```html
<td colspan="2">Average</td>
```

Las tablas deben utilizarse para datos tabulares y no como herramienta de layout.

---

# 18. Accesibilidad y WCAG

WCAG utiliza los principios **POUR**:

```text
Perceivable
Operable
Understandable
Robust
```

Una página accesible debe contemplar:

- estructura semántica;
- navegación por teclado;
- nombres y labels claros;
- alternativas textuales;
- multimedia accesible;
- compatibilidad con tecnologías de asistencia.

---

# 19. Tecnologías de asistencia

Ejemplos:

- screen readers;
- screen magnifiers;
- braille keyboards;
- alternative pointing devices;
- voice recognition.

Herramientas de auditoría mencionadas en el curso:

- Lighthouse;
- WAVE;
- IBM Equal Access Accessibility Checker;
- axe DevTools.

---

# 20. Texto alternativo y enlaces accesibles

## `alt`

```html
<img
  src="dog.jpg"
  alt="A golden retriever running through snow"
>
```

El texto debe comunicar la función o información relevante de la imagen.

Para imágenes decorativas:

```html
alt=""
```

## Texto de enlaces

Preferible:

```html
<a href="/docs">Read the HTML documentation</a>
```

Evitar enlaces sin contexto como:

```html
<a href="/docs">Click here</a>
```

---

# 21. Multimedia accesible

Para audio y video pueden ser necesarios:

- captions;
- transcripts;
- audio descriptions.

Esto permite que el contenido pueda ser comprendido por usuarios con discapacidades auditivas o visuales.

---

# 22. Navegación por teclado

## `tabindex`

Valores recomendados:

### `0`

Participa en el orden natural de tabulación:

```html
<div tabindex="0">Focusable</div>
```

### `-1`

Puede recibir foco programáticamente pero no mediante el recorrido normal con `Tab`:

```html
<p tabindex="-1">Error message</p>
```

Debe evitarse:

```text
tabindex > 0
```

porque altera artificialmente el orden de navegación.

## `accesskey`

Define un atajo:

```html
<button accesskey="s">Save</button>
```

---

# 23. WAI-ARIA

ARIA complementa HTML proporcionando información adicional para tecnologías de asistencia.

## Roles

Ejemplos:

```html
role="tab"
role="menu"
role="alert"
role="dialog"
```

Categorías principales:

- document structure;
- widget;
- landmark;
- live region;
- window;
- abstract.

Los roles abstractos no deben utilizarse directamente.

---

# 24. Nombres y descripciones accesibles

## `aria-label`

Define directamente un nombre:

```html
<button aria-label="Search">
  🔍
</button>
```

## `aria-labelledby`

Referencia el texto existente de otro elemento:

```html
<h2 id="title">Settings</h2>

<section aria-labelledby="title">
  ...
</section>
```

## `aria-describedby`

Referencia contenido descriptivo adicional:

```html
<input
  id="password"
  type="password"
  aria-describedby="password-help"
>

<p id="password-help">
  Minimum 8 characters.
</p>
```

## `aria-hidden`

Evita que un elemento sea anunciado por tecnologías de asistencia:

```html
<i
  class="icon"
  aria-hidden="true"
></i>
```

Es adecuado para contenido decorativo, no para información importante.

---

# 25. HTML nativo antes que ARIA

Siempre que exista un elemento HTML que represente correctamente el propósito y comportamiento deseados, debe preferirse frente a recrearlo con elementos genéricos y ARIA.

Preferible:

```html
<button>Save</button>
```

En vez de:

```html
<div role="button">Save</div>
```

Los elementos nativos ya incluyen muchas características:

- semántica;
- foco;
- comportamiento de teclado;
- compatibilidad con tecnologías de asistencia.

---

# 26. Herramientas de desarrollo HTML

## HTML Validator

Comprueba la validez sintáctica del markup.

## DOM Inspector

Permite inspeccionar y modificar temporalmente la estructura que el navegador construyó.

## Browser DevTools

Permiten:

- inspeccionar HTML y CSS;
- depurar JavaScript;
- revisar la red;
- analizar rendimiento;
- investigar errores.

---

# Checklist de repaso

Antes de dar por dominada la sección HTML, deberías poder explicar:

- qué diferencia existe entre un elemento, una etiqueta y un atributo;
- qué son los void elements;
- cómo se estructura un documento HTML;
- cuándo utilizar `id` y cuándo `class`;
- qué diferencia existe entre rutas absolutas y relativas;
- qué aporta el HTML semántico;
- cómo mantener una jerarquía correcta de headings;
- diferencias entre `em`, `strong`, `i` y `b`;
- cómo funcionan formularios, inputs, labels y botones;
- cómo se agrupan radio buttons y checkboxes;
- cómo se estructura correctamente una tabla;
- qué significan los principios POUR;
- por qué son importantes `alt`, labels y link text descriptivo;
- cómo funciona la navegación por teclado;
- cuándo utilizar `tabindex="0"` y `tabindex="-1"`;
- qué son WAI-ARIA, roles y nombres accesibles;
- diferencias entre `aria-label`, `aria-labelledby`, `aria-describedby` y `aria-hidden`;
- por qué conviene utilizar HTML nativo antes que ARIA cuando sea posible.

---

## Resumen final

La sección **HTML** no consiste únicamente en aprender etiquetas.

El objetivo principal es construir documentos que sean:

- **estructurados**, mediante elementos y jerarquías correctas;
- **semánticos**, utilizando elementos según su significado;
- **interactivos**, mediante formularios, enlaces y multimedia;
- **comprensibles**, tanto para humanos como para navegadores;
- **accesibles**, para diferentes usuarios y tecnologías de asistencia.

Una buena base de HTML permite que CSS y JavaScript se apoyen sobre una estructura clara, robusta y mantenible.
