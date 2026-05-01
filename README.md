<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="Mohammad Ramiz — Android · Python Backend · AI/ML Developer from India">
<meta property="og:title" content="Mohammad Ramiz — Dev Profile">
<meta property="og:description" content="Android · Python Backend · AI/ML | Building HostForge & SupplierInv AI">
<meta property="og:url" content="https://RamizMohammad.github.io">
<title>Mohammad Ramiz — Dev Profile</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;700&family=Syne:wght@400;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --acid: #c8ff00;
    --neon: #00ffe0;
    --plasma: #ff2cf3;
    --orange: #ff6b2b;
    --ink: #060608;
    --ink2: #0e0f13;
    --ink3: #15161c;
    --card: #111318;
    --border: #ffffff12;
    --border2: #ffffff22;
    --text: #e8e8f0;
    --muted: #6b6b80;
  }
 
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
 
  html { scroll-behavior: smooth; }
 
  body {
    background: var(--ink);
    color: var(--text);
    font-family: 'Space Grotesk', sans-serif;
    line-height: 1.5;
    overflow-x: hidden;
    min-height: 100vh;
  }
 
  /* scanline overlay */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.025) 2px,
      rgba(0,0,0,0.025) 4px
    );
    pointer-events: none;
    z-index: 9999;
  }
 
  /* ambient glows */
  .glow-1 {
    position: fixed;
    width: 600px; height: 600px;
    background: radial-gradient(circle, rgba(200,255,0,0.04) 0%, transparent 70%);
    border-radius: 50%;
    top: -200px; right: -100px;
    pointer-events: none;
    z-index: 0;
  }
  .glow-2 {
    position: fixed;
    width: 500px; height: 500px;
    background: radial-gradient(circle, rgba(255,44,243,0.04) 0%, transparent 70%);
    border-radius: 50%;
    bottom: -100px; left: -100px;
    pointer-events: none;
    z-index: 0;
  }
  .glow-3 {
    position: fixed;
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(0,255,224,0.03) 0%, transparent 70%);
    border-radius: 50%;
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    pointer-events: none;
    z-index: 0;
  }
 
  .wrapper {
    max-width: 920px;
    margin: 0 auto;
    padding: 2rem 1.5rem 6rem;
    position: relative;
    z-index: 1;
  }
 
  /* ─── TOP BAR ─── */
  .topbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-bottom: 2rem;
    border-bottom: 1px solid var(--border);
    margin-bottom: 2rem;
  }
 
  .topbar-logo {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    letter-spacing: 0.15em;
  }
  .topbar-logo span { color: var(--acid); }
 
  .topbar-nav {
    display: flex;
    gap: 1.5rem;
    list-style: none;
  }
 
  .topbar-nav a {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    text-decoration: none;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    transition: color 0.2s;
  }
 
  .topbar-nav a:hover { color: var(--acid); }
 
  /* ─── HERO ─── */
  .hero {
    position: relative;
    border: 1px solid var(--border2);
    background: var(--ink2);
    padding: 3rem 2.5rem 2.5rem;
    margin-bottom: 2px;
    overflow: hidden;
  }
 
  .hero::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--plasma), var(--neon), var(--acid));
  }
 
  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: var(--acid);
    color: #000;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 0.15em;
    padding: 4px 12px;
    margin-bottom: 2rem;
    text-transform: uppercase;
  }
 
  .hero-badge::before {
    content: '▶';
    font-size: 7px;
  }
 
  h1.name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(3.5rem, 10vw, 7.5rem);
    font-weight: 800;
    letter-spacing: -0.04em;
    line-height: 0.88;
    color: #fff;
    margin-bottom: 1.5rem;
  }
 
  h1.name .accent {
    display: block;
    color: var(--acid);
    text-shadow: 0 0 60px rgba(200,255,0,0.25);
  }
 
  .hero-meta {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 1.5rem;
    margin-top: 2rem;
    padding-top: 2rem;
    border-top: 1px solid var(--border);
  }
 
  .hero-meta-item .label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    color: var(--muted);
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-bottom: 4px;
  }
 
  .hero-meta-item .val {
    font-size: 13px;
    color: var(--text);
    font-weight: 500;
  }
 
  .hero-status {
    position: absolute;
    top: 2rem;
    right: 2rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    text-align: right;
    line-height: 1.9;
  }
 
  .live-dot {
    display: inline-block;
    width: 6px; height: 6px;
    background: var(--acid);
    border-radius: 50%;
    margin-right: 5px;
    animation: blink 1.5s ease-in-out infinite;
  }
 
  @keyframes blink {
    0%, 100% { opacity: 1; box-shadow: 0 0 4px var(--acid); }
    50% { opacity: 0.2; box-shadow: none; }
  }
 
  /* ─── TAGS ─── */
  .tag-row {
    display: flex;
    gap: 5px;
    flex-wrap: wrap;
    padding: 1rem 0;
    margin-bottom: 2px;
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
  }
 
  .tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    border: 1px solid var(--border2);
    padding: 4px 10px;
    background: var(--ink3);
    cursor: default;
    transition: all 0.2s;
    user-select: none;
  }
 
  .tag:hover { color: var(--acid); border-color: rgba(200,255,0,0.3); }
  .tag.a { color: var(--neon); border-color: rgba(0,255,224,0.2); }
  .tag.b { color: var(--plasma); border-color: rgba(255,44,243,0.2); }
  .tag.c { color: var(--orange); border-color: rgba(255,107,43,0.2); }
  .tag.d { color: var(--acid); border-color: rgba(200,255,0,0.2); }
 
  /* ─── STATS ─── */
  .stats {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 2px;
    margin-bottom: 2px;
  }
 
  .stat {
    background: var(--ink2);
    border: 1px solid var(--border);
    padding: 1.5rem 1.25rem;
    display: flex;
    flex-direction: column;
    gap: 6px;
    transition: border-color 0.2s;
  }
 
  .stat:hover { border-color: var(--border2); }
 
  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 2.8rem;
    font-weight: 800;
    line-height: 1;
  }
  .stat-num.s1 { color: var(--acid); }
  .stat-num.s2 { color: var(--neon); }
  .stat-num.s3 { color: var(--plasma); }
  .stat-num.s4 { color: var(--orange); }
 
  .stat-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    color: var(--muted);
    letter-spacing: 0.2em;
    text-transform: uppercase;
  }
 
  /* ─── SECTION HEADER ─── */
  .section-head {
    display: flex;
    align-items: center;
    gap: 12px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin: 2.5rem 0 1rem;
  }
 
  .section-head::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }
 
  /* ─── STACK ─── */
  .stack-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
    margin-bottom: 2px;
  }
 
  .stack-card {
    background: var(--ink2);
    border: 1px solid var(--border);
    padding: 1.5rem;
    transition: border-color 0.2s;
  }
 
  .stack-card:hover { border-color: var(--border2); }
 
  .stack-cat {
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-bottom: 1rem;
    padding-bottom: 0.75rem;
    border-bottom: 1px solid var(--border);
  }
 
  .stack-card.mobile .stack-cat { color: var(--neon); }
  .stack-card.backend .stack-cat { color: var(--acid); }
  .stack-card.ai .stack-cat { color: var(--plasma); }
 
  .tech-pill {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    background: var(--ink3);
    border: 1px solid var(--border);
    padding: 4px 9px;
    font-size: 11px;
    font-weight: 500;
    color: var(--text);
    margin: 2px;
    transition: border-color 0.2s;
  }
 
  .tech-pill:hover { border-color: var(--border2); }
 
  .dot {
    width: 5px; height: 5px;
    border-radius: 50%;
    flex-shrink: 0;
  }
 
  .dot.neon { background: var(--neon); }
  .dot.acid { background: var(--acid); }
  .dot.plasma { background: var(--plasma); }
 
  /* ─── PROJECTS ─── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
  }
 
  .project-card {
    background: var(--ink2);
    border: 1px solid var(--border);
    padding: 1.75rem;
    position: relative;
    overflow: hidden;
    transition: all 0.25s;
    cursor: default;
  }
 
  .project-card:hover {
    background: #13141b;
    border-color: var(--border2);
  }
 
  .project-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 1px;
    opacity: 0;
    transition: opacity 0.25s;
  }
 
  .project-card:hover::after { opacity: 1; }
 
  .project-card.p1::after { background: var(--plasma); }
  .project-card.p2::after { background: var(--acid); }
  .project-card.p3::after { background: var(--neon); }
  .project-card.p4::after { background: var(--orange); }
  .project-card.p5::after { background: var(--plasma); }
  .project-card.p6::after { background: var(--acid); }
 
  .p-number {
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    color: var(--muted);
    letter-spacing: 0.2em;
    margin-bottom: 0.75rem;
  }
 
  .p-name {
    font-family: 'Syne', sans-serif;
    font-size: 1.4rem;
    font-weight: 700;
    color: #fff;
    letter-spacing: -0.02em;
    margin-bottom: 0.5rem;
  }
 
  .p-desc {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.7;
    margin-bottom: 1.25rem;
  }
 
  .p-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 4px;
  }
 
  .p-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    padding: 3px 8px;
    border: 1px solid;
    letter-spacing: 0.05em;
  }
 
  .t-plasma { color: var(--plasma); border-color: rgba(255,44,243,0.25); background: rgba(255,44,243,0.05); }
  .t-acid   { color: var(--acid);   border-color: rgba(200,255,0,0.25);   background: rgba(200,255,0,0.05); }
  .t-neon   { color: var(--neon);   border-color: rgba(0,255,224,0.25);   background: rgba(0,255,224,0.05); }
  .t-orange { color: var(--orange); border-color: rgba(255,107,43,0.25);  background: rgba(255,107,43,0.05); }
 
  .p-link {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    margin-top: 1rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    text-decoration: none;
    letter-spacing: 0.1em;
    transition: color 0.2s;
  }
 
  .p-link:hover { color: var(--acid); }
 
  /* ─── TICKER ─── */
  .ticker-block {
    background: var(--ink2);
    border: 1px solid var(--border);
    border-left: 3px solid var(--acid);
    padding: 1rem 1.25rem;
    overflow: hidden;
    margin-bottom: 2px;
  }
 
  .ticker-head {
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    color: var(--acid);
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-bottom: 6px;
  }
 
  .ticker-track {
    white-space: nowrap;
    animation: scroll 18s linear infinite;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--muted);
  }
 
  .ticker-track span { color: var(--text); }
 
  @keyframes scroll {
    0% { transform: translateX(0); }
    100% { transform: translateX(-50%); }
  }
 
  /* ─── CONTACT ─── */
  .contact-grid {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 2px;
  }
 
  .contact-btn {
    background: var(--ink2);
    border: 1px solid var(--border);
    color: var(--muted);
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    padding: 1rem 0.75rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    cursor: pointer;
    transition: all 0.2s;
    text-decoration: none;
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }
 
  .contact-btn:hover {
    color: #fff;
    border-color: var(--border2);
    background: var(--ink3);
  }
 
  .contact-btn:hover .cb-label { color: var(--acid); }
 
  .contact-icon {
    font-size: 20px;
    line-height: 1;
  }
 
  .cb-label {
    font-size: 9px;
    color: var(--muted);
    transition: color 0.2s;
    letter-spacing: 0.15em;
  }
 
  /* COPY ROW */
  .copy-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
    margin-top: 2px;
    margin-bottom: 2px;
  }
 
  .copy-block {
    background: var(--ink3);
    border: 1px solid var(--border);
    padding: 0.75rem 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
 
  .copy-block.cb-neon { border-left: 2px solid var(--neon); }
  .copy-block.cb-plasma { border-left: 2px solid var(--plasma); }
 
  .copy-block code {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--neon);
  }
 
  .copy-block.cb-plasma code { color: var(--plasma); }
 
  .copy-btn {
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    color: var(--muted);
    background: none;
    border: 1px solid var(--border2);
    padding: 3px 10px;
    cursor: pointer;
    transition: all 0.2s;
    letter-spacing: 0.12em;
  }
 
  .copy-btn:hover { color: var(--acid); border-color: rgba(200,255,0,0.3); }
 
  /* ─── GITHUB STATS ─── */
  .gh-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
    margin-bottom: 2px;
  }
 
  .gh-stats img {
    width: 100%;
    display: block;
    filter: brightness(0.95);
  }
 
  /* ─── FOOTER ─── */
  .footer {
    border-top: 1px solid var(--border);
    margin-top: 3rem;
    padding-top: 1.5rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 1rem;
  }
 
  .footer-left {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
  }
  .footer-left span { color: var(--acid); }
 
  .footer-right {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    display: flex;
    align-items: center;
    gap: 1rem;
  }
 
  /* ─── RESPONSIVE ─── */
  @media (max-width: 700px) {
    .stats { grid-template-columns: 1fr 1fr; }
    .stack-grid { grid-template-columns: 1fr; }
    .projects-grid { grid-template-columns: 1fr; }
    .contact-grid { grid-template-columns: repeat(3, 1fr); }
    .copy-row { grid-template-columns: 1fr; }
    .gh-stats { grid-template-columns: 1fr; }
    .topbar-nav { display: none; }
    .hero-status { display: none; }
    h1.name { font-size: 3.5rem; }
  }
</style>
</head>
<body>
 
<div class="glow-1"></div>
<div class="glow-2"></div>
<div class="glow-3"></div>
 
<div class="wrapper">
 
  <!-- TOP BAR -->
  <div class="topbar">
    <div class="topbar-logo"><span>◈</span> MR.DEV</div>
    <nav>
      <ul class="topbar-nav">
        <li><a href="#stack">stack</a></li>
        <li><a href="#projects">projects</a></li>
        <li><a href="#connect">connect</a></li>
        <li><a href="https://github.com/RamizMohammad" target="_blank">github ↗</a></li>
      </ul>
    </nav>
  </div>
 
  <!-- HERO -->
  <div class="hero">
    <div class="hero-status">
      <span class="live-dot"></span>AVAILABLE FOR WORK<br>
      IND / REMOTE<br>
      UTC+5:30
    </div>
 
    <div class="hero-badge">PROFILE_v2.0</div>
 
    <h1 class="name">
      MOHAMMAD
      <span class="accent">RAMIZ</span>
    </h1>
 
    <div class="hero-meta">
      <div class="hero-meta-item">
        <div class="label">Role</div>
        <div class="val">Android · Python Backend · AI/ML</div>
      </div>
      <div class="hero-meta-item">
        <div class="label">Currently Building</div>
        <div class="val">HostForge · SupplierInv AI</div>
      </div>
      <div class="hero-meta-item">
        <div class="label">Learning</div>
        <div class="val">KMP · LLM Fine-tuning · RAG Systems</div>
      </div>
      <div class="hero-meta-item">
        <div class="label">Vibe</div>
        <div class="val">Coding is meditation. Kaggle is the dojo.</div>
      </div>
    </div>
  </div>
 
  <!-- TAGS -->
  <div class="tag-row">
    <span class="tag a">kotlin</span>
    <span class="tag b">python</span>
    <span class="tag c">fastapi</span>
    <span class="tag d">gemini</span>
    <span class="tag">docker-swarm</span>
    <span class="tag">traefik</span>
    <span class="tag b">llm-pipelines</span>
    <span class="tag">redis</span>
    <span class="tag c">mongodb</span>
    <span class="tag a">kmp</span>
    <span class="tag">rag-systems</span>
    <span class="tag b">kaggle</span>
    <span class="tag">oss-contributor</span>
    <span class="tag d">firebase</span>
    <span class="tag">pytorch</span>
    <span class="tag a">tensorflow</span>
  </div>
 
  <!-- STATS -->
  <div class="stats">
    <div class="stat">
      <div class="stat-num s1">6+</div>
      <div class="stat-label">live projects</div>
    </div>
    <div class="stat">
      <div class="stat-num s2">3</div>
      <div class="stat-label">tech domains</div>
    </div>
    <div class="stat">
      <div class="stat-num s3">∞</div>
      <div class="stat-label">commits/curiosity</div>
    </div>
    <div class="stat">
      <div class="stat-num s4">5+</div>
      <div class="stat-label">years coding</div>
    </div>
  </div>
 
  <!-- STACK -->
  <div class="section-head" id="stack">// stack</div>
 
  <div class="stack-grid">
    <div class="stack-card mobile">
      <div class="stack-cat">Mobile</div>
      <div>
        <span class="tech-pill"><span class="dot neon"></span>Kotlin</span>
        <span class="tech-pill"><span class="dot neon"></span>Android</span>
        <span class="tech-pill"><span class="dot neon"></span>Java</span>
        <span class="tech-pill"><span class="dot neon"></span>Firebase</span>
        <span class="tech-pill"><span class="dot neon"></span>Jetpack Compose</span>
        <span class="tech-pill"><span class="dot neon"></span>Room</span>
        <span class="tech-pill"><span class="dot neon"></span>WorkManager</span>
        <span class="tech-pill"><span class="dot neon"></span>FCM</span>
      </div>
    </div>
    <div class="stack-card backend">
      <div class="stack-cat">Backend & Infra</div>
      <div>
        <span class="tech-pill"><span class="dot acid"></span>Python</span>
        <span class="tech-pill"><span class="dot acid"></span>FastAPI</span>
        <span class="tech-pill"><span class="dot acid"></span>Flask</span>
        <span class="tech-pill"><span class="dot acid"></span>Node.js</span>
        <span class="tech-pill"><span class="dot acid"></span>Docker</span>
        <span class="tech-pill"><span class="dot acid"></span>Docker Swarm</span>
        <span class="tech-pill"><span class="dot acid"></span>Traefik</span>
        <span class="tech-pill"><span class="dot acid"></span>Redis</span>
        <span class="tech-pill"><span class="dot acid"></span>MongoDB</span>
        <span class="tech-pill"><span class="dot acid"></span>MySQL</span>
      </div>
    </div>
    <div class="stack-card ai">
      <div class="stack-cat">AI / ML</div>
      <div>
        <span class="tech-pill"><span class="dot plasma"></span>Gemini</span>
        <span class="tech-pill"><span class="dot plasma"></span>TensorFlow</span>
        <span class="tech-pill"><span class="dot plasma"></span>PyTorch</span>
        <span class="tech-pill"><span class="dot plasma"></span>scikit-learn</span>
        <span class="tech-pill"><span class="dot plasma"></span>RAG</span>
        <span class="tech-pill"><span class="dot plasma"></span>LLM Fine-tuning</span>
        <span class="tech-pill"><span class="dot plasma"></span>OCR / Vision</span>
        <span class="tech-pill"><span class="dot plasma"></span>Arduino</span>
      </div>
    </div>
  </div>
 
  <!-- PROJECTS -->
  <div class="section-head" id="projects">// projects</div>
 
  <div class="projects-grid">
    <div class="project-card p1">
      <div class="p-number">01 — ANDROID · SOCIAL</div>
      <div class="p-name">Confess</div>
      <div class="p-desc">Anonymous confession app — real-time feeds, reactions & encrypted delivery. Shipped on Play Store.</div>
      <div class="p-tags">
        <span class="p-tag t-plasma">Kotlin</span>
        <span class="p-tag t-plasma">Firebase</span>
        <span class="p-tag t-plasma">Android</span>
        <span class="p-tag t-plasma">Encrypted</span>
      </div>
      <a class="p-link" href="https://play.google.com/store/apps/details?id=in.mohammad.ramiz.confess" target="_blank">▶ Play Store ↗</a>
    </div>
 
    <div class="project-card p2">
      <div class="p-number">02 — BACKEND · SaaS</div>
      <div class="p-name">Linkium</div>
      <div class="p-desc">Smart branded link management — create, track & share short links at scale. Live production system.</div>
      <div class="p-tags">
        <span class="p-tag t-acid">Python</span>
        <span class="p-tag t-acid">FastAPI</span>
        <span class="p-tag t-acid">MongoDB</span>
        <span class="p-tag t-acid">Analytics</span>
      </div>
      <a class="p-link" href="https://www.linkium.space" target="_blank">▶ linkium.space ↗</a>
    </div>
 
    <div class="project-card p3">
      <div class="p-number">03 — REALTIME · DEV TOOLS</div>
      <div class="p-name">BuddyCode</div>
      <div class="p-desc">Collaborative pair-programming environment — live cursor sync, any language, zero latency.</div>
      <div class="p-tags">
        <span class="p-tag t-neon">Node.js</span>
        <span class="p-tag t-neon">WebSockets</span>
        <span class="p-tag t-neon">Docker</span>
        <span class="p-tag t-neon">Real-time</span>
      </div>
      <a class="p-link" href="https://www.buddycode.online" target="_blank">▶ buddycode.online ↗</a>
    </div>
 
    <div class="project-card p4">
      <div class="p-number">04 — DEVOPS · PLATFORM</div>
      <div class="p-name">HostForge</div>
      <div class="p-desc">Render-like developer hosting — Docker Swarm + Traefik TLS + Git deploys + free tier.</div>
      <div class="p-tags">
        <span class="p-tag t-orange">FastAPI</span>
        <span class="p-tag t-orange">Docker Swarm</span>
        <span class="p-tag t-orange">Traefik</span>
        <span class="p-tag t-orange">Redis</span>
      </div>
      <a class="p-link" href="https://github.com/RamizMohammad" target="_blank">▶ Source ↗</a>
    </div>
 
    <div class="project-card p5">
      <div class="p-number">05 — AI/ML · ENTERPRISE</div>
      <div class="p-name">SupplierInv AI</div>
      <div class="p-desc">Gemini OCR invoice-to-PO matching — HSN validation, fuzzy logic, async Redis queues.</div>
      <div class="p-tags">
        <span class="p-tag t-plasma">Gemini</span>
        <span class="p-tag t-plasma">FastAPI</span>
        <span class="p-tag t-plasma">MongoDB</span>
        <span class="p-tag t-plasma">Redis</span>
      </div>
      <a class="p-link" href="https://github.com/RamizMohammad" target="_blank">▶ Source ↗</a>
    </div>
 
    <div class="project-card p6">
      <div class="p-number">06 — ANDROID · PRODUCTIVITY</div>
      <div class="p-name">Mr. Manager</div>
      <div class="p-desc">Lightweight Android task & team manager — offline-first architecture with background sync engine.</div>
      <div class="p-tags">
        <span class="p-tag t-acid">Kotlin</span>
        <span class="p-tag t-acid">Room</span>
        <span class="p-tag t-acid">WorkManager</span>
        <span class="p-tag t-acid">Open Source</span>
      </div>
      <a class="p-link" href="https://github.com/KobraOp/Mr.-Manager" target="_blank">▶ Source ↗</a>
    </div>
  </div>
 
  <!-- GITHUB STATS -->
  <div class="section-head">// git log --stat</div>
 
  <div class="gh-stats">
    <img src="https://github-readme-stats.vercel.app/api?username=RamizMohammad&show_icons=true&theme=dark&hide_border=true&bg_color=0e0f13&title_color=c8ff00&icon_color=00ffe0&text_color=e8e8f0&ring_color=c8ff00&include_all_commits=true&count_private=true" alt="GitHub Stats">
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=RamizMohammad&layout=compact&theme=dark&hide_border=true&bg_color=0e0f13&title_color=c8ff00&text_color=e8e8f0&langs_count=8" alt="Top Languages">
  </div>
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=RamizMohammad&theme=react-dark&hide_border=true&bg_color=0e0f13&color=c8ff00&line=00ffe0&point=ff2cf3&area=true&area_color=1a2200&custom_title=Commit%20Activity&radius=0" alt="Activity Graph" style="width:100%; display:block; margin-bottom: 2px; filter: brightness(0.95);">
 
  <!-- LEARNING TICKER -->
  <div class="section-head">// currently_learning</div>
 
  <div class="ticker-block">
    <div class="ticker-head">→ incoming skills</div>
    <div class="ticker-track">
      <span>Kotlin Multiplatform</span> &nbsp;·&nbsp;
      <span>LLM Fine-tuning</span> &nbsp;·&nbsp;
      <span>RAG Systems</span> &nbsp;·&nbsp;
      <span>Vector Databases</span> &nbsp;·&nbsp;
      <span>Agent Frameworks</span> &nbsp;·&nbsp;
      <span>Compose Multiplatform</span> &nbsp;·&nbsp;
      <span>Qdrant</span> &nbsp;·&nbsp;
      <span>LangChain</span> &nbsp;·&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      <span>Kotlin Multiplatform</span> &nbsp;·&nbsp;
      <span>LLM Fine-tuning</span> &nbsp;·&nbsp;
      <span>RAG Systems</span> &nbsp;·&nbsp;
      <span>Vector Databases</span> &nbsp;·&nbsp;
      <span>Agent Frameworks</span> &nbsp;·&nbsp;
      <span>Compose Multiplatform</span> &nbsp;·&nbsp;
      <span>Qdrant</span> &nbsp;·&nbsp;
      <span>LangChain</span>
    </div>
  </div>
 
  <!-- CONNECT -->
  <div class="section-head" id="connect">// connect</div>
 
  <div class="contact-grid">
    <a class="contact-btn" href="https://www.linkedin.com/in/mohammad-ramiz-886468217" target="_blank">
      <span class="contact-icon">in</span>
      <span class="cb-label">LinkedIn</span>
    </a>
    <a class="contact-btn" href="https://twitter.com/mohammad__ramiz" target="_blank">
      <span class="contact-icon">𝕏</span>
      <span class="cb-label">Twitter</span>
    </a>
    <a class="contact-btn" href="https://kaggle.com/kobraop" target="_blank">
      <span class="contact-icon">◈</span>
      <span class="cb-label">Kaggle</span>
    </a>
    <a class="contact-btn" href="mailto:ramizanas6@gmail.com">
      <span class="contact-icon">@</span>
      <span class="cb-label">Email</span>
    </a>
    <a class="contact-btn" href="https://www.mohammadramiz.in" target="_blank">
      <span class="contact-icon">◎</span>
      <span class="cb-label">Portfolio</span>
    </a>
  </div>
 
  <div class="copy-row">
    <div class="copy-block cb-neon">
      <code>ramizanas6@gmail.com</code>
      <button class="copy-btn" onclick="navigator.clipboard.writeText('ramizanas6@gmail.com'); this.textContent='COPIED ✓'; setTimeout(()=>this.textContent='COPY',1800)">COPY</button>
    </div>
    <div class="copy-block cb-plasma">
      <code>github.com/RamizMohammad</code>
      <button class="copy-btn" onclick="navigator.clipboard.writeText('github.com/RamizMohammad'); this.textContent='COPIED ✓'; setTimeout(()=>this.textContent='COPY',1800)">COPY</button>
    </div>
  </div>
 
  <!-- FOOTER -->
  <div class="footer">
    <div class="footer-left">crafted with <span>◈</span> by Mohammad Ramiz — 2025</div>
    <div class="footer-right">
      <span>India / Remote</span>
      <span>·</span>
      <span>Android · Python · AI</span>
    </div>
  </div>
 
</div>
</body>
</html>
 
