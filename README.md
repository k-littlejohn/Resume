# Kaitlyn Littlejohn — Developer Portfolio

**BSc Computer Science · Minor in Economics · MacEwan University, Edmonton AB**

[![HTML](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![No Frameworks](https://img.shields.io/badge/No_Frameworks-22c55e?style=flat-square)](.)
[![Open to Work](https://img.shields.io/badge/Open_to_Opportunities-16a34a?style=flat-square)](mailto:kaitlyn.littlejohn@outlook.com)

> A handcrafted, zero-dependency developer portfolio. Custom cursor system, animated particle canvas, scroll-reveal animations, and a fully responsive layout, vanilla HTML, CSS, and JavaScript. No React. No Tailwind. No build step.

---

## Live Site

**[kaitlyn-littlejohn.github.io/Resume](https://k-littlejohn.github.io/Resume)**

---

## File Structure

```
kaitlyn-portfolio/
├── index.html        ← entry point, all content and sections
├── styles.css        ← design system, layout, animations, responsive
├── main.js           ← cursor, particle canvas, scroll reveal, nav
└── resume_pic.png    ← profile photo used in the About section
```

---

## Features

### Custom Cursor System
Two-element cursor — a 7px dot that snaps to position instantly, and a 34px ring that trails behind using a `0.11` lerp smoothing factor. On hover over interactive elements (links, buttons, cards, pills) the ring scales up and shifts to a brighter green.

### Animated Particle Canvas
A `<canvas>` element renders 120 floating particles in green and emerald tones. Particles within 115px of each other are connected by fading lines. Runs on `requestAnimationFrame` for smooth 60fps — zero libraries.

### Scroll Reveal Animations
`IntersectionObserver` watches every `.reveal` element and triggers a `fadeUp` transition on entry at a `0.1` threshold. Staggered delay classes (`.d1`, `.d2`, `.d3`) create cascading reveals within each section. Each element animates once and is immediately unobserved.

### Sticky Nav with Active Section Highlighting
After 50px of scroll the nav gains a frosted-glass backdrop (`backdrop-filter: blur` + semi-transparent background). A second `IntersectionObserver` tracks which section is in view at a `0.45` threshold and highlights the matching nav link in green.

### Project Card Mouse-Glow Effect
Each project card tracks the cursor via `mousemove` and writes `--mx` / `--my` CSS custom properties. A `radial-gradient` in the card's `::before` pseudo-element follows the cursor, creating a subtle green spotlight that follows your mouse across the card.

### Film Grain Texture
A fixed SVG `fractalNoise` filter overlay at 15% opacity with `mix-blend-mode: multiply` adds tactile depth to the background — no extra HTTP requests, no image assets.

---

## Tech Stack

| Category | Technologies |
|---|---|
| **Structure** | HTML5, semantic markup |
| **Styling** | CSS3, custom properties, Grid, Flexbox, `clamp()` |
| **Scripting** | Vanilla JS (ES2022+), Canvas API, `requestAnimationFrame` |
| **Browser APIs** | `IntersectionObserver`, `ScrollY`, `ResizeObserver` |
| **Typography** | Outfit (headings), DM Sans (body) via Google Fonts |
| **Effects** | SVG fractalNoise grain, `backdrop-filter`, radial gradients |

---

## Quick Start

**1. Download**
All four files (`index.html`, `styles.css`, `main.js`, `resume_pic.png`) must live in the same folder.

**2. Open locally**
Double-click `index.html` — no server, no install, no build step required. Works in any modern browser.

**3. Personalise**
All content lives in `index.html`. The entire colour theme is controlled by six variables at the top of `styles.css`:

```css
:root {
  --green:       #1a9e50;   /* primary accent */
  --green-light: #4ec97e;   /* scrollbar, hover highlights */
  --green-dark:  #0e7a3a;   /* button hover state */
  --green-pale:  #d4f5e2;   /* gradient backgrounds */
  --green-glow:  rgba(26,158,80,0.18);  /* shadow glow */
  --mint:        #e0f7ea;   /* hover fill backgrounds */
}
```

**4. Deploy**
Drag into [Netlify Drop](https://app.netlify.com/drop), push to GitHub and enable **GitHub Pages**, or connect to Vercel. No build command, no configuration needed.

---

## Projects Featured

| Project | Stack | Role |
|---|---|---|
| **ChalkItUp** — Android Tutoring App | Kotlin, Firebase, MVVM, Material Design 3 | UI/UX Lead |
| **Taktik** — Forex Strategy Simulator | Flutter, Dart, SQLite, REST API | UI/UX Lead |
| **Rentify** — Student Rental Platform | Next.js, React, Supabase, Vercel | Full-Stack |
| **Netflix Trend Dashboard** | Tableau | Data Viz |
| **Edmonton Housing Map** | Java, ArcGIS Maps SDK | GIS Desktop |

---

## Contact

| | |
|---|---|
| **Email** | [kaitlyn.littlejohn@outlook.com](mailto:kaitlyn.littlejohn@outlook.com) |
| **LinkedIn** | [linkedin.com/in/kaitlyn-littlejohn](https://linkedin.com/in/kaitlyn-littlejohn) |
| **GitHub** | [github.com/k-littlejohn](https://github.com/k-littlejohn) |
| **Tableau Public** | [public.tableau.com/app/profile/kaitlyn.littlejohn](https://public.tableau.com/app/profile/kaitlyn.littlejohn) |

---

*© 2026 Kaitlyn Littlejohn · Built with zero dependencies*
