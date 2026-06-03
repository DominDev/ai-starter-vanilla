---
name: fix-bug
description: Diagnose and fix a bug in a Vanilla HTML/CSS/JS project. Identifies the correct layer, reads minimum files, targeted fix.
---

# Fix Bug (Vanilla)

Opis problemu: {{args}}

## Warstwa → plik

| Objaw | Zacznij tutaj |
|-------|---------------|
| Zły tekst | `index.html` |
| Layout / wizualny | `src/css/*.css` |
| Animacja / przejście | CSS lub JS IntersectionObserver |
| Formularz | `src/js/*.js` + HTML form |
| Menu mobilne | `src/js/*.js` + CSS |
| Błąd build | `npm run minify:css` / `npm run minify:js` |
| Obraz nie ładuje | `assets/img/originals/` vs `assets/img/optimized/` |

Czytaj TYLKO podejrzany plik. Podaj root cause w 1-2 zdaniach. Napraw minimalnie — tylko pliki źródłowe (nigdy `.min.*`). Weryfikuj: `npm run minify:css && npm run minify:js`.
