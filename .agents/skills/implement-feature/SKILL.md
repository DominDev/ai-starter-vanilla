---
name: implement-feature
description: Tiered feature implementation for Vanilla HTML/CSS/JS projects — scales questions to task complexity. Use when asked to add a new section, feature, animation, or interaction.
---

# Implement Feature (Vanilla)

## Step 1 — Classify task size (silently)

- **Small** (1-2 files, style tweak, new element): 0-1 questions → plan
- **Medium** (new section, interaction, form): 2-3 questions → plan
- **Large** (new page, major layout change, complex animation): 4-6 questions → plan

Tell the user the classification.

## Step 2 — Ask only what you don't know

Focus on:
- Which page / section?
- Content to add (text, images, video)?
- Animation style (subtle / prominent)?
- Mobile behaviour?

## Step 3 — Short plan

List files to create/modify (max 1 line each). Wait for OK.

## Step 4 — Implement

- **HTML**: semantic HTML5, BEM class names, ARIA attributes → `index.html`
- **CSS**: `:root` variables, BEM, mobile-first → `src/css/style.css`
- **JS**: init on `DOMContentLoaded`, IntersectionObserver → `src/js/main.js`
- **Images**: place originals in `assets/img/originals/`, run `npm run optimize:images`

## Rules

- Edit source files only — never `.min.css` / `.min.js`
- Mobile-first CSS: base → 768px → 1024px → 1440px
- Verify: `npm run minify:css && npm run minify:js` after changes
- A11y: new sections need proper heading hierarchy, aria labels
