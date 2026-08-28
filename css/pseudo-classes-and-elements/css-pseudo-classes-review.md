# CSS Pseudo-classes

Resumen del módulo **CSS Pseudo-classes** del curso **Responsive Web Design v9** de freeCodeCamp.

## 1. Qué es una pseudo-class

Una **pseudo-class** es una keyword añadida a un selector para seleccionar un elemento según:

- su estado;
- su posición;
- su relación con otros elementos;
- la interacción del usuario.

Sintaxis:

```css
selector:pseudo-class {
  property: value;
}
```

Ejemplo:

```css
button:hover {
  background-color: black;
}
```

---

# User Action Pseudo-classes

## 2. `:hover`

Selecciona un elemento mientras el puntero está sobre él.

```css
button:hover {
  background-color: navy;
}
```

No debe utilizarse como única forma de comunicar información importante, ya que dispositivos táctiles no tienen necesariamente hover.

---

## 3. `:active`

Representa el estado durante la activación del elemento.

```css
button:active {
  transform: scale(0.98);
}
```

En un botón suele corresponder al momento en el que está siendo presionado.

---

## 4. `:focus`

Se aplica cuando un elemento recibe foco.

```css
input:focus {
  outline: 2px solid blue;
}
```

El foco puede obtenerse mediante:

- teclado;
- click;
- scripts.

Mantener un indicador visible de foco es importante para accesibilidad.

---

## 5. `:focus-within`

Selecciona un elemento cuando:

- el propio elemento tiene foco;
- alguno de sus descendientes tiene foco.

```css
form:focus-within {
  border-color: blue;
}
```

Es útil para destacar un grupo completo cuando uno de sus controles está activo.

---

# Input Pseudo-classes

## 6. `:enabled`

Selecciona controles habilitados.

```css
input:enabled {
  background: white;
}
```

---

## 7. `:disabled`

Selecciona controles deshabilitados.

```css
button:disabled {
  opacity: 0.5;
}
```

---

## 8. `:checked`

Selecciona radio buttons o checkboxes marcados.

```css
input:checked {
  accent-color: green;
}
```

---

## 9. `:valid`

Selecciona controles cuyo valor cumple las reglas de validación.

```css
input:valid {
  border-color: green;
}
```

---

## 10. `:invalid`

Selecciona controles que no cumplen las restricciones.

```css
input:invalid {
  border-color: red;
}
```

---

## 11. `:in-range`

Selecciona valores dentro de los límites establecidos.

```html
<input type="number" min="1" max="10">
```

```css
input:in-range {
  border-color: green;
}
```

---

## 12. `:out-of-range`

Selecciona valores fuera del rango permitido.

```css
input:out-of-range {
  border-color: red;
}
```

---

## 13. `:required`

Selecciona controles con el atributo `required`.

```css
input:required {
  border-left: 3px solid orange;
}
```

---

## 14. `:optional`

Selecciona controles que no son obligatorios.

```css
input:optional {
  border-left: 3px solid gray;
}
```

---

## 15. `:autofill`

Selecciona campos rellenados automáticamente por el navegador.

```css
input:autofill {
  background-color: lightyellow;
}
```

---

# Location Pseudo-classes

## 16. `:any-link`

Selecciona enlaces que poseen `href`, hayan sido visitados o no.

Conceptualmente combina:

```text
:link
:visited
```

```css
:any-link {
  text-decoration: none;
}
```

---

## 17. `:link`

Selecciona enlaces no visitados.

```css
a:link {
  color: blue;
}
```

---

## 18. `:visited`

Selecciona enlaces visitados.

```css
a:visited {
  color: purple;
}
```

Los navegadores restringen algunas propiedades que pueden aplicarse a `:visited` por privacidad.

---

## 19. `:local-link`

Está pensada para seleccionar links que apuntan al mismo documento o contexto local.

Puede utilizarse para distinguir navegación interna de links externos.

---

## 20. `:target`

Selecciona el elemento cuyo `id` coincide con el fragmento de la URL.

Si la URL es:

```text
example.com/page#pricing
```

entonces:

```html
<section id="pricing">
```

puede seleccionarse con:

```css
:target {
  background-color: yellow;
}
```

---

# Tree-structural Pseudo-classes

## 21. `:root`

Selecciona el elemento raíz.

En HTML suele ser:

```html
<html>
```

Uso muy frecuente:

```css
:root {
  --primary-color: navy;
}
```

---

## 22. `:empty`

Selecciona elementos que no contienen nodos hijos relevantes.

```css
p:empty {
  display: none;
}
```

---

## 23. `:first-child`

Selecciona un elemento si es el primer hijo de su padre.

```css
li:first-child {
  font-weight: bold;
}
```

---

## 24. `:last-child`

Selecciona el último hijo.

```css
li:last-child {
  margin-bottom: 0;
}
```

---

## 25. `:only-child`

Selecciona un elemento si es el único hijo del padre.

```css
li:only-child {
  list-style: none;
}
```

---

## 26. `:nth-child()`

Selecciona elementos según su posición entre los hijos.

```css
li:nth-child(2) {
  color: red;
}
```

También acepta patrones:

```css
li:nth-child(odd) {
  background: #eee;
}
```

```css
li:nth-child(2n) {
  background: #eee;
}
```

---

## 27. `:nth-last-child()`

Funciona como `:nth-child()`, pero cuenta desde el final.

```css
li:nth-last-child(2) {
  color: blue;
}
```

---

# Pseudo-classes `of-type`

Estas pseudo-classes tienen en cuenta la posición entre hermanos del **mismo tipo de elemento**.

## 28. `:first-of-type`

```css
p:first-of-type {
  font-weight: bold;
}
```

Selecciona el primer `p` entre los elementos hermanos de tipo `p`.

---

## 29. `:last-of-type`

```css
p:last-of-type {
  margin-bottom: 0;
}
```

---

## 30. `:nth-of-type()`

```css
p:nth-of-type(2) {
  color: green;
}
```

Cuenta sólo elementos del mismo tipo.

---

## 31. `:only-of-type`

Selecciona un elemento si es el único de su tipo dentro del padre.

```css
img:only-of-type {
  display: block;
}
```

---

# Functional Pseudo-classes

Las **functional pseudo-classes** reciben argumentos.

---

## 32. `:is()`

Permite agrupar alternativas de selectores.

```css
p:is(.warning, .error) {
  color: red;
}
```

Equivale conceptualmente a seleccionar:

```text
p.warning
o
p.error
```

Ayuda a evitar repetición.

---

## 33. `:where()`

Funciona de forma similar a `:is()`, pero su especificidad es siempre:

```text
0
```

```css
:where(h1, h2, h3) {
  margin: 0;
}
```

Es especialmente útil para estilos base fáciles de sobrescribir.

---

## 34. `:has()`

Selecciona un elemento según lo que contiene o según relaciones con otros elementos.

```css
article:has(h2) {
  border: 2px solid hotpink;
}
```

Esto selecciona artículos que contienen un `h2`.

Por eso suele describirse informalmente como un **parent selector**, aunque puede expresar relaciones más amplias.

---

## 35. `:not()`

Selecciona elementos que no coinciden con un selector.

```css
p:not(.example) {
  color: blue;
}
```

---

# Pseudo-elements

Una **pseudo-element** selecciona una parte o región conceptual de un elemento, no un estado.

Normalmente utiliza doble `::`.

---

## 36. `::before`

Inserta contenido generado antes del contenido real.

```css
.note::before {
  content: "ℹ ";
}
```

Se usa principalmente para contenido decorativo.

---

## 37. `::after`

Inserta contenido generado después.

```css
.external::after {
  content: " ↗";
}
```

---

## 38. `::first-letter`

Selecciona la primera letra.

```css
article p:first-of-type::first-letter {
  font-size: 2rem;
}
```

---

## 39. `::marker`

Selecciona el marcador de listas.

```css
li::marker {
  color: red;
}
```

Puede modificar bullets o numeración.

---

# Diferencia entre pseudo-class y pseudo-element

### Pseudo-class

Representa estado, posición o condición:

```css
button:hover
input:valid
li:first-child
```

### Pseudo-element

Representa una parte conceptual:

```css
p::first-letter
li::marker
div::before
```

---

## Resumen rápido

Los conceptos fundamentales de **CSS Pseudo-classes** son:

- Las pseudo-classes seleccionan elementos por estado, posición o relación.
- `:hover`, `:active`, `:focus` y `:focus-within` responden a interacción.
- `:enabled`, `:disabled`, `:checked`, `:valid`, `:invalid`, `:required` y otras permiten estilizar formularios por estado.
- `:link`, `:visited`, `:any-link`, `:local-link` y `:target` están relacionadas con ubicación y navegación.
- `:first-child`, `:last-child`, `:nth-child()` y similares seleccionan según posición en el árbol.
- Las variantes `*-of-type` cuentan sólo elementos del mismo tipo.
- `:is()` agrupa alternativas.
- `:where()` funciona como `:is()` pero con especificidad `0`.
- `:has()` selecciona según relaciones o descendientes.
- `:not()` excluye coincidencias.
- `::before`, `::after`, `::first-letter` y `::marker` son pseudo-elements.
