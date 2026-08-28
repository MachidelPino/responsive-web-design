# CSS Relative and Absolute Units

Resumen del módulo **CSS Relative and Absolute Units** del curso **Responsive Web Design v9** de freeCodeCamp.

## 1. Unidades absolutas

Las **absolute units** tienen una relación fija entre sí dentro del modelo de CSS.

Son útiles cuando se necesita una medida específica y no dependiente de otro elemento.

---

## 2. `px`

`px` es la unidad absoluta más utilizada en CSS.

```css
.box {
  width: 200px;
}
```

En CSS:

```text
1in = 96px
```

Por definición:

```text
1px = 1/96in
```

Un CSS pixel no debe interpretarse necesariamente como un pixel físico exacto de la pantalla.

---

## 3. `in`

Representa pulgadas.

```text
1in = 96px
```

```css
.box {
  width: 1in;
}
```

---

## 4. `cm`

Representa centímetros.

```css
.box {
  width: 2cm;
}
```

Relación estándar:

```text
1in = 2.54cm
```

---

## 5. `mm`

Representa milímetros.

```text
10mm = 1cm
```

```css
.box {
  width: 10mm;
}
```

---

## 6. `q`

Representa **quarter-millimeters**.

```text
1q = 1/4mm
40q = 1cm
```

---

## 7. `pc`

Representa **picas**.

```text
1pc = 1/6in
```

---

## 8. `pt`

Representa **points**.

```text
1pt = 1/72in
```

Es una unidad frecuente en contextos tipográficos e impresión.

---

## Tabla de unidades absolutas

| Unidad | Significado | Relación |
| --- | --- | --- |
| `px` | pixel CSS | `1/96in` |
| `in` | inch | `96px` |
| `cm` | centimeter | `1/2.54in` |
| `mm` | millimeter | `1/10cm` |
| `q` | quarter-millimeter | `1/40cm` |
| `pc` | pica | `1/6in` |
| `pt` | point | `1/72in` |

---

# Unidades relativas

Las **relative units** dependen de otro valor.

Pueden depender de:

- un elemento padre;
- el font size;
- el root element;
- el viewport.

Son fundamentales para interfaces flexibles y responsive.

---

## 9. Porcentajes

Un porcentaje se calcula con respecto a un valor de referencia que depende de la propiedad.

Ejemplo:

```css
.child {
  width: 50%;
}
```

En este caso, el ancho es aproximadamente la mitad del ancho disponible del contenedor padre.

---

## 10. `em`

`em` se relaciona con el tamaño de fuente.

En muchas propiedades:

```text
1em = font-size del propio elemento
```

Ejemplo:

```css
.button {
  font-size: 20px;
  padding: 1em;
}
```

El padding será proporcional al tamaño del texto.

### `em` en `font-size`

Cuando `em` se utiliza en la propia propiedad `font-size`, se calcula respecto al `font-size` heredado del padre.

```css
.parent {
  font-size: 20px;
}

.child {
  font-size: 2em;
}
```

Resultado:

```text
2 × 20px = 40px
```

### Posible efecto acumulativo

Con elementos anidados pueden producirse escalados sucesivos.

```css
.parent {
  font-size: 1.2em;
}
```

Si esa regla se repite en distintos niveles, el tamaño puede multiplicarse.

---

## 11. `rem`

`rem` significa **root em**.

Se calcula respecto al tamaño de fuente del elemento raíz:

```html
<html>
```

Ejemplo:

```css
html {
  font-size: 16px;
}

.title {
  font-size: 2rem;
}
```

Resultado:

```text
2 × 16px = 32px
```

La diferencia principal:

```text
em  → depende del contexto del elemento
rem → depende del root
```

Esto hace que `rem` sea muy útil para mantener escalas consistentes.

---

# Unidades de viewport

## 12. `vh`

`vh` significa **viewport height**.

```text
1vh = 1% de la altura del viewport
```

Ejemplo:

```css
.hero {
  height: 100vh;
}
```

Esto intenta ocupar toda la altura del viewport.

---

## 13. `vw`

`vw` significa **viewport width**.

```text
1vw = 1% del ancho del viewport
```

Ejemplo:

```css
.banner {
  width: 80vw;
}
```

---

## Comparación rápida

```text
50%  → relativo a un contexto determinado, frecuentemente el padre
2em  → relativo al font-size contextual
2rem → relativo al font-size de html
50vh → 50% del alto del viewport
50vw → 50% del ancho del viewport
```

---

# `calc()`

## 14. Función `calc()`

`calc()` permite realizar cálculos directamente en CSS.

Ejemplo:

```css
.content {
  width: calc(100% - 40px);
}
```

Esto permite combinar distintas unidades.

```css
.sidebar-layout {
  width: calc(100vw - 300px);
}
```

Puede utilizar operaciones aritméticas para construir layouts flexibles.

### Operaciones

`calc()` puede trabajar con:

```text
+
-
*
/
```

según la sintaxis y compatibilidad del tipo de valor utilizado.

Un caso muy frecuente es combinar porcentajes con longitudes:

```css
width: calc(100% - 2rem);
```

---

# Cuándo elegir cada unidad

## `px`

Útil para:

- bordes;
- detalles pequeños;
- dimensiones que necesitan control preciso.

```css
border: 1px solid black;
```

## `%`

Útil para:

- tamaños relacionados con el contenedor;
- layouts fluidos.

```css
width: 80%;
```

## `rem`

Útil para:

- tipografía;
- spacing consistente;
- escalas globales.

```css
padding: 1.5rem;
```

## `em`

Útil cuando una dimensión debería escalar junto al elemento.

```css
button {
  padding: 0.5em 1em;
}
```

## `vh` / `vw`

Útiles cuando la medida debe depender del viewport.

```css
.hero {
  min-height: 100vh;
}
```

---

## Resumen rápido

Los conceptos fundamentales de **CSS Relative and Absolute Units** son:

- Las unidades absolutas incluyen `px`, `in`, `cm`, `mm`, `q`, `pc` y `pt`.
- `1in` equivale a `96px`.
- `px` es la unidad absoluta más común en interfaces web.
- `%` expresa valores relativos a un contexto determinado.
- `em` depende del font size contextual.
- En `font-size`, `em` depende del tamaño heredado del padre.
- `rem` depende siempre del `font-size` del root `html`.
- `1vh` representa 1% de la altura del viewport.
- `1vw` representa 1% del ancho del viewport.
- Las unidades relativas permiten layouts y tipografías más flexibles.
- `calc()` permite combinar cálculos y distintas unidades dentro de CSS.
