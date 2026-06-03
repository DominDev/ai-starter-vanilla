---
name: scaffold-component
description: Scaffolds a new section or module for a Vanilla HTML/CSS/JS project — HTML markup + CSS styles + optional JS initialization. Use when asked to create a new section, component, or UI module.
---

# Scaffold Section/Module (Vanilla)

## What to create

3 parts (HTML + CSS + optional JS). No separate files needed for small sections — add to existing files.

## HTML template

```html
<!-- Add to index.html in correct position -->
<section id="section-name" class="section-name" aria-labelledby="section-name-heading">
  <div class="section-name__container">
    <h2 id="section-name-heading" class="section-name__title">Section Title</h2>
    <p class="section-name__text">Description text.</p>
    <!-- content -->
  </div>
</section>
```

## CSS template

Add to `src/css/style.css` (or a new `src/css/section-name.css`):

```css
/* ========================================
   Section Name
   ======================================== */

.section-name {
  padding: var(--spacing-lg) 0;
  background: var(--color-bg);
}

.section-name__container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--spacing-md);
}

.section-name__title {
  font-size: clamp(1.75rem, 3vw, 2.5rem);
  color: var(--color-text);
  margin-bottom: var(--spacing-md);
}

/* Tablet */
@media (min-width: 768px) {
  .section-name { }
}

/* Desktop */
@media (min-width: 1024px) {
  .section-name { }
}
```

## JS template (if interaction needed)

Add to `src/js/main.js`:

```js
// Section Name — scroll reveal
function initSectionName() {
  const elements = document.querySelectorAll('.section-name__item');
  if (!elements.length) return;

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('is-visible');
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.15 });

  elements.forEach(el => observer.observe(el));
}

document.addEventListener('DOMContentLoaded', () => {
  initSectionName();
});
```

## Conventions

- BEM naming: `.block__element--modifier`
- All colors/spacing: `:root` CSS variables
- Mobile-first: base → `768px` → `1024px` → `1440px`
- Semantic HTML + ARIA for accessibility
- After scaffolding: run `npm run minify:css && npm run minify:js`
