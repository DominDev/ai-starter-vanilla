---
description: Audyt CSS (konwencje, specyficzność, duplikaty, martwe style). Raport do _docs/report-css.md.
argument-hint: [repo | plik | oba]
allowed-tools: Read, Grep, Glob, Write, Edit
---

Wykonaj audyt CSS dla: $ARGUMENTS

Sprawdź:
- Konwencja (np. BEM) i spójność nazewnictwa klas.
- Duplikaty reguł, nadmierna specyficzność, !important (czy jest konieczne).
- Selekcje „zbyt szerokie” (np. .container a span ...) i ryzyko niechcianych efektów.
- Reset/normalize i czy nie psuje elementów formularzy.
- Media queries: spójność breakpointów i brak „patchy” dla pojedynczych urządzeń.
- Animacje: czy nie wymuszają layoutu (prefer transform/opacity).
- Podejrzenie martwych stylów (heurystycznie) i jak to zweryfikować.

Wynik:
1) Executive summary
2) Must / Should / Could + gdzie (plik/sekcja)
3) Checklista wdrożeniowa

Na końcu:
- zapisz raport do `_docs/report-css.md`
- w odpowiedzi pokaż tylko streszczenie + listę „Must”
