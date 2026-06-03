---
name: project-context
description: Loads the architecture cheat sheet for Vanilla HTML/CSS/JS projects — directory structure, build pipeline, layer responsibilities, CSS/JS conventions. Use at session start or when you need a full project overview.
---

# Project Context (Vanilla)

## Tech stack

HTML5 + CSS3 (`:root` variables, Grid/Flex, BEM) + Vanilla JS ES2020+.
Build: npm scripts. Watch: `node _scripts/watch.js` (Ctrl+Shift+B in VSCode).

## Directory structure

```
project/
├── index.html              ← entry point (or multiple .html files)
├── src/
│   ├── css/
│   │   ├── style.css       ← source (EDIT THIS)
│   │   └── style.min.css   ← auto-generated (DON'T EDIT)
│   └── js/
│       ├── main.js         ← source (EDIT THIS)
│       └── main.min.js     ← auto-generated (DON'T EDIT)
├── assets/
│   ├── img/originals/      ← place source images here
│   ├── img/optimized/      ← WebP/AVIF (auto-generated)
│   ├── vid/originals/
│   ├── vid/optimized/      ← WebM/MP4 (auto-generated)
│   └── fonts/
├── _scripts/               ← build tools (not production)
├── _docs/                  ← guides and audit reports
└── package.json
```

## Build commands

```bash
npm run watch           # all watchers (auto-rebuild on save)
npm run minify:css      # src/css/*.css → *.min.css
npm run minify:js       # src/js/*.js → *.min.js
npm run optimize:images # originals/ → optimized/ (WebP/AVIF)
npm run optimize:video  # originals/ → optimized/ (WebM/MP4)
```

## CSS conventions

```css
:root {
  --color-primary: #FF1F1F;
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
function initModule() {
  const el = document.querySelector('.element');
  if (!el) return; // guard clause
  // IntersectionObserver for scroll effects
}
document.addEventListener('DOMContentLoaded', initModule);
```

## Rules

- Edit source files only — never `.min.*`
- All colors/spacing via `:root` variables
- BEM class naming
- Images always through originals → optimize pipeline
