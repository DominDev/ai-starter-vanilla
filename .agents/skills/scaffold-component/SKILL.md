---
name: scaffold-component
description: Scaffolds a new section or module for Vanilla HTML/CSS/JS — HTML markup, CSS styles, optional JS initialization. Use when asked to create a new section, component, or UI module.
---

# Scaffold Section/Module (Vanilla)

## HTML template

```html
<section id="section-name" class="section-name" aria-labelledby="section-name-heading">
  <div class="section-name__container">
    <h2 id="section-name-heading" class="section-name__title">Section Title</h2>
    <!-- content -->
  </div>
</section>
```

## CSS template

Add to `src/css/style.css`:

```css
/* ========================================
   Section Name
   ======================================== */

.section-name {
  padding: var(--spacing-lg) 0;
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

@media (min-width: 768px) { }
@media (min-width: 1024px) { }
```

## JS template (if interaction needed)

Add to `src/js/main.js`:

```js
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
- After scaffolding: `npm run minify:css && npm run minify:js`
