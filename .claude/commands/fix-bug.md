---
name: fix-bug
description: Diagnoses and fixes bugs in Vanilla HTML/CSS/JS projects. Identifies the affected layer first, then reads only minimum files. Use when something is broken, looks wrong, or behaves unexpectedly.
---

# Fix Bug (Vanilla)

## Step 1 — Identify the layer

| Symptom | Start here |
|---------|-----------|
| Wrong text / copy | `index.html` or relevant HTML file |
| Visual / layout issue | `src/css/*.css` |
| Animation / transition broken | CSS `@keyframes`, `transition`, or JS IntersectionObserver |
| Form not working | `src/js/*.js` + HTML form markup |
| Mobile menu / nav issue | `src/js/*.js` (burger menu) + CSS |
| Build output wrong | Run `npm run minify:css` or `npm run minify:js` and check output |
| Image not loading | Check paths: `assets/img/originals/` vs `assets/img/optimized/` |
| Performance issue | Check render-blocking scripts, image sizes, lazy-load |

## Step 2 — Read minimum files

Read ONLY the suspected file. Use grep to pinpoint the issue. Do NOT read all CSS/JS files.

## Step 3 — Diagnose

State the root cause in 1-2 sentences. Show the problematic code.

## Step 4 — Fix

- Targeted edit — change only what is broken
- Do not refactor surrounding code
- Source files only: never edit `.min.css` or `.min.js` (auto-generated)

## Step 5 — Verify

Run `npm run minify:css` / `npm run minify:js` to confirm no build errors.
For visual issues: note what to check in the browser.

## File map

```
HTML structure   → index.html (or other .html files)
Source styles    → src/css/style.css (or specific module CSS)
Source JS        → src/js/main.js (or specific module JS)
Build output     → src/css/style.min.css, src/js/main.min.js (auto-generated)
Images           → assets/img/originals/ → assets/img/optimized/
Build scripts    → _scripts/minify-css.js, minify-js.js, optimize-images.js
```
