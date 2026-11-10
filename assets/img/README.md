# Imágenes de la web 🎨

Guía para las ilustradoras (y para Nuria). Esta carpeta no aparece en la web, es solo una nota.

## Carpetas

| Carpeta | Qué va aquí |
|---|---|
| `backgrounds/` | Fondo general de la barra lateral (`default.jpeg` es el de ahora, del tema original) |
| `covers/` | Portadillas de cada sección: `about.jpg`, `research.jpg`, `publications.jpg`, `tutorials.jpg`, `gallery.jpg`, `open-positions.jpg` |
| `gallery/infographics/` | **Infografías** (mujeres en la ciencia, divulgación) |
| `gallery/conferences/` | Fotos de congresos |
| `gallery/abstracts/` | Graphical abstracts de artículos |
| `gallery/outreach/` | Divulgación y vida en el laboratorio |
| `illustrators/` | Foto o autorretrato de cada ilustradora (opcional) y `cover.jpg` para la tarjeta *Artistic team* de la galería |
| `blog/` | Imágenes para las entradas del blog |

## Cómo se ve la ilustración de fondo / portadilla

El fondo ocupa la **barra lateral izquierda**, con la foto, el nombre y el menú **en blanco encima**:

- En ordenador es una columna **alta y estrecha** (¼ del ancho de la pantalla, toda la altura).
- En móvil es una **franja ancha** arriba de la página.

La imagen se recorta automáticamente desde el centro, así que:

- **Tamaño recomendado:** 1600 × 1600 px (cuadrada), con lo importante en el centro.
- **Contraste:** el texto va en blanco, así que mejor tonos medios u oscuros, o una zona tranquila en el centro.
- **Formato:** JPG o WebP, idealmente **menos de 400 KB** (se puede comprimir en [squoosh.app](https://squoosh.app)).
- **Nombres:** en minúsculas, sin espacios ni tildes, por ejemplo `research.jpg`.

## Cómo activar una portadilla

En el archivo de la sección (por ejemplo `research.md`), quitar el `#` de la línea:

```yaml
# cover_image: /assets/img/covers/research.jpg
```

Para cambiar el fondo de toda la web, cambiar `cover_image` en `_config.yml`.

## Infografías

- **Formato vertical**, por ejemplo **1080 × 1350 px** (4:5, el mismo que Instagram) o A4. Se muestran **enteras**, sin recortar.
- Para que se lean bien, el texto de la infografía no debería ser más pequeño de unos 28 px a ese tamaño.
- **Nombre:** año y tema, por ejemplo `2026-rosalind-franklin.jpg`.
- Después de subirla, añadirla a `_data/gallery.yml`, en la parte `infographics` (hay un ejemplo).

## Imágenes de la galería

- **Tamaño:** unos 1600 px de ancho máximo, formato horizontal (4:3) queda mejor.
- Cada sección puede tener una imagen de presentación llamada `cover.jpg` dentro de su carpeta.
- Después de subir una foto, hay que añadirla a `_data/gallery.yml` (hay un ejemplo dentro).
