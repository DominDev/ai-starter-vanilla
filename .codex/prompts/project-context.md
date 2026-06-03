---
name: project-context
description: Load the architecture cheat sheet for Vanilla HTML/CSS/JS projects.
---

# Project Context (Vanilla)

Stack: HTML5 + CSS3 (`:root`, Grid/Flex, BEM) + Vanilla JS ES2020+.

```
project/
├── index.html
├── src/css/style.css     ← edytuj (style.min.css — auto)
├── src/js/main.js        ← edytuj (main.min.js — auto)
├── assets/img/originals/ ← tu umieszczaj obrazy
├── assets/img/optimized/ ← WebP/AVIF (auto)
├── _scripts/             ← build tools
└── package.json
```

Build: `npm run watch` | `minify:css` | `minify:js` | `optimize:images` | `optimize:video`

CSS: `:root` zmienne dla wszystkich kolorów/spacingów. BEM. Mobile-first.
JS: guard clause + IntersectionObserver. Init na DOMContentLoaded.
Zasada: edytuj tylko pliki źródłowe, nigdy `.min.*`.
