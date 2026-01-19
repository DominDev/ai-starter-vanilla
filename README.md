# AI Agents Starter Pack (Vanilla HTML/CSS/JS)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Author: DominDev](https://img.shields.io/badge/Author-DominDev-blue.svg)](https://github.com/DominDev)
[![Claude Code](https://img.shields.io/badge/AI-Claude_Code-orange.svg)](https://docs.anthropic.com/en/docs/claude-code)
[![Gemini CLI](https://img.shields.io/badge/AI-Gemini_CLI-4285F4.svg)](https://github.com/google-gemini/gemini-cli)
[![Codex CLI](https://img.shields.io/badge/AI-Codex_CLI-10a37f.svg)](https://www.npmjs.com/package/@openai/codex)

> A production-ready starter pack for vanilla HTML/CSS/JS websites with 3 preconfigured AI coding assistants. Skip the setup, start building.

## Why This Starter Pack?

- **3 AI Agents, 1 Workflow** - Claude Code, Gemini CLI, and Codex CLI all share identical slash commands
- **Mandatory Brief-First Approach** - Enforces proper requirements gathering before coding
- **15 Built-in Audits** - SEO, accessibility, performance, responsive design, security, and more
- **Media Optimization Pipeline** - Scripts for image/video compression ready to use
- **Professional Standards** - BEM CSS, semantic HTML5, WCAG AA compliance baked in

---

## What's Included

### AI Agent Configurations

| Agent | Config File | Commands | Settings |
|-------|-------------|----------|----------|
| **Claude Code CLI** | `CLAUDE.md` | `.claude/commands/*.md` | `.claude/settings.local.json` |
| **Gemini CLI** | `GEMINI.md` | `.gemini/commands/*.toml` | `.gemini/settings.json` |
| **Codex CLI** | `CODEX.md` | `.codex/prompts/*.md` | `.codex/config.toml` |

### Helper Scripts (`_scripts/`)

| Script | Purpose | Usage |
|--------|---------|-------|
| `watch.js` | CSS/JS file watcher with auto-minify | `node _scripts/watch.js` |
| `auto-minify-css.js` | CSS minification (one-time or watch) | `node _scripts/auto-minify-css.js` |
| `minify-js.js` | JavaScript minification (Terser) | `node _scripts/minify-js.js` |
| `optimize-images.js` | Image optimization (Sharp) - AVIF/WebP/JPG | `node _scripts/optimize-images.js` |
| `optimize-video.js` | Video optimization (FFmpeg) - WebM/MP4 | `node _scripts/optimize-video.js` |
| `snapshot_code.ps1` | Project code snapshot | PowerShell script |
| `snapshot_structure.ps1` | Directory structure snapshot | PowerShell script |
| `run-codex.ps1` | Codex CLI wrapper (sets CODEX_HOME) | `.\_scripts\run-codex.ps1` |

### Documentation (`_docs/`)

| Guide | Description |
|-------|-------------|
| `guide-automation.md` | Watch & minify workflow setup |
| `guide-media-optimization.md` | Image/video optimization pipeline |
| `guide-claude-mem.md` | Claude Memory plugin (persistent cross-session memory) |
| `notes-claude-mem.md` | Claude Memory quick reference |

### Project Configuration

| File | Purpose |
|------|---------|
| `.editorconfig` | Code formatting standards (UTF-8, LF, 2-space indent) |
| `.gitattributes` | Git line ending rules |
| `.gitignore` | Starter pack gitignore (AI configs committed) |
| `.gitignore.template` | User project gitignore (AI configs ignored) |

---

## Quick Start

### Prerequisites

- **Node.js 18+** (for helper scripts)
- At least one AI CLI installed (see Installation below)

### Installation

#### Claude Code CLI
```bash
# macOS/Linux
curl -fsSL https://claude.ai/install.sh | sh

# Or via npm
npm install -g @anthropic-ai/claude-code
```
[Full documentation](https://docs.anthropic.com/en/docs/claude-code)

#### Gemini CLI
```bash
npm install -g @google/gemini-cli
```
[Full documentation](https://github.com/google-gemini/gemini-cli)

#### Codex CLI
```bash
npm install -g @openai/codex
```
[Full documentation](https://www.npmjs.com/package/@openai/codex)

### Install Node Dependencies (for helper scripts)

```bash
npm init -y
npm install -D terser sharp ffmpeg-static
```

---

## Usage

### Claude Code CLI

```bash
# In project directory
claude
```

### Gemini CLI

```bash
# In project directory
gemini

# With optional system prompt override:
export GEMINI_SYSTEM_MD=1  # Linux/macOS
$env:GEMINI_SYSTEM_MD="1"  # Windows PowerShell
gemini
```

### Codex CLI

```powershell
# Recommended: Use the PowerShell wrapper (sets CODEX_HOME)
.\_scripts\run-codex.ps1

# Or directly (requires manual CODEX_HOME)
$env:CODEX_HOME=".codex"
codex
```

---

## Slash Commands Reference

All three agents share the same command set for consistency.

### Workflow Commands

| Command | Description |
|---------|-------------|
| `/stage-brief` | Start Stage 1: Ask 8-12 discovery questions (zero code) |
| `/stage-vision` | Start Stage 2: Propose visual direction (palette, typography, layout) |
| `/mode-quick-fix` | Quick fix mode: Skip brief, go straight to minimal fix |
| `/readme-generate` | Generate professional README.md + LICENSE.md (DominDev branding) |

### Audit Commands

| Command | Output | Description |
|---------|--------|-------------|
| `/audit-seo` | `_docs/report-seo.md` | SEO + technical audit |
| `/audit-a11y` | `_docs/report-a11y.md` | Accessibility (WCAG/ARIA/keyboard/focus) |
| `/audit-performance` | `_docs/report-performance.md` | Core Web Vitals + performance |
| `/audit-responsive` | `_docs/report-responsive.md` | Responsive design + mobile UX |
| `/audit-assets` | `_docs/report-assets.md` | Image/font optimization opportunities |
| `/audit-html` | `_docs/report-html.md` | HTML semantics + correctness |
| `/audit-css` | `_docs/report-css.md` | CSS conventions + best practices |

### Content & UX Commands

| Command | Output | Description |
|---------|--------|-------------|
| `/content-copy-ux` | `_docs/report-copy-ux.md` | Copy review + UX improvements |
| `/content-form-review` | `_docs/report-forms.md` | Form validation + accessibility |

### Maintenance Commands

| Command | Output | Description |
|---------|--------|-------------|
| `/project-cleanup` | `_docs/report-project-cleanup.md` | Repository organization review |
| `/security-basics` | `_docs/report-security-basics.md` | Frontend security baseline |
| `/deploy-checklist` | `_docs/checklist-deploy.md` | Pre-deployment verification |

---

## Configuration

### Claude Code CLI

Settings in `.claude/settings.local.json` provide broad permissions for trusted projects:
- Auto-approval for most operations
- File edit, bash, web fetch allowed
- Helper script execution permitted

### Gemini CLI

Use the `--approval-mode=yolo` flag for broad access:
```bash
gemini --approval-mode=yolo
```

### Codex CLI

Configuration in `.codex/config.toml`:
- `model = "gpt-5.2-codex"` - Recommended for ChatGPT account (use `gpt-4o` for OpenAI API)
- `approval_policy = "never"` - Auto-approval
- `sandbox_mode = "danger-full-access"` - Full filesystem access
- `model_reasoning_effort = "medium"` - Balanced reasoning/speed

**Available models:**
- ChatGPT account: `gpt-5.2-codex`, `gpt-5.1-codex-max`, `gpt-5.1-codex-mini`, `gpt-5.2`
- OpenAI API: `gpt-4o`, `gpt-4-turbo`, `gpt-3.5-turbo`

> **Warning:** All three agents are configured with broad permissions. Use only in trusted projects!

---

## Project Standards

All agents enforce the same development standards:

### HTML
- Semantic HTML5
- One `<h1>` per page
- Correct heading hierarchy
- Accessibility-first approach

### CSS
- BEM methodology
- CSS custom properties (`:root` variables)
- CSS Grid + Flexbox
- Full responsiveness (1024/768/480/360px breakpoints)
- No Tailwind unless explicitly requested

### JavaScript
- Vanilla JS (no frameworks)
- `DOMContentLoaded` initialization
- `IntersectionObserver` for scroll reveals
- Mobile hamburger menu pattern

### Quality Gates
- **UX:** Nielsen heuristics
- **Accessibility:** WCAG AA compliance (contrast, keyboard, focus, reduced motion)
- **Performance:** Core Web Vitals mindset (no render-blocking, lazy-load, minimal JS)

### Git Conventions
- Commit messages: imperative mood, max 72 chars
- Format: `type(scope): description`
- Example: `fix(css): correct mobile nav overflow`

---

## Git Setup for Your Project

This starter pack includes two gitignore files:

### `.gitignore` (for this starter pack repo)
- AI configs (`CLAUDE.md`, `.claude/`, etc.) are **NOT** ignored
- This allows the starter pack to include all configuration files

### `.gitignore.template` (for your projects)
- AI configs **ARE** ignored
- After copying the starter pack to a new project:

```bash
# Linux/macOS
mv .gitignore.template .gitignore

# Windows
ren .gitignore.template .gitignore
```

This ensures your project-specific AI configurations stay local and don't get committed to your project's repository.

---

## Helper Scripts

### Watch Mode (Development)

Start the CSS/JS watcher for automatic minification:

```bash
node _scripts/watch.js
```

Or use VS Code: `Ctrl+Shift+B` → "Watch & Minify Assets"

### Media Optimization

**Images** (generates AVIF/WebP/JPG in 4 sizes):
```bash
node _scripts/optimize-images.js
# Input:  assets/img/originals/
# Output: assets/img/optimized/
```

**Video** (generates WebM/MP4):
```bash
node _scripts/optimize-video.js
# Input:  assets/video/originals/
# Output: assets/video/optimized/
```

See `_docs/guide-media-optimization.md` for HTML usage examples.

---

## File Structure

```
ai-starter-vanilla/
├── .claude/                    # Claude Code CLI config
│   ├── commands/*.md           # Slash command definitions
│   └── settings.local.json     # Project settings
├── .gemini/                    # Gemini CLI config
│   ├── commands/*.toml         # Slash command definitions
│   └── settings.json           # Project settings
├── .codex/                     # Codex CLI config
│   ├── prompts/*.md            # Slash command definitions
│   ├── config.toml             # Project settings
│   └── AGENTS.md               # Agent guidance
├── _docs/                      # Documentation & reports
│   ├── guide-*.md              # Guides
│   ├── report-*.md             # Audit reports (generated)
│   └── notes-*.md              # Quick references
├── _scripts/                   # Helper scripts
│   ├── watch.js                # File watcher
│   ├── optimize-images.js      # Image optimization
│   ├── optimize-video.js       # Video optimization
│   └── ...                     # Other utilities
├── CLAUDE.md                   # Claude Code operating rules
├── GEMINI.md                   # Gemini CLI operating rules
├── CODEX.md                    # Codex CLI operating rules
├── .editorconfig               # Code formatting
├── .gitattributes              # Git line endings
├── .gitignore                  # Starter pack gitignore
├── .gitignore.template         # User project gitignore
├── LICENSE                     # MIT License
└── README.md                   # This file
```

---

## Credits

Created and maintained by **DominDev**.

This starter pack combines best practices from professional web development with the power of AI coding assistants. It enforces a brief-first workflow, ensuring proper requirements gathering before any code is written.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
