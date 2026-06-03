---
name: scaffold-component
description: Scaffold a new section or module for Vanilla HTML/CSS/JS — HTML markup, CSS styles, optional JS.
---

# Scaffold Section/Module (Vanilla)

Opis: {{args}}

**HTML** (do `index.html`):
```html
<section id="section-name" class="section-name" aria-labelledby="section-name-heading">
  <div class="section-name__container">
    <h2 id="section-name-heading" class="section-name__title">Tytuł</h2>
  </div>
</section>
```

**CSS** (do `src/css/style.css`) — BEM, `:root` zmienne, mobile-first (base → 768px → 1024px).

**JS** (do `src/js/main.js`, tylko gdy interakcja) — guard clause + IntersectionObserver.

Po scaffoldingu: `npm run minify:css && npm run minify:js`.
