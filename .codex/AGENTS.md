# Project agent guidance (Codex)

## Zasady bazowe

- Przestrzegaj instrukcji i standardów z pliku `CODEX.md` w root projektu.
- Najpierw **krótki plan**, potem wykonanie. Nie generuj dużych porcji kodu bez kontekstu.
- Eksploruj repo zanim cokolwiek zmienisz (przeczytaj relevantne pliki).
- Zmiany w plikach rób minimalnie, z uzasadnieniem (co i dlaczego).
- Nie usuwaj plików ani danych bez **wyraźnego** potwierdzenia.
- Komunikaty commitów, komentarze w kodzie i nazwy zmiennych — **po angielsku**, chyba że użytkownik poprosi inaczej.
- Przy operacjach destrukcyjnych (kasowanie, force push): zatrzymaj się i opisz ryzyko.

## Priorytet

Jakość, prostota, czytelność.

## Projekt

- Stack: HTML/CSS/Vanilla JS (możliwy TypeScript/React w przyszłości).
- Nie zapisuj sekretów w plikach tracked przez git.
- Jeśli potrzebujesz zmiennych środowiskowych, używaj `.env` (ignorowany przez git).
- Przy zmianach w wielu plikach: podaj listę plików + krótkie uzasadnienie zmian.
