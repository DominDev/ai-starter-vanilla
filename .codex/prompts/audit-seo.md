---
name: audit-seo
description: Audyt SEO + techniczny. Raport do _docs/report-seo.md.
---

Wykonaj audyt SEO + techniczny dla projektu/strony.

Zakres minimalny (sprawdź i udokumentuj):
- Title, description, canonical, OG/Twitter cards.
- Struktura nagłówków H1–H6 (jeden H1, hierarchia).
- Sitemap, robots.txt (jeśli dotyczy).
- Performance: Core Web Vitals (LCP/FID/CLS), render-blocking, lazy-load.
- Mobile-friendly: viewport, responsywność, touch targets.
- Semantyka: poprawne HTML5 tagi, landmarki.
- Linki wewnętrzne/zewnętrzne: rel, nofollow/noopener, broken links.
- Schema.org/structured data (jeśli dotyczy).
- HTTPS, redirecty 301/302, status codes.

Wynik (format obowiązkowy):
1) Executive summary (5–10 punktów: największe problemy + wpływ na ranking/UX)
2) Lista problemów Must / Should / Could + priorytet
3) Checklista wdrożeniowa (konkretne taski + kryteria akceptacji)
4) Jeśli to repo: wskazanie plików/fragmentów do zmiany + przykładowe poprawki (krótkie)

Na końcu:
- zapisz pełny raport do `_docs/report-seo.md`
- w odpowiedzi pokaż tylko streszczenie + listę „Must"
