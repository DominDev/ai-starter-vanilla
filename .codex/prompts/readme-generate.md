---
name: readme-generate
description: Generate professional README.md and LICENSE.md for the project (DominDev branding, tech stack, features, setup).
---

Generate a **professional README.md** for this project in **English**.

## Analysis Phase (Required)

1. **Scan project structure:**
   - List all files (glob): HTML, CSS, JS, JSON
   - Identify key directories: `src/`, `assets/`, `_scripts/`, etc.
   - Read `package.json` if exists → extract dependencies, scripts

2. **Analyze technology stack:**
   - HTML files → meta tags, semantic structure, features
   - CSS files → Grid/Flexbox, variables, frameworks (if any)
   - JS files → vanilla/framework, key features (forms, animations, etc.)
   - Build tools → npm scripts, bundlers, optimizations

3. **Extract project metadata:**
   - Project name (from folder name or package.json)
   - Key features (from HTML structure and JS functionality)
   - Performance hints (minified files, lazy-load, WebP/AVIF)
   - Accessibility (ARIA, semantic HTML, focus management)

## README.md Structure

### 1. Hero Section
```markdown
# Project Name

> One-sentence tagline describing the value proposition

[![Live Demo](https://img.shields.io/badge/demo-live-success?style=for-the-badge)](https://example.com)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://www.w3.org/html/)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://www.w3.org/Style/CSS/)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)](LICENSE.md)

[🚀 Live Demo](https://example.com) • [📧 Contact](mailto:contact@domindev.com)
```

### 2. Visual Preview
```markdown
## 📸 Preview

![Desktop Preview](assets/screenshots/desktop.png)
![Mobile Preview](assets/screenshots/mobile.png)

*Optional: Add GIF/video for interactions*
```

### 3. About & Business Value
```markdown
## 💡 About

[2-3 sentences: What problem does this solve? Who is it for? What makes it unique?]

### ✨ Key Features

- 🎯 **Feature 1** - Business value (e.g., "Conversion-optimized CTA placement")
- ⚡ **Feature 2** - Technical benefit (e.g., "Sub-second load time")
- 📱 **Feature 3** - UX benefit (e.g., "Mobile-first responsive design")
- ♿ **Feature 4** - Accessibility (e.g., "WCAG 2.1 AA compliant")
- 🔒 **Feature 5** - Security (e.g., "CSP headers, XSS protection")

[List 5-8 concrete features detected from codebase]
```

### 4. Tech Stack
```markdown
## 🛠️ Tech Stack

| Category | Technologies | Why? |
|----------|-------------|------|
| **Frontend** | HTML5, CSS3 (Grid/Flexbox), Vanilla JavaScript | [Reason: performance, simplicity, no framework overhead] |
| **Build Tools** | [npm scripts / Vite / Webpack] | [Reason: if applicable] |
| **Optimization** | [Terser, Sharp, FFmpeg] | [Reason: if detected in package.json] |
| **Deployment** | [Netlify / Vercel / GitHub Pages] | [Reason: if detected or inferred] |
| **Fonts** | [Google Fonts: Outfit, etc.] | [Reason: if detected] |

### Why This Stack?

[2-3 sentences explaining architectural decisions]
```

### 5. Performance & Quality
```markdown
## ⚡ Performance & Quality

### Lighthouse Scores
[If known/measurable, add screenshot or table]

| Category | Score |
|----------|-------|
| Performance | 🟢 90+ |
| Accessibility | 🟢 90+ |
| Best Practices | 🟢 90+ |
| SEO | 🟢 90+ |

### Core Web Vitals
- **LCP:** < 2.5s (optimized images, critical CSS inline)
- **FID:** < 100ms (minimal JS, event delegation)
- **CLS:** < 0.1 (reserved space for images, no layout shifts)

### Optimizations Applied
- ✅ Minified CSS/JS
- ✅ Lazy-loaded images
- ✅ WebP/AVIF formats
- ✅ Critical CSS inlining
- ✅ Deferred non-critical scripts
- ✅ Browser caching headers
```

### 6. Accessibility
```markdown
## ♿ Accessibility

- **WCAG 2.1 Level AA** compliant
- Semantic HTML5 structure
- Keyboard navigation support
- Screen reader friendly
- Focus management (modals, menus)
- Color contrast ratios > 4.5:1
- `prefers-reduced-motion` support
```

### 7. Getting Started
```markdown
## 🚀 Getting Started

### Prerequisites
- Node.js 18+ (if build tools used)
- Modern browser (Chrome 90+, Firefox 88+, Safari 14+)

### Installation

\`\`\`bash
# Clone repository
git clone https://github.com/DominDev/project-name.git
cd project-name

# Install dependencies (if applicable)
npm install

# Start development server (if applicable)
npm start
# or simply open index.html in browser

# Build for production (if applicable)
npm run build
\`\`\`

### Project Structure

\`\`\`
project-name/
├── index.html              # Main page
├── src/
│   ├── css/
│   │   ├── style.css       # Main styles
│   │   └── style.min.css   # Minified (production)
│   ├── js/
│   │   ├── main.js         # Main script
│   │   └── main.min.js     # Minified (production)
│   └── assets/
│       ├── img/            # Images (WebP/AVIF)
│       ├── fonts/          # Custom fonts
│       └── icons/          # SVG icons
├── _scripts/               # Build scripts
├── README.md
└── LICENSE.md
\`\`\`
```

### 8. Environment Variables (if applicable)
```markdown
## 🔐 Environment Variables

If this project uses API keys or environment-specific config, create `.env` file:

\`\`\`bash
# Example .env (copy from .env.example)
API_KEY=your_api_key_here
ANALYTICS_ID=your_analytics_id
\`\`\`

**Note:** `.env` is gitignored. Never commit secrets.
```

### 9. Deployment
```markdown
## 📦 Deployment

### Hosting
[Detect or recommend: Netlify / Vercel / GitHub Pages]

### Deploy Steps
\`\`\`bash
# Example for Netlify
netlify deploy --prod

# or GitHub Pages
npm run build
git push origin main
\`\`\`

### Custom Domain
[If detected, add instructions for domain setup]
```

### 10. Roadmap (optional)
```markdown
## 🗺️ Roadmap

- [ ] Add dark mode toggle
- [ ] Implement i18n (multi-language support)
- [ ] Add blog section (if planned)
- [ ] Integrate CMS (if planned)
- [ ] A/B testing setup

[Only include if there's clear technical debt or planned features]
```

### 11. License
```markdown
## 📄 License

This project is licensed under the **MIT License** with additional restrictions:

- ✅ Code is free to use, modify, and distribute
- ❌ Images, logos, and content are **All Rights Reserved**
- ❌ Brand assets may not be used without permission

See [LICENSE.md](LICENSE.md) for full details.
```

### 12. Author (DominDev Branding)
```markdown
## 👨‍💻 Author

<div align="center">

### Crafted with ❤️ by **DominDev**

**Building digital experiences that convert.**

[![Website](https://img.shields.io/badge/Website-domindev.com-FF1F1F?style=for-the-badge&logo=google-chrome&logoColor=white)](https://domindev.com)
[![Email](https://img.shields.io/badge/Email-contact@domindev.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:contact@domindev.com)
[![GitHub](https://img.shields.io/badge/GitHub-DominDev-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/DominDev)

---

⭐ **If you like this project, give it a star on GitHub!**

</div>
```

---

## LICENSE.md Generation

Also create `LICENSE.md` with:

```markdown
# MIT License (Code) + All Rights Reserved (Assets)

Copyright (c) [YEAR] DominDev

## Code License (MIT)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## Assets License (All Rights Reserved)

All images, graphics, logos, icons, videos, audio files, and written content
in this repository are **All Rights Reserved** and may not be used, copied,
modified, or distributed without explicit written permission from DominDev.

This includes but is not limited to:
- `/assets/img/` directory and all subdirectories
- `/assets/fonts/` (if custom/commercial fonts)
- Brand assets, logos, and trademarks
- Written content (copy, descriptions, blog posts)

For licensing inquiries, contact: contact@domindev.com
```

---

## Output Instructions

1. **Analyze** the project thoroughly (scan files, read key files)
2. **Generate** complete README.md with all sections
3. **Generate** LICENSE.md
4. **Backup** existing README.md to `README.backup.md` if it exists
5. **Write** both files to project root
6. **Summary**: Show user a brief summary of what was included (tech stack detected, features found, sections generated)

**Important:**
- Use actual project data (don't make up features)
- If uncertain about something (e.g., deployment), write "TBD" or ask user
- Replace `[YEAR]` with current year (2026) in LICENSE
- Replace placeholder URLs with actual data if found
- Maintain professional, technical tone (Senior Developer level)
