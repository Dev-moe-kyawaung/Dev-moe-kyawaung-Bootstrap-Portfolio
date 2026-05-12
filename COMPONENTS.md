# 🧩 COMPONENTS.md
## Portfolio Component Reference — Moe Kyaw Aung

> Detailed documentation for every component, animation, and interactive element in `index.html`

---

## 📐 Design System

### CSS Variables (Design Tokens)

```css
:root {
  /* Backgrounds */
  --bg-deep:    #04050a;              /* Main page background */
  --bg-card:    #0a0d16;              /* Card / surface background */
  --bg-glass:   rgba(10,13,22,0.7);  /* Glassmorphism backdrop */
  --border:     rgba(255,255,255,0.06); /* Default border */
  --border-glow:rgba(99,179,237,0.25);  /* Hover/active border */

  /* Brand Colors */
  --cyan:        #63b3ed;  /* Primary accent */
  --cyan-bright: #90cdf4;  /* Primary bright variant */
  --violet:      #b794f4;  /* Secondary accent */
  --violet-dim:  #805ad5;  /* Secondary dark */
  --rose:        #fc8181;  /* Tertiary / warning */
  --gold:        #f6d860;  /* Highlight / featured */

  /* Typography */
  --text:       #e2e8f0;  /* Primary text */
  --text-muted: #718096;  /* Muted / placeholder */
  --text-dim:   #a0aec0;  /* Dimmed body text */

  /* Font Families */
  --font-display: 'Clash Display', sans-serif;
  --font-body:    'Cabinet Grotesk', sans-serif;
  --font-serif:   'Instrument Serif', serif;

  /* Gradients */
  --grad-main: linear-gradient(135deg, #63b3ed 0%, #b794f4 100%);
  --grad-card: linear-gradient(145deg, rgba(99,179,237,0.06), rgba(183,148,244,0.04));

  /* Shadows */
  --shadow-glow: 0 0 40px rgba(99,179,237,0.12), 0 20px 60px rgba(0,0,0,0.5);
}
```

---

## 🌐 Three.js 3D Background

**Location:** `<canvas id="bg-canvas">` + `<script>` block  
**Library:** Three.js r128

### Scene Objects
| Object | Geometry | Count | Material | Animation |
|---|---|---|---|---|
| Particles | `IcosahedronGeometry(0.4, 0)` | 80 | `MeshStandardMaterial` | Float + rotate, wrap bounds |
| Torus Ring 1 | `TorusGeometry(12, 0.12, 3, 80)` | 1 | `MeshBasicMaterial` wireframe | `rotation.z += 0.001` |
| Torus Ring 2 | `TorusGeometry(18, 0.08, 3, 100)` | 1 | `MeshBasicMaterial` wireframe | `rotation.z -= 0.0008` |

### Lights
| Light | Type | Color | Intensity |
|---|---|---|---|
| Ambient | `AmbientLight` | `#63b3ed` | 0.4 |
| Point 1 | `PointLight` | `#b794f4` | 1.5 (range: 60) |
| Point 2 | `PointLight` | `#63b3ed` | 1.0 (range: 50) |

### Mouse Parallax
```javascript
// Camera follows mouse at 4% speed per frame
camera.position.x += (mx - camera.position.x) * 0.04;
camera.position.y += (-my - camera.position.y) * 0.04;
```

---

## 🖱️ Custom Cursor

**Elements:** `#cursor-dot` + `#cursor-ring`

```css
#cursor-dot  { width: 8px;  background: var(--cyan); mix-blend-mode: screen; }
#cursor-ring { width: 40px; border: 1.5px solid rgba(99,179,237,0.5); }
```

**Behavior:**
- Dot follows mouse instantly (`translate -50%,-50%`)
- Ring lags behind at 13% interpolation speed
- On hover (links/buttons): dot scales 2.5×, ring scales 1.6× + turns violet

---

## 🔝 Navbar Component

**Bootstrap classes:** `.navbar`, `.navbar-expand-lg`, `.navbar-collapse`  
**Custom class:** `.navbar-custom`

| State | Padding | Shadow |
|---|---|---|
| Default | `1rem 0` | none |
| `.scrolled` (after 60px) | `0.6rem 0` | `0 4px 30px rgba(0,0,0,0.5)` |

**Elements:**
- `.navbar-brand-custom` — gradient text logo
- `.nav-link-custom` — with underline slide animation on hover
- `.btn-nav-cta` — gradient CTA button (hidden on mobile)

---

## 🦸 Hero Section

### Left Column
| Element | Class | Description |
|---|---|---|
| Status Badge | `.hero-badge` | Pill with animated dot |
| Main Title | `.hero-title` | Clash Display, clamp(3.2rem → 6.5rem) |
| Subtitle | `.hero-subtitle` | Violet color, Clash Display |
| Description | `.hero-desc` | Cabinet Grotesk body |
| CTA Buttons | `.btn-primary-custom` + `.btn-outline-custom` | Gradient + ghost |
| Stats Row | Custom border-left stats | 3 inline metrics |

### Right Column — 3D Tilt Profile Card
| Element | Description |
|---|---|
| `.profile-3d-wrapper` | `perspective: 1000px` container |
| `.profile-3d-card` | Tilts on mousemove: `rotateY()` + `rotateX()` |
| `.avatar-3d` | Floating avatar — `@keyframes float-avatar` |
| `.stat-grid` | 3-column stat display |
| `.tech-pills` | Colored pill tags |

**Tilt calculation:**
```javascript
const x = (mouseX - rect.left) / rect.width  - 0.5; // -0.5 to 0.5
const y = (mouseY - rect.top)  / rect.height - 0.5;
card.style.transform = `perspective(800px) rotateY(${x*16}deg) rotateX(${-y*10}deg) scale(1.02)`;
```

---

## 📖 About Section

### Highlight Cards (6 cards, 2-column Bootstrap grid)
```html
<div class="about-highlight-card">
  <div class="hl-icon hl-icon-cyan">🏗️</div>
  <div>
    <div class="hl-title">Feature Title</div>
    <div class="hl-desc">Description text</div>
  </div>
</div>
```

**Icon variants:** `.hl-icon-cyan` · `.hl-icon-violet` · `.hl-icon-rose` · `.hl-icon-gold`

---

## 📊 Skills Section

### Skill Bar Cards (3 cards)
```html
<div class="skill-3d-card">
  <div class="skill-bar-row">
    <div class="skill-bar-header">
      <span>Kotlin</span>
      <span>97%</span>
    </div>
    <div class="bar-bg">
      <div class="bar-progress" data-w="97"></div>  <!-- data-w triggers fill -->
    </div>
  </div>
</div>
```

**Animation trigger:** `IntersectionObserver` at `threshold: 0.25`  
**CSS transition:** `width 1.4s cubic-bezier(0.25, 0.46, 0.45, 0.94)`  
**3D hover:** `perspective(800px) rotateX(3deg) translateY(-5px)`

### Tech Orb Grid (12 items, 4-column grid)
```html
<div class="tech-orb">
  <div class="tech-orb-icon">🤖</div>
  <div class="tech-orb-name">Android</div>
</div>
```

---

## ⏳ Experience Timeline

```css
.timeline-wrap::before {
  /* Vertical gradient line */
  background: linear-gradient(180deg, var(--cyan), var(--violet), transparent);
}
.timeline-dot {
  /* Glowing circle dot */
  box-shadow: 0 0 16px rgba(99,179,237,0.5);
}
```

**Each entry has:**  
Date badge → Role title → Company → Description → Achievement list (▸) → Tag pills

**Dot colors:**  
- 2022–Present: `--cyan` (blue)  
- 2020–2022: `--violet` (purple)  
- 2019–2020: `--rose` (red)

---

## 💼 Project Cards

### Featured Card (full-width)
- 2-column inner layout on desktop
- Metrics row: Coverage / Faster Boot / Crash-free
- Full tech stack badge list

### Standard Card
```css
.project-card-3d:hover {
  transform: perspective(1000px) rotateY(-3deg) rotateX(3deg) translateZ(10px);
  box-shadow: 20px 20px 60px rgba(0,0,0,0.5), 0 0 40px rgba(99,179,237,0.08);
}
```

**Shine overlay:** `::after` with `linear-gradient(135deg, rgba(255,255,255,0.07) 0%, transparent 60%)`

---

## 🏆 Certification Flip Cards

**CSS 3D Transform — no JavaScript required**

```css
.cert-flip-card { perspective: 1000px; }
.cert-flip-inner { transform-style: preserve-3d; transition: transform 0.6s; }
.cert-flip-card:hover .cert-flip-inner { transform: rotateY(180deg); }
.cert-front  { backface-visibility: hidden; }
.cert-back   { backface-visibility: hidden; transform: rotateY(180deg); }
```

| Card | Icon | Front | Back |
|---|---|---|---|
| 1 | 🎓 | BSc Computer Science | Degree detail |
| 2 | 🎓 | BA English | Degree detail |
| 3 | 🔥 | Firebase Developer | Firebase cert detail |
| 4 | 📱 | Android & Kotlin | Android cert detail |
| 5 | ☕ | Java & DSA | Java cert detail |
| 6 | 🔧 | Git & GitHub | Git cert detail |

---

## 📬 Contact Section

### Contact Link Rows
```html
<a class="contact-row" href="mailto:...">
  <div class="contact-icon-box"><i class="bi bi-envelope-fill"></i></div>
  <div>
    <div class="contact-lbl">Email</div>
    <div class="contact-val">moekyawaung@asia.com</div>
  </div>
  <i class="bi bi-arrow-right contact-arrow"></i>
</a>
```
**Hover:** `translateX(5px)` slide-right effect

### Contact Form
Bootstrap `.form-control` with custom dark override:
```css
.form-control-custom {
  background: rgba(255,255,255,0.03);
  border: 1px solid var(--border);
  /* focus: */
  border-color: rgba(99,179,237,0.4);
  box-shadow: 0 0 0 3px rgba(99,179,237,0.08);
}
```

---

## 🔄 AOS Animation Config

```javascript
AOS.init({
  once: true,           // Animate only once (not on scroll back)
  duration: 750,        // 750ms animation duration
  easing: 'ease-out-cubic',
  offset: 60            // Trigger 60px before element enters viewport
});
```

### AOS Attributes Used
| Element | Animation | Delay |
|---|---|---|
| Hero left | `fade-right` | 0ms |
| Hero right | `fade-left` | 150ms |
| Section tags | `fade-up` | 0ms |
| Highlight cards | `zoom-in` | 0/80/160/240/320/400ms |
| Skill cards | `fade-up` | 0/100/200ms |
| Exp left | `fade-right` | 0ms |
| Exp right | `fade-left` | 0ms |
| Project cards | `zoom-in` / `fade-up` | 0/100/200ms |
| Cert cards | `zoom-in` | 0–300ms staggered |
| Contact cols | `fade-right` / `fade-left` | 0ms |

---

## 📱 Responsive Breakpoints

Uses Bootstrap 5 breakpoints:

| Breakpoint | Width | Changes |
|---|---|---|
| `xs` | <576px | Single column, stacked layout |
| `sm` | ≥576px | 2-column highlight/cert grid |
| `lg` | ≥992px | Full desktop layout, navbar links visible |

**Custom responsive override at 768px:**
```css
@media (max-width: 768px) {
  .hero-title { font-size: 2.8rem; }
  .tech-orb-grid { grid-template-columns: repeat(3, 1fr); }
  .navbar-collapse { background: rgba(4,5,10,0.95); backdrop-filter: blur(20px); }
}
```

---

## 🔧 JavaScript Functions Summary

| Function | Trigger | Purpose |
|---|---|---|
| Three.js `animate()` | `requestAnimationFrame` | 3D scene render loop |
| Cursor `animCursor()` | `requestAnimationFrame` | Smooth cursor ring follow |
| `IntersectionObserver` (skills) | Scroll | Trigger skill bar fill animation |
| `IntersectionObserver` (navbar) | Scroll 60px | Add `.scrolled` class to navbar |
| Card tilt | `mousemove` on `#tiltCard` | 3D perspective tilt |
| Card reset | `mouseleave` on `#tiltCard` | Reset to flat with `0.5s ease` |
| Cursor scale | `mouseenter`/`mouseleave` | Scale dot + ring on interactive elements |
| Form submit | `onclick` on `.btn-form-submit` | Show "Sent!" text feedback |
| `AOS.init()` | Page load | Initialize scroll animations |

---

*Last updated: 2026 · Moe Kyaw Aung · github.com/Dev-moe-kyawaung*
