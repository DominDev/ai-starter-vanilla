---
name: content-form-review
description: Przegląd formularzy (UX/walidacja/dostępność/conversion). Raport do _docs/report-forms.md.
---

Wykonaj przegląd formularzy dla projektu/strony.

Zakres minimalny (sprawdź i udokumentuj):
- Field organization: logical order, grouping (fieldset/legend), progress indicators.
- Labels: label/for association, clear text, required/optional indicators.
- Input types: email/tel/number/date, autocomplete attributes, input modes.
- Placeholders: nie zamiast label, helpful examples, nie kluczowe info.
- Validation: inline validation, helpful error messages, success feedback.
- Error handling: specific errors, gdzie i kiedy pokazać, jak poprawić.
- Accessibility: keyboard navigation, focus management, screen reader support.
- Submit button: clear label, disabled states, loading indicators, confirmation.
- Privacy: GDPR/RODO compliance, opt-in/out, links do polityki prywatności.
- Mobile UX: touch targets, keyboard types, autofill, screen space.

Wynik (format obowiązkowy):
1) Executive summary (5–10 punktów: największe problemy + wpływ na conversion/abandonment)
2) Lista problemów Must / Should / Could + priorytet + conversion/UX impact
3) Checklista wdrożeniowa (konkretne taski + kryteria akceptacji)
4) Jeśli to repo: wskazanie plików/fragmentów do zmiany + przykładowe poprawki (krótkie)

Na końcu:
- zapisz pełny raport do `_docs/report-forms.md`
- w odpowiedzi pokaż tylko streszczenie + listę „Must"
