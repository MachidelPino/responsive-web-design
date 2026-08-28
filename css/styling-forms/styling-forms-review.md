# Styling Forms

Resumen del módulo **Styling Forms** del curso **Responsive Web Design v9** de freeCodeCamp.

## 1. Estilizar inputs sin perder accesibilidad

Los elementos de formulario pueden personalizarse con CSS igual que otros elementos de la página, pero deben conservar señales visuales claras para que sigan siendo fáciles de usar.

Al estilizar inputs hay que prestar atención especialmente a:

- tamaño del texto;
- contraste;
- estado de foco;
- estados de error;
- consistencia entre navegadores.

## 2. Tamaño de fuente

El texto dentro de un input debe ser suficientemente grande para poder leerse con comodidad.

```css
input {
  font-size: 1rem;
}
```

Un tamaño demasiado pequeño puede dificultar el uso del formulario, especialmente en dispositivos móviles o para personas con dificultades visuales.

## 3. Contraste

El texto debe mantener suficiente contraste con el fondo.

```css
input {
  color: #111;
  background-color: #fff;
}
```

También deben distinguirse correctamente bordes, placeholders, mensajes de error y estados disabled.

# Foco

## 4. Los inputs pueden recibir foco

Los controles de formulario pueden recibir foco mediante teclado, mouse, touch o JavaScript. Al navegar con `Tab`, por ejemplo, un input puede recibir foco.

El usuario necesita saber claramente qué control está activo.

## 5. Indicador visible de foco

No conviene eliminar el indicador de foco sin reemplazarlo por otro igualmente visible.

```css
input:focus {
  outline: 3px solid blue;
}
```

También puede utilizarse un borde:

```css
input:focus {
  border: 3px solid blue;
}
```

Una mala práctica sería:

```css
input:focus {
  outline: none;
}
```

si no se agrega ningún indicador alternativo.

# `appearance`

## 6. Estilos nativos del navegador

Los navegadores aplican estilos predeterminados a muchos controles, especialmente:

- checkboxes;
- radio buttons;
- selects;
- date pickers;
- color pickers.

Estos estilos pueden variar según navegador, sistema operativo y dispositivo.

## 7. `appearance: none`

La propiedad:

```css
appearance: none;
```

elimina gran parte de la apariencia nativa del navegador.

```css
input[type="checkbox"] {
  appearance: none;
}
```

Esto permite tener mayor control sobre el aspecto del elemento.

## 8. Ventaja de `appearance: none`

Permite crear controles personalizados.

```css
input[type="checkbox"] {
  appearance: none;
  width: 1.2rem;
  height: 1.2rem;
  border: 2px solid black;
}
```

Después se puede definir un estado marcado:

```css
input[type="checkbox"]:checked {
  background-color: navy;
}
```

## 9. Riesgo de `appearance: none`

Al eliminar la apariencia nativa también pueden desaparecer señales que el navegador proporcionaba automáticamente.

Por eso, al crear un control personalizado hay que reconstruir correctamente estados como:

- foco;
- checked;
- disabled;
- error;
- validación.

```css
input[type="checkbox"]:focus {
  outline: 3px solid orange;
}
```

# Inputs especiales

## 10. `datetime-local`

El input:

```html
<input type="datetime-local">
```

utiliza controles complejos proporcionados por el navegador.

Puede incluir selector de fecha, selector de hora, iconos internos y distintas partes interactivas.

Gran parte de su apariencia depende del navegador y del sistema operativo.

## 11. `color`

El input:

```html
<input type="color">
```

también suele utilizar una interfaz nativa compleja. Al activarse puede abrir un color picker proporcionado por el navegador o el sistema operativo.

## 12. Pseudo-elements internos

Inputs como `datetime-local` y `color` pueden apoyarse internamente en pseudo-elements específicos del navegador.

Eso dificulta conseguir exactamente el mismo diseño en todos los navegadores.

Una regla que funcione en un navegador puede:

- no funcionar en otro;
- utilizar un pseudo-element distinto;
- producir un resultado visual diferente.

# Compatibilidad entre navegadores

## 13. Browser-dependent styling

El aspecto de algunos controles HTML depende mucho del navegador.

Por ejemplo, un mismo:

```html
<input type="datetime-local">
```

puede verse diferente en Chrome, Firefox, Safari o Edge.

Por eso no siempre es conveniente intentar controlar hasta el último detalle visual de los controles nativos.

## 14. Priorizar funcionalidad y accesibilidad

Una estrategia razonable consiste en conservar primero un control funcional y accesible, y después agregar mejoras visuales.

La funcionalidad principal debería seguir disponible aunque alguna personalización específica no se aplique.

# Buenas prácticas

## 15. Priorizar usabilidad sobre personalización

Antes de personalizar un control conviene comprobar que siga siendo:

- legible;
- reconocible;
- focusable;
- utilizable con teclado;
- comprensible en estados de error;
- funcional en distintos navegadores.

## 16. No eliminar señales importantes

Evitar eliminar sin reemplazo:

- focus indicators;
- checked indicators;
- error states;
- disabled states.

Si el navegador proporcionaba una señal visual y se elimina mediante CSS, esa señal debe recrearse.

## 17. Probar formularios en distintos navegadores

Conviene probar especialmente:

- `datetime-local`;
- `color`;
- checkboxes personalizados;
- radio buttons personalizados;
- selects;
- estados `:focus`;
- validación.

# Ejemplo conceptual

```css
input {
  font: inherit;
  color: #111;
  background-color: #fff;
  border: 1px solid #777;
  border-radius: 0.25rem;
  padding: 0.5rem;
}

input:focus {
  outline: 3px solid #2463eb;
  outline-offset: 2px;
}

input:invalid {
  border-color: #b00020;
}
```

La prioridad es que el diseño personalizado no elimine información visual necesaria para utilizar el formulario.

## Resumen rápido

Los conceptos fundamentales de **Styling Forms** son:

- Los inputs deben mantener texto suficientemente grande y buen contraste.
- Los controles de formulario necesitan un indicador de foco claramente visible.
- No debe eliminarse `outline` sin proporcionar una alternativa equivalente.
- Los navegadores aplican estilos nativos a muchos controles.
- `appearance: none` elimina gran parte de esa apariencia y permite mayor personalización.
- Al utilizar `appearance: none` hay que recrear correctamente estados como foco, selección y error.
- Inputs como `datetime-local` y `color` utilizan interfaces y pseudo-elements complejos.
- Su apariencia puede cambiar considerablemente entre navegadores.
- No siempre es posible conseguir una apariencia idéntica en todos los browsers.
- La funcionalidad y accesibilidad deben tener prioridad sobre la personalización visual.
