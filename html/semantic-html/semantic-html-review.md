# Semantic HTML

Resumen del módulo **Semantic HTML** del curso **Responsive Web Design v9** de freeCodeCamp.

## 1. Qué es HTML semántico

El **HTML semántico** utiliza elementos cuyo nombre describe el propósito y la función del contenido que contienen.

Esto permite que:

- el código sea más fácil de leer y mantener;
- los navegadores comprendan mejor la estructura de la página;
- los motores de búsqueda interpreten mejor el contenido;
- las tecnologías de asistencia, como los screen readers, puedan navegar y comunicar mejor la estructura del documento.

### HTML semántico vs. HTML presentacional

Los elementos **semánticos** describen el significado o rol del contenido:

```html
<header>
<nav>
<main>
<article>
<section>
<footer>
```

En cambio, los antiguos elementos **presentacionales** describían principalmente cómo debía verse algo:

```html
<center>
<big>
<font>
```

Estos elementos presentacionales están obsoletos. La presentación visual debe realizarse con CSS.

### Jerarquía de encabezados

HTML proporciona encabezados desde `h1` hasta `h6`.

```html
<h1>Título principal</h1>
<h2>Sección</h2>
<h3>Subsección</h3>
```

La jerarquía debe representar la estructura lógica del contenido.

No conviene saltar niveles arbitrariamente, por ejemplo de `h2` a `h4`, porque esto rompe la jerarquía lógica que interpretan tecnologías como los screen readers.

---

## 2. Elementos estructurales

### `header`

Representa contenido introductorio de una página o sección.

Puede contener:

- títulos;
- logos;
- navegación;
- información introductoria.

```html
<header>
  <h1>CatPhotoApp</h1>
  <p>Welcome to our cat gallery.</p>
</header>
```

### `main`

Contiene el **contenido principal** de la página.

```html
<main>
  <h1>Artículo principal</h1>
  <p>Contenido...</p>
</main>
```

### `section`

Agrupa contenido relacionado dentro de una sección temática.

Normalmente debería tener un encabezado que describa su propósito.

```html
<section>
  <h2>Sobre mí</h2>
  <p>Información personal...</p>
</section>
```

### `nav`

Representa una sección dedicada principalmente a enlaces de navegación.

```html
<nav>
  <ul>
    <li><a href="#about">About</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>
```

### `article`

Representa contenido **autocontenido e independiente**, capaz de tener sentido por sí mismo.

Ejemplos habituales:

- publicaciones de blog;
- noticias;
- comentarios;
- artículos.

```html
<article>
  <h2>My First Blog Post</h2>
  <p>Contenido del artículo...</p>
</article>
```

### `aside`

Representa contenido relacionado de forma indirecta con el contenido principal.

Ejemplos:

- una barra lateral;
- enlaces relacionados;
- información complementaria.

### `footer`

Representa el pie de una página o sección.

Puede contener:

- copyright;
- información de contacto;
- enlaces relacionados;
- información del autor.

---

## 3. Figuras y contenido independiente

### `figure`

Agrupa contenido independiente, como:

- imágenes;
- diagramas;
- ilustraciones;
- gráficos;
- fragmentos de código.

```html
<figure>
  <img src="cats.jpg" alt="Two tabby kittens sleeping together.">
  <figcaption>Two sleeping cats.</figcaption>
</figure>
```

### `figcaption`

Proporciona una leyenda o descripción para el contenido de `figure`.

---

## 4. Énfasis, importancia y atención visual

HTML dispone de varios elementos que pueden producir resultados visuales similares, pero tienen **significados semánticos diferentes**.

### `em`

Indica **stress emphasis**: una palabra o fragmento debe enfatizarse dentro de la oración.

```html
<p>Never give up on <em>your</em> dreams.</p>
```

El énfasis puede alterar la interpretación de una frase.

### `strong`

Indica contenido de **gran importancia, urgencia o seriedad**.

```html
<p><strong>Warning:</strong> This product may cause allergic reactions.</p>
```

### `i`

Representa texto que se distingue del contenido circundante por una razón semántica, como:

- una expresión idiomática;
- una voz alternativa;
- un término técnico;
- una expresión en otro idioma;
- un pensamiento.

```html
<p>There is a certain <i lang="fr">je ne sais quoi</i> in the air.</p>
```

El atributo `lang` puede especificar el idioma del fragmento.

### `b`

Llama la atención sobre un fragmento de texto **sin indicar que sea más importante**.

Puede utilizarse, por ejemplo, para:

- palabras clave;
- nombres de productos;
- fragmentos relevantes en un resumen.

```html
<p>The <b>QuickCharge Pro</b> performed well.</p>
```

### Cuándo usar CSS

`em`, `strong`, `i` y `b` no deben elegirse únicamente por su apariencia visual.

Si el objetivo es simplemente mostrar texto en cursiva, negrita u otro estilo sin aportar significado semántico, debe utilizarse **CSS**.

---

## 5. Listas de descripción

### `dl`

Representa una **description list**, es decir, una lista de términos acompañados por sus descripciones.

### `dt`

Representa el término.

### `dd`

Representa su descripción.

```html
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language</dd>

  <dt>CSS</dt>
  <dd>Cascading Style Sheets</dd>
</dl>
```

---

## 6. Citas

### `blockquote`

Representa una cita extensa proveniente de otra fuente.

```html
<blockquote cite="https://example.com/article">
  Texto citado.
</blockquote>
```

El atributo `cite` puede contener la URL de la fuente.

### `q`

Representa una cita corta integrada dentro de una línea de texto.

```html
<p>The author said <q>Momentum is everything.</q></p>
```

También puede utilizar el atributo `cite`.

### `cite`

Representa el **título de una obra referenciada**, como:

- un libro;
- un artículo;
- una película;
- una canción.

```html
<p><cite>Cosmos</cite> was written by Carl Sagan.</p>
```

No debe confundirse con el atributo `cite`: uno es un elemento visible dentro del documento y el otro aporta una URL asociada a una cita.

---

## 7. Abreviaturas y datos de contacto

### `abbr`

Representa una abreviatura.

El atributo `title` puede incluir su forma completa.

```html
<p>
  <abbr title="HyperText Markup Language">HTML</abbr>
  is the foundation of the web.
</p>
```

### `address`

Representa información de contacto relacionada con una persona, organización o contenido.

```html
<address>
  123 Main Street<br>
  Springfield, IL 62701
</address>
```

### `br`

Inserta un salto de línea.

```html
123 Main Street<br>
Springfield, IL 62701
```

Debe utilizarse cuando el salto de línea forma parte del contenido, no para crear espaciado visual.

### Enlaces `tel:` y `mailto:`

Un enlace puede iniciar una llamada:

```html
<a href="tel:+11234567890">Call us</a>
```

O abrir el cliente de correo:

```html
<a href="mailto:example@email.com">Email us</a>
```

---

## 8. Fechas y horas

### `time`

Representa una fecha, hora o período temporal.

```html
<time datetime="2026-08-28">August 28, 2026</time>
```

### `datetime`

El atributo `datetime` proporciona una representación legible por máquinas.

Para fecha y hora puede utilizarse el formato ISO 8601:

```text
YYYY-MM-DDThh:mm:ss
```

Por ejemplo:

```html
<time datetime="2026-08-28T15:30:00">
  28 de agosto a las 15:30
</time>
```

---

## 9. Superíndices y subíndices

### `sup`

Representa texto en superíndice.

Casos habituales:

- exponentes;
- números ordinales;
- referencias.

```html
<p>2<sup>2</sup> = 4</p>
```

### `sub`

Representa texto en subíndice.

Casos habituales:

- fórmulas químicas;
- variables;
- notas.

```html
<p>CO<sub>2</sub></p>
```

---

## 10. Código y texto preformateado

### `code`

Representa un fragmento de código.

```html
<p>Use <code>console.log()</code> to print a value.</p>
```

### `pre`

Representa texto preformateado y conserva espacios y saltos de línea.

Suele combinarse con `code` para bloques de código:

```html
<pre><code>
body {
  color: red;
}
</code></pre>
```

---

## 11. Anotaciones de texto

### `u`

Representa texto con una **anotación no textual**.

Puede utilizarse, por ejemplo, para señalar errores ortográficos.

```html
<p>This word is <u>incorret</u>.</p>
```

No debe utilizarse simplemente para subrayar texto por estilo.

### `s`

Representa contenido que **ya no es preciso o relevante**.

```html
<p><s>Meeting at 12:00.</s></p>
<p>The meeting has been canceled.</p>
```

---

## 12. Ruby annotations

Las **ruby annotations** se utilizan principalmente para agregar pronunciación o explicaciones breves junto a determinados sistemas de escritura, especialmente en idiomas de Asia Oriental.

### `ruby`

Contenedor principal de la anotación.

### `rt`

Contiene el texto de pronunciación o explicación.

### `rp`

Proporciona paréntesis de respaldo para navegadores que no soporten correctamente ruby annotations.

```html
<ruby>
  明日 <rp>(</rp><rt>Ashita</rt><rp>)</rp>
</ruby>
```

---

## 13. Enlaces internos

Los enlaces internos permiten navegar a una sección del mismo documento.

El enlace utiliza un fragment identifier:

```html
<a href="#about-section">Go to About</a>
```

Y el destino posee el mismo `id`:

```html
<section id="about-section">
  <h2>About</h2>
</section>
```

Son útiles para:

- tablas de contenido;
- páginas largas;
- navegación interna;
- skip links de accesibilidad.

---

## Resumen rápido

Los puntos centrales de **Semantic HTML** son:

- El HTML semántico describe el significado y la estructura del contenido.
- La estructura de encabezados debe seguir una jerarquía lógica.
- `header`, `nav`, `main`, `section`, `article`, `aside` y `footer` describen regiones de la página.
- `em`, `strong`, `i` y `b` poseen significados distintos; no deben elegirse sólo por su apariencia.
- `figure` y `figcaption` relacionan contenido independiente con una descripción.
- `blockquote`, `q` y `cite` permiten representar citas y sus fuentes.
- `abbr`, `address`, `time`, `code`, `sup`, `sub`, `u` y `s` aportan significado específico al contenido.
- `ruby`, `rt` y `rp` permiten anotaciones de pronunciación.
- `tel:` y `mailto:` crean enlaces de teléfono y correo.
- Los enlaces internos relacionan `href="#id"` con un elemento que posea ese `id`.
