# README Section Templates

Use these templates when generating README.md via `/readme-generate`.

## Hero Section

```markdown
# Project Name

> **Bold tagline** - What makes this different

<div align="center">

[![Live Demo](https://img.shields.io/badge/🚀_Live_Demo-success?style=for-the-badge)](URL)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github)](URL)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)

</div>

### 🎯 Quick Stats

| Metric | Value | Benchmark |
|--------|-------|-----------|
| **Performance** | 🟢 95+ | Industry avg: 70 |
| **Load Time** | ⚡ < 1s | Industry avg: 3-5s |
| **Bundle Size** | 📦 < 50KB | Industry avg: 200KB+ |
```

## Preview Section

```markdown
## 📸 Preview

<div align="center">
<table>
<tr>
<td width="50%">**Desktop** 🖥️<br>![Desktop](screenshot-path)</td>
<td width="50%">**Mobile** 📱<br>![Mobile](screenshot-path)</td>
</tr>
</table>
</div>
```

## Features Table

```markdown
## ✨ Key Features

| Feature | Description | Impact |
|---------|-------------|--------|
| 🎯 **Feature** | Business value | 🚀 Metric |
```

## Comparison Matrix

```markdown
### 🎨 What Makes This Different?

<table>
<tr>
<td width="50%">

#### ❌ Typical Projects
- Bloated frameworks
- Slow load times (3-5s)
- Generic templates

</td>
<td width="50%">

#### ✅ This Project
- Vanilla JS — zero overhead
- < 1s load time
- Custom design

</td>
</tr>
</table>
```

## Tech Stack Badges (Vanilla)

```markdown
## 🛠️ Tech Stack

<div align="center">

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![npm](https://img.shields.io/badge/npm-CB3837?style=for-the-badge&logo=npm&logoColor=white)

</div>

### 📊 Stack Comparison

| Category | This Project | Alternative | Why Better? |
|----------|-------------|-------------|-------------|
| JS | Vanilla (0 KB) | React (140 KB) | Faster TTI |
| CSS | Custom Grid (0 KB) | Bootstrap (180 KB) | No unused code |
| Images | WebP/AVIF | PNG/JPG | 50% smaller |
```

## Performance Section

```markdown
## ⚡ Performance

### Core Web Vitals

```
┌──────────┬────────────────┬──────────┬────────────┐
│  Metric  │  This Project  │  Target  │  Industry  │
├──────────┼────────────────┼──────────┼────────────┤
│   LCP    │   🟢 X.Xs      │  < 2.5s  │  4.2s      │
│   FID    │   🟢 Xms       │  < 100ms │  180ms     │
│   CLS    │   🟢 X.XX      │  < 0.1   │  0.25      │
└──────────┴────────────────┴──────────┴────────────┘
```
```

## Accessibility Section

```markdown
## ♿ Accessibility — WCAG 2.1 AA

| Standard | Status | Details |
|----------|--------|---------|
| **Perceivable** | ✅ | Contrast 4.5:1+, alt text |
| **Operable** | ✅ | Keyboard nav, focus management |
| **Understandable** | ✅ | Clear language, consistent nav |
| **Robust** | ✅ | Valid HTML5, ARIA, semantic markup |
```

## Getting Started Section

```markdown
## 🚀 Getting Started

### Quick Start

```bash
git clone URL
cd project-name
npm install
npm run watch   # start dev (auto-minify on save)
# or open index.html directly in browser
```

### 📁 Project Structure

```
project-name/
├── 📄 index.html
├── 📁 src/
│   ├── 📁 css/        ← source styles
│   └── 📁 js/         ← source JavaScript
├── 📁 assets/
│   └── 📁 img/originals/  ← place images here
├── 📁 _scripts/       ← build automation
└── 📄 package.json
```
```

## Roadmap Section

```markdown
## 🗺️ Roadmap

| Priority | Feature | Status |
|----------|---------|--------|
| 🔴 High | Feature | 📋 Planned |
| 🟡 Medium | Feature | 💭 Considering |
```

## License Section

```markdown
## 📄 License

| Type | Coverage | Terms |
|------|----------|-------|
| ✅ **MIT** | Source code | Free to use/modify |
| ❌ **ARR** | Assets, brand | Permission required |
```
