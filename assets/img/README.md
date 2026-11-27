# Imágenes de la web 🎨

Guía para las ilustradoras (y para Nuria). Esta carpeta no aparece en la web, es solo una nota.

## Carpetas

| Carpeta | Qué va aquí |
|---|---|
| `backgrounds/` | Fondo de la barra lateral (`sidebar.jpg`), oscuro y con el texto en blanco encima |
| `covers/` | Portadillas de cada sección: `about.jpg`, `research.jpg`, `publications.jpg`, `tutorials.jpg`, `gallery.jpg`, `open-positions.jpg` |
| `gallery/infographics/` | **Infografías** (mujeres en la ciencia, divulgación) |
| `gallery/conferences/` | Fotos de congresos |
| `gallery/abstracts/` | Graphical abstracts de artículos |
| `gallery/outreach/` | Divulgación y vida en el laboratorio |
| `illustrators/` | Foto o autorretrato de cada ilustradora (opcional) y `cover.jpg` para la tarjeta *Artistic team* de la galería |
| `stories/from-leaf-to-lead/` | Ilustraciones scrapbook de la serie *From Leaf to Lead* (plantas medicinales) |
| `stories/women-in-drug-design/` | Ilustraciones de la serie *Women in Drug Design* |
| `stories/structure-function/` | Ilustraciones de *From Structure to Function (and Back)* |
| `stories/paths-in-science/` | **Fotos de Nuria** para *We Make the Path by Walking* |
| `stories/rare-diseases/` | Ilustraciones de la serie *Rare but Real* (enfermedades raras) |
| `blog/` | Imágenes para otras entradas del blog (tutoriales…) |

## Cómo se ve la ilustración de fondo / portadilla

El fondo ocupa la **barra lateral izquierda**, con la foto, el nombre y el menú **en blanco encima**:

- En ordenador es una columna **alta y estrecha** (¼ del ancho de la pantalla, toda la altura).
- En móvil es una **franja ancha** arriba de la página.

La imagen se recorta automáticamente desde el centro, así que:

- **Tamaño recomendado:** 1600 × 1600 px (cuadrada), con lo importante en el centro.
- **Contraste:** el texto va en blanco, así que mejor tonos medios u oscuros, o una zona tranquila en el centro.
- **Formato:** JPG o WebP, idealmente **menos de 400 KB** (se puede comprimir en [squoosh.app](https://squoosh.app)).
- **Nombres:** en minúsculas, sin espacios ni tildes, por ejemplo `research.jpg`.

## Cómo activar el fondo de una sección

En el archivo de la sección (por ejemplo `pages/research.md`), añadir esta línea en la cabecera,
o quitarle el `#` si ya está:

```yaml
background_image: /assets/img/covers/research.jpg
```

El fondo se ve **alrededor del panel blanco** del texto, así que conviene que sea suave y claro.

Para cambiar el fondo de la barra lateral (el mismo en toda la web), cambiar `cover_image` en
`_config.yml`. Ese sí es oscuro, porque lleva el texto en blanco encima.

### Ya puestos

- Barra lateral: `backgrounds/sidebar.jpg`
- Home: `covers/home.jpg` · About: `covers/about.jpg` · Research: `covers/research.jpg` ·
  Publications: `covers/publications.jpg`
- Faltan: Tutorials, Scientific Stories, Gallery, Open positions y Contact.

## Scientific Stories (cabeceras de las entradas)

Cada entrada lleva **una ilustración de cabecera**. La misma imagen sirve para la web y para
redes sociales, si se entrega así:

### Una sola imagen madre

- **Lienzo cuadrado de 2400 × 2400 px.**
- **Fondo transparente** (PNG), no blanco. Así se ve bien tanto en la web clara como si alguien
  la mira con el móvil en modo oscuro.
- **Todo lo importante dentro del círculo central**, dejando un margen generoso arriba y abajo
  que se pueda recortar sin perder nada. Esa es la "zona segura".
- **Sin texto dentro del dibujo.** Los títulos los pone la web, y así la misma ilustración vale
  en español y en inglés.

De esa imagen salen todas las versiones (eso lo hago yo, no hace falta que las exporte ella):

| Dónde | Tamaño | Cómo se obtiene |
|---|---|---|
| Cabecera en la web | 1800 × 1200 px (3:2) | recortando arriba y abajo |
| Lista de la serie | miniatura automática | — |
| LinkedIn / Instagram | 1200 × 1200 px | la imagen cuadrada entera |

### Si prefiere trabajar en vertical

No hay problema: que entregue el dibujo vertical **centrado dentro de un lienzo cuadrado** de
2400 × 2400 px, con el espacio sobrante transparente.

### Otros detalles

- **Formato:** PNG con transparencia. Si pesa mucho, yo lo comprimo.
- **Nombre:** el tema de la entrada, en minúsculas y sin tildes, por ejemplo
  `friedreich-ataxia.png`.
- Cada serie puede tener además una imagen de presentación `cover.png` en su carpeta, con las
  mismas características.
- **Cuántas:** una por entrada. Si una entrada es larga, pueden añadirse uno o dos dibujos
  pequeños sueltos para acompañar el texto.

## Infografías

- **Formato vertical**, por ejemplo **1080 × 1350 px** (4:5, el mismo que Instagram) o A4. Se muestran **enteras**, sin recortar.
- Para que se lean bien, el texto de la infografía no debería ser más pequeño de unos 28 px a ese tamaño.
- **Nombre:** año y tema, por ejemplo `2026-rosalind-franklin.jpg`.
- Después de subirla, añadirla a `_data/gallery.yml`, en la parte `infographics` (hay un ejemplo).

## Imágenes de la galería

- **Tamaño:** unos 1600 px de ancho máximo, formato horizontal (4:3) queda mejor.
- Cada sección puede tener una imagen de presentación llamada `cover.jpg` dentro de su carpeta.
- Después de subir una foto, hay que añadirla a `_data/gallery.yml` (hay un ejemplo dentro).
