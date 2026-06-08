<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>PM Radar — Monisha Sood</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
:root {
  --white: #ffffff; --off-white: #f7f6f3; --paper: #fafaf8;
  --ink: #0f0f0e; --ink-2: #2d2d2b; --ink-3: #5a5a57; --ink-4: #9b9b97; --ink-5: #c8c8c4; --ink-6: #e8e8e4;
  --rule: #e4e4e0;
  --accent: #1a6b3c; --accent-light: #e8f4ed; --accent-mid: #2d8a52;
  --amber: #b45309; --amber-light: #fef3c7;
  --red: #b91c1c; --red-light: #fee2e2;
  --blue: #1d4ed8; --blue-light: #eff6ff;
  --shadow-sm: 0 1px 3px rgba(0,0,0,.06), 0 1px 2px rgba(0,0,0,.04);
  --shadow-md: 0 4px 12px rgba(0,0,0,.08);
  --r: 10px; --r-sm: 6px;
}
html, body { height: 100%; overflow: hidden; }
body { font-family: 'Plus Jakarta Sans', system-ui, sans-serif; background: var(--paper); color: var(--ink); display: flex; flex-direction: column; font-size: 14px; }

/* TOPBAR */
.topbar { background: var(--white); border-bottom: 1px solid var(--rule); padding: 0 24px; height: 52px; display: flex; align-items: center; justify-content: space-between; flex-shrink: 0; box-shadow: var(--shadow-sm); z-index: 10; }
.brand { display: flex; align-items: center; gap: 12px; }
.brand-mark { width: 30px; height: 30px; background: var(--ink); border-radius: 7px; display: flex; align-items: center; justify-content: center; font-size: 14px; flex-shrink: 0; }
.brand-name { font-family: 'Instrument Serif', serif; font-size: 16px; color: var(--ink); }
.brand-div { width: 1px; height: 16px; background: var(--rule); }
.brand-sub { font-size: 12px; color: var(--ink-4); }
.topbar-right { display: flex; align-items: center; gap: 8px; }
.live-badge { display: flex; align-items: center; gap: 5px; padding: 4px 10px; background: var(--accent-light); border-radius: 20px; font-size: 11px; font-weight: 600; color: var(--accent); }
.live-dot { width: 6px; height: 6px; border-radius: 50%; background: var(--accent-mid); animation: pulse 2.5s ease-in-out infinite; }
@keyframes pulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:.5;transform:scale(.85)} }

/* BUTTONS */
.btn { display: inline-flex; align-items: center; gap: 6px; padding: 7px 14px; border-radius: var(--r-sm); border: none; cursor: pointer; font-family: 'Plus Jakarta Sans', sans-serif; font-size: 13px; font-weight: 600; line-height: 1; transition: all .15s; white-space: nowrap; }
.btn:disabled { opacity: .45; cursor: not-allowed; transform: none !important; }
.btn-primary { background: var(--ink); color: white; }
.btn-primary:hover:not(:disabled) { background: var(--ink-2); transform: translateY(-1px); box-shadow: var(--shadow-sm); }
.btn-secondary { background: var(--white); color: var(--ink); border: 1px solid var(--rule); box-shadow: var(--shadow-sm); }
.btn-secondary:hover:not(:disabled) { border-color: var(--ink-4); background: var(--off-white); }
.btn-accent { background: var(--accent); color: white; }
.btn-accent:hover:not(:disabled) { background: var(--accent-mid); transform: translateY(-1px); }
.btn-ghost { background: transparent; color: var(--ink-3); border: 1px solid transparent; }
.btn-ghost:hover { background: var(--off-white); color: var(--ink); }
.btn-sm { padding: 5px 10px; font-size: 12px; }
.btn-lg { padding: 10px 18px; font-size: 13px; }

/* LAYOUT */
.workspace { display: grid; grid-template-columns: 340px 1fr; flex: 1; min-height: 0; }

/* LEFT PANEL */
.left-panel { background: var(--white); border-right: 1px solid var(--rule); display: flex; flex-direction: column; min-height: 0; overflow: hidden; }
.panel-head { padding: 14px 18px 12px; border-bottom: 1px solid var(--rule); flex-shrink: 0; }
.panel-head-top { display: flex; align-items: center; justify-content: space-between; margin-bottom: 10px; }
.panel-title { font-size: 13px; font-weight: 700; display: flex; align-items: center; gap: 7px; }
.count-chip { background: var(--ink); color: white; font-size: 10px; font-weight: 700; padding: 2px 7px; border-radius: 10px; font-family: 'JetBrains Mono', monospace; }
.new-chip { background: var(--accent-light); color: var(--accent); font-size: 10px; font-weight: 700; padding: 2px 8px; border-radius: 10px; }
.search-wrap { position: relative; margin-bottom: 10px; }
.search-icon { position: absolute; left: 10px; top: 50%; transform: translateY(-50%); color: var(--ink-4); font-size: 13px; pointer-events: none; }
.search-input { width: 100%; padding: 8px 10px 8px 30px; background: var(--off-white); border: 1px solid var(--rule); border-radius: var(--r-sm); font-family: 'Plus Jakarta Sans', sans-serif; font-size: 13px; color: var(--ink); outline: none; transition: all .15s; }
.search-input:focus { border-color: var(--ink-3); background: var(--white); box-shadow: 0 0 0 3px rgba(15,15,14,.06); }
.search-input::placeholder { color: var(--ink-5); }
.filters { display: flex; gap: 5px; flex-wrap: wrap; }
.fpill { padding: 4px 10px; border-radius: 20px; border: 1px solid var(--rule); background: transparent; color: var(--ink-3); font-size: 11px; font-weight: 500; cursor: pointer; font-family: 'Plus Jakarta Sans', sans-serif; transition: all .12s; white-space: nowrap; }
.fpill:hover { border-color: var(--ink-3); color: var(--ink); }
.fpill.on { background: var(--ink); border-color: var(--ink); color: white; }

/* JOB LIST — KEY: overflow-y here */
.job-list { flex: 1; overflow-y: auto; min-height: 0; scrollbar-width: thin; scrollbar-color: var(--ink-6) transparent; }
.job-item { padding: 13px 18px; border-bottom: 1px solid var(--rule); cursor: pointer; transition: background .1s; border-left: 3px solid transparent; }
.job-item:hover { background: var(--off-white); }
.job-item.active { background: var(--off-white); border-left-color: var(--ink); }
.job-item-top { display: flex; justify-content: space-between; align-items: flex-start; gap: 8px; margin-bottom: 3px; }
.job-item-title { font-size: 13px; font-weight: 600; color: var(--ink); line-height: 1.35; flex: 1; }
.job-item-time { font-size: 10px; color: var(--ink-4); font-family: 'JetBrains Mono', monospace; white-space: nowrap; flex-shrink: 0; margin-top: 2px; }
.job-item-co { font-size: 12px; color: var(--ink-3); margin-bottom: 7px; }
.job-item-pills { display: flex; gap: 4px; flex-wrap: wrap; }
.pill { display: inline-flex; align-items: center; padding: 2px 7px; border-radius: 4px; font-size: 10px; font-weight: 600; letter-spacing: .2px; font-family: 'JetBrains Mono', monospace; }
.p-new { background: var(--accent-light); color: var(--accent); }
.p-remote { background: var(--blue-light); color: var(--blue); }
.p-sponsor { background: var(--amber-light); color: var(--amber); }
.p-nosponsor { background: var(--red-light); color: var(--red); }
.p-match { background: var(--off-white); color: var(--ink-3); border: 1px solid var(--rule); }
.p-tag { background: var(--off-white); color: var(--ink-4); border: 1px solid var(--rule); }

/* RIGHT PANEL */
.right-panel { display: flex; flex-direction: column; min-height: 0; overflow: hidden; background: var(--paper); }
.tab-bar { background: var(--white); border-bottom: 1px solid var(--rule); padding: 0 24px; display: flex; align-items: center; flex-shrink: 0; }
.tab { padding: 15px 4px; margin-right: 22px; font-size: 13px; font-weight: 500; color: var(--ink-3); cursor: pointer; border-bottom: 2px solid transparent; transition: all .15s; white-space: nowrap; }
.tab:hover { color: var(--ink); }
.tab.active { color: var(--ink); font-weight: 700; border-bottom-color: var(--ink); }

/* CONTENT — scrollable */
.content { flex: 1; overflow-y: auto; min-height: 0; scrollbar-width: thin; scrollbar-color: var(--ink-6) transparent; }
.tab-pane { display: none; }
.tab-pane.active { display: block; }

/* ACTION BAR — always visible */
.action-bar { background: var(--white); border-top: 1px solid var(--rule); padding: 12px 24px; display: flex; align-items: center; gap: 10px; flex-shrink: 0; box-shadow: 0 -2px 8px rgba(0,0,0,.04); }
.action-hint { font-size: 12px; color: var(--ink-4); }
.action-spacer { flex: 1; }

/* EMPTY STATE */
.empty { display: flex; flex-direction: column; align-items: center; justify-content: center; min-height: 360px; gap: 10px; padding: 40px; }
.empty-icon { font-size: 32px; opacity: .18; }
.empty-title { font-size: 15px; font-weight: 600; color: var(--ink-3); }
.empty-sub { font-size: 13px; color: var(--ink-4); text-align: center; line-height: 1.55; max-width: 380px; }

/* DETAIL */
.detail-wrap { padding: 24px 28px; max-width: 820px; }
.eyebrow { font-family: 'JetBrains Mono', monospace; font-size: 10px; font-weight: 500; color: var(--ink-4); letter-spacing: .8px; text-transform: uppercase; margin-bottom: 8px; }
.detail-title { font-family: 'Instrument Serif', serif; font-size: 24px; color: var(--ink); line-height: 1.2; letter-spacing: -.3px; margin-bottom: 5px; }
.detail-company { font-size: 14px; color: var(--ink-3); margin-bottom: 14px; }
.detail-pills { display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 20px; }
.match-card { background: var(--white); border: 1px solid var(--rule); border-radius: var(--r); padding: 16px 18px; margin-bottom: 22px; box-shadow: var(--shadow-sm); }
.match-card-top { display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px; }
.match-lbl { font-size: 10px; font-family: 'JetBrains Mono', monospace; color: var(--ink-4); text-transform: uppercase; letter-spacing: .8px; }
.match-num { font-family: 'Instrument Serif', serif; font-size: 26px; color: var(--accent); line-height: 1; }
.match-track { height: 3px; background: var(--rule); border-radius: 2px; overflow: hidden; margin-bottom: 10px; }
.match-fill { height: 100%; background: linear-gradient(90deg, var(--accent), var(--accent-mid)); border-radius: 2px; transition: width .9s cubic-bezier(.4,0,.2,1); }
.match-skills { display: flex; gap: 5px; flex-wrap: wrap; }
.mskill { padding: 3px 8px; border-radius: 4px; font-size: 11px; font-weight: 500; background: var(--accent-light); color: var(--accent); }
.section { margin-bottom: 22px; }
.section-title { font-size: 10px; font-family: 'JetBrains Mono', monospace; color: var(--ink-4); text-transform: uppercase; letter-spacing: .8px; margin-bottom: 8px; padding-bottom: 7px; border-bottom: 1px solid var(--rule); }
.section-body { font-size: 13.5px; color: var(--ink-2); line-height: 1.75; }
.req-list { list-style: none; }
.req-list li { display: flex; gap: 10px; align-items: flex-start; padding: 4px 0; font-size: 13px; color: var(--ink-2); line-height: 1.5; }
.req-list li::before { content: "–"; color: var(--ink-4); flex-shrink: 0; }

/* CV / COVER OUTPUT */
.output-wrap { padding: 24px 28px; max-width: 820px; }
.output-head { display: flex; align-items: flex-start; justify-content: space-between; margin-bottom: 18px; gap: 12px; }
.output-title { font-family: 'Instrument Serif', serif; font-size: 20px; color: var(--ink); margin-bottom: 3px; }
.output-sub { font-size: 12px; color: var(--ink-4); }
.output-box { background: var(--white); border: 1px solid var(--rule); border-radius: var(--r); box-shadow: var(--shadow-sm); overflow: hidden; }
.output-box-head { padding: 10px 16px; border-bottom: 1px solid var(--rule); background: var(--off-white); display: flex; align-items: center; justify-content: space-between; }
.output-box-lbl { font-size: 10px; font-family: 'JetBrains Mono', monospace; color: var(--ink-4); text-transform: uppercase; letter-spacing: .6px; }
.copy-btn { padding: 4px 10px; background: var(--white); border: 1px solid var(--rule); border-radius: 4px; font-size: 11px; cursor: pointer; font-family: 'Plus Jakarta Sans', sans-serif; font-weight: 600; color: var(--ink-3); transition: all .12s; }
.copy-btn:hover { border-color: var(--ink-3); color: var(--ink); }
.output-body { padding: 18px 20px; font-family: 'JetBrains Mono', monospace; font-size: 12px; line-height: 1.85; color: var(--ink-2); white-space: pre-wrap; min-height: 80px; }
.output-loading { display: flex; align-items: center; justify-content: center; gap: 10px; min-height: 160px; color: var(--ink-4); font-size: 13px; }
.spinner { width: 18px; height: 18px; border: 2px solid var(--rule); border-top-color: var(--ink-3); border-radius: 50%; animation: spin .7s linear infinite; flex-shrink: 0; }
@keyframes spin { to { transform: rotate(360deg); } }
.cursor { display: inline-block; width: 2px; height: 12px; background: var(--ink-3); margin-left: 1px; vertical-align: text-bottom; animation: blink .65s step-end infinite; }
@keyframes blink { 50% { opacity: 0; } }

/* MY CV TAB */
.mycv-wrap { padding: 24px 28px; max-width: 820px; }
.mycv-title { font-family: 'Instrument Serif', serif; font-size: 22px; color: var(--ink); margin-bottom: 6px; }
.mycv-sub { font-size: 13px; color: var(--ink-3); line-height: 1.6; margin-bottom: 22px; }
.mycv-box { background: var(--white); border: 1px solid var(--rule); border-radius: var(--r); box-shadow: var(--shadow-sm); overflow: hidden; margin-bottom: 16px; }
.mycv-box-head { padding: 11px 16px; border-bottom: 1px solid var(--rule); background: var(--off-white); display: flex; align-items: center; justify-content: space-between; }
.mycv-box-lbl { font-size: 11px; font-family: 'JetBrains Mono', monospace; color: var(--ink-3); font-weight: 600; text-transform: uppercase; letter-spacing: .5px; }
.cv-textarea { width: 100%; padding: 16px 18px; font-family: 'JetBrains Mono', monospace; font-size: 12px; line-height: 1.85; color: var(--ink-2); background: var(--white); border: none; outline: none; resize: vertical; min-height: 400px; }
.cv-textarea::placeholder { color: var(--ink-5); font-family: 'Plus Jakarta Sans', sans-serif; font-size: 13px; line-height: 1.6; }
.mycv-note { font-size: 12px; color: var(--ink-4); line-height: 1.6; display: flex; gap: 8px; align-items: flex-start; padding: 12px 14px; background: var(--off-white); border: 1px solid var(--rule); border-radius: var(--r-sm); }
.mycv-note-icon { flex-shrink: 0; margin-top: 1px; }
.save-indicator { font-size: 11px; color: var(--accent); font-weight: 600; display: none; }
.save-indicator.show { display: inline; }

/* SETUP */
.setup-wrap { padding: 24px 28px; max-width: 680px; }
.setup-title { font-family: 'Instrument Serif', serif; font-size: 22px; color: var(--ink); margin-bottom: 5px; }
.setup-sub { font-size: 13px; color: var(--ink-3); line-height: 1.6; margin-bottom: 24px; }
.setup-sec { margin-bottom: 22px; }
.setup-sec-title { font-size: 10px; font-family: 'JetBrains Mono', monospace; color: var(--ink-4); text-transform: uppercase; letter-spacing: .8px; margin-bottom: 8px; }
.cfg-table { background: var(--white); border: 1px solid var(--rule); border-radius: var(--r); overflow: hidden; box-shadow: var(--shadow-sm); }
.cfg-row { display: flex; align-items: center; justify-content: space-between; padding: 12px 16px; border-bottom: 1px solid var(--rule); gap: 14px; }
.cfg-row:last-child { border-bottom: none; }
.cfg-key { font-size: 13px; color: var(--ink-2); font-weight: 500; }
.cfg-val { font-size: 12px; color: var(--ink-3); font-family: 'JetBrains Mono', monospace; }
.cfg-right { display: flex; align-items: center; gap: 8px; }
.dot-green { width: 7px; height: 7px; border-radius: 50%; background: var(--accent-mid); flex-shrink: 0; }
.dot-amber { width: 7px; height: 7px; border-radius: 50%; background: #f59e0b; flex-shrink: 0; }
.toggle { position: relative; width: 32px; height: 18px; background: var(--ink-6); border-radius: 9px; cursor: pointer; transition: background .2s; flex-shrink: 0; }
.toggle.on { background: var(--ink); }
.toggle::after { content:''; position: absolute; top: 2px; left: 2px; width: 14px; height: 14px; background: white; border-radius: 50%; transition: left .2s; box-shadow: 0 1px 3px rgba(0,0,0,.2); }
.toggle.on::after { left: 16px; }
.step-row { display: flex; gap: 12px; align-items: flex-start; padding: 12px 16px; border-bottom: 1px solid var(--rule); background: var(--white); }
.step-row:first-child { border-radius: var(--r) var(--r) 0 0; }
.step-row:last-child { border-bottom: none; border-radius: 0 0 var(--r) var(--r); }
.step-num { width: 20px; height: 20px; background: var(--ink); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 10px; font-weight: 700; flex-shrink: 0; margin-top: 2px; }
.step-text { font-size: 13px; color: var(--ink-2); line-height: 1.55; }
.step-text strong { color: var(--ink); font-weight: 600; }

/* LIST LOADING */
.list-loading { display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 50px 20px; gap: 10px; }
.list-loading-text { font-size: 13px; color: var(--ink-4); }

::-webkit-scrollbar { width: 4px; height: 4px; }
::-webkit-scrollbar-track { background: transparent; }
::-webkit-scrollbar-thumb { background: var(--ink-6); border-radius: 2px; }
::-webkit-scrollbar-thumb:hover { background: var(--ink-5); }
</style>
</head>
<body>

<!-- TOPBAR -->
<header class="topbar">
  <div class="brand">
    <div class="brand-mark">🎯</div>
    <div class="brand-name">PM Radar</div>
    <div class="brand-div"></div>
    <div class="brand-sub">Monisha Sood — First-to-Apply Engine</div>
  </div>
  <div class="topbar-right">
    <div class="live-badge"><div class="live-dot"></div>LIVE · 4 boards</div>
    <button class="btn btn-secondary btn-sm" onclick="refreshJobs()">↻ Refresh</button>
  </div>
</header>

<!-- WORKSPACE -->
<div class="workspace">

  <!-- LEFT -->
  <aside class="left-panel">
    <div class="panel-head">
      <div class="panel-head-top">
        <div class="panel-title">
          Open Roles
          <span class="count-chip" id="job-count">—</span>
          <span class="new-chip" id="new-chip">loading…</span>
        </div>
      </div>
      <div class="search-wrap">
        <span class="search-icon">⌕</span>
        <input class="search-input" placeholder="Search title, company, keyword…" id="search-input" oninput="filterJobs()">
      </div>
      <div class="filters">
        <button class="fpill on" onclick="setFilter('all',this)">All</button>
        <button class="fpill" onclick="setFilter('new',this)">New today</button>
        <button class="fpill" onclick="setFilter('nyc',this)">New York</button>
        <button class="fpill" onclick="setFilter('remote',this)">Remote</button>
        <button class="fpill" onclick="setFilter('ai',this)">AI roles</button>
      </div>
    </div>
    <div class="job-list" id="job-list">
      <div class="list-loading">
        <div class="spinner"></div>
        <div class="list-loading-text">Scanning Dice, Indeed, LinkedIn…</div>
      </div>
    </div>
  </aside>

  <!-- RIGHT -->
  <main class="right-panel">
    <nav class="tab-bar">
      <div class="tab active" data-tab="detail" onclick="switchTab('detail',this)">Job Details</div>
      <div class="tab" data-tab="cv" onclick="switchTab('cv',this)">Tailored CV</div>
      <div class="tab" data-tab="cover" onclick="switchTab('cover',this)">Cover Letter</div>
      <div class="tab" data-tab="mycv" onclick="switchTab('mycv',this)">My CV ✏️</div>
      <div class="tab" data-tab="setup" onclick="switchTab('setup',this)">⚡ Setup</div>
    </nav>

    <div class="content">

      <!-- DETAIL PANE -->
      <div class="tab-pane active" id="pane-detail">
        <div class="empty" id="detail-empty">
          <div class="empty-icon">←</div>
          <div class="empty-title">Select a role to get started</div>
          <div class="empty-sub">Pick any job from the list on the left. Then use the action bar below to generate a tailored CV or cover letter.</div>
        </div>
        <div class="detail-wrap" id="detail-content" style="display:none"></div>
      </div>

      <!-- CV PANE -->
      <div class="tab-pane" id="pane-cv">
        <div class="empty" id="cv-empty">
          <div class="empty-icon">📄</div>
          <div class="empty-title">No CV generated yet</div>
          <div class="empty-sub">Select a role from the left, then click <strong>Generate CV</strong> below to get a tailored, ATS-optimised resume in under 30 seconds.</div>
        </div>
        <div class="output-wrap" id="cv-content" style="display:none"></div>
      </div>

      <!-- COVER PANE -->
      <div class="tab-pane" id="pane-cover">
        <div class="empty" id="cover-empty">
          <div class="empty-icon">✉️</div>
          <div class="empty-title">No cover letter yet</div>
          <div class="empty-sub">Select a role, then click <strong>Generate Cover Letter</strong> below to get a tailored letter in your voice.</div>
        </div>
        <div class="output-wrap" id="cover-content" style="display:none"></div>
      </div>

      <!-- MY CV PANE -->
      <div class="tab-pane" id="pane-mycv">
        <div class="mycv-wrap">
          <div class="mycv-title">My Base CV</div>
          <div class="mycv-sub">Paste your current resume here. When you generate a tailored CV, the AI will edit this exact document — keeping your words and structure, and adapting it for the selected role.</div>

          <div class="mycv-box">
            <div class="mycv-box-head">
              <div class="mycv-box-lbl">Your Resume (plain text)</div>
              <div style="display:flex;align-items:center;gap:10px">
                <span class="save-indicator" id="save-indicator">✓ Saved</span>
                <button class="btn btn-secondary btn-sm" onclick="clearCV()">Clear</button>
                <button class="btn btn-primary btn-sm" onclick="saveCV()">Save CV</button>
              </div>
            </div>
            <textarea class="cv-textarea" id="cv-textarea" placeholder="Paste your resume here in plain text…

Example:
MONISHA SOOD
Product Manager | New York, NY

EXPERIENCE

SecondWind Pro — Product Manager
Jan 2023 – Present
• Built zero-to-one NIL analytics platform for D1 athletes
• Onboarded 500+ athletes across 40% of partner schools
...

(The AI will edit this document when you generate a tailored CV for a role)"
              oninput="autosaveCV()"></textarea>
          </div>

          <div class="mycv-note">
            <span class="mycv-note-icon">ℹ️</span>
            <span>Your CV is saved in your browser's local storage. It stays here between sessions. When you generate a tailored CV for a role, the AI edits <em>this document</em> — not a generic template — so your real voice and formatting is preserved.</span>
          </div>
        </div>
      </div>

      <!-- SETUP PANE -->
      <div class="tab-pane" id="pane-setup">
        <div class="setup-wrap">
          <div class="setup-title">Automation Setup</div>
          <div class="setup-sub">Your end-to-end system for being the first applicant on every PM role that matches your profile.</div>

          <div class="setup-sec">
            <div class="setup-sec-title">How it works</div>
            <div class="cfg-table">
              <div class="step-row"><div class="step-num">1</div><div class="step-text"><strong>Radar scans</strong> Indeed, Dice, LinkedIn, and Wellfound every 30 minutes for new PM roles</div></div>
              <div class="step-row"><div class="step-num">2</div><div class="step-text"><strong>Smart filters</strong> surface only roles matching your seniority, industry, and H-1B eligibility</div></div>
              <div class="step-row"><div class="step-num">3</div><div class="step-text"><strong>Gmail alert</strong> lands in your inbox the moment a strong match is posted</div></div>
              <div class="step-row"><div class="step-num">4</div><div class="step-text"><strong>Open this dashboard</strong>, select the role, generate tailored CV + cover letter in under 60 seconds</div></div>
              <div class="step-row"><div class="step-num">5</div><div class="step-text"><strong>Apply immediately</strong> — most candidates haven't seen the posting yet</div></div>
            </div>
          </div>

          <div class="setup-sec">
            <div class="setup-sec-title">Search filters</div>
            <div class="cfg-table">
              <div class="cfg-row"><div class="cfg-key">Location</div><div class="cfg-val">United States (all)</div></div>
              <div class="cfg-row"><div class="cfg-key">Keywords</div><div class="cfg-val">Product Manager, PM, APM</div></div>
              <div class="cfg-row"><div class="cfg-key">Level</div><div class="cfg-val">Mid / Senior / Staff</div></div>
              <div class="cfg-row"><div class="cfg-key">Visa</div><div class="cfg-val">H-1B sponsors flagged</div></div>
              <div class="cfg-row"><div class="cfg-key">Salary floor</div><div class="cfg-val">$120,000+</div></div>
              <div class="cfg-row"><div class="cfg-key">Check frequency</div><div class="cfg-val">Every 30 min</div></div>
            </div>
          </div>

          <div class="setup-sec">
            <div class="setup-sec-title">Alerts</div>
            <div class="cfg-table">
              <div class="cfg-row"><div class="cfg-key">Gmail instant alert</div><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
              <div class="cfg-row"><div class="cfg-key">Weekly digest</div><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
              <div class="cfg-row"><div class="cfg-key">Priority alert for 90%+ matches</div><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
            </div>
          </div>

          <div class="setup-sec">
            <div class="setup-sec-title">Job boards</div>
            <div class="cfg-table">
              <div class="cfg-row"><div class="cfg-key">Indeed</div><div class="cfg-right"><div class="dot-green"></div><div class="cfg-val">Connected via MCP</div><div class="toggle on" onclick="this.classList.toggle('on')"></div></div></div>
              <div class="cfg-row"><div class="cfg-key">Dice</div><div class="cfg-right"><div class="dot-green"></div><div class="cfg-val">Connected via MCP</div><div class="toggle on" onclick="this.classList.toggle('on')"></div></div></div>
              <div class="cfg-row"><div class="cfg-key">LinkedIn</div><div class="cfg-right"><div class="dot-green"></div><div class="cfg-val">Via Zapier</div><div class="toggle on" onclick="this.classList.toggle('on')"></div></div></div>
              <div class="cfg-row"><div class="cfg-key">Wellfound</div><div class="cfg-right"><div class="dot-amber"></div><div class="cfg-val">Manual</div><div class="toggle" onclick="this.classList.toggle('on')"></div></div></div>
            </div>
          </div>

          <div class="setup-sec">
            <div class="setup-sec-title">Anthropic API Key</div>
            <div class="cfg-table">
              <div class="cfg-row">
                <div class="cfg-key">Key status</div>
                <div class="cfg-right">
                  <div class="cfg-val" id="key-status">Checking…</div>
                  <button class="btn btn-secondary btn-sm" onclick="showApiKeyModal()">Update Key</button>
                  <button class="btn btn-ghost btn-sm" onclick="clearApiKey()">Clear</button>
                </div>
              </div>
            </div>
            <div style="font-size:12px;color:var(--ink-4);margin-top:8px;line-height:1.5">Your key is stored in your browser only. Get one at <a href="https://console.anthropic.com/keys" target="_blank" style="color:var(--accent)">console.anthropic.com/keys</a>.</div>
          </div>

          <button class="btn btn-primary btn-lg" style="width:100%;justify-content:center" onclick="saveSetup(this)">Save &amp; Activate</button>
        </div>
      </div>

    </div><!-- /content -->

    <!-- ACTION BAR — always visible -->
    <div class="action-bar" id="action-bar">
      <button class="btn btn-accent btn-lg" id="btn-cv" onclick="generateCV()">✨ Generate CV</button>
      <button class="btn btn-secondary btn-lg" id="btn-cover" onclick="generateCover()">✉️ Cover Letter</button>
      <div class="action-spacer"></div>
      <span class="action-hint" id="action-hint">← Select a role to generate materials</span>
      <button class="btn btn-ghost" id="btn-apply" onclick="applyNow()" style="display:none">Apply now →</button>
    </div>
  </main>

</div>

<script>
// ── FALLBACK PROFILE (used if no CV pasted) ───────────────────────────────
const FALLBACK_PROFILE = `MONISHA SOOD
Product Manager | New York, NY (relocating)
OPT status — H-1B sponsorship required

EXPERIENCE

SecondWind Pro — Product Manager (NIL Analytics Platform)
2023 – Present
• Built zero-to-one AI-powered analytics platform for Division 1 athletes
• Onboarded 500+ D1 athletes; achieved 40% partner school adoption rate
• Led full product lifecycle: discovery, roadmap, design, and go-to-market

Flyhomes — Operations Associate to Product Strategy Lead
2020 – 2023
• Delivered $48M in cost savings through process and product automation
• Improved customer CSAT by 32% through product-led service improvements
• Reduced manual effort by 70% via internal workflow tooling
• Supported $500K+ in fundraising with strategic product narratives

Flexera — MBA Capstone: AI Win/Loss Analytics Dashboard
2025 – 2026
• Led 12 stakeholder interviews across Sales, RevOps, and Marketing
• Prototyped full dashboard in Figma; built predictive modeling framework
• Presented to C-suite; validated with 12 internal Flexera employees

SKILLS
Product strategy · Zero-to-one launches · Data analytics · AI/ML product thinking · Figma · JIRA · SQL · Agile · Cross-functional leadership · B2B SaaS · Platform business models · NIL/sports tech · Fintech

EDUCATION
MBA, Technology Strategy & Product Management
Wisconsin School of Business — May 2026

PROJECTS
FreshPlate — AI food management platform (Anthropic API)
AI Trend Radar — Real-time social trend detection for content creators`;

// ── JOBS DATA ─────────────────────────────────────────────────────────────
const JOBS = [
  { id:1, title:"Product Manager – AI", company:"Tachyon Technologies", location:"Chicago, IL", posted:"Today", salary:null, isNew:true, isRemote:false, sponsors:null, isAI:true, url:"https://www.dice.com/job-detail/79d25676-7255-4711-a60e-a4a6e72dafdd", tags:["AI","Generative AI","Agentic"], matchScore:92, matchSkills:["AI/ML Products","Zero-to-one","Roadmap ownership","Cross-functional"], description:"Own one product end-to-end within a growing AI platform — conversational assistants, agentic workflows, knowledge retrieval, or content creation. Lead the full product lifecycle from discovery through delivery.", requirements:["5+ years PM experience","Generative or agentic AI product experience","Strong roadmap and prioritisation skills","Comfortable working cross-functionally at pace","Excellent written and verbal communication"] },
  { id:2, title:"Senior PM – AI Data Infrastructure", company:"NetApp", location:"San Jose, CA", posted:"Today", salary:null, isNew:true, isRemote:false, sponsors:true, isAI:true, url:"https://www.dice.com/direct-apply/b5194b07-293e-416c-9b61-e163268e3a37", tags:["AI","Data","Enterprise","Storage"], matchScore:83, matchSkills:["Data analytics","Enterprise SaaS","AI/ML","Stakeholder mgmt"], description:"Own the AI data infrastructure product roadmap at NetApp. Deliver unified storage and data services that help enterprises unlock AI and multicloud potential. Collaborate with engineering and data science teams.", requirements:["5+ years PM in data or infrastructure","AI/ML product background preferred","Enterprise storage or cloud experience","Data-driven analytical mindset","Ability to translate technical concepts for business audiences"] },
  { id:3, title:"Senior PM – AI Enablement", company:"Bullish (CoinDesk)", location:"New York, NY", posted:"Yesterday", salary:"$205K – $270K", isNew:false, isRemote:false, sponsors:false, isAI:true, url:"https://www.dice.com/job-detail/2f2b34c2-0e87-4212-9f01-aeec2be893ed", tags:["AI","Fintech","NYC"], matchScore:74, matchSkills:["AI products","Fintech","Analytics","B2B"], description:"Lead AI enablement products at Bullish, an institutionally focused global digital asset platform. Own the roadmap for AI capabilities that improve information services and exchange workflows.", requirements:["4+ years PM experience","AI product background","Fintech or financial services preferred","Strong stakeholder skills","NYC-based or willing to relocate"] },
  { id:4, title:"AI Product Manager (Consultant)", company:"Dell Technologies", location:"Seattle, WA", posted:"Yesterday", salary:"$167K – $238K", isNew:false, isRemote:false, sponsors:true, isAI:true, url:"https://www.dice.com/job-detail/ebc2c354-c08d-44ed-bd99-2a65b9e1a60e", tags:["AI","Enterprise","Direct Hire"], matchScore:80, matchSkills:["AI/ML products","Enterprise","Business outcomes","Cross-functional"], description:"Develop and deploy AI solutions for Dell's internal teams. Lead AI product strategy with obsession over measurable business value and customer experience impact.", requirements:["5+ years PM or solutions consulting","Deep enterprise AI use case knowledge","Strong business outcome framing","Stakeholder alignment at scale","Comfortable with ambiguity"] },
  { id:5, title:"Principal PM – Customer Identity", company:"Disney Entertainment & ESPN Technology", location:"New York, NY", posted:"Today", salary:"In description", isNew:true, isRemote:false, sponsors:false, isAI:false, url:"https://www.dice.com/direct-apply/067660b0-5aea-41bd-be25-32c145c66c09", tags:["Identity","Platform","Consumer","Media"], matchScore:76, matchSkills:["Platform PM","B2C","Cross-functional","Data"], description:"Build the identity and authentication platform powering Disney, Hulu, ESPN, and Disney+. Own product direction for customer account management, login, and personalisation at global scale.", requirements:["7+ years PM experience","Identity or account platform background preferred","Consumer product at scale","Strong technical and cross-functional skills","Ability to influence without authority"] },
  { id:6, title:"Senior PM – Licensing & AI Systems", company:"Disney Experiences", location:"Orlando, FL", posted:"Today", salary:null, isNew:true, isRemote:false, sponsors:false, isAI:true, url:"https://www.dice.com/direct-apply/8bc616c5-9df7-44c7-a350-5064ac45d7aa", tags:["AI","Licensing","Project Hire"], matchScore:69, matchSkills:["AI products","Process automation","Stakeholder mgmt"], description:"2.5-year project hire. Own licensing product approval systems and AI tooling for Walt Disney World and other resort brands.", requirements:["4+ years PM experience","AI or ML systems background preferred","Licensing or content management a plus","Process and workflow design skills","Comfort with large matrixed organisations"] },
  { id:7, title:"Lead PM – Data & AI Integration", company:"Walt Disney Company (Corporate)", location:"Orlando, FL", posted:"Today", salary:null, isNew:true, isRemote:false, sponsors:false, isAI:true, url:"https://www.dice.com/direct-apply/957c8bb9-599e-4c6d-8320-7d02b2bec26c", tags:["AI","Data","VMO","Project Hire"], matchScore:71, matchSkills:["AI/data products","Roadmap","Enterprise","Cross-functional"], description:"Project hire owning data and AI integration across Disney's Technology VMO. Drive adoption of AI tools and data services that improve how Disney's technology organisation delivers.", requirements:["6+ years PM or related","Data and AI integration background","Enterprise programme management","Strong stakeholder alignment","Experience in large technology organisations"] },
  { id:8, title:"Senior PM II – Commerce, Tax & Billing", company:"Disney Entertainment & ESPN Technology", location:"New York, NY", posted:"Today", salary:"In description", isNew:true, isRemote:false, sponsors:false, isAI:false, url:"https://www.dice.com/direct-apply/a00eac6a-2c2a-4bca-800a-5178df2e2c86", tags:["Commerce","Billing","Platform","NYC"], matchScore:72, matchSkills:["Platform PM","Process automation","B2C","Data"], description:"Own the commerce, tax, and billing product stack for Disney+ and ESPN streaming. Define and deliver systems powering subscriptions and financial transactions for millions of users globally.", requirements:["5+ years PM experience","Commerce or billing product background strongly preferred","Strong analytical skills","High-scale consumer product experience","Excellent engineering partnership"] },
  { id:9, title:"Product Manager – Product Owner / Analyst", company:"SES", location:"Washington, DC (Hybrid)", posted:"3 days ago", salary:"DOE", isNew:false, isRemote:false, sponsors:false, isAI:false, url:"https://www.dice.com/job-detail/6eec061f-fd76-4597-9138-bf98e32d22f9", tags:["Hybrid","Easy Apply","Direct Hire"], matchScore:65, matchSkills:["Roadmap","Agile","Stakeholder mgmt","Spec-driven dev"], description:"Define and prioritise product direction for a delivery team practicing spec-driven development. Bridge business goals, user needs, technical feasibility, and delivery execution.", requirements:["3+ years PM or PO experience","Spec-driven or agile development background","Strong business analysis skills","Traceable, testable product spec experience","Excellent cross-team communication"] },
  { id:10, title:"Product Manager (Healthcare Software)", company:"Robert Half", location:"Saint Paul, MN", posted:"3 days ago", salary:"$59 – $68/hr", isNew:false, isRemote:false, sponsors:false, isAI:false, url:"https://www.dice.com/job-detail/2c6d6b82-eb09-4469-9adc-c553a605c462", tags:["Healthcare","Contract-to-Perm"], matchScore:60, matchSkills:["Roadmap","Cross-functional","Market insights","Agile"], description:"Guide product direction for a growing IT software organisation. Contract-to-permanent partnering with Product Owners and engineering in healthcare software.", requirements:["3+ years PM experience","Healthcare software knowledge preferred","Market research and insight translation","Agile delivery","Minnesota-based preferred"] },
  { id:11, title:"Product Manager – Provider Finder (Insurance)", company:"Horizontal Talent", location:"Denver, CO", posted:"3 days ago", salary:"$22 – $50/hr", isNew:false, isRemote:true, sponsors:false, isAI:false, url:"https://www.dice.com/job-detail/cbbaf47b-5af3-4950-953c-a7fe072135fc", tags:["Remote","Healthcare","Insurance","Scrum"], matchScore:63, matchSkills:["Backlog management","Sprint planning","Stakeholder mgmt","Agile"], description:"Lead a provider finder project for an insurance client. Oversee product backlog delivery with scrum teams, lead sprint planning, and facilitate communication around product vision and priorities.", requirements:["3+ years PM experience","Healthcare or insurance a plus","Scrum and agile required","Backlog management and prioritisation","Strong written and verbal communication"] },
  { id:12, title:"Technical PM – Pricing & Packaging Analytics", company:"DIRECTV", location:"Los Angeles, CA", posted:"Today", salary:"In description", isNew:true, isRemote:false, sponsors:false, isAI:false, url:"https://www.dice.com/direct-apply/36ec9345-b5b1-4d75-b450-8c8c8f5305eb", tags:["Technical PM","Pricing","Analytics","Media"], matchScore:68, matchSkills:["Analytics","Data-driven","Stakeholder mgmt","Technical comms"], description:"Define and evolve DIRECTV's pricing and packaging analytics systems. Bridge business stakeholders and technical teams to translate goals into scalable, secure, high-performing solutions.", requirements:["5+ years technical PM","Pricing or billing analytics background preferred","Translate business requirements to engineering","Strong data skills","Media or subscription business a plus"] },
  { id:13, title:"Product Owner / PM – Conversational AI (Voice)", company:"Everest Global Solutions", location:"Atlanta, GA (Hybrid)", posted:"Today", salary:"DOE", isNew:true, isRemote:false, sponsors:false, isAI:true, url:"https://www.dice.com/job-detail/6b98e150-75d1-4b8c-b173-7709cfba4a58", tags:["Conversational AI","Voice AI","Healthcare","Easy Apply"], matchScore:77, matchSkills:["AI products","Voice/NLP","Healthcare","Roadmap ownership"], description:"Own the product vision, roadmap, and delivery for a Conversational AI Voice platform in the healthcare payer space. Define the future of AI-powered patient and member interactions.", requirements:["8+ years PM / PO experience","4+ years Conversational or Voice AI","Healthcare domain strongly preferred","Agile and business analysis skills","AI vendor selection and integration experience"] }
];

// ── STATE ─────────────────────────────────────────────────────────────────
let selected = null;
let activeTab = 'detail';
let activeFilter = 'all';
let cvText = '';
let coverText = '';
let saveTimer = null;


// ── API KEY MANAGEMENT ────────────────────────────────────────────────────
function getApiKey() {
  let key = localStorage.getItem('pm_radar_api_key');
  if (!key) {
    showApiKeyModal();
    return null;
  }
  return key;
}

function showApiKeyModal() {
  document.getElementById('api-modal').style.display = 'flex';
}

function saveApiKey() {
  const val = document.getElementById('api-key-input').value.trim();
  if (!val.startsWith('sk-ant-')) {
    document.getElementById('api-key-error').style.display = 'block';
    return;
  }
  localStorage.setItem('pm_radar_api_key', val);
  document.getElementById('api-modal').style.display = 'none';
  document.getElementById('key-status').textContent = 'API key saved ✓';
  document.getElementById('key-status').style.color = 'var(--accent)';
}

function clearApiKey() {
  localStorage.removeItem('pm_radar_api_key');
  document.getElementById('api-key-input').value = '';
  document.getElementById('key-status').textContent = 'No key saved';
  document.getElementById('key-status').style.color = 'var(--ink-4)';
}

function checkKeyStatus() {
  const key = localStorage.getItem('pm_radar_api_key');
  const el = document.getElementById('key-status');
  if (el) {
    el.textContent = key ? 'API key saved ✓' : 'No key saved';
    el.style.color = key ? 'var(--accent)' : 'var(--ink-4)';
  }
  if (key) {
    document.getElementById('api-modal').style.display = 'none';
  }
}

// ── CV STORAGE ────────────────────────────────────────────────────────────
function loadStoredCV() {
  try {
    const stored = localStorage.getItem('pm_radar_cv');
    if (stored) document.getElementById('cv-textarea').value = stored;
  } catch(e) {}
}

function autosaveCV() {
  clearTimeout(saveTimer);
  saveTimer = setTimeout(() => {
    try {
      localStorage.setItem('pm_radar_cv', document.getElementById('cv-textarea').value);
      const ind = document.getElementById('save-indicator');
      ind.classList.add('show');
      setTimeout(() => ind.classList.remove('show'), 2000);
    } catch(e) {}
  }, 800);
}

function saveCV() {
  try {
    localStorage.setItem('pm_radar_cv', document.getElementById('cv-textarea').value);
    const ind = document.getElementById('save-indicator');
    ind.classList.add('show');
    setTimeout(() => ind.classList.remove('show'), 2000);
  } catch(e) {}
}

function clearCV() {
  if (confirm('Clear your saved CV?')) {
    document.getElementById('cv-textarea').value = '';
    try { localStorage.removeItem('pm_radar_cv'); } catch(e) {}
  }
}

function getUserCV() {
  const typed = document.getElementById('cv-textarea').value.trim();
  return typed || FALLBACK_PROFILE;
}

// ── INIT ──────────────────────────────────────────────────────────────────
function init() {
  loadStoredCV();
  checkKeyStatus();
  setTimeout(() => {
    renderJobList(JOBS);
    document.getElementById('job-count').textContent = JOBS.length;
    const n = JOBS.filter(j => j.isNew).length;
    document.getElementById('new-chip').textContent = n + ' new today';
  }, 800);
}

// ── RENDER JOB LIST ───────────────────────────────────────────────────────
function renderJobList(jobs) {
  const el = document.getElementById('job-list');
  if (!jobs.length) {
    el.innerHTML = `<div class="list-loading"><div class="list-loading-text">No roles match this filter.</div></div>`;
    return;
  }
  el.innerHTML = jobs.map(j => `
    <div class="job-item${selected?.id===j.id?' active':''}" id="ji-${j.id}" onclick="selectJob(${j.id})">
      <div class="job-item-top">
        <div class="job-item-title">${j.title}</div>
        <div class="job-item-time">${j.posted}</div>
      </div>
      <div class="job-item-co">${j.company} · ${j.location}</div>
      <div class="job-item-pills">
        ${j.isNew?'<span class="pill p-new">NEW</span>':''}
        ${j.isRemote?'<span class="pill p-remote">REMOTE</span>':''}
        ${j.sponsors===true?'<span class="pill p-sponsor">H-1B ✓</span>':''}
        ${j.sponsors===false?'<span class="pill p-nosponsor">No sponsor</span>':''}
        ${j.salary?`<span class="pill p-tag">${j.salary}</span>`:''}
        <span class="pill p-match">${j.matchScore}% match</span>
      </div>
    </div>`).join('');
}

// ── SELECT JOB ────────────────────────────────────────────────────────────
function selectJob(id) {
  selected = JOBS.find(j => j.id===id);
  cvText = ''; coverText = '';
  document.querySelectorAll('.job-item').forEach(el => el.classList.remove('active'));
  document.getElementById('ji-'+id)?.classList.add('active');
  renderDetail();
  // show apply button, update hint
  document.getElementById('action-hint').style.display = 'none';
  document.getElementById('btn-apply').style.display = '';
  // reset output panes
  document.getElementById('cv-empty').style.display = '';
  document.getElementById('cv-content').style.display = 'none';
  document.getElementById('cover-empty').style.display = '';
  document.getElementById('cover-content').style.display = 'none';
  // switch to detail
  switchTab('detail', document.querySelector('[data-tab="detail"]'));
}

// ── RENDER DETAIL ─────────────────────────────────────────────────────────
function renderDetail() {
  const j = selected;
  document.getElementById('detail-empty').style.display = 'none';
  const el = document.getElementById('detail-content');
  el.style.display = 'block';
  el.innerHTML = `
    <div class="eyebrow">${j.company} · ${j.location} · ${j.posted}</div>
    <div class="detail-title">${j.title}</div>
    <div class="detail-company">${j.company}</div>
    <div class="detail-pills">
      ${j.isNew?'<span class="pill p-new">POSTED TODAY</span>':''}
      ${j.isRemote?'<span class="pill p-remote">REMOTE</span>':''}
      ${j.sponsors===true?'<span class="pill p-sponsor">H-1B SPONSORSHIP</span>':''}
      ${j.sponsors===false?'<span class="pill p-nosponsor">NO SPONSORSHIP LISTED</span>':''}
      ${j.salary?`<span class="pill p-tag">${j.salary}</span>`:''}
      ${j.tags.map(t=>`<span class="pill p-tag">${t}</span>`).join('')}
    </div>
    <div class="match-card">
      <div class="match-card-top">
        <div class="match-lbl">PROFILE MATCH SCORE</div>
        <div class="match-num">${j.matchScore}%</div>
      </div>
      <div class="match-track"><div class="match-fill" style="width:${j.matchScore}%"></div></div>
      <div class="match-skills">${j.matchSkills.map(s=>`<span class="mskill">✓ ${s}</span>`).join('')}</div>
    </div>
    <div class="section">
      <div class="section-title">About the role</div>
      <div class="section-body">${j.description}</div>
    </div>
    <div class="section">
      <div class="section-title">Requirements</div>
      <ul class="req-list">${j.requirements.map(r=>`<li>${r}</li>`).join('')}</ul>
    </div>`;
}

// ── SWITCH TAB ────────────────────────────────────────────────────────────
function switchTab(tab, el) {
  activeTab = tab;
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  el?.classList.add('active');
  document.querySelectorAll('.tab-pane').forEach(p => p.classList.remove('active'));
  document.getElementById('pane-'+tab)?.classList.add('active');
  // hide action bar on setup/mycv tabs
  const bar = document.getElementById('action-bar');
  bar.style.display = (tab==='setup'||tab==='mycv') ? 'none' : 'flex';
}

// ── GENERATE CV ───────────────────────────────────────────────────────────
async function generateCV() {
  if (!selected) {
    alert('Please select a role from the left first.');
    return;
  }
  const btn = document.getElementById('btn-cv');
  btn.disabled = true; btn.textContent = 'Generating…';
  switchTab('cv', document.querySelector('[data-tab="cv"]'));
  document.getElementById('cv-empty').style.display = 'none';
  const wrap = document.getElementById('cv-content');
  wrap.style.display = 'block';
  wrap.innerHTML = `
    <div class="output-head">
      <div>
        <div class="output-title">Tailored CV — ${selected.title}</div>
        <div class="output-sub">${selected.company} · edited from your base CV for this role</div>
      </div>
    </div>
    <div class="output-box">
      <div class="output-box-head">
        <div class="output-box-lbl">Resume · ATS-safe plain text</div>
        <button class="copy-btn" onclick="copyOut('cv')" id="copy-cv-btn">Copy</button>
      </div>
      <div class="output-body output-loading" id="cv-body">
        <div class="spinner"></div>&nbsp; Tailoring your CV…
      </div>
    </div>`;

  const baseCV = getUserCV();
  const hasCustomCV = document.getElementById('cv-textarea').value.trim().length > 0;

  try {
    const prompt = `You are a senior PM resume editor who specialises in ATS optimisation.

${hasCustomCV ? 'CANDIDATE\'S ACTUAL CV (edit this — do not replace it with a generic template):' : 'CANDIDATE PROFILE (build a resume from this):'}
${baseCV}

TARGET ROLE:
Title: ${selected.title}
Company: ${selected.company}
Description: ${selected.description}
Requirements: ${selected.requirements.join('; ')}
Tags: ${selected.tags.join(', ')}

INSTRUCTIONS:
${hasCustomCV
  ? `Edit the candidate's actual CV above. Keep their real formatting, structure, and bullet points — only make targeted changes:
- Reorder bullets within each role to front-load the most relevant experience for THIS job
- Rewrite 2-3 bullets to mirror the job description's exact language (ATS keywords)
- Update the summary/headline to match this role's framing
- Adjust the skills section to prioritise keywords from this JD
- Do NOT invent experience, metrics, or roles that aren't in the original CV`
  : `Build a clean, ATS-optimised one-page resume. Include summary, experience with metrics, skills, education.`}

Rules: No em dashes. Confident, direct, human voice. Output the full edited resume in plain text only.`;

    const apiKey = getApiKey();
    if (!apiKey) return;
    const res = await fetch('https://api.anthropic.com/v1/messages', {
      method:'POST',
      headers:{
        'Content-Type':'application/json',
        'x-api-key': apiKey,
        'anthropic-version': '2023-06-01',
        'anthropic-dangerous-direct-browser-access': 'true'
      },
      body: JSON.stringify({ model:'claude-sonnet-4-20250514', max_tokens:1200, messages:[{role:'user',content:prompt}] })
    });
    const data = await res.json();
    if (data.error) throw new Error(data.error.message);
    cvText = data.content?.[0]?.text || 'Error generating — please try again.';
    const body = document.getElementById('cv-body');
    body.classList.remove('output-loading');
    body.innerHTML = `<span id="cv-text"></span><span class="cursor"></span>`;
    streamText(document.getElementById('cv-text'), cvText, () => body.querySelector('.cursor')?.remove());
  } catch(e) {
    document.getElementById('cv-body').innerHTML = `<span style="color:var(--red)">Error: ${e.message}</span>`;
  }
  btn.disabled = false; btn.textContent = '✨ Generate CV';
}

// ── GENERATE COVER LETTER ─────────────────────────────────────────────────
async function generateCover() {
  if (!selected) {
    alert('Please select a role from the left first.');
    return;
  }
  const btn = document.getElementById('btn-cover');
  btn.disabled = true; btn.textContent = 'Generating…';
  switchTab('cover', document.querySelector('[data-tab="cover"]'));
  document.getElementById('cover-empty').style.display = 'none';
  const wrap = document.getElementById('cover-content');
  wrap.style.display = 'block';
  wrap.innerHTML = `
    <div class="output-head">
      <div>
        <div class="output-title">Cover Letter — ${selected.title}</div>
        <div class="output-sub">${selected.company} · tailored to this role</div>
      </div>
    </div>
    <div class="output-box">
      <div class="output-box-head">
        <div class="output-box-lbl">Cover Letter · Ready to send</div>
        <button class="copy-btn" onclick="copyOut('cover')">Copy</button>
      </div>
      <div class="output-body output-loading" id="cover-body">
        <div class="spinner"></div>&nbsp; Writing your cover letter…
      </div>
    </div>`;

  try {
    const prompt = `You are a senior PM career coach who writes sharp, human cover letters that get callbacks.

CANDIDATE PROFILE:
${getUserCV()}

TARGET ROLE:
Title: ${selected.title}
Company: ${selected.company}
Description: ${selected.description}
Requirements: ${selected.requirements.join('; ')}

Write a concise cover letter (3 short paragraphs, under 280 words):
1. Opening — hook with the most compelling match. No "I am excited to apply" openers.
2. Body — specific evidence from her experience mapping directly to this role. Real metrics. Connect her work to what this company is building.
3. Close — short and direct. Signal genuine interest in this company specifically.

Rules: No em dashes. Conversational and specific, not corporate. Under 280 words. Start with "Dear Hiring Team," and output letter text only.`;

    const apiKey2 = getApiKey();
    if (!apiKey2) return;
    const res = await fetch('https://api.anthropic.com/v1/messages', {
      method:'POST',
      headers:{
        'Content-Type':'application/json',
        'x-api-key': apiKey2,
        'anthropic-version': '2023-06-01',
        'anthropic-dangerous-direct-browser-access': 'true'
      },
      body: JSON.stringify({ model:'claude-sonnet-4-20250514', max_tokens:600, messages:[{role:'user',content:prompt}] })
    });
    const data = await res.json();
    if (data.error) throw new Error(data.error.message);
    coverText = data.content?.[0]?.text || 'Error — please try again.';
    const body = document.getElementById('cover-body');
    body.classList.remove('output-loading');
    body.innerHTML = `<span id="cover-text"></span><span class="cursor"></span>`;
    streamText(document.getElementById('cover-text'), coverText, () => body.querySelector('.cursor')?.remove());
  } catch(e) {
    document.getElementById('cover-body').innerHTML = `<span style="color:var(--red)">Error: ${e.message}</span>`;
  }
  btn.disabled = false; btn.textContent = '✉️ Cover Letter';
}

// ── HELPERS ───────────────────────────────────────────────────────────────
function streamText(el, text, done) {
  let i = 0;
  const iv = setInterval(() => {
    if (i < text.length) { el.textContent += text[i++]; el.closest('.output-body,.cv-body').scrollTop = 99999; }
    else { clearInterval(iv); if(done) done(); }
  }, 5);
}

function copyOut(which) {
  const text = which==='cv' ? cvText : coverText;
  navigator.clipboard.writeText(text).then(() => {
    const btn = document.getElementById('copy-cv-btn') || document.querySelector('.copy-btn');
    const allBtns = document.querySelectorAll('.copy-btn');
    allBtns.forEach(b => { b.textContent='Copied!'; setTimeout(()=>b.textContent='Copy',2000); });
  });
}

function applyNow() { if(selected?.url) window.open(selected.url,'_blank'); }

function filterJobs() {
  const q = document.getElementById('search-input').value.toLowerCase();
  let res = JOBS.filter(j => {
    if (activeFilter==='new') return j.isNew;
    if (activeFilter==='nyc') return j.location.includes('New York');
    if (activeFilter==='remote') return j.isRemote;
    if (activeFilter==='ai') return j.isAI;
    return true;
  });
  if(q) res = res.filter(j => j.title.toLowerCase().includes(q)||j.company.toLowerCase().includes(q)||j.tags.some(t=>t.toLowerCase().includes(q)));
  renderJobList(res);
}

function setFilter(f, el) {
  activeFilter = f;
  document.querySelectorAll('.fpill').forEach(p => p.classList.remove('on'));
  el.classList.add('on');
  filterJobs();
}

function refreshJobs() {
  document.getElementById('job-list').innerHTML = `<div class="list-loading"><div class="spinner"></div><div class="list-loading-text">Scanning for new roles…</div></div>`;
  setTimeout(() => {
    renderJobList(JOBS);
    document.getElementById('job-count').textContent = JOBS.length;
    document.getElementById('new-chip').textContent = JOBS.filter(j=>j.isNew).length + ' new today';
  }, 1200);
}

function saveSetup(btn) {
  btn.textContent='✓ Saved';
  btn.style.background='var(--accent)';
  setTimeout(()=>{btn.textContent='Save & Activate';btn.style.background='';},2500);
}

init();
</script>

<!-- API KEY MODAL -->
<div id="api-modal" style="display:none;position:fixed;inset:0;background:rgba(0,0,0,.45);z-index:1000;align-items:center;justify-content:center;backdrop-filter:blur(2px)">
  <div style="background:var(--white);border-radius:14px;padding:28px 32px;max-width:460px;width:90%;box-shadow:0 20px 60px rgba(0,0,0,.2)">
    <div style="font-family:'Instrument Serif',serif;font-size:20px;color:var(--ink);margin-bottom:6px">Anthropic API Key Required</div>
    <div style="font-size:13px;color:var(--ink-3);line-height:1.6;margin-bottom:20px">
      To generate tailored CVs and cover letters, paste your Anthropic API key below. It's stored only in your browser — never sent anywhere except directly to Anthropic's API.
    </div>
    <div style="margin-bottom:8px">
      <input id="api-key-input" type="password" placeholder="sk-ant-api03-..." style="width:100%;padding:10px 12px;border:1px solid var(--rule);border-radius:var(--r-sm);font-family:'JetBrains Mono',monospace;font-size:13px;outline:none;color:var(--ink);background:var(--off-white)">
    </div>
    <div id="api-key-error" style="display:none;font-size:12px;color:var(--red);margin-bottom:8px">Key should start with sk-ant-</div>
    <div style="display:flex;gap:8px;align-items:center;margin-bottom:16px">
      <button class="btn btn-primary" onclick="saveApiKey()" style="flex:1;justify-content:center">Save Key &amp; Continue</button>
      <button class="btn btn-ghost" onclick="document.getElementById('api-modal').style.display='none'">Cancel</button>
    </div>
    <div style="font-size:11px;color:var(--ink-4);line-height:1.5">
      Get your key at <a href="https://console.anthropic.com/keys" target="_blank" style="color:var(--accent)">console.anthropic.com/keys</a>. Your key is saved in localStorage and never leaves your browser except in direct API calls to Anthropic.
    </div>
  </div>
</div>
</body>
</html>
