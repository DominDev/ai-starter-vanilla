---
name: security-basics
description: Podstawy bezpieczeństwa frontu (XSS/CSRF/headers/secrets). Raport do _docs/report-security-basics.md.
---

Wykonaj przegląd podstaw bezpieczeństwa frontendowego dla projektu/strony.

Zakres minimalny (sprawdź i udokumentuj):
- XSS (Cross-Site Scripting): user input sanitization, innerHTML vs textContent, CSP headers.
- CSRF (Cross-Site Request Forgery): tokens, SameSite cookies, referer checking.
- Content Security Policy: CSP headers, inline scripts/styles, trusted sources.
- HTTPS: force HTTPS, mixed content, HSTS header.
- Secrets exposure: API keys in code, .env files in git, client-side secrets.
- Dependencies: known vulnerabilities (npm audit), outdated packages, supply chain.
- Headers: X-Content-Type-Options, X-Frame-Options, Referrer-Policy, Permissions-Policy.
- Input validation: client-side + server-side, type checking, length limits.
- Authentication: password storage (never client-side), session management, logout.
- Third-party scripts: tracking, analytics, CDN integrity (SRI), privacy implications.

Wynik (format obowiązkowy):
1) Executive summary (5–10 punktów: największe zagrożenia + potential impact)
2) Lista problemów Must / Should / Could + priorytet + severity (Critical/High/Medium/Low)
3) Checklista wdrożeniowa (konkretne taski + kryteria akceptacji)
4) Jeśli to repo: wskazanie plików/fragmentów do zmiany + przykładowe poprawki (krótkie)

Na końcu:
- zapisz pełny raport do `_docs/report-security-basics.md`
- w odpowiedzi pokaż tylko streszczenie + listę „Must" i „Critical"
