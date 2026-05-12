<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,14,20&height=220&section=header&text=Moe%20Kyaw%20Aung&fontSize=58&fontColor=63b3ed&animation=fadeIn&fontAlignY=38&desc=Bootstrap%205%20%2B%20Three.js%203D%20Premium%20Portfolio&descAlignY=60&descColor=b794f4" width="100%"/>

<br/>

[![Live Demo](https://img.shields.io/badge/🌐_Live_Demo-Visit_Portfolio-63b3ed?style=for-the-badge&labelColor=0a0d16)](https://dev-moe-kyawaung.github.io/Developer-moekyawaung-portfolio/)
[![Bootstrap](https://img.shields.io/badge/Bootstrap-5.3.3-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)](https://getbootstrap.com/)
[![Three.js](https://img.shields.io/badge/Three.js-r128-000000?style=for-the-badge&logo=threedotjs&logoColor=white)](https://threejs.org/)
[![AOS](https://img.shields.io/badge/AOS-2.3.4-68d391?style=for-the-badge)](https://michalsnik.github.io/aos/)
[![License](https://img.shields.io/badge/License-MIT-f6d860?style=for-the-badge)](LICENSE)
[![GitHub Pages](https://img.shields.io/badge/Deployed-GitHub_Pages-181717?style=for-the-badge&logo=github&logoColor=white)](https://pages.github.com/)

<br/>

```
╔═══════════════════════════════════════════════════════════════════╗
║   Bootstrap 5 · Three.js r128 · AOS 2.3.4 · Bootstrap Icons     ║
║   Zero Build Step · Pure HTML/CSS/JS · GitHub Pages Ready        ║
╚═══════════════════════════════════════════════════════════════════╝
```

</div>

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [File Structure](#-file-structure)
- [Dependencies & CDN](#-dependencies--cdn)
- [Quick Start](#-quick-start)
- [Deploy to GitHub Pages](#-deploy-to-github-pages)
- [Customization Guide](#-customization-guide)
- [Browser Support](#-browser-support)
- [Performance](#-performance)
- [License](#-license)

---

## 🎯 Overview

A **premium, single-file portfolio website** built for Senior Android Developer **Moe Kyaw Aung**. Combines Bootstrap 5's responsive grid system with Three.js real-time 3D WebGL animations — delivered with **zero build step required**.

> 🔗 **Live URL:** [https://dev-moe-kyawaung.github.io/Developer-moekyawaung-portfolio/](https://dev-moe-kyawaung.github.io/Developer-moekyawaung-portfolio/)

---

## ✨ Features

### 3D & Motion
| Feature | Technology | Details |
|---|---|---|
| 3D Background Scene | Three.js r128 | 80 floating icosahedra particles + 2 wireframe torus rings |
| Mouse Parallax Camera | Three.js | Camera follows mouse in 3D space |
| 3D Card Tilt | Vanilla JS | Profile card tilts on mouse — `perspective(800px)` |
| Cert Card 3D Flip | CSS 3D Transform | `rotateY(180deg)` flip on hover |
| Skill Bar Animation | CSS + IntersectionObserver | Fills on scroll with `cubic-bezier` easing |
| Scroll Reveal | AOS 2.3.4 | fade, zoom, slide — triggered by IntersectionObserver |
| Avatar Float | CSS `@keyframes` | Continuous floating with subtle rotation |
| Status Pulse | CSS `@keyframes` | Live green blinking dot |
| Navbar Shrink | JS scroll event | Padding shrinks + shadow on scroll |

### Bootstrap 5 Components Used
| Component | Bootstrap Class | Customized |
|---|---|---|
| Navbar | `.navbar`, `.navbar-expand-lg`, `.navbar-collapse` | ✅ Custom glass background |
| Grid System | `.container`, `.row`, `.col-lg-*` | ✅ All sections |
| Responsive Collapse | `.collapse`, `data-bs-toggle` | ✅ Mobile nav |
| Utility Classes | `d-flex`, `gap-*`, `mt-*`, `mb-*`, `text-center` | ✅ Throughout |
| Form Controls | `.form-control` | ✅ Custom dark styling |

### Sections (8 Sections)
```
1. Hero          → 3D tilt card, animated headline, stat counters, CTA buttons
2. About         → Bio paragraphs + 6 highlight feature cards
3. Skills        → 3 animated skill bar cards + 12 tech orb grid
4. Experience    → Vertical CSS timeline with 3 job entries
5. Projects      → 1 featured large card + 3 project cards with 3D hover
6. Certifications→ 6 flip cards (CSS 3D front/back)
7. Contact       → 4 contact link rows + styled Bootstrap form
8. Footer        → Brand logo + social icon buttons
```

---

## 📁 File Structure

```
Developer-moekyawaung-portfolio/
│
├── index.html                     ← ⭐ Main portfolio (all-in-one file)
├── README.md                      ← Documentation (this file)
├── LICENSE                        ← MIT License
├── .gitignore                     ← Git ignore rules
├── requirements.txt               ← CDN dependency reference list
├── COMPONENTS.md                  ← Detailed component guide
│
├── assets/                        ← Static assets (all optional)
│   ├── images/
│   │   ├── profile.jpg            ← Replace avatar "M" letter with real photo
│   │   ├── og-image.png           ← Open Graph social preview (1200×630px)
│   │   ├── favicon.ico            ← Browser tab icon
│   │   └── projects/
│   │       ├── pulsesync.png
│   │       ├── pulsesync-azure.png
│   │       ├── roadmap-app.png
│   │       └── portfolio.png
│   └── resume/
│       └── moe-kyaw-aung-cv.pdf   ← Downloadable CV/Resume
│
└── .github/
    └── workflows/
        └── deploy.yml             ← GitHub Actions auto-deploy
```

---

## 📦 Dependencies & CDN

**No npm. No build step. All loaded from CDN.**

### CSS Dependencies

```html
<!-- 1. Bootstrap 5.3.3 — Grid, utilities, navbar collapse -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet"/>

<!-- 2. Bootstrap Icons 1.11.3 — Icon set -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.min.css" rel="stylesheet"/>

<!-- 3. AOS 2.3.4 — Animate On Scroll styles -->
<link href="https://unpkg.com/aos@2.3.4/dist/aos.css" rel="stylesheet"/>

<!-- 4. Google Fonts — Typography -->
<link href="https://fonts.googleapis.com/css2?family=Clash+Display:wght@400;500;600;700&family=Cabinet+Grotesk:wght@300;400;500;700;800;900&family=Instrument+Serif:ital@0;1&display=swap" rel="stylesheet"/>
```

### JavaScript Dependencies

```html
<!-- 1. Bootstrap Bundle 5.3.3 — Navbar + JS components -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>

<!-- 2. AOS 2.3.4 — Scroll animation engine -->
<script src="https://unpkg.com/aos@2.3.4/dist/aos.js"></script>

<!-- 3. Three.js r128 — WebGL 3D rendering engine -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
```

### Full Dependency Table

| # | Library | Version | Type | CDN Provider | Size (gzip) | Purpose |
|---|---|---|---|---|---|---|
| 1 | Bootstrap CSS | 5.3.3 | CSS | jsDelivr | ~22 KB | Grid, utilities, dark theme |
| 2 | Bootstrap JS Bundle | 5.3.3 | JS | jsDelivr | ~35 KB | Navbar collapse, popper |
| 3 | Bootstrap Icons | 1.11.3 | CSS Font | jsDelivr | ~50 KB | All icons throughout |
| 4 | Three.js | r128 | JS | cdnjs | ~155 KB | 3D WebGL scene |
| 5 | AOS | 2.3.4 | CSS + JS | unpkg | ~8 KB | Scroll reveal animations |
| 6 | Clash Display | 400–700 | Web Font | Google | ~25 KB | Display headings |
| 7 | Cabinet Grotesk | 300–900 | Web Font | Google | ~30 KB | Body text |
| 8 | Instrument Serif | 400, italic | Web Font | Google | ~15 KB | Decorative italic text |

### Google Fonts Detail

| Font | CSS Variable | Weights | Used For |
|---|---|---|---|
| Clash Display | `--font-display` | 400, 500, 600, 700 | `.navbar-brand`, section titles, buttons, stat numbers |
| Cabinet Grotesk | `--font-body` | 300, 400, 500, 700, 800, 900 | `body`, paragraphs, descriptions, labels |
| Instrument Serif | `--font-serif` | 400, 400i | Decorative stroke-outline italic text in hero/section titles |

### Bootstrap Icons Used

```
bi-arrow-up-right   bi-grid-3x3-gap    bi-envelope        bi-person-check
bi-github           bi-box-arrow-up-right  bi-geo-alt-fill
bi-envelope-fill    bi-phone-fill      bi-linkedin
bi-arrow-right      bi-send-fill       bi-check-lg
bi-download         bi-star-fill
```

---

## ⚡ Quick Start

### Option A — Open Directly
```bash
git clone https://github.com/Dev-moe-kyawaung/Developer-moekyawaung-portfolio.git
cd Developer-moekyawaung-portfolio

# macOS
open index.html

# Windows
start index.html

# Linux
xdg-open index.html
```

### Option B — Local Server (Recommended for Three.js)
```bash
# Python 3 (no install needed)
python3 -m http.server 8080
# → http://localhost:8080

# Node.js (if installed)
npx serve .
# → http://localhost:3000

# PHP
php -S localhost:8080
# → http://localhost:8080
```

> ⚠️ **Three.js** may have CORS issues when opened as a local file (`file://`).
> Use a local server (Option B) for best results.

---

## 🌐 Deploy to GitHub Pages

### Method 1 — Settings UI (Simplest)
```
1. Push code to GitHub repo
2. Repo → Settings → Pages
3. Source: "Deploy from a branch"
4. Branch: main → / (root) → Save
5. Wait 1–3 minutes
6. Live at: https://dev-moe-kyawaung.github.io/Developer-moekyawaung-portfolio/
```

### Method 2 — GitHub Actions (Auto-deploy on push)
```bash
# Already included in .github/workflows/deploy.yml
# Just push to main:
git add .
git commit -m "✨ Portfolio update"
git push origin main
# → Auto-deploys via GitHub Actions
```

### Method 3 — gh-pages npm package
```bash
npm install -g gh-pages
gh-pages -d .
```

### First-Time Setup Commands
```bash
git init
git add .
git commit -m "🚀 Initial portfolio launch"
git branch -M main
git remote add origin https://github.com/Dev-moe-kyawaung/Developer-moekyawaung-portfolio.git
git push -u origin main
```

---

## 🎨 Customization Guide

### 1. Change Color Theme
```css
/* Find in index.html <style> section — :root variables */
:root {
  --cyan:    #63b3ed;   /* Primary accent — your brand color */
  --violet:  #b794f4;   /* Secondary accent */
  --rose:    #fc8181;   /* Tertiary accent */
  --gold:    #f6d860;   /* Highlight / badge color */
  --bg-deep: #04050a;   /* Page background */
  --bg-card: #0a0d16;   /* Card background */
}
```

### 2. Update Three.js Particle Colors
```javascript
// Find in <script> at bottom of index.html:
const mat = new THREE.MeshStandardMaterial({
  color: 0x63b3ed,  // Primary particle color (hex without #)
});
const matV = new THREE.MeshStandardMaterial({
  color: 0xb794f4,  // Secondary particle color
});
const pointLight = new THREE.PointLight(0xb794f4, 1.5, 60); // Light color
```

### 3. Add Real Profile Photo
```html
<!-- Find this in Hero section: -->
<div class="avatar-inner-3d">M</div>

<!-- Replace with: -->
<img src="assets/images/profile.jpg"
     alt="Moe Kyaw Aung"
     style="width:100%; height:100%; border-radius:50%; object-fit:cover; object-position:center top;">
```

### 4. Add Resume Download Button
```html
<!-- Add inside hero .d-flex.gap-3 div: -->
<a href="assets/resume/moe-kyaw-aung-cv.pdf"
   download="Moe-Kyaw-Aung-Resume.pdf"
   class="btn-outline-custom">
  <i class="bi bi-download"></i> Download CV
</a>
```

### 5. Add Open Graph Meta Tags (for link preview)
```html
<!-- Add inside <head>: -->
<meta property="og:title" content="Moe Kyaw Aung — Senior Android Developer">
<meta property="og:description" content="5+ years building production Android apps with Kotlin, Jetpack Compose, and Clean Architecture.">
<meta property="og:image" content="https://dev-moe-kyawaung.github.io/Developer-moekyawaung-portfolio/assets/images/og-image.png">
<meta property="og:url" content="https://dev-moe-kyawaung.github.io/Developer-moekyawaung-portfolio/">
<meta name="twitter:card" content="summary_large_image">
```

### 6. Change Particle Count / Speed
```javascript
// Find in Three.js setup:
for (let i = 0; i < 80; i++) {     // ← Change 80 to more/fewer particles
  m.userData = {
    vx: (Math.random() - 0.5) * 0.02,  // ← Increase for faster movement
    vy: (Math.random() - 0.5) * 0.015,
  };
}
```

---

## 🌍 Browser Support

| Browser | Min Version | WebGL 3D | CSS 3D | Status |
|---|---|---|---|---|
| Chrome | 90+ | ✅ | ✅ | ✅ Full support |
| Firefox | 88+ | ✅ | ✅ | ✅ Full support |
| Safari | 14+ | ✅ | ✅ | ✅ Full support |
| Edge | 90+ | ✅ | ✅ | ✅ Full support |
| Opera | 76+ | ✅ | ✅ | ✅ Full support |
| Mobile Chrome | 90+ | ✅ | ✅ | ✅ Full support |
| Mobile Safari | 14+ | ✅ | ✅ | ✅ Full support |
| Samsung Internet | 14+ | ⚠️ | ✅ | ⚠️ Partial 3D |
| IE 11 | — | ❌ | ⚠️ | ❌ Not supported |

---

## 📊 Performance

| Metric | Value |
|---|---|
| HTML file size | ~85 KB |
| Three.js (CDN) | ~584 KB (cached after first load) |
| Bootstrap CSS+JS | ~100 KB (cached) |
| Total first load | ~900 KB |
| Total cached load | ~85 KB |
| Estimated Lighthouse Score | 85–92 (Desktop) |

---

## 📄 License

```
MIT License — © 2026 Moe Kyaw Aung
Free to use as a portfolio template with proper attribution.
```

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,14,20&height=120&section=footer" width="100%"/>
<p>Built with ❤️ by Moe Kyaw Aung · Tachileik, Myanmar</p>
</div>
