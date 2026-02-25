<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Tesnim — GitHub Profile README</title>
  <link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;700;800&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #0a0a0f;
      --card: #111118;
      --border: #1e1e2e;
      --accent: #00ffc8;
      --accent2: #7b61ff;
      --text: #e8e8f0;
      --muted: #6b6b80;
      --mono: 'Space Mono', monospace;
      --sans: 'Syne', sans-serif;
    }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--sans);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      padding: 40px 20px;
      overflow-x: hidden;
    }

    /* animated grid background */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(var(--border) 1px, transparent 1px),
        linear-gradient(90deg, var(--border) 1px, transparent 1px);
      background-size: 40px 40px;
      opacity: 0.35;
      z-index: 0;
      pointer-events: none;
    }

    .wrapper {
      position: relative;
      z-index: 1;
      width: 100%;
      max-width: 780px;
      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    /* ---- HERO ---- */
    .hero {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 48px 40px 40px;
      position: relative;
      overflow: hidden;
      animation: fadeUp .7s ease both;
    }

    .hero::before {
      content: '';
      position: absolute;
      top: -80px; right: -80px;
      width: 300px; height: 300px;
      background: radial-gradient(circle, rgba(0,255,200,.12), transparent 70%);
      pointer-events: none;
    }
    .hero::after {
      content: '';
      position: absolute;
      bottom: -60px; left: -60px;
      width: 240px; height: 240px;
      background: radial-gradient(circle, rgba(123,97,255,.1), transparent 70%);
      pointer-events: none;
    }

    .badge {
      font-family: var(--mono);
      font-size: 11px;
      color: var(--accent);
      border: 1px solid var(--accent);
      border-radius: 4px;
      padding: 3px 10px;
      display: inline-block;
      letter-spacing: .1em;
      margin-bottom: 20px;
    }

    .hero h1 {
      font-family: var(--sans);
      font-size: clamp(2.4rem, 6vw, 3.6rem);
      font-weight: 800;
      line-height: 1.1;
      letter-spacing: -.02em;
    }

    .hero h1 .name {
      color: var(--accent);
      display: block;
    }

    .hero h1 .role {
      color: var(--text);
      display: block;
    }

    .hero p {
      margin-top: 18px;
      font-family: var(--mono);
      font-size: 13px;
      color: var(--muted);
      line-height: 1.7;
      max-width: 520px;
    }

    .hero p span {
      color: var(--accent2);
    }

    /* ---- SECTION LABEL ---- */
    .section-label {
      font-family: var(--mono);
      font-size: 11px;
      letter-spacing: .15em;
      color: var(--muted);
      text-transform: uppercase;
      margin-bottom: 12px;
    }

    /* ---- GRID ROW ---- */
    .grid-2 {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 20px;
    }

    @media (max-width: 560px) {
      .grid-2 { grid-template-columns: 1fr; }
      .hero { padding: 32px 24px; }
    }

    /* ---- CARD ---- */
    .card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 14px;
      padding: 28px 28px 24px;
      animation: fadeUp .7s ease both;
    }

    .card:nth-child(2) { animation-delay: .1s; }
    .card:nth-child(3) { animation-delay: .2s; }

    /* ---- LANGUAGE PILLS ---- */
    .pills {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 4px;
    }

    .pill {
      display: flex;
      align-items: center;
      gap: 8px;
      font-family: var(--mono);
      font-size: 12px;
      color: var(--text);
      background: #1a1a28;
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 8px 14px;
      transition: border-color .2s, color .2s;
    }

    .pill:hover {
      border-color: var(--accent);
      color: var(--accent);
    }

    .pill .dot {
      width: 8px; height: 8px;
      border-radius: 50%;
      flex-shrink: 0;
    }

    /* language colors */
    .dot-html   { background: #e34c26; }
    .dot-css    { background: #264de4; }
    .dot-c      { background: #555599; }
    .dot-js     { background: #f7df1e; }

    /* ---- TECH STACK ---- */
    .tech-list {
      display: flex;
      flex-direction: column;
      gap: 10px;
      margin-top: 4px;
    }

    .tech-item {
      display: flex;
      align-items: center;
      gap: 12px;
      font-family: var(--mono);
      font-size: 12px;
      color: var(--text);
      background: #1a1a28;
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 10px 14px;
      transition: border-color .2s, color .2s;
    }

    .tech-item:hover {
      border-color: var(--accent2);
      color: var(--accent2);
    }

    .tech-icon {
      font-size: 18px;
    }

    /* ---- STAT BAR ---- */
    .stat-bar-wrap {
      margin-top: 4px;
      display: flex;
      flex-direction: column;
      gap: 14px;
    }

    .stat-row {
      display: flex;
      flex-direction: column;
      gap: 6px;
    }

    .stat-label {
      display: flex;
      justify-content: space-between;
      font-family: var(--mono);
      font-size: 11px;
      color: var(--muted);
    }

    .stat-label span:last-child { color: var(--accent); }

    .bar-bg {
      height: 4px;
      background: #1a1a28;
      border-radius: 99px;
      overflow: hidden;
    }

    .bar-fill {
      height: 100%;
      border-radius: 99px;
      background: linear-gradient(90deg, var(--accent2), var(--accent));
      animation: barGrow 1.2s ease both;
      transform-origin: left;
    }

    @keyframes barGrow {
      from { width: 0 !important; }
    }

    /* ---- FOOTER LINE ---- */
    .footer-line {
      font-family: var(--mono);
      font-size: 11px;
      color: var(--muted);
      text-align: center;
      padding: 8px 0;
      letter-spacing: .05em;
      animation: fadeUp .7s .4s ease both;
    }

    .footer-line span { color: var(--accent); }

    /* ---- ANIMATIONS ---- */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px); }
      to   { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>
  <div class="wrapper">

    <!-- HERO -->
    <div class="hero">
      <div class="badge">// PROFILE.README</div>
      <h1>
        <span class="name">Tesnim</span>
        <span class="role">Software Engineer &amp; Programmer</span>
      </h1>
      <p>
        Building things with code — from low-level <span>C</span> to interactive
        <span>web experiences</span>. Comfortable in the terminal, obsessed
        with clean systems, and always shipping.
      </p>
    </div>

    <!-- LANGUAGES + TECH -->
    <div class="grid-2">

      <!-- Languages -->
      <div class="card">
        <div class="section-label">// Languages</div>
        <div class="pills">
          <div class="pill"><span class="dot dot-html"></span> HTML</div>
          <div class="pill"><span class="dot dot-css"></span> CSS</div>
          <div class="pill"><span class="dot dot-c"></span> C</div>
          <div class="pill"><span class="dot dot-js"></span> JavaScript</div>
        </div>
      </div>

      <!-- Tech & Tools -->
      <div class="card">
        <div class="section-label">// Technologies</div>
        <div class="tech-list">
          <div class="tech-item"><span class="tech-icon">🐳</span> Docker</div>
          <div class="tech-item"><span class="tech-icon">🐧</span> Linux</div>
        </div>
      </div>

    </div>

    <!-- SKILL LEVELS -->
    <div class="card" style="animation-delay:.3s">
      <div class="section-label">// Skill Overview</div>
      <div class="stat-bar-wrap">
        <div class="stat-row">
          <div class="stat-label"><span>HTML / CSS</span><span>90%</span></div>
          <div class="bar-bg"><div class="bar-fill" style="width:90%"></div></div>
        </div>
        <div class="stat-row">
          <div class="stat-label"><span>JavaScript</span><span>78%</span></div>
          <div class="bar-bg"><div class="bar-fill" style="width:78%"></div></div>
        </div>
        <div class="stat-row">
          <div class="stat-label"><span>C</span><span>72%</span></div>
          <div class="bar-bg"><div class="bar-fill" style="width:72%"></div></div>
        </div>
        <div class="stat-row">
          <div class="stat-label"><span>Docker &amp; Linux</span><span>80%</span></div>
          <div class="bar-bg"><div class="bar-fill" style="width:80%"></div></div>
        </div>
      </div>
    </div>

    <!-- FOOTER -->
    <div class="footer-line">
      crafted by <span>Tesnim</span> · software engineer · always building
    </div>

  </div>
</body>
</html>
