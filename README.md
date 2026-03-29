<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shivani Kumari Singh — README Preview</title>
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Rajdhani:wght@300;400;500;600;700&family=Orbitron:wght@400;600;700;900&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #020b14;
    --bg2: #040f1c;
    --panel: #071828;
    --border: #0d4f6e;
    --accent: #00d4ff;
    --accent2: #7b2fff;
    --accent3: #00ff9f;
    --warn: #ff6b35;
    --text: #c8e8f8;
    --muted: #4a7a96;
    --glow: 0 0 20px rgba(0,212,255,0.4);
    --glow2: 0 0 20px rgba(123,47,255,0.4);
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Rajdhani', sans-serif;
    font-size: 16px;
    line-height: 1.6;
    overflow-x: hidden;
  }

  /* SCANLINE OVERLAY */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.05) 2px,
      rgba(0,0,0,0.05) 4px
    );
    pointer-events: none;
    z-index: 1000;
  }

  /* GRID BG */
  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,212,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,212,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 960px;
    margin: 0 auto;
    padding: 40px 24px;
    position: relative;
    z-index: 1;
  }

  /* ═══ HERO ═══ */
  .hero {
    position: relative;
    padding: 48px 0 32px;
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 40px;
    align-items: center;
  }

  .hero-badge {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    color: var(--accent3);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .hero-badge::before { content: '▶'; animation: blink 1.2s infinite; }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  .hero h1 {
    font-family: 'Orbitron', monospace;
    font-size: clamp(28px, 5vw, 48px);
    font-weight: 900;
    line-height: 1.1;
    background: linear-gradient(135deg, #fff 0%, var(--accent) 50%, var(--accent2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 16px;
  }

  .hero-sub {
    font-size: 17px;
    color: var(--muted);
    font-weight: 400;
    max-width: 540px;
    line-height: 1.7;
  }
  .hero-sub strong { color: var(--accent); font-weight: 600; }

  .avatar-wrap {
    position: relative;
    width: 160px;
    height: 160px;
    flex-shrink: 0;
  }
  .avatar-wrap img {
    width: 160px;
    height: 160px;
    border-radius: 50%;
    object-fit: cover;
    border: 3px solid var(--accent);
    box-shadow: var(--glow), 0 0 60px rgba(0,212,255,0.2);
    display: block;
  }
  .avatar-ring {
    position: absolute;
    inset: -12px;
    border-radius: 50%;
    border: 1px solid rgba(0,212,255,0.3);
    animation: spin 12s linear infinite;
  }
  .avatar-ring::after {
    content: '';
    position: absolute;
    top: 4px; left: 4px;
    width: 12px; height: 12px;
    background: var(--accent3);
    border-radius: 50%;
    box-shadow: 0 0 10px var(--accent3);
  }
  @keyframes spin { to { transform: rotate(360deg); } }

  /* STATUS PILLS */
  .status-row {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
    margin-top: 20px;
  }
  .pill {
    display: flex;
    align-items: center;
    gap: 6px;
    background: rgba(0,212,255,0.06);
    border: 1px solid rgba(0,212,255,0.2);
    border-radius: 100px;
    padding: 5px 14px;
    font-size: 12px;
    font-family: 'Share Tech Mono', monospace;
    color: var(--accent);
    letter-spacing: 1px;
  }
  .pill.green { color: var(--accent3); border-color: rgba(0,255,159,0.25); background: rgba(0,255,159,0.05); }
  .pill.purple { color: #c084fc; border-color: rgba(192,132,252,0.25); background: rgba(192,132,252,0.05); }
  .pill::before { content: '●'; font-size: 8px; animation: blink 2s infinite; }

  /* ═══ DIVIDER ═══ */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border), var(--accent), var(--border), transparent);
    margin: 32px 0;
    position: relative;
  }
  .divider::after {
    content: attr(data-label);
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: var(--bg);
    padding: 0 16px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    color: var(--accent);
    letter-spacing: 3px;
  }

  /* ═══ SECTION TITLES ═══ */
  .section-title {
    font-family: 'Orbitron', monospace;
    font-size: 14px;
    font-weight: 700;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  /* ═══ GAME ═══ */
  .game-section {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    position: relative;
    box-shadow: 0 0 40px rgba(0,0,0,0.6), inset 0 1px 0 rgba(255,255,255,0.05);
  }
  .game-header {
    background: rgba(0,212,255,0.06);
    border-bottom: 1px solid var(--border);
    padding: 12px 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-family: 'Share Tech Mono', monospace;
    font-size: 12px;
    color: var(--muted);
  }
  .game-header span { color: var(--accent); }
  .dot-row { display: flex; gap: 6px; }
  .dot { width: 10px; height: 10px; border-radius: 50%; }
  .dot.r { background: #ff5f57; }
  .dot.y { background: #febc2e; }
  .dot.g { background: #28c840; }

  canvas#gameCanvas {
    display: block;
    width: 100%;
    max-width: 920px;
    height: 280px;
    cursor: crosshair;
    background: #010a10;
  }

  .game-controls {
    padding: 12px 20px;
    display: flex;
    align-items: center;
    gap: 16px;
    border-top: 1px solid var(--border);
    background: rgba(0,0,0,0.3);
    flex-wrap: wrap;
  }
  .game-controls .info {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    flex: 1;
  }
  .game-controls .info span { color: var(--accent3); }

  .btn {
    font-family: 'Share Tech Mono', monospace;
    font-size: 12px;
    letter-spacing: 2px;
    padding: 8px 20px;
    border: 1px solid var(--accent);
    background: rgba(0,212,255,0.08);
    color: var(--accent);
    cursor: pointer;
    border-radius: 4px;
    transition: all 0.2s;
    text-transform: uppercase;
  }
  .btn:hover {
    background: rgba(0,212,255,0.2);
    box-shadow: var(--glow);
    transform: translateY(-1px);
  }
  .btn.red { border-color: var(--warn); color: var(--warn); background: rgba(255,107,53,0.08); }
  .btn.red:hover { background: rgba(255,107,53,0.2); box-shadow: 0 0 20px rgba(255,107,53,0.4); }

  /* ═══ PROJECTS ═══ */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 20px;
  }

  .project-card {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 24px;
    position: relative;
    overflow: hidden;
    transition: transform 0.3s, box-shadow 0.3s, border-color 0.3s;
    cursor: default;
  }
  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
  }
  .project-card.blue::before { background: linear-gradient(90deg, var(--accent2), var(--accent)); }
  .project-card.green::before { background: linear-gradient(90deg, var(--accent3), var(--accent)); }
  .project-card.orange::before { background: linear-gradient(90deg, var(--warn), #ffcc00); }

  .project-card:hover {
    transform: translateY(-4px);
    border-color: rgba(0,212,255,0.4);
    box-shadow: 0 12px 40px rgba(0,0,0,0.5), 0 0 30px rgba(0,212,255,0.1);
  }

  .project-icon {
    font-size: 28px;
    margin-bottom: 12px;
    display: block;
  }
  .project-title {
    font-family: 'Orbitron', monospace;
    font-size: 14px;
    font-weight: 700;
    color: #fff;
    margin-bottom: 4px;
  }
  .project-subtitle {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 1px;
    margin-bottom: 12px;
    text-transform: uppercase;
  }
  .project-desc {
    font-size: 14px;
    color: var(--text);
    line-height: 1.6;
    margin-bottom: 16px;
    opacity: 0.85;
  }
  .tag-row { display: flex; flex-wrap: wrap; gap: 6px; }
  .tag {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    padding: 3px 9px;
    border-radius: 100px;
    border: 1px solid rgba(0,212,255,0.2);
    color: var(--muted);
    letter-spacing: 0.5px;
  }

  /* ═══ TECH STACK ═══ */
  .tech-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }
  .tech-badge {
    display: flex;
    align-items: center;
    gap: 7px;
    background: rgba(0,212,255,0.05);
    border: 1px solid rgba(0,212,255,0.15);
    border-radius: 6px;
    padding: 7px 14px;
    font-size: 13px;
    font-weight: 600;
    color: var(--text);
    transition: all 0.2s;
  }
  .tech-badge:hover {
    background: rgba(0,212,255,0.12);
    border-color: var(--accent);
    transform: scale(1.05);
    color: #fff;
  }
  .tech-badge .icon { font-size: 16px; }

  /* ═══ SKILLS BAR ═══ */
  .skills-list { display: flex; flex-direction: column; gap: 14px; }
  .skill-item label {
    display: flex;
    justify-content: space-between;
    font-family: 'Share Tech Mono', monospace;
    font-size: 12px;
    color: var(--accent);
    letter-spacing: 1px;
    margin-bottom: 6px;
    text-transform: uppercase;
  }
  .skill-item label span { color: var(--muted); }
  .skill-bar {
    height: 6px;
    background: rgba(255,255,255,0.05);
    border-radius: 100px;
    overflow: hidden;
    position: relative;
  }
  .skill-bar-fill {
    height: 100%;
    border-radius: 100px;
    position: relative;
    animation: growBar 1.5s cubic-bezier(0.16, 1, 0.3, 1) forwards;
    transform-origin: left;
  }
  @keyframes growBar { from { width: 0 !important; } }
  .skill-bar-fill::after {
    content: '';
    position: absolute;
    top: 0; right: 0;
    width: 4px; height: 100%;
    background: #fff;
    border-radius: 100px;
    box-shadow: 0 0 8px currentColor;
  }

  /* ═══ SOCIAL ═══ */
  .social-row {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
  }
  .social-btn {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 11px 20px;
    border: 1px solid var(--border);
    border-radius: 8px;
    background: var(--panel);
    color: var(--text);
    text-decoration: none;
    font-size: 14px;
    font-weight: 600;
    font-family: 'Rajdhani', sans-serif;
    transition: all 0.25s;
  }
  .social-btn:hover {
    border-color: var(--accent);
    color: var(--accent);
    box-shadow: var(--glow);
    transform: translateY(-2px);
  }
  .social-btn .sicon { font-size: 18px; }

  /* ═══ STATS CARDS ═══ */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 16px;
  }
  .stat-card {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px;
    text-align: center;
    position: relative;
    overflow: hidden;
    transition: transform 0.2s;
  }
  .stat-card:hover { transform: translateY(-3px); }
  .stat-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent2), var(--accent));
  }
  .stat-num {
    font-family: 'Orbitron', monospace;
    font-size: 32px;
    font-weight: 900;
    color: var(--accent);
    text-shadow: var(--glow);
    display: block;
  }
  .stat-label {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-top: 4px;
    display: block;
  }

  /* ═══ FOOTER ═══ */
  .footer {
    text-align: center;
    padding: 40px 0 20px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    letter-spacing: 2px;
  }
  .footer strong { color: var(--accent); }

  /* ═══ TYPING EFFECT ═══ */
  .typing {
    font-family: 'Share Tech Mono', monospace;
    font-size: 15px;
    color: var(--accent3);
    overflow: hidden;
    border-right: 2px solid var(--accent3);
    white-space: nowrap;
    animation: typing 3s steps(40, end) forwards, cursor 0.75s step-end infinite;
    width: 0;
  }
  @keyframes typing { to { width: 100%; } }
  @keyframes cursor { 0%,100%{border-color:var(--accent3)} 50%{border-color:transparent} }

  /* ═══ TERMINAL BOX ═══ */
  .terminal {
    background: #010810;
    border: 1px solid var(--border);
    border-radius: 10px;
    overflow: hidden;
  }
  .terminal-bar {
    background: #071220;
    border-bottom: 1px solid var(--border);
    padding: 10px 16px;
    display: flex;
    align-items: center;
    gap: 16px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 12px;
    color: var(--muted);
  }
  .terminal-body {
    padding: 20px 24px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 13px;
    line-height: 2;
  }
  .terminal-body .prompt { color: var(--accent3); }
  .terminal-body .cmd { color: #fff; }
  .terminal-body .output { color: var(--muted); }
  .terminal-body .highlight { color: var(--accent); }
  .terminal-body .val { color: #c084fc; }

  @media (max-width: 640px) {
    .hero { grid-template-columns: 1fr; }
    .avatar-wrap { order: -1; margin: 0 auto; }
  }
</style>
</head>
<body>
<div class="container">

  <!-- ═══ HERO ═══ -->
  <section class="hero">
    <div>
      <div class="hero-badge">// INITIALIZED — PROFILE.README.MD</div>
      <h1>Shivani Kumari Singh</h1>
      <p class="hero-sub">
        <strong>B.Tech CSE · Cybersecurity</strong> — Engineering secure systems at the intersection of
        network defense, post-quantum cryptography, and modern web development.
        CTF competitor · Vulnerability hunter · Frontend craftsperson.
      </p>
      <div class="status-row">
        <div class="pill green">OPEN TO OPPORTUNITIES</div>
        <div class="pill">CTF ACTIVE</div>
        <div class="pill purple">PQC RESEARCH</div>
      </div>
    </div>
    <div class="avatar-wrap">
      <img src="https://raw.githubusercontent.com/shivanisingh-sks/shivanisingh-sks/main/profile.png" alt="Shivani" onerror="this.src='data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 width=%22160%22 height=%22160%22><rect width=%22160%22 height=%22160%22 fill=%22%23071828%22 rx=%2280%22/><text x=%2280%22 y=%22100%22 font-size=%2264%22 text-anchor=%22middle%22>🛡️</text></svg>'">
      <div class="avatar-ring"></div>
    </div>
  </section>

  <!-- ═══ TERMINAL ═══ -->
  <div class="terminal" style="margin-bottom:32px">
    <div class="terminal-bar">
      <div class="dot-row"><div class="dot r"></div><div class="dot y"></div><div class="dot g"></div></div>
      <span>shivani@cyberlab:~$</span>
    </div>
    <div class="terminal-body">
      <div><span class="prompt">➜</span> <span class="cmd">whoami</span></div>
      <div class="output">  <span class="highlight">Shivani Kumari Singh</span> · Cybersecurity Engineer · Frontend Developer</div>
      <div><span class="prompt">➜</span> <span class="cmd">cat focus.txt</span></div>
      <div class="output">  <span class="val">Zero-Trust</span> · <span class="val">Post-Quantum Cryptography</span> · <span class="val">OT/ICS Security</span> · <span class="val">Penetration Testing</span></div>
      <div><span class="prompt">➜</span> <span class="cmd">status --current</span></div>
      <div class="output">  <span class="highlight">[ ACTIVE ]</span> Building the future of secure digital infrastructure 🚀</div>
    </div>
  </div>

  <!-- ═══ GAME ═══ -->
  <div class="divider" data-label="// LIVE GAME"></div>
  <div class="section-title">🎮 Cyber Defender — Live Game</div>

  <div class="game-section">
    <div class="game-header">
      <div class="dot-row"><div class="dot r"></div><div class="dot y"></div><div class="dot g"></div></div>
      <span>CYBER_DEFENDER_v1.0</span>
      <span id="gameScore">SCORE: 0 | LIVES: ♥♥♥</span>
    </div>
    <canvas id="gameCanvas" width="920" height="280"></canvas>
    <div class="game-controls">
      <div class="info">← → MOVE &nbsp;|&nbsp; SPACE / CLICK SHOOT &nbsp;|&nbsp; Defend against incoming threats! <span id="waveInfo">WAVE 1</span></div>
      <button class="btn" onclick="startGame()">▶ START</button>
      <button class="btn red" onclick="resetGame()">↺ RESET</button>
    </div>
  </div>

  <!-- ═══ STATS ═══ -->
  <div class="divider" data-label="// METRICS"></div>
  <div class="section-title">📊 Stats Overview</div>
  <div class="stats-row" style="margin-bottom:32px">
    <div class="stat-card">
      <span class="stat-num" id="ctrCommits">0</span>
      <span class="stat-label">Commits</span>
    </div>
    <div class="stat-card">
      <span class="stat-num" id="ctrCTF">0</span>
      <span class="stat-label">CTF Solved</span>
    </div>
    <div class="stat-card">
      <span class="stat-num" id="ctrProj">0</span>
      <span class="stat-label">Projects</span>
    </div>
    <div class="stat-card">
      <span class="stat-num" id="ctrTools">0</span>
      <span class="stat-label">Security Tools</span>
    </div>
  </div>

  <!-- ═══ PROJECTS ═══ -->
  <div class="divider" data-label="// PROJECTS"></div>
  <div class="section-title">🛡️ Featured Projects</div>
  <div class="projects-grid" style="margin-bottom:32px">

    <div class="project-card blue">
      <span class="project-icon">🏗️</span>
      <div class="project-title">Qavach</div>
      <div class="project-subtitle">// E-GOVERNANCE · PQC</div>
      <p class="project-desc">Digital Service Delivery Framework utilizing NIST-aligned Post-Quantum Cryptography. Zero-Trust Architecture ensures data integrity and privacy at every layer.</p>
      <div class="tag-row">
        <span class="tag">Cryptography</span>
        <span class="tag">Zero-Trust</span>
        <span class="tag">NIST</span>
        <span class="tag">E-Governance</span>
      </div>
    </div>

    <div class="project-card green">
      <span class="project-icon">⚡</span>
      <div class="project-title">SwiftAutomate</div>
      <div class="project-subtitle">// OT/ICS SECURITY · SOC</div>
      <p class="project-desc">Low-cost ICS simulation lab integrating Arduino sensors with Prometheus, Grafana & Loki. Custom Web SOC Dashboard for real-time security alert monitoring.</p>
      <div class="tag-row">
        <span class="tag">OT Security</span>
        <span class="tag">ICS</span>
        <span class="tag">Grafana</span>
        <span class="tag">Arduino</span>
      </div>
    </div>

    <div class="project-card orange">
      <span class="project-icon">🏥</span>
      <div class="project-title">C.A.R.E.</div>
      <div class="project-subtitle">// HEALTHTECH · PRIVACY</div>
      <p class="project-desc">Secure health records sharing via encrypted FHIR bundles and a zero-data-storage broker. AI-powered insights directly within the EMR platform.</p>
      <div class="tag-row">
        <span class="tag">HealthTech</span>
        <span class="tag">FHIR</span>
        <span class="tag">AI/ML</span>
        <span class="tag">Encryption</span>
      </div>
    </div>

  </div>

  <!-- ═══ TECH STACK ═══ -->
  <div class="divider" data-label="// TECH STACK"></div>
  <div class="section-title">💻 Tech Arsenal</div>
  <div class="tech-grid" style="margin-bottom:32px">
    <div class="tech-badge"><span class="icon">🐍</span> Python</div>
    <div class="tech-badge"><span class="icon">⚛️</span> React</div>
    <div class="tech-badge"><span class="icon">🌊</span> Flutter</div>
    <div class="tech-badge"><span class="icon">☕</span> Java</div>
    <div class="tech-badge"><span class="icon">⚙️</span> C / C++</div>
    <div class="tech-badge"><span class="icon">🟩</span> Node.js</div>
    <div class="tech-badge"><span class="icon">🎨</span> HTML5/CSS3</div>
    <div class="tech-badge"><span class="icon">🗄️</span> MySQL</div>
    <div class="tech-badge"><span class="icon">🔥</span> Firebase</div>
    <div class="tech-badge"><span class="icon">☁️</span> AWS</div>
    <div class="tech-badge"><span class="icon">☁️</span> Google Cloud</div>
    <div class="tech-badge"><span class="icon">🐙</span> Git / GitHub</div>
    <div class="tech-badge"><span class="icon">🎨</span> Figma</div>
    <div class="tech-badge"><span class="icon">🔢</span> NumPy</div>
    <div class="tech-badge"><span class="icon">📦</span> Expo</div>
    <div class="tech-badge"><span class="icon">📹</span> FFmpeg</div>
  </div>

  <!-- ═══ SECURITY SKILLS ═══ -->
  <div class="divider" data-label="// SECURITY SKILLS"></div>
  <div class="section-title">🔐 Security Expertise</div>
  <div class="skills-list" style="margin-bottom:32px">
    <div class="skill-item">
      <label>Network Security <span>92%</span></label>
      <div class="skill-bar"><div class="skill-bar-fill" style="width:92%;background:linear-gradient(90deg,var(--accent2),var(--accent))"></div></div>
    </div>
    <div class="skill-item">
      <label>Post-Quantum Cryptography <span>88%</span></label>
      <div class="skill-bar"><div class="skill-bar-fill" style="width:88%;background:linear-gradient(90deg,#7b2fff,#c084fc)"></div></div>
    </div>
    <div class="skill-item">
      <label>Zero-Trust Architecture <span>85%</span></label>
      <div class="skill-bar"><div class="skill-bar-fill" style="width:85%;background:linear-gradient(90deg,var(--accent3),var(--accent))"></div></div>
    </div>
    <div class="skill-item">
      <label>OT / ICS Security <span>80%</span></label>
      <div class="skill-bar"><div class="skill-bar-fill" style="width:80%;background:linear-gradient(90deg,var(--warn),#ffcc00)"></div></div>
    </div>
    <div class="skill-item">
      <label>Penetration Testing <span>78%</span></label>
      <div class="skill-bar"><div class="skill-bar-fill" style="width:78%;background:linear-gradient(90deg,var(--accent),var(--accent2))"></div></div>
    </div>
  </div>

  <!-- ═══ SOCIALS ═══ -->
  <div class="divider" data-label="// CONNECT"></div>
  <div class="section-title">🌐 Find Me Online</div>
  <div class="social-row" style="margin-bottom:40px">
    <a href="https://www.linkedin.com/in/shivani-kumari-singh-102098314" class="social-btn" target="_blank">
      <span class="sicon">💼</span> LinkedIn
    </a>
    <a href="mailto:shivanikumarisingh83@gmail.com" class="social-btn">
      <span class="sicon">📧</span> Email
    </a>
    <a href="https://github.com/shivanisingh-sks" class="social-btn" target="_blank">
      <span class="sicon">🐙</span> GitHub
    </a>
  </div>

  <!-- ═══ FOOTER ═══ -->
  <div class="divider" data-label=""></div>
  <div class="footer">
    <div>Crafted with 💙 by <strong>Shivani Kumari Singh</strong></div>
    <div style="margin-top:8px;font-size:11px">// SECURING THE DIGITAL WORLD · ONE LINE AT A TIME</div>
  </div>

</div>

<script>
// ═══════════════════════════════
//  COUNTER ANIMATION
// ═══════════════════════════════
function animateCounter(el, target, duration=1600) {
  let start = 0;
  const step = target / (duration / 16);
  const timer = setInterval(() => {
    start = Math.min(start + step, target);
    el.textContent = Math.floor(start) + (target >= 10 ? '+' : '');
    if (start >= target) clearInterval(timer);
  }, 16);
}

const observer = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      animateCounter(document.getElementById('ctrCommits'), 120);
      animateCounter(document.getElementById('ctrCTF'), 47);
      animateCounter(document.getElementById('ctrProj'), 12);
      animateCounter(document.getElementById('ctrTools'), 20);
      observer.disconnect();
    }
  });
});
observer.observe(document.getElementById('ctrCommits'));


// ═══════════════════════════════
//  CYBER DEFENDER GAME
// ═══════════════════════════════
const canvas = document.getElementById('gameCanvas');
const ctx = canvas.getContext('2d');

// Responsive canvas
function resizeCanvas() {
  const w = canvas.parentElement.clientWidth;
  canvas.width = Math.min(w, 920);
  canvas.height = 280;
}
resizeCanvas();
window.addEventListener('resize', () => { resizeCanvas(); });

let game = null;
let animFrame = null;

class CyberGame {
  constructor() {
    this.W = canvas.width;
    this.H = canvas.height;
    this.score = 0;
    this.lives = 3;
    this.wave = 1;
    this.running = false;
    this.gameOver = false;
    this.won = false;

    // Player
    this.player = {
      x: this.W / 2,
      y: this.H - 40,
      w: 44, h: 20,
      speed: 5,
      color: '#00d4ff'
    };

    // Keys
    this.keys = {};
    this.bullets = [];
    this.enemies = [];
    this.particles = [];
    this.stars = Array.from({length: 60}, () => ({
      x: Math.random() * this.W,
      y: Math.random() * this.H,
      r: Math.random() * 1.5 + 0.3,
      speed: Math.random() * 0.4 + 0.1,
      alpha: Math.random() * 0.7 + 0.3
    }));
    this.shootCooldown = 0;
    this.spawnTimer = 0;

    this.labels = ['XSS','SQL','DDoS','RCE','MITM','0day','RAT','Bot'];

    this.spawnWave();
    this.running = true;
  }

  spawnWave() {
    this.enemies = [];
    const rows = Math.min(2 + this.wave, 4);
    const cols = Math.min(4 + this.wave, 9);
    for (let r = 0; r < rows; r++) {
      for (let c = 0; c < cols; c++) {
        this.enemies.push({
          x: 60 + c * Math.floor((this.W - 120) / (cols - 1 || 1)),
          y: 30 + r * 42,
          w: 36, h: 22,
          hp: 1,
          alive: true,
          dx: (0.8 + this.wave * 0.15),
          label: this.labels[Math.floor(Math.random() * this.labels.length)]
        });
      }
    }
    this.enemyDir = 1;
    this.enemyDropTimer = 0;
  }

  spawnParticles(x, y, color) {
    for (let i = 0; i < 10; i++) {
      this.particles.push({
        x, y,
        vx: (Math.random() - 0.5) * 5,
        vy: (Math.random() - 0.5) * 5,
        alpha: 1,
        color,
        r: Math.random() * 3 + 1
      });
    }
  }

  shoot() {
    if (this.shootCooldown > 0) return;
    this.bullets.push({ x: this.player.x, y: this.player.y - 14, speed: 9, color: '#00ff9f' });
    this.shootCooldown = 12;
  }

  update() {
    if (!this.running || this.gameOver) return;
    this.W = canvas.width;
    this.H = canvas.height;

    // Move player
    if (this.keys['ArrowLeft'] || this.keys['a']) this.player.x = Math.max(this.player.w/2 + 4, this.player.x - this.player.speed);
    if (this.keys['ArrowRight'] || this.keys['d']) this.player.x = Math.min(this.W - this.player.w/2 - 4, this.player.x + this.player.speed);
    if ((this.keys[' '] || this.keys['Space'])) this.shoot();

    if (this.shootCooldown > 0) this.shootCooldown--;

    // Move bullets
    this.bullets = this.bullets.filter(b => b.y > -10);
    this.bullets.forEach(b => b.y -= b.speed);

    // Move enemies
    let edgeHit = false;
    this.enemies.filter(e => e.alive).forEach(e => {
      e.x += e.dx * this.enemyDir;
      if (e.x > this.W - 30 || e.x < 30) edgeHit = true;
    });
    if (edgeHit) {
      this.enemyDir *= -1;
      this.enemies.filter(e => e.alive).forEach(e => e.y += 14);
    }

    // Bullet-enemy collisions
    this.bullets.forEach(b => {
      this.enemies.forEach(e => {
        if (!e.alive) return;
        if (Math.abs(b.x - e.x) < e.w/2 + 3 && Math.abs(b.y - e.y) < e.h/2 + 3) {
          e.alive = false;
          b.y = -999;
          this.score += 10 * this.wave;
          this.spawnParticles(e.x, e.y, '#00ff9f');
        }
      });
    });

    // Enemy reaches bottom
    this.enemies.filter(e => e.alive).forEach(e => {
      if (e.y > this.H - 50) {
        this.lives--;
        e.alive = false;
        this.spawnParticles(e.x, e.y, '#ff6b35');
        if (this.lives <= 0) { this.gameOver = true; this.running = false; }
      }
    });

    // Enemy shoots at player (random)
    if (Math.random() < 0.006 * this.wave) {
      const alive = this.enemies.filter(e => e.alive);
      if (alive.length) {
        const shooter = alive[Math.floor(Math.random() * alive.length)];
        this.bullets.push({ x: shooter.x, y: shooter.y + 10, speed: -3.5, color: '#ff6b35', enemy: true });
      }
    }

    // Enemy bullets hit player
    this.bullets.forEach(b => {
      if (!b.enemy) return;
      if (Math.abs(b.x - this.player.x) < this.player.w/2 + 4 && Math.abs(b.y - this.player.y) < this.player.h/2 + 6) {
        this.lives--;
        b.y = 9999;
        this.spawnParticles(this.player.x, this.player.y, '#ff6b35');
        if (this.lives <= 0) { this.gameOver = true; this.running = false; }
      }
    });

    // Particles
    this.particles.forEach(p => {
      p.x += p.vx; p.y += p.vy;
      p.vx *= 0.9; p.vy *= 0.9;
      p.alpha -= 0.04;
    });
    this.particles = this.particles.filter(p => p.alpha > 0);

    // Next wave
    if (this.enemies.every(e => !e.alive)) {
      this.wave++;
      if (this.wave > 5) { this.won = true; this.gameOver = true; this.running = false; return; }
      this.spawnWave();
    }

    // Update HUD
    const hearts = '♥'.repeat(Math.max(0,this.lives)) + '♡'.repeat(Math.max(0, 3-this.lives));
    document.getElementById('gameScore').textContent = `SCORE: ${this.score} | LIVES: ${hearts}`;
    document.getElementById('waveInfo').textContent = `WAVE ${this.wave}`;
  }

  draw() {
    ctx.clearRect(0, 0, this.W, this.H);

    // BG
    ctx.fillStyle = '#010a10';
    ctx.fillRect(0, 0, this.W, this.H);

    // Stars
    this.stars.forEach(s => {
      s.y += s.speed;
      if (s.y > this.H) { s.y = 0; s.x = Math.random() * this.W; }
      ctx.globalAlpha = s.alpha;
      ctx.fillStyle = '#7ab8d4';
      ctx.beginPath();
      ctx.arc(s.x, s.y, s.r, 0, Math.PI*2);
      ctx.fill();
    });
    ctx.globalAlpha = 1;

    // Ground line
    ctx.strokeStyle = 'rgba(0,212,255,0.15)';
    ctx.lineWidth = 1;
    ctx.beginPath();
    ctx.moveTo(0, this.H - 28);
    ctx.lineTo(this.W, this.H - 28);
    ctx.stroke();

    // Player (shield shape)
    const px = this.player.x, py = this.player.y;
    ctx.save();
    ctx.shadowBlur = 16;
    ctx.shadowColor = '#00d4ff';
    ctx.fillStyle = '#00d4ff';
    ctx.beginPath();
    ctx.moveTo(px, py - this.player.h/2);
    ctx.lineTo(px + this.player.w/2, py + this.player.h/2);
    ctx.lineTo(px - this.player.w/2, py + this.player.h/2);
    ctx.closePath();
    ctx.fill();
    // Cockpit
    ctx.fillStyle = '#fff';
    ctx.beginPath();
    ctx.arc(px, py - 2, 4, 0, Math.PI*2);
    ctx.fill();
    ctx.restore();

    // Enemies
    this.enemies.filter(e => e.alive).forEach(e => {
      ctx.save();
      ctx.shadowBlur = 10;
      ctx.shadowColor = '#ff6b35';
      ctx.strokeStyle = '#ff6b35';
      ctx.lineWidth = 1.5;
      // Skull-like box
      ctx.strokeRect(e.x - e.w/2, e.y - e.h/2, e.w, e.h);
      ctx.fillStyle = 'rgba(255,107,53,0.12)';
      ctx.fillRect(e.x - e.w/2, e.y - e.h/2, e.w, e.h);
      // Label
      ctx.fillStyle = '#ff9070';
      ctx.font = 'bold 8px "Share Tech Mono"';
      ctx.textAlign = 'center';
      ctx.textBaseline = 'middle';
      ctx.fillText(e.label, e.x, e.y);
      ctx.restore();
    });

    // Bullets
    this.bullets.forEach(b => {
      if (b.y < -10 || b.y > this.H + 10) return;
      ctx.save();
      ctx.shadowBlur = 12;
      ctx.shadowColor = b.color;
      ctx.fillStyle = b.color;
      ctx.fillRect(b.x - 2, b.y - 7, 4, 14);
      ctx.restore();
    });

    // Particles
    this.particles.forEach(p => {
      ctx.save();
      ctx.globalAlpha = p.alpha;
      ctx.shadowBlur = 8;
      ctx.shadowColor = p.color;
      ctx.fillStyle = p.color;
      ctx.beginPath();
      ctx.arc(p.x, p.y, p.r, 0, Math.PI*2);
      ctx.fill();
      ctx.restore();
    });

    // Game Over / Win overlay
    if (this.gameOver) {
      ctx.fillStyle = 'rgba(1,8,16,0.85)';
      ctx.fillRect(0, 0, this.W, this.H);
      ctx.save();
      ctx.textAlign = 'center';
      ctx.textBaseline = 'middle';
      if (this.won) {
        ctx.fillStyle = '#00ff9f';
        ctx.shadowColor = '#00ff9f';
        ctx.shadowBlur = 30;
        ctx.font = 'bold 32px Orbitron';
        ctx.fillText('SYSTEM SECURED! 🛡️', this.W/2, this.H/2 - 20);
        ctx.font = '14px Share Tech Mono';
        ctx.fillStyle = '#4a7a96';
        ctx.fillText('SCORE: ' + this.score + ' — All threats neutralized!', this.W/2, this.H/2 + 20);
      } else {
        ctx.fillStyle = '#ff6b35';
        ctx.shadowColor = '#ff6b35';
        ctx.shadowBlur = 30;
        ctx.font = 'bold 28px Orbitron';
        ctx.fillText('BREACH DETECTED', this.W/2, this.H/2 - 20);
        ctx.font = '13px Share Tech Mono';
        ctx.fillStyle = '#4a7a96';
        ctx.fillText('SCORE: ' + this.score + ' — Press RESET to reinitialize', this.W/2, this.H/2 + 20);
      }
      ctx.restore();
    }

    // Idle screen
    if (!this.running && !this.gameOver) {
      ctx.fillStyle = 'rgba(1,8,16,0.9)';
      ctx.fillRect(0, 0, this.W, this.H);
      ctx.textAlign = 'center';
      ctx.textBaseline = 'middle';
      ctx.fillStyle = '#00d4ff';
      ctx.font = '18px Orbitron';
      ctx.shadowColor = '#00d4ff'; ctx.shadowBlur = 20;
      ctx.fillText('CYBER DEFENDER', this.W/2, this.H/2 - 20);
      ctx.font = '12px Share Tech Mono';
      ctx.fillStyle = '#4a7a96'; ctx.shadowBlur = 0;
      ctx.fillText('Press START — Use ← → to move, SPACE or CLICK to shoot', this.W/2, this.H/2 + 16);
    }
  }

  loop() {
    this.update();
    this.draw();
    animFrame = requestAnimationFrame(() => this.loop());
  }
}

function startGame() {
  if (!game) { game = new CyberGame(); game.running = false; }
  game.running = true;
  if (!animFrame) game.loop();
}

function resetGame() {
  if (animFrame) { cancelAnimationFrame(animFrame); animFrame = null; }
  game = new CyberGame();
  game.running = false;
  document.getElementById('gameScore').textContent = 'SCORE: 0 | LIVES: ♥♥♥';
  document.getElementById('waveInfo').textContent = 'WAVE 1';
  game.draw();
}

// Input
document.addEventListener('keydown', e => {
  if (!game) return;
  game.keys[e.key] = true;
  if (e.key === ' ') { e.preventDefault(); game.shoot(); }
});
document.addEventListener('keyup', e => { if (game) game.keys[e.key] = false; });
canvas.addEventListener('click', e => {
  if (game && game.running) {
    const rect = canvas.getBoundingClientRect();
    game.player.x = (e.clientX - rect.left) * (canvas.width / rect.width);
    game.shoot();
  }
});
canvas.addEventListener('mousemove', e => {
  if (game && game.running) {
    const rect = canvas.getBoundingClientRect();
    game.player.x = (e.clientX - rect.left) * (canvas.width / rect.width);
  }
});

// Initial idle draw
window.addEventListener('load', () => {
  game = new CyberGame();
  game.running = false;
  game.draw();
});
</script>
</body>
</html>
