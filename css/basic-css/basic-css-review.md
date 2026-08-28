# Basic CSS

Resumen del módulo **Basic CSS** del curso **Responsive Web Design v9** de freeCodeCamp.

# Fundamentos de CSS

## 1. Qué es CSS

**CSS (Cascading Style Sheets)** es un lenguaje de estilos utilizado para controlar la presentación visual de documentos HTML.

Permite definir aspectos como:

- colores;
- tipografía;
- fondos;
- tamaños;
- espaciado;
- layouts;
- bordes;
- comportamiento visual responsive.

HTML describe principalmente la estructura y el contenido; CSS describe cómo se presentan.

---

## 2. Anatomía de una regla CSS

Una regla CSS tiene dos partes principales:

1. **selector**;
2. **declaration block**.

Sintaxis:

```css
selector {
  property: value;
}
```

Ejemplo:

```css
p {
  color: red;
  font-size: 18px;
}
```

### Selector

Determina qué elementos serán estilizados.

```css
p
```

### Declaration block

Es el bloque delimitado por `{}`:

```css
{
  color: red;
  font-size: 18px;
}
```

### Declaration

Cada declaración está formada por:

```text
property: value;
```

Ejemplo:

```css
color: red;
```

---

## 3. `meta viewport`

Una página responsive suele incluir:

```html
<meta
  name="viewport"
  content="width=device-width, initial-scale=1.0"
>
```

Este elemento le indica al navegador cómo controlar el ancho y la escala de la página en distintos dispositivos.

Es especialmente importante en:

- teléfonos;
- tablets;
- interfaces responsive.

Sin una configuración adecuada del viewport, una página puede representarse con una escala incorrecta en dispositivos móviles.

---

## 4. Default Browser Styles

Los navegadores aplican estilos predeterminados a muchos elementos HTML.

Por ejemplo, pueden existir valores por defecto para:

- `margin`;
- `padding`;
- tamaño de headings;
- estilos de listas;
- estilos de enlaces.

Por eso un elemento puede verse estilizado incluso si todavía no escribiste CSS.

Ejemplo conceptual:

```html
<h1>Title</h1>
```

El navegador suele mostrarlo grande y en negrita mediante su **user agent stylesheet**.

---

# Formas de aplicar CSS

## 5. Inline CSS

El CSS se escribe directamente dentro del atributo `style`.

```html
<p style="color: red;">
  Red paragraph
</p>
```

Ventajas:

- útil para pruebas rápidas;
- aplica directamente al elemento.

Desventajas:

- mezcla estructura con presentación;
- difícil de reutilizar;
- difícil de mantener;
- alta specificity.

Por eso normalmente se evita en proyectos reales.

---

## 6. Internal CSS

Se escribe dentro de un elemento `style`, normalmente en `head`.

```html
<head>
  <style>
    p {
      color: red;
    }
  </style>
</head>
```

Puede ser útil para:

- demos;
- ejemplos pequeños;
- documentos simples.

Pero no suele ser la mejor opción para proyectos grandes.

---

## 7. External CSS

Se escribe en un archivo separado:

```text
styles.css
```

Y se vincula desde HTML:

```html
<link
  rel="stylesheet"
  href="styles.css"
>
```

Es la opción habitual para proyectos reales porque mejora:

- separación de responsabilidades;
- reutilización;
- mantenimiento;
- organización.

---

# Dimensiones

## 8. `width`

Controla el ancho de un elemento.

```css
.box {
  width: 300px;
}
```

Si no se especifica:

```css
width: auto;
```

El navegador calcula el ancho según:

- contenido;
- elemento padre;
- `display`;
- reglas de layout.

---

## 9. `min-width`

Define el ancho mínimo permitido.

```css
.card {
  min-width: 200px;
}
```

El elemento no debería reducirse por debajo de ese valor.

---

## 10. `max-width`

Define el ancho máximo.

```css
.container {
  max-width: 1200px;
}
```

Es muy útil en layouts responsive.

Ejemplo típico:

```css
img {
  max-width: 100%;
}
```

Evita que una imagen supere el ancho disponible.

---

## 11. `height`

Controla la altura.

```css
.box {
  height: 200px;
}
```

Por defecto:

```css
height: auto;
```

Esto permite que la altura se adapte al contenido.

---

## 12. `min-height`

Define una altura mínima.

```css
.hero {
  min-height: 400px;
}
```

---

## 13. `max-height`

Define una altura máxima.

```css
.panel {
  max-height: 500px;
}
```

---

# CSS Combinators

Los **combinators** permiten expresar relaciones entre elementos.

---

## 14. Descendant Combinator

Sintaxis:

```css
parent descendant
```

Ejemplo:

```css
ul li {
  color: blue;
}
```

Selecciona todos los `li` que estén dentro de un `ul`, sin importar cuántos niveles de profundidad existan.

HTML:

```html
<ul>
  <li>Item</li>
</ul>
```

También seleccionaría un `li` más profundo:

```html
<ul>
  <div>
    <li>Item</li>
  </div>
</ul>
```

---

## 15. Child Combinator `>`

Selecciona únicamente hijos directos.

```css
.container > p {
  color: red;
}
```

HTML:

```html
<div class="container">
  <p>Selected</p>

  <div>
    <p>Not selected</p>
  </div>
</div>
```

Diferencia:

```text
A B  → cualquier descendiente B dentro de A
A > B → sólo hijos directos B de A
```

---

## 16. Next-sibling Combinator `+`

Selecciona el hermano inmediatamente siguiente.

```css
h2 + p {
  color: red;
}
```

HTML:

```html
<h2>Title</h2>
<p>Selected</p>
<p>Not selected</p>
```

Sólo selecciona el primer `p`.

---

## 17. Subsequent-sibling Combinator `~`

Selecciona hermanos posteriores que compartan el mismo padre.

```css
h2 ~ p {
  color: red;
}
```

HTML:

```html
<h2>Title</h2>
<p>Selected</p>
<p>Selected</p>
```

Diferencia:

```text
A + B → sólo el siguiente B
A ~ B → todos los B posteriores hermanos
```

---

# Comportamiento de display

## 18. Inline Elements

Los elementos inline:

- no comienzan automáticamente en una nueva línea;
- ocupan sólo el ancho necesario;
- fluyen junto con el texto.

Ejemplos habituales:

```html
<span>
<a>
<img>
```

Ejemplo:

```html
<span>One</span>
<span>Two</span>
```

Aparecen normalmente en la misma línea si hay espacio.

---

## 19. Block Elements

Los elementos block:

- comienzan en una nueva línea;
- ocupan por defecto todo el ancho disponible.

Ejemplos:

```html
<div>
<p>
<section>
```

---

## 20. `inline-block`

Se define mediante:

```css
display: inline-block;
```

Combina características de ambos modelos:

- participa en el flujo inline;
- permite definir `width` y `height` como un bloque.

Ejemplo:

```css
.badge {
  display: inline-block;
  width: 100px;
  height: 40px;
}
```

---

# Box Model: Margin y Padding

## 21. `margin`

Crea espacio **fuera** del borde del elemento.

Conceptualmente:

```text
elemento
↓
border
↓
margin
↓
otros elementos
```

Ejemplo:

```css
.card {
  margin: 20px;
}
```

---

## 22. `padding`

Crea espacio **dentro** del borde, entre contenido y borde.

```css
.card {
  padding: 20px;
}
```

Conceptualmente:

```text
border
  padding
    content
```

---

## 23. Diferencia entre margin y padding

```text
padding → espacio interno
margin  → espacio externo
```

---

# Shorthand de spacing

## 24. Un valor

```css
margin: 20px;
```

Se aplica a:

```text
top
right
bottom
left
```

---

## 25. Dos valores

```css
margin: 10px 20px;
```

Equivale a:

```text
top/bottom → 10px
left/right → 20px
```

---

## 26. Tres valores

```css
margin: 10px 20px 30px;
```

Equivale a:

```text
top        → 10px
left/right → 20px
bottom     → 30px
```

---

## 27. Cuatro valores

```css
margin: 10px 20px 30px 40px;
```

Orden:

```text
top
right
bottom
left
```

Puede recordarse como recorrido horario:

```text
TRBL
Top Right Bottom Left
```

La misma lógica se aplica a:

```css
padding
```

---

# CSS Specificity

## 28. Qué es specificity

La **specificity** representa el peso de un selector cuando varias reglas compiten por aplicar la misma propiedad a un elemento.

Ejemplo:

```css
p {
  color: blue;
}

.message {
  color: red;
}
```

HTML:

```html
<p class="message">Text</p>
```

La clase tiene mayor specificity, por lo que el texto será rojo.

---

## 29. Representación de specificity

El review utiliza una estructura de cuatro componentes:

```text
(inline, IDs, classes, types)
```

Ejemplo:

```text
(0, 0, 1, 0)
```

Cada posición representa una categoría de selector.

---

## 30. Universal Selector `*`

```css
* {
  box-sizing: border-box;
}
```

Specificity:

```text
(0, 0, 0, 0)
```

Es el selector de menor peso.

---

## 31. Type Selector

Selecciona por nombre de elemento.

```css
p {
  color: blue;
}
```

Specificity:

```text
(0, 0, 0, 1)
```

---

## 32. Class Selector

```css
.message {
  color: red;
}
```

Specificity:

```text
(0, 0, 1, 0)
```

Tiene más peso que un type selector.

---

## 33. ID Selector

```css
#message {
  color: green;
}
```

Specificity:

```text
(0, 1, 0, 0)
```

Tiene más peso que clases y type selectors.

---

## 34. Inline Styles

```html
<p style="color: purple;">
```

Specificity:

```text
(1, 0, 0, 0)
```

Tienen más peso que los selectors normales.

---

## Comparación

```text
Universal   → (0, 0, 0, 0)
Type        → (0, 0, 0, 1)
Class       → (0, 0, 1, 0)
ID          → (0, 1, 0, 0)
Inline      → (1, 0, 0, 0)
```

De forma simplificada:

```text
inline > id > class > type > universal
```

---

# Internal vs External CSS y Specificity

## 35. La ubicación no determina specificity

Internal y external CSS no tienen una specificity distinta por estar ubicados en lugares diferentes.

Ejemplo:

```html
<style>
  .message {
    color: red;
  }
</style>
```

y:

```css
.message {
  color: blue;
}
```

tienen la misma specificity si usan el mismo selector.

Si compiten por la misma propiedad y tienen igual prioridad, puede intervenir el **source order**.

---

# Source Order

## 36. Regla posterior

Cuando dos declaraciones tienen:

- mismo origen relevante;
- misma importancia;
- misma specificity;

la que aparece después gana.

```css
p {
  color: blue;
}

p {
  color: red;
}
```

Resultado:

```text
red
```

---

# `!important`

## 37. Keyword `!important`

Puede forzar una declaración a tener prioridad sobre declaraciones normales.

```css
p {
  color: red !important;
}
```

Debe utilizarse con cautela porque puede:

- dificultar overrides;
- complicar debugging;
- generar CSS difícil de mantener.

No debería ser la primera solución ante un problema de specificity.

---

# Cascade

## 38. Qué es la cascade

La **cascade** es el mecanismo que CSS utiliza para decidir qué declaración aplicar cuando varias reglas afectan la misma propiedad.

El navegador tiene en cuenta factores como:

- origen;
- importancia;
- specificity;
- source order.

La specificity es sólo una parte de la cascade.

---

# Inheritance

## 39. Qué es inheritance

La **inheritance** permite que ciertas propiedades pasen desde un elemento padre hacia sus descendientes.

Ejemplo:

```css
body {
  color: navy;
}
```

HTML:

```html
<body>
  <p>This text can inherit navy.</p>
</body>
```

Muchas propiedades relacionadas con texto suelen heredarse.

Ejemplos habituales:

```text
color
font-family
font-size
line-height
```

No todas las propiedades se heredan.

Por ejemplo, normalmente:

```text
margin
padding
border
width
height
```

no se heredan automáticamente.

---

# Relación entre cascade, specificity e inheritance

Estos conceptos están relacionados pero no significan lo mismo.

### Cascade

Decide qué declaración gana cuando existen múltiples candidatas.

### Specificity

Es uno de los criterios usados por la cascade para comparar selectors.

### Inheritance

Permite que un valor llegue desde un ancestro cuando el elemento no posee un valor ganador propio para esa propiedad.

Conceptualmente:

```text
declarations aplicables
        ↓
cascade
        ↓
specificity / source order / importance
        ↓
valor ganador
```

Si no hay una declaración aplicable y la propiedad es heredable:

```text
valor del padre
```

---

# Resumen rápido

Los conceptos fundamentales de **Basic CSS** son:

- CSS controla la presentación visual del HTML.
- Una regla CSS tiene un selector y un declaration block.
- Cada declaration utiliza `property: value`.
- `meta viewport` es importante para páginas responsive en dispositivos móviles.
- Los navegadores aplican estilos por defecto.
- CSS puede ser inline, internal o external.
- External CSS suele ser la opción preferida para proyectos reales.
- `width`, `min-width`, `max-width`, `height`, `min-height` y `max-height` controlan dimensiones.
- El descendant combinator selecciona cualquier descendiente.
- `>` selecciona hijos directos.
- `+` selecciona el sibling inmediatamente siguiente.
- `~` selecciona siblings posteriores.
- Los elementos inline y block tienen comportamientos distintos.
- `inline-block` combina flujo inline con dimensiones de block.
- `padding` crea espacio interno y `margin` espacio externo.
- Las shorthand de margin y padding aceptan entre uno y cuatro valores.
- Specificity determina el peso relativo de selectors en conflictos.
- La jerarquía básica es `inline > id > class > type > universal`.
- Internal y external CSS no tienen specificity distinta por su ubicación.
- Si la specificity empata, el source order puede decidir.
- `!important` debe utilizarse con cautela.
- La cascade determina qué declaración termina aplicándose.
- Inheritance permite que determinadas propiedades pasen de padres a hijos.
