# Design Fundamentals

Resumen del módulo **Design Fundamentals** del curso **Responsive Web Design v9** de freeCodeCamp.

## 1. Terminología básica de diseño

### Layout

El **layout** es la forma en la que se organizan los elementos visuales dentro de una página o pantalla.

Incluye la distribución de:

- texto;
- imágenes;
- controles;
- espacios vacíos.

Un buen layout facilita comprender la información.

### Alignment

El **alignment** describe cómo se posicionan los elementos en relación con otros.

Una alineación consistente ayuda a que el diseño se perciba:

- ordenado;
- limpio;
- coherente.

### Composition

La **composition** es la organización global de los elementos para formar un diseño armónico.

Define cómo se relacionan:

- texto;
- imágenes;
- formas;
- espacios.

### Balance

El **balance** representa cómo se distribuye el peso visual.

Puede ser:

- **simétrico**;
- **asimétrico**.

El objetivo es evitar que una zona del diseño domine de forma no intencional.

### Scale

La **scale** compara el tamaño de un elemento con otro.

Puede utilizarse para:

- destacar contenido;
- establecer jerarquía;
- separar niveles de importancia.

### Hierarchy

La **visual hierarchy** determina qué elementos deberían llamar la atención primero.

Puede construirse mediante:

- tamaño;
- color;
- contraste;
- posición;
- peso tipográfico;
- espacio.

Una buena jerarquía guía al usuario a través del contenido.

### Contrast

El **contrast** crea diferencias visuales claras.

Puede lograrse mediante cambios en:

- color;
- tamaño;
- forma;
- textura;
- peso.

Además de crear énfasis, mejora la legibilidad.

### White Space

El **white space** o **negative space** es el espacio vacío alrededor y entre elementos.

No es espacio desperdiciado.

Sirve para:

- separar grupos;
- reducir ruido visual;
- mejorar legibilidad;
- aumentar jerarquía.

---

## 2. UI y UX

### UI

**UI (User Interface)** comprende los elementos visuales e interactivos con los que el usuario interactúa.

Ejemplos:

- botones;
- links;
- menus;
- icons;
- inputs;
- imágenes;
- texto.

### UX

**UX (User Experience)** se refiere a la experiencia general del usuario al utilizar un producto.

Una buena UX tiende a ser:

- intuitiva;
- eficiente;
- accesible;
- consistente;
- agradable.

UI y UX están relacionadas, pero no son equivalentes:

```text
UI → cómo se presenta e interactúa la interfaz
UX → cómo se siente y funciona la experiencia completa
```

---

## 3. Design Brief

Un **design brief** documenta:

- objetivos;
- requisitos;
- alcance;
- restricciones;
- necesidades del cliente o proyecto.

Funciona como una guía para mantener el diseño alineado con el problema real.

---

## 4. Vector-based Design

El diseño vectorial representa gráficos mediante fórmulas matemáticas.

Ventajas:

- escalado sin pérdida de calidad;
- buena adaptación a distintos tamaños;
- utilidad para logos, iconos e ilustraciones.

---

## 5. Prototyping

El **prototyping** consiste en crear un modelo de una interfaz o producto antes de construir la versión final.

Puede servir para:

- validar flujos;
- detectar problemas;
- probar ideas;
- obtener feedback temprano.

---

# Fundamentos de UI

## 6. Contraste accesible

El contraste entre foreground y background debe permitir leer el contenido con claridad.

WCAG recomienda como referencia:

- **4.5:1** para texto normal;
- **3:1** para texto grande.

---

## 7. Jerarquía visual

Una buena jerarquía define un recorrido claro para la vista.

El usuario debería poder distinguir rápidamente:

1. qué es más importante;
2. qué contenido es secundario;
3. qué acciones puede realizar.

---

## 8. Responsive Images

Las **responsive images** se adaptan al tamaño disponible.

El objetivo es que funcionen correctamente en:

- desktops;
- tablets;
- teléfonos.

Una imagen no debería romper el layout ni desbordarse en pantallas pequeñas.

Una regla habitual es:

```css
img {
  max-width: 100%;
  height: auto;
}
```

---

## 9. Progressive Enhancement

**Progressive enhancement** consiste en diseñar primero una base funcional accesible para todos y luego agregar mejoras para navegadores o dispositivos con más capacidades.

Idea general:

```text
contenido y función esencial
        ↓
mejoras visuales
        ↓
interacciones avanzadas
```

La funcionalidad esencial no debería depender de una característica opcional.

---

# Diseño centrado en el usuario

## 10. User-centered Design

El **user-centered design** coloca las necesidades del usuario en el centro del proceso.

Considera:

- objetivos;
- limitaciones;
- preferencias;
- contexto;
- accesibilidad.

El diseño no debería partir únicamente de lo que el equipo quiere construir.

---

## 11. User Research

El **user research** estudia sistemáticamente a las personas que utilizan el producto.

Busca comprender:

- necesidades;
- comportamientos;
- problemas;
- motivaciones.

La investigación reduce decisiones basadas únicamente en intuición.

---

## 12. Exit Interviews

Son encuestas o entrevistas realizadas cuando un usuario abandona o cancela un producto.

Sirven para detectar:

- motivos de abandono;
- fricciones;
- expectativas incumplidas;
- oportunidades de mejora.

---

## 13. User Testing

Consiste en observar o registrar cómo usuarios reales interactúan con la interfaz.

Permite detectar problemas que pueden no ser evidentes para el equipo que diseñó el producto.

---

## 14. A/B Testing

Compara dos variantes de una experiencia.

Ejemplo:

```text
Grupo A → diseño actual
Grupo B → nueva variante
```

Luego se comparan métricas para evaluar cuál funciona mejor.

---

## 15. User Requirements

Los **user requirements** describen qué necesita poder hacer el usuario o qué condiciones debe cumplir el producto.

Pueden surgir de:

- research;
- stakeholders;
- requisitos de negocio;
- estándares;
- restricciones técnicas.

---

# Patrones de UI

## 16. Progressive Disclosure

Muestra sólo la información relevante para la tarea actual y oculta detalles secundarios hasta que sean necesarios.

Objetivo:

- reducir cognitive load;
- simplificar decisiones;
- evitar interfaces sobrecargadas.

---

## 17. Deferred / Lazy Registration

Permite que el usuario explore o interactúe con el producto antes de obligarlo a registrarse.

Puede reducir fricción inicial.

---

# Buenas prácticas de diseño

## 18. Dark Mode

Un modo oscuro reemplaza una interfaz clara por una paleta predominantemente oscura.

Conviene evitar colores demasiado saturados porque pueden generar fatiga visual sobre fondos oscuros.

Los colores desaturados suelen producir mejores resultados.

---

## 19. Breadcrumbs

Los **breadcrumbs** indican la posición del usuario dentro de una jerarquía.

Ejemplo:

```text
Home > Products > Laptops > Model X
```

Buenas prácticas:

- colocarlos cerca de la parte superior;
- hacerlos legibles;
- no darles más protagonismo que al contenido principal.

---

## 20. Cards

Una **card** agrupa información relacionada dentro de un bloque visual.

Buenas prácticas:

- evitar exceso de información;
- mantener jerarquía clara;
- utilizar imágenes de calidad;
- evitar clutter visual.

---

## 21. Infinite Scroll

Carga nuevo contenido automáticamente a medida que el usuario se desplaza.

Ventaja:

- flujo continuo.

Problemas posibles:

- dificultad para volver a una posición anterior;
- pérdida de orientación;
- menos control.

Una alternativa es:

```text
Load more
```

que da al usuario mayor control.

---

## 22. Modal Dialog

Un **modal** aparece sobre el contenido existente.

Normalmente:

- bloquea temporalmente interacción con el fondo;
- utiliza un overlay;
- concentra atención en una tarea.

Cuando sea posible, utilizar el elemento HTML:

```html
<dialog>
```

aporta comportamiento y beneficios de accesibilidad nativos.

El usuario debe tener una forma clara de cerrarlo.

---

## 23. Indicadores de progreso

En procesos de varios pasos conviene indicar el progreso.

Ejemplos:

```text
Step 2 of 4
```

o una barra de progreso.

Deben:

- ser visibles;
- ser fáciles de entender;
- permitir volver a pasos anteriores cuando corresponda.

---

## 24. Shopping Cart

En e-commerce, el carrito debería:

- ser fácil de encontrar;
- usar iconografía reconocible;
- mostrar claramente los productos seleccionados;
- ofrecer un CTA claro hacia checkout.

---

# Herramientas de diseño

## 25. Figma

Herramienta cloud orientada a UI/UX.

Permite:

- vector design;
- prototipos;
- colaboración;
- comentarios;
- layouts automáticos.

## 26. Sketch

Herramienta popular para:

- interfaces;
- prototipos;
- iconos;
- layouts.

## 27. Adobe XD

Herramienta vectorial de diseño y prototipado, históricamente integrada con otras herramientas Adobe.

## 28. Canva

Herramienta orientada a creación visual rápida.

Puede utilizarse para:

- presentaciones;
- posters;
- imágenes;
- videos cortos;
- piezas gráficas.

---

## Resumen rápido

Los conceptos centrales de **Design Fundamentals** son:

- Layout organiza los elementos de una interfaz.
- Alignment, composition, balance y scale construyen orden visual.
- Hierarchy define qué debe llamar la atención primero.
- Contrast mejora diferenciación y legibilidad.
- White space reduce ruido y mejora claridad.
- UI representa la interfaz; UX representa la experiencia completa.
- Un design brief guía objetivos y requisitos.
- Prototyping permite validar ideas antes de implementar.
- Progressive enhancement preserva la funcionalidad esencial.
- User-centered design parte de necesidades reales de usuarios.
- User research, user testing y A/B testing aportan evidencia.
- Progressive disclosure reduce carga cognitiva.
- Lazy registration reduce fricción inicial.
- Dark mode, breadcrumbs, cards, modals, progress indicators e infinite scroll requieren decisiones cuidadas de UX.
