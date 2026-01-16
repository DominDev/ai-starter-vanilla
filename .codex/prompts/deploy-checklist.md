---
name: deploy-checklist
description: Checklist przed wdrożeniem/publikacją (SEO/UX/404/OG/cache). Raport do _docs/checklist-deploy.md.
---

Przygotuj checklistę przed publikacją dla projektu/strony.

Uwzględnij:
- SEO: title/description, canonical, robots/sitemap (jeśli dotyczy), OG/Twitter cards.
- UX: działające CTA, formularze, walidacje, stany błędów, 404/redirecty.
- Performance: obrazy, fonty, render-blocking, cache headers, CDN.
- A11Y: focus states, ARIA dla kluczowych elementów, kontrast (ryzyka).
- Security: HTTPS, CSP, headers (X-Frame-Options, X-Content-Type-Options), secrets removed.
- Prawne: polityka prywatności/cookies (jeśli dotyczy), GDPR/RODO compliance.
- Content: typos, broken links, placeholder content removed, copyright year.
- Monitoring minimum: jak szybko wykryć, że strona „padła" (np. prosty uptime check).
- Analytics: tracking scripts, GDPR-compliant consent, goals/events setup.
- Mobile: viewport meta, responsive testing, touch targets, mobile menu.

Wynik (format obowiązkowy):
1) Lista kontrolna (checkboxy z kategoriami)
2) „Stop-ship" — co blokuje publikację (must-fix przed go-live)
3) Jak zweryfikować każdy punkt (gdzie kliknąć / co sprawdzić / jakie narzędzie użyć)
4) Post-deploy checklist (co sprawdzić zaraz po publikacji)

Na końcu:
- zapisz checklistę do `_docs/checklist-deploy.md`
- w odpowiedzi pokaż tylko najważniejsze „Stop-ship" issues
