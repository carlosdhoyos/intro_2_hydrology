# Introducción a la Hidrología

Material del curso de Hidrología — Carlos D. Hoyos, Facultad de Minas, Universidad Nacional de Colombia.

Sitio publicado: https://carlosdhoyos.github.io/intro_2_hydrology/

## Estructura

```
intro_2_hydrology/
├── myst.yml            ← configuración y tabla de contenido del libro
├── index.md            ← página de inicio del libro
├── recursos.md         ← lista de PDFs e interactivos
├── capitulos/          ← capítulos del libro (.md o .ipynb), con LaTeX
├── notebooks/          ← Jupyter notebooks
├── documentos/         ← PDFs (notas, diapositivas, talleres)
├── interactivos/       ← HTML autocontenidos (simuladores, visualizaciones)
├── datos/              ← datos usados en notebooks y ejemplos
├── figuras/            ← imágenes usadas en los capítulos
└── referencias.bib     ← bibliografía (BibTeX)
```

## Subir archivos desde el navegador

1. Entra a la carpeta (`documentos/` o `interactivos/`) en GitHub.
2. **Add file → Upload files**, arrastra los archivos y haz **Commit changes**.
3. En uno o dos minutos quedan publicados en
   `https://carlosdhoyos.github.io/intro_2_hydrology/<carpeta>/<archivo>`.

Usa nombres en minúscula, sin espacios ni tildes.

## Escribir capítulos

Los capítulos son archivos Markdown ([MyST](https://mystmd.org/guide)) con ecuaciones en LaTeX:
`$P - ET$` en línea o bloques `$$ ... $$`. Cada capítulo nuevo se agrega a `toc` en `myst.yml`.

Las referencias van en `referencias.bib` y se citan con `[@clave]`, por ejemplo `[@chow1988]`.

Para verlo en local: `npx jupyter-book@2.1.7 start` (requiere Node.js).
