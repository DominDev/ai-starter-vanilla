---
name: audit-html
description: Audyt HTML (semantyka/poprawność/struktura). Raport do _docs/report-html.md.
---

Wykonaj audyt HTML (semantyka, poprawność, struktura) dla projektu/strony.

Zakres minimalny (sprawdź i udokumentuj):
- Semantyka: poprawne użycie HTML5 (header/nav/main/article/section/aside/footer).
- Nagłówki: jeden H1, hierarchia H1-H6, brak przeskoków.
- Formularze: label/for, fieldset/legend, input types, autocomplete, required/optional.
- Linki i przyciski: <a> dla nawigacji, <button> dla akcji, href vs onclick.
- Listy: <ul>/<ol>/<dl> gdzie stosowne, nie div-soup.
- Tables: tylko dla danych tabelarycznych, <th>, scope, caption.
- Meta tags: lang, charset, viewport, title, description.
- Validation: błędy HTML (W3C validator), deprecated tags, niezamknięte tagi.
- Accessibility hooks: ARIA tylko gdy konieczne, nie nadpisuj semantyki.
- IDs: unikalne, sensowne naming, brak polskich znaków/spacji.

Wynik (format obowiązkowy):
1) Executive summary (5–10 punktów: największe problemy semantyczne/strukturalne)
2) Lista problemów Must / Should / Could + priorytet + impact na SEO/A11Y
3) Checklista wdrożeniowa (konkretne taski + kryteria akceptacji)
4) Jeśli to repo: wskazanie plików/fragmentów do zmiany + przykładowe poprawki (krótkie)

Na końcu:
- zapisz pełny raport do `_docs/report-html.md`
- w odpowiedzi pokaż tylko streszczenie + listę „Must"
