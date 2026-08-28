# HTML Tables and Forms

Resumen del módulo **HTML Tables and Forms** del curso **Responsive Web Design v9** de freeCodeCamp.

## 1. Formularios HTML

Los formularios permiten recopilar datos ingresados por el usuario.

### `form`

El elemento `form` contiene los controles que forman parte del formulario.

```html
<form action="/submit" method="POST">
  <!-- form controls -->
</form>
```

### `action`

El atributo `action` indica la URL a la que se enviarán los datos.

```html
<form action="/register">
```

### `method`

El atributo `method` indica el método HTTP utilizado para enviar la información.

Los más comunes son:

- `GET`;
- `POST`.

```html
<form action="/search" method="GET">
```

De forma conceptual:

- **GET** suele utilizarse para solicitar o buscar información y normalmente representa los datos en la URL.
- **POST** suele utilizarse para enviar datos al servidor dentro de la petición.

---

## 2. Elemento `input`

`input` es uno de los controles más utilizados en formularios.

```html
<input type="text">
```

Es un **void element**, por lo que no posee etiqueta de cierre.

### `type`

Define el tipo de control.

Algunos valores habituales son:

```text
text
email
password
number
date
radio
checkbox
button
```

Ejemplos:

```html
<input type="text">
<input type="email">
<input type="password">
<input type="number">
```

### `name`

Asigna el nombre con el que el valor será identificado al enviar el formulario.

```html
<input type="text" name="username">
```

Conceptualmente, `name` actúa como la **clave** asociada al valor enviado.

En radio buttons, varios controles con el mismo `name` forman un único grupo:

```html
<input type="radio" name="plan" value="basic">
<input type="radio" name="plan" value="pro">
```

De ese grupo sólo puede seleccionarse una opción a la vez.

### `value`

Define el valor asociado al control.

```html
<input type="radio" name="plan" value="pro">
```

También puede utilizarse para definir el texto de un:

```html
<input type="button" value="Show Alert">
```

### `placeholder`

Muestra una pista temporal dentro del campo.

```html
<input
  type="text"
  placeholder="e.g. Quincy Larson"
>
```

El placeholder no reemplaza a un `label`: sólo debe utilizarse como ayuda complementaria.

### `size`

Indica aproximadamente cuántos caracteres deberían ser visibles dentro de ciertos inputs de texto.

```html
<input type="text" size="20">
```

No establece un límite a la cantidad de caracteres que pueden escribirse.

---

## 3. Restricciones y validación

HTML puede aplicar validaciones básicas antes de enviar un formulario.

### `required`

Indica que un campo debe completarse antes de enviar el formulario.

```html
<input type="email" required>
```

Es un atributo booleano.

### `min` y `max`

Definen valores mínimo y máximo permitidos en controles compatibles, como `number`.

```html
<input
  type="number"
  min="2"
  max="10"
>
```

### `minlength` y `maxlength`

Definen la cantidad mínima y máxima de caracteres.

```html
<input
  type="text"
  minlength="5"
  maxlength="30"
>
```

### Diferencia entre `size` y `maxlength`

```html
<input size="20" maxlength="30">
```

- `size="20"` afecta principalmente el tamaño visible del control.
- `maxlength="30"` limita realmente la cantidad de caracteres que puede introducir el usuario.

---

## 4. `disabled` y `readonly`

### `disabled`

Deshabilita el control.

```html
<input type="number" disabled>
```

Un control deshabilitado no puede ser utilizado normalmente por el usuario.

### `readonly`

Hace que el valor no pueda editarse.

```html
<input type="text" value="ABC123" readonly>
```

El control sigue siendo legible e interactuable de formas distintas a un control completamente deshabilitado.

Ambos son atributos booleanos.

---

## 5. Labels y asociación con inputs

### `label`

Proporciona una etiqueta textual a un control de formulario.

Una asociación correcta mejora:

- usabilidad;
- accesibilidad;
- interacción mediante mouse o touch;
- comprensión por screen readers.

Existen dos formas principales de asociación.

### Asociación explícita

El atributo `for` del `label` coincide con el `id` del input:

```html
<label for="email">Email Address:</label>
<input type="email" id="email" name="email">
```

Relación:

```text
for="email"  →  id="email"
```

### Asociación implícita

El input se coloca dentro del `label`:

```html
<label>
  Full Name:
  <input type="text" name="full-name">
</label>
```

En ambos casos el label queda asociado al control correspondiente.

---

## 6. Botones

### Elemento `button`

Crea un botón interactivo.

```html
<button type="button">Show Form</button>
```

El atributo `type` controla su comportamiento.

### `type="submit"`

Envía el formulario:

```html
<button type="submit">Submit Form</button>
```

### `type="reset"`

Restablece los controles a sus valores iniciales:

```html
<button type="reset">Reset Form</button>
```

### `type="button"`

Crea un botón sin comportamiento de envío predeterminado:

```html
<button type="button">Show Form</button>
```

Es útil cuando la acción será implementada mediante JavaScript.

---

## 7. Radio buttons

Los radio buttons representan opciones mutuamente excluyentes.

```html
<input
  id="yes"
  type="radio"
  name="answer"
  value="yes"
>
<label for="yes">Yes</label>

<input
  id="no"
  type="radio"
  name="answer"
  value="no"
>
<label for="no">No</label>
```

La propiedad clave es que ambos comparten:

```html
name="answer"
```

Esto hace que formen un mismo grupo.

---

## 8. Checkboxes

Los checkboxes permiten seleccionar opciones de forma independiente.

```html
<input
  type="checkbox"
  id="location"
  name="location"
  value="location"
>
<label for="location">Location</label>
```

A diferencia de los radio buttons, normalmente pueden seleccionarse varias opciones simultáneamente.

---

## 9. `fieldset` y `legend`

### `fieldset`

Agrupa controles relacionados dentro de un formulario.

### `legend`

Describe el propósito del grupo.

```html
<fieldset>
  <legend>Preferred contact method</legend>

  <input
    id="email-contact"
    type="radio"
    name="contact"
    value="email"
  >
  <label for="email-contact">Email</label>

  <input
    id="phone-contact"
    type="radio"
    name="contact"
    value="phone"
  >
  <label for="phone-contact">Phone</label>
</fieldset>
```

Esta estructura es especialmente útil para:

- grupos de radio buttons;
- grupos de checkboxes;
- conjuntos de campos relacionados.

También mejora la accesibilidad porque proporciona contexto sobre el conjunto de controles.

---

## 10. Estado de foco

Un control se encuentra en estado **focused** cuando recibe el foco del usuario.

Esto puede ocurrir al:

- hacer clic;
- tocar el elemento;
- navegar con el teclado, por ejemplo mediante `Tab`.

El foco es fundamental para la navegación por teclado y puede estilizarse con CSS mediante:

```css
input:focus {
  /* styles */
}
```

---

# Tablas HTML

## 11. Elemento `table`

`table` representa información tabular organizada en filas y columnas.

```html
<table>
  ...
</table>
```

Las tablas deben utilizarse para **datos tabulares**, no como herramienta de layout.

---

## 12. Filas y celdas

### `tr`

Representa una fila.

```html
<tr>
  ...
</tr>
```

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

Ejemplo:

```html
<table>
  <tr>
    <th>Name</th>
    <th>Score</th>
  </tr>
  <tr>
    <td>Alex</td>
    <td>92</td>
  </tr>
</table>
```

---

## 13. Estructura de una tabla

### `thead`

Agrupa las filas que forman el encabezado de la tabla.

### `tbody`

Agrupa el contenido principal.

### `tfoot`

Agrupa información de cierre, como:

- totales;
- promedios;
- resúmenes.

```html
<table>
  <thead>
    ...
  </thead>

  <tbody>
    ...
  </tbody>

  <tfoot>
    ...
  </tfoot>
</table>
```

Estas agrupaciones aportan estructura semántica al documento.

---

## 14. `caption`

Proporciona un título o descripción breve para la tabla.

```html
<table>
  <caption>Exam Grades</caption>
  ...
</table>
```

Debe colocarse inmediatamente después de la etiqueta de apertura de `table`.

Es útil tanto visualmente como para tecnologías de asistencia.

---

## 15. `colspan`

Permite que una celda abarque varias columnas.

```html
<td colspan="2">Average Grade</td>
```

Si el valor es `2`, la celda ocupa el espacio de dos columnas.

Ejemplo:

```html
<tfoot>
  <tr>
    <td colspan="2">Average Grade</td>
    <td>78</td>
  </tr>
</tfoot>
```

---

## 16. Ejemplo completo de tabla

```html
<table>
  <caption>Exam Grades</caption>

  <thead>
    <tr>
      <th>Last Name</th>
      <th>First Name</th>
      <th>Grade</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>Davis</td>
      <td>Alex</td>
      <td>54</td>
    </tr>

    <tr>
      <td>Doe</td>
      <td>Samantha</td>
      <td>92</td>
    </tr>
  </tbody>

  <tfoot>
    <tr>
      <td colspan="2">Average Grade</td>
      <td>73</td>
    </tr>
  </tfoot>
</table>
```

---

# Herramientas para trabajar con HTML

## 17. HTML Validator

Un **HTML validator** analiza el código para detectar errores de sintaxis o estructuras inválidas.

Puede ayudar a encontrar:

- etiquetas mal cerradas;
- atributos inválidos;
- errores de anidamiento;
- markup no conforme con HTML.

---

## 18. DOM Inspector

El **DOM Inspector** permite inspeccionar la representación de la página construida por el navegador.

Sirve para:

- explorar elementos;
- inspeccionar atributos;
- modificar temporalmente el DOM;
- probar cambios sin editar el archivo original.

---

## 19. DevTools

Las **browser DevTools** reúnen diferentes herramientas para desarrollo web.

Permiten, entre otras cosas:

- inspeccionar HTML y CSS;
- depurar JavaScript;
- revisar requests de red;
- analizar rendimiento;
- modificar temporalmente elementos y estilos;
- investigar errores.

---

## Resumen rápido

Los conceptos fundamentales de **HTML Tables and Forms** son:

- `form` agrupa los controles y utiliza `action` y `method` para definir el envío.
- `input` admite distintos tipos y atributos para capturar y restringir datos.
- `name` identifica el dato enviado; `value` representa su valor.
- `required`, `min`, `max`, `minlength` y `maxlength` proporcionan validación básica.
- Todo control debería tener un `label` correctamente asociado.
- `fieldset` y `legend` agrupan y describen controles relacionados.
- Los radio buttons comparten `name` cuando pertenecen al mismo grupo.
- Los checkboxes permiten elecciones independientes.
- `table`, `tr`, `th` y `td` forman la estructura básica de una tabla.
- `thead`, `tbody` y `tfoot` separan grupos de filas semánticamente.
- `caption` describe la tabla y `colspan` permite que una celda abarque varias columnas.
- Validators, DOM Inspector y DevTools son herramientas fundamentales para revisar y depurar HTML.
