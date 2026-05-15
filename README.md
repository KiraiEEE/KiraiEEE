<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>kiraieee@github</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg:        #0d0f14;
    --bg2:       #13161e;
    --bg3:       #1a1e28;
    --border:    #2a2f3f;
    --green:     #4ade80;
    --green-dim: #22c55e;
    --teal:      #2dd4bf;
    --yellow:    #facc15;
    --muted:     #6b7280;
    --text:      #e2e8f0;
    --arrow:     #4ade80;
  }

  body {
    font-family: 'JetBrains Mono', monospace;
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
    display: grid;
    place-items: center;
    padding: 2rem;
  }

  .card {
    display: grid;
    grid-template-columns: 1fr 1.1fr;
    gap: 0;
    max-width: 960px;
    width: 100%;
    border: 1px solid var(--border);
    border-radius: 10px;
    overflow: hidden;
    background: var(--bg2);
  }

  /* ── LEFT: ascii ─────────────────────── */
  .ascii-panel {
    background: var(--bg);
    border-right: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 2rem 1.5rem;
    overflow: hidden;
  }

  .ascii-art {
    font-size: 7.2px;
    line-height: 1.18;
    color: var(--green-dim);
    white-space: pre;
    user-select: none;
    filter: brightness(0.9);
  }

  /* ── RIGHT: info ─────────────────────── */
  .info-panel {
    padding: 2rem 2rem 2rem 2.25rem;
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }

  .header-line {
    display: flex;
    align-items: center;
    gap: 8px;
    padding-bottom: 1rem;
    border-bottom: 1px solid var(--border);
  }

  .handle {
    font-size: 15px;
    font-weight: 600;
    color: var(--green);
    letter-spacing: 0.03em;
  }

  .handle::before { content: '> '; color: var(--muted); }

  .blink {
    display: inline-block;
    width: 8px;
    height: 15px;
    background: var(--green);
    vertical-align: middle;
    margin-left: 4px;
    animation: blink 1.1s step-end infinite;
  }

  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  /* ── section ─────────────────────── */
  .section {}

  .cmd-line {
    font-size: 11.5px;
    color: var(--muted);
    margin-bottom: 0.6rem;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .cmd-line::before {
    content: '$';
    color: var(--green);
    font-weight: 600;
  }

  .cmd-line span { color: var(--yellow); }

  .rows {
    display: flex;
    flex-direction: column;
    gap: 4px;
    padding-left: 2px;
  }

  .row {
    display: grid;
    grid-template-columns: 80px 1fr;
    align-items: baseline;
    font-size: 12.5px;
  }

  .key {
    color: var(--muted);
    font-size: 11px;
    letter-spacing: 0.06em;
    text-transform: lowercase;
  }

  .val {
    color: var(--text);
    display: flex;
    align-items: baseline;
    gap: 6px;
    flex-wrap: wrap;
  }

  .val::before {
    content: '→';
    color: var(--arrow);
    flex-shrink: 0;
    font-size: 11px;
  }

  .tag {
    background: var(--bg3);
    border: 1px solid var(--border);
    border-radius: 3px;
    padding: 1px 6px;
    font-size: 11px;
    color: var(--teal);
    white-space: nowrap;
  }

  .tag.soft { color: var(--text); opacity: 0.75; }

  .row.indent {
    grid-template-columns: 80px 1fr;
  }
  .row.indent .key { visibility: hidden; }

  .footer {
    margin-top: auto;
    padding-top: 1rem;
    border-top: 1px solid var(--border);
    font-size: 11px;
    color: var(--muted);
    display: flex;
    align-items: center;
    gap: 4px;
  }

  .footer .prompt { color: var(--green); }
</style>
</head>
<body>

<div class="card">

  <!-- ASCII -->
  <div class="ascii-panel">
    <pre class="ascii-art">
⠀⠀⠀⡠⠀⡠⠊⠁⠀⠀⣠⡴⠛⠉⣠⡶⠟⠋⣥⣠⣤⡀⠀⠀⠀⠀⠀⠀⠈⠑⢦⣄⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢶⡄⠀⠀⠀⠀⠀
⠀⢀⣜⣴⠟⢀⠄⢀⠴⠊⡁⠀⣠⠞⢁⠆⢀⠜⠋⠀⠈⠛⢦⡀⠀⠀⠀⠀⠀⠀⠀⠈⠻⣷⣄⣀⠀⠀⠀⠀⠀⠀⠈⠂⠈⠢⡀⠀⠀⠀
⠀⣾⠟⠁⠐⠁⠀⠀⡠⠊⠀⠔⠁⠀⡜⠀⠀⢀⠀⢀⠀⠀⠀⠑⣄⠀⠀⠀⠀⠀⠀⢢⣀⠈⢻⣿⣷⡀⠀⠀⠀⠀⠀⠀⠀⡀⠈⠂⡀⠀
⣼⠃⠀⠀⠀⠀⣠⢞⣠⠄⢲⢂⡔⣸⠀⠀⣠⡇⠀⠘⡇⠀⠀⠀⠈⢦⠀⠀⠀⠀⢸⠀⠈⠉⢀⣍⣈⢻⣦⠀⠀⠀⠀⠀⠀⠱⡀⠀⠘⢦
⠁⠀⠀⠀⢀⡴⠋⢘⡇⢠⡾⠋⠀⡇⠀⢠⠃⠀⠀⠀⠻⡄⠀⠀⠀⠈⠳⡀⠀⠀⠈⡆⠀⢰⡟⠁⠈⠳⣿⠀⠀⠁⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠐⠁⠀⢴⡞⣡⠋⠀⠀⢸⠁⠀⠏⠀⠀⠀⠀⠀⢱⠀⠀⠀⠀⠀⠱⡄⠀⠀⠘⣄⠀⠹⡗⢤⡀⠈⠳⡄⠀⢹⡀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⣠⠋⡴⠃⡄⠀⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠁⠀⠀⠀⠀⠀⠹⡄⠀⠀⠈⢦⡀⠙⣄⠙⢦⣤⣾⡆⠀⣇⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⣿⡞⠁⠀⡇⠀⠀⣿⠀⠀⠀⠀⠀⠀⠀⠀⠘⡄⠀⠀⠀⠀⠀⠀⢰⡀⠀⣆⠀⠱⣄⣸⡇⠀⠘⠿⢻⠀⢸⠀⠀⠀⠀⠀⠀
⠀⠀⢳⠀⣠⠟⠀⠀⠀⡇⠀⢠⣿⡄⠀⠀⠀⠀⠀⠀⠀⠀⢱⠀⠀⠀⠀⠀⠀⢸⡇⠀⡿⡄⠀⠈⢛⢧⣀⡀⠂⣸⠀⢸⠀⠀⡄⠀⠀⠀
⠀⠀⠀⠻⣏⡀⠀⠀⠀⣷⠀⢸⣿⣿⡀⢢⠀⠀⡀⠀⠀⠀⠀⢧⠀⠀⠀⡇⠀⣼⡇⢠⠇⢹⣄⠀⠘⡆⢈⠉⠛⠁⠀⢸⠀⠀⠟⢆⠀⠀
⡇⠀⣤⠀⠹⣷⡀⠀⠀⣿⡄⢸⣿⠻⣧⠈⢧⠀⠹⡀⠀⠀⠀⠈⣆⠀⠀⣧⢰⠇⡇⣸⠀⠀⠹⣆⠀⣿⣼⡄⠀⠀⠀⢸⡆⢸⠀⠘⣆⠀
⢹⡀⣿⣧⡀⠹⣷⡀⠀⢹⣷⢸⣿⡆⠹⣧⡘⣧⠀⠱⡄⠀⡀⠀⠸⡆⠀⢹⡏⢀⣿⣧⡠⠤⠴⢿⡇⣻⣿⣇⠀⠀⠀⢸⡇⡜⠀⢀⡏⠀
⠘⣧⠀⢸⣷⣄⢻⣷⣄⠈⣿⣿⣿⣉⡛⢻⡷⣿⣇⠀⢹⣦⣱⡄⠀⢹⡖⢻⠋⣹⣿⣥⣴⣶⣶⣶⣿⣿⣉⣿⡄⠀⠀⢸⣵⠃⠀⣸⡇⠀
⠀⠹⡆⢸⠻⣿⠮⢿⣿⣷⣾⣿⡿⠋⢛⣻⣿⣿⣿⣧⠈⣿⣿⣿⣦⡀⢻⣼⠘⣿⠟⠉⢴⣾⣿⣿⡟⠻⡇⢹⣧⠀⠀⣾⡏⡰⢰⡇⠀⣠
⠀⠀⠹⣼⡄⠘⣷⡀⠙⢿⣿⡿⣇⠀⠈⢻⣿⣿⡿⠻⣷⣼⡏⢻⣟⠻⣾⣿⡄⠁⠀⠀⠈⠛⠛⠋⠁⠀⢠⣿⣿⡀⢠⣿⠟⢡⣿⠃⣾⠃
⠀⠀⠀⠙⣧⠀⣿⢷⣄⢀⣹⣿⣿⣅⠀⠈⠁⠀⠀⠀⠈⣿⣿⡄⠙⠦⠘⢿⣿⣄⠀⠀⠀⠀⠀⠀⢀⣴⣫⡾⣿⡇⣼⠋⣴⣿⣿⡞⠁⠀
⠀⠀⠀⠀⠈⠀⣿⣤⣝⠋⠛⢿⣿⣿⣿⣷⡂⠀⠀⠀⠀⠀⠁⠙⢆⠀⠀⠀⠙⢌⠂⠀⠀⠀⣠⡴⢻⡿⠋⣰⣿⣷⣧⣾⣿⡿⠋⠀⠀⠀
⠀⠀⠀⠀⠀⠀⣿⣿⣿⣧⡀⠈⠛⣿⣍⡛⠛⠓⠢⠤⠀⠀⢀⣷⠈⠀⠀⠀⠀⠀⠀⠠⠔⠋⠁⣠⣏⣴⠞⢋⣸⣿⣯⣿⣏⣀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⢸⣿⣿⣷⡹⣷⣤⣽⣾⣽⣢⢤⣀⠀⠀⠀⠊⢾⣄⠀⠀⠀⠀⠀⠀⠀⠀⣠⣾⣿⠭⠔⠒⠛⠛⠛⠿⣿⣿⡟⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⣿⡟⣿⣿⣌⠻⣍⠉⠛⢿⣟⠛⠛⠓⠀⠀⢀⣈⣀⣀⡀⠀⢀⣠⡶⣿⡾⠋⠀⠀⠀⠀⠀⠀⠀⠀⠀⠙⢿⣆⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠘⣇⠘⣿⣿⠳⣜⢷⣄⠀⢿⣿⣦⣄⡀⠀⠀⠈⠉⠉⠉⠁⠈⣀⣴⡟⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠙⠂⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠈⠀⠈⢿⣇⠈⠳⢿⣷⣼⣿⣿⣽⣿⣶⣄⠀⠀⠀⠀⠀⠈⢨⢿⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢄
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠙⠂⠀⠀⠑⠿⣿⡎⠛⢧⠈⠙⠙⠦⣄⣠⣤⣴⣿⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠛⡆⠀⠀⠀⠀⠀⠀⣸⣿⣿⣿⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⣤⣤⣀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠉⠛⣿⡄⠀⠀⠀⠀⠀⠀⠀⠀⣰⡟⠋⠚⢳⡿⠻⡄⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠘⣷⠀⠀⠀⠀⠀⠀⠀⠀⣿⠁⠀⣴⠟⠃⠀⣷⠀⡀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⣾⡟⣧⠀⠀⠀⠀⠀⠀⠀⠘⢧⣾⠃⠀⢀⣼⠃⢠⡇
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⣶⠏⣿⢷⡟⠢⡀⠀⠀⠀⠀⠀⠠⠄⠉⠛⠛⢭⣴⠇⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣠⠔⢊⢀⡟⢸⡟⢸⣷⡄⠀⡀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠉⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⠄⠊⠁⠀⠀⠎⣸⡇⣿⢇⠏⠹⣿⡄⠱⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⠜⠁⠀⠀⠀⠀⢀⡴⣿⠟⣡⠋⠀⠀⢹⣷⡀⣷⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⠎⠀⠀⠀⠀⢀⡴⠋⣼⠏⠀⣿⠀⢀⠔⠉⠙⠳⣿⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡎⠀⠀⠀⠀⠀⣿⠀⠀⣿⠀⠀⢿⠀⡎⠀⠀⠀⠀⢸⣷⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢇⠀⠀⠀⠀⢀⣿⣤⣤⣿⡆⠀⢸⣦⢃⡴⠀⠀⠀⠘⣿⣷⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⣀⣀⣀⣀⣀⣀⣀⠘⣄⠀⠀⢠⣿⣿⠻⣿⣿⠇⢀⣼⠿⠋⠀⠀⠀⠀⠀⠈⢿⣿⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⡞⠁⠀⠀⠀⠀⠀⠀⠈⠳⣿⣈⡶⠋⣹⣿⣧⡈⡿⠀⣠⣷⡾⠀⠀⠀⠀⠀⠀⠀⠀⠙⣿⡆⠀⠀⠀⠀⠀⣀⣤⠴
⠀⠀⠀⠀⠀⠀⠀⡸⠀⠀⢲⣤⣠⣤⣄⣠⡀⠀⠙⢯⡀⠀⢸⣿⣿⡿⠁⣰⣿⣿⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢿⡄⠀⢠⣶⡿⠏⠀⠀
⠀⠀⠀⠀⠀⠀⠰⠁⠀⠀⣾⣿⠠⠀⠀⠈⠻⣶⣄⠀⠙⠲⣿⡹⠏⠀⣰⣿⠿⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢱⣴⠟⠁⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⡠⠦⠚⠉⠀⠀⠀⠐⠀⠀⠈⢿⡷⢤⠴⠛⠁⠀⠀⢈⣀⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢻⡄⠀⠀⠀⠀⠀</pre>
  </div>

  <!-- INFO -->
  <div class="info-panel">

    <div class="header-line">
      <span class="handle">kiraieee@github</span>
      <span class="blink"></span>
    </div>

    <!-- env -->
    <div class="section">
      <div class="cmd-line"><span>cat</span> eny.inf</div>
      <div class="rows">
        <div class="row"><span class="key">name</span><span class="val">akram ben fekih</span></div>
        <div class="row"><span class="key">job</span><span class="val">no job (yet)</span></div>
        <div class="row"><span class="key">height</span><span class="val">too short</span></div>
        <div class="row"><span class="key">skills</span><span class="val">a lot</span></div>
      </div>
    </div>

    <!-- stack -->
    <div class="section">
      <div class="cmd-line"><span>cat</span> stack.inf</div>
      <div class="rows">
        <div class="row">
          <span class="key">frontend</span>
          <span class="val"><span class="tag">Vue.js</span><span class="tag">Nuxt</span></span>
        </div>
        <div class="row">
          <span class="key">backend</span>
          <span class="val"><span class="tag">Express</span><span class="tag">Sequelize</span></span>
        </div>
        <div class="row indent">
          <span class="key">›</span>
          <span class="val"><span class="tag">.NET WinUI</span></span>
        </div>
        <div class="row">
          <span class="key">mobile</span>
          <span class="val"><span class="tag">Flutter</span></span>
        </div>
        <div class="row">
          <span class="key">ai / ml</span>
          <span class="val"><span class="tag">TensorFlow</span><span class="tag">PyTorch</span><span class="tag">Pandas</span></span>
        </div>
        <div class="row">
          <span class="key">tools</span>
          <span class="val"><span class="tag">Claude Code</span></span>
        </div>
      </div>
    </div>

    <!-- hobbies -->
    <div class="section">
      <div class="cmd-line"><span>cat</span> hobby.inf</div>
      <div class="rows">
        <div class="row">
          <span class="key">gaming</span>
          <span class="val"><span class="tag soft">Genshin</span><span class="tag soft">Valorant</span></span>
        </div>
        <div class="row">
          <span class="key">vibes</span>
          <span class="val"><span class="tag soft">cafe hopping</span><span class="tag soft">anime</span></span>
        </div>
        <div class="row">
          <span class="key">always</span>
          <span class="val">learning...</span>
        </div>
      </div>
    </div>

    <div class="footer">
      <span class="prompt">$</span> _
    </div>

  </div>
</div>

</body>
</html>
