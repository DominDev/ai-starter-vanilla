# Project agent guidance (Codex)

## Zasady bazowe

- Przestrzegaj instrukcji i standardów z pliku `CODEX.md` w root projektu.
- Najpierw **krótki plan**, potem wykonanie. Nie generuj dużych porcji kodu bez kontekstu.
- Eksploruj repo zanim cokolwiek zmienisz (przeczytaj relevantne pliki).
- Zmiany w plikach rób minimalnie, z uzasadnieniem (co i dlaczego).
- Nie usuwaj plików ani danych bez **wyraźnego** potwierdzenia.
- Komunikaty commitów, komentarze w kodzie i nazwy zmiennych — **po angielsku**.
- Przy operacjach destrukcyjnych (kasowanie, force push): zatrzymaj się i opisz ryzyko.

## Priorytet

Jakość, prostota, czytelność.

## Stack

HTML5 + CSS3 (BEM, `:root` zmienne, Grid/Flex) + Vanilla JS ES2020+.
Build pipeline: npm scripts (minify:css, minify:js, optimize:images, optimize:video).

## Skills

Workflow skills dostępne przez komendę `/skills` w Codex TUI:
- `fix-bug` — diagnoza i naprawa bugów (warstwa HTML/CSS/JS)
- `implement-feature` — tiered workflow implementacji (auto-skala pytań)
- `scaffold-component` — scaffold nowej sekcji HTML + CSS + JS
- `project-context` — mapa architektury projektu

Auto-context skills (aktywowane automatycznie przez Codex na podstawie opisu):
- `vanilla-conventions` — konwencje HTML/CSS/JS dla tego projektu
- `vanilla-architecture` — struktura plików i pipeline buildowania
