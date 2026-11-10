# Guía para editar la web

Notas internas (esta carpeta no se publica en la web).

Todo se puede editar desde la web de GitHub (botón ✏️ en cada archivo). La web se actualiza sola un par de minutos después de guardar.

| Quiero cambiar… | Archivo |
|---|---|
| Título, descripción, foto de perfil, fondo general | `_config.yml` |
| Menú lateral | `_data/navigation.yml` |
| Iconos de contacto (email, ORCID, LinkedIn…) | `_data/social.yml` |
| Texto de cada sección | `pages/about.md`, `pages/research.md`, `pages/publications.md`, `pages/contact.md`… |
| Fotos de la galería | `_data/gallery.yml` + imágenes en `assets/img/gallery/` |
| Ilustradoras | `_data/illustrators.yml` |
| Gente en *Open positions* | `_data/people.yml` |
| Ilustraciones y tamaños | ver `assets/img/README.md` |

Los comentarios `<!-- ✏️ ... -->` dentro de los archivos indican qué falta por rellenar (no se ven en la web).

## Scientific Stories (series del blog)

1. Copia la plantilla `_drafts/story-template.md`.
2. Guárdala en `_posts/` como `AAAA-MM-DD-titulo-corto.md`.
3. Pon `series: from-leaf-to-lead` o `series: women-in-drug-design`.
4. La ilustración de cabecera va en `assets/img/stories/<serie>/` y se indica con `image:`.
5. Los datos de cada serie (descripción, ilustradora) están en `_data/series.yml`. Para crear una serie nueva, añádela ahí y crea su página en `pages/stories/` copiando una de las que hay.

## Escribir en el blog

1. Copia la plantilla `_drafts/tutorial-template.md`.
2. Guárdala en `_posts/` con el nombre `AAAA-MM-DD-titulo-corto.md` (por ejemplo `2026-11-20-intro-to-python.md`).
3. Con `categories: [tutorials]` aparece en la sección *Tutorials*. Sin esa categoría, solo sale en el blog de la portada.

Lo que esté en `_drafts/` no se publica.
