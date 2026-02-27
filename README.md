<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Navdeep</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;1,400&family=Courier+Prime:wght@400;700&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0a0a0a;
    --fg: #e8e4dc;
    --dim: #5a5650;
    --accent: #c9b89a;
    --rule: #1e1e1e;
  }

  body {
    background: var(--bg);
    color: var(--fg);
    font-family: 'Courier Prime', monospace;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 60px 20px;
  }

  .container {
    max-width: 640px;
    width: 100%;
  }

  .header {
    border-top: 1px solid var(--fg);
    padding-top: 32px;
    margin-bottom: 56px;
    opacity: 0;
    animation: rise 1s ease forwards 0.2s;
  }

  .name {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.8rem, 8vw, 4.5rem);
    font-weight: 400;
    letter-spacing: -0.02em;
    line-height: 1;
    margin-bottom: 12px;
  }

  .name em {
    font-style: italic;
    color: var(--accent);
  }

  .role {
    font-size: 0.72rem;
    letter-spacing: 0.22em;
    text-transform: uppercase;
    color: var(--dim);
    display: flex;
    gap: 24px;
  }

  .role span::before {
    content: '—  ';
    color: var(--rule);
  }

  .bio {
    margin-bottom: 56px;
    opacity: 0;
    animation: rise 1s ease forwards 0.5s;
  }

  .bio p {
    font-family: 'Playfair Display', serif;
    font-size: 1.05rem;
    line-height: 1.85;
    color: #b0aba3;
    font-style: italic;
    max-width: 480px;
  }

  .section-label {
    font-size: 0.65rem;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--dim);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 16px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--rule);
  }

  .stack {
    margin-bottom: 56px;
    opacity: 0;
    animation: rise 1s ease forwards 0.8s;
  }

  .tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .tag {
    border: 1px solid var(--rule);
    padding: 6px 14px;
    font-size: 0.72rem;
    letter-spacing: 0.12em;
    color: var(--dim);
    transition: all 0.2s ease;
    cursor: default;
  }

  .tag:hover {
    border-color: var(--accent);
    color: var(--accent);
  }

  .projects {
    margin-bottom: 56px;
    opacity: 0;
    animation: rise 1s ease forwards 1.1s;
  }

  .project {
    padding: 24px 0;
    border-bottom: 1px solid var(--rule);
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 16px;
    align-items: start;
    transition: all 0.2s ease;
  }

  .project:first-of-type {
    border-top: 1px solid var(--rule);
  }

  .project:hover .project-name {
    color: var(--accent);
  }

  .project-name {
    font-family: 'Playfair Display', serif;
    font-size: 1.1rem;
    font-weight: 500;
    margin-bottom: 6px;
    transition: color 0.2s ease;
  }

  .project-desc {
    font-size: 0.78rem;
    color: var(--dim);
    line-height: 1.6;
    letter-spacing: 0.03em;
  }

  .project-tech {
    font-size: 0.65rem;
    letter-spacing: 0.15em;
    color: #3a3832;
    text-transform: uppercase;
    text-align: right;
    padding-top: 4px;
  }

  .footer {
    opacity: 0;
    animation: rise 1s ease forwards 1.4s;
    display: flex;
    flex-wrap: wrap;
    gap: 24px;
    align-items: center;
  }

  .stat-block {
    display: flex;
    flex-direction: column;
    gap: 4px;
  }

  .stat-value {
    font-family: 'Playfair Display', serif;
    font-size: 1.4rem;
    color: var(--fg);
  }

  .stat-label {
    font-size: 0.62rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--dim);
  }

  .divider-v {
    width: 1px;
    height: 36px;
    background: var(--rule);
  }

  .badge-row {
    margin-top: 32px;
    display: flex;
    gap: 12px;
    align-items: center;
    flex-wrap: wrap;
  }

  .badge-row img {
    height: 22px;
    filter: grayscale(1) brightness(0.7);
    transition: filter 0.2s ease;
  }

  .badge-row img:hover {
    filter: grayscale(0.3) brightness(1);
  }

  .cursor {
    display: inline-block;
    width: 2px;
    height: 1em;
    background: var(--accent);
    margin-left: 4px;
    vertical-align: middle;
    animation: blink 1.1s step-end infinite;
  }

  @keyframes blink {
    50% { opacity: 0; }
  }

  @keyframes rise {
    from { opacity: 0; transform: translateY(16px); }
    to   { opacity: 1; transform: translateY(0); }
  }
</style>
</head>
<body>
<div class="container">

  <header class="header">
    <h1 class="name">Nav<em>deep</em><span class="cursor"></span></h1>
    <div class="role">
      <span>Full-Stack</span>
      <span>DevOps</span>
    </div>
  </header>

  <section class="bio">
    <p>Keeping systems running. Building things that matter. Obsessed with clean infrastructure and minimal code that does more.</p>
  </section>

  <section class="stack">
    <div class="section-label">Stack</div>
    <div class="tags">
      <div class="tag">TypeScript</div>
      <div class="tag">Python</div>
      <div class="tag">JavaScript</div>
      <div class="tag">discord.py</div>
      <div class="tag">DevOps</div>
    </div>
  </section>

  <section class="projects">
    <div class="section-label">Work</div>

    <div class="project">
      <div>
        <div class="project-name">questor</div>
        <div class="project-desc">A minimal quest completer bot. Lightweight, focused, built to run.</div>
      </div>
      <div class="project-tech">discord.py</div>
    </div>

  </section>

  <footer class="footer">
    <div class="badge-row">
      <a href="https://codetime.dev" target="_blank">
        <img src="https://shields.jannchie.com/endpoint?style=for-the-badge&color=222&url=https%3A%2F%2Fapi.codetime.dev%2Fv3%2Fusers%2Fshield%3Fuid%3D35660%26tz%3DAsia%2FKolkata" alt="CodeTime">
      </a>
      <a href="https://github.com/oeut" target="_blank">
        <img src="https://lanyard.kyrie25.dev/api/1470061983704547503?waveColor=fff&waveSpotifyColor=212121&gradient=fff&borderRadius=25px&bg=000" alt="Discord Status">
      </a>
      <img src="https://komarev.com/ghpvc/?username=csynholic&color=gray&style=plastic" alt="Profile Views">
    </div>
  </footer>

</div>
</body>
</html>
