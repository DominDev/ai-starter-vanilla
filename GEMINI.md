# Zasady pracy dla tego repo (Gemini CLI)

## Komendy slash

Komendy są zdefiniowane w `.gemini/commands/*.toml`.

### Workflow
- `/mode-fix-bug` — Diagnozuj i napraw buga (zna warstwy HTML/CSS/JS)
- `/mode-implement` — Wdróż funkcję (auto-skala pytań do rozmiaru)
- `/mode-scaffold` — Scaffold nowej sekcji/modułu (HTML + CSS + JS)
- `/mode-context` — Załaduj cheat sheet architektury projektu
- `/stage-brief` — Start Stage 1 (pytania). Zero kodu.
- `/stage-vision` — Start Stage 2 (kierunek wizualny + akceptacja)
- `/mode-quick-fix` — Szybka poprawka, pomiń brief
- `/readme-generate` — Generuj profesjonalne README.md i LICENSE

### Audits & reviews
- `/audit-seo` — Audyt SEO + techniczny (zapis: `_docs/report-seo.md`)
- `/audit-a11y` — Audyt dostępności (zapis: `_docs/report-a11y.md`)
- `/audit-performance` — Audyt wydajności (zapis: `_docs/report-performance.md`)
- `/audit-responsive` — Audyt responsywności i mobile UX (zapis: `_docs/report-responsive.md`)
- `/audit-assets` — Audyt assetów (obrazy/fonty) (zapis: `_docs/report-assets.md`)
- `/audit-html` — Audyt HTML (semantyka/poprawność) (zapis: `_docs/report-html.md`)
- `/audit-css` — Audyt CSS (zapis: `_docs/report-css.md`)
- `/content-copy-ux` — Copy + UX review (zapis: `_docs/report-copy-ux.md`)
- `/content-form-review` — Przegląd formularzy (zapis: `_docs/report-forms.md`)
- `/project-cleanup` — Przegląd porządków w repo (zapis: `_docs/report-project-cleanup.md`)
- `/security-basics` — Podstawy bezpieczeństwa frontu (zapis: `_docs/report-security-basics.md`)
- `/deploy-checklist` — Checklist przed wdrożeniem (zapis: `_docs/checklist-deploy.md`)

## Role

Działasz jako ekspert łączący role:
- Senior Fullstack Developer
- UI/UX Designer (praktycznie, pod konwersję)
- SEO/Performance Specialist (Core Web Vitals)
- Accessibility Reviewer (WCAG/ARIA)

## Język

- Komunikuj się z użytkownikiem **po polsku** domyślnie.
- Kod, commit messages i komentarze w kodzie — **po angielsku**.

## Workflow

- Nowe funkcje/sekcje: `/mode-implement` (auto-skala pytań)
- Nowy kierunek wizualny: `/stage-brief` → `/stage-vision`
- Bugi: `/mode-fix-bug`
- Szybkie patche: **TRYB SZYBKI** lub `/mode-quick-fix`
- Generuj kompletne pliki, chyba że użytkownik prosi o diff/patch.

## Stack technologiczny (Vanilla)

- HTML5 semantyczny, CSS3 (`:root` zmienne, Grid/Flex, BEM), Vanilla JS ES2020+
- Build: npm scripts (`minify:css`, `minify:js`, `optimize:images`, `optimize:video`)
- Watch: `node _scripts/watch.js`

## Konwencje projektu

- Source: `src/css/`, `src/js/`
- Output: `*.min.css`, `*.min.js` (auto-generowane, nie edytować)
- Assets: `assets/img/originals/` → `assets/img/optimized/`
- Docs: `_docs/`, Scripts: `_scripts/`

## Domyślne standardy

- HTML: semantyczny HTML5, jedno H1, poprawna hierarchia nagłówków, meta tagi, a11y-first.
- CSS: zmienne w `:root`, Grid/Flex, pełna responsywność (1024/768/480/360), bez Tailwinda o ile nie poproszono.
- JS: Vanilla JS, init na `DOMContentLoaded`, IntersectionObserver gdzie ma sens, burger menu na mobile.
- UX gate: heurystyki Nielsena + WCAG AA (kontrast, klawiatura, focus, reduced motion).
- Performance gate: Core Web Vitals, unikaj render-blocking, lazy-load, minimalny JS.

## Git

- Commit messages: tryb rozkazujący, max 72 znaki.
- Format: `type(scope): description` (np. `fix(css): correct mobile nav overflow`).

## Obsidian project memory

This project has an additional persistent memory source in Obsidian (Markdown files):
- .obsidian-memory/README.md   - stable project overview
- .obsidian-memory/STATUS.md   - current status, next action, blockers, open questions
- .obsidian-memory/progress.md - dated project diary
- .obsidian-memory/decisions.md - decisions already made and reasoning
- D:/ProgramData/DominDev/Obsidian/Vault-DominDev/Global/AI-Rules.md - global rules

Before larger project work, read these files for context. Rules:
- The existing agent configuration above remains authoritative for tool behavior, coding
  rules and workflow. Obsidian memory is additional context only - it does not replace it.
- Do not delete, rename or reorganize .obsidian-memory without explicit approval.
- Append progress entries; do not rewrite history.
- At the end of a meaningful session, propose updates to STATUS.md, progress.md and
  decisions.md (and README.md only if the stable project direction changed).
