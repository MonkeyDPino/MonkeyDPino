# README Redesign Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace the current student-framed README with a professional backend/cloud engineer profile targeting recruiters.

**Architecture:** Single file (`README.md`) using Markdown + inline HTML. Gradient header via `capsule-render.vercel.app`, social badges via `shields.io`, tech icons via `skillicons.dev`, stats via `github-readme-stats`. GitHub's HTML sanitizer supports inline `style` with basic CSS (colors, borders, border-radius, background gradients, flex is unreliable — use `<table>` for layout instead).

**Tech Stack:** Markdown, inline HTML/CSS, capsule-render, shields.io, skillicons.dev, github-readme-stats

---

## File Map

| File | Action | Purpose |
|---|---|---|
| `README.md` | Rewrite | The entire profile page |

---

## Task 1: Write the header

**Files:**
- Modify: `README.md` (full rewrite — start fresh)

- [ ] **Step 1: Replace README.md with the header section only**

Open `README.md` and replace all content with:

```markdown
<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=200&section=header&text=Juan%20Esteban%20Pino&fontSize=42&fontColor=fff&animation=fadeIn&fontAlignY=36&desc=Backend%20%26%20Cloud%20Engineer%20%C2%B7%20Full-Stack%20%C2%B7%20Medell%C3%ADn%2C%20Colombia%20%F0%9F%87%A8%F0%9F%87%B4&descAlignY=54&descSize=17" alt="header" width="100%" />

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/juan-pino-vidal/)
[![WhatsApp](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://wa.me/+573233927516)
[![Portfolio](https://img.shields.io/badge/Portfolio-pinodev.vercel.app-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white)](https://pinodev.vercel.app)

</div>
```

- [ ] **Step 2: Verify the header images load**

Open a browser and paste each URL to confirm it returns an image (not a 404):
- `https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=200&section=header&text=Juan%20Esteban%20Pino&fontSize=42&fontColor=fff&animation=fadeIn&fontAlignY=36`
- `https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white`
- `https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white`
- `https://img.shields.io/badge/Portfolio-pinodev.vercel.app-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white`

All four must return images. If any return 404, fix the URL before proceeding.

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "feat: add gradient header and social badges"
```

---

## Task 2: Write the About section

**Files:**
- Modify: `README.md` (append)

- [ ] **Step 1: Append the About section**

Add after the existing content in `README.md`:

```markdown

---

## About

<div style="border-left: 3px solid #21262d; padding-left: 14px;">

Backend-focused Software Engineer with hands-on experience designing and deploying production systems on **AWS**. I architect cloud-native infrastructures (serverless + EC2), build robust APIs, and own CI/CD pipelines end-to-end — with full-stack range to ship features from database to UI when needed.

</div>
```

- [ ] **Step 2: Preview the file**

Open `README.md` in a Markdown preview (VS Code preview, or push to a branch and check GitHub's preview). Verify:
- Horizontal rule renders as a divider
- Left-border accent div is visible
- Text reads correctly with **AWS** bolded

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "feat: add backend-focused About section"
```

---

## Task 3: Write the Experience timeline

**Files:**
- Modify: `README.md` (append)

- [ ] **Step 1: Append the Experience section**

Add after the existing content in `README.md`:

```markdown

---

## Experience

<table border="0" cellpadding="0" cellspacing="0">
<tr>
<td width="24" valign="top" align="center">
  <div style="width:12px;height:12px;border-radius:50%;background-color:#58a6ff;margin-top:4px;"></div>
  <div style="width:2px;background:linear-gradient(to bottom,#58a6ff,#3fb950);min-height:80px;margin:4px auto 0;"></div>
</td>
<td valign="top" style="padding-left:12px;padding-bottom:24px;">

**Agentemotor** &nbsp;<sub>Backend & Cloud Developer</sub>

▸ Designed scalable AWS infrastructure: `EC2 · ALB · Lambda · API Gateway · ElastiCache · Cognito`
▸ Built SOAT insurance sales platform with bidirectional **Odoo 18 ERP** integration via Python APIs
▸ Delivered full-stack features with **React + Vite** frontend and **Node.js + Express** backend
▸ Automated delivery with **GitHub Actions CI/CD** + Docker orchestration

</td>
</tr>
<tr>
<td width="24" valign="top" align="center">
  <div style="width:12px;height:12px;border-radius:50%;background-color:#3fb950;margin-top:4px;"></div>
</td>
<td valign="top" style="padding-left:12px;">

**Universidad Tecnológica de Pereira** &nbsp;<sub>Research Assistant</sub>

▸ Contributed to **Quantum Computing** research — methodology structuring and algorithm development
▸ Authored scientific documents with advanced **LaTeX** for high-complexity mathematical content

</td>
</tr>
</table>
```

- [ ] **Step 2: Verify timeline renders**

Preview the README (GitHub preview or VS Code). Verify:
- Two rows are visible with colored dots on the left
- Blue dot for Agentemotor, green dot for UTP
- Gradient line connects the two rows (if GitHub strips the gradient, `background-color:#30363d` is an acceptable fallback — update `background:linear-gradient(...)` to `background-color:#30363d` if needed)
- Bullet text with `▸` renders correctly with bold tech terms

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "feat: add Experience timeline section"
```

---

## Task 4: Write the Tech Stack section

**Files:**
- Modify: `README.md` (append)

- [ ] **Step 1: Append the Tech Stack section**

Add after the existing content in `README.md`:

```markdown

---

## Tech Stack

<table border="0">
<tr>
  <td><b>Languages</b></td>
  <td><img src="https://skillicons.dev/icons?i=js,ts,python&theme=dark" /></td>
</tr>
<tr>
  <td><b>Frontend</b></td>
  <td><img src="https://skillicons.dev/icons?i=react,html,css,vite&theme=dark" /></td>
</tr>
<tr>
  <td><b>Backend</b></td>
  <td><img src="https://skillicons.dev/icons?i=nodejs,express&theme=dark" /></td>
</tr>
<tr>
  <td><b>Cloud</b></td>
  <td><img src="https://skillicons.dev/icons?i=aws,docker,linux,githubactions&theme=dark" /></td>
</tr>
<tr>
  <td><b>Databases</b></td>
  <td><img src="https://skillicons.dev/icons?i=postgres,redis&theme=dark" /></td>
</tr>
</table>
```

- [ ] **Step 2: Verify icons load**

Paste these URLs in a browser to confirm they return icon strip images (not errors):
- `https://skillicons.dev/icons?i=js,ts,python&theme=dark`
- `https://skillicons.dev/icons?i=react,html,css,vite&theme=dark`
- `https://skillicons.dev/icons?i=nodejs,express&theme=dark`
- `https://skillicons.dev/icons?i=aws,docker,linux,githubactions&theme=dark`
- `https://skillicons.dev/icons?i=postgres,redis&theme=dark`

If `githubactions` returns a broken icon, replace with `github` as a fallback. If `express` is not available, remove it (Node.js implies Express).

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "feat: add Tech Stack section with skillicons.dev badges"
```

---

## Task 5: Write the GitHub Stats footer

**Files:**
- Modify: `README.md` (append)

- [ ] **Step 1: Append the GitHub Stats section**

Add after the existing content in `README.md`:

```markdown

---

<div align="center">

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=MonkeyDPino&theme=dark&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=c9d1d9)](https://github.com/MonkeyDPino)

</div>
```

- [ ] **Step 2: Verify the stats widget loads**

Open this URL in a browser to confirm it returns a stats card (not an error):

`https://github-readme-stats.vercel.app/api/top-langs/?username=MonkeyDPino&theme=dark&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=c9d1d9`

The card should show language percentages with a dark background matching the profile theme.

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "feat: add GitHub stats footer"
```

---

## Task 6: Final review

**Files:**
- Modify: `README.md` (fixes only if needed)

- [ ] **Step 1: Push to GitHub and review live rendering**

```bash
git push origin main
```

Then open `https://github.com/MonkeyDPino` in a browser. Verify the full profile against the spec:

| Section | Check |
|---|---|
| Header | Gradient wave banner with name + subtitle renders |
| Social badges | All 3 badges (LinkedIn, WhatsApp, Portfolio) are visible and linked |
| About | Left border visible, text correct |
| Experience | Blue dot → green dot, both roles with bullets |
| Tech Stack | All 5 category rows with correct icons |
| GitHub Stats | Dark-themed language card renders |

- [ ] **Step 2: Fix any rendering issues**

Common GitHub rendering quirks to watch for:
- **Gradient line not rendering:** Replace `background:linear-gradient(to bottom,#58a6ff,#3fb950)` with `background-color:#30363d`
- **`<div>` styles stripped:** If inline styles are stripped on any element, switch to a `<table>` equivalent or remove the style
- **skillicons.dev icon missing:** Replace with the closest available icon key (check `https://skillicons.dev` for the full list)

- [ ] **Step 3: Final commit if fixes were needed**

```bash
git add README.md
git commit -m "fix: adjust rendering for GitHub HTML sanitization"
git push origin main
```
