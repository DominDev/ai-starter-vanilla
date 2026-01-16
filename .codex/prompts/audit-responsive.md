---
name: audit-responsive
description: Audyt responsywności i mobile UX. Raport do _docs/report-responsive.md.
---

Wykonaj audyt responsywności i mobile UX dla projektu/strony.

Zakres minimalny (sprawdź i udokumentuj):
- Breakpointy: 1024px, 768px, 480px, 360px (sprawdź layout na każdym).
- Viewport: meta viewport, brak horizontal scroll, touch targets min 44x44px.
- Layout: Grid/Flexbox/Stack, brak fixed width w pikselach (używaj %, rem, vw).
- Typografia: fluid typography (clamp/vw), czytelność na mobile (min 16px body text).
- Navigation: burger menu na mobile, touch-friendly, keyboard accessible.
- Images/Media: responsive images (srcset/sizes), aspect-ratio, object-fit.
- Forms: touch-friendly inputs, odpowiednie keyboard types (tel/email/number), autocomplete.
- Interactive elements: hover states na desktop, tap states na mobile, no hover-only functionality.
- Orientacja: landscape/portrait (jeśli aplikacja tego wymaga).

Wynik (format obowiązkowy):
1) Executive summary (5–10 punktów: największe problemy UX na mobile + desktop)
2) Lista problemów Must / Should / Could + priorytet + device impact
3) Checklista wdrożeniowa (konkretne taski + kryteria akceptacji)
4) Jeśli to repo: wskazanie plików/selektorów/fragmentów do zmiany + przykładowe poprawki (krótkie)

Na końcu:
- zapisz pełny raport do `_docs/report-responsive.md`
- w odpowiedzi pokaż tylko streszczenie + listę „Must"
