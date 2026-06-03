---
name: readme-generate
description: Generate professional README.md and LICENSE for the project (DominDev branding, tech stack, features, setup). Use when user asks to create or regenerate the project README.
argument-hint: [minimal | standard | detailed]
allowed-tools: Read, Grep, Glob, Write, Edit
---

# Generate README.md + LICENSE

## Analysis Phase

1. Scan project: glob HTML/CSS/JS/JSON, read `package.json`
2. Detect tech stack, features, performance hints, accessibility
3. Extract project name and metadata

## README Sections

Generate all sections in order using templates from reference files:

1. **Hero** — badges, quick stats table → see [readme-ref/sections.md](readme-ref/sections.md)
2. **Preview** — desktop/mobile screenshots
3. **About & Features** — feature table with impact, comparison matrix
4. **Tech Stack** — HTML5/CSS3/Vanilla JS badges, stack comparison table
5. **Performance** — Lighthouse scores, Core Web Vitals ASCII table
6. **Accessibility** — WCAG compliance table
7. **Getting Started** — prerequisites, quick start, project structure
8. **Lessons Learned** — what worked, challenges, retrospective
9. **Deployment** — hosting comparison, deploy commands
10. **Roadmap** — priority table with status
11. **License** — dual license table (MIT code / ARR assets)
12. **Author** — DominDev branding block → see [readme-ref/branding.md](readme-ref/branding.md)

## LICENSE

Generate dual MIT (code) + All Rights Reserved (assets) license. Template in [readme-ref/branding.md](readme-ref/branding.md).

## Output

1. Backup existing README.md to `README.backup.md`
2. Write `README.md` and `LICENSE` to project root
3. Show summary: detected stack, features, sections generated

## Rules

- Use actual project data, never fabricate metrics
- Confident, bold tone (Senior Developer level)
- Visual: emoji grids, comparison tables, ASCII boxes
- Replace `[YEAR]` with 2026
