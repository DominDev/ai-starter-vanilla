---
name: vanilla-architecture
description: Project architecture for Vanilla HTML/CSS/JS projects — directory structure, build pipeline, file responsibilities, multi-file patterns. Activates when working on project structure, imports, or file organization.
---

# Vanilla Project Architecture

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
│   │   ├── originals/      ← source images (place here)
│   │   └── optimized/      ← WebP/AVIF output (auto-generated)
│   ├── vid/
│   │   ├── originals/      ← source video
│   │   └── optimized/      ← WebM/MP4 output (auto-generated)
│   └── fonts/              ← web fonts (woff2)
├── _scripts/               ← build tools (not production)
│   ├── watch.js            ← central file watcher
│   ├── minify-css.js       ← CSS minification (Terser)
│   ├── minify-js.js        ← JS minification (Terser + source maps)
│   ├── optimize-images.js  ← image conversion (Sharp → WebP/AVIF, 400/800/1200/1600px)
│   └── optimize-video.js   ← video encoding (FFmpeg → WebM/MP4)
├── _docs/                  ← documentation, audit reports
├── package.json
└── .gitignore
```

## Build pipeline

```bash
npm run watch           # all watchers simultaneously (VSCode Ctrl+Shift+B)
npm run minify:css      # src/css/*.css → *.min.css
npm run minify:js       # src/js/*.js → *.min.js + source maps
npm run optimize:images # originals/ → optimized/ (4 sizes × 3 formats)
npm run optimize:video  # originals/ → optimized/ (WebM VP9 + MP4 H.264)
```

## Layer responsibilities

| Layer | File | Responsibility |
|-------|------|----------------|
| Structure | `index.html` | Semantic markup, sections, forms, meta |
| Styles | `src/css/style.css` | Layout, visual design, responsive, animations |
| Behavior | `src/js/main.js` | DOM interactions, scroll effects, API calls |
| Images | `assets/img/originals/` | Source → auto-optimized to WebP/AVIF |
| Build | `_scripts/` | Automation, not production code |

## Multi-file CSS pattern (when CSS grows)

```
src/css/
├── base.css        ← :root vars, reset, typography
├── layout.css      ← grid, header, footer, nav
├── hero.css        ← hero section
├── sections.css    ← content sections
└── style.css       ← @import all above (entry point for minifier)
```

## Multi-file JS pattern (when JS grows)

```
src/js/
├── utils.js        ← helper functions
├── animations.js   ← IntersectionObserver, scroll effects
├── nav.js          ← mobile menu, sticky nav
├── form.js         ← form validation, submission
└── main.js         ← imports and initializes all modules
```

## HTML loading pattern

```html
<!-- In <head> -->
<link rel="stylesheet" href="src/css/style.min.css">

<!-- Before </body> or with defer -->
<script src="src/js/main.min.js" defer></script>
```
