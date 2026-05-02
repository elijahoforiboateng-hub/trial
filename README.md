# Lesson Quick Trial Starter
Ofori-Boateng Elijah 

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>⌨️ INPUT/OUTPUT Devices Quiz Challenge</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Exo+2:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0e1a;
    --panel: #111827;
    --panel2: #1a2235;
    --border: #1e3a5f;
    --accent: #00d4ff;
    --accent2: #7c3aed;
    --accent3: #10b981;
    --gold: #f59e0b;
    --red: #ef4444;
    --text: #e2e8f0;
    --muted: #64748b;
    --lvl1: #10b981;
    --lvl2: #3b82f6;
    --lvl3: #f59e0b;
    --lvl4: #ef4444;
    --radius: 14px;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'Exo 2', sans-serif;
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
    overflow-x: hidden;
    background-image:
      radial-gradient(ellipse 80% 50% at 20% -20%, rgba(0,212,255,0.07) 0%, transparent 60%),
      radial-gradient(ellipse 60% 40% at 80% 110%, rgba(124,58,237,0.08) 0%, transparent 60%);
  }

  /* Starfield */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      radial-gradient(1px 1px at 10% 15%, rgba(255,255,255,0.4) 0%, transparent 100%),
      radial-gradient(1px 1px at 30% 60%, rgba(255,255,255,0.3) 0%, transparent 100%),
      radial-gradient(1px 1px at 55% 25%, rgba(255,255,255,0.5) 0%, transparent 100%),
      radial-gradient(1px 1px at 75% 80%, rgba(255,255,255,0.3) 0%, transparent 100%),
      radial-gradient(1px 1px at 90% 40%, rgba(255,255,255,0.4) 0%, transparent 100%),
      radial-gradient(1px 1px at 15% 85%, rgba(255,255,255,0.2) 0%, transparent 100%),
      radial-gradient(1px 1px at 65% 55%, rgba(255,255,255,0.3) 0%, transparent 100%);
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 820px;
    margin: 0 auto;
    padding: 24px 20px 60px;
    position: relative;
    z-index: 1;
  }

  /* ============ SCREENS ============ */
  .screen { display: none; animation: fadeIn 0.4s ease; }
  .screen.active { display: block; }

  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(16px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* ============ HEADER ============ */
  .site-header {
    text-align: center;
    padding: 40px 0 32px;
    border-bottom: 1px solid var(--border);
    margin-bottom: 40px;
  }
  .site-header .kicker {
    font-family: 'Orbitron', monospace;
    font-size: 11px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 16px;
  }
  .site-header h1 {
    font-family: 'Orbitron', monospace;
    font-size: clamp(28px, 6vw, 48px);
    font-weight: 900;
    line-height: 1.1;
    background: linear-gradient(135deg, var(--accent) 0%, #fff 50%, var(--accent2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 12px;
  }
  .site-header .subtitle {
    color: var(--muted);
    font-size: 15px;
    font-weight: 300;
    letter-spacing: 1px;
  }

  /* ============ CARDS ============ */
  .card {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 28px;
    margin-bottom: 20px;
  }

  /* ============ HOW TO PLAY ============ */
  .howto-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin: 24px 0;
  }
  @media (max-width: 560px) { .howto-grid { grid-template-columns: 1fr; } }

  .howto-item {
    background: var(--panel2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px;
    display: flex;
    gap: 14px;
    align-items: flex-start;
  }
  .howto-icon { font-size: 28px; line-height: 1; }
  .howto-item h3 { font-family: 'Orbitron', monospace; font-size: 11px; letter-spacing: 2px; color: var(--accent); margin-bottom: 6px; }
  .howto-item p { font-size: 13px; color: var(--muted); line-height: 1.5; }

  /* ============ LEVEL CARDS ============ */
  .levels-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 14px;
    margin: 24px 0;
  }
  @media (max-width: 480px) { .levels-grid { grid-template-columns: 1fr; } }

  .level-card {
    background: var(--panel2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .level-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
  }
  .level-card.l1::before { background: var(--lvl1); }
  .level-card.l2::before { background: var(--lvl2); }
  .level-card.l3::before { background: var(--lvl3); }
  .level-card.l4::before { background: var(--lvl4); }
  .level-card .badge { font-size: 28px; margin-bottom: 8px; }
  .level-card .lvl-label { font-family: 'Orbitron', monospace; font-size: 10px; letter-spacing: 2px; margin-bottom: 4px; }
  .level-card.l1 .lvl-label { color: var(--lvl1); }
  .level-card.l2 .lvl-label { color: var(--lvl2); }
  .level-card.l3 .lvl-label { color: var(--lvl3); }
  .level-card.l4 .lvl-label { color: var(--lvl4); }
  .level-card h3 { font-size: 14px; font-weight: 700; margin-bottom: 6px; }
  .level-card p { font-size: 12px; color: var(--muted); }

  /* ============ BUTTONS ============ */
  .btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    padding: 14px 32px;
    border-radius: 8px;
    font-family: 'Orbitron', monospace;
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    cursor: pointer;
    border: none;
    transition: all 0.2s;
  }
  .btn-primary {
    background: linear-gradient(135deg, var(--accent), #0080aa);
    color: #000;
    width: 100%;
    margin-top: 8px;
  }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 24px rgba(0,212,255,0.3); }
  .btn-secondary {
    background: transparent;
    border: 1px solid var(--accent);
    color: var(--accent);
    width: 100%;
    margin-top: 8px;
  }
  .btn-secondary:hover { background: rgba(0,212,255,0.1); }

  /* ============ PROGRESS ============ */
  .progress-bar-wrap {
    background: var(--panel2);
    border-radius: 100px;
    height: 6px;
    margin: 16px 0;
    overflow: hidden;
  }
  .progress-bar-fill {
    height: 100%;
    border-radius: 100px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transition: width 0.5s cubic-bezier(0.4,0,0.2,1);
  }

  /* ============ QUIZ HEAD ============ */
  .quiz-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
    flex-wrap: wrap;
    gap: 10px;
  }
  .quiz-level-badge {
    font-family: 'Orbitron', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    padding: 5px 14px;
    border-radius: 100px;
    font-weight: 700;
  }
  .quiz-level-badge.l1 { background: rgba(16,185,129,0.15); color: var(--lvl1); border: 1px solid rgba(16,185,129,0.3); }
  .quiz-level-badge.l2 { background: rgba(59,130,246,0.15); color: var(--lvl2); border: 1px solid rgba(59,130,246,0.3); }
  .quiz-level-badge.l3 { background: rgba(245,158,11,0.15); color: var(--lvl3); border: 1px solid rgba(245,158,11,0.3); }
  .quiz-level-badge.l4 { background: rgba(239,68,68,0.15); color: var(--lvl4); border: 1px solid rgba(239,68,68,0.3); }

  .quiz-score-display {
    font-family: 'Orbitron', monospace;
    font-size: 13px;
    color: var(--gold);
  }

  .question-number {
    font-family: 'Orbitron', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    color: var(--muted);
    margin-bottom: 8px;
  }

  .pts-badge {
    display: inline-block;
    font-family: 'Orbitron', monospace;
    font-size: 10px;
    padding: 3px 10px;
    border-radius: 100px;
    background: rgba(245,158,11,0.15);
    color: var(--gold);
    border: 1px solid rgba(245,158,11,0.3);
    margin-bottom: 16px;
  }

  .question-text {
    font-size: clamp(17px, 3vw, 22px);
    font-weight: 600;
    line-height: 1.4;
    margin-bottom: 28px;
    color: #fff;
  }

  /* ============ OPTIONS ============ */
  .options { display: flex; flex-direction: column; gap: 12px; }

  .option-btn {
    background: var(--panel2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px 20px;
    text-align: left;
    cursor: pointer;
    color: var(--text);
    font-family: 'Exo 2', sans-serif;
    font-size: 15px;
    transition: all 0.2s;
    display: flex;
    align-items: center;
    gap: 14px;
    position: relative;
    overflow: hidden;
  }
  .option-btn:hover:not(:disabled) {
    border-color: var(--accent);
    background: rgba(0,212,255,0.05);
    transform: translateX(4px);
  }
  .option-btn:disabled { cursor: default; }
  .option-btn .opt-letter {
    font-family: 'Orbitron', monospace;
    font-size: 12px;
    font-weight: 700;
    width: 30px;
    height: 30px;
    border-radius: 6px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: var(--panel);
    flex-shrink: 0;
    transition: all 0.2s;
  }
  .option-btn.correct {
    border-color: var(--accent3);
    background: rgba(16,185,129,0.1);
    color: #fff;
  }
  .option-btn.correct .opt-letter {
    background: var(--accent3);
    color: #000;
  }
  .option-btn.wrong {
    border-color: var(--red);
    background: rgba(239,68,68,0.08);
    color: var(--muted);
  }
  .option-btn.wrong .opt-letter {
    background: var(--red);
    color: #fff;
  }

  /* ============ EXPLANATION ============ */
  .explanation-box {
    margin-top: 20px;
    background: var(--panel2);
    border: 1px solid var(--border);
    border-left: 4px solid var(--accent);
    border-radius: var(--radius);
    padding: 20px;
    display: none;
    animation: fadeIn 0.3s ease;
  }
  .explanation-box.show { display: block; }
  .explanation-box .exp-header {
    font-family: 'Orbitron', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    color: var(--accent);
    margin-bottom: 10px;
  }
  .explanation-box .exp-text {
    font-size: 14px;
    line-height: 1.6;
    color: var(--text);
  }
  .explanation-box .exp-text .tick { color: var(--accent3); }
  .explanation-box .exp-text .cross { color: var(--red); }

  .pts-earned {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-family: 'Orbitron', monospace;
    font-size: 18px;
    font-weight: 700;
    color: var(--gold);
    margin-bottom: 12px;
  }

  /* ============ LEVEL COMPLETE ============ */
  .level-complete-screen { text-align: center; }
  .level-complete-icon { font-size: 80px; margin-bottom: 16px; animation: pulse 2s infinite; }
  @keyframes pulse { 0%,100% { transform: scale(1); } 50% { transform: scale(1.08); } }
  .level-complete-screen h2 {
    font-family: 'Orbitron', monospace;
    font-size: clamp(22px, 5vw, 36px);
    font-weight: 900;
    color: #fff;
    margin-bottom: 8px;
  }
  .level-complete-screen .badge-earned {
    font-size: 20px;
    color: var(--gold);
    margin-bottom: 24px;
  }
  .pts-summary {
    font-family: 'Orbitron', monospace;
    font-size: 28px;
    font-weight: 700;
    color: var(--accent);
    margin-bottom: 8px;
  }
  .pts-summary-label { font-size: 13px; color: var(--muted); margin-bottom: 32px; }

  /* ============ FINAL RESULTS ============ */
  .final-screen { text-align: center; }
  .final-trophy { font-size: 90px; margin-bottom: 16px; animation: bounce 1.5s infinite; }
  @keyframes bounce { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-12px)} }
  .final-screen h2 {
    font-family: 'Orbitron', monospace;
    font-size: clamp(24px, 5vw, 40px);
    font-weight: 900;
    background: linear-gradient(135deg, var(--gold), #fff, var(--gold));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 8px;
  }

  .score-breakdown {
    background: var(--panel2);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    overflow: hidden;
    margin: 28px 0;
    text-align: left;
  }
  .score-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px 24px;
    border-bottom: 1px solid var(--border);
  }
  .score-row:last-child { border-bottom: none; }
  .score-row .sr-label { font-size: 14px; color: var(--muted); }
  .score-row .sr-pts { font-family: 'Orbitron', monospace; font-size: 16px; font-weight: 700; color: var(--accent); }
  .score-row.total {
    background: linear-gradient(90deg, rgba(0,212,255,0.05), transparent);
    border-top: 1px solid var(--accent);
  }
  .score-row.total .sr-label { color: #fff; font-weight: 700; font-size: 15px; }
  .score-row.total .sr-pts { color: var(--gold); font-size: 22px; }

  .badges-row {
    display: flex;
    justify-content: center;
    gap: 24px;
    flex-wrap: wrap;
    margin: 20px 0 32px;
    font-size: 13px;
    color: var(--muted);
  }
  .badges-row span { display: flex; align-items: center; gap: 6px; }

  /* ============ REFERENCE SCREEN ============ */
  .ref-cols {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
    margin-top: 20px;
  }
  @media (max-width: 600px) { .ref-cols { grid-template-columns: 1fr; } }
  .ref-col { background: var(--panel2); border: 1px solid var(--border); border-radius: 10px; padding: 18px; }
  .ref-col h3 {
    font-family: 'Orbitron', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    margin-bottom: 14px;
    padding-bottom: 10px;
    border-bottom: 1px solid var(--border);
  }
  .ref-col.input h3 { color: var(--lvl1); }
  .ref-col.output h3 { color: var(--lvl4); }
  .ref-col.both h3 { color: var(--lvl2); }
  .ref-col ul { list-style: none; }
  .ref-col ul li { font-size: 12px; color: var(--muted); padding: 4px 0; border-bottom: 1px solid rgba(255,255,255,0.03); }
  .ref-col ul li::before { content: '›'; margin-right: 6px; color: var(--accent); }

  /* ============ NAV ============ */
  .nav-tabs {
    display: flex;
    gap: 8px;
    justify-content: center;
    margin-bottom: 32px;
    flex-wrap: wrap;
  }
  .nav-tab {
    background: transparent;
    border: 1px solid var(--border);
    color: var(--muted);
    padding: 8px 18px;
    border-radius: 100px;
    font-family: 'Orbitron', monospace;
    font-size: 10px;
    letter-spacing: 1px;
    cursor: pointer;
    transition: all 0.2s;
  }
  .nav-tab:hover, .nav-tab.active {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(0,212,255,0.07);
  }

  /* ============ SCORE BAR TOP ============ */
  .top-score-bar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 12px 20px;
    margin-bottom: 24px;
    gap: 12px;
    flex-wrap: wrap;
  }
  .top-score-bar .ts-item { display: flex; align-items: center; gap: 8px; font-size: 13px; color: var(--muted); }
  .top-score-bar .ts-item strong { font-family: 'Orbitron', monospace; font-size: 14px; color: var(--text); }
  .divider { width: 1px; height: 24px; background: var(--border); }

  /* ============ SECTION TITLE ============ */
  .section-title {
    text-align: center;
    margin-bottom: 28px;
  }
  .section-title .kicker {
    font-family: 'Orbitron', monospace;
    font-size: 10px;
    letter-spacing: 3px;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 10px;
  }
  .section-title h2 {
    font-family: 'Orbitron', monospace;
    font-size: clamp(20px, 4vw, 30px);
    font-weight: 900;
    color: #fff;
  }

  /* Animations */
  @keyframes slideUp { from { transform: translateY(30px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
  .animate-in { animation: slideUp 0.4s ease both; }

  .hint-text { text-align: center; font-size: 12px; color: var(--muted); margin-top: 12px; font-style: italic; }
</style>
</head>
<body>
<div class="container">

  <!-- HEADER -->
  <header class="site-header">
    <div class="kicker">⌨️ OFORI BOATENG ELIJAH ONLINE LEARNING CLASS</div>
    <h1>INPUT/OUTPUT DEVICES<br>QUIZ CHALLENGE</h1>
    <div class="subtitle">25 Questions · 4 Levels · Earn Badges · Scored · Explained</div>
  </header>

  <!-- NAV -->
  <nav class="nav-tabs">
    <button class="nav-tab active" onclick="showScreen('home')">🏠 Home</button>
    <button class="nav-tab" onclick="showScreen('quiz')">▶ Quiz</button>
    <button class="nav-tab" onclick="showScreen('reference')">📋 Reference</button>
  </nav>

  <!-- ===== HOME SCREEN ===== -->
  <div id="screen-home" class="screen active">

    <!-- How to Play -->
    <div class="card">
      <div class="section-title">
        <div class="kicker">Getting Started</div>
        <h2>HOW TO PLAY</h2>
      </div>
      <div class="howto-grid">
        <div class="howto-item">
          <div class="howto-icon">🎯</div>
          <div>
            <h3>Objective</h3>
            <p>Answer all 25 questions correctly to earn the MASTER badge and a perfect score.</p>
          </div>
        </div>
        <div class="howto-item">
          <div class="howto-icon">📊</div>
          <div>
            <h3>4 Levels</h3>
            <p>Progress from Beginner → Intermediate → Advanced → Expert. Each level is harder!</p>
          </div>
        </div>
        <div class="howto-item">
          <div class="howto-icon">⭐</div>
          <div>
            <h3>Scoring</h3>
            <p>Lvl 1 = 1pt · Lvl 2 = 2pts · Lvl 3 = 3pts · Lvl 4 = 4pts · MAX: 63 points</p>
          </div>
        </div>
        <div class="howto-item">
          <div class="howto-icon">💡</div>
          <div>
            <h3>Feedback</h3>
            <p>Every answer includes an explanation — learn from both correct AND incorrect answers.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Level Overview -->
    <div class="card">
      <div class="section-title">
        <div class="kicker">Scoring System</div>
        <h2>LEVELS & BADGES</h2>
      </div>
      <div class="levels-grid">
        <div class="level-card l1">
          <div class="badge">🌟</div>
          <div class="lvl-label">LEVEL 1</div>
          <h3>Beginner</h3>
          <p>7 Questions · 1pt each · Max 7pts</p>
          <p style="margin-top:8px;font-size:11px;color:#10b981">STARTER BADGE</p>
        </div>
        <div class="level-card l2">
          <div class="badge">🔷</div>
          <div class="lvl-label">LEVEL 2</div>
          <h3>Intermediate</h3>
          <p>7 Questions · 2pts each · Max 14pts</p>
          <p style="margin-top:8px;font-size:11px;color:#3b82f6">EXPLORER BADGE</p>
        </div>
        <div class="level-card l3">
          <div class="badge">⚡</div>
          <div class="lvl-label">LEVEL 3</div>
          <h3>Advanced</h3>
          <p>7 Questions · 3pts each · Max 21pts</p>
          <p style="margin-top:8px;font-size:11px;color:#f59e0b">CHAMPION BADGE</p>
        </div>
        <div class="level-card l4">
          <div class="badge">🏆</div>
          <div class="lvl-label">LEVEL 4</div>
          <h3>Expert</h3>
          <p>4 Questions · 4pts each · Max 16pts</p>
          <p style="margin-top:8px;font-size:11px;color:#ef4444">MASTER BADGE</p>
        </div>
      </div>
      <button class="btn btn-primary" onclick="startQuiz()">▶ START QUIZ</button>
    </div>

  </div>

  <!-- ===== QUIZ SCREEN ===== -->
  <div id="screen-quiz" class="screen">
    <div id="quiz-question-area"></div>
  </div>

  <!-- ===== REFERENCE SCREEN ===== -->
  <div id="screen-reference" class="screen">
    <div class="card">
      <div class="section-title">
        <div class="kicker">Study Guide</div>
        <h2>INPUT vs OUTPUT DEVICES</h2>
      </div>
      <div class="ref-cols">
        <div class="ref-col input">
          <h3>INPUT DEVICES</h3>
          <ul>
            <li>Keyboard</li>
            <li>Mouse / Trackpad</li>
            <li>Scanner</li>
            <li>Microphone</li>
            <li>Webcam / Digital Camera</li>
            <li>RFID Reader</li>
            <li>Barcode Reader</li>
            <li>Fingerprint Scanner</li>
            <li>MIDI Controller</li>
            <li>Eye Tracker</li>
            <li>Graphics Tablet</li>
          </ul>
        </div>
        <div class="ref-col output">
          <h3>OUTPUT DEVICES</h3>
          <ul>
            <li>Monitor / Display</li>
            <li>Printer (2D)</li>
            <li>Plotter</li>
            <li>Speakers</li>
            <li>Projector</li>
            <li>Braille Display</li>
            <li>3D Printer</li>
            <li>Headphones</li>
            <li>Haptic Feedback</li>
            <li>VR Headset Display</li>
            <li>GPU (renders to display)</li>
          </ul>
        </div>
        <div class="ref-col both">
          <h3>BOTH (I/O)</h3>
          <ul>
            <li>Touchscreen</li>
            <li>NIC (Network Interface Card)</li>
            <li>Haptic Game Controller</li>
            <li>VR System (full)</li>
            <li>Modem / Router</li>
            <li>Smart Speakers (Alexa etc.)</li>
          </ul>
        </div>
      </div>
    </div>
  </div>

</div>

<script>
// ============================
//  DATA
// ============================
const questions = [
  // LEVEL 1
  { level:1, pts:1, q:"Which of the following is an INPUT device?", opts:["Monitor","Keyboard","Printer","Speaker"], correct:1,
    exp: {tick:"A keyboard is an input device because it sends data (keystrokes) INTO the computer for processing.", cross:"A monitor displays output; a printer and speaker also produce output. Only the keyboard sends data into the computer."} },
  { level:1, pts:1, q:"A computer monitor is best described as:", opts:["An input device","A storage device","An output device","A processing device"], correct:2,
    exp: {tick:"A monitor is an OUTPUT device — it displays processed information from the computer to the user.", cross:"Monitors don't send data INTO the computer (that's input), they DISPLAY results, making them output devices."} },
  { level:1, pts:1, q:"Which device allows you to capture a physical photo and send it to a computer?", opts:["Speaker","Scanner","Projector","Printer"], correct:1,
    exp: {tick:"A scanner converts physical documents or photos into digital data and sends them into the computer — it is an INPUT device.", cross:"Speakers and projectors are output devices. A printer outputs data onto paper. A scanner captures physical images as digital INPUT."} },
  { level:1, pts:1, q:"Which of these produces SOUND as output from a computer?", opts:["Microphone","Webcam","Speakers","Mouse"], correct:2,
    exp: {tick:"Speakers are output devices that convert electrical signals from the computer into sound waves we can hear.", cross:"A microphone captures sound as INPUT. A webcam captures images as INPUT. A mouse sends cursor movements as INPUT. Speakers produce sound OUTPUT."} },
  { level:1, pts:1, q:"What does a mouse do?", opts:["Displays images","Prints documents","Controls cursor movement on screen","Stores files permanently"], correct:2,
    exp: {tick:"A mouse is an input device that tracks movement and sends cursor position and click data into the computer.", cross:"Displaying images is a monitor's job; printing is a printer's job; storing files is a hard drive's job. The mouse only controls the cursor."} },
  { level:1, pts:1, q:"Which device would a visually impaired user use to read screen content aloud?", opts:["Microphone","Screen reader software with speakers","Scanner","Webcam"], correct:1,
    exp: {tick:"Screen reader software processes text on screen and outputs it as speech through speakers — this is an accessibility output solution.", cross:"A microphone captures voice input. A scanner captures physical documents. A webcam captures video. Speakers with screen reader software provide audio output of text."} },
  { level:1, pts:1, q:"A printer is classified as:", opts:["Input device","Processing device","Output device","Storage device"], correct:2,
    exp: {tick:"A printer receives processed data from the computer and produces a physical (hard copy) output on paper.", cross:"Input devices send data TO the computer. Processing happens in the CPU. Storage devices save data. Printers produce physical output — they are OUTPUT devices."} },

  // LEVEL 2
  { level:2, pts:2, q:"A touch screen on a smartphone acts as:", opts:["Only input","Only output","Both input and output","Neither input nor output"], correct:2,
    exp: {tick:"A touchscreen displays information (output) AND detects finger touches to send commands (input). It is a dual-purpose device.", cross:"Touchscreens are both! The screen itself shows visuals (output) while the touch-sensitive layer detects your finger position (input)."} },
  { level:2, pts:2, q:"Which of these is NOT an example of a pointing device?", opts:["Trackball","Graphics tablet","Joystick","Barcode reader"], correct:3,
    exp: {tick:"A barcode reader is a scanning/optical input device, NOT a pointing device. Pointing devices control cursor position on screen.", cross:"Trackballs, graphics tablets, and joysticks all control cursor movement (pointing devices). A barcode reader captures data by reading barcodes — a different input category."} },
  { level:2, pts:2, q:"What type of output does a plotter produce?", opts:["Sound output","Large-format precise line drawings and diagrams","3D printed objects","Digital image files"], correct:1,
    exp: {tick:"A plotter is a specialised output device that draws precise lines on large-format paper — used in engineering, architecture, and design.", cross:"Plotters are not speakers (no sound), not 3D printers (no objects), and not cameras (no files). They draw large vector graphics on paper."} },
  { level:2, pts:2, q:"Which input device converts spoken words into text on a computer?", opts:["Keyboard","Scanner","Microphone with speech recognition software","Webcam"], correct:2,
    exp: {tick:"A microphone captures voice input, and speech recognition software converts it into text — combining hardware and software input processing.", cross:"Keyboards input text manually. Scanners input images. Webcams input video. A microphone + speech recognition is the correct answer for voice-to-text input."} },
  { level:2, pts:2, q:"A digital camera connected to a computer is used as:", opts:["An output device","A processing device","An input device","A storage device only"], correct:2,
    exp: {tick:"When connected to a computer, a digital camera transfers photo/video data INTO the computer — functioning as an input device.", cross:"The camera outputs images to its own screen, but when connected to a computer it feeds data INTO it. In this context it acts as an input device."} },
  { level:2, pts:2, q:"What is the primary function of a GPU (Graphics Processing Unit) in relation to output?", opts:["It stores graphics files","It processes and renders images/video sent to the display","It captures screen images as input","It controls the printer"], correct:1,
    exp: {tick:"The GPU processes graphics data and sends rendered visuals to the monitor — it is critical for display output quality.", cross:"The GPU doesn't store files (that's a hard drive), capture images (that's a capture card/webcam), or control printers (that's the CPU/driver). It renders graphics for display output."} },
  { level:2, pts:2, q:"Braille displays are examples of:", opts:["Input devices for visually impaired users","Output devices for visually impaired users","Both input and output devices","Processing devices"], correct:1,
    exp: {tick:"Braille displays convert digital text into tactile Braille patterns that users can feel — they are specialised OUTPUT devices for visually impaired users.", cross:"Braille displays only produce output (tactile text). They don't send data into the computer. They are accessible output devices."} },

  // LEVEL 3
  { level:3, pts:3, q:"Which technology does an RFID reader use to read data from tags?", opts:["Laser light","Radio frequency electromagnetic fields","Infrared beams","Ultrasonic waves"], correct:1,
    exp: {tick:"RFID (Radio Frequency Identification) readers use radio frequency electromagnetic fields to wirelessly read data from RFID tags — used in access cards, inventory, and passports.", cross:"Lasers are used in barcode scanners. Infrared is used in remote controls. Ultrasound is used in sonar. RFID specifically uses radio frequency fields."} },
  { level:3, pts:3, q:"A haptic feedback controller (e.g., game controller with rumble) is classified as:", opts:["Input only","Output only","Both input and output","Storage device"], correct:2,
    exp: {tick:"A haptic controller sends button/joystick input to the computer AND receives vibration signals from the computer as tactile output. It is a bidirectional device.", cross:"Buttons and joysticks send input. Vibration motors produce tactile output. Modern game controllers do both simultaneously — they are input/output devices."} },
  { level:3, pts:3, q:"What distinguishes a capacitive touchscreen from a resistive touchscreen?", opts:["Capacitive requires a stylus; resistive detects any touch","Capacitive detects electrical conductivity; resistive detects physical pressure","Capacitive uses infrared; resistive uses cameras","They are functionally identical"], correct:1,
    exp: {tick:"Capacitive screens detect the electrical conductivity of fingers (or conductive stylus). Resistive screens detect physical pressure from any object. Capacitive screens are more sensitive and support multi-touch.", cross:"Capacitive screens work with fingers (not necessarily a stylus). Infrared and camera-based are different touchscreen technologies entirely."} },
  { level:3, pts:3, q:"In the context of OCR (Optical Character Recognition), the scanner acts as:", opts:["An output device converting digital text to physical print","An input device converting physical text to digital data","A processing device that interprets meaning","A storage device that saves original documents"], correct:1,
    exp: {tick:"OCR systems use a scanner (input) to capture an image of physical text, then software interprets (processes) the image to produce editable digital text.", cross:"The scanner is the INPUT stage — it captures the physical document. OCR software does the processing. The scanner itself doesn't output, process meaning, or store files."} },
  { level:3, pts:3, q:"Which output device is used to produce three-dimensional physical objects from digital designs?", opts:["Plotter","Laser printer","3D printer","CNC milling machine"], correct:2,
    exp: {tick:"A 3D printer is an additive manufacturing output device that builds three-dimensional objects layer by layer from digital design files.", cross:"Plotters produce 2D large-format drawings. Laser printers produce 2D paper output. CNC mills subtract material (subtractive) rather than adding it. Only 3D printers build 3D objects additively."} },
  { level:3, pts:3, q:"What is the role of a MIDI controller in a music studio setup?", opts:["It amplifies sound output from speakers","It stores audio files on disk","It sends musical note and control data into a computer as input","It processes digital audio into analogue signals"], correct:2,
    exp: {tick:"A MIDI controller is an input device that sends note, velocity, pitch, and control data into a computer/DAW, where software instruments generate the actual audio output.", cross:"Amplifiers handle audio output. Hard drives store files. DACs/audio interfaces process audio signals. MIDI controllers only generate digital control messages as INPUT."} },
  { level:3, pts:3, q:"Which input technology do most modern laptops use to replace a physical mouse?", opts:["Joystick","Trackpad (touchpad)","Graphics tablet","Optical encoder wheel"], correct:1,
    exp: {tick:"A trackpad (touchpad) is a touch-sensitive surface built into laptops that detects finger gestures and movement to control the cursor — replacing the external mouse.", cross:"Joysticks are used in gaming/aviation. Graphics tablets are used by designers. Optical encoder wheels are used in mice. The trackpad is the standard built-in laptop pointing device."} },

  // LEVEL 4
  { level:4, pts:4, q:"In biometric authentication systems, a fingerprint scanner functions as:", opts:["A storage device saving fingerprints to disk","A processing device that matches patterns","An input device that captures biometric data for verification","An output device displaying matched results"], correct:2,
    exp: {tick:"The fingerprint scanner captures biometric data (INPUT). The matching and verification is done by software (PROCESSING). The result is then displayed (OUTPUT). The scanner's role is specifically INPUT.", cross:"Storage, processing, and output are separate stages. The fingerprint scanner only captures the biometric data — it is the INPUT stage of the biometric system."} },
  { level:4, pts:4, q:"A VR headset with motion tracking and haptic gloves represents:", opts:["Pure input system","Pure output system","A closed-loop input/output system where user actions affect the virtual environment and vice versa","A processing-only system"], correct:2,
    exp: {tick:"VR systems are closed-loop I/O: motion sensors input position data, the headset outputs visuals and audio, haptic gloves output touch feedback AND input hand gestures — creating an immersive bidirectional loop.", cross:"VR is neither pure input nor pure output. The immersive experience requires constant bidirectional data flow — user movements as input, synthesised sensory experiences as output."} },
  { level:4, pts:4, q:"Which of the following BEST explains why a network interface card (NIC) can be considered both an input and output device?", opts:["It stores both incoming and outgoing data packets","It receives incoming data (input) and transmits outgoing data (output) over a network","It processes data before sending it to the CPU","It only functions as output when uploading files"], correct:1,
    exp: {tick:"A NIC receives data packets from the network (input to the computer) and transmits data packets to the network (output from the computer) — making it a full-duplex input/output device.", cross:"NICs don't store data (that's RAM/HDD), and while they have some processing circuitry, their primary I/O role is bidirectional data communication over the network."} },
  { level:4, pts:4, q:"In an eye-tracking system used for accessibility (allowing paralysed users to control a computer), the eye tracker functions as:", opts:["An output device displaying where the user looks","An input device that converts gaze direction into cursor control signals","A processing device interpreting brain signals","A storage device recording eye movements"], correct:1,
    exp: {tick:"An eye tracker uses cameras and infrared to detect gaze direction, converting it into cursor control signals sent INTO the computer — it is a specialised INPUT device enabling hands-free computer control.", cross:"The eye tracker doesn't display anything, interpret brain signals, or store eye movements as its primary function. It feeds gaze coordinates into the computer as an innovative INPUT device."} },
];

const levelInfo = {
  1: { label:"LEVEL 1 — BEGINNER", cls:"l1", badge:"🌟", badgeLabel:"STARTER BADGE", color:"var(--lvl1)", range:[0,6] },
  2: { label:"LEVEL 2 — INTERMEDIATE", cls:"l2", badge:"🔷", badgeLabel:"EXPLORER BADGE", color:"var(--lvl2)", range:[7,13] },
  3: { label:"LEVEL 3 — ADVANCED", cls:"l3", badge:"⚡", badgeLabel:"CHAMPION BADGE", color:"var(--lvl3)", range:[14,20] },
  4: { label:"LEVEL 4 — EXPERT", cls:"l4", badge:"🏆", badgeLabel:"MASTER BADGE", color:"var(--lvl4)", range:[21,24] },
};

// State
let currentQ = 0;
let totalScore = 0;
let levelScores = {1:0, 2:0, 3:0, 4:0};
let answered = false;
let quizStarted = false;

// ============================
//  NAV
// ============================
function showScreen(name) {
  document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
  document.querySelectorAll('.nav-tab').forEach(t => t.classList.remove('active'));
  document.getElementById('screen-' + name).classList.add('active');
  const tabs = document.querySelectorAll('.nav-tab');
  const map = { home: 0, quiz: 1, reference: 2 };
  if (map[name] !== undefined) tabs[map[name]].classList.add('active');
  if (name === 'quiz' && !quizStarted) renderHome();
  else if (name === 'quiz') renderQuestion();
}

function renderHome() {
  // Just show the home screen via the quiz tab — redirect to quiz screen
  document.getElementById('quiz-question-area').innerHTML = `
    <div class="card" style="text-align:center">
      <div style="font-size:60px;margin-bottom:16px">🎮</div>
      <h2 style="font-family:'Orbitron',monospace;font-size:24px;margin-bottom:12px;color:#fff">Ready to start?</h2>
      <p style="color:var(--muted);margin-bottom:24px">Test your knowledge of Input & Output Devices across 4 levels!</p>
      <button class="btn btn-primary" onclick="startQuiz()">▶ START QUIZ</button>
    </div>`;
}

// ============================
//  QUIZ LOGIC
// ============================
function startQuiz() {
  currentQ = 0;
  totalScore = 0;
  levelScores = {1:0,2:0,3:0,4:0};
  answered = false;
  quizStarted = true;
  showScreen('quiz');
  renderQuestion();
}

function renderQuestion() {
  if (currentQ >= questions.length) { showFinalResults(); return; }

  const q = questions[currentQ];
  const li = levelInfo[q.level];
  const progress = ((currentQ) / questions.length) * 100;
  const qNum = currentQ + 1;

  // Check if this is the start of a new level (and not q0)
  const prevLevel = currentQ > 0 ? questions[currentQ-1].level : 0;
  if (q.level > prevLevel && currentQ > 0) {
    showLevelComplete(prevLevel);
    return;
  }

  const stars = '⭐'.repeat(q.pts);
  const optLetters = ['A','B','C','D'];

  document.getElementById('quiz-question-area').innerHTML = `
    <div class="top-score-bar animate-in">
      <div class="ts-item">📊 Question <strong>${qNum} / ${questions.length}</strong></div>
      <div class="divider"></div>
      <div class="ts-item">Score <strong style="color:var(--gold)">${totalScore} pts</strong></div>
      <div class="divider"></div>
      <div class="ts-item">Level <strong>${q.level} / 4</strong></div>
    </div>

    <div class="progress-bar-wrap">
      <div class="progress-bar-fill" style="width:${progress}%"></div>
    </div>

    <div class="card animate-in">
      <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:16px;flex-wrap:wrap;gap:8px">
        <span class="quiz-level-badge ${li.cls}">${li.label}</span>
        <span class="pts-badge">${stars} ${q.pts} pt${q.pts>1?'s':''}</span>
      </div>
      <div class="question-number">QUESTION ${qNum} OF ${questions.length}</div>
      <div class="question-text">${q.q}</div>
      <div class="options" id="options-wrap">
        ${q.opts.map((opt,i) => `
          <button class="option-btn" onclick="selectAnswer(${i})" id="opt-${i}">
            <span class="opt-letter">${optLetters[i]}</span>
            <span>${opt}</span>
          </button>
        `).join('')}
      </div>
      <div class="explanation-box" id="explanation-box"></div>
      <div id="next-btn-wrap"></div>
      <p class="hint-text" id="hint-text">Select the correct answer above</p>
    </div>`;
}

function selectAnswer(chosen) {
  if (answered) return;
  answered = true;

  const q = questions[currentQ];
  const isCorrect = chosen === q.correct;
  const optLetters = ['A','B','C','D'];

  // Style buttons
  for (let i = 0; i < q.opts.length; i++) {
    const btn = document.getElementById('opt-' + i);
    btn.disabled = true;
    if (i === q.correct) btn.classList.add('correct');
    else if (i === chosen && !isCorrect) btn.classList.add('wrong');
  }

  // Score
  if (isCorrect) {
    totalScore += q.pts;
    levelScores[q.level] = (levelScores[q.level] || 0) + q.pts;
  }

  // Explanation
  const expBox = document.getElementById('explanation-box');
  expBox.classList.add('show');
  expBox.innerHTML = `
    <div class="exp-header">💡 EXPLANATION</div>
    ${isCorrect ? `<div class="pts-earned">+${q.pts} PT${q.pts>1?'S':''} EARNED! 🎉</div>` : `<div style="color:var(--red);font-weight:700;margin-bottom:8px">✗ Incorrect — Correct answer: ${optLetters[q.correct]}) ${q.opts[q.correct]}</div>`}
    <div class="exp-text">
      <span class="tick">✔</span> ${q.exp.tick}<br><br>
      <span class="cross">✘</span> ${q.exp.cross}
    </div>`;

  document.getElementById('hint-text').style.display = 'none';

  // Next button
  const nextWrap = document.getElementById('next-btn-wrap');
  nextWrap.style.marginTop = '16px';
  const isLastInLevel = currentQ === questions.length - 1 || questions[currentQ+1].level > q.level;
  nextWrap.innerHTML = `<button class="btn btn-primary" onclick="nextQuestion()">${isLastInLevel ? (currentQ === questions.length-1 ? '🏆 See Final Results' : `✅ Complete Level ${q.level}`) : '▶ Next Question'}</button>`;
}

function nextQuestion() {
  answered = false;
  currentQ++;
  renderQuestion();
}

function showLevelComplete(level) {
  const li = levelInfo[level];
  const pts = levelScores[level] || 0;
  const maxPts = level === 4 ? 16 : 7 * level; // approximate
  const actualMax = questions.filter(q=>q.level===level).reduce((a,q)=>a+q.pts,0);

  document.getElementById('quiz-question-area').innerHTML = `
    <div class="card level-complete-screen animate-in">
      <div class="level-complete-icon">${li.badge}</div>
      <h2>LEVEL ${level} COMPLETE!</h2>
      <div class="badge-earned">${li.badge} ${li.badgeLabel}</div>
      <div class="pts-summary">${pts} / ${actualMax} pts</div>
      <div class="pts-summary-label">Level ${level} Score</div>
      <div style="margin-bottom:24px;color:var(--muted);font-size:14px">Total score so far: <strong style="color:var(--gold)">${totalScore} pts</strong></div>
      <button class="btn btn-primary" onclick="continueToNextLevel(${level+1})">▶ Continue to Level ${level+1}</button>
    </div>`;
}

function continueToNextLevel(level) {
  answered = false;
  renderQuestion();
}

function showFinalResults() {
  const l1max = questions.filter(q=>q.level===1).reduce((a,q)=>a+q.pts,0);
  const l2max = questions.filter(q=>q.level===2).reduce((a,q)=>a+q.pts,0);
  const l3max = questions.filter(q=>q.level===3).reduce((a,q)=>a+q.pts,0);
  const l4max = questions.filter(q=>q.level===4).reduce((a,q)=>a+q.pts,0);

  document.getElementById('quiz-question-area').innerHTML = `
    <div class="card final-screen animate-in">
      <div class="final-trophy">🏆</div>
      <h2>FINAL RESULTS</h2>
      <p style="color:var(--muted);margin-bottom:24px">You've completed all 4 levels!</p>

      <div class="score-breakdown">
        <div class="score-row">
          <span class="sr-label">🌟 Level 1 — Beginner (7 × 1pt)</span>
          <span class="sr-pts">${levelScores[1]} / ${l1max} pts</span>
        </div>
        <div class="score-row">
          <span class="sr-label">🔷 Level 2 — Intermediate (7 × 2pts)</span>
          <span class="sr-pts">${levelScores[2]} / ${l2max} pts</span>
        </div>
        <div class="score-row">
          <span class="sr-label">⚡ Level 3 — Advanced (7 × 3pts)</span>
          <span class="sr-pts">${levelScores[3]} / ${l3max} pts</span>
        </div>
        <div class="score-row">
          <span class="sr-label">🏆 Level 4 — Expert (4 × 4pts)</span>
          <span class="sr-pts">${levelScores[4]} / ${l4max} pts</span>
        </div>
        <div class="score-row total">
          <span class="sr-label">TOTAL SCORE</span>
          <span class="sr-pts">${totalScore} / 63 pts</span>
        </div>
      </div>

      <div class="badges-row">
        <span>🌟 Starter</span>
        <span>🔷 Explorer</span>
        <span>⚡ Champion</span>
        <span>🏆 Master</span>
      </div>

      <p style="color:var(--muted);margin-bottom:20px;font-size:14px">
        ${totalScore === 63 ? '🎉 PERFECT SCORE! You are a true I/O Master!' : totalScore >= 50 ? '🔥 Excellent work! Nearly perfect!' : totalScore >= 35 ? '👍 Great job! Keep studying to hit that perfect score.' : '📚 Good effort! Review the Reference guide and try again.'}
      </p>

      <button class="btn btn-primary" onclick="startQuiz()" style="margin-bottom:10px">🔄 Play Again</button>
      <button class="btn btn-secondary" onclick="showScreen('reference')">📋 View Reference Guide</button>
    </div>`;
}
</script>
</body>
</html>
