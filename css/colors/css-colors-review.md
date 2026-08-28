# CSS Colors

Resumen del módulo **CSS Colors** del curso **Responsive Web Design v9** de freeCodeCamp.

# Teoría del color

## 1. Color Theory

La **color theory** estudia:

- cómo interactúan los colores;
- cómo se relacionan;
- cómo producen armonía;
- cómo afectan la percepción.

Es útil para construir interfaces visualmente coherentes y comunicar distintas sensaciones.

---

## 2. Primary Colors

En el modelo tradicional presentado en el review, los colores primarios son:

- red;
- yellow;
- blue.

Se consideran colores base a partir de los cuales se derivan otros mediante mezcla.

---

## 3. Secondary Colors

Se obtienen al combinar dos colores primarios.

Ejemplos:

- green;
- orange;
- purple.

---

## 4. Tertiary Colors

Se obtienen combinando un color primario con un color secundario adyacente.

Ejemplos:

- yellow-green;
- blue-green;
- blue-violet.

---

## 5. Warm Colors

Incluyen principalmente:

- reds;
- oranges;
- yellows.

Suelen asociarse con:

- energía;
- calor;
- comodidad.

---

## 6. Cool Colors

Incluyen principalmente:

- blues;
- greens;
- purples.

Suelen asociarse con:

- calma;
- serenidad;
- profesionalismo.

---

## 7. Color Wheel

La **color wheel** representa visualmente las relaciones entre colores.

Permite construir esquemas de color de forma sistemática.

---

# Esquemas de color

## 8. Analogous

Utiliza colores adyacentes en la color wheel.

Tiende a producir una sensación:

- cohesionada;
- armónica;
- suave.

---

## 9. Complementary

Utiliza colores opuestos en la rueda.

Produce:

- alto contraste;
- impacto visual;
- fuerte diferenciación.

Debe utilizarse con cuidado cuando ambos colores compiten por protagonismo.

---

## 10. Triadic

Utiliza tres colores aproximadamente equidistantes en la rueda.

Formarían aproximadamente un triángulo equilátero.

Tiende a producir combinaciones:

- vibrantes;
- variadas;
- equilibradas.

---

## 11. Monochromatic

Parte de un único color base y modifica:

- lightness;
- darkness;
- saturation.

Produce una identidad visual coherente y puede generar contraste sin abandonar una misma familia cromática.

---

# Colores en CSS

## 12. Named Colors

CSS incluye nombres predefinidos.

```css
.title {
  color: blue;
}
```

Ejemplos:

```text
red
blue
darkred
lightgreen
rebeccapurple
```

Son cómodos, aunque ofrecen menos control que otros modelos.

---

## 13. `rgb()`

RGB significa:

```text
Red
Green
Blue
```

Cada canal controla la intensidad de uno de esos componentes.

Ejemplo:

```css
p {
  color: rgb(255, 0, 0);
}
```

Representa rojo.

Valores clásicos:

```text
0 → sin intensidad
255 → máxima intensidad
```

Ejemplos:

```css
rgb(255, 0, 0)   /* red */
rgb(0, 255, 0)   /* green */
rgb(0, 0, 255)   /* blue */
rgb(0, 0, 0)     /* black */
rgb(255,255,255) /* white */
```

---

## 14. Alpha y `rgba()`

El canal **alpha** controla transparencia.

```css
div {
  background-color: rgba(0, 0, 255, 0.5);
}
```

Valores habituales:

```text
0   → completamente transparente
1   → completamente opaco
0.5 → 50% de opacidad
```

La sintaxis moderna de CSS permite incluir alpha directamente en funciones de color modernas, por lo que `rgba()` puede verse también como una variante histórica de `rgb()` con alpha explícito.

---

# HSL

## 15. `hsl()`

HSL representa un color mediante:

```text
Hue
Saturation
Lightness
```

### Hue

Representa la posición del color alrededor de la rueda.

Se expresa normalmente en grados.

```text
0deg   → red
120deg → green
240deg → blue
```

### Saturation

Representa la intensidad del color.

```text
0%   → sin saturación
100% → saturación máxima
```

### Lightness

Controla luminosidad.

```text
0%   → black
50%  → color normal
100% → white
```

Ejemplo:

```css
p {
  color: hsl(120 100% 50%);
}
```

---

## 16. Alpha en `hsl()`

La sintaxis moderna utiliza `/`.

```css
p {
  color: hsl(120 100% 50% / 0.8);
}
```

---

## 17. `hsla()`

`hsla()` es una forma legacy de expresar HSL con alpha.

```css
div {
  background-color: hsla(0, 100%, 50%, 0.5);
}
```

En CSS moderno suele preferirse:

```css
hsl(0 100% 50% / 0.5)
```

---

# Hexadecimal

## 18. Hex Colors

Los colores hexadecimales representan valores RGB utilizando base 16.

Caracteres disponibles:

```text
0 1 2 3 4 5 6 7 8 9 A B C D E F
```

Formato:

```text
#RRGGBB
```

Ejemplo:

```css
color: #FF5733;
```

Cada par representa:

```text
RR → red
GG → green
BB → blue
```

---

## 19. Shorthand hexadecimal

Cuando cada par repite el mismo carácter:

```text
#22FFBB
```

puede reducirse a:

```text
#2FB
```

Ejemplo:

```css
color: #FFF;
```

equivale a:

```css
color: #FFFFFF;
```

---

# `box-shadow`

## 20. Concepto

`box-shadow` agrega una o varias sombras a la caja de un elemento.

Sintaxis general:

```css
box-shadow: offset-x offset-y blur-radius spread-radius color;
```

Ejemplo:

```css
.card {
  box-shadow: 10px 10px 20px rgba(0, 0, 0, 0.5);
}
```

---

## 21. Offset X

Controla desplazamiento horizontal.

```text
positivo → derecha
negativo → izquierda
```

---

## 22. Offset Y

Controla desplazamiento vertical.

```text
positivo → abajo
negativo → arriba
```

---

## 23. Blur Radius

Controla qué tan difusa es la sombra.

```css
box-shadow: 0 4px 20px black;
```

Mayor blur:

```text
bordes más suaves
```

Si se omite:

```text
0
```

---

## 24. Spread Radius

Controla cuánto se expande o contrae la sombra.

```css
box-shadow: 0 0 10px 5px black;
```

Puede ser positivo o negativo.

---

## 25. Color

Puede utilizar cualquier sintaxis CSS válida:

```css
black
#000
rgb(0, 0, 0)
rgba(0, 0, 0, 0.5)
hsl(0 0% 0% / 0.5)
```

---

## 26. `inset`

Convierte la sombra exterior en interior.

```css
box {
  box-shadow: inset 0 0 10px black;
}
```

---

## 27. Múltiples sombras

Se separan con comas.

```css
.card {
  box-shadow:
    0 2px 4px rgba(0, 0, 0, 0.2),
    0 8px 24px rgba(0, 0, 0, 0.15);
}
```

Se dibujan en capas.

---

# Gradientes

## 28. `linear-gradient()`

Crea una transición de colores sobre una línea.

```css
.banner {
  background: linear-gradient(to right, red, blue);
}
```

Puede definirse dirección:

```css
background: linear-gradient(to bottom right, red, blue);
```

O ángulo:

```css
background: linear-gradient(45deg, red, blue);
```

Puede contener múltiples color stops:

```css
background:
  linear-gradient(45deg, red, yellow, green, blue);
```

---

## 29. `radial-gradient()`

Crea una transición que se expande desde un punto.

```css
.circle {
  background: radial-gradient(circle, red, blue);
}
```

Puede ser:

- circular;
- elliptical.

---

# Elección de modelo de color

## Named colors

Ventajas:

- lectura rápida;
- comodidad.

Desventaja:

- control limitado.

## Hex

Ventajas:

- compacto;
- muy común.

## RGB

Ventajas:

- relación directa con canales de luz;
- sencillo para manipulación programática.

## HSL

Ventajas:

- suele resultar más intuitivo para modificar tono, saturación o luminosidad.

Ejemplo:

```css
--primary: hsl(220 80% 50%);
--primary-light: hsl(220 80% 70%);
--primary-dark: hsl(220 80% 30%);
```

---

## Resumen rápido

Los conceptos fundamentales de **CSS Colors** son:

- La color theory estudia relaciones y efectos perceptivos de los colores.
- Primary, secondary y tertiary colors describen familias de mezcla.
- Warm colors y cool colors generan asociaciones visuales diferentes.
- Analogous, complementary, triadic y monochromatic son esquemas de color frecuentes.
- CSS permite usar named colors, RGB, HSL y hexadecimal.
- `rgb()` combina canales red, green y blue.
- Alpha controla transparencia.
- `hsl()` utiliza hue, saturation y lightness.
- La sintaxis moderna de `hsl()` admite alpha mediante `/`.
- `hsla()` es una sintaxis legacy.
- Hex utiliza base 16 y puede usar shorthand de tres caracteres.
- `box-shadow` combina offsets, blur, spread y color.
- `inset` crea sombras interiores.
- Pueden combinarse varias sombras.
- `linear-gradient()` crea gradientes lineales.
- `radial-gradient()` crea gradientes radiales.
