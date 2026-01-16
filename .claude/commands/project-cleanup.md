---
description: Porządek w repo (struktura, nazewnictwo, duplikaty, szybkie usprawnienia). Raport do _docs/report-project-cleanup.md.
argument-hint: [repo]
allowed-tools: Read, Grep, Glob, Write, Edit, Bash
---

Wykonaj przegląd repo dla: $ARGUMENTS

Cel: ułatwić utrzymanie bez przepisywania projektu.

Sprawdź:
- Struktura katalogów (src/assets/styles/scripts itp.) i czy jest czytelna.
- Nazewnictwo plików i klas (spójność, kebab-case itp.).
- Duplikaty (np. podobne komponenty/sekcje).
- Martwe pliki (heurystycznie) i jak zweryfikować, że można je usunąć.
- Podstawowe metadane: README, _docs, spis komend, checklisty.

Wynik:
1) Executive summary
2) Must / Should / Could (priorytety porządków)
3) Proponowana docelowa struktura (minimalna, bez rewolucji)
4) Checklista wdrożeniowa

Na końcu:
- zapisz raport do `_docs/report-project-cleanup.md`
- w odpowiedzi pokaż tylko streszczenie + listę „Must”
