# Instrukcja przenoszenia systemu budowania (The Gemini Build System)

Ten dokument opisuje, jak przenieść i skonfigurować zautomatyzowany system minifikacji i optymalizacji (Watch, CSS, JS, Images, Video) do nowego projektu.

## 1. Wymagane pliki i foldery

Skopiuj następujące katalogi z tego projektu do **root** nowego projektu:

1.  📂 **`_scripts/`**
    *   Zawiera całą logikę: `watch.js`, `minify-css.js`, `minify-js.js`, `optimize-images.js`, `optimize-video.js`.
2.  📂 **`.vscode/`**
    *   Zawiera `tasks.json` (integracja skrótu Ctrl+Shift+B z ikoną 👁️).

## 2. Konfiguracja `package.json`

W nowym projekcie otwórz `package.json` i upewnij się, że zawiera poniższe wpisy.

### Sekcja `scripts`
Dodaj lub nadpisz te komendy, aby umożliwić uruchamianie narzędzi:

```json
"scripts": {
  "watch": "node _scripts/watch.js",
  "minify:css": "node _scripts/minify-css.js",
  "minify:js": "node _scripts/minify-js.js",
  "optimize:images": "node _scripts/optimize-images.js"
}
```

### Sekcja `devDependencies`
Dodaj te biblioteki, aby narzędzia działały (Sharp do obrazów, Terser do JS, FFmpeg do wideo):

```json
"devDependencies": {
  "ffmpeg-static": "^5.2.0",
  "sharp": "^0.33.2",
  "terser": "^5.27.0"
}
```

> **Wskazówka:** Jeśli `package.json` nie istnieje w nowym projekcie, uruchom najpierw `npm init -y`.

## 3. Instalacja

Po zaktualizowaniu `package.json` uruchom w terminalu:

```bash
npm install
```

## 4. Konwencja struktury katalogów

System domyślnie oczekuje następującej struktury. Jeśli nowy projekt ma inną, należy dostosować ścieżki w plikach w `_scripts/`.

```text
root/
├── src/
│   ├── css/          <-- Pliki źródłowe CSS (np. style.css)
│   └── js/           <-- Pliki źródłowe JS (np. main.js)
└── assets/
    ├── img/
    │   └── originals/  <-- Tutaj wrzucasz obrazy (JPG, PNG)
    └── vid/
        └── originals/  <-- Tutaj wrzucasz wideo (MP4, MOV)
```

System automatycznie wygeneruje:
*   `*.min.css` w `src/css/`
*   `*.min.js` i `*.map` w `src/js/`
*   Zoptymalizowane obrazy w `assets/img/optimized/` (zachowując strukturę podkatalogów)
*   Zoptymalizowane wideo w `assets/vid/optimized/`

## 5. Dostosowanie konfiguracji plików

Domyślnie minifikatory przetwarzają konkretne nazwy plików. Sprawdź i edytuj te listy w nowym projekcie:

### `_scripts/minify-css.js`
Edytuj tablicę `FILES_TO_MINIFY` na początku pliku:
```javascript
const FILES_TO_MINIFY = [
  { input: 'src/css/style.css', output: 'src/css/style.min.css' }
  // Dodaj inne pliki CSS jeśli istnieją
];
```

### `_scripts/minify-js.js`
Edytuj tablicę `FILES_TO_MINIFY`:
```javascript
const FILES_TO_MINIFY = [
  { input: 'src/js/main.js', output: 'src/js/main.min.js' },
  // Usuń lub dodaj inne pliki (np. config.js, sliders.js)
];
```

## 6. Uruchomienie

Aby rozpocząć pracę w trybie deweloperskim (nasłuchiwanie zmian):

1.  Otwórz **Command Palette** (Ctrl+Shift+P) lub wciśnij **Ctrl+Shift+B**.
2.  Wybierz zadanie: **`👀 Watch: Monitoruj zmiany (CSS/JS/Img/Vid)`**.

Alternatywnie z terminala: `npm run watch`.
