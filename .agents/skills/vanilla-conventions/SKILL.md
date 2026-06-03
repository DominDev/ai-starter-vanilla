---
name: vanilla-conventions
description: Coding conventions for Vanilla HTML/CSS/JS projects. Activates automatically when creating or modifying HTML, CSS, or JavaScript. Provides correct patterns without reading existing files.
---

# Vanilla JS Project Conventions

## HTML

```html
<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Page Title</title>
  <link rel="stylesheet" href="src/css/style.min.css">
</head>
<body>
  <header>...</header>
  <main>
    <section id="hero" class="hero">...</section>
  </main>
  <footer>...</footer>
  <script src="src/js/main.min.js" defer></script>
</body>
</html>
```

Rules:
- One `<h1>` per page/view
- Scripts: `defer` attribute always
- ARIA landmarks: `header`, `main`, `nav`, `footer`, `section`
- Images: always `alt` attribute; decorative → `alt=""` + `aria-hidden="true"`

## CSS

```css
/* Design system via :root */
:root {
  --color-primary: #FF1F1F;
  --color-text: #1a1a1a;
  --color-bg: #ffffff;
  --spacing-sm: 1rem;
  --spacing-md: 2rem;
  --spacing-lg: 5rem;
}

/* BEM: block__element--modifier */
.hero { }
.hero__title { }
.hero__title--large { }

/* Mobile-first responsive */
.component { /* base (mobile) */ }
@media (min-width: 768px)  { .component { /* tablet  */ } }
@media (min-width: 1024px) { .component { /* desktop */ } }
@media (min-width: 1440px) { .component { /* wide    */ } }

/* Reduced motion */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

Rules:
- All colors/spacing/fonts: `:root` CSS variables (no hardcoded values)
- Naming: BEM (`.block__element--modifier`)
- No Tailwind, no Bootstrap (unless explicitly requested)

## JavaScript

```js
// Module pattern — init on DOMContentLoaded
function initModuleName() {
  const element = document.querySelector('.element');
  if (!element) return; // guard clause

  // IntersectionObserver for scroll reveal
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('is-visible');
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1 });

  observer.observe(element);
}

document.addEventListener('DOMContentLoaded', () => {
  initModuleName();
});
```

Rules:
- ES2020+ syntax (const/let, arrow functions, optional chaining `?.`, nullish `??`)
- No framework — direct DOM APIs
- Guard clauses: always check element exists before using
- IntersectionObserver for scroll animations (never scroll event listeners)
- Hamburger menu: toggle `.is-open` class, manage `aria-expanded`

## Build output

- `src/css/style.css` → auto-minified to `src/css/style.min.css`
- `src/js/main.js` → auto-minified to `src/js/main.min.js`
- Edit source files only. Never edit `.min.*` files.
