# Bitácora entrega de Examen — Portafolio

Este es el sitio web de mi portafolio diseñado en Figma y programado en HTML, CSS y JavaScript.
Diseño de Interfaces Web · Escuela de Diseño UDP · 2026.

---

## 1. Links

- **Figma:** [Portafolio — Dayana Pañitrur](https://www.figma.com/design/SvdCCedXN1f5jIqTT5qNZ4/Portafolio?node-id=0-1&t=dZy0oRhedNlDO1jj-1)
- **Sitio en GitHub Pages:** https://dayanapanitrur.github.io/portafolio/index.html
- **Repositorio Portafolio:** https://github.com/dayanapanitrur/portafolio
---

### Entrega final — 23 de noviembre

- **Qué hice:** pasé el diseño de Figma a código. El sitio tiene 6 páginas enlazadas entre sí:
  - `index.html`: portada, sobre mí y proyectos.
  - `contacto.html`: correo, GitHub y LinkedIn.
  - 4 páginas de proyecto: Banca modular, Mimus thenca, SEQ-01 y SEQ-02, y Sin_Te.
- **Interacciones:**
  * cabe destacar que trabajando en el código se agregaron algunas interacciones que en figma no pude realizar.
  - Header pegado arriba (sticky) que cambia de color según el fondo y marca con un punto la sección visible.
  - Portada azul que se "rasca" con el cursor y deja ver una foto de paisaje durante medio segundo.
  - Caja de CD en 3D en "Sobre mí", que se abre con hover en desktop y con un toque en mobile.
  - Pila de vinilos con los proyectos: el hover o el toque saca un vinilo, y la rueda del mouse o el swipe hacen avanzar la pila en loop.
  - Cursor personalizado tipo *bounding box*, tal como en el UI Kit, que muestra el nombre de lo que apunta y sus coordenadas.
- **Cambios respecto del Figma al revisar el sitio:**
  - Quité el texto "toca el cd para abrirlo".
  - El vinilo activo ahora pasa al frente de la pila para que se vea su portada completa.
  - Reemplacé el garabato de la portada por el fondo azul que se revela con el cursor.

---

## 3. Uso de IA

**Herramienta:** Claude Code (aplicación de escritorio de Claude), modelo Claude Opus 5.5, se le fue enviado mi archivo de Figma para leer colores, tipografías, componentes y medidas.

**Dónde no usé IA:** el diseño en Figma (UI kit, componentes y prototipo), las fotos, los textos de los proyectos y las decisiones de diseño.

### 3.1 Análisis antes de programar

> **Prompt:** «Antes de comenzar con cualquier código quiero que analices todas las reglas requeridas que se deben aplicar al código. Te adjunto mi link de Figma para que entiendas la estructura, y tomes en cuenta cada componente, organización, colores, tipografía, estilos, etc. Escribe el CSS para que la página se vea como el PNG. Usa solo flexbox, unidades rem y %. No uses grid ni frameworks, usa position solo para el header y que este quede sticky en la parte superior. Comenta cada regla en español explicando qué hace, en lenguaje simple.»
> Además le entregué la lista de qué sacar y qué no sacar de Dev Mode (sí: colores, tipografía, radios, gap, padding y alineación; no: position absolute, anchos y altos fijos, márgenes con decimales ni frames sin Auto Layout).

- **Qué me entregó:**
  - Un resumen de la rúbrica.
  - Los colores, las tipografías y los espacios del Figma convertidos a rem.
  - Una lista de problemas en mi archivo: frames sin Auto Layout, títulos distintos entre desktop y mobile, textos de relleno, una falta de ortografía ("Ejeemplo") y elementos encimados que no se pueden hacer sin `position`.
- **Qué ajusté y por qué:** usé la lista para decidir qué valores tomar de Dev Mode y cuáles no.

### 3.2 Preguntas para hacerlo de inmediato en una sola ronda

> **Prompt:** «El diseño en Figma está listo, hay ciertas cosas que ajustaremos en código ahora. Debes hacer las cosas al pie de la letra y bien hechas, con sus conversiones, con la integración de la tipografía, etc. […] Hazme las preguntas necesarias para hacer las cosas de un solo tiro y no estar arreglando de a poco.»

- **Qué me entregó:** 8 preguntas con opciones. Mis respuestas fueron:
  - Trabajar en la carpeta `codigo/`.
  - Encimar los vinilos con flex y `transform`.
  - Que el texto del header se invierta según el fondo.
  - Títulos de sección azules en desktop y en mobile.
  - Usar el modelo 3D final del CD (`cd-case-con-foto.glb`).
  - Carrusel con hover o toque, más scroll en loop.
  - Garabato interactivo.
  - Tipografías desde Google Fonts.
- **Qué ajusté y por qué:**
  - Para el header elegí `mix-blend-mode`. Claude me mostró que con ese método el texto blanco sobre el azul `#142BFF` se ve amarillo, así que acepté cambiarlo por un javascript que pasa el texto a azul cuando la portada ya pasó.
  - También acepté que en mobile el segundo toque abra el proyecto. Si no, no habría forma de entrar a las páginas de proyecto desde el celular.

### 3.3 Contenido de los proyectos

> **Prompt:** le entregué el nombre, el año, la descripción y los autores de todos los proyectos para que automatizara la página base de proyecto.

- **Qué me entregó:** las 4 páginas de proyecto armadas con mis textos.
- **Qué ajusté y por qué:**
  - Acepté algunas correcciones que me marcó:
   - "SEQ-01 Y SEQ-02" quedó con "y" minúscula.
   - Corregí "CD555" por "NE555", ya que es más conocido por ese nombre.
  - Definí las áreas: Mimus thenca solo "diseño industrial"; SEQ y Sin_Te, "diseño industrial" y "electrónica".

### 3.4 Ajustes después de revisar en Live Server

> **Prompt:** «Quitar el texto de toca el cd para abrirlo. Los vinilos deben salir hacia el lado, para que se logre ver la portada. El fondo azul debe ser reactivo al cursor. El cursor no tiene el diseño de Figma, que se debería poder hacer con JS.»

- **Qué me entregó:**
  - Quitó el texto.
  - Hizo que el vinilo activo pase al frente.
  - Creó un efecto de "linterna" sobre la portada.
  - Programó el cursor *bounding box* con coordenadas en vivo.
- **Qué ajusté y por qué:**
  - La IA me preguntó qué efecto quería en el fondo. Elegí que revelara la foto.
  - Para el cursor elegí que muestre el nombre de lo que apunta y que funcione en todo el sitio, solo con mouse.

> **Prompt:** «Hay que eliminar la línea anterior que parece una serpiente, queda solo lo reactivo, el fondo aparece a medida que el cursor pasa por el color azul y deja un delay de medio segundo actuando casi como un "paint".»

> **Prompt:** «Ahora aparece todo el fondo, corrige que la imagen se revela solo en las zonas por donde pasa el cursor como una pintura, el cursor es el que va revelando como un rascador, no aparece todo el fondo de inmediato.»

- **Qué me entregó:**
  - Quitó el garabato.
  - Hizo el fondo "rascable" con un `<canvas>`.
  - Corrigió el error en Safari (ver Problemas y soluciones).
- **Qué ajusté y por qué:** lo revisé en mi navegador hasta que se comportó como yo quería: azul de inicio y la foto solo por donde pasa el cursor.

### 3.5 Esta bitácora

> **Prompt:** «Ahora sí recurro para que me ayudes redactando el README, déjalo listo en markdown para copiar y pegar.»

- **Qué me entregó:** la estructura de este README con lo que se hizo en la sesión.
- **Qué ajusté y por qué:** completé los avances, los links y los aprendizajes con mis propias palabras.

---

## 4. Problemas y soluciones

| Problema | Solución |
|---|---|
| El Figma usa elementos encimados (caja de CD, pila de vinilos, cursor), pero la regla era usar `position` solo en el header. | El CD es un modelo 3D dentro de un `<canvas>`. Los vinilos van en una fila flex con margen negativo y `transform`. El cursor es un elemento flex que se mueve con `transform`. |
| El header es sticky con letras blancas y, sobre las secciones claras, dejaba de leerse. | Un JavaScript le agrega una clase que cambia el texto a azul cuando la portada azul ya pasó. |
| El fondo azul/blanco del inicio se repetía cada media pantalla. | El degradado se calculaba sobre la ventana y no sobre la página. Lo arreglé dándole fondo blanco a `html`. |
| Al saltar a una sección desde el menú, el título quedaba tapado por el header. | Agregué `scroll-margin-top` con el alto del header. |
| Abriendo `index.html` con doble clic, el CD 3D no cargaba. | Los módulos de JavaScript y el modelo `.glb` necesitan un servidor. Lo pruebo con Live Server en VS Code. |
| Las imágenes descargadas de Figma pesaban hasta 9,5 MB. | Las convertí a JPG de 1600 px de ancho (entre 150 y 480 KB cada una). |
| En mobile, el vinilo que salía quedaba tapado por los de adelante. | El vinilo activo pasa al frente de la pila (`z-index`) y sale 40 px hacia el lado. |
| El efecto del fondo no funcionaba: el navegador no aceptaba `@property` con `initial-value: 0rem`. | Ese valor no puede depender del tamaño de letra, así que lo cambié a `0`. |
| El cursor aparecía lejos del mouse. | Las medidas `offsetTop` dentro de un elemento con `transform` se calculan distinto. Las cambié por `getBoundingClientRect()`. |
| En Safari se veía la foto completa mientras se movía el mouse. | El dibujo se convertía en una imagen nueva en cada cuadro y Safari no alcanzaba a cargarla. Ahora se dibuja directo en un `<canvas>` puesto detrás del header y la portada (con margen negativo igual a su alto). |

---

## 5. Aprendizajes

- **Diseñar pensando en el código:** los frames sin Auto Layout no se pueden copiar de Dev Mode, porque entregan posiciones fijas. Lo que sí sirve directo son los colores, las tipografías, los gaps y los paddings.
- **Encimar sin `position`:** se puede con flexbox, márgenes negativos y `transform`, y entendí cómo funciona el orden de capas (`z-index`) en los elementos flex.
- **Convertir medidas:** todo lo de Figma lo pasé a `rem` (dividiendo los px por 16), y usé `%` para que el sitio se adapte al ancho de la pantalla.
- **Probar en más de un navegador:** algo que funcionaba en Chrome fallaba en Safari, y solo lo descubrí probándolo.
- **Trabajar con IA:** sirve más cuando le doy reglas claras y reviso lo que entrega. Varias decisiones fueron mías: el efecto del fondo, cómo salen los vinilos y qué muestra el cursor. Otras las cambié después de verlas funcionando.
