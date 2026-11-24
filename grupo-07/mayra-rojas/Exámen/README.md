# Portafolio "Enredo"

**Mayra Rojas Navarrete**

## Links

- **Figma:** [Mayra_Rojas](https://www.figma.com/design/L9RpAE1Ldrwp0iBiD6lh7e/Mayra_Rojas?node-id=2-3&t=4RawuXpS1ifvomIv-1)
- **GitHub Pages:**

---

## Registro por avance

### Avance 1 · Concepto y referentes

Mi proyecto será la página web de mi portafolio.

Para empezar a diseñar un boceto necesitaba una identidad gráfica que unifica mis gustos personales y profesionales. Busqué varios referentes de páginas web, especialmente de tiendas y portafolios de arte con la estética que buscaba.

#### Referentes

**[Emergence Projects](https://emergenceprojects.com/)**
Esta es una página web de Khoren Matevosyan, un artista visual y director de arte de Armenia.
- Me llamó mucho la atención su página de entrada, que tiene una ilustración monocromática y que va cambiando al menú principal cuando haces scroll.
- Me gustaría tomar en cuenta el uso de símbolos y la interactividad de estos.

**[Saint Helena Studio](https://sainthelenastudio.com/)**
Esta página es de una diseñadora multidisciplinaria de Italia.
- Rescato la interactividad del cursor, que cada vez que lo mueves deja una especie de trazo.
- Me gusta su página principal, que tiene el nombre de su estudio en grande.
- También la información y cómo la diagrama en la página.

**[Maison Moderne Studio](https://maisonmodernestudio.com/)**
Esta web es de Modernè, un estudio de Londres dedicado al branding de marcas.
- Me gustaría aplicar sus estilos de tipografías.
- Su interacción al hacer scroll y al pasar por encima de los elementos.
- Su diagramación de ciertos frames.

### Avance 2 · Diseño en Figma

- Avancé en el Figma: incluí las animaciones y el dibujo de los íconos de cada sección del portafolio, y la animación de la primera página.
- Incluí las tipografías, colores y botones en el UI kit:
  - **Futura PT Condensed** para el body.
  - **Kolo LP** para los headers.

### Avance 3 · Semana previa al examen

#### Miércoles 18

- Comencé el código HTML y CSS.
- Continué con el Figma: seleccioné los proyectos e imágenes, avancé con el footer y empecé la versión mobile.

#### Sábado 21

- Terminé el Figma desktop.
- El logo del footer en escritorio no estaba centrado verticalmente: quedaba pegado abajo. Ahora queda centrado (60 px arriba y 60 px abajo).
- Hice el footer mobile igual al Figma: logo centrado arriba, enlaces (Sobre mí, Proyectos, Contacto) a la izquierda, y dirección, correo y año a la derecha.
- Revisé que el footer se viera bien en un celular (393 px) y en pantallas grandes (1440 px y 1728 px, que es el ancho de un MacBook Pro de 16").

---

## Uso de IA

**Herramienta:** Claude

### 1. Fotos de los proyectos

**Prompt:** adjunté las fotos de los proyectos en tres entregas:
- 20 fotos con los nombres de las capas de Figma (Proceso, Grafica, Archivo, Principal_Lum, Detalle_broche, Espalda, calle, penultima_lampara, entre otras).
- 12 fotos más (Jorge_Morales, Iso, Principal, Archivo_vivo, Cuento, Lum, Habitar_la_luz, Entrejuegos_1, IMG_1272_1, entre otras).
- Las 4 fotos que faltaban de "Habitar la luz": principal, iso, general y detalle de la lámpara.

**Qué se hizo:**
- Se ubicó cada foto en su página y en su lugar del collage.
- Las fotos con fondo transparente (isométricas y personaje del cuento) se dejaron en PNG para que se vean sobre el fondo crema.
- Si una foto falta, se muestra un recuadro de color en vez de una imagen rota.

### 2. Fuentes e íconos animados

**Prompt:**
> Necesito que incluyas las fuentes y los iconos animados

**Qué se hizo:**
- **Garabato de la portada:** el trazo se dibuja en 2 segundos, en bucle, con los tiempos de Figma.
- **Trazo de Sobre mí:** se dibuja detrás de mi foto.
- **Íconos y logo:** al pasar el cursor, el trazo se redibuja en bucle, como la variante hover de mi diseño.
- **Agregado de Claude (se puede quitar):** las fotos aparecen suavemente al hacer scroll y los íconos de la portada entran de a uno.
- Quien tenga activada la opción de menos movimiento ve todo quieto.

### 3. Footer y versión mobile

**Prompt:**
> necesito arreglar el footer porque el ícono de la izquiera no está centrado, además necesito hacer la versión mobile que está en figma [link del frame "Mobile"]

**Qué se hizo:**
- Leyó el diseño mobile directo desde Figma y cambió `style.css` (página de inicio) y `paginas.css` (resto de las páginas).
- Encontró que el logo del footer tenía `align-self: end` (por eso quedaba abajo) y lo cambió a `center`.
- Para mobile armó el footer con una grilla de dos filas: el logo arriba al centro, los enlaces a la izquierda y la dirección a la derecha, usando las medidas de Figma.
- Lo probó en el navegador en tamaño celular y escritorio.

### 4. Revisión en pantalla grande

**Prompt:**
> ¿se ve centrado para un mac de 16?

**Qué se hizo:** probó el sitio a 1728 × 1117 px (la resolución por defecto de ese computador) y confirmó que el logo, los enlaces y la dirección quedan centrados en el footer. No hubo que cambiar código.

**Qué ajusté y por qué:** nada, porque ya estaba bien.

### 5. Orden de esta bitácora

**Prompt:**
> A continuación te adjunto mi bitacora, necesito que me la ordenes y organices para que sea más facil de leer

**Qué se hizo:**
- Ordenó la bitácora con títulos por sección y por avance, y separó los días de la semana previa al examen.
- Pasó los referentes y los usos de IA a listas, con el mismo formato en cada uno (prompt y qué se hizo).
- Arregló la tabla de problemas y soluciones, que estaba a medio formatear.
- Corrigió detalles de ortografía y mayúsculas, sin cambiar el contenido.

### 6. Fotos que no se veían en GitHub Pages

**Prompt:**
> sos, lo subi a github pages y no se ven las fotos https://mayraarn.github.io/enredo-mayra-portafolio/proyecto-1.html

**Qué se hizo:**
- Comparó las rutas de las fotos en el código con los archivos publicados en el repositorio.
- Encontró que las fotos estaban sueltas en la raíz y no dentro de la carpeta `img/`, que es donde las buscan las páginas.
- Me explicó cómo subir la carpeta `img` completa desde GitHub. No hubo que cambiar código.

---

## Problemas y soluciones

| Problema | Solución |
|---|---|
| El logo del footer (escritorio) no estaba centrado: quedaba pegado al borde de abajo. | Tenía `align-self: end` y lo cambié a `center` en el CSS. |
| En celular el footer se veía distinto al diseño de Figma: todo en una columna y alineado a la izquierda. | Lo armé con `grid-template-areas`: el logo arriba en el centro, los enlaces a la izquierda y la dirección a la derecha, con las medidas de Figma (22 px de margen y 18 px de letra). |
| En mobile el logo del footer medía 45 px de alto en vez de 40 px, y eso bajaba todo lo demás. | El SVG tomaba la proporción de sus atributos `width` y `height`, no la del dibujo. Le di un alto fijo (`height: 40px`). |
| Los cambios del footer había que hacerlos dos veces. | El inicio usa `style.css` y las demás páginas usan `paginas.css`, así que el arreglo va en los dos archivos. |
| Al subir el sitio a GitHub Pages no se veían las fotos. Las páginas las buscan en la carpeta `img/` (por ejemplo `img/p1-principal.jpg`), pero las subí sueltas en la raíz del repositorio, así que la carpeta `img` no existía y las fotos daban error 404. | Subí la carpeta `img` completa (arrastrando la carpeta, no las fotos sueltas) con **Add file → Upload files**, para que las rutas coincidieran con las del código. |

---

## ¿Qué aprendí?

- Cómo pasar tipografías de Adobe Fonts a Figma y al código.
- Diseñar primero para escritorio y después adaptarlo a celular.
- Usar CSS Grid para ordenar un bloque, como el footer, en varias zonas.
- Animar un trazo SVG para que parezca dibujado a mano.
- Usar IA como apoyo para traspasar el diseño de Figma a código, sobre todo con las animaciones.
