# portpolio
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Daihn Kim — Deployment Strategist</title>
<meta name="description" content="Portfolio of Daihn Kim — Deployment Strategist who turns ambiguous business problems into working deployed systems.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
<style>
/* ─────────────────────────────────────────────
   DESIGN TOKENS
───────────────────────────────────────────── */
:root {
  --bg:         #161616;
  --surface:    #1e1e1e;
  --surface-2:  #252525;
  --border:     #2d2d2d;
  --accent:     #e84040;
  --accent-dim: rgba(232,64,64,0.12);
  --accent-dim2:rgba(232,64,64,0.06);
  --text:       #f5f5f5;
  --text-2:     #999999;
  --text-3:     #555555;
  --green:      #64c864;
  --green-dim:  rgba(100,200,100,0.10);
  --red-dim:    rgba(255,80,80,0.08);
  --yellow:     #ffb400;
  --radius:     12px;
  --radius-lg:  20px;
  --max-w:      1200px;
  --gap:        24px;
  --py:         120px;
  --font:       'Inter', -apple-system, sans-serif;
  --ease:       0.25s ease;
}

/* ─────────────────────────────────────────────
   RESET
───────────────────────────────────────────── */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; font-size: 16px; }
body { background: var(--bg); color: var(--text); font-family: var(--font); line-height: 1.6; overflow-x: hidden; -webkit-font-smoothing: antialiased; }
a { color: inherit; text-decoration: none; }
img { display: block; max-width: 100%; height: auto; }
button { font-family: inherit; cursor: pointer; border: none; background: none; }

/* ─────────────────────────────────────────────
   TYPOGRAPHY
───────────────────────────────────────────── */
h1 { font-size: clamp(3.5rem, 9vw, 7.5rem); font-weight: 900; line-height: 0.95; letter-spacing: -0.03em; }
h2 { font-size: clamp(2rem, 5vw, 4rem); font-weight: 900; line-height: 1.05; letter-spacing: -0.025em; }
h3 { font-size: clamp(1.1rem, 2.2vw, 1.4rem); font-weight: 800; letter-spacing: -0.01em; }
h4 { font-size: 1rem; font-weight: 700; color: var(--text); }
p { color: var(--text-2); line-height: 1.75; }
.label {
  font-size: 0.72rem; font-weight: 800;
  letter-spacing: 0.16em; text-transform: uppercase;
  color: var(--accent);
}

/* ─────────────────────────────────────────────
   LAYOUT
───────────────────────────────────────────── */
.container { max-width: var(--max-w); margin: 0 auto; padding: 0 48px; }
.section   { padding: var(--py) 0; }
.divider   { border: none; border-top: 1px solid var(--border); }

/* ─────────────────────────────────────────────
   NAVIGATION
───────────────────────────────────────────── */
#nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 200;
  padding: 22px 0;
  transition: background var(--ease), border-color var(--ease), padding var(--ease);
  border-bottom: 1px solid transparent;
}
#nav.scrolled {
  background: rgba(22,22,22,0.92);
  backdrop-filter: blur(16px);
  border-color: var(--border);
  padding: 16px 0;
}
.nav-inner { display: flex; align-items: center; justify-content: space-between; }
.nav-logo {
  font-size: 1.2rem; font-weight: 900; letter-spacing: -0.02em;
  display: flex; align-items: center; gap: 2px;
}
.nav-logo .dot { color: var(--accent); }
.nav-links { display: flex; align-items: center; gap: 36px; }
.nav-links a { font-size: 0.82rem; font-weight: 600; color: var(--text-2); transition: color var(--ease); }
.nav-links a:hover { color: var(--text); }
.nav-cta {
  padding: 9px 22px; background: var(--accent); color: #fff !important;
  border-radius: 7px; font-size: 0.82rem; font-weight: 800;
  transition: background var(--ease), transform var(--ease);
  letter-spacing: 0.02em;
}
.nav-cta:hover { background: #ff5252; transform: translateY(-1px); }

/* ─────────────────────────────────────────────
   HERO
───────────────────────────────────────────── */
#hero {
  min-height: 100vh; display: flex; flex-direction: column;
  justify-content: center; padding-top: 120px; position: relative; overflow: hidden;
}
.hero-glow {
  position: absolute; top: 20%; right: -10%; width: 60vw; height: 60vw;
  max-width: 800px; max-height: 800px;
  background: radial-gradient(circle, rgba(232,64,64,0.09) 0%, transparent 65%);
  pointer-events: none; z-index: 0;
}
.hero-grid {
  position: absolute; inset: 0; z-index: 0; opacity: 0.03;
  background-image:
    linear-gradient(rgba(255,255,255,0.5) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,0.5) 1px, transparent 1px);
  background-size: 60px 60px;
}
.hero-content { position: relative; z-index: 1; max-width: 900px; }
.hero-label { margin-bottom: 28px; display: flex; align-items: center; gap: 12px; }
.hero-label::after {
  content: ''; flex: 1; max-width: 60px; height: 1px; background: var(--accent); opacity: 0.4;
}
.hero-name { color: var(--text); margin-bottom: 28px; }
.hero-name em { font-style: normal; color: var(--accent); }
.hero-tagline {
  font-size: clamp(1.05rem, 2vw, 1.35rem); font-weight: 600; color: var(--text-2);
  max-width: 560px; margin-bottom: 52px; line-height: 1.55;
}
.hero-stats { display: flex; gap: 52px; margin-bottom: 48px; }
.hero-stat-num {
  font-size: 2.8rem; font-weight: 900; color: var(--accent); line-height: 1;
  letter-spacing: -0.03em;
}
.hero-stat-label { font-size: 0.75rem; color: var(--text-3); font-weight: 600; letter-spacing: 0.06em; margin-top: 5px; text-transform: uppercase; }
.hero-actions { display: flex; gap: 14px; }
.btn {
  display: inline-flex; align-items: center; gap: 8px;
  padding: 14px 32px; border-radius: 8px; font-size: 0.9rem; font-weight: 700;
  transition: all var(--ease); letter-spacing: 0.01em;
}
.btn-primary { background: var(--accent); color: #fff; }
.btn-primary:hover { background: #ff5252; transform: translateY(-2px); box-shadow: 0 12px 32px rgba(232,64,64,0.3); }
.btn-ghost { border: 1px solid var(--border); color: var(--text-2); }
.btn-ghost:hover { border-color: var(--text-3); color: var(--text); }
.hero-scroll {
  position: absolute; bottom: 48px; left: 50%; transform: translateX(-50%);
  display: flex; flex-direction: column; align-items: center; gap: 10px;
  color: var(--text-3); font-size: 0.65rem; font-weight: 800; letter-spacing: 0.18em;
  text-transform: uppercase;
}
.scroll-bar {
  width: 1px; height: 48px;
  background: linear-gradient(to bottom, var(--accent), transparent);
  animation: scrollFade 2.4s ease-in-out infinite;
}
@keyframes scrollFade { 0%,100%{opacity:1;transform:scaleY(1)} 50%{opacity:0.3;transform:scaleY(0.6)} }

/* ─────────────────────────────────────────────
   ABOUT
───────────────────────────────────────────── */
#about { border-top: 1px solid var(--border); }
.about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 80px; align-items: start; }
.about-bio h2 { margin: 20px 0 24px; }
.about-bio p { margin-bottom: 14px; }
.cap-list { display: flex; flex-direction: column; gap: 10px; margin-top: 32px; }
.cap-item {
  display: flex; align-items: flex-start; gap: 14px;
  padding: 14px 18px; background: var(--surface); border-radius: 10px;
  border: 1px solid var(--border);
}
.cap-dot { width: 7px; height: 7px; background: var(--accent); border-radius: 50%; flex-shrink: 0; margin-top: 6px; }
.cap-item span { font-size: 0.875rem; color: var(--text-2); line-height: 1.55; }
.skills-label { margin-bottom: 18px; }
.skills-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
.skill-card {
  padding: 18px; background: var(--surface); border-radius: var(--radius);
  border: 1px solid var(--border);
}
.skill-cat { font-size: 0.65rem; font-weight: 800; letter-spacing: 0.14em; text-transform: uppercase; color: var(--accent); margin-bottom: 10px; }
.skill-tags { display: flex; flex-wrap: wrap; gap: 6px; }
.skill-tag {
  padding: 4px 10px; background: var(--surface-2);
  border-radius: 5px; font-size: 0.78rem; color: var(--text-2); font-weight: 500;
}

/* ─────────────────────────────────────────────
   PROJECT OVERVIEW GRID
───────────────────────────────────────────── */
#projects { border-top: 1px solid var(--border); }
.sec-header { display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 56px; }
.sec-header p { max-width: 280px; text-align: right; font-size: 0.9rem; }
.proj-grid { display: grid; grid-template-columns: repeat(3,1fr); gap: var(--gap); }
.proj-card {
  padding: 32px; background: var(--surface); border-radius: var(--radius-lg);
  border: 1px solid var(--border); cursor: pointer;
  transition: border-color var(--ease), transform var(--ease), box-shadow var(--ease);
  display: flex; flex-direction: column;
}
.proj-card:hover {
  border-color: var(--accent); transform: translateY(-5px);
  box-shadow: 0 24px 48px rgba(0,0,0,0.5), 0 0 0 1px rgba(232,64,64,0.15);
}
.proj-num { font-size: 0.7rem; font-weight: 800; color: var(--text-3); margin-bottom: 18px; letter-spacing: 0.1em; }
.proj-title { font-size: 1.2rem; font-weight: 800; margin-bottom: 8px; line-height: 1.3; letter-spacing: -0.01em; }
.proj-period { font-size: 0.78rem; color: var(--accent); font-weight: 700; margin-bottom: 18px; }
.proj-desc { font-size: 0.87rem; color: var(--text-2); flex: 1; margin-bottom: 24px; line-height: 1.7; }
.proj-metric {
  padding: 14px 18px; border-radius: 9px; margin-bottom: 18px;
  background: var(--accent-dim); border-left: 3px solid var(--accent);
}
.proj-metric.wip { background: rgba(255,180,0,0.08); border-color: var(--yellow); }
.proj-metric-val { font-size: 1.35rem; font-weight: 900; color: var(--accent); letter-spacing: -0.02em; }
.proj-metric.wip .proj-metric-val { color: var(--yellow); }
.proj-metric-label { font-size: 0.73rem; color: var(--text-2); margin-top: 2px; }
.proj-tags { display: flex; flex-wrap: wrap; gap: 6px; }
.proj-tag { padding: 4px 10px; background: var(--surface-2); border-radius: 5px; font-size: 0.73rem; color: var(--text-3); }
.proj-arrow { display: flex; align-items: center; gap: 8px; font-size: 0.82rem; font-weight: 800; color: var(--accent); margin-top: 20px; letter-spacing: 0.02em; }

/* ─────────────────────────────────────────────
   PROJECT DETAIL SECTIONS
───────────────────────────────────────────── */
.proj-detail { border-top: 1px solid var(--border); padding: var(--py) 0; }

/* Meta + Header */
.pd-meta { display: flex; gap: 32px; margin-bottom: 28px; flex-wrap: wrap; align-items: center; }
.pd-meta-item { display: flex; flex-direction: column; gap: 4px; }
.pd-meta-key { font-size: 0.63rem; font-weight: 800; letter-spacing: 0.13em; text-transform: uppercase; color: var(--text-3); }
.pd-meta-val { font-size: 0.88rem; font-weight: 700; color: var(--text); }
.badge {
  display: inline-flex; align-items: center; gap: 6px;
  padding: 5px 12px; border-radius: 20px; font-size: 0.72rem; font-weight: 800; letter-spacing: 0.04em;
}
.badge-live { background: var(--green-dim); color: var(--green); border: 1px solid rgba(100,200,100,0.3); }
.badge-wip  { background: rgba(255,180,0,0.12); color: var(--yellow); border: 1px solid rgba(255,180,0,0.3); }
.badge-dot  { width: 5px; height: 5px; border-radius: 50%; background: currentColor; animation: blink 2s infinite; }
@keyframes blink { 0%,100%{opacity:1} 50%{opacity:0.3} }
.pd-title { margin: 0 0 18px; }
.pd-subtitle { font-size: 1.05rem; max-width: 700px; }

/* Tabs */
.tabs { display: flex; gap: 2px; margin-bottom: 48px; border-bottom: 1px solid var(--border); padding-bottom: 0; overflow-x: auto; }
.tab {
  padding: 12px 22px; font-size: 0.82rem; font-weight: 800; color: var(--text-3);
  cursor: pointer; border-bottom: 2px solid transparent; margin-bottom: -1px;
  transition: color var(--ease), border-color var(--ease); white-space: nowrap; letter-spacing: 0.03em;
}
.tab.on { color: var(--text); border-color: var(--accent); }
.tab:hover:not(.on) { color: var(--text-2); }
.tab-pane { display: none; animation: fadeIn 0.3s ease; }
.tab-pane.on { display: block; }
@keyframes fadeIn { from{opacity:0;transform:translateY(8px)} to{opacity:1;transform:translateY(0)} }

/* Content blocks */
.grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: var(--gap); }
.grid-3 { display: grid; grid-template-columns: repeat(3,1fr); gap: var(--gap); }
.block {
  padding: 28px 32px; background: var(--surface); border-radius: var(--radius);
  border: 1px solid var(--border);
}
.block h4 { margin-bottom: 14px; font-size: 0.95rem; }
.block p { font-size: 0.875rem; }
.block ul { list-style: none; display: flex; flex-direction: column; gap: 9px; margin-top: 12px; }
.block li { display: flex; gap: 10px; font-size: 0.875rem; color: var(--text-2); line-height: 1.6; }
.block li::before { content: '→'; color: var(--accent); font-weight: 900; flex-shrink: 0; font-size: 0.85rem; }
.block strong { color: var(--text); font-weight: 700; }

/* Architecture diagram */
.arch { display: flex; flex-direction: column; gap: 10px; }
.arch-row { padding: 20px 24px; background: var(--surface); border-radius: var(--radius); border: 1px solid var(--border); }
.arch-row-label { font-size: 0.63rem; font-weight: 800; letter-spacing: 0.14em; text-transform: uppercase; color: var(--accent); margin-bottom: 10px; }
.arch-nodes { display: flex; flex-wrap: wrap; gap: 8px; }
.arch-node { padding: 6px 14px; border-radius: 6px; font-size: 0.8rem; font-weight: 600; }
.arch-node.p { background: var(--accent-dim); color: var(--accent); border: 1px solid rgba(232,64,64,0.25); }
.arch-node.s { background: var(--surface-2); color: var(--text-2); border: 1px solid var(--border); }
.arch-arrow { text-align: center; color: var(--text-3); font-size: 1.1rem; padding: 4px 0; }

/* Workflow */
.flow { display: flex; flex-direction: column; }
.flow-step { display: flex; gap: 24px; align-items: flex-start; padding: 24px 0; border-bottom: 1px solid var(--border); }
.flow-step:last-child { border-bottom: none; }
.step-n {
  width: 36px; height: 36px; background: var(--accent); border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 0.78rem; font-weight: 900; color: #fff; flex-shrink: 0;
}
.step-body h4 { font-size: 0.95rem; margin-bottom: 6px; }
.step-body p { font-size: 0.87rem; }

/* Impact Metrics */
.metrics { display: grid; grid-template-columns: repeat(3,1fr); gap: var(--gap); margin-bottom: var(--gap); }
.metric {
  padding: 32px 28px; background: var(--surface); border-radius: var(--radius-lg);
  border: 1px solid var(--border); text-align: center;
}
.metric-val {
  font-size: clamp(2rem, 4.5vw, 3.2rem); font-weight: 900; color: var(--accent);
  line-height: 1; margin-bottom: 10px; letter-spacing: -0.03em;
}
.metric-label { font-size: 0.85rem; color: var(--text); font-weight: 700; margin-bottom: 4px; }
.metric-sub { font-size: 0.75rem; color: var(--text-3); }

/* Before / After */
.ba { display: grid; grid-template-columns: 1fr 1fr; gap: var(--gap); margin-top: 32px; }
.ba-card { padding: 24px 28px; border-radius: var(--radius); border: 1px solid; }
.ba-before { background: var(--red-dim); border-color: rgba(232,80,80,0.2); }
.ba-after  { background: var(--green-dim); border-color: rgba(100,200,100,0.2); }
.ba-label { font-size: 0.68rem; font-weight: 800; letter-spacing: 0.12em; text-transform: uppercase; margin-bottom: 14px; }
.ba-before .ba-label { color: #e87070; }
.ba-after  .ba-label { color: var(--green); }
.ba-list { display: flex; flex-direction: column; gap: 9px; }
.ba-item { font-size: 0.875rem; color: var(--text-2); display: flex; gap: 10px; line-height: 1.55; }

/* Screenshots */
.ss-grid { display: grid; grid-template-columns: repeat(2,1fr); gap: var(--gap); }
.ss-card {
  border-radius: var(--radius); overflow: hidden;
  border: 1px solid var(--border); cursor: pointer;
  transition: transform var(--ease), border-color var(--ease), box-shadow var(--ease);
}
.ss-card:hover { transform: scale(1.018); border-color: var(--accent); box-shadow: 0 8px 32px rgba(0,0,0,0.4); }
.ss-img { width: 100%; aspect-ratio: 16/9; object-fit: cover; object-position: top center; display: block; }
.ss-cap { padding: 12px 16px; background: var(--surface-2); font-size: 0.8rem; color: var(--text-2); line-height: 1.4; }

/* Tech chips */
.chips { display: flex; flex-wrap: wrap; gap: 10px; }
.chip {
  display: flex; align-items: center; gap: 8px;
  padding: 9px 16px; background: var(--surface); border-radius: 8px;
  border: 1px solid var(--border); font-size: 0.83rem; font-weight: 600; color: var(--text-2);
  transition: border-color var(--ease);
}
.chip:hover { border-color: var(--accent); }
.chip-dot { width: 7px; height: 7px; border-radius: 50%; background: var(--accent); flex-shrink: 0; }

/* ─────────────────────────────────────────────
   CONTACT
───────────────────────────────────────────── */
#contact { border-top: 1px solid var(--border); }
.contact-inner { display: flex; justify-content: space-between; align-items: center; gap: 60px; }
.contact-left h2 { margin: 16px 0 14px; }
.contact-left p { max-width: 400px; }
.contact-links { display: flex; flex-direction: column; gap: 12px; flex-shrink: 0; }
.contact-link {
  display: flex; align-items: center; gap: 14px;
  padding: 16px 22px; background: var(--surface); border-radius: var(--radius);
  border: 1px solid var(--border); font-size: 0.88rem; font-weight: 700;
  min-width: 280px; transition: border-color var(--ease), transform var(--ease);
  color: var(--text-2);
}
.contact-link:hover { border-color: var(--accent); transform: translateX(4px); color: var(--text); }
.contact-icon { font-size: 1.1rem; width: 20px; text-align: center; flex-shrink: 0; }

/* Footer */
.foot { padding: 28px 0; border-top: 1px solid var(--border); }
.foot-inner { display: flex; justify-content: space-between; align-items: center; }
.foot-copy { font-size: 0.78rem; color: var(--text-3); }
.foot-back { font-size: 0.78rem; color: var(--text-3); transition: color var(--ease); }
.foot-back:hover { color: var(--accent); }

/* ─────────────────────────────────────────────
   LIGHTBOX
───────────────────────────────────────────── */
#lightbox {
  position: fixed; inset: 0; background: rgba(0,0,0,0.95); z-index: 1000;
  display: none; align-items: center; justify-content: center; padding: 40px;
}
#lightbox.open { display: flex; }
#lightbox img { max-width: 90vw; max-height: 88vh; object-fit: contain; border-radius: var(--radius); }
.lb-close {
  position: absolute; top: 20px; right: 20px; width: 44px; height: 44px;
  background: var(--surface); border-radius: 50%; display: flex; align-items: center;
  justify-content: center; color: var(--text); font-size: 1.1rem; cursor: pointer;
  border: 1px solid var(--border); transition: background var(--ease);
}
.lb-close:hover { background: var(--surface-2); }
.lb-caption {
  position: absolute; bottom: 40px; left: 50%; transform: translateX(-50%);
  background: var(--surface); padding: 10px 20px; border-radius: 8px;
  font-size: 0.82rem; color: var(--text-2); white-space: nowrap;
  border: 1px solid var(--border);
}

/* ─────────────────────────────────────────────
   SCROLL REVEAL
───────────────────────────────────────────── */
.reveal { opacity: 0; transform: translateY(28px); transition: opacity 0.65s ease, transform 0.65s ease; }
.reveal.vis { opacity: 1; transform: translateY(0); }
.reveal[data-delay="1"] { transition-delay: 0.1s; }
.reveal[data-delay="2"] { transition-delay: 0.2s; }
.reveal[data-delay="3"] { transition-delay: 0.3s; }

/* ─────────────────────────────────────────────
   RESPONSIVE
───────────────────────────────────────────── */
@media (max-width: 1024px) {
  :root { --py: 100px; }
  .container { padding: 0 32px; }
  .about-grid { grid-template-columns: 1fr; gap: 52px; }
  .proj-grid  { grid-template-columns: 1fr; }
  .metrics    { grid-template-columns: repeat(2,1fr); }
  .grid-2     { grid-template-columns: 1fr; }
  .grid-3     { grid-template-columns: 1fr 1fr; }
  .ba         { grid-template-columns: 1fr; }
  .ss-grid    { grid-template-columns: 1fr; }
  .contact-inner { flex-direction: column; align-items: flex-start; gap: 48px; }
  .contact-link { min-width: 0; width: 100%; }
  .hero-stats { flex-wrap: wrap; gap: 36px; }
}
@media (max-width: 640px) {
  :root { --py: 72px; }
  .container { padding: 0 20px; }
  .nav-links { display: none; }
  .metrics  { grid-template-columns: 1fr; }
  .grid-3   { grid-template-columns: 1fr; }
  .skills-grid { grid-template-columns: 1fr; }
  h1 { font-size: clamp(2.8rem, 12vw, 4.5rem); }
}
</style>
</head>
<body>

<!-- ════════════════════════════════════════════
     NAVIGATION
════════════════════════════════════════════ -->
<nav id="nav">
  <div class="container">
    <div class="nav-inner">
      <a href="#hero" class="nav-logo">DK<span class="dot">.</span></a>
      <div class="nav-links">
        <a href="#projects">Projects</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
        <a href="https://github.com/daihnkim" target="_blank" rel="noopener" class="nav-cta">GitHub →</a>
      </div>
    </div>
  </div>
</nav>

<!-- ════════════════════════════════════════════
     HERO
════════════════════════════════════════════ -->
<section id="hero">
  <div class="hero-glow"></div>
  <div class="hero-grid"></div>
  <div class="container">
    <div class="hero-content">
      <div class="hero-label label">Deployment Strategist</div>
      <h1 class="hero-name">Daihn<br><em>Kim</em><span style="color:var(--accent)">.</span></h1>
      <p class="hero-tagline">From customer pain to deployed solution — end to end.</p>
      <div class="hero-stats">
        <div class="hero-stat">
          <div class="hero-stat-num">3</div>
          <div class="hero-stat-label">Systems Deployed</div>
        </div>
        <div class="hero-stat">
          <div class="hero-stat-num">₩4M</div>
          <div class="hero-stat-label">Monthly Savings</div>
        </div>
        <div class="hero-stat">
          <div class="hero-stat-num">450+</div>
          <div class="hero-stat-label">Active Users Served</div>
        </div>
        <div class="hero-stat">
          <div class="hero-stat-num">75%</div>
          <div class="hero-stat-label">Ops Time Reduced</div>
        </div>
      </div>
      <div class="hero-actions">
        <a href="#projects" class="btn btn-primary">View Projects →</a>
        <a href="#contact" class="btn btn-ghost">Get in Touch</a>
      </div>
    </div>
  </div>
  <div class="hero-scroll">
    <span>Scroll</span>
    <div class="scroll-bar"></div>
  </div>
</section>

<!-- ════════════════════════════════════════════
     ABOUT
════════════════════════════════════════════ -->
<section id="about" class="section">
  <div class="container">
    <div class="about-grid">
      <div class="reveal">
        <div class="label">About</div>
        <h2>I connect business problems to working systems.</h2>
        <p>I specialize in translating ambiguous, real-world operational problems into deployed solutions — bridging the gap between non-technical stakeholders and technical execution.</p>
        <p>My work spans the full delivery cycle: gathering requirements from business teams, designing system architecture, building data pipelines and custom UIs, and operating systems through post-launch.</p>
        <div class="cap-list">
          <div class="cap-item"><div class="cap-dot"></div><span>Structuring ambiguous business requirements into technical specs</span></div>
          <div class="cap-item"><div class="cap-dot"></div><span>Designing human-in-the-loop workflows for non-technical operators</span></div>
          <div class="cap-item"><div class="cap-dot"></div><span>Connecting data pipelines to real operational workflows</span></div>
          <div class="cap-item"><div class="cap-dot"></div><span>Iterating based on user feedback through live operations</span></div>
        </div>
      </div>
      <div class="reveal" data-delay="2">
        <div class="label skills-label">Technical Skills</div>
        <div class="skills-grid">
          <div class="skill-card">
            <div class="skill-cat">Frontend</div>
            <div class="skill-tags">
              <span class="skill-tag">React</span><span class="skill-tag">Next.js</span>
              <span class="skill-tag">TypeScript</span><span class="skill-tag">Tailwind CSS</span>
            </div>
          </div>
          <div class="skill-card">
            <div class="skill-cat">Backend & Data</div>
            <div class="skill-tags">
              <span class="skill-tag">Supabase</span><span class="skill-tag">PostgreSQL</span>
              <span class="skill-tag">Python</span><span class="skill-tag">SQL</span>
            </div>
          </div>
          <div class="skill-card">
            <div class="skill-cat">Deployment</div>
            <div class="skill-tags">
              <span class="skill-tag">Vercel</span><span class="skill-tag">GitHub Pages</span>
              <span class="skill-tag">REST API</span><span class="skill-tag">Supabase Auth</span>
            </div>
          </div>
          <div class="skill-card">
            <div class="skill-cat">Automation</div>
            <div class="skill-tags">
              <span class="skill-tag">Browserbase</span><span class="skill-tag">PDF Parsing</span>
              <span class="skill-tag">Template Engine</span><span class="skill-tag">Job Queue</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ════════════════════════════════════════════
     PROJECTS OVERVIEW
════════════════════════════════════════════ -->
<section id="projects" class="section">
  <div class="container">
    <div class="sec-header reveal">
      <div>
        <div class="label" style="margin-bottom:12px">Selected Work</div>
        <h2>Projects</h2>
      </div>
      <p>Three systems, each solving a real operational problem — from discovery to deployment.</p>
    </div>
    <div class="proj-grid">
      <a href="#proj-eval" class="proj-card reveal">
        <div class="proj-num">01 ／ Evaluation System</div>
        <h3 class="proj-title">Integrated Performance Evaluation Platform</h3>
        <div class="proj-period">Dec 2025 – Jan 2026</div>
        <p class="proj-desc">Full-cycle performance management system for a 400-employee enterprise — automating competency reviews, 360° evaluations, and self-assessments with real-time admin oversight.</p>
        <div class="proj-metric">
          <div class="proj-metric-val">₩4,000,000</div>
          <div class="proj-metric-label">Monthly operational cost savings</div>
        </div>
        <div class="proj-tags">
          <span class="proj-tag">React / Next.js</span>
          <span class="proj-tag">Supabase</span>
          <span class="proj-tag">PostgreSQL</span>
          <span class="proj-tag">Role-based Auth</span>
        </div>
        <div class="proj-arrow">View Case Study <span>→</span></div>
      </a>

      <a href="#proj-reminder" class="proj-card reveal" data-delay="1">
        <div class="proj-num">02 ／ Reminder Admin</div>
        <h3 class="proj-title">Survey Reminder Automation Tool</h3>
        <div class="proj-period">Apr 2026 – May 2026</div>
        <p class="proj-desc">Admin tool to automate personalized reminder messages for 150 leadership survey participants. Solo-built from requirements gathering to production deployment.</p>
        <div class="proj-metric">
          <div class="proj-metric-val">8 hrs → 2 hrs</div>
          <div class="proj-metric-label">75% ops time reduction per campaign</div>
        </div>
        <div class="proj-tags">
          <span class="proj-tag">Next.js</span>
          <span class="proj-tag">TypeScript</span>
          <span class="proj-tag">Supabase</span>
          <span class="proj-tag">Human-in-loop</span>
        </div>
        <div class="proj-arrow">View Case Study <span>→</span></div>
      </a>

      <a href="#proj-resume" class="proj-card reveal" data-delay="2">
        <div class="proj-num">03 ／ Job Search Automation</div>
        <h3 class="proj-title">Resume & JD Matching Pipeline</h3>
        <div class="proj-period">May 2026 – Present</div>
        <p class="proj-desc">Personal automation pipeline for job applications: scrapes job postings, parses resumes from PDF, analyzes JD keyword fit, and surfaces bullet-level optimization suggestions.</p>
        <div class="proj-metric wip">
          <div class="proj-metric-val">In Progress</div>
          <div class="proj-metric-label">MVP live · keyword matching in development</div>
        </div>
        <div class="proj-tags">
          <span class="proj-tag">Python</span>
          <span class="proj-tag">Flask</span>
          <span class="proj-tag">Browserbase</span>
          <span class="proj-tag">PDF Parsing</span>
        </div>
        <div class="proj-arrow">View Case Study <span>→</span></div>
      </a>
    </div>
  </div>
</section>

<!-- ════════════════════════════════════════════
     PROJECT 1 — EVALUATION SYSTEM
════════════════════════════════════════════ -->
<section id="proj-eval" class="proj-detail">
  <div class="container">
    <!-- Header -->
    <div class="reveal">
      <div class="label" style="margin-bottom:20px">Project 01</div>
      <div class="pd-meta">
        <div class="pd-meta-item">
          <span class="pd-meta-key">Timeline</span>
          <span class="pd-meta-val">Dec 2025 – Jan 2026</span>
        </div>
        <div class="pd-meta-item">
          <span class="pd-meta-key">My Role</span>
          <span class="pd-meta-val">System Design &amp; Development (under PM)</span>
        </div>
        <div class="pd-meta-item">
          <span class="pd-meta-key">Users</span>
          <span class="pd-meta-val">~400 employees · Enterprise HR client</span>
        </div>
        <div class="pd-meta-item">
          <span class="pd-meta-key">Status</span>
          <span class="badge badge-live"><span class="badge-dot"></span>Deployed &amp; Post-op Complete</span>
        </div>
      </div>
      <h2 class="pd-title">Integrated Performance<br>Evaluation Platform</h2>
      <p class="pd-subtitle">Transformed a manual, error-prone HR evaluation process into a centralized web platform — serving 400 employees across competency reviews, 360° evaluations, and self-assessments.</p>
    </div>

    <!-- Tabs -->
    <div class="tabs reveal" style="margin-top:52px">
      <div class="tab on" data-tab="e1">Overview</div>
      <div class="tab" data-tab="e2">Architecture</div>
      <div class="tab" data-tab="e3">Workflow</div>
      <div class="tab" data-tab="e4">Impact</div>
      <div class="tab" data-tab="e5">Screenshots</div>
      <div class="tab" data-tab="e6">Tech Stack</div>
    </div>

    <!-- TAB: Overview -->
    <div id="e1" class="tab-pane on">
      <div class="grid-2" style="margin-bottom:var(--gap)">
        <div class="block">
          <h4>🔴 The Problem</h4>
          <p style="margin-bottom:10px">An enterprise HR client ran annual performance cycles for 400 employees using a mix of Excel and email — leading to critical bottlenecks:</p>
          <ul>
            <li>Assignment errors from manual Excel mapping across 40+ departments</li>
            <li>No real-time visibility into evaluation progress — HR had to follow up individually</li>
            <li>Three separate tools for competency reviews, 360° evaluations, and self-assessments created data silos</li>
            <li>Post-evaluation result compilation took days of manual Excel consolidation</li>
          </ul>
        </div>
        <div class="block">
          <h4>🟢 The Solution</h4>
          <p style="margin-bottom:10px">A unified web platform consolidating all evaluation types under a single admin dashboard and participant portal:</p>
          <ul>
            <li>One-click assignment engine: maps evaluators to targets by tier (T1–T4) automatically</li>
            <li>Live progress dashboard with per-employee and per-department drill-down</li>
            <li>Unified portal: competency review, 360°, and self-assessment in one system</li>
            <li>Structured Excel export for downstream HR analytics — ready in seconds</li>
          </ul>
        </div>
      </div>
      <div class="block">
        <h4>👤 My Role</h4>
        <p>Working under a PM, I owned the full technical delivery: requirements sessions with the HR team, translating business needs into system design, database schema, frontend UI for both admin and participant portals, API routes, and post-deployment operations support. I designed the assignment logic, data model for evaluation cycles, and the analytics views from scratch.</p>
      </div>
    </div>

    <!-- TAB: Architecture -->
    <div id="e2" class="tab-pane">
      <div class="arch">
        <div class="arch-row">
          <div class="arch-row-label">Business Input</div>
          <div class="arch-nodes">
            <span class="arch-node p">HR Requirements</span>
            <span class="arch-node p">Employee Roster (400 users)</span>
            <span class="arch-node p">Evaluation Criteria &amp; Question Bank</span>
          </div>
        </div>
        <div class="arch-arrow">↓</div>
        <div class="arch-row">
          <div class="arch-row-label">Data Layer — Supabase / PostgreSQL</div>
          <div class="arch-nodes">
            <span class="arch-node s">Users &amp; Roles</span>
            <span class="arch-node s">Evaluation Cycles</span>
            <span class="arch-node s">Question Bank</span>
            <span class="arch-node s">Assignment Matrix (42,899 records)</span>
            <span class="arch-node s">Response Records</span>
            <span class="arch-node s">Self-Assessment Data</span>
          </div>
        </div>
        <div class="arch-arrow">↓</div>
        <div class="arch-row">
          <div class="arch-row-label">Application Layer — Next.js + React</div>
          <div class="arch-nodes">
            <span class="arch-node s">Admin Portal (cycle config, oversight)</span>
            <span class="arch-node s">Evaluator Portal (personal tasks)</span>
            <span class="arch-node s">Auto-Assignment Engine</span>
            <span class="arch-node s">Real-time Progress Dashboard</span>
            <span class="arch-node s">Analytics &amp; Score Viewer</span>
            <span class="arch-node s">Excel Exporter</span>
          </div>
        </div>
        <div class="arch-arrow">↓</div>
        <div class="arch-row">
          <div class="arch-row-label">User Roles</div>
          <div class="arch-nodes">
            <span class="arch-node p">HR Admin — cycle management, monitoring, export</span>
            <span class="arch-node p">Manager — competency + 360° evaluations</span>
            <span class="arch-node p">Employee — self-assessment</span>
          </div>
        </div>
      </div>
    </div>

    <!-- TAB: Workflow -->
    <div id="e3" class="tab-pane">
      <div class="flow">
        <div class="flow-step">
          <div class="step-n">1</div>
          <div class="step-body">
            <h4>Requirements Discovery</h4>
            <p>Sat with the HR team to map existing pain points, evaluation types, org hierarchy, and approval workflows. Translated business requirements into a system design spec before writing code.</p>
          </div>
        </div>
        <div class="flow-step">
          <div class="step-n">2</div>
          <div class="step-body">
            <h4>Cycle Configuration</h4>
            <p>HR admin creates an evaluation cycle, sets the date range, selects evaluation types, and uploads the employee roster with tier classifications (T1–T4). All in a guided UI flow.</p>
          </div>
        </div>
        <div class="flow-step">
          <div class="step-n">3</div>
          <div class="step-body">
            <h4>Automated Assignment Generation</h4>
            <p>The assignment engine reads tier data and automatically generates evaluator–target pairings per evaluation type. Manual overrides are available. Result: 42,899 assignments generated with zero mapping errors.</p>
          </div>
        </div>
        <div class="flow-step">
          <div class="step-n">4</div>
          <div class="step-body">
            <h4>Evaluation Period — Human-in-the-Loop</h4>
            <p>Evaluators access assigned targets through a personalized portal showing their tasks, deadlines, and submission status. The system surfaces stalled evaluations for HR escalation in real time.</p>
          </div>
        </div>
        <div class="flow-step">
          <div class="step-n">5</div>
          <div class="step-body">
            <h4>Admin Monitoring &amp; Live Dashboard</h4>
            <p>HR admin monitors overall progress %, department-level breakdown, and individual completion status. Filters and search enable targeted follow-up without any manual tracking spreadsheet.</p>
          </div>
        </div>
        <div class="flow-step">
          <div class="step-n">6</div>
          <div class="step-body">
            <h4>Result Export &amp; Post-Processing</h4>
            <p>Upon cycle close, results are aggregated and exported as structured Excel files for downstream analytics. Our team performed data integrity verification and post-operation checks — fully supported through the end of the cycle.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- TAB: Impact -->
    <div id="e4" class="tab-pane">
      <div class="metrics">
        <div class="metric">
          <div class="metric-val">₩4M</div>
          <div class="metric-label">Monthly Cost Savings</div>
          <div class="metric-sub">Operational overhead eliminated</div>
        </div>
        <div class="metric">
          <div class="metric-val">400</div>
          <div class="metric-label">Employees Onboarded</div>
          <div class="metric-sub">On a single unified platform</div>
        </div>
        <div class="metric">
          <div class="metric-val">42,899</div>
          <div class="metric-label">Auto-Assigned Evaluations</div>
          <div class="metric-sub">Zero manual mapping errors</div>
        </div>
      </div>
      <div class="ba">
        <div class="ba-card ba-before">
          <div class="ba-label">Before</div>
          <div class="ba-list">
            <div class="ba-item">✗ Assignment errors from manual Excel mapping across 40+ departments</div>
            <div class="ba-item">✗ No real-time visibility into evaluation progress — constant manual follow-up</div>
            <div class="ba-item">✗ Three separate tools created data silos between evaluation types</div>
            <div class="ba-item">✗ Days of manual Excel work to compile post-cycle results</div>
            <div class="ba-item">✗ High coordination overhead across 400 employees = ₩4M/month in labor cost</div>
          </div>
        </div>
        <div class="ba-card ba-after">
          <div class="ba-label">After</div>
          <div class="ba-list">
            <div class="ba-item">✓ One-click automated assignment — 42,899 records, zero errors</div>
            <div class="ba-item">✓ Live dashboard: overall % + per-department + per-person breakdown</div>
            <div class="ba-item">✓ All three evaluation types unified in one system and portal</div>
            <div class="ba-item">✓ Structured Excel export in seconds — no post-processing required</div>
            <div class="ba-item">✓ ₩4,000,000/month in operational savings</div>
          </div>
        </div>
      </div>
    </div>

    <!-- TAB: Screenshots -->
    <div id="e5" class="tab-pane">
      <div class="ss-grid">
        <div class="ss-card" onclick="lb('assets/screenshots/eval/eval-1.png','Admin Dashboard — Evaluation cycle overview with live progress tracking')">
          <img class="ss-img" src="assets/screenshots/eval/eval-1.png" alt="Admin Dashboard" loading="lazy">
          <div class="ss-cap">Admin Dashboard — Evaluation cycle overview with live progress %</div>
        </div>
        <div class="ss-card" onclick="lb('assets/screenshots/eval/eval-2.png','Assignment Management — Auto-generated evaluator–target pairings with tier labels')">
          <img class="ss-img" src="assets/screenshots/eval/eval-2.png" alt="Assignment Management" loading="lazy">
          <div class="ss-cap">Assignment Management — Auto-generated pairings with tier labels (T1–T4)</div>
        </div>
        <div class="ss-card" onclick="lb('assets/screenshots/eval/eval-3.png','Analytics Dashboard — Individual evaluator score breakdown by competency dimension')">
          <img class="ss-img" src="assets/screenshots/eval/eval-3.png" alt="Analytics Dashboard" loading="lazy">
          <div class="ss-cap">Analytics Dashboard — Individual score breakdown by competency dimension</div>
        </div>
        <div class="ss-card" onclick="lb('assets/screenshots/eval/eval-7.png','Evaluator Portal — Personalized task view with submission status and deadlines')">
          <img class="ss-img" src="assets/screenshots/eval/eval-7.png" alt="Evaluator Portal" loading="lazy">
          <div class="ss-cap">Evaluator Portal — Personalized view with 1st/2nd round progress tracking</div>
        </div>
        <div class="ss-card" onclick="lb('assets/screenshots/eval/eval-4.png','User Management — Evaluator list with real-time submission rate per person')">
          <img class="ss-img" src="assets/screenshots/eval/eval-4.png" alt="User Management" loading="lazy">
          <div class="ss-cap">User Management — Evaluator list with per-person submission status</div>
        </div>
        <div class="ss-card" onclick="lb('assets/screenshots/eval/eval-8.png','Evaluation Form — Structured competency rating interface for evaluators')">
          <img class="ss-img" src="assets/screenshots/eval/eval-8.png" alt="Evaluation Form" loading="lazy">
          <div class="ss-cap">Evaluation Form — Structured competency rating interface</div>
        </div>
      </div>
    </div>

    <!-- TAB: Tech Stack -->
    <div id="e6" class="tab-pane">
      <div class="chips" style="margin-bottom:32px">
        <div class="chip"><div class="chip-dot"></div>React / Next.js</div>
        <div class="chip"><div class="chip-dot"></div>TypeScript</div>
        <div class="chip"><div class="chip-dot"></div>Supabase</div>
        <div class="chip"><div class="chip-dot"></div>PostgreSQL</div>
        <div class="chip"><div class="chip-dot"></div>Role-based Auth (Admin / Evaluator / Employee)</div>
        <div class="chip"><div class="chip-dot"></div>Excel Export (SheetJS)</div>
        <div class="chip"><div class="chip-dot"></div>Real-time subscriptions (Supabase Realtime)</div>
        <div class="chip"><div class="chip-dot"></div>Vercel</div>
      </div>
      <div class="block">
        <h4>Key Engineering Decisions</h4>
        <ul>
          <li><strong>Assignment as data, not logic</strong> — assignment matrix stored as database records, enabling real-time queries, overrides, and audit trails without rebuilding logic</li>
          <li><strong>Role-based portal separation</strong> — admin, evaluator, and employee views are distinct route trees, preventing confusion and UI complexity for non-technical users</li>
          <li><strong>Progress as a derived metric</strong> — progress % is computed from response records at query time, always reflecting the true state without a separate sync job</li>
          <li><strong>Export is a first-class feature</strong> — structured Excel output matching downstream HR tools was designed from day one, not bolted on</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- ════════════════════════════════════════════
     PROJECT 2 — REMINDER ADMIN
════════════════════════════════════════════ -->
<section id="proj-reminder" class="proj-detail">
  <div class="container">
    <div class="reveal">
      <div class="label" style="margin-bottom:20px">Project 02</div>
      <div class="pd-meta">
        <div class="pd-meta-item">
          <span class="pd-meta-key">Timeline</span>
          <span class="pd-meta-val">Apr 2026 – May 2026</span>
        </div>
        <div class="pd-meta-item">
          <span class="pd-meta-key">My Role</span>
          <span class="pd-meta-val">Solo — Requirements to Production Deployment</span>
        </div>
        <div class="pd-meta-item">
          <span class="pd-meta-key">Scope</span>
          <span class="pd-meta-val">150 leaders · 450 surveys</span>
        </div>
        <div class="pd-meta-item">
          <span class="pd-meta-key">Status</span>
          <span class="badge badge-live"><span class="badge-dot"></span>Live &amp; Operating</span>
        </div>
      </div>
      <h2 class="pd-title">Survey Reminder<br>Automation Tool</h2>
      <p class="pd-subtitle">I gathered requirements, designed the solution, and shipped a production admin tool — solo. Cut a manual 8-person-hour task down to 2 hours, with a human approval gate built in.</p>
    </div>

    <div class="tabs reveal" style="margin-top:52px">
      <div class="tab on" data-tab="r1">Overview</div>
      <div class="tab" data-tab="r2">Architecture</div>
      <div class="tab" data-tab="r3">Workflow</div>
      <div class="tab" data-tab="r4">Impact</div>
      <div class="tab" data-tab="r5">Implementation</div>
    </div>

    <!-- TAB: Overview -->
    <div id="r1" class="tab-pane on">
      <div class="grid-2" style="margin-bottom:var(--gap)">
        <div class="block">
          <h4>🔴 The Problem</h4>
          <p style="margin-bottom:10px">During a leadership 360° survey cycle, the ops team needed to send personalized reminders to 150 leaders. Each message required:</p>
          <ul>
            <li>A unique leader name in the body</li>
            <li>A specific deadline date per cohort</li>
            <li>A unique survey URL per leader</li>
            <li>Consistent tone and brand formatting</li>
          </ul>
          <p style="margin-top:12px">Previously: 4 people spent 8 hours manually composing from an Excel sheet. Error-prone, tedious, and unscalable.</p>
        </div>
        <div class="block">
          <h4>🟢 My Discovery Process</h4>
          <p style="margin-bottom:10px">I ran a requirements session with the operations team to understand:</p>
          <ul>
            <li>Which variables changed per recipient (name, deadline, link)</li>
            <li>What approval checkpoints they needed before mass-sending</li>
            <li>How they wanted to track send status and errors</li>
            <li>What "failure" looked like — and what would erode trust fastest</li>
          </ul>
          <p style="margin-top:12px">The key insight: the team's biggest fear was sending the wrong message to 150 people at once. I designed an explicit human review gate before any batch send.</p>
        </div>
      </div>
    </div>

    <!-- TAB: Architecture -->
    <div id="r2" class="tab-pane">
      <div class="arch">
        <div class="arch-row">
          <div class="arch-row-label">Input</div>
          <div class="arch-nodes">
            <span class="arch-node p">Recipient list (Supabase)</span>
            <span class="arch-node p">Message template</span>
            <span class="arch-node p">Variables: {LEADER_NAME} {DEADLINE_LABEL} {SURVEY_LINK}</span>
          </div>
        </div>
        <div class="arch-arrow">↓</div>
        <div class="arch-row">
          <div class="arch-row-label">Admin Interface — Next.js</div>
          <div class="arch-nodes">
            <span class="arch-node s">Compose Form</span>
            <span class="arch-node s">Real-time Preview Panel</span>
            <span class="arch-node s">Recipient Manager</span>
            <span class="arch-node s">Job Log Table</span>
          </div>
        </div>
        <div class="arch-arrow">↓</div>
        <div class="arch-row">
          <div class="arch-row-label">Human-in-the-Loop Gate (designed from requirements)</div>
          <div class="arch-nodes">
            <span class="arch-node p">Preview rendered message → Operator approves → Batch send triggered</span>
          </div>
        </div>
        <div class="arch-arrow">↓</div>
        <div class="arch-row">
          <div class="arch-row-label">Delivery &amp; Monitoring</div>
          <div class="arch-nodes">
            <span class="arch-node s">Variable interpolation per recipient</span>
            <span class="arch-node s">Batch message dispatch</span>
            <span class="arch-node s">Per-send status logging (success / failed)</span>
            <span class="arch-node s">Error surfacing for retry</span>
          </div>
        </div>
      </div>
    </div>

    <!-- TAB: Workflow -->
    <div id="r3" class="tab-pane">
      <div class="flow">
        <div class="flow-step">
          <div class="step-n">1</div>
          <div class="step-body">
            <h4>Requirements Discovery</h4>
            <p>Mapped current pain points, message variables, and failure scenarios with the operations team. Translated directly into a feature spec — no code written until the workflow was agreed upon.</p>
          </div>
        </div>
        <div class="flow-step">
          <div class="step-n">2</div>
          <div class="step-body">
            <h4>Template Composition</h4>
            <p>Operator opens the compose form and writes a message using {LEADER_NAME}, {DEADLINE_LABEL}, and {SURVEY_LINK} placeholders. A real-time preview panel renders the actual message instantly as they type.</p>
          </div>
        </div>
        <div class="flow-step">
          <div class="step-n">3</div>
          <div class="step-body">
            <h4>Human Review Gate</h4>
            <p>Before any message is sent, the operator reviews the rendered output. This step — a direct response to the team's trust concerns — creates an explicit moment of human judgment before committing to 150 sends.</p>
          </div>
        </div>
        <div class="flow-step">
          <div class="step-n">4</div>
          <div class="step-body">
            <h4>Batch Send</h4>
            <p>On approval, the system iterates through all 450 survey assignments, interpolates variables per recipient, and dispatches personalized messages. Progress is displayed in real time.</p>
          </div>
        </div>
        <div class="flow-step">
          <div class="step-n">5</div>
          <div class="step-body">
            <h4>Log &amp; Error Review</h4>
            <p>All send attempts are logged with timestamp, job type, status (success / failed), and error message. Failed sends surface immediately — no silent failures, and any error is actionable.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- TAB: Impact -->
    <div id="r4" class="tab-pane">
      <div class="metrics">
        <div class="metric">
          <div class="metric-val">75%</div>
          <div class="metric-label">Time Reduction</div>
          <div class="metric-sub">8 person-hours → 2 hours per campaign</div>
        </div>
        <div class="metric">
          <div class="metric-val">150</div>
          <div class="metric-label">Leaders Reached</div>
          <div class="metric-sub">Per survey campaign cycle</div>
        </div>
        <div class="metric">
          <div class="metric-val">450</div>
          <div class="metric-label">Surveys Managed</div>
          <div class="metric-sub">Upward, downward &amp; peer evaluations</div>
        </div>
      </div>
      <div class="ba">
        <div class="ba-card ba-before">
          <div class="ba-label">Before</div>
          <div class="ba-list">
            <div class="ba-item">✗ 4 people × 2 hours each = 8 person-hours per campaign</div>
            <div class="ba-item">✗ Manual copy-paste from Excel into message composer for 150 recipients</div>
            <div class="ba-item">✗ No systematic send confirmation or error tracking</div>
            <div class="ba-item">✗ Fatigue-driven errors — occasional wrong-name or wrong-link sends</div>
          </div>
        </div>
        <div class="ba-card ba-after">
          <div class="ba-label">After</div>
          <div class="ba-list">
            <div class="ba-item">✓ 1 operator · 2 hours · no manual composing required</div>
            <div class="ba-item">✓ Template engine handles all variable interpolation automatically</div>
            <div class="ba-item">✓ Full job log — status + error message per send</div>
            <div class="ba-item">✓ Human review gate prevents batch send mistakes</div>
          </div>
        </div>
      </div>
    </div>

    <!-- TAB: Implementation -->
    <div id="r5" class="tab-pane">
      <div class="grid-2" style="margin-bottom:var(--gap)">
        <div class="block">
          <h4>Key Design Decisions</h4>
          <ul>
            <li><strong>Real-time preview</strong> — the operator sees the rendered message as they type, making the template feel tangible and reducing errors before any send action</li>
            <li><strong>Explicit human gate</strong> — approval step required before batch dispatch; designed around the team's stated trust concern, not added as an afterthought</li>
            <li><strong>Job log as a product feature</strong> — all send attempts logged with full status; failures surface immediately and are designed to be actionable</li>
          </ul>
        </div>
        <div class="block">
          <h4>What I Learned</h4>
          <ul>
            <li>The most valuable feature was the preview panel — automation without visibility doesn't build trust with non-technical operators</li>
            <li>Friction at the right moment (the review gate) increased adoption confidence significantly</li>
            <li>For ops teams that care about accountability, logging is a first-class product concern — not a debugging convenience</li>
          </ul>
        </div>
      </div>
      <div class="label" style="margin-bottom:16px">Tech Stack</div>
      <div class="chips">
        <div class="chip"><div class="chip-dot"></div>Next.js 14</div>
        <div class="chip"><div class="chip-dot"></div>TypeScript</div>
        <div class="chip"><div class="chip-dot"></div>Supabase (DB + Auth)</div>
        <div class="chip"><div class="chip-dot"></div>PostgreSQL</div>
        <div class="chip"><div class="chip-dot"></div>Custom template engine ({variable} interpolation)</div>
        <div class="chip"><div class="chip-dot"></div>Job Queue + Structured Logger</div>
        <div class="chip"><div class="chip-dot"></div>Vercel</div>
      </div>
    </div>
  </div>
</section>

<!-- ════════════════════════════════════════════
     PROJECT 3 — RESUME & JD AUTOMATION
════════════════════════════════════════════ -->
<section id="proj-resume" class="proj-detail">
  <div class="container">
    <div class="reveal">
      <div class="label" style="margin-bottom:20px">Project 03</div>
      <div class="pd-meta">
        <div class="pd-meta-item">
          <span class="pd-meta-key">Timeline</span>
          <span class="pd-meta-val">May 2026 – Present</span>
        </div>
        <div class="pd-meta-item">
          <span class="pd-meta-key">My Role</span>
          <span class="pd-meta-val">Solo — Design &amp; Development</span>
        </div>
        <div class="pd-meta-item">
          <span class="pd-meta-key">Type</span>
          <span class="pd-meta-val">Personal / Technical Project</span>
        </div>
        <div class="pd-meta-item">
          <span class="pd-meta-key">Status</span>
          <span class="badge badge-wip"><span class="badge-dot"></span>In Progress — MVP Live</span>
        </div>
      </div>
      <h2 class="pd-title">Resume &amp; Job Search<br>Automation Pipeline</h2>
      <p class="pd-subtitle">A personal end-to-end pipeline: scraping job postings with Browserbase, parsing my resume from PDF, and running keyword-level fit analysis against each JD — surfacing bullet-by-bullet optimization gaps.</p>
    </div>

    <div class="tabs reveal" style="margin-top:52px">
      <div class="tab on" data-tab="j1">Overview</div>
      <div class="tab" data-tab="j2">Architecture</div>
      <div class="tab" data-tab="j3">Workflow</div>
      <div class="tab" data-tab="j4">Engineering Notes</div>
    </div>

    <!-- TAB: Overview -->
    <div id="j1" class="tab-pane on">
      <div class="grid-2" style="margin-bottom:var(--gap)">
        <div class="block">
          <h4>🔴 The Problem</h4>
          <p style="margin-bottom:10px">Resume tailoring for each JD is essential but slow and hard to scale:</p>
          <ul>
            <li>30–60 min per application to read a JD and map keywords to resume bullets</li>
            <li>Easy to miss high-priority terms buried in lengthy requirements sections</li>
            <li>No systematic way to compare coverage across multiple applications</li>
            <li>Manual process doesn't scale when applying to 10+ roles simultaneously</li>
          </ul>
        </div>
        <div class="block">
          <h4>🟢 Solution Design</h4>
          <p style="margin-bottom:10px">A layered pipeline separating each concern:</p>
          <ul>
            <li><strong>Collection</strong> — Browserbase scraper crawls job boards, extracts structured JD data into jobs.csv</li>
            <li><strong>Parsing</strong> — PDF resume parser extracts experience blocks and bullets with a raw-text fallback for failures</li>
            <li><strong>Analysis</strong> — Rule-based NLP extracts and scores JD keywords by section weight and frequency</li>
            <li><strong>Matching</strong> — Bullet-by-bullet coverage analysis flags missing high-priority keywords</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- TAB: Architecture -->
    <div id="j2" class="tab-pane">
      <div class="arch">
        <div class="arch-row">
          <div class="arch-row-label">Collection Layer</div>
          <div class="arch-nodes">
            <span class="arch-node p">Browserbase SDK (headless browser)</span>
            <span class="arch-node s">Job board scraper</span>
            <span class="arch-node s">JD structuring → jobs.csv</span>
          </div>
        </div>
        <div class="arch-arrow">↓</div>
        <div class="arch-row">
          <div class="arch-row-label">Resume Parsing Layer — Python</div>
          <div class="arch-nodes">
            <span class="arch-node s">pdfplumber (primary)</span>
            <span class="arch-node s">pypdf (fallback)</span>
            <span class="arch-node s">Manual paste (UI fallback)</span>
            <span class="arch-node s">Section splitter</span>
            <span class="arch-node s">Experience parser → resume.json</span>
          </div>
        </div>
        <div class="arch-arrow">↓</div>
        <div class="arch-row">
          <div class="arch-row-label">Analysis Layer</div>
          <div class="arch-nodes">
            <span class="arch-node p">JD keyword extractor (rule-based NLP)</span>
            <span class="arch-node s">Noun phrase extraction</span>
            <span class="arch-node s">Section-weighted scoring (Requirements &gt; Preferred)</span>
            <span class="arch-node s">Category tagging: Role / Skill / Responsibility</span>
          </div>
        </div>
        <div class="arch-arrow">↓</div>
        <div class="arch-row">
          <div class="arch-row-label">Review UI — Flask + Vanilla JS</div>
          <div class="arch-nodes">
            <span class="arch-node s">Resume Studio editor (inline edit)</span>
            <span class="arch-node s">JD input &amp; keyword category view</span>
            <span class="arch-node s">Coverage % per bullet</span>
            <span class="arch-node s">Missing keyword flags &amp; rewrite suggestions</span>
          </div>
        </div>
      </div>
    </div>

    <!-- TAB: Workflow -->
    <div id="j3" class="tab-pane">
      <div class="flow">
        <div class="flow-step">
          <div class="step-n">1</div>
          <div class="step-body">
            <h4>Job Collection (Automated)</h4>
            <p>Browserbase scraper runs against job boards. Extracts title, company, full JD text, and requirements. Saves structured output to jobs.csv — shareable and filterable.</p>
          </div>
        </div>
        <div class="flow-step">
          <div class="step-n">2</div>
          <div class="step-body">
            <h4>Resume Upload &amp; Parse</h4>
            <p>User uploads a PDF resume. Parser extracts work experience into structured blocks (company, title, dates, bullets). Failed sections are saved as raw text for manual correction. Target: 80% auto-parsed, 20% human-corrected in UI.</p>
          </div>
        </div>
        <div class="flow-step">
          <div class="step-n">3</div>
          <div class="step-body">
            <h4>JD Keyword Analysis</h4>
            <p>JD text is processed: noun phrases extracted, scored by frequency and section weight (Requirements section ranks highest), and categorized into Role / Skill / Responsibility. Top verbs extracted separately for bullet rewriting.</p>
          </div>
        </div>
        <div class="flow-step">
          <div class="step-n">4</div>
          <div class="step-body">
            <h4>Bullet-Level Coverage Matching</h4>
            <p>Each resume bullet is tokenized and matched against JD keywords. Coverage % is calculated. Missing high-priority keywords are surfaced per bullet with category and priority context.</p>
          </div>
        </div>
        <div class="flow-step">
          <div class="step-n">5</div>
          <div class="step-body">
            <h4>Human Review &amp; Rewrite (In Progress)</h4>
            <p>User reviews suggestions and edits bullets inline. Current MVP: template-based rewrite hints. Phase 2: optional LLM-assisted rewrites with explicit warnings and original preservation.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- TAB: Engineering Notes -->
    <div id="j4" class="tab-pane">
      <div class="grid-2" style="margin-bottom:var(--gap)">
        <div class="block">
          <h4>Architecture Principles</h4>
          <ul>
            <li><strong>Layered, independently testable</strong> — each stage (extract → parse → analyze → match) can be run and verified in isolation</li>
            <li><strong>Raw text preserved at every stage</strong> — parse failures are recoverable; never lose the original input</li>
            <li><strong>Deterministic base, optional LLM</strong> — rule-based is debuggable, trustworthy, and works offline; LLM is a later opt-in layer</li>
            <li><strong>Edit UI is first-class</strong> — 80% automation target means 20% lives in a good edit interface, not more parsing complexity</li>
          </ul>
        </div>
        <div class="block">
          <h4>Key Takeaways (In Progress)</h4>
          <ul>
            <li>PDF parsing inconsistency is a product constraint to accept, not an engineering problem to "solve" indefinitely</li>
            <li>The most valuable feature is showing what's <em style="color:var(--accent)">missing</em>, not just what matches — the gap is what drives action</li>
            <li>Rewrite suggestions without user control are dangerous — always show what changed and preserve the original</li>
            <li>Job scraping and resume analysis share the same underlying need: clean, structured, comparable text</li>
          </ul>
        </div>
      </div>
      <div class="label" style="margin-bottom:16px">Tech Stack</div>
      <div class="chips">
        <div class="chip"><div class="chip-dot"></div>Python 3.12</div>
        <div class="chip"><div class="chip-dot"></div>Flask</div>
        <div class="chip"><div class="chip-dot"></div>pdfplumber + pypdf</div>
        <div class="chip"><div class="chip-dot"></div>Browserbase SDK</div>
        <div class="chip"><div class="chip-dot"></div>Rule-based NLP (custom)</div>
        <div class="chip"><div class="chip-dot"></div>HTML / CSS / Vanilla JS</div>
        <div class="chip"><div class="chip-dot"></div>JSON persistence (resume.json)</div>
      </div>
    </div>
  </div>
</section>

<!-- ════════════════════════════════════════════
     CONTACT
════════════════════════════════════════════ -->
<section id="contact" class="section">
  <div class="container">
    <div class="contact-inner reveal">
      <div class="contact-left">
        <div class="label">Get In Touch</div>
        <h2>Let's work<br>together.</h2>
        <p>Open to Deployment Strategist, Forward Deployed Engineer, and Solutions Engineer roles. I bring the full cycle — from understanding a customer's problem to operating the solution in production.</p>
      </div>
      <div class="contact-links">
        <a href="mailto:daihnkim@gmail.com" class="contact-link">
          <span class="contact-icon">✉</span>
          <span>daihnkim@gmail.com</span>
        </a>
        <a href="https://github.com/daihnkim-rgb/portpolio" target="_blank" rel="noopener" class="contact-link">
          <span class="contact-icon">⌥</span>
          <span>github.com/daihnkim</span>
        </a>
        <a href="https://www.linkedin.com/in/danny-kim-%EA%B9%80%EB%8B%A4%EC%9D%B8-9024a1260/" target="_blank" rel="noopener" class="contact-link">
          <span class="contact-icon">▣</span>
          <span>linkedin.com/in/daihnkim</span>
        </a>
      </div>
    </div>
  </div>
</section>

<footer class="foot">
  <div class="container">
    <div class="foot-inner">
      <span class="foot-copy">© 2026 Daihn Kim · Built for deployment.</span>
      <a href="#hero" class="foot-back">↑ Back to top</a>
    </div>
  </div>
</footer>

<!-- ════════════════════════════════════════════
     LIGHTBOX
════════════════════════════════════════════ -->
<div id="lightbox" onclick="lbClose()">
  <button class="lb-close" onclick="lbClose()">✕</button>
  <img id="lb-img" src="" alt="">
  <div class="lb-caption" id="lb-cap"></div>
</div>

<!-- ════════════════════════════════════════════
     JAVASCRIPT
════════════════════════════════════════════ -->
<script>
// ── Nav scroll ──────────────────────────────────
const nav = document.getElementById('nav');
const onScroll = () => nav.classList.toggle('scrolled', scrollY > 50);
window.addEventListener('scroll', onScroll, { passive: true });

// ── Tabs ────────────────────────────────────────
document.querySelectorAll('.tab').forEach(tab => {
  tab.addEventListener('click', () => {
    const section = tab.closest('.proj-detail');
    const id = tab.dataset.tab;
    section.querySelectorAll('.tab').forEach(t => t.classList.remove('on'));
    section.querySelectorAll('.tab-pane').forEach(p => p.classList.remove('on'));
    tab.classList.add('on');
    document.getElementById(id).classList.add('on');
  });
});

// ── Scroll Reveal ───────────────────────────────
const observer = new IntersectionObserver(entries => {
  entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('vis'); });
}, { threshold: 0.08, rootMargin: '0px 0px -40px 0px' });
document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

// ── Lightbox ────────────────────────────────────
function lb(src, caption) {
  document.getElementById('lb-img').src = src;
  document.getElementById('lb-cap').textContent = caption || '';
  document.getElementById('lightbox').classList.add('open');
  document.body.style.overflow = 'hidden';
}
function lbClose() {
  document.getElementById('lightbox').classList.remove('open');
  document.body.style.overflow = '';
}
document.addEventListener('keydown', e => { if (e.key === 'Escape') lbClose(); });

// ── Smooth anchor navigation ─────────────────────
document.querySelectorAll('a[href^="#"]').forEach(a => {
  a.addEventListener('click', e => {
    const t = document.querySelector(a.getAttribute('href'));
    if (t) { e.preventDefault(); t.scrollIntoView({ behavior: 'smooth', block: 'start' }); }
  });
});
</script>
</body>
</html>