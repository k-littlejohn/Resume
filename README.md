<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>README — Kaitlyn Littlejohn Portfolio</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet" />
  <style>
    /* ── RESET & BASE ─────────────────────────────────────────── */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg:        #0a0f0d;
      --bg2:       #0f1710;
      --bg3:       #141f15;
      --surface:   #1a2b1c;
      --surface2:  #1f3321;

      --green:     #22c55e;
      --green-dim: #16a34a;
      --green-pale:#bbf7d0;
      --green-glow:rgba(34,197,94,0.15);
      --green-line:rgba(34,197,94,0.25);

      --text:      #f0fdf4;
      --text2:     #a7c4aa;
      --muted:     #5a7a5e;
      --border:    rgba(34,197,94,0.12);
      --border2:   rgba(34,197,94,0.22);

      --mono:      'DM Mono', monospace;
      --sans:      'Outfit', sans-serif;
    }

    html { scroll-behavior: smooth; font-size: 16px; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--sans);
      font-weight: 400;
      line-height: 1.75;
      -webkit-font-smoothing: antialiased;
      overflow-x: hidden;
    }

    /* ── NOISE TEXTURE ────────────────────────────────────────── */
    body::before {
      content: '';
      position: fixed; inset: 0; z-index: 0;
      pointer-events: none;
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='200' height='200'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='200' height='200' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
      opacity: 0.4;
    }

    /* ── GLOW ORBS ────────────────────────────────────────────── */
    .orb {
      position: fixed; border-radius: 50%;
      filter: blur(120px); pointer-events: none; z-index: 0;
    }
    .orb-1 {
      width: 600px; height: 600px;
      background: radial-gradient(circle, rgba(34,197,94,0.06), transparent 70%);
      top: -200px; left: -100px;
    }
    .orb-2 {
      width: 400px; height: 400px;
      background: radial-gradient(circle, rgba(34,197,94,0.04), transparent 70%);
      bottom: 100px; right: -100px;
    }

    /* ── LAYOUT ───────────────────────────────────────────────── */
    .wrap {
      position: relative; z-index: 1;
      max-width: 860px;
      margin: 0 auto;
      padding: 80px 40px 120px;
    }

    /* ── HEADER ───────────────────────────────────────────────── */
    .readme-header {
      border: 1px solid var(--border2);
      border-radius: 16px;
      background: var(--bg2);
      padding: 52px 56px;
      margin-bottom: 56px;
      position: relative;
      overflow: hidden;
    }
    .readme-header::before {
      content: '';
      position: absolute; inset: 0;
      background: linear-gradient(135deg, rgba(34,197,94,0.05) 0%, transparent 60%);
      pointer-events: none;
    }
    .readme-badge-row {
      display: flex; gap: 10px; flex-wrap: wrap;
      margin-bottom: 28px;
    }
    .badge {
      font-family: var(--mono);
      font-size: 0.7rem;
      padding: 4px 12px;
      border-radius: 100px;
      border: 1px solid var(--green-line);
      color: var(--green);
      background: rgba(34,197,94,0.07);
      letter-spacing: 0.05em;
    }
    .badge.dim {
      color: var(--muted);
      border-color: rgba(255,255,255,0.08);
      background: rgba(255,255,255,0.03);
    }
    .readme-title {
      font-size: 2.6rem;
      font-weight: 800;
      letter-spacing: -0.02em;
      line-height: 1.1;
      margin-bottom: 16px;
      color: var(--text);
    }
    .readme-title span { color: var(--green); }
    .readme-subtitle {
      font-size: 1.05rem;
      color: var(--text2);
      font-weight: 300;
      max-width: 560px;
      line-height: 1.75;
    }

    /* ── SECTION HEADINGS ─────────────────────────────────────── */
    .section {
      margin-bottom: 52px;
    }
    .section-label {
      display: flex;
      align-items: center;
      gap: 14px;
      margin-bottom: 24px;
    }
    .section-label .tag {
      font-family: var(--mono);
      font-size: 0.65rem;
      color: var(--green);
      letter-spacing: 0.2em;
      text-transform: uppercase;
      font-weight: 500;
    }
    .section-label .line {
      flex: 1;
      height: 1px;
      background: var(--border);
    }
    .section-label .num {
      font-family: var(--mono);
      font-size: 0.65rem;
      color: var(--muted);
    }

    /* ── OVERVIEW GRID ────────────────────────────────────────── */
    .overview-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 16px;
    }
    .overview-card {
      background: var(--bg2);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 28px 30px;
      transition: border-color 0.3s, background 0.3s;
    }
    .overview-card:hover {
      border-color: var(--border2);
      background: var(--bg3);
    }
    .overview-card h3 {
      font-size: 0.88rem;
      font-weight: 700;
      color: var(--text);
      margin-bottom: 6px;
      letter-spacing: 0.01em;
    }
    .overview-card p {
      font-size: 0.84rem;
      color: var(--text2);
      font-weight: 300;
      line-height: 1.65;
    }

    /* ── FILE TREE ────────────────────────────────────────────── */
    .file-tree {
      background: var(--bg2);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 32px 36px;
      font-family: var(--mono);
      font-size: 0.85rem;
    }
    .file-tree .tree-header {
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 20px;
      padding-bottom: 16px;
      border-bottom: 1px solid var(--border);
    }
    .tree-header .dots { display: flex; gap: 6px; }
    .tree-header .dot {
      width: 10px; height: 10px; border-radius: 50%;
    }
    .dot-r { background: #ff5f57; }
    .dot-y { background: #febc2e; }
    .dot-g { background: #28c840; }
    .tree-header .filename {
      font-size: 0.72rem; color: var(--muted); margin-left: auto;
    }
    .tree-line {
      display: flex;
      align-items: center;
      gap: 10px;
      padding: 4px 0;
      color: var(--text2);
    }
    .tree-line .indent { color: var(--muted); user-select: none; }
    .tree-line .fname { color: var(--text); }
    .tree-line .fname.green { color: var(--green); }
    .tree-line .fname.dim { color: var(--muted); }
    .tree-line .comment {
      margin-left: auto;
      font-size: 0.75rem;
      color: var(--muted);
    }

    /* ── FEATURE LIST ─────────────────────────────────────────── */
    .feature-list {
      display: flex;
      flex-direction: column;
      gap: 12px;
    }
    .feature-item {
      display: flex;
      gap: 16px;
      align-items: flex-start;
      background: var(--bg2);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 20px 24px;
      transition: border-color 0.25s;
    }
    .feature-item .fi-body h4 {
      font-size: 0.92rem;
      font-weight: 600;
      color: var(--text);
      margin-bottom: 4px;
    }
    .feature-item .fi-body p {
      font-size: 0.83rem;
      color: var(--text2);
      font-weight: 300;
      line-height: 1.6;
    }
    .feature-item .fi-tag {
      margin-left: auto;
      flex-shrink: 0;
      font-family: var(--mono);
      font-size: 0.68rem;
      color: var(--green);
      background: rgba(34,197,94,0.07);
      border: 1px solid var(--green-line);
      padding: 3px 10px;
      border-radius: 100px;
      align-self: flex-start;
    }

    /* ── CODE BLOCK ───────────────────────────────────────────── */
    .code-block {
      background: var(--bg2);
      border: 1px solid var(--border);
      border-radius: 12px;
      overflow: hidden;
    }
    .code-block .cb-header {
      display: flex;
      align-items: center;
      gap: 8px;
      padding: 12px 20px;
      border-bottom: 1px solid var(--border);
      background: rgba(0,0,0,0.2);
    }
    .cb-header .dots { display: flex; gap: 5px; }
    .cb-header .dot { width: 9px; height: 9px; border-radius: 50%; }
    .cb-header .lang {
      margin-left: auto;
      font-family: var(--mono);
      font-size: 0.68rem;
      color: var(--muted);
    }
    .code-block pre {
      padding: 24px 28px;
      font-family: var(--mono);
      font-size: 0.82rem;
      line-height: 1.85;
      color: var(--text2);
      overflow-x: auto;
    }
    .code-block .kw  { color: var(--green); }
    .code-block .str { color: #86efac; }
    .code-block .cm  { color: var(--muted); font-style: italic; }
    .code-block .val { color: #fde68a; }

    /* ── TECH STACK ───────────────────────────────────────────── */
    .tech-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 12px;
    }
    .tech-card {
      background: var(--bg2);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 20px 22px;
      transition: border-color 0.25s, transform 0.2s;
    }
    .tech-card:hover {
      border-color: var(--border2);
      transform: translateY(-2px);
    }
    .tech-card .tc-label {
      font-family: var(--mono);
      font-size: 0.65rem;
      color: var(--muted);
      letter-spacing: 0.14em;
      text-transform: uppercase;
      margin-bottom: 10px;
    }
    .tech-card .tc-items {
      display: flex; flex-wrap: wrap; gap: 6px;
    }
    .tc-pill {
      font-size: 0.75rem;
      font-weight: 500;
      color: var(--text2);
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
      padding: 3px 10px;
      border-radius: 4px;
    }
    .tc-pill.hi {
      color: var(--green);
      background: rgba(34,197,94,0.07);
      border-color: var(--green-line);
    }

    /* ── QUICK START ──────────────────────────────────────────── */
    .steps {
      display: flex;
      flex-direction: column;
      gap: 0;
      position: relative;
    }
    .steps::before {
      content: '';
      position: absolute;
      left: 20px; top: 40px; bottom: 40px;
      width: 1px;
      background: var(--border);
    }
    .step {
      display: flex;
      gap: 20px;
      align-items: flex-start;
      padding: 20px 0;
    }
    .step-num {
      width: 40px; height: 40px;
      border-radius: 50%;
      background: var(--bg2);
      border: 1px solid var(--border2);
      display: flex; align-items: center; justify-content: center;
      font-family: var(--mono); font-size: 0.75rem;
      color: var(--green); flex-shrink: 0;
      position: relative; z-index: 1;
    }
    .step-body h4 {
      font-size: 0.92rem; font-weight: 600;
      color: var(--text); margin-bottom: 6px;
    }
    .step-body p {
      font-size: 0.83rem; color: var(--text2);
      font-weight: 300; line-height: 1.6;
    }
    .step-body code {
      font-family: var(--mono); font-size: 0.8rem;
      color: var(--green); background: rgba(34,197,94,0.07);
      padding: 2px 8px; border-radius: 4px;
      border: 1px solid var(--green-line);
    }

    /* ── CONTACT STRIP ────────────────────────────────────────── */
    .contact-strip {
      background: var(--bg2);
      border: 1px solid var(--border2);
      border-radius: 14px;
      padding: 36px 40px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 24px;
      flex-wrap: wrap;
    }
    .contact-strip .cs-left h3 {
      font-size: 1.1rem; font-weight: 700;
      color: var(--text); margin-bottom: 6px;
    }
    .contact-strip .cs-left p {
      font-size: 0.85rem; color: var(--text2);
      font-weight: 300;
    }
    .contact-links {
      display: flex; gap: 10px; flex-wrap: wrap;
    }
    .contact-link {
      display: inline-flex; align-items: center; gap: 7px;
      font-size: 0.8rem; font-weight: 600;
      text-decoration: none;
      padding: 9px 18px; border-radius: 8px;
      transition: all 0.2s;
    }
    .contact-link.primary {
      background: var(--green); color: #031a08;
    }
    .contact-link.primary:hover { background: #16a34a; }
    .contact-link.secondary {
      background: rgba(34,197,94,0.07);
      border: 1px solid var(--green-line);
      color: var(--green);
    }
    .contact-link.secondary:hover {
      background: rgba(34,197,94,0.14);
    }

    /* ── FOOTER ───────────────────────────────────────────────── */
    .readme-footer {
      margin-top: 64px;
      padding-top: 32px;
      border-top: 1px solid var(--border);
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 12px;
    }
    .readme-footer .fl {
      font-family: var(--mono);
      font-size: 0.72rem;
      color: var(--muted);
    }
    .readme-footer .fr {
      font-family: var(--mono);
      font-size: 0.72rem;
      color: var(--muted);
    }
    .readme-footer .fr span { color: var(--green); }

    /* ── INLINE NOTE ──────────────────────────────────────────── */
    .note-box {
      background: rgba(34,197,94,0.05);
      border: 1px solid var(--green-line);
      border-left: 3px solid var(--green);
      border-radius: 0 8px 8px 0;
      padding: 16px 20px;
      margin-bottom: 24px;
    }
    .note-box p {
      font-size: 0.85rem;
      color: var(--text2);
      font-weight: 300;
      line-height: 1.65;
    }
    .note-box p strong { color: var(--green); font-weight: 600; }

    /* ── DIVIDER ──────────────────────────────────────────────── */
    .divider {
      height: 1px;
      background: var(--border);
      margin: 48px 0;
    }

    /* ── RESPONSIVE ───────────────────────────────────────────── */
    @media (max-width: 680px) {
      .wrap { padding: 40px 20px 80px; }
      .readme-header { padding: 36px 28px; }
      .readme-title { font-size: 1.9rem; }
      .overview-grid { grid-template-columns: 1fr; }
      .tech-grid { grid-template-columns: 1fr 1fr; }
      .contact-strip { flex-direction: column; }
    }
    @media (max-width: 480px) {
      .tech-grid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

  <div class="orb orb-1"></div>
  <div class="orb orb-2"></div>

  <div class="wrap">

    <!-- ══ HEADER ══════════════════════════════════════════════ -->
    <header class="readme-header">
      <div class="readme-badge-row">
        <span class="badge">v1.0.0</span>
        <span class="badge">Vanilla HTML / CSS / JS</span>
        <span class="badge">No Frameworks</span>
        <span class="badge dim">Open to Opportunities</span>
      </div>
      <h1 class="readme-title">
        kaitlyn-littlejohn<br>
        <span>/ portfolio</span>
      </h1>
      <p class="readme-subtitle">
        A handcrafted, zero-dependency developer portfolio. Custom cursor system, 
        animated particle canvas, scroll-reveal animations, and responsive layout — 
        all written from scratch in vanilla HTML, CSS, and JavaScript.
      </p>
    </header>

    <!-- ══ OVERVIEW ════════════════════════════════════════════ -->
    <section class="section">
      <div class="section-label">
        <span class="tag">Overview</span>
        <span class="line"></span>
        <span class="num">01</span>
      </div>

      <div class="overview-grid">
        <div class="overview-card">
          
          <h3>Zero-Dependency Design</h3>
          <p>No React, no Tailwind, no build step. Every animation, layout, and interaction is pure CSS and vanilla JavaScript — intentional craft, not boilerplate.</p>
        </div>
        <div class="overview-card">
          
          <h3>Instant Load</h3>
          <p>No bundler, no node_modules, no framework overhead. Open index.html in any browser and it runs. Deploy anywhere — GitHub Pages, Netlify, Vercel — in seconds.</p>
        </div>
        <div class="overview-card">
          
          <h3>Fully Responsive</h3>
          <p>Three-tier responsive breakpoints: desktop (1280px+), tablet (900px), and mobile (580px). Every section reflows gracefully across screen sizes.</p>
        </div>
        <div class="overview-card">
          
          <h3>Emerald Green Theme</h3>
          <p>Cohesive design system built on CSS custom properties — green accent palette, dark tones, and grain texture. Swap the palette in six variable definitions.</p>
        </div>
      </div>
    </section>

    <!-- ══ FILE STRUCTURE ═══════════════════════════════════════ -->
    <section class="section">
      <div class="section-label">
        <span class="tag">File Structure</span>
        <span class="line"></span>
        <span class="num">02</span>
      </div>

      <div class="file-tree">
        <div class="tree-header">
          <div class="dots">
            <div class="dot dot-r"></div>
            <div class="dot dot-y"></div>
            <div class="dot dot-g"></div>
          </div>
          <span class="filename">kaitlyn-portfolio/</span>
        </div>
        <div class="tree-line">
          <span class="indent">│</span>
          <span class="fname green">kaitlyn-portfolio/</span>
        </div>
        <div class="tree-line">
          <span class="indent">│  ├──</span>
          <span class="fname green">index.html</span>
          <span class="comment">← entry point, all content</span>
        </div>
        <div class="tree-line">
          <span class="indent">│  ├──</span>
          <span class="fname green">styles.css</span>
          <span class="comment">← design system, layout, animations</span>
        </div>
        <div class="tree-line">
          <span class="indent">│  ├──</span>
          <span class="fname green">main.js</span>
          <span class="comment">← cursor, canvas, scroll, nav</span>
        </div>
        <div class="tree-line">
          <span class="indent">│  ├──</span>
          <span class="fname">resume_pic.png</span>
          <span class="comment">← profile photo (About section)</span>
        </div>
        <div class="tree-line">
          <span class="indent">│  └──</span>
          <span class="fname dim">README.html</span>
          <span class="comment">← this file</span>
        </div>
      </div>
    </section>

    <!-- ══ FEATURES ════════════════════════════════════════════ -->
    <section class="section">
      <div class="section-label">
        <span class="tag">Features</span>
        <span class="line"></span>
        <span class="num">03</span>
      </div>

      <div class="feature-list">
        <div class="feature-item">
          
          <div class="fi-body">
            <h4>Custom Cursor System</h4>
            <p>A two-element cursor — a precise 7px dot that snaps to position, and a 34px ring that trails behind with a 0.11 lerp smoothing factor. The ring scales up and brightens on hover over interactive elements (links, buttons, cards, pills).</p>
          </div>
          <span class="fi-tag">CSS + JS</span>
        </div>
        <div class="feature-item">
          
          <div class="fi-body">
            <h4>Animated Particle Canvas</h4>
            <p>WebGL-style canvas rendering 120 floating particles in green and emerald tones. Adjacent particles within 115px are connected by fading lines. Runs on <code style="font-family:var(--mono);color:var(--green);font-size:0.8rem">requestAnimationFrame</code> for smooth 60fps performance.</p>
          </div>
          <span class="fi-tag">Canvas API</span>
        </div>
        <div class="feature-item">
          
          <div class="fi-body">
            <h4>Scroll Reveal Animations</h4>
            <p>IntersectionObserver watches every <code style="font-family:var(--mono);color:var(--green);font-size:0.8rem">.reveal</code> element and triggers a <code style="font-family:var(--mono);color:var(--green);font-size:0.8rem">fadeUp</code> transition on entry. Staggered delays (<code style="font-family:var(--mono);color:var(--green);font-size:0.8rem">.d1</code>, <code style="font-family:var(--mono);color:var(--green);font-size:0.8rem">.d2</code>, <code style="font-family:var(--mono);color:var(--green);font-size:0.8rem">.d3</code>) create cascading reveals within sections. Each element animates once and is unobserved.</p>
          </div>
          <span class="fi-tag">Intersection Observer</span>
        </div>
        <div class="feature-item">
          
          <div class="fi-body">
            <h4>Sticky Nav with Active Highlighting</h4>
            <p>Nav gains a frosted-glass backdrop (backdrop-filter blur + semi-transparent background) after 50px scroll. A second IntersectionObserver tracks active sections and highlights the corresponding nav link in green at 45% viewport threshold.</p>
          </div>
          <span class="fi-tag">Scroll + Observer</span>
        </div>
        <div class="feature-item">
          
          <div class="fi-body">
            <h4>Project Card Mouse-Glow</h4>
            <p>Each project card tracks cursor position via <code style="font-family:var(--mono);color:var(--green);font-size:0.8rem">mousemove</code> and sets <code style="font-family:var(--mono);color:var(--green);font-size:0.8rem">--mx</code> / <code style="font-family:var(--mono);color:var(--green);font-size:0.8rem">--my</code> CSS custom properties. A radial gradient in the card's <code style="font-family:var(--mono);color:var(--green);font-size:0.8rem">::before</code> pseudo-element follows the cursor, creating a subtle spotlight effect on hover.</p>
          </div>
          <span class="fi-tag">CSS Variables + JS</span>
        </div>
        <div class="feature-item">
          
          <div class="fi-body">
            <h4>Film Grain Texture</h4>
            <p>A fixed SVG fractalNoise filter overlaid across the entire page at 15% opacity with <code style="font-family:var(--mono);color:var(--green);font-size:0.8rem">mix-blend-mode: multiply</code>. Adds tactile depth without adding any HTTP requests or image assets.</p>
          </div>
          <span class="fi-tag">SVG Filter</span>
        </div>
      </div>
    </section>

    <!-- ══ TECH STACK ═══════════════════════════════════════════ -->
    <section class="section">
      <div class="section-label">
        <span class="tag">Tech Stack</span>
        <span class="line"></span>
        <span class="num">04</span>
      </div>

      <div class="note-box">
        <p><strong>No build tools. No package.json. No node_modules.</strong> This project has zero runtime dependencies. Everything ships as three plain files that any browser can open directly.</p>
      </div>

      <div class="tech-grid">
        <div class="tech-card">
          <div class="tc-label">Structure</div>
          <div class="tc-items">
            <span class="tc-pill hi">HTML5</span>
            <span class="tc-pill">Semantic markup</span>
            <span class="tc-pill">ARIA labels</span>
          </div>
        </div>
        <div class="tech-card">
          <div class="tc-label">Styling</div>
          <div class="tc-items">
            <span class="tc-pill hi">CSS3</span>
            <span class="tc-pill">Custom Properties</span>
            <span class="tc-pill">Grid + Flexbox</span>
            <span class="tc-pill">clamp()</span>
          </div>
        </div>
        <div class="tech-card">
          <div class="tc-label">Scripting</div>
          <div class="tc-items">
            <span class="tc-pill hi">ES2022+</span>
            <span class="tc-pill">Canvas API</span>
            <span class="tc-pill">requestAnimationFrame</span>
          </div>
        </div>
        <div class="tech-card">
          <div class="tc-label">Browser APIs</div>
          <div class="tc-items">
            <span class="tc-pill hi">IntersectionObserver</span>
            <span class="tc-pill">ScrollY</span>
            <span class="tc-pill">ResizeObserver</span>
          </div>
        </div>
        <div class="tech-card">
          <div class="tc-label">Typography</div>
          <div class="tc-items">
            <span class="tc-pill hi">Outfit</span>
            <span class="tc-pill">DM Sans</span>
            <span class="tc-pill">Google Fonts</span>
          </div>
        </div>
        <div class="tech-card">
          <div class="tc-label">Effects</div>
          <div class="tc-items">
            <span class="tc-pill hi">SVG fractalNoise</span>
            <span class="tc-pill">backdrop-filter</span>
            <span class="tc-pill">radial-gradient</span>
          </div>
        </div>
      </div>
    </section>

    <!-- ══ QUICK START ══════════════════════════════════════════ -->
    <section class="section">
      <div class="section-label">
        <span class="tag">Quick Start</span>
        <span class="line"></span>
        <span class="num">05</span>
      </div>

      <div class="steps">
        <div class="step">
          <div class="step-num">01</div>
          <div class="step-body">
            <h4>Download the files</h4>
            <p>All three files — <code>index.html</code>, <code>styles.css</code>, and <code>main.js</code> — must live in the same folder alongside <code>resume_pic.png</code>.</p>
          </div>
        </div>
        <div class="step">
          <div class="step-num">02</div>
          <div class="step-body">
            <h4>Open locally</h4>
            <p>Double-click <code>index.html</code> to open in any modern browser. No server required. The custom cursor is hidden on touch devices automatically.</p>
          </div>
        </div>
        <div class="step">
          <div class="step-num">03</div>
          <div class="step-body">
            <h4>Personalise</h4>
            <p>All content is in <code>index.html</code>. All colours live in <code>:root</code> variables at the top of <code>styles.css</code> — change <code>--green</code> to any accent colour and the whole theme updates.</p>
          </div>
        </div>
        <div class="step">
          <div class="step-num">04</div>
          <div class="step-body">
            <h4>Deploy</h4>
            <p>Drag the folder into <code>Netlify Drop</code>, push to a GitHub repo and enable <code>GitHub Pages</code>, or connect to Vercel. No build command, no configuration — publish as-is.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- ══ HOW TO CUSTOMISE ═════════════════════════════════════ -->
    <section class="section">
      <div class="section-label">
        <span class="tag">Customisation</span>
        <span class="line"></span>
        <span class="num">06</span>
      </div>

      <div class="code-block">
        <div class="cb-header">
          <div class="dots">
            <div class="dot dot-r"></div>
            <div class="dot dot-y"></div>
            <div class="dot dot-g"></div>
          </div>
          <span class="lang">styles.css — :root</span>
        </div>
        <pre><span class="cm">/* ── Change the entire colour theme in 6 lines ── */</span>
<span class="kw">:root</span> {
  <span class="cm">/* Swap --green to any colour (hex, hsl, oklch) */</span>
  <span class="val">--green</span>:       <span class="str">#1a9e50</span>;   <span class="cm">/* primary accent */</span>
  <span class="val">--green-light</span>: <span class="str">#4ec97e</span>;   <span class="cm">/* scrollbar, hover highlights */</span>
  <span class="val">--green-dark</span>:  <span class="str">#0e7a3a</span>;   <span class="cm">/* button hover state */</span>
  <span class="val">--green-pale</span>:  <span class="str">#d4f5e2</span>;   <span class="cm">/* gradient background */</span>
  <span class="val">--green-glow</span>:  <span class="str">rgba(26,158,80,0.18)</span>;  <span class="cm">/* shadow glow */</span>
  <span class="val">--mint</span>:        <span class="str">#e0f7ea</span>;   <span class="cm">/* hover backgrounds */</span>

  <span class="cm">/* Fonts — loaded from Google Fonts in &lt;head&gt; */</span>
  <span class="val">--hf</span>: <span class="str">'Outfit'</span>, sans-serif;   <span class="cm">/* display headings */</span>
  <span class="val">--bf</span>: <span class="str">'DM Sans'</span>, sans-serif;   <span class="cm">/* body text */</span>
}</pre>
      </div>
    </section>

    <div class="divider"></div>

    <!-- ══ CONTACT ══════════════════════════════════════════════ -->
    <section class="section">
      <div class="section-label">
        <span class="tag">Get In Touch</span>
        <span class="line"></span>
        <span class="num">07</span>
      </div>

      <div class="contact-strip">
        <div class="cs-left">
          <h3>Kaitlyn Littlejohn</h3>
          <p>BSc Computer Science · Minor in Economics · MacEwan University, Edmonton AB<br>
          Open to full-time roles in software development, data analytics, and front-end engineering.</p>
        </div>
        <div class="contact-links">
          <a href="mailto:kaitlyn.littlejohn@outlook.com" class="contact-link primary">Email Me</a>
          <a href="https://linkedin.com/in/kaitlyn-littlejohn" target="_blank" class="contact-link secondary">LinkedIn</a>
          <a href="https://github.com/k-littlejohn" target="_blank" class="contact-link secondary">GitHub</a>
          <a href="https://public.tableau.com/app/profile/kaitlyn.littlejohn" target="_blank" class="contact-link secondary">Tableau</a>
        </div>
      </div>
    </section>

    <!-- ══ FOOTER ════════════════════════════════════════════════ -->
    <footer class="readme-footer">
      <span class="fl">README.html · kaitlyn-littlejohn / portfolio</span>
      <span class="fr">Built with care and zero dependencies · © 2026 Kaitlyn Littlejohn</span>
    </footer>

  </div>
</body>
</html>