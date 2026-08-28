# HTML Accessibility

Resumen del módulo **HTML Accessibility** del curso **Responsive Web Design v9** de freeCodeCamp.

## 1. Qué es la accesibilidad web

La **accesibilidad web** busca que sitios y aplicaciones puedan ser utilizados por la mayor cantidad posible de personas, incluidas aquellas con discapacidades:

- visuales;
- auditivas;
- motoras;
- cognitivas.

No consiste únicamente en adaptar una página para screen readers. También incluye navegación por teclado, contenido comprensible, multimedia accesible y estructuras robustas.

---

## 2. WCAG

**WCAG (Web Content Accessibility Guidelines)** es un conjunto de recomendaciones para crear contenido web accesible.

Sus cuatro principios se resumen con el acrónimo **POUR**:

| Principio | Significado |
| --- | --- |
| **P**erceivable | Perceptible |
| **O**perable | Operable |
| **U**nderstandable | Comprensible |
| **R**obust | Robusto |

### Perceivable

El contenido debe poder ser percibido por el usuario mediante distintas formas.

Ejemplos:

- texto alternativo para imágenes;
- captions para video;
- transcripciones para audio.

### Operable

La interfaz debe poder utilizarse mediante diferentes métodos de interacción.

Ejemplos:

- navegación por teclado;
- foco visible;
- controles accesibles.

### Understandable

La información y la interacción deben resultar comprensibles y predecibles.

### Robust

El contenido debe funcionar correctamente con distintos navegadores, dispositivos y tecnologías de asistencia.

---

## 3. Tecnologías de asistencia

### Screen readers

Programas que interpretan el contenido y lo presentan mediante voz sintetizada o dispositivos braille.

Son especialmente utilizados por personas ciegas o con dificultades visuales.

Para funcionar correctamente dependen de:

- estructura HTML clara;
- elementos semánticos;
- labels;
- nombres accesibles;
- información ARIA cuando es necesaria.

### Teclados de texto grande o braille

Permiten a personas con discapacidades visuales interactuar con dispositivos mediante teclas adaptadas o braille.

### Screen magnifiers

Amplían visualmente regiones de la pantalla.

Son útiles para personas con baja visión.

### Alternative pointing devices

Dispositivos alternativos al mouse tradicional, como:

- joysticks;
- trackballs;
- touchpads;
- otros dispositivos adaptados.

### Voice recognition

Permite controlar una computadora mediante comandos de voz y puede resultar especialmente útil para personas con discapacidades motoras.

---

## 4. Herramientas de auditoría

Existen herramientas automáticas que ayudan a detectar problemas de accesibilidad.

Entre las mencionadas por freeCodeCamp se encuentran:

- Google Lighthouse;
- WAVE;
- IBM Equal Access Accessibility Checker;
- axe DevTools.

Estas herramientas pueden encontrar muchos problemas, pero no reemplazan las pruebas manuales.

La accesibilidad también debe comprobarse mediante:

- navegación sólo con teclado;
- lectura y comprensión del contenido;
- prueba con tecnologías de asistencia cuando sea posible.

---

# Buenas prácticas de accesibilidad

## 5. Jerarquía de encabezados

Los encabezados deben reflejar la estructura lógica del documento.

```html
<h1>Documentation</h1>

<h2>Installation</h2>

<h3>Windows</h3>
<h3>Linux</h3>

<h2>Configuration</h2>
```

Una jerarquía correcta ayuda a los usuarios de tecnologías de asistencia a comprender y navegar el contenido.

---

## 6. Tablas accesibles

Las tablas deben utilizar elementos que describan correctamente su estructura.

### `th`

Representa una celda de encabezado.

```html
<th>Name</th>
```

### `td`

Representa una celda de datos.

```html
<td>Alex</td>
```

### `caption`

Describe el propósito de la tabla.

Debe ubicarse inmediatamente después de abrir `table`:

```html
<table>
  <caption>Exam Grades</caption>
  ...
</table>
```

Esto permite que un screen reader pueda anunciar el propósito de la tabla antes de recorrer sus datos.

---

## 7. Labels en formularios

Los inputs deben tener un nombre o label que comunique claramente su propósito.

```html
<label for="email">Email:</label>
<input id="email" type="email">
```

La relación se establece mediante:

```text
for="email" → id="email"
```

Esto ayuda tanto a usuarios visuales como a tecnologías de asistencia.

---

## 8. Uso de `span`

`span` es un contenedor inline genérico.

No posee significado semántico propio, pero puede utilizarse para:

- aplicar estilos a una parte del texto;
- envolver contenido;
- proporcionar un `id` que pueda ser referenciado desde atributos ARIA.

```html
<span id="password-help">
  Your password must contain at least 8 characters.
</span>
```

---

## 9. Texto alternativo para imágenes

El atributo `alt` proporciona una alternativa textual.

```html
<img
  src="dog.jpg"
  alt="A golden retriever running through snow"
>
```

Un buen texto alternativo debe comunicar la información importante de la imagen dentro de su contexto.

No debe limitarse a frases genéricas como:

```text
image
picture
photo
```

si la imagen transmite información relevante.

### Imágenes decorativas

Cuando una imagen es puramente decorativa, normalmente puede utilizarse:

```html
alt=""
```

Esto permite que los screen readers puedan ignorarla.

---

## 10. Texto descriptivo en enlaces

El texto de un enlace debe indicar su destino o propósito.

Menos útil:

```html
<a href="/docs">Click here</a>
```

Más descriptivo:

```html
<a href="/docs">Read the HTML documentation</a>
```

Esto beneficia especialmente a quienes navegan enlaces mediante tecnologías de asistencia y pueden escucharlos fuera del contexto del párrafo.

---

## 11. Audio y video accesible

Para personas con discapacidades auditivas deberían ofrecerse:

- captions;
- transcripts.

Para personas con discapacidades visuales puede ser necesario proporcionar:

- audio descriptions.

### Captions

Representan mediante texto el diálogo y sonidos relevantes de un video.

### Transcript

Proporciona una versión textual del contenido hablado.

### Audio description

Describe información visual importante que no puede deducirse únicamente mediante el audio original.

---

# Navegación por teclado

## 12. Foco

Un elemento **focusable** puede recibir el foco del teclado.

Los elementos interactivos nativos, como:

- enlaces;
- botones;
- inputs;

ya poseen comportamiento de teclado adecuado en muchos casos.

El foco es fundamental para usuarios que no utilizan mouse.

---

## 13. `tabindex`

`tabindex` permite controlar si un elemento puede recibir foco y cómo participa en la navegación con `Tab`.

### `tabindex="0"`

Hace que un elemento participe del orden de tabulación natural.

```html
<div tabindex="0">Focusable content</div>
```

### `tabindex="-1"`

Permite que el elemento reciba foco de forma programática, pero evita que forme parte del recorrido normal con `Tab`.

```html
<p tabindex="-1">
  Sorry, there was an error with your submission.
</p>
```

Puede ser útil para dirigir el foco hacia:

- mensajes de error;
- contenido actualizado;
- regiones específicas.

### Valores mayores que `0`

Debe evitarse:

```html
tabindex="1"
tabindex="2"
```

Asignar valores positivos altera manualmente el orden natural del documento y puede producir una experiencia confusa o difícil de mantener.

La recomendación general es utilizar:

```text
0
-1
```

cuando `tabindex` sea realmente necesario.

---

## 14. `accesskey`

Define un atajo de teclado para activar o enfocar un elemento.

```html
<button accesskey="s">Save</button>
```

También puede utilizarse con enlaces:

```html
<a href="/" accesskey="h">Home</a>
```

Puede ayudar a ciertos usuarios, aunque los atajos deben diseñarse con cuidado porque pueden entrar en conflicto con combinaciones del navegador, sistema operativo o tecnología de asistencia.

---

# WAI-ARIA

## 15. Qué es WAI-ARIA

**WAI-ARIA** significa:

**Web Accessibility Initiative – Accessible Rich Internet Applications**.

ARIA proporciona roles y atributos que permiten comunicar información adicional sobre elementos y componentes a tecnologías de asistencia.

ARIA es especialmente útil para interfaces dinámicas o componentes que no pueden expresarse completamente mediante HTML nativo.

Sin embargo, cuando existe un elemento HTML semántico que representa correctamente el comportamiento deseado, normalmente debe preferirse ese elemento nativo.

---

## 16. ARIA roles

Los **roles** indican qué función cumple un elemento.

Ejemplos:

```html
role="tab"
role="menu"
role="alert"
```

Existen seis categorías principales de roles.

### Document structure roles

Describen la estructura general del documento y las relaciones entre partes del contenido.

### Widget roles

Describen componentes interactivos.

Ejemplo conceptual:

```text
scrollbar
tab
menuitem
```

### Landmark roles

Identifican regiones importantes de la página y facilitan la navegación.

Los screen readers pueden utilizarlos para saltar rápidamente entre secciones principales.

### Live region roles

Representan regiones cuyo contenido puede cambiar dinámicamente.

Permiten que tecnologías de asistencia anuncien actualizaciones importantes.

Un ejemplo es:

```html
role="alert"
```

### Window roles

Representan subventanas o interfaces similares.

Ejemplos:

```text
dialog
alertdialog
```

### Abstract roles

Son utilizados internamente para organizar el modelo ARIA.

**No deben ser utilizados directamente por desarrolladores.**

---

# Nombres y descripciones accesibles

## 17. `aria-label`

Define directamente el nombre accesible de un elemento.

Puede utilizarse cuando el control no posee texto visible suficiente.

```html
<button aria-label="Search">
  <i class="fas fa-search"></i>
</button>
```

Visualmente el botón puede mostrar únicamente un icono, mientras que el screen reader recibe el nombre:

```text
Search
```

---

## 18. `aria-labelledby`

Permite que uno o varios elementos existentes proporcionen el nombre accesible.

```html
<h2 id="dialog-title">Delete account?</h2>

<div
  role="dialog"
  aria-labelledby="dialog-title"
>
  ...
</div>
```

La diferencia conceptual es:

```text
aria-label       → define el texto directamente.
aria-labelledby  → referencia texto existente mediante un id.
```

---

## 19. `aria-describedby`

Relaciona un elemento con contenido adicional que lo describe.

Ejemplo:

```html
<form>
  <label for="password">Password:</label>

  <input
    type="password"
    id="password"
    aria-describedby="password-help"
  >

  <p id="password-help">
    Your password must be at least 8 characters long.
  </p>
</form>
```

Relación:

```text
aria-describedby="password-help"
                     ↓
id="password-help"
```

Es útil para:

- instrucciones;
- requisitos;
- mensajes de error;
- información adicional.

---

## 20. `aria-hidden`

Oculta un elemento del **accessibility tree**, por lo que tecnologías como los screen readers no lo anuncian.

```html
<button>
  <i
    class="fa-solid fa-gear"
    aria-hidden="true"
  ></i>
  <span>Settings</span>
</button>
```

En este caso el icono es decorativo y el texto `Settings` ya comunica el propósito del botón.

`aria-hidden="true"` no oculta visualmente el elemento: sólo evita que sea expuesto a tecnologías de asistencia.

No debe utilizarse sobre contenido importante que el usuario necesite comprender o manipular.

---

## 21. HTML semántico antes que ARIA

Una regla importante al trabajar con accesibilidad es preferir elementos HTML nativos cuando ya proporcionan la semántica y comportamiento necesarios.

Preferible:

```html
<button>Save</button>
```

En lugar de intentar recrear un botón genérico:

```html
<div role="button">Save</div>
```

El `button` nativo ya incorpora:

- semántica;
- foco;
- comportamiento de teclado;
- integración con tecnologías de asistencia.

ARIA debe complementar HTML cuando sea necesario, no reemplazar innecesariamente la semántica nativa.

---

## Resumen rápido

Los conceptos fundamentales de **HTML Accessibility** son:

- WCAG se organiza alrededor de los principios **POUR**: Perceivable, Operable, Understandable y Robust.
- La accesibilidad contempla múltiples discapacidades y formas de interacción.
- Screen readers, magnificadores, dispositivos alternativos y reconocimiento de voz son tecnologías de asistencia.
- Una estructura correcta de encabezados, tablas, labels y enlaces mejora la navegación.
- Las imágenes relevantes necesitan texto alternativo adecuado.
- Audio y video deberían ofrecer captions, transcripts y, cuando corresponda, audio descriptions.
- La navegación por teclado y el foco son aspectos esenciales.
- `tabindex` debería utilizar principalmente `0` o `-1`, evitando valores positivos.
- WAI-ARIA aporta roles y atributos adicionales para interfaces accesibles.
- `aria-label` define un nombre; `aria-labelledby` lo toma de otro elemento; `aria-describedby` agrega una descripción.
- `aria-hidden="true"` evita que contenido decorativo sea anunciado por tecnologías de asistencia.
- Siempre que sea posible, debe preferirse HTML semántico nativo antes que recrear comportamiento con ARIA.
