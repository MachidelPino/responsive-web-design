# CSS Backgrounds and Borders

Resumen del módulo **CSS Backgrounds and Borders** del curso **Responsive Web Design v9** de freeCodeCamp.

## 1. Estilizar listas

### `line-height`

`line-height` controla la altura de línea y, por lo tanto, el espacio vertical entre líneas de texto.

Acepta valores como:

- `normal`;
- números;
- porcentajes;
- unidades como `em`.

```css
p {
  line-height: 1.5;
}
```

También puede utilizarse para mejorar la legibilidad de listas.

### `list-style-type`

Define el tipo de marcador de una lista.

Valores comunes:

```text
disc
circle
square
decimal
```

Ejemplo:

```css
ul {
  list-style-type: square;
}
```

### `list-style-position`

Controla si el marcador se ubica dentro o fuera de la caja principal del `li`.

Valores:

```text
inside
outside
```

```css
ul {
  list-style-position: inside;
}
```

### `list-style-image`

Permite utilizar una imagen como marcador.

```css
ul {
  list-style-image: url("marker.png");
}
```

### Espaciado con `margin`

Además de `line-height`, puede utilizarse `margin` para separar items.

```css
li {
  margin-bottom: 1rem;
}
```

---

## 2. Estilizar enlaces

Las **pseudo-classes** permiten seleccionar elementos según su estado.

### `:link`

Selecciona enlaces aún no visitados.

```css
a:link {
  color: blue;
}
```

### `:visited`

Selecciona enlaces ya visitados.

```css
a:visited {
  color: purple;
}
```

### `:hover`

Se activa cuando el puntero está sobre el elemento.

```css
a:hover {
  text-decoration: underline;
}
```

### `:focus`

Se aplica cuando el elemento recibe foco, por ejemplo mediante teclado.

```css
a:focus {
  outline: 2px solid orange;
}
```

El foco visible es importante para accesibilidad.

### `:active`

Se aplica mientras el elemento está siendo activado.

```css
a:active {
  color: red;
}
```

---

# Fondos

## 3. `background-image`

Define una o más imágenes de fondo.

```css
.hero {
  background-image: url("image.jpg");
}
```

También puede recibir gradientes:

```css
.hero {
  background-image: linear-gradient(to right, red, blue);
}
```

---

## 4. `background-size`

Controla el tamaño de la imagen de fondo.

### `cover`

Escala la imagen hasta cubrir completamente el elemento.

```css
.hero {
  background-size: cover;
}
```

Puede recortar partes de la imagen si las proporciones no coinciden.

### `contain`

Escala la imagen para que entre completa dentro del elemento.

```css
.hero {
  background-size: contain;
}
```

Puede dejar espacio libre.

---

## 5. `background-repeat`

Controla la repetición de la imagen.

El valor por defecto es:

```css
background-repeat: repeat;
```

Para evitarla:

```css
background-repeat: no-repeat;
```

---

## 6. `background-position`

Controla la posición inicial del fondo.

Puede utilizar:

- keywords;
- porcentajes;
- longitudes.

```css
.hero {
  background-position: center top;
}
```

Keywords frecuentes:

```text
top
bottom
left
right
center
```

---

## 7. `background-attachment`

Controla si el fondo se desplaza junto con el contenido.

### `scroll`

Valor predeterminado.

```css
background-attachment: scroll;
```

### `fixed`

Mantiene el fondo fijo respecto al viewport.

```css
background-attachment: fixed;
```

---

## 8. Shorthand `background`

`background` permite configurar varias propiedades en una sola declaración.

```css
.hero {
  background: center top / cover no-repeat url("image.jpg");
}
```

También puede utilizarse de forma más simple:

```css
body {
  background: no-repeat url("image.jpg");
}
```

---

## 9. Contraste de foreground y background

El color del texto y el fondo deben mantener suficiente contraste para conservar la legibilidad.

WCAG recomienda, como referencia general:

- **4.5:1** para texto normal;
- **3:1** para texto grande.

Un diseño visualmente atractivo no debería sacrificar legibilidad.

---

# Bordes

## 10. Propiedades por lado

CSS permite definir cada lado de forma independiente.

```css
.box {
  border-top: 3px solid blue;
  border-right: 2px solid red;
  border-bottom: 1px dashed green;
  border-left: 4px dotted orange;
}
```

Cada declaración combina normalmente:

```text
width + style + color
```

---

## 11. Shorthand `border`

Permite definir ancho, estilo y color en una sola propiedad.

```css
.box {
  border: 1px solid black;
}
```

---

## 12. `border-style`

Define el estilo visual del borde.

Valores comunes:

```text
solid
dashed
dotted
double
```

```css
.box {
  border-style: dashed;
}
```

---

## 13. `border-radius`

Redondea las esquinas.

```css
.card {
  border-radius: 12px;
}
```

También puede utilizarse para crear formas circulares cuando las dimensiones lo permiten:

```css
.avatar {
  border-radius: 50%;
}
```

---

# Gradientes

## 14. `linear-gradient()`

Crea una transición de colores a lo largo de una línea.

```css
.banner {
  background: linear-gradient(to right, red, blue);
}
```

Puede definirse dirección mediante keywords o ángulos.

```css
.banner {
  background: linear-gradient(45deg, red, blue);
}
```

Puede incluir múltiples color stops.

```css
.banner {
  background: linear-gradient(to right, red, yellow, green);
}
```

---

## 15. `radial-gradient()`

Crea un gradiente que se expande desde un punto central.

```css
.circle {
  background: radial-gradient(circle, red, blue);
}
```

Puede tener forma circular o elíptica.

---

## Resumen rápido

Los conceptos centrales de **CSS Backgrounds and Borders** son:

- `line-height` y `margin` ayudan a controlar el espaciado y legibilidad.
- `list-style-type`, `list-style-position` y `list-style-image` permiten personalizar listas.
- `:link`, `:visited`, `:hover`, `:focus` y `:active` representan estados de enlaces.
- `background-image` define imágenes o gradientes de fondo.
- `background-size: cover` cubre el contenedor; `contain` muestra toda la imagen.
- `background-repeat`, `background-position` y `background-attachment` controlan el comportamiento del fondo.
- `background` es la shorthand de las propiedades de fondo.
- Debe mantenerse buen contraste entre foreground y background.
- `border` permite definir ancho, estilo y color.
- Los bordes pueden configurarse por lado.
- `border-radius` redondea esquinas.
- `linear-gradient()` y `radial-gradient()` crean transiciones de color.
