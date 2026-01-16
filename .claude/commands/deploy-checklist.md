---
description: Checklista przed wdrożeniem/publikacją (SEO/UX/404/OG/cache). Raport do _docs/checklist-deploy.md.
argument-hint: [url | repo | oba]
allowed-tools: WebSearch, WebFetch, Read, Grep, Glob, Write, Edit
---

Przygotuj checklistę przed publikacją dla: $ARGUMENTS

Uwzględnij:
- SEO: title/description, canonical, robots/sitemap (jeśli dotyczy), OG/Twitter cards.
- UX: działające CTA, formularze, walidacje, stany błędów, 404/redirecty.
- Performance: obrazy, fonty, render-blocking, cache.
- A11Y: focus, aria dla kluczowych elementów, kontrast (ryzyka).
- Prawne: polityka prywatności/cookies (jeśli dotyczy).
- Monitoring minimum: jak szybko wykryć, że strona „padła” (np. prosty uptime check).

Wynik:
1) Lista kontrolna (checkboxy)
2) „Stop-ship” – co blokuje publikację
3) Jak zweryfikować (gdzie kliknąć / co sprawdzić)

Na końcu:
- zapisz checklistę do `_docs/checklist-deploy.md`
- w odpowiedzi pokaż tylko najważniejsze „Stop-ship”
