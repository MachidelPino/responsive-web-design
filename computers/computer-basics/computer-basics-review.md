# Computer Basics

Resumen del módulo **Computer Basics** del curso **Responsive Web Design v9** de freeCodeCamp.

## 1. Componentes principales de una computadora

### Motherboard

La **motherboard** o placa madre es la placa principal del sistema.

Conecta y permite la comunicación entre componentes como:

- CPU;
- memoria RAM;
- almacenamiento;
- GPU;
- dispositivos y conectores.

Funciona como la base física sobre la que se integran los componentes principales de la computadora.

### CPU

La **CPU (Central Processing Unit)** es el procesador encargado de ejecutar instrucciones y realizar cálculos.

Puede pensarse como el componente que procesa gran parte de las operaciones necesarias para ejecutar programas.

### RAM

La **RAM (Random Access Memory)** es una memoria temporal utilizada mientras la computadora está funcionando.

Características principales:

- permite acceso rápido a datos en uso;
- almacena temporalmente información que necesita la CPU;
- su contenido se pierde cuando se apaga la computadora.

No debe confundirse con el almacenamiento permanente.

### HDD

Un **HDD (Hard Disk Drive)** es un dispositivo de almacenamiento permanente.

Conserva los datos incluso cuando la computadora está apagada.

Se utiliza para almacenar:

- sistema operativo;
- programas;
- documentos;
- imágenes;
- otros archivos.

### SSD

Un **SSD (Solid State Drive)** también proporciona almacenamiento permanente, pero utiliza memoria flash en lugar de componentes mecánicos.

En comparación con un HDD, normalmente ofrece:

- mayor velocidad;
- menor latencia;
- ausencia de partes móviles.

### PSU

La **PSU (Power Supply Unit)** convierte la electricidad proveniente de la red eléctrica en la energía que necesitan los componentes de la computadora.

### GPU

La **GPU (Graphics Processing Unit)** está especializada en procesar y renderizar gráficos.

Se utiliza para tareas como:

- representar la interfaz gráfica;
- renderizar imágenes y video;
- videojuegos;
- cargas de trabajo paralelas especializadas.

---

## 2. Acceso a Internet

### ISP

Un **ISP (Internet Service Provider)** es una empresa que proporciona acceso a Internet.

Algunos tipos de conexión mencionados en el curso son:

- dial-up;
- DSL;
- cable;
- fiber-optic;
- satellite.

Las tecnologías difieren principalmente en:

- velocidad;
- latencia;
- disponibilidad;
- infraestructura utilizada.

---

## 3. Seguridad al iniciar sesión

Algunas prácticas básicas para proteger el acceso a una computadora son:

- utilizar contraseñas fuertes;
- habilitar **two-factor authentication (2FA)**;
- utilizar un password manager.

### Contraseñas fuertes

Una contraseña debería ser:

- difícil de adivinar;
- suficientemente larga;
- diferente para cada servicio importante.

### Two-factor authentication

**2FA** agrega un segundo factor de verificación además de la contraseña.

De esta forma, conocer únicamente la contraseña no necesariamente permite acceder a la cuenta.

### Password managers

Un **password manager** permite almacenar y gestionar contraseñas de forma segura.

También facilita utilizar contraseñas largas y únicas sin tener que memorizarlas todas.

---

# Herramientas de desarrollo

## 4. IDE

Un **IDE (Integrated Development Environment)** reúne herramientas para desarrollar software dentro de un mismo entorno.

Normalmente puede incluir:

- editor de código;
- ejecución de programas;
- debugging;
- integración con herramientas de desarrollo;
- testing.

Su objetivo es facilitar tareas como escribir, probar y depurar código.

---

## 5. Code Editor

Un **code editor** es una herramienta especializada en escribir y editar código fuente.

Puede incluir características como:

- syntax highlighting;
- autocompletado;
- extensiones;
- navegación entre archivos;
- integración con herramientas externas.

Un IDE suele proporcionar un entorno más integrado, mientras que un editor puede ser más liviano y ampliarse mediante extensiones.

---

## 6. Git

**Git** es un sistema de control de versiones.

Permite:

- registrar cambios en archivos;
- consultar el historial del proyecto;
- crear versiones del código;
- trabajar con branches;
- colaborar con otras personas;
- revertir cambios cuando sea necesario.

Git trabaja con **repositories**.

---

## 7. Repositories

Un **repository** es un espacio donde se almacenan los archivos de un proyecto junto con su historial de versiones.

Puede existir:

- localmente, en la computadora;
- remotamente, en un servicio de hosting.

Servicios populares de alojamiento de repositorios incluyen:

- GitHub;
- GitLab;
- Bitbucket.

Git y GitHub no son lo mismo:

- **Git** es el sistema de control de versiones.
- **GitHub** es una plataforma que permite alojar y colaborar sobre repositorios Git.

---

## 8. Package Managers

Un **package manager** automatiza la instalación y administración de paquetes, librerías y dependencias.

Permite realizar tareas como:

- instalar paquetes;
- actualizarlos;
- eliminarlos;
- gestionar versiones y dependencias.

Ejemplos:

| Ecosistema | Package manager |
| --- | --- |
| JavaScript | npm |
| Python | pip |
| Java | Maven |

Las **dependencies** son paquetes externos que un proyecto necesita para funcionar.

---

## 9. Testing

El testing permite comprobar que el software funciona de acuerdo con lo esperado.

Existen librerías y frameworks que automatizan este proceso.

Ejemplos mencionados en el curso:

- Jest;
- PHPUnit;
- JUnit.

La idea general es ejecutar pruebas que verifiquen comportamientos concretos del programa y detecten errores cuando se modifica el código.

---

# Archivos y sistemas de archivos

## 10. Archivos y directorios

Un **file system** organiza la información almacenada en un dispositivo.

Sus elementos principales son:

- files;
- directories.

Un **directory** es otro nombre para una carpeta.

Los directorios pueden contener:

- archivos;
- otros directorios.

Esto permite crear una estructura jerárquica.

---

## 11. Root directory

El **root directory** es el directorio de nivel superior de un sistema de archivos o estructura determinada.

Los demás directorios se encuentran directa o indirectamente dentro de él.

Conceptualmente:

```text
root/
├── folder-a/
│   └── file.txt
└── folder-b/
```

---

## 12. Buenas prácticas al nombrar archivos

Los nombres deberían ser descriptivos y fáciles de mantener.

Preferible:

```text
about-us.html
```

En lugar de:

```text
page1.html
```

Un nombre descriptivo ayuda a entender el propósito del archivo sin necesidad de abrirlo.

También conviene mantener convenciones consistentes dentro de un proyecto.

---

## 13. `index.html`

En muchos servidores web, `index.html` representa la página predeterminada de un directorio.

Por ejemplo, al visitar:

```text
https://example.com/
```

el servidor puede entregar automáticamente:

```text
index.html
```

Por eso suele utilizarse como archivo principal de una página o sitio web simple.

---

## 14. Explorer y Finder

Los sistemas operativos incluyen herramientas gráficas para administrar archivos.

### Windows

Utiliza **File Explorer**.

### macOS

Utiliza **Finder**.

Estas herramientas permiten:

- crear archivos y carpetas;
- moverlos;
- copiarlos;
- renombrarlos;
- eliminarlos;
- buscarlos.

---

## 15. Buscar archivos y carpetas

Los gestores de archivos incorporan funciones de búsqueda.

Esto permite localizar elementos utilizando datos como:

- nombre;
- tipo;
- ubicación.

La capacidad de buscar correctamente archivos se vuelve especialmente importante a medida que los proyectos crecen.

---

# Markdown y documentación

## 16. Markdown

**Markdown** es un lenguaje de marcado ligero utilizado principalmente para escribir documentación.

Permite expresar estructura utilizando texto plano.

Ejemplo:

```md
# Título

## Sección

- Elemento 1
- Elemento 2

**Texto importante**
```

Es muy común en proyectos de software.

---

## 17. README

Un archivo `README` contiene información importante sobre un proyecto.

Normalmente se llama:

```text
README.md
```

Puede incluir:

- descripción;
- instalación;
- instrucciones de uso;
- requisitos;
- ejemplos;
- información para colaboradores.

Markdown es uno de los formatos más habituales para escribir README files.

---

# Tipos de archivos web

## 18. HTML, CSS y JavaScript

Las extensiones permiten identificar el tipo de un archivo.

### HTML

```text
.html
```

Ejemplo:

```text
index.html
```

Contiene la estructura y contenido de la página.

### CSS

```text
.css
```

Ejemplo:

```text
styles.css
```

Contiene reglas de estilo.

### JavaScript

```text
.js
```

Ejemplo:

```text
script.js
```

Contiene código JavaScript.

---

# Formatos multimedia

## 19. Imágenes y gráficos

### JPEG

```text
.jpg
.jpeg
```

Formato común para fotografías y otras imágenes con muchos colores.

### PNG

```text
.png
```

Formato de imagen muy utilizado que puede soportar transparencia.

### GIF

```text
.gif
```

Formato que puede almacenar animaciones simples.

### SVG

```text
.svg
```

Formato de gráficos vectoriales.

A diferencia de formatos rasterizados como JPEG o PNG, un SVG describe formas matemáticamente y puede escalar sin perder nitidez.

---

## 20. Audio

### MP3

```text
.mp3
```

Es uno de los formatos de audio comprimido más utilizados.

---

## 21. Video

### MP4

```text
.mp4
```

Formato ampliamente utilizado para video.

### MOV

```text
.mov
```

Formato desarrollado originalmente por Apple y utilizado para contenido de video.

---

# Fuentes

## 22. TTF

**TTF (TrueType Font)** es un formato común de fuentes.

```text
.ttf
```

---

## 23. WOFF y WOFF2

**WOFF (Web Open Font Format)** fue diseñado específicamente para utilizar fuentes en la web.

```text
.woff
```

Su sucesor es:

```text
.woff2
```

**WOFF2** proporciona mejor compresión y es un formato habitual para servir fuentes web modernas.

---

# Archivos comprimidos

## 24. ZIP

**ZIP** es un formato utilizado para comprimir uno o varios archivos y directorios.

```text
.zip
```

La compresión puede:

- reducir el tamaño total;
- agrupar múltiples archivos en uno;
- facilitar su transferencia o distribución.

---

# Navegación por la web

## 25. Web browser

Un **web browser** es una aplicación utilizada para acceder e interactuar con sitios web.

Ejemplos:

- Google Chrome;
- Mozilla Firefox;
- Microsoft Edge.

El navegador:

1. solicita recursos a través de Internet;
2. recibe documentos y archivos;
3. interpreta tecnologías como HTML, CSS y JavaScript;
4. presenta el resultado al usuario.

---

## 26. Search engine

Un **search engine** es un servicio que permite buscar información disponible en la web.

Ejemplos:

- Google;
- Bing;
- Yahoo.

No debe confundirse un navegador con un motor de búsqueda:

| Browser | Search engine |
| --- | --- |
| Aplicación que permite navegar la web | Servicio que permite buscar contenido |
| Chrome | Google Search |
| Firefox | Bing |
| Edge | Yahoo |

Un navegador puede utilizar distintos motores de búsqueda.

---

# Estrategias de búsqueda

## 27. Operador `site:`

Permite limitar los resultados a un sitio o dominio determinado.

```text
site:developer.mozilla.org flexbox
```

Esto busca resultados relacionados con `flexbox` dentro del dominio indicado.

Otro ejemplo:

```text
site:freecodecamp.org html
```

---

## 28. Operador `filetype:`

Permite buscar archivos de un tipo determinado.

```text
filetype:pdf computer networks
```

También puede combinarse con otros operadores:

```text
site:example.edu filetype:pdf algorithms
```

---

## 29. Excluir términos con `-`

Un término precedido por `-` puede utilizarse para excluir resultados relacionados con ese término.

```text
python -snake
```

La intención sería buscar información sobre Python excluyendo resultados asociados con serpientes.

---

## 30. Incluir términos con `+`

El review de freeCodeCamp también presenta `+` como una forma de indicar que un término debe incluirse en la búsqueda.

```text
web development +css
```

La sintaxis exacta y el comportamiento de operadores pueden variar entre motores de búsqueda, pero el concepto general es aprender a refinar una consulta en lugar de depender únicamente de una búsqueda genérica.

---

# Resumen rápido

Los conceptos centrales de **Computer Basics** son:

- La motherboard conecta los componentes principales de una computadora.
- La CPU ejecuta instrucciones; la RAM almacena temporalmente datos en uso.
- HDD y SSD proporcionan almacenamiento persistente.
- La PSU suministra energía y la GPU procesa gráficos.
- Un ISP proporciona acceso a Internet.
- Contraseñas fuertes, 2FA y password managers mejoran la seguridad.
- Un IDE integra herramientas de desarrollo; un code editor se centra principalmente en editar código.
- Git permite controlar versiones y los repositorios almacenan proyectos e historial.
- GitHub, GitLab y Bitbucket alojan repositorios remotos.
- Package managers administran librerías y dependencias.
- Testing verifica que el software se comporte correctamente.
- Un file system organiza archivos y directorios; el root directory representa el nivel superior.
- Markdown es ampliamente utilizado para documentación y archivos `README.md`.
- `.html`, `.css` y `.js` identifican los archivos principales del desarrollo web.
- JPEG, PNG, GIF y SVG son formatos gráficos; MP3 es común para audio y MP4/MOV para video.
- WOFF y WOFF2 son formatos orientados a fuentes web.
- ZIP permite comprimir archivos y directorios.
- Un browser permite navegar la web; un search engine permite buscar información dentro de ella.
- Operadores como `site:`, `filetype:` y `-` permiten realizar búsquedas más precisas.
