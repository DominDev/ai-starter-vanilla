---
name: audit-performance
description: Audyt wydajności (Core Web Vitals/loading/optymalizacje). Raport do _docs/report-performance.md.
---

Wykonaj audyt wydajności dla projektu/strony.

Zakres minimalny (sprawdź i udokumentuj):
- Core Web Vitals: LCP, FID/INP, CLS (diagnostyka + przyczyny).
- Loading: render-blocking resources (CSS/JS), critical path, lazy-load obrazów/video.
- Images: format (WebP/AVIF), wymiary, compression, responsive images (srcset/sizes).
- Fonts: font-display, subsetting, preload, WOFF2.
- JS/CSS: minifikacja, tree-shaking, code splitting, bundle size.
- Caching: HTTP headers (Cache-Control, ETag), service workers (jeśli dotyczy).
- Network: HTTP/2, CDN, DNS prefetch/preconnect, liczba requestów.
- Third-party scripts: async/defer, impact na performance, alternatywy.

Wynik (format obowiązkowy):
1) Executive summary (5–10 punktów: największe bottlenecki + wpływ na UX/metryki)
2) Lista problemów Must / Should / Could + priorytet + szacowany impact
3) Checklista wdrożeniowa (konkretne taski + kryteria akceptacji)
4) Jeśli to repo: wskazanie plików/fragmentów do zmiany + przykładowe poprawki (krótkie)

Na końcu:
- zapisz pełny raport do `_docs/report-performance.md`
- w odpowiedzi pokaż tylko streszczenie + listę „Must"
