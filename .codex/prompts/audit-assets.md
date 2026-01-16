---
name: audit-assets
description: Audyt assetów (obrazy/fonty/ikony/media). Raport do _docs/report-assets.md.
---

Wykonaj audyt assetów (images, fonts, icons, media) dla projektu/strony.

Zakres minimalny (sprawdź i udokumentuj):
- Images: format (WebP/AVIF/JPEG/PNG), compression, dimensions vs display size, alt text.
- Responsive images: srcset/sizes, picture element, art direction.
- Icons: SVG vs icon fonts vs PNG, inline vs external, optimization (SVGO).
- Fonts: format (WOFF2), subsetting, preload, font-display, liczba variant/weights.
- Video: format (WebM/MP4), compression, poster image, lazy-load, autoplay policies.
- File naming: conventions, organization, duplicates.
- Accessibility: alt text, aria-label dla dekoracyjnych, meaningful filenames.
- Performance impact: total asset size, number of requests, blocking vs async.

Wynik (format obowiązkowy):
1) Executive summary (5–10 punktów: największe problemy + wpływ na performance/UX)
2) Lista problemów Must / Should / Could + priorytet + size/performance impact
3) Checklista wdrożeniowa (konkretne taski + kryteria akceptacji)
4) Jeśli to repo: wskazanie plików do optymalizacji + rekomendowane narzędzia/ustawienia

Na końcu:
- zapisz pełny raport do `_docs/report-assets.md`
- w odpowiedzi pokaż tylko streszczenie + listę „Must"
