# Guía de estilo para interactivos

Para que un HTML interactivo se vea como el sitio principal
(https://carlosdhoyos.github.io/), copia el texto de abajo en el chat de Claude
donde lo estés creando o editando.

---

```text
Ajusta este HTML para que coincida con el estilo de mi sitio web (carlosdhoyos.github.io).
Mantén toda la funcionalidad; cambia solo la apariencia. Debe seguir siendo UN solo
archivo HTML autocontenido.

TIPOGRAFÍA
- Fuente "Geist" (texto) y "Geist Mono" (números, etiquetas, código), desde Google Fonts:
  <link href="https://fonts.googleapis.com/css2?family=Geist:wght@400;500;600&family=Geist+Mono&display=swap" rel="stylesheet">
- Títulos en peso 600 con letter-spacing ligeramente negativo (-0.02em).

COLORES (usar variables CSS en :root)
Modo claro:
  --bg: #f7f8fb;  --fg: #0d1321;  --muted: #5b6475;  --line: #dfe3ea;
  --card: rgba(255,255,255,0.8);  --accent: #1d4ed8;  --accent-2: #0ea5e9;
Modo oscuro:
  --bg: #070b14;  --fg: #e8edf6;  --muted: #94a0b4;  --line: #1e2738;
  --card: rgba(13,20,36,0.8);  --accent: #60a5fa;  --accent-2: #22d3ee;
- Define el modo oscuro con :root[data-theme="dark"] { ... }.
- Para series de gráficas usa accent y accent-2 primero; si necesitas más colores,
  elige tonos que se vean bien en ambos modos.

MODO OSCURO Y IDIOMA (para que respete lo que el visitante eligió en mi sitio)
Pon este script en el <head>, antes del CSS:
  <script>
  (function(){var d=document.documentElement,t,l;
  try{t=localStorage.getItem('theme');l=localStorage.getItem('lang')}catch(e){}
  d.dataset.theme=t||(matchMedia('(prefers-color-scheme: dark)').matches?'dark':'light');
  d.lang=l||'es';})()
  </script>
- Agrega un botón pequeño (ícono de luna/sol) arriba a la derecha que cambie
  data-theme entre "light" y "dark" y lo guarde con localStorage.setItem('theme', ...).
- Si el contenido es bilingüe, usa document.documentElement.lang ('es' o 'en').

COMPONENTES
- Fondo de página var(--bg), texto var(--fg), texto secundario var(--muted).
- Tarjetas/paneles: fondo var(--card), borde 1px solid var(--line), border-radius 16px,
  padding 24px. Al pasar el mouse: borde con el color accent y translateY(-2px).
- Botones principales: forma de píldora (border-radius 999px), fondo var(--fg),
  texto var(--bg). Botones secundarios: píldora con borde var(--line) y fondo var(--card).
- Controles (sliders, inputs): color de acento var(--accent); inputs con borde
  var(--line), redondeados, y borde var(--accent) al enfocar.
- Etiquetas y números pequeños en Geist Mono, color var(--accent).
- Para resaltar algo, degradado de var(--accent) a var(--accent-2).
- Ancho máximo del contenido 1024px, centrado, con márgenes laterales de 16px
  (24px en pantallas medianas). Debe verse bien en celular.
- Transiciones suaves (0.2–0.3s). Respeta prefers-reduced-motion.

ENCABEZADO
- Arriba, un enlace discreto "← Hidrología" que lleve a
  https://carlosdhoyos.github.io/cursos/hidrologia/
- Título del recurso grande (unos 40px, peso 600) y una línea de descripción en var(--muted).

ECUACIONES (si las hay)
- Usa KaTeX desde cdn.jsdelivr.net y que el color siga a var(--fg).
```

---

## Por qué funciona el modo oscuro compartido

Los interactivos se publican en el mismo dominio que el sitio principal
(`carlosdhoyos.github.io`), así que pueden leer la preferencia de tema e idioma que el
visitante eligió allí (`localStorage` con las claves `theme` y `lang`).

Los colores vienen de `src/app/globals.css` del repositorio
[carlosdhoyos.github.io](https://github.com/carlosdhoyos/carlosdhoyos.github.io); si
cambian allí, actualiza esta guía.
