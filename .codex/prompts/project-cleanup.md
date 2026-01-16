---
name: project-cleanup
description: Przegląd porządków w repo (dead code/duplicates/structure). Raport do _docs/report-project-cleanup.md.
---

Wykonaj przegląd porządków w repo (project cleanup) dla projektu.

Zakres minimalny (sprawdź i udokumentuj):
- Dead code: unused files, functions, variables, CSS rules, imports.
- Duplicates: repeated code, copy-paste patterns, opportunities for DRY.
- File structure: logical organization, naming conventions, folder hierarchy.
- Dependencies: unused packages (package.json), outdated versions, security vulnerabilities.
- Comments: outdated, commented-out code, TODO/FIXME tracking.
- Git: large files in history, .gitignore gaps, untracked sensitive files.
- Documentation: outdated README, missing docs, inline comments quality.
- Build artifacts: committed build files, temp files, cache in repo.
- Naming: inconsistent naming, abbreviations, meaningful names.
- Config files: duplicates, environment-specific configs, secrets exposure.

Wynik (format obowiązkowy):
1) Executive summary (5–10 punktów: największe problemy + wpływ na maintainability/security)
2) Lista problemów Must / Should / Could + priorytet + cleanup effort
3) Checklista wdrożeniowa (konkretne taski + bezpieczeństwo/backup przed usunięciem)
4) Konkretna lista plików do usunięcia/refactoringu + uzasadnienie

Na końcu:
- zapisz pełny raport do `_docs/report-project-cleanup.md`
- w odpowiedzi pokaż tylko streszczenie + listę „Must"
