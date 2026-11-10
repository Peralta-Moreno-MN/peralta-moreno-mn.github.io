# peralta-moreno-mn.github.io

Academic website of **María Nuria Peralta Moreno** → https://peralta-moreno-mn.github.io

Built with [Jekyll](https://jekyllrb.com/) and the [Not Pure Poole](https://github.com/vszhub/not-pure-poole) theme, published with GitHub Pages. Illustrations by the artists credited in the [Artistic team](https://peralta-moreno-mn.github.io/gallery/artistic-team/) page.

## Guía rápida para editar

Todo se puede editar desde la web de GitHub (botón ✏️ en cada archivo). La web se actualiza sola un par de minutos después de guardar.

| Quiero cambiar… | Archivo |
|---|---|
| Título, descripción, foto de perfil, fondo general | `_config.yml` |
| Menú lateral | `_data/navigation.yml` |
| Iconos de contacto (email, ORCID, LinkedIn…) | `_data/social.yml` |
| Texto de cada sección | `about.md`, `research.md`, `publications.md`, `open-positions.md`… |
| Fotos de la galería | `_data/gallery.yml` + imágenes en `assets/img/gallery/` |
| Ilustradoras | `_data/illustrators.yml` |
| Gente en *Open positions* | `_data/people.yml` |
| Ilustraciones y tamaños | ver `assets/img/README.md` |

Los comentarios `<!-- ✏️ ... -->` dentro de los archivos indican qué falta por rellenar (no se ven en la web).

## Escribir en el blog

1. Copia la plantilla `_drafts/tutorial-template.md`.
2. Guárdala en `_posts/` con el nombre `AAAA-MM-DD-titulo-corto.md` (por ejemplo `2026-11-20-intro-to-python.md`).
3. Con `categories: [tutorials]` aparece en la sección *Tutorials*. Sin esa categoría, solo sale en el blog de la portada.

Lo que esté en `_drafts/` no se publica.
