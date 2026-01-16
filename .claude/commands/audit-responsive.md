---
description: Audyt responsywności i mobile UX. Raport do _docs/report-responsive.md.
argument-hint: [url | repo | oba]
allowed-tools: WebSearch, WebFetch, Read, Grep, Glob, Write, Edit
---

Wykonaj audyt responsywności dla: $ARGUMENTS

Sprawdź i opisz (minimum):
- Breakpointy: 360/375/390/414/768/1024/1440.
- Overflow (poziomy scroll), elementy wychodzące poza viewport.
- Touch targets: zbyt małe przyciski/linki, odstępy, przypadkowe kliknięcia.
- Sticky/fixed elementy: czy nie zasłaniają treści (CTA, scroll-to-top, menu).
- Typografia: skala fontów, długość linii, łamanie nagłówków i nieprzyjemne „wdowy/sieroty”.
- Nawigacja: menu mobile (otwieranie/zamykanie), focus, przewijanie tła.
- Media: obrazy/video skalowanie, aspect ratio, brak CLS (width/height).
- Formularze: typy pól (email/tel), autocomplete, czytelność błędów, zoom i viewport.

Wynik:
1) Executive summary
2) Problemy Must / Should / Could + gdzie występują (sekcja/komponent/plik)
3) Checklista wdrożeniowa + kryteria akceptacji

Na końcu:
- zapisz raport do `_docs/report-responsive.md`
- w odpowiedzi pokaż tylko streszczenie + listę „Must”
