# Przewodnik Optymalizacji Mediów

Ten dokument opisuje procesy i narzędzia służące do automatycznej optymalizacji obrazów i wideo w projekcie.

---

## 1. Optymalizacja Obrazów

Skrypt `_scripts/optimize-images.js` wykorzystuje bibliotekę **Sharp** do generowania responsywnych wariantów zdjęć.

### Jak używać:
1. Umieść oryginalne zdjęcia (np. `photo.jpg`) w jednym folderze: **`assets/img/originals/`**.
2. Uruchom komendę:
   ```bash
   npm run optimize:images
   ```
3. Zoptymalizowane pliki (AVIF, WebP, JPG w 4 rozmiarach) pojawią się w folderze: **`assets/img/optimized/`**.

### Użycie w HTML:
Zawsze używaj tagu `<picture>` dla najlepszej wydajności, wskazując ścieżkę do `optimized`:

```html
<picture>
    <source type="image/avif" 
            srcset="assets/img/optimized/photo-400.avif 400w, 
                    assets/img/optimized/photo-800.avif 800w, 
                    assets/img/optimized/photo-1200.avif 1200w"
            sizes="(max-width: 768px) 100vw, 50vw">
    <source type="image/webp" 
            srcset="assets/img/optimized/photo-400.webp 400w, 
                    assets/img/optimized/photo-800.webp 800w, 
                    assets/img/optimized/photo-1200.webp 1200w"
            sizes="(max-width: 768px) 100vw, 50vw">
    <img src="assets/img/optimized/photo-800.jpg" 
         alt="Opis zdjęcia" 
         loading="lazy" 
         width="800" height="600">
</picture>
```

---

## 2. Optymalizacja Wideo

Skrypt `_scripts/optimize-video.js` wykorzystuje **ffmpeg** (przez `ffmpeg-static`) do konwersji wideo na lekkie formaty webowe.

### Jak używać:
1. Umieść oryginalne wideo (np. `video.mp4`) w folderze: **`assets/video/originals/`**.
2. Uruchom komendę:
   ```bash
   npm run optimize:video
   ```
3. Zoptymalizowane pliki (`.webm`, `.mp4` zoptymalizowany) pojawią się w folderze: **`assets/video/optimized/`**.

### Co robi skrypt?
- Generuje format **WebM (VP9)**: Lżejszy o ~30-50% od MP4, wspierany przez nowoczesne przeglądarki.
- Generuje format **MP4 (H.264)**: Z flagą `+faststart` (moov atom na początku) dla natychmiastowego streamingu i parametrami `profile: main` dla kompatybilności.
- Usuwa ścieżkę audio (domyślnie, można zmienić w konfigu skryptu), co drastycznie zmniejsza rozmiar plików tła.

### Użycie w HTML (Background Video):

```html
<video autoplay muted loop playsinline poster="assets/img/optimized/video-poster.webp">
    <source src="assets/video/optimized/video.webm" type="video/webm">
    <source src="assets/video/optimized/video.mp4" type="video/mp4">
</video>
```
**Kolejność ma znaczenie!** Przeglądarka pobierze pierwszy wspierany format (zazwyczaj lżejszy WebM).

---

## 3. Komendy NPM

| Komenda | Opis |
|---------|------|
| `npm run optimize:images` | Przetwarza obrazy z `assets/img/originals` -> `assets/img/optimized` |
| `npm run optimize:video` | Przetwarza wideo z `assets/video/originals` -> `assets/video/optimized` |
| `npm run build` | Uruchamia pełną optymalizację (obrazy + wideo + minifikacja kodu) |