# Automatyzacja projektu: Watch & Minify

Ten dokument opisuje system automatycznej minifikacji zasobów (CSS i JS) wdrożony w projekcie. Dzięki niemu praca na plikach źródłowych jest wygodna, a strona zawsze ładuje zoptymalizowane wersje produkcyjne.

## 1. Jak to działa?

Strona internetowa (`index.html`) jest skonfigurowana w trybie produkcyjnym, co oznacza, że ładuje skompresowane pliki:
- `src/css/style.min.css` (zamiast `style.css`)
- `src/js/main.min.js` (zamiast `main.js`)
- `src/js/privacy-content.min.js` (zamiast `privacy-content.js`)

Abyś mógł wygodnie edytować kod źródłowy, a przeglądarka widziała zmiany, wdrożono **system "Watcher"**.

**Watcher** to proces działający w tle, który:
1. Obserwuje foldery `src/css` i `src/js`.
2. Wykrywa moment zapisu pliku (`Ctrl + S`).
3. Automatycznie uruchamia odpowiednie skrypty minifikujące.
4. Generuje/nadpisuje pliki `.min.*` w ułamku sekundy.

---

## 2. Jak uruchomić Watchera?

Korzystając z Visual Studio Code, masz gotowe zadanie systemowe.

### Sposób A: Skrót klawiszowy (Rekomendowany)
1. Będąc w VS Code, naciśnij skrót: **`Ctrl + Shift + B`** (jest to domyślny skrót dla "Build Task").
2. Zadanie **"🚀 Watch & Minify Assets"** uruchomi się automatycznie w tle.
3. To wszystko! Możesz teraz edytować pliki i odświeżać przeglądarkę.

### Sposób B: Menu VS Code
1. Wybierz z górnego menu: **Terminal** -> **Run Build Task...**
2. Wybierz z listy: **"🚀 Watch & Minify Assets"**.

### Sposób C: Terminal (Opcja awaryjna)
Jeśli nie korzystasz z VS Code lub wolisz terminal:
1. Otwórz terminal w folderze głównym projektu.
2. Wpisz komendę: `node _scripts/watch.js`

---

## 3. Struktura plików (Dla deweloperów)

### Skrypty pomocnicze (`_scripts/`)
| Plik | Funkcja |
|------|---------|
| `watch.js` | Główny sterownik. Monitoruje zmiany w plikach i deleguje zadania. |
| `minify-js.js` | Kompresuje pliki JavaScript używając `terser`. Konfiguracja plików wejściowych/wyjściowych znajduje się wewnątrz tego pliku. |
| `auto-minify-css.js` | Kompresuje pliki CSS (usuwa spacje, komentarze, optymalizuje składnię). |

### Konfiguracja VS Code (`.vscode/tasks.json`)
Definiuje zadanie "🚀 Watch & Minify Assets", które jest traktowane jako domyślny "Build task". Ustawienie `"presentation": { "reveal": "silent" }` sprawia, że terminal nie wyskakuje natrętnie przy każdej zmianie, a jedynie działa cicho w tle.

---

## 4. Rozwiązywanie problemów

**Q: Zmieniłem CSS, odświeżam stronę, ale nie widzę zmian.**
A: Sprawdź, czy Watcher jest uruchomiony. Jeśli nie, uruchom go (`Ctrl + Shift + B`). Jeśli jest uruchomiony, sprawdź panel Terminala w VS Code (zakładka "Tasks"), czy nie pojawił się błąd składni (Syntax Error) w Twoim kodzie, który zablokował minifikację.

**Q: Dodałem nowy plik JS, ale nie tworzy się jego wersja .min.**
A: Musisz dodać ten plik do konfiguracji w `_scripts/minify-js.js` (tablica `FILES_TO_MINIFY`), aby system wiedział, że ma go przetwarzać.

**Q: Chcę pracować bez minifikacji (tryb debugowania).**
A: Musisz ręcznie zmienić w `index.html` linki z `.min.css`/`.min.js` na `.css`/`.js`. Pamiętaj jednak, aby przed wrzuceniem na produkcję cofnąć te zmiany, aby strona ładowała się szybko.
