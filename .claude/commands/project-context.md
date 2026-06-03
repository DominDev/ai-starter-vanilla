---
name: project-context
description: Loads the project architecture cheat sheet for Vanilla HTML/CSS/JS projects — directory structure, build pipeline, file responsibilities, and conventions. Use at session start or when you need a full project overview.
---

# Project Context (Vanilla)

## Tech stack

HTML5 + CSS3 (`:root` variables, Grid/Flex, BEM) + Vanilla JS ES2020+.
Build: npm scripts. Watch: `node _scripts/watch.js`.

## Standard directory structure

```
project/
├── index.html              ← main entry (or multiple .html pages)
├── src/
│   ├── css/
│   │   ├── style.css       ← source styles (EDIT THIS)
│   │   └── style.min.css   ← auto-generated (DON'T EDIT)
│   └── js/
│       ├── main.js         ← source JS (EDIT THIS)
│       └── main.min.js     ← auto-generated (DON'T EDIT)
├── assets/
│   ├── img/
│   │   ├── originals/      ← place source images here
│   │   └── optimized/      ← WebP/AVIF output (auto-generated)
│   ├── vid/
│   │   ├── originals/
│   │   └── optimized/      ← WebM/MP4 output (auto-generated)
│   └── fonts/              ← web fonts (woff2)
├── _scripts/               ← build tools (not production code)
│   ├── watch.js            ← file watcher (Ctrl+Shift+B)
│   ├── minify-css.js       ← CSS minification (Terser)
│   ├── minify-js.js        ← JS minification (Terser + source maps)
│   ├── optimize-images.js  ← image conversion (Sharp → WebP/AVIF)
│   └── optimize-video.js   ← video encoding (FFmpeg → WebM/MP4)
├── _docs/                  ← docs, audit reports (not deployed)
├── package.json
├── .gitignore
└── .editorconfig
```

## Build pipeline

```bash
npm run watch           # start all file watchers (Ctrl+Shift+B in VSCode)
npm run minify:css      # src/css/*.css → *.min.css
npm run minify:js       # src/js/*.js → *.min.js (+ source maps)
npm run optimize:images # assets/img/originals/ → optimized/ (WebP/AVIF, 400/800/1200/1600px)
npm run optimize:video  # assets/vid/originals/ → optimized/ (WebM/MP4)
```

## Layer responsibilities

| Layer | File(s) | Responsibility |
|-------|---------|----------------|
| Structure | `index.html` | Semantic markup, sections, forms, meta |
| Styles | `src/css/style.css` | Layout, visual design, responsive, animations |
| Behavior | `src/js/main.js` | DOM interactions, scroll effects, API calls |
| Images | `assets/img/originals/` | Source images → optimized via npm script |
| Build | `_scripts/` | Automation tools, not production code |

## CSS conventions

```css
:root {
  --color-primary: #FF1F1F;   /* main brand color */
  --color-text: #1a1a1a;
  --color-bg: #ffffff;
  --spacing-sm: 1rem;
  --spacing-md: 2rem;
  --spacing-lg: 5rem;
}

/* BEM: .block__element--modifier */
/* Mobile-first: base → 768px → 1024px → 1440px */
```

## JS conventions

```js
// Guard clause + IntersectionObserver pattern
function initModuleName() {
  const el = document.querySelector('.element');
  if (!el) return;
  // ...
}
document.addEventListener('DOMContentLoaded', initModuleName);
```

## Rules

- Edit source files only — never `.min.*` files
- All colors/spacing: `:root` variables
- BEM class naming
- Images: always through `assets/img/originals/` → optimize pipeline
