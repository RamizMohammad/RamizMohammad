<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;700&family=Syne:wght@400;700;800&display=swap');

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
    --border2: #ffffff20;
    --text: #e8e8f0;
    --muted: #6b6b80;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--ink);
    color: var(--text);
    font-family: 'Space Grotesk', sans-serif;
    line-height: 1.5;
    overflow-x: hidden;
    padding: 0;
  }

  /* SCAN LINE */
  body::before {
    content: '';
    position: fixed;
    top: 0; left: 0; right: 0; bottom: 0;
    background: repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0,0,0,0.03) 2px, rgba(0,0,0,0.03) 4px);
    pointer-events: none;
    z-index: 1000;
  }

  .wrapper {
    max-width: 860px;
    margin: 0 auto;
    padding: 3rem 1.5rem 5rem;
  }

  /* ─── HERO ─── */
  .hero {
    position: relative;
    border: 1px solid var(--border2);
    background: var(--ink2);
    border-radius: 2px;
    padding: 2.5rem 2rem 2rem;
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

  .noise-badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: var(--acid);
    color: #000;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 0.15em;
    padding: 4px 10px;
    border-radius: 2px;
    margin-bottom: 1.5rem;
    text-transform: uppercase;
  }

  .noise-badge::before {
    content: '▶';
    font-size: 7px;
    color: #000;
  }

  h1.name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(3rem, 9vw, 6rem);
    font-weight: 800;
    letter-spacing: -0.03em;
    line-height: 0.9;
    color: #fff;
    margin-bottom: 1rem;
  }

  h1.name span {
    display: block;
    color: var(--acid);
    -webkit-text-stroke: 1px var(--acid);
    text-shadow: 0 0 40px var(--acid)60;
  }

  .hero-meta {
    display: flex;
    gap: 2rem;
    margin-top: 1.5rem;
    flex-wrap: wrap;
  }

  .hero-meta-item {
    display: flex;
    flex-direction: column;
  }

  .hero-meta-item .label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    color: var(--muted);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 2px;
  }

  .hero-meta-item .val {
    font-size: 13px;
    color: var(--text);
    font-weight: 500;
  }

  .hero-coords {
    position: absolute;
    top: 1.5rem;
    right: 1.5rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    text-align: right;
    line-height: 1.8;
  }

  .hero-coords .live-dot {
    display: inline-block;
    width: 6px; height: 6px;
    background: var(--acid);
    border-radius: 50%;
    margin-right: 5px;
    animation: pulse 1.5s ease-in-out infinite;
  }

  @keyframes pulse {
    0%,100% { opacity: 1; }
    50% { opacity: 0.2; }
  }

  /* ─── TAG ROW ─── */
  .tag-row {
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
    margin: 1.5rem 0;
  }

  .tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    border: 1px solid var(--border2);
    padding: 4px 10px;
    border-radius: 2px;
    background: var(--ink3);
    transition: all 0.2s;
    cursor: default;
  }

  .tag:hover { color: var(--acid); border-color: var(--acid)50; }
  .tag.hi { color: var(--neon); border-color: var(--neon)30; }
  .tag.hi2 { color: var(--plasma); border-color: var(--plasma)30; }
  .tag.hi3 { color: var(--orange); border-color: var(--orange)30; }

  /* ─── SECTION LABEL ─── */
  .sec-label {
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-bottom: 1rem;
    margin-top: 2.5rem;
  }

  .sec-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ─── GRID ─── */
  .grid-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
  }

  .grid-3 {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 2px;
  }

  /* ─── STACK CARD ─── */
  .stack-card {
    background: var(--ink2);
    border: 1px solid var(--border);
    padding: 1.25rem;
    position: relative;
    overflow: hidden;
    transition: border-color 0.2s;
  }

  .stack-card:hover { border-color: var(--border2); }

  .stack-card .sc-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-bottom: 0.75rem;
  }

  .stack-card.android .sc-label { color: var(--neon); }
  .stack-card.backend .sc-label { color: var(--acid); }
  .stack-card.ai .sc-label { color: var(--plasma); }

  .tech-pill {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    background: var(--ink3);
    border: 1px solid var(--border);
    padding: 3px 8px;
    border-radius: 2px;
    font-size: 11px;
    font-weight: 500;
    color: var(--text);
    margin: 2px;
  }

  .dot {
    width: 5px; height: 5px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  .dot.neon { background: var(--neon); }
  .dot.acid { background: var(--acid); }
  .dot.plasma { background: var(--plasma); }
  .dot.orange { background: var(--orange); }

  /* ─── PROJECT CARDS ─── */
  .project-card {
    background: var(--ink2);
    border: 1px solid var(--border);
    padding: 1.5rem;
    position: relative;
    overflow: hidden;
    transition: all 0.25s;
    cursor: default;
  }

  .project-card:hover {
    border-color: var(--border2);
    background: #13141a;
  }

  .project-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 1px;
  }

  .project-card.p1::after { background: var(--plasma); }
  .project-card.p2::after { background: var(--acid); }
  .project-card.p3::after { background: var(--neon); }
  .project-card.p4::after { background: var(--orange); }
  .project-card.p5::after { background: var(--plasma); }
  .project-card.p6::after { background: var(--acid); }

  .p-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    margin-bottom: 0.75rem;
  }

  .p-name {
    font-family: 'Syne', sans-serif;
    font-size: 1.2rem;
    font-weight: 700;
    color: #fff;
    margin-bottom: 0.4rem;
    letter-spacing: -0.01em;
  }

  .p-desc {
    font-size: 12px;
    color: var(--muted);
    line-height: 1.6;
    margin-bottom: 1rem;
  }

  .p-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 4px;
  }

  .p-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    padding: 2px 7px;
    border-radius: 2px;
    border: 1px solid;
  }

  .p-tag.t1 { color: var(--plasma); border-color: var(--plasma)30; background: var(--plasma)08; }
  .p-tag.t2 { color: var(--acid); border-color: var(--acid)30; background: var(--acid)08; }
  .p-tag.t3 { color: var(--neon); border-color: var(--neon)30; background: var(--neon)08; }
  .p-tag.t4 { color: var(--orange); border-color: var(--orange)30; background: var(--orange)08; }

  /* ─── STAT STRIP ─── */
  .stat-strip {
    display: flex;
    gap: 2px;
    margin: 2px 0;
  }

  .stat-box {
    flex: 1;
    background: var(--ink2);
    border: 1px solid var(--border);
    padding: 1.25rem 1rem;
    display: flex;
    flex-direction: column;
    gap: 4px;
  }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 2.2rem;
    font-weight: 800;
    line-height: 1;
  }

  .stat-num.c1 { color: var(--acid); }
  .stat-num.c2 { color: var(--neon); }
  .stat-num.c3 { color: var(--plasma); }

  .stat-lbl {
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    color: var(--muted);
    letter-spacing: 0.15em;
    text-transform: uppercase;
  }

  /* ─── CONTACT ─── */
  .contact-row {
    display: flex;
    gap: 2px;
    flex-wrap: wrap;
    margin-top: 2px;
  }

  .contact-btn {
    flex: 1;
    min-width: 120px;
    background: var(--ink2);
    border: 1px solid var(--border);
    color: var(--muted);
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    padding: 0.9rem 1rem;
    display: flex;
    align-items: center;
    gap: 8px;
    cursor: pointer;
    transition: all 0.2s;
    text-decoration: none;
    letter-spacing: 0.05em;
  }

  .contact-btn:hover { color: #fff; border-color: var(--border2); background: var(--ink3); }
  .contact-btn .cb-icon { font-size: 14px; }

  /* ─── LEARNING TICKER ─── */
  .ticker-wrap {
    overflow: hidden;
    background: var(--ink2);
    border: 1px solid var(--border);
    border-left: 3px solid var(--acid);
    padding: 0.75rem 1rem;
    margin-top: 2px;
    position: relative;
  }

  .ticker-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    color: var(--acid);
    letter-spacing: 0.2em;
    margin-bottom: 4px;
    text-transform: uppercase;
  }

  .ticker-items {
    display: flex;
    gap: 2rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    overflow: hidden;
    white-space: nowrap;
    animation: ticker 14s linear infinite;
  }

  .ticker-items span { color: var(--text); }

  @keyframes ticker {
    0% { transform: translateX(0); }
    100% { transform: translateX(-50%); }
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
  }

  /* GLOW ACCENT */
  .glow-accent {
    position: fixed;
    width: 400px;
    height: 400px;
    background: radial-gradient(circle, var(--acid)06 0%, transparent 70%);
    border-radius: 50%;
    top: -100px;
    right: -100px;
    pointer-events: none;
    z-index: 0;
  }

  .glow-accent2 {
    position: fixed;
    width: 300px;
    height: 300px;
    background: radial-gradient(circle, var(--plasma)05 0%, transparent 70%);
    border-radius: 50%;
    bottom: 0;
    left: -80px;
    pointer-events: none;
    z-index: 0;
  }

  .rel { position: relative; z-index: 1; }

  /* ─── COPY BTN ─── */
  .copy-block {
    background: var(--ink3);
    border: 1px solid var(--border);
    border-left: 2px solid var(--neon);
    padding: 0.6rem 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 2px;
  }

  .copy-block code {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--neon);
  }

  .copy-block .copy-btn {
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    color: var(--muted);
    background: none;
    border: 1px solid var(--border2);
    padding: 3px 8px;
    cursor: pointer;
    transition: all 0.2s;
    border-radius: 2px;
    letter-spacing: 0.1em;
  }

  .copy-block .copy-btn:hover { color: var(--neon); border-color: var(--neon)40; }
</style>
</head>
<body>
<div class="glow-accent"></div>
<div class="glow-accent2"></div>

<div class="wrapper rel">

  <!-- ─── HERO ─── -->
  <div class="hero">
    <div class="hero-coords">
      <span class="live-dot"></span>AVAILABLE FOR WORK<br>
      IND / REMOTE<br>
      UTC+5:30
    </div>

    <div class="noise-badge">PROFILE_v2.0</div>

    <h1 class="name">
      MOHAMMAD
      <span>RAMIZ</span>
    </h1>

    <div class="hero-meta">
      <div class="hero-meta-item">
        <span class="label">Role</span>
        <span class="val">Android · Python Backend · AI/ML</span>
      </div>
      <div class="hero-meta-item">
        <span class="label">Currently building</span>
        <span class="val">HostForge · SupplierInv AI</span>
      </div>
      <div class="hero-meta-item">
        <span class="label">Vibe</span>
        <span class="val">Coding is meditation. Kaggle is the dojo.</span>
      </div>
    </div>
  </div>

  <!-- TAGS -->
  <div class="tag-row">
    <span class="tag hi">kotlin</span>
    <span class="tag hi2">python</span>
    <span class="tag hi3">fastapi</span>
    <span class="tag hi">gemini</span>
    <span class="tag">docker-swarm</span>
    <span class="tag">traefik</span>
    <span class="tag hi2">llm-pipelines</span>
    <span class="tag">redis</span>
    <span class="tag hi3">mongodb</span>
    <span class="tag hi">kmp</span>
    <span class="tag">rag-systems</span>
    <span class="tag hi2">kaggle</span>
    <span class="tag">oss-contributor</span>
  </div>

  <!-- ─── STATS ─── -->
  <div class="stat-strip">
    <div class="stat-box">
      <div class="stat-num c1">6+</div>
      <div class="stat-lbl">live projects</div>
    </div>
    <div class="stat-box">
      <div class="stat-num c2">3</div>
      <div class="stat-lbl">tech domains</div>
    </div>
    <div class="stat-box">
      <div class="stat-num c3">∞</div>
      <div class="stat-lbl">commits / curiosity</div>
    </div>
    <div class="stat-box">
      <div class="stat-num c1">5+</div>
      <div class="stat-lbl">years coding</div>
    </div>
  </div>

  <!-- ─── STACK ─── -->
  <div class="sec-label">// stack</div>

  <div class="grid-3">
    <div class="stack-card android">
      <div class="sc-label">Mobile</div>
      <div>
        <span class="tech-pill"><span class="dot neon"></span>Kotlin</span>
        <span class="tech-pill"><span class="dot neon"></span>Android</span>
        <span class="tech-pill"><span class="dot neon"></span>Java</span>
        <span class="tech-pill"><span class="dot neon"></span>Firebase</span>
        <span class="tech-pill"><span class="dot neon"></span>Room</span>
        <span class="tech-pill"><span class="dot neon"></span>WorkManager</span>
      </div>
    </div>
    <div class="stack-card backend">
      <div class="sc-label">Backend & Infra</div>
      <div>
        <span class="tech-pill"><span class="dot acid"></span>Python</span>
        <span class="tech-pill"><span class="dot acid"></span>FastAPI</span>
        <span class="tech-pill"><span class="dot acid"></span>Flask</span>
        <span class="tech-pill"><span class="dot acid"></span>Node.js</span>
        <span class="tech-pill"><span class="dot acid"></span>Docker</span>
        <span class="tech-pill"><span class="dot acid"></span>Swarm</span>
        <span class="tech-pill"><span class="dot acid"></span>Traefik</span>
        <span class="tech-pill"><span class="dot acid"></span>Redis</span>
        <span class="tech-pill"><span class="dot acid"></span>MongoDB</span>
        <span class="tech-pill"><span class="dot acid"></span>MySQL</span>
      </div>
    </div>
    <div class="stack-card ai">
      <div class="sc-label">AI / ML</div>
      <div>
        <span class="tech-pill"><span class="dot plasma"></span>Gemini</span>
        <span class="tech-pill"><span class="dot plasma"></span>TensorFlow</span>
        <span class="tech-pill"><span class="dot plasma"></span>PyTorch</span>
        <span class="tech-pill"><span class="dot plasma"></span>scikit-learn</span>
        <span class="tech-pill"><span class="dot plasma"></span>RAG</span>
        <span class="tech-pill"><span class="dot plasma"></span>LLM fine-tune</span>
        <span class="tech-pill"><span class="dot plasma"></span>OCR</span>
      </div>
    </div>
  </div>

  <!-- ─── PROJECTS ─── -->
  <div class="sec-label">// projects</div>

  <div class="grid-2">
    <div class="project-card p1">
      <div class="p-num">01 — ANDROID</div>
      <div class="p-name">Confess</div>
      <div class="p-desc">Anonymous confession app — real-time feeds, reactions & encrypted delivery. Shipped on Play Store.</div>
      <div class="p-tags">
        <span class="p-tag t1">Kotlin</span>
        <span class="p-tag t1">Firebase</span>
        <span class="p-tag t1">Android</span>
        <span class="p-tag t1">Play Store</span>
      </div>
    </div>

    <div class="project-card p2">
      <div class="p-num">02 — BACKEND</div>
      <div class="p-name">Linkium</div>
      <div class="p-desc">Smart branded link management — create, track & share short links at scale. Live production system.</div>
      <div class="p-tags">
        <span class="p-tag t2">Python</span>
        <span class="p-tag t2">FastAPI</span>
        <span class="p-tag t2">MongoDB</span>
        <span class="p-tag t2">linkium.space</span>
      </div>
    </div>

    <div class="project-card p3">
      <div class="p-num">03 — REALTIME</div>
      <div class="p-name">BuddyCode</div>
      <div class="p-desc">Collaborative pair-programming environment — live cursor sync across any language. Zero latency.</div>
      <div class="p-tags">
        <span class="p-tag t3">Node.js</span>
        <span class="p-tag t3">WebSockets</span>
        <span class="p-tag t3">Docker</span>
        <span class="p-tag t3">buddycode.online</span>
      </div>
    </div>

    <div class="project-card p4">
      <div class="p-num">04 — DEVOPS</div>
      <div class="p-name">HostForge</div>
      <div class="p-desc">Render-like hosting platform — Docker Swarm + Traefik TLS + Git deploys + free tier included.</div>
      <div class="p-tags">
        <span class="p-tag t4">FastAPI</span>
        <span class="p-tag t4">Docker Swarm</span>
        <span class="p-tag t4">Traefik</span>
        <span class="p-tag t4">Redis</span>
      </div>
    </div>

    <div class="project-card p5">
      <div class="p-num">05 — AI / ML</div>
      <div class="p-name">SupplierInv AI</div>
      <div class="p-desc">Gemini OCR invoice-to-PO matching — HSN validation, fuzzy logic, async queues with Redis.</div>
      <div class="p-tags">
        <span class="p-tag t1">Gemini</span>
        <span class="p-tag t1">FastAPI</span>
        <span class="p-tag t1">MongoDB</span>
        <span class="p-tag t1">Redis</span>
      </div>
    </div>

    <div class="project-card p6">
      <div class="p-num">06 — ANDROID</div>
      <div class="p-name">Mr. Manager</div>
      <div class="p-desc">Lightweight team task manager — offline-first architecture with background sync engine.</div>
      <div class="p-tags">
        <span class="p-tag t2">Kotlin</span>
        <span class="p-tag t2">Room</span>
        <span class="p-tag t2">WorkManager</span>
        <span class="p-tag t2">Open Source</span>
      </div>
    </div>
  </div>

  <!-- ─── CURRENTLY LEARNING ─── -->
  <div class="sec-label">// currently_learning</div>

  <div class="ticker-wrap">
    <div class="ticker-label">→ loading new skills</div>
    <div class="ticker-items">
      <span>Kotlin Multiplatform (KMP)</span> · 
      <span>LLM Fine-tuning</span> · 
      <span>RAG Systems</span> · 
      <span>Vector Databases</span> · 
      <span>Agent Frameworks</span> · 
      <span>Compose Multiplatform</span> · 
      &nbsp;&nbsp;&nbsp;
      <span>Kotlin Multiplatform (KMP)</span> · 
      <span>LLM Fine-tuning</span> · 
      <span>RAG Systems</span> · 
      <span>Vector Databases</span> · 
      <span>Agent Frameworks</span> · 
      <span>Compose Multiplatform</span>
    </div>
  </div>

  <!-- ─── CONTACT ─── -->
  <div class="sec-label">// connect</div>

  <div class="contact-row">
    <a class="contact-btn" href="https://www.linkedin.com/in/mohammad-ramiz-886468217">
      <span class="cb-icon">in</span>LinkedIn
    </a>
    <a class="contact-btn" href="https://twitter.com/mohammad__ramiz">
      <span class="cb-icon">𝕏</span>Twitter
    </a>
    <a class="contact-btn" href="https://kaggle.com/kobraop">
      <span class="cb-icon">◈</span>Kaggle
    </a>
    <a class="contact-btn" href="mailto:ramizanas6@gmail.com">
      <span class="cb-icon">@</span>Email
    </a>
    <a class="contact-btn" href="https://www.mohammadramiz.in">
      <span class="cb-icon">◎</span>Portfolio
    </a>
  </div>

  <!-- COPY SNIPPETS -->
  <div class="copy-block">
    <code>ramizanas6@gmail.com</code>
    <button class="copy-btn" onclick="navigator.clipboard.writeText('ramizanas6@gmail.com'); this.textContent='COPIED'; setTimeout(()=>this.textContent='COPY',1500)">COPY</button>
  </div>
  <div class="copy-block" style="border-left-color: var(--plasma);">
    <code>github.com/RamizMohammad</code>
    <button class="copy-btn" onclick="navigator.clipboard.writeText('github.com/RamizMohammad'); this.textContent='COPIED'; setTimeout(()=>this.textContent='COPY',1500)">COPY</button>
  </div>

  <!-- ─── FOOTER ─── -->
  <div class="footer">
    <div class="footer-left">
      crafted with <span>◈</span> by Mohammad Ramiz — 2025
    </div>
    <div class="footer-right">
      india / remote · android · python · ai
    </div>
  </div>

</div>
</body>
</html>
