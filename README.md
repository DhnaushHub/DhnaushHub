<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Dhanush Ram M — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;600&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0d1117;
    --bg2: #161b22;
    --bg3: #1c2128;
    --border: #30363d;
    --purple: #7e3ace;
    --purple2: #a56ef5;
    --blue: #58a6ff;
    --green: #3fb950;
    --text: #e6edf3;
    --text2: #8b949e;
    --red: #f85149;
    --gold: #e3b341;
  }
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Inter', sans-serif;
    overflow-x: hidden;
  }

  /* ── STAR CANVAS ── */
  #stars-canvas {
    position: fixed; top: 0; left: 0;
    width: 100%; height: 100%;
    z-index: 0; pointer-events: none;
  }

  /* ── LAYOUT ── */
  .wrapper {
    position: relative; z-index: 1;
    max-width: 900px; margin: 0 auto;
    padding: 0 1.5rem 4rem;
  }

  /* ── HEADER WAVE ── */
  .header-wave {
    width: 100vw; margin-left: calc(-50vw + 50%);
    background: linear-gradient(135deg, #0f0c29 0%, #302b63 50%, #24243e 100%);
    padding: 3.5rem 2rem 5rem;
    position: relative; overflow: hidden;
    text-align: center; margin-bottom: -2rem;
  }
  .header-wave::after {
    content: '';
    position: absolute; bottom: -1px; left: 0; right: 0;
    height: 60px;
    background: var(--bg);
    clip-path: ellipse(55% 100% at 50% 100%);
  }
  .header-wave h1 {
    font-size: clamp(2rem, 5vw, 3.2rem);
    font-weight: 700; color: #fff;
    letter-spacing: -0.5px;
    text-shadow: 0 0 30px rgba(126,58,206,0.6);
  }
  .header-subtitle {
    color: #c9b8ff; font-size: 1rem;
    margin-top: 0.4rem; font-weight: 300;
    letter-spacing: 1px;
  }
  .typing-wrap { margin: 1.2rem auto 0; max-width: 480px; height: 32px; }
  #typing-text {
    font-family: 'Fira Code', monospace;
    font-size: 1rem; color: var(--purple2);
    border-right: 2px solid var(--purple2);
    white-space: nowrap; overflow: hidden;
    display: inline-block;
    animation: blink-cursor 0.75s step-end infinite;
  }
  @keyframes blink-cursor { 50% { border-color: transparent; } }

  /* ── GITHUB BUTTON with CAT ── */
  .github-zone {
    display: inline-block; position: relative;
    margin-top: 2rem;
  }
  .github-btn {
    display: inline-flex; align-items: center; gap: 10px;
    background: #fff; color: #0d1117;
    text-decoration: none; font-weight: 600;
    font-size: 0.95rem; padding: 0.65rem 1.6rem;
    border-radius: 8px;
    transition: transform 0.2s, box-shadow 0.2s;
    position: relative; z-index: 2;
  }
  .github-btn:hover { transform: translateY(-2px); box-shadow: 0 8px 24px rgba(0,0,0,0.5); }
  .github-btn svg { width: 22px; height: 22px; }
  .octocat-attacker {
    position: absolute;
    bottom: 100%; left: 50%; transform: translateX(-50%) translateY(40px);
    font-size: 2.4rem; opacity: 0;
    transition: all 0.3s cubic-bezier(0.34,1.56,0.64,1);
    pointer-events: none; z-index: 10;
    filter: drop-shadow(0 2px 8px rgba(0,0,0,0.8));
  }
  .octocat-msg {
    position: absolute;
    bottom: calc(100% + 52px); left: 50%; transform: translateX(-50%);
    background: #ff4444; color: #fff;
    font-size: 0.75rem; font-weight: 600;
    padding: 4px 12px; border-radius: 20px;
    white-space: nowrap; opacity: 0;
    transition: opacity 0.2s 0.15s;
    pointer-events: none; z-index: 10;
  }
  .github-zone:hover .octocat-attacker {
    opacity: 1; transform: translateX(-50%) translateY(-4px) rotate(-15deg);
  }
  .github-zone:hover .octocat-msg { opacity: 1; }

  /* ── SOCIAL PILLS ── */
  .socials { display: flex; gap: 0.7rem; flex-wrap: wrap; justify-content: center; margin-top: 1.2rem; }
  .social-pill {
    display: inline-flex; align-items: center; gap: 6px;
    padding: 6px 14px; border-radius: 20px;
    font-size: 0.8rem; font-weight: 500;
    text-decoration: none; border: 1px solid;
    transition: transform 0.2s, opacity 0.2s;
  }
  .social-pill:hover { transform: translateY(-2px); opacity: 0.85; }
  .pill-gmail { background: rgba(209,72,54,0.15); border-color: rgba(209,72,54,0.4); color: #f28b82; }
  .pill-li { background: rgba(10,102,194,0.15); border-color: rgba(10,102,194,0.4); color: #58a6ff; }
  .pill-portfolio { background: rgba(126,58,206,0.15); border-color: rgba(126,58,206,0.4); color: var(--purple2); }
  .pv-badge {
    margin-top: 0.8rem; display: inline-block;
    background: rgba(126,58,206,0.15); border: 1px solid rgba(126,58,206,0.3);
    color: var(--purple2); font-size: 0.75rem; padding: 4px 12px; border-radius: 12px;
  }

  /* ── SECTIONS ── */
  section { margin: 3rem 0; }
  .section-title {
    font-size: 1.15rem; font-weight: 600; color: var(--text);
    display: flex; align-items: center; gap: 8px;
    padding-bottom: 0.6rem;
    border-bottom: 1px solid var(--border);
    margin-bottom: 1.5rem;
  }
  .section-title span { color: var(--purple); font-size: 1.3rem; }

  /* ── ABOUT (CODE BLOCK) ── */
  .code-block {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 12px; overflow: hidden;
  }
  .code-topbar {
    background: var(--bg3);
    padding: 0.6rem 1rem;
    display: flex; align-items: center; gap: 6px;
    border-bottom: 1px solid var(--border);
  }
  .dot { width: 12px; height: 12px; border-radius: 50%; }
  .dot-red { background: #ff5f57; }
  .dot-yellow { background: #febc2e; }
  .dot-green { background: #28c840; }
  .code-filename { font-size: 0.75rem; color: var(--text2); margin-left: 6px; font-family: 'Fira Code', monospace; }
  .code-content { padding: 1.5rem; font-family: 'Fira Code', monospace; font-size: 0.85rem; line-height: 1.8; overflow-x: auto; }
  .kw { color: #ff7b72; }
  .fn { color: #d2a8ff; }
  .str { color: #a5d6ff; }
  .cm { color: #5c6d7e; font-style: italic; }
  .num { color: #79c0ff; }
  .cls { color: #ffa657; }
  .var { color: var(--text); }

  /* ── TECH BADGES ── */
  .badge-group { margin-bottom: 1.5rem; }
  .badge-group-title {
    font-size: 0.75rem; color: var(--text2);
    text-transform: uppercase; letter-spacing: 1px;
    margin-bottom: 0.6rem; font-weight: 600;
  }
  .badges-row { display: flex; flex-wrap: wrap; gap: 8px; }
  .tech-badge {
    display: inline-flex; align-items: center; gap: 6px;
    padding: 6px 12px; border-radius: 6px;
    font-size: 0.78rem; font-weight: 600;
    cursor: default; position: relative;
    transition: transform 0.2s, box-shadow 0.2s;
    border: 1px solid transparent;
  }
  .tech-badge:hover { transform: translateY(-3px) scale(1.05); box-shadow: 0 6px 20px rgba(0,0,0,0.4); }
  .tech-badge .badge-icon { font-size: 1rem; }

  /* tooltip */
  .tech-badge::after {
    content: attr(data-tip);
    position: absolute; bottom: calc(100% + 8px); left: 50%; transform: translateX(-50%);
    background: #1c2128; border: 1px solid var(--purple);
    color: var(--purple2); font-size: 0.72rem; font-weight: 500;
    padding: 6px 12px; border-radius: 8px;
    white-space: nowrap; opacity: 0;
    pointer-events: none;
    transition: opacity 0.2s 0.1s, transform 0.2s 0.1s;
    font-family: 'Fira Code', monospace;
    z-index: 50;
    transform: translateX(-50%) translateY(4px);
  }
  .tech-badge:hover::after {
    opacity: 1;
    transform: translateX(-50%) translateY(0);
  }

  /* badge colors */
  .b-py   { background:#3776ab20; border-color:#3776ab60; color:#4ec9b0; }
  .b-js   { background:#f7df1e18; border-color:#f7df1e50; color:#f7df1e; }
  .b-ts   { background:#3178c618; border-color:#3178c650; color:#5ba4f5; }
  .b-node { background:#33993320; border-color:#33993360; color:#3fb950; }
  .b-html { background:#e34f2618; border-color:#e34f2650; color:#f28b82; }
  .b-css  { background:#1572b618; border-color:#1572b650; color:#58a6ff; }
  .b-php  { background:#777bb420; border-color:#777bb450; color:#a78bfa; }
  .b-react{ background:#61dafb18; border-color:#61dafb50; color:#61dafb; }
  .b-rn   { background:#20232a;   border-color:#61dafb40; color:#61dafb; }
  .b-flask{ background:#ffffff10; border-color:#ffffff30; color:#e6edf3; }
  .b-dj   { background:#09231818; border-color:#09231860; color:#3fb950; }
  .b-sb   { background:#6db33f18; border-color:#6db33f50; color:#6db33f; }
  .b-tw   { background:#06b6d418; border-color:#06b6d450; color:#22d3ee; }
  .b-mysql{ background:#4479a118; border-color:#4479a150; color:#58a6ff; }
  .b-mongo{ background:#47a24818; border-color:#47a24850; color:#3fb950; }
  .b-redis{ background:#dc382d18; border-color:#dc382d50; color:#f85149; }
  .b-git  { background:#f0503218; border-color:#f0503250; color:#f28b82; }
  .b-linux{ background:#fcc62418; border-color:#fcc62450; color:#fcc624; }
  .b-vs   { background:#007acc18; border-color:#007acc50; color:#58a6ff; }
  .b-post { background:#ff6c3718; border-color:#ff6c3750; color:#ffa657; }
  .b-adobe{ background:#ff000018; border-color:#ff000050; color:#f85149; }

  /* ── PROJECTS ── */
  .projects-grid { display: grid; gap: 1.2rem; }
  .project-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 12px; padding: 1.4rem 1.5rem;
    position: relative; overflow: hidden;
    transition: border-color 0.3s, transform 0.3s;
    cursor: default;
  }
  .project-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, var(--purple), var(--blue));
    transform: scaleX(0); transform-origin: left;
    transition: transform 0.4s ease;
  }
  .project-card:hover { border-color: var(--purple); transform: translateY(-3px); }
  .project-card:hover::before { transform: scaleX(1); }
  .project-title { font-size: 1rem; font-weight: 600; color: var(--text); margin-bottom: 4px; }
  .project-sub { font-size: 0.78rem; color: var(--purple2); font-weight: 500; margin-bottom: 0.8rem; }
  .project-points { list-style: none; }
  .project-points li {
    font-size: 0.82rem; color: var(--text2); line-height: 1.6;
    padding: 3px 0; display: flex; gap: 8px;
  }
  .project-points li::before { content: attr(data-icon); flex-shrink: 0; }
  .stack-chips { display: flex; flex-wrap: wrap; gap: 6px; margin-top: 1rem; }
  .chip {
    font-size: 0.7rem; font-weight: 600;
    padding: 3px 10px; border-radius: 20px;
    background: rgba(126,58,206,0.15);
    border: 1px solid rgba(126,58,206,0.3);
    color: var(--purple2);
    font-family: 'Fira Code', monospace;
  }

  /* ── STATS CARDS ── */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 1rem;
  }
  .stat-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 12px; overflow: hidden;
  }
  .stat-card img { width: 100%; display: block; }

  /* ── EXPLORING TABLE ── */
  .explore-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 1rem;
  }
  .explore-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 10px; padding: 1rem;
    display: flex; gap: 10px; align-items: flex-start;
    transition: border-color 0.3s;
  }
  .explore-card:hover { border-color: var(--purple); }
  .explore-icon { font-size: 1.4rem; flex-shrink: 0; }
  .explore-title { font-size: 0.85rem; font-weight: 600; color: var(--text); }
  .explore-sub { font-size: 0.75rem; color: var(--text2); margin-top: 2px; line-height: 1.5; }

  /* ── FOOTER ── */
  .footer-wave {
    width: 100vw; margin-left: calc(-50vw + 50%);
    background: linear-gradient(135deg, #24243e 0%, #302b63 50%, #0f0c29 100%);
    padding: 2.5rem 2rem;
    text-align: center; margin-top: 4rem;
  }
  .footer-wave h3 { font-size: 1.1rem; color: #fff; font-weight: 600; margin-bottom: 1rem; }
  .connect-btn {
    display: inline-flex; align-items: center; gap: 8px;
    background: var(--purple); color: #fff;
    text-decoration: none; font-weight: 600;
    font-size: 0.9rem; padding: 0.7rem 1.8rem;
    border-radius: 8px;
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .connect-btn:hover { transform: translateY(-2px); box-shadow: 0 8px 24px rgba(126,58,206,0.4); }
</style>
</head>
<body>

<canvas id="stars-canvas"></canvas>

<!-- ── HEADER ── -->
<div class="header-wave">
  <h1>Dhanush Ram M</h1>
  <p class="header-subtitle">Software Engineer &nbsp;|&nbsp; Full Stack Developer &nbsp;|&nbsp; AI Enthusiast</p>
  <div class="typing-wrap"><span id="typing-text"></span></div>

  <!-- GitHub Button + Cat Attack -->
  <div style="margin-top:1.8rem">
    <div class="github-zone" style="display:inline-block;position:relative">
      <div class="octocat-msg">Don't Do This... 😾</div>
      <div class="octocat-attacker">🐱</div>
      <a href="https://github.com/DhnaushHub" class="github-btn" target="_blank" rel="noopener">
        <svg viewBox="0 0 24 24" fill="currentColor">
          <path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/>
        </svg>
        DhnaushHub on GitHub
      </a>
    </div>
  </div>

  <div class="socials">
    <a href="mailto:dhanushram406@gmail.com" class="social-pill pill-gmail">✉️ dhanushram406@gmail.com</a>
    <a href="https://linkedin.com/in/dhanushram" class="social-pill pill-li" target="_blank">💼 LinkedIn</a>
    <a href="#" class="social-pill pill-portfolio">🌐 Portfolio</a>
  </div>
  <div><span class="pv-badge">👁 Profile Views Tracker</span></div>
</div>

<div class="wrapper">

  <!-- ── ABOUT ── -->
  <section>
    <div class="section-title"><span>🧑‍💻</span> About Me</div>
    <div class="code-block">
      <div class="code-topbar">
        <div class="dot dot-red"></div>
        <div class="dot dot-yellow"></div>
        <div class="dot dot-green"></div>
        <span class="code-filename">dhanush.py</span>
      </div>
      <div class="code-content">
        <div><span class="kw">class</span> <span class="cls">DhanushRamM</span>:</div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="kw">def</span> <span class="fn">__init__</span>(<span class="var">self</span>):</div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="var">self</span>.name&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;= <span class="str">"Dhanush Ram M"</span></div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="var">self</span>.role&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;= <span class="str">"Full Stack Developer &amp; AI Enthusiast"</span></div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="var">self</span>.education = <span class="str">"B.E. CSE @ St. Joseph College (CGPA: 8.37 / 10)"</span></div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="var">self</span>.location&nbsp; = <span class="str">"Tamil Nadu, India 🇮🇳"</span></div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="var">self</span>.languages = [<span class="str">"English"</span>, <span class="str">"Tamil"</span>]</div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="var">self</span>.interests = [<span class="str">"GenAI"</span>, <span class="str">"Prompt Engineering"</span>, <span class="str">"Full Stack"</span>, <span class="str">"UI/UX"</span>, <span class="str">"Linux"</span>]</div>
        <br/>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="kw">def</span> <span class="fn">current_focus</span>(<span class="var">self</span>):</div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="kw">return</span> [</div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="str">"🔭 Building full-stack web &amp; mobile apps"</span>,</div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="str">"🧠 Exploring Generative AI &amp; LLM integration"</span>,</div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="str">"🎨 Crafting intuitive UI/UX experiences"</span>,</div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="str">"📚 3rd Year CSE Student — always learning"</span>,</div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;]</div>
        <br/>
        <div><span class="var">me</span> = <span class="cls">DhanushRamM</span>() <span class="cm"># Instantiate excellence ✨</span></div>
      </div>
    </div>
  </section>

  <!-- ── TECH STACK ── -->
  <section>
    <div class="section-title"><span>🛠️</span> Tech Stack</div>

    <div class="badge-group">
      <div class="badge-group-title">💬 Languages &amp; Web</div>
      <div class="badges-row">
        <span class="tech-badge b-py"  data-tip="&lt;Python /&gt; — Simple. Elegant. Powerful. 🐍">🐍 Python</span>
        <span class="tech-badge b-js"  data-tip="&lt;JavaScript /&gt; — The magic that makes the web dance 💃">⚡ JavaScript</span>
        <span class="tech-badge b-ts"  data-tip="&lt;TypeScript /&gt; — JavaScript with a safety net 🛡️">🔷 TypeScript</span>
        <span class="tech-badge b-node" data-tip="&lt;Node.js /&gt; — JavaScript escaped the browser 🚀">🟩 Node.js</span>
        <span class="tech-badge b-html" data-tip="&lt;HTML /&gt; — The skeleton of every dream on the web 🦴">🔥 HTML5</span>
        <span class="tech-badge b-css"  data-tip="&lt;CSS /&gt; — Where art meets the browser ✨">🎨 CSS3</span>
        <span class="tech-badge b-php"  data-tip="&lt;PHP /&gt; — Still powering 78% of the web 🌐">🐘 PHP</span>
      </div>
    </div>

    <div class="badge-group">
      <div class="badge-group-title">🧩 Frameworks &amp; Libraries</div>
      <div class="badges-row">
        <span class="tech-badge b-react" data-tip="&lt;React /&gt; — Build once, render everywhere ⚛️">⚛️ React.js</span>
        <span class="tech-badge b-rn"    data-tip="&lt;ReactNative /&gt; — One codebase, two platforms 📱">📱 React Native</span>
        <span class="tech-badge b-flask" data-tip="&lt;Flask /&gt; — Micro but mighty 🧪">🧪 Flask</span>
        <span class="tech-badge b-dj"    data-tip="&lt;Django /&gt; — For perfectionists with deadlines 🎯">🎯 Django</span>
        <span class="tech-badge b-sb"    data-tip="&lt;SpringBoot /&gt; — Enterprise power, dev joy ☕">☕ Spring Boot</span>
        <span class="tech-badge b-tw"    data-tip="&lt;Tailwind /&gt; — Utility-first, beauty-always 🎨">💨 TailwindCSS</span>
      </div>
    </div>

    <div class="badge-group">
      <div class="badge-group-title">🗄️ Databases</div>
      <div class="badges-row">
        <span class="tech-badge b-mysql" data-tip="&lt;MySQL /&gt; — Data that stays where you put it 🗄️">🐬 MySQL</span>
        <span class="tech-badge b-mongo" data-tip="&lt;MongoDB /&gt; — Documents, not tables. Freedom. 🍃">🍃 MongoDB</span>
        <span class="tech-badge b-redis" data-tip="&lt;Redis /&gt; — Speed is a feature ⚡">⚡ Redis</span>
      </div>
    </div>

    <div class="badge-group">
      <div class="badge-group-title">⚙️ Tools &amp; Platforms</div>
      <div class="badges-row">
        <span class="tech-badge b-git"   data-tip="&lt;Git /&gt; — Because final_v3.zip isn't version control 😅">🔴 Git &amp; GitHub</span>
        <span class="tech-badge b-linux" data-tip="&lt;Linux /&gt; — Real devs live in the terminal 💻">🐧 Linux</span>
        <span class="tech-badge b-vs"    data-tip="&lt;VSCode /&gt; — The editor that just gets it 🔵">🔵 VS Code</span>
        <span class="tech-badge b-post"  data-tip="&lt;Postman /&gt; — Test before you trust 🔬">🔬 Postman</span>
        <span class="tech-badge b-adobe" data-tip="&lt;Adobe /&gt; — Where design becomes destiny 🎭">🎭 Adobe UI-UX</span>
      </div>
    </div>
  </section>

  <!-- ── PROJECTS ── -->
  <section>
    <div class="section-title"><span>🚀</span> Featured Projects</div>
    <div class="projects-grid">

      <div class="project-card">
        <div class="project-title">🏘️ Smart Community Platform</div>
        <div class="project-sub">Scalable Platform &amp; Hybrid Database Architecture</div>
        <ul class="project-points">
          <li data-icon="🔗">Scalable community platform leveraging a hybrid relational + NoSQL database design for performance and flexibility.</li>
          <li data-icon="⚡">Redis caching for fast data retrieval and low-latency user experience at scale.</li>
          <li data-icon="🎨">Responsive front-end with clean UI/UX and community engagement features.</li>
        </ul>
        <div class="stack-chips">
          <span class="chip">Flask</span><span class="chip">MySQL</span><span class="chip">MongoDB</span><span class="chip">Redis</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-title">📝 Personal Blog Management System</div>
        <div class="project-sub">Full-Stack CRUD App with Responsive UI</div>
        <ul class="project-points">
          <li data-icon="📋">Full-stack <strong>CRUD</strong> blog app with dynamic content rendering and backend routing via Python Flask.</li>
          <li data-icon="📱">Fully <strong>responsive UI</strong> built with clean UI/UX principles for an optimal reading &amp; writing experience.</li>
          <li data-icon="🔒">Structured relational data management with MySQL for reliable content storage.</li>
        </ul>
        <div class="stack-chips">
          <span class="chip">HTML</span><span class="chip">CSS</span><span class="chip">JS</span><span class="chip">Flask</span><span class="chip">MySQL</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-title">🌦️ Real-Time Monitoring Weather App</div>
        <div class="project-sub">Frontend &amp; REST API Integration</div>
        <ul class="project-points">
          <li data-icon="🌍">Live weather intelligence — temperature forecasts, humidity, wind speed &amp; location-based data in real time.</li>
          <li data-icon="📡">Powered by <strong>REST API integrations</strong> with Django as robust backend for data processing.</li>
          <li data-icon="🖌️">Mobile-first intuitive UI built in React Native for seamless cross-platform experience.</li>
        </ul>
        <div class="stack-chips">
          <span class="chip">React Native</span><span class="chip">Django</span><span class="chip">REST API</span><span class="chip">UI/UX</span>
        </div>
      </div>

    </div>
  </section>

  <!-- ── GITHUB STATS ── -->
  <section>
    <div class="section-title"><span>📊</span> GitHub Stats</div>
    <div class="stats-grid">
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api?username=DhnaushHub&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&hide_border=true&bg_color=161b22&title_color=a56ef5&icon_color=a56ef5&text_color=c9d1d9" alt="Dhanush's GitHub Stats"/>
      </div>
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=DhnaushHub&layout=compact&langs_count=8&theme=tokyonight&hide_border=true&bg_color=161b22&title_color=a56ef5&text_color=c9d1d9" alt="Top Languages"/>
      </div>
    </div>
    <div class="stat-card" style="margin-top:1rem">
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=DhnaushHub&theme=tokyonight&hide_border=true&background=161b22&ring=7E3ACE&fire=FF6B6B&currStreakLabel=a56ef5" alt="GitHub Streak" style="width:100%;display:block"/>
    </div>
  </section>

  <!-- ── TROPHIES ── -->
  <section>
    <div class="section-title"><span>🏆</span> GitHub Trophies</div>
    <div style="background:var(--bg2);border:1px solid var(--border);border-radius:12px;overflow:hidden;padding:1rem;text-align:center">
      <img src="https://github-profile-trophy.vercel.app/?username=DhnaushHub&theme=tokyonight&no-frame=true&no-bg=true&margin-w=6&row=1" alt="GitHub Trophies" style="max-width:100%"/>
    </div>
  </section>

  <!-- ── CURRENTLY EXPLORING ── -->
  <section>
    <div class="section-title"><span>🌱</span> Currently Exploring</div>
    <div class="explore-grid">
      <div class="explore-card">
        <div class="explore-icon">🤖</div>
        <div>
          <div class="explore-title">Generative AI &amp; LLMs</div>
          <div class="explore-sub">Building with Claude, GPT APIs &amp; advanced Prompt Engineering</div>
        </div>
      </div>
      <div class="explore-card">
        <div class="explore-icon">🧱</div>
        <div>
          <div class="explore-title">Full-Stack Patterns</div>
          <div class="explore-sub">Microservices, Redis caching, REST &amp; GraphQL at scale</div>
        </div>
      </div>
      <div class="explore-card">
        <div class="explore-icon">📱</div>
        <div>
          <div class="explore-title">Cross-Platform Mobile</div>
          <div class="explore-sub">Deepening React Native expertise for production apps</div>
        </div>
      </div>
      <div class="explore-card">
        <div class="explore-icon">🎨</div>
        <div>
          <div class="explore-title">Design Systems</div>
          <div class="explore-sub">Reusable component libraries with TailwindCSS</div>
        </div>
      </div>
    </div>
  </section>

</div>

<!-- ── FOOTER ── -->
<div class="footer-wave">
  <h3>💬 Let's Connect &amp; Build Something Awesome Together!</h3>
  <a href="mailto:dhanushram406@gmail.com" class="connect-btn">✉️ Say Hello — dhanushram406@gmail.com</a>
</div>

<script>
/* ── STARFIELD ── */
(function(){
  const c = document.getElementById('stars-canvas');
  const ctx = c.getContext('2d');
  let W, H, stars=[];
  function resize(){ W=c.width=window.innerWidth; H=c.height=window.innerHeight; }
  function init(){
    resize();
    stars=[];
    for(let i=0;i<160;i++) stars.push({
      x:Math.random()*W, y:Math.random()*H,
      r:Math.random()*1.2+0.3,
      a:Math.random(),
      sp:Math.random()*0.008+0.002
    });
  }
  function tick(){
    ctx.clearRect(0,0,W,H);
    stars.forEach(s=>{
      s.a+=s.sp; if(s.a>1)s.a=0;
      ctx.beginPath();
      ctx.arc(s.x,s.y,s.r,0,Math.PI*2);
      ctx.fillStyle=`rgba(165,110,245,${Math.abs(Math.sin(s.a))})`;
      ctx.fill();
    });
    requestAnimationFrame(tick);
  }
  window.addEventListener('resize',init);
  init(); tick();
})();

/* ── TYPING ANIMATION ── */
(function(){
  const lines=[
    "Hey there! I'm Dhanush 👋",
    "Full-Stack Developer 🚀",
    "AI & GenAI Enthusiast 🤖",
    "UI/UX Craftsman 🎨",
    "Always building something cool ✨"
  ];
  const el=document.getElementById('typing-text');
  let li=0,ci=0,deleting=false,wait=0;
  function type(){
    if(wait>0){wait--;setTimeout(type,40);return;}
    const cur=lines[li];
    if(!deleting){
      ci++;el.textContent=cur.slice(0,ci);
      if(ci===cur.length){deleting=true;wait=55;setTimeout(type,60);return;}
    } else {
      ci--;el.textContent=cur.slice(0,ci);
      if(ci===0){deleting=false;li=(li+1)%lines.length;wait=8;}
    }
    setTimeout(type,deleting?28:62);
  }
  type();
})();
</script>
</body>
</html>
