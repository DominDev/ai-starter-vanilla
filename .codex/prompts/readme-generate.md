---
name: readme-generate
description: Generate professional README.md and LICENSE for the project (DominDev branding, tech stack, features, setup).
---

# Generate README.md + LICENSE (Vanilla)

**Note:** Codex slash commands use `.agents/skills/` — this file documents the workflow.

## Analysis

1. Scan: glob HTML/CSS/JS/JSON, read `package.json`
2. Detect: HTML5/CSS3/Vanilla JS stack, features, performance, a11y
3. Extract project name and metadata

## README Sections

1. Hero — badges, quick stats
2. Preview — desktop/mobile screenshots
3. About & Features — feature table, comparison matrix (Vanilla vs frameworks)
4. Tech Stack — HTML5/CSS3/JS/npm badges, stack comparison
5. Performance — Lighthouse, Core Web Vitals ASCII table
6. Accessibility — WCAG table
7. Getting Started — quick start, project structure
8. Lessons Learned
9. Deployment — Netlify/Vercel/GitHub Pages
10. Roadmap
11. License — dual MIT (code) + ARR (assets)
12. Author — DominDev branding

## Output

Backup README.md → README.backup.md. Write README.md + LICENSE.

## Rules

- Real project data only
- Confident, bold tone
- DominDev brand: #FF1F1F, `for-the-badge`, "Building digital experiences that convert."
- Year: 2026
