---
description: Podstawy bezpieczeństwa frontendu (nagłówki, linki zewnętrzne, embed, CSP - jeśli dotyczy). Raport do _docs/report-security-basics.md.
argument-hint: [url | repo | oba]
allowed-tools: WebSearch, WebFetch, Read, Grep, Glob, Write, Edit
---

Wykonaj przegląd podstaw bezpieczeństwa dla: $ARGUMENTS

Zakres:
- Linki zewnętrzne i target=_blank (noopener/noreferrer).
- Inline JS/CSS: ryzyka i czy da się ograniczyć.
- Embed’y (mapy, iframe): sandbox, allow, polityki.
- Sekrety w repo (heurystycznie): klucze, tokeny, identyfikatory.
- Jeśli masz wpływ na hosting: nagłówki (HSTS, X-Content-Type-Options, Referrer-Policy, Permissions-Policy).
- CSP: tylko jako opcja; wskaż bezpieczne minimum i ryzyko „zepsucia” strony.

Wynik:
1) Executive summary
2) Must / Should / Could
3) Checklista wdrożeniowa + kryteria akceptacji

Na końcu:
- zapisz raport do `_docs/report-security-basics.md`
- w odpowiedzi pokaż tylko streszczenie + listę „Must”
