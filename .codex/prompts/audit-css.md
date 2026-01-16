---
name: audit-css
description: Audyt CSS (organizacja/naming/performance/best practices). Raport do _docs/report-css.md.
---

Wykonaj audyt CSS dla projektu/strony.

Zakres minimalny (sprawdź i udokumentuj):
- Organizacja: struktura plików, imports, logical sections, komentarze.
- Naming conventions: BEM/SMACSS/utility-classes, consistency, meaningful names.
- Variables: CSS custom properties (:root), naming, usage, theming.
- Selectors: specificity, depth, !important usage, avoid over-qualification.
- Responsive: mobile-first vs desktop-first, breakpoints, media queries organization.
- Layout: Grid/Flexbox usage, moderne vs legacy techniques, box-sizing.
- Performance: unused CSS, critical CSS, minification, bundle size.
- Browser support: vendor prefixes, fallbacks, feature queries (@supports).
- Accessibility: focus-visible, reduced-motion, high-contrast, color-only dependence.
- Maintainability: duplication, magic numbers, dead code, documentation.

Wynik (format obowiązkowy):
1) Executive summary (5–10 punktów: największe problemy + wpływ na maintainability/performance)
2) Lista problemów Must / Should / Could + priorytet + refactoring effort
3) Checklista wdrożeniowa (konkretne taski + kryteria akceptacji)
4) Jeśli to repo: wskazanie plików/fragmentów do zmiany + przykładowe poprawki (krótkie)

Na końcu:
- zapisz pełny raport do `_docs/report-css.md`
- w odpowiedzi pokaż tylko streszczenie + listę „Must"
