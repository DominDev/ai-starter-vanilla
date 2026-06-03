---
name: implement-feature
description: Tiered feature implementation for Vanilla HTML/CSS/JS — scales questions to task complexity.
---

# Implement Feature (Vanilla)

Opis: {{args}}

**Małe** (1-2 pliki): 0-1 pytań. **Średnie** (nowa sekcja): 2-3 pytania. **Duże** (nowa strona): 4-6 pytań. Podaj klasyfikację.

Zapytaj o: która sekcja, jakie treści, styl animacji, mobile.

Krótki plan → czekaj na OK → implementuj:
- HTML: semantyczny, BEM, ARIA → `index.html`
- CSS: `:root` zmienne, BEM, mobile-first → `src/css/style.css`
- JS: `DOMContentLoaded`, IntersectionObserver → `src/js/main.js`

Weryfikuj: `npm run minify:css && npm run minify:js`.
