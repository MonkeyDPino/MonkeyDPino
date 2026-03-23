# README Redesign — Design Spec

**Date:** 2026-03-23
**Author:** Juan Esteban Pino Vidal
**Status:** Approved

---

## Goal

Redesign the GitHub profile README (`MonkeyDPino/README.md`) to present Juan as a senior-level Backend & Cloud Engineer to recruiters and hiring managers. The current README reads as a student profile — the redesign must signal professional experience and technical depth at a glance.

---

## Design Decisions

| Decision | Choice | Rationale |
|---|---|---|
| Primary audience | Recruiters / hiring managers | Optimize for fast scanning, not peer networking |
| First impression | Work experience & impact | Not skills list — show what was built |
| Visual style | Bold and modern | Stand out from generic profiles |
| Layout | Timeline Story (C) | Gradient header + vertical experience timeline |
| Bottom sections | Tech stack badges + GitHub stats | Skills at a glance, no "Currently" section |

---

## Layout Structure

### 1. Header
- Name in blue→green gradient (`#58a6ff` → `#3fb950`), large, bold
- Subtitle: `Backend & Cloud Engineer · Full-Stack · Medellín, Colombia 🇨🇴`
- Three `shields.io for-the-badge` social links in a centered row:
  - **LinkedIn** — `logo=linkedin`, blue (`#0A66C2`)
  - **WhatsApp** — `logo=whatsapp`, green (`#25D366`)
  - **Portfolio** — `logo=googlechrome`, blue (`#4285F4`), label: `pinodev.vercel.app`

### 2. About
- Left-border accent (`#21262d`)
- Backend-first framing: *"Backend-focused Software Engineer with hands-on experience designing and deploying production systems on AWS. I architect cloud-native infrastructures (serverless + EC2), build robust APIs, and own CI/CD pipelines end-to-end — with full-stack range to ship features from database to UI when needed."*

### 3. Experience (Timeline)
Vertical timeline with blue dot → green dot connected by a blue-to-green gradient line.

**Note on dates:** Experience entries intentionally omit date ranges. The timeline is visual only (dot + line), not chronological with dates shown.

**Agentemotor** — Backend & Cloud Developer
- Designed scalable AWS infrastructure: EC2 · ALB · Lambda · API Gateway · ElastiCache · Cognito
- Built SOAT insurance sales platform with bidirectional Odoo 18 ERP integration via Python APIs
- Delivered full-stack features with React + Vite frontend and Node.js + Express backend
- Automated delivery with GitHub Actions CI/CD + Docker orchestration

**Universidad Tecnológica de Pereira** — Research Assistant
- Contributed to Quantum Computing research — methodology structuring and algorithm development
- Authored scientific documents with advanced LaTeX for high-complexity mathematical content

### 4. Tech Stack
Categorized rows using `skillicons.dev` icons (`theme=dark`):

| Category | Icons |
|---|---|
| Languages | `js, ts, python` |
| Frontend | `react, html, css, vite` |
| Backend | `nodejs, express` |
| Cloud | `aws, docker, linux, githubactions` |
| Databases | `postgres, redis` |

URL format: `https://skillicons.dev/icons?i=<icons>&theme=dark`

### 5. GitHub Stats
- `github-readme-stats` Top Languages widget
- Full URL: `https://github-readme-stats.vercel.app/api/top-langs/?username=MonkeyDPino&theme=dark&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=c9d1d9`

---

## Styling Reference

- Background: GitHub dark (`#0d1117`)
- Primary accent: `#58a6ff` (blue)
- Secondary accent: `#3fb950` (green)
- Body text: `#c9d1d9`
- Muted text: `#8b949e`
- Section dividers: `border-top: 1px solid #21262d`
- Section labels: `11px, uppercase, letter-spacing: 1.5px`

---

## What Was Removed from the Old README

- Student framing ("I'm a Systems Engineering Student")
- Facebook icon link
- YouTube Music playlist link
- Inline GIF decoration
- Emoji bullet points (`💻`, `📚`, `🌝`)
- Java and Spring badges
- C++ badge
- MongoDB badge (replaced with Redis)
- SQL badge
- IntelliJ IDEA and Visual Studio Code badges
- Git and GitHub badges (redundant on a GitHub profile)
- Flat black shields.io tech badges (replaced with skillicons.dev)
- Both GIF decorations (waving hand on title, coding GIF aligned right)

---

## Implementation Notes

- README is pure Markdown with inline HTML for gradient text and layout
- Gradient name requires `<div>` with inline CSS (GitHub renders inline styles in README)
- Timeline dots/lines are HTML/CSS divs — GitHub supports these
- `skillicons.dev` images use a single `<img>` tag per row, which GitHub renders correctly
- All external image sources must be HTTPS and publicly accessible
