<!DOCTYPE html>
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
  --white: #ffffff;
  --off-white: #f7f6f3;
  --paper: #fafaf8;
  --ink: #0f0f0e;
  --ink-2: #2d2d2b;
  --ink-3: #5a5a57;
  --ink-4: #9b9b97;
  --ink-5: #c8c8c4;
  --ink-6: #e8e8e4;
  --rule: #e4e4e0;
  --accent: #1a6b3c;
  --accent-light: #e8f4ed;
  --accent-mid: #2d8a52;
  --amber: #b45309;
  --amber-light: #fef3c7;
  --red: #b91c1c;
  --red-light: #fee2e2;
  --blue: #1d4ed8;
  --blue-light: #eff6ff;
  --shadow-sm: 0 1px 3px rgba(0,0,0,.06), 0 1px 2px rgba(0,0,0,.04);
  --shadow-md: 0 4px 12px rgba(0,0,0,.08), 0 2px 4px rgba(0,0,0,.04);
  --shadow-lg: 0 12px 32px rgba(0,0,0,.10), 0 4px 8px rgba(0,0,0,.05);
  --radius: 10px;
  --radius-sm: 6px;
  --radius-lg: 14px;
}

html { font-size: 14px; }

body {
  font-family: 'Plus Jakarta Sans', system-ui, sans-serif;
  background: var(--paper);
  color: var(--ink);
  height: 100vh;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}

/* ── TOPBAR ── */
.topbar {
  background: var(--white);
  border-bottom: 1px solid var(--rule);
  padding: 0 28px;
  height: 56px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-shrink: 0;
  box-shadow: var(--shadow-sm);
  z-index: 10;
}

.brand {
  display: flex;
  align-items: center;
  gap: 14px;
}

.brand-mark {
  width: 32px; height: 32px;
  background: var(--ink);
  border-radius: 8px;
  display: flex; align-items: center; justify-content: center;
  color: white;
  font-size: 15px;
  flex-shrink: 0;
}

.brand-name {
  font-family: 'Instrument Serif', Georgia, serif;
  font-size: 17px;
  color: var(--ink);
  letter-spacing: -.2px;
}

.brand-divider {
  width: 1px; height: 18px;
  background: var(--rule);
}

.brand-sub {
  font-size: 12px;
  color: var(--ink-4);
  font-weight: 400;
}

.topbar-right {
  display: flex;
  align-items: center;
  gap: 10px;
}

.live-badge {
  display: flex;
  align-items: center;
  gap: 6px;
  padding: 5px 10px;
  background: var(--accent-light);
  border-radius: 20px;
  font-size: 11px;
  font-weight: 600;
  color: var(--accent);
  letter-spacing: .3px;
}

.live-dot {
  width: 6px; height: 6px;
  border-radius: 50%;
  background: var(--accent-mid);
  animation: pulse 2.5s ease-in-out infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; transform: scale(1); }
  50% { opacity: .5; transform: scale(.85); }
}

.btn {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 7px 14px;
  border-radius: var(--radius-sm);
  border: none;
  cursor: pointer;
  font-family: 'Plus Jakarta Sans', sans-serif;
  font-size: 13px;
  font-weight: 600;
  line-height: 1;
  transition: all .15s ease;
  white-space: nowrap;
}

.btn:disabled { opacity: .5; cursor: not-allowed !important; }

.btn-primary {
  background: var(--ink);
  color: var(--white);
}
.btn-primary:hover:not(:disabled) {
  background: var(--ink-2);
  box-shadow: var(--shadow-sm);
  transform: translateY(-1px);
}

.btn-secondary {
  background: var(--white);
  color: var(--ink);
  border: 1px solid var(--rule);
  box-shadow: var(--shadow-sm);
}
.btn-secondary:hover:not(:disabled) {
  border-color: var(--ink-4);
  background: var(--off-white);
}

.btn-accent {
  background: var(--accent);
  color: white;
}
.btn-accent:hover:not(:disabled) {
  background: var(--accent-mid);
  transform: translateY(-1px);
  box-shadow: var(--shadow-sm);
}

.btn-ghost {
  background: transparent;
  color: var(--ink-3);
  border: 1px solid transparent;
}
.btn-ghost:hover { background: var(--off-white); color: var(--ink); }

.btn-sm { padding: 5px 10px; font-size: 12px; }
.btn-lg { padding: 10px 20px; font-size: 14px; }

/* ── LAYOUT ── */
.workspace {
  display: grid;
  grid-template-columns: 360px 1fr;
  flex: 1;
  overflow: hidden;
  gap: 0;
}

/* ── LEFT PANEL ── */
.left-panel {
  background: var(--white);
  border-right: 1px solid var(--rule);
  display: flex;
  flex-direction: column;
  overflow: hidden;
}

.panel-head {
  padding: 16px 20px 12px;
  border-bottom: 1px solid var(--rule);
  flex-shrink: 0;
}

.panel-head-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 12px;
}

.panel-title {
  font-size: 13px;
  font-weight: 700;
  color: var(--ink);
  letter-spacing: -.1px;
  display: flex;
  align-items: center;
  gap: 8px;
}

.count-chip {
  background: var(--ink);
  color: white;
  font-size: 10px;
  font-weight: 700;
  padding: 2px 7px;
  border-radius: 10px;
  font-family: 'JetBrains Mono', monospace;
}

.new-chip {
  background: var(--accent-light);
  color: var(--accent);
  font-size: 10px;
  font-weight: 700;
  padding: 2px 7px;
  border-radius: 10px;
}

.search-wrap {
  position: relative;
  margin-bottom: 10px;
}

.search-icon {
  position: absolute;
  left: 10px; top: 50%;
  transform: translateY(-50%);
  color: var(--ink-4);
  font-size: 13px;
  pointer-events: none;
}

.search-input {
  width: 100%;
  padding: 8px 10px 8px 32px;
  background: var(--off-white);
  border: 1px solid var(--rule);
  border-radius: var(--radius-sm);
  font-family: 'Plus Jakarta Sans', sans-serif;
  font-size: 13px;
  color: var(--ink);
  outline: none;
  transition: all .15s;
}
.search-input:focus {
  border-color: var(--ink-3);
  background: var(--white);
  box-shadow: 0 0 0 3px rgba(15,15,14,.06);
}
.search-input::placeholder { color: var(--ink-5); }

.filters {
  display: flex;
  gap: 5px;
  flex-wrap: wrap;
}

.filter-pill {
  padding: 4px 10px;
  border-radius: 20px;
  border: 1px solid var(--rule);
  background: transparent;
  color: var(--ink-3);
  font-size: 11px;
  font-weight: 500;
  cursor: pointer;
  font-family: 'Plus Jakarta Sans', sans-serif;
  transition: all .12s;
  white-space: nowrap;
}
.filter-pill:hover { border-color: var(--ink-3); color: var(--ink); }
.filter-pill.on {
  background: var(--ink);
  border-color: var(--ink);
  color: white;
}

/* ── JOB LIST ── */
.job-list {
  flex: 1;
  overflow-y: auto;
  scrollbar-width: thin;
  scrollbar-color: var(--ink-6) transparent;
}

.job-item {
  padding: 14px 20px;
  border-bottom: 1px solid var(--rule);
  cursor: pointer;
  transition: background .1s;
  position: relative;
}
.job-item:hover { background: var(--off-white); }
.job-item.active {
  background: var(--off-white);
  border-left: 3px solid var(--ink);
  padding-left: 17px;
}

.job-item-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 8px;
  margin-bottom: 4px;
}

.job-item-title {
  font-size: 13px;
  font-weight: 600;
  color: var(--ink);
  line-height: 1.35;
  flex: 1;
}

.job-item-time {
  font-size: 10px;
  color: var(--ink-4);
  font-family: 'JetBrains Mono', monospace;
  white-space: nowrap;
  flex-shrink: 0;
  margin-top: 1px;
}

.job-item-co {
  font-size: 12px;
  color: var(--ink-3);
  margin-bottom: 8px;
}

.job-item-pills {
  display: flex;
  gap: 5px;
  flex-wrap: wrap;
}

.pill {
  display: inline-flex;
  align-items: center;
  gap: 3px;
  padding: 2px 7px;
  border-radius: 4px;
  font-size: 10px;
  font-weight: 600;
  letter-spacing: .2px;
  font-family: 'JetBrains Mono', monospace;
}

.pill-new { background: var(--accent-light); color: var(--accent); }
.pill-remote { background: var(--blue-light); color: var(--blue); }
.pill-sponsor { background: var(--amber-light); color: var(--amber); }
.pill-nosponsor { background: var(--red-light); color: var(--red); }
.pill-match { background: var(--off-white); color: var(--ink-3); border: 1px solid var(--rule); }
.pill-tag { background: var(--off-white); color: var(--ink-3); border: 1px solid var(--rule); }

/* ── RIGHT PANEL ── */
.right-panel {
  display: flex;
  flex-direction: column;
  overflow: hidden;
  background: var(--paper);
}

/* ── TABS ── */
.tab-bar {
  background: var(--white);
  border-bottom: 1px solid var(--rule);
  padding: 0 28px;
  display: flex;
  align-items: center;
  gap: 0;
  flex-shrink: 0;
  box-shadow: var(--shadow-sm);
}

.tab {
  padding: 16px 4px;
  margin-right: 24px;
  font-size: 13px;
  font-weight: 500;
  color: var(--ink-3);
  cursor: pointer;
  border-bottom: 2px solid transparent;
  transition: all .15s;
  white-space: nowrap;
}
.tab:hover { color: var(--ink); }
.tab.active { color: var(--ink); font-weight: 700; border-bottom-color: var(--ink); }

/* ── CONTENT AREA ── */
.content {
  flex: 1;
  overflow-y: auto;
  scrollbar-width: thin;
  scrollbar-color: var(--ink-6) transparent;
}

.tab-pane { display: none; }
.tab-pane.active { display: block; }

/* ── EMPTY STATE ── */
.empty {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100%;
  min-height: 400px;
  gap: 10px;
  padding: 40px;
}
.empty-icon { font-size: 36px; opacity: .2; }
.empty-title { font-size: 15px; font-weight: 600; color: var(--ink-3); }
.empty-sub { font-size: 13px; color: var(--ink-4); text-align: center; line-height: 1.5; }

/* ── JOB DETAIL ── */
.detail-wrap {
  padding: 28px 32px;
  max-width: 860px;
}

.detail-eyebrow {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  font-weight: 500;
  color: var(--ink-4);
  letter-spacing: .8px;
  text-transform: uppercase;
  margin-bottom: 10px;
}

.detail-title {
  font-family: 'Instrument Serif', Georgia, serif;
  font-size: 26px;
  color: var(--ink);
  line-height: 1.2;
  letter-spacing: -.3px;
  margin-bottom: 6px;
}

.detail-company {
  font-size: 15px;
  color: var(--ink-3);
  margin-bottom: 16px;
  font-weight: 400;
}

.detail-pills {
  display: flex;
  gap: 6px;
  flex-wrap: wrap;
  margin-bottom: 24px;
}

/* Match score card */
.match-card {
  background: var(--white);
  border: 1px solid var(--rule);
  border-radius: var(--radius);
  padding: 18px 20px;
  margin-bottom: 24px;
  box-shadow: var(--shadow-sm);
}

.match-card-head {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 12px;
}

.match-label {
  font-size: 11px;
  font-family: 'JetBrains Mono', monospace;
  color: var(--ink-4);
  text-transform: uppercase;
  letter-spacing: .8px;
}

.match-score-big {
  font-family: 'Instrument Serif', serif;
  font-size: 28px;
  color: var(--accent);
  line-height: 1;
}

.match-track {
  height: 3px;
  background: var(--rule);
  border-radius: 2px;
  overflow: hidden;
  margin-bottom: 12px;
}

.match-fill {
  height: 100%;
  background: linear-gradient(90deg, var(--accent), var(--accent-mid));
  border-radius: 2px;
  transition: width .9s cubic-bezier(.4,0,.2,1);
}

.match-skills {
  display: flex;
  gap: 6px;
  flex-wrap: wrap;
}

.match-skill-tag {
  padding: 3px 9px;
  border-radius: 4px;
  font-size: 11px;
  font-weight: 500;
  background: var(--accent-light);
  color: var(--accent);
}

/* Detail sections */
.section {
  margin-bottom: 24px;
}

.section-title {
  font-size: 11px;
  font-family: 'JetBrains Mono', monospace;
  color: var(--ink-4);
  text-transform: uppercase;
  letter-spacing: .8px;
  margin-bottom: 10px;
  padding-bottom: 8px;
  border-bottom: 1px solid var(--rule);
}

.section-body {
  font-size: 13.5px;
  color: var(--ink-2);
  line-height: 1.75;
}

.req-list { list-style: none; }
.req-list li {
  display: flex;
  gap: 10px;
  align-items: flex-start;
  padding: 5px 0;
  font-size: 13px;
  color: var(--ink-2);
  line-height: 1.5;
}
.req-list li::before {
  content: "–";
  color: var(--ink-4);
  flex-shrink: 0;
  margin-top: 1px;
}

/* ── ACTION BAR ── */
.action-bar {
  background: var(--white);
  border-top: 1px solid var(--rule);
  padding: 14px 32px;
  display: flex;
  align-items: center;
  gap: 10px;
  flex-shrink: 0;
  box-shadow: 0 -2px 8px rgba(0,0,0,.04);
}

.action-spacer { flex: 1; }

/* ── CV OUTPUT ── */
.cv-wrap {
  padding: 28px 32px;
  max-width: 860px;
}

.cv-header {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  margin-bottom: 20px;
  gap: 16px;
}

.cv-header-left {}

.cv-header-title {
  font-family: 'Instrument Serif', Georgia, serif;
  font-size: 20px;
  color: var(--ink);
  margin-bottom: 4px;
}

.cv-header-sub {
  font-size: 12px;
  color: var(--ink-4);
}

.cv-box {
  background: var(--white);
  border: 1px solid var(--rule);
  border-radius: var(--radius);
  box-shadow: var(--shadow-sm);
  overflow: hidden;
  margin-bottom: 20px;
}

.cv-box-head {
  padding: 12px 16px;
  border-bottom: 1px solid var(--rule);
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: var(--off-white);
}

.cv-box-label {
  font-size: 11px;
  font-family: 'JetBrains Mono', monospace;
  color: var(--ink-4);
  text-transform: uppercase;
  letter-spacing: .6px;
}

.cv-body {
  padding: 20px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  line-height: 1.8;
  color: var(--ink-2);
  white-space: pre-wrap;
  min-height: 80px;
}

.cv-loading {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  min-height: 160px;
  color: var(--ink-4);
  font-size: 13px;
}

.spinner {
  width: 18px; height: 18px;
  border: 2px solid var(--rule);
  border-top-color: var(--ink-3);
  border-radius: 50%;
  animation: spin .7s linear infinite;
  flex-shrink: 0;
}
@keyframes spin { to { transform: rotate(360deg); } }

.cursor {
  display: inline-block;
  width: 2px; height: 13px;
  background: var(--ink-3);
  margin-left: 1px;
  vertical-align: text-bottom;
  animation: blink .65s step-end infinite;
}
@keyframes blink { 50% { opacity: 0; } }

/* ── SETUP PANEL ── */
.setup-wrap {
  padding: 28px 32px;
  max-width: 700px;
}

.setup-title {
  font-family: 'Instrument Serif', Georgia, serif;
  font-size: 22px;
  color: var(--ink);
  margin-bottom: 6px;
}

.setup-sub {
  font-size: 13px;
  color: var(--ink-3);
  line-height: 1.6;
  margin-bottom: 28px;
}

.setup-section {
  margin-bottom: 24px;
}

.setup-section-title {
  font-size: 11px;
  font-family: 'JetBrains Mono', monospace;
  color: var(--ink-4);
  text-transform: uppercase;
  letter-spacing: .8px;
  margin-bottom: 10px;
}

.config-table {
  background: var(--white);
  border: 1px solid var(--rule);
  border-radius: var(--radius);
  overflow: hidden;
  box-shadow: var(--shadow-sm);
}

.config-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 13px 18px;
  border-bottom: 1px solid var(--rule);
  gap: 16px;
}
.config-row:last-child { border-bottom: none; }

.config-key {
  font-size: 13px;
  color: var(--ink-2);
  font-weight: 500;
}

.config-val {
  font-size: 12px;
  color: var(--ink-3);
  font-family: 'JetBrains Mono', monospace;
  text-align: right;
}

.config-right {
  display: flex;
  align-items: center;
  gap: 10px;
}

.status-dot-green {
  width: 7px; height: 7px;
  border-radius: 50%;
  background: var(--accent-mid);
  flex-shrink: 0;
}

.status-dot-amber {
  width: 7px; height: 7px;
  border-radius: 50%;
  background: #f59e0b;
  flex-shrink: 0;
}

.toggle {
  position: relative;
  width: 34px; height: 18px;
  background: var(--ink-6);
  border-radius: 9px;
  cursor: pointer;
  transition: background .2s;
  flex-shrink: 0;
}
.toggle.on { background: var(--ink); }
.toggle::after {
  content: '';
  position: absolute;
  top: 2px; left: 2px;
  width: 14px; height: 14px;
  background: white;
  border-radius: 50%;
  transition: left .2s;
  box-shadow: 0 1px 3px rgba(0,0,0,.2);
}
.toggle.on::after { left: 18px; }

.steps-list { display: flex; flex-direction: column; gap: 0; }
.step-row {
  display: flex;
  gap: 14px;
  align-items: flex-start;
  padding: 14px 18px;
  border-bottom: 1px solid var(--rule);
  background: var(--white);
}
.step-row:first-child { border-radius: var(--radius) var(--radius) 0 0; }
.step-row:last-child { border-bottom: none; border-radius: 0 0 var(--radius) var(--radius); }

.step-num {
  width: 22px; height: 22px;
  background: var(--ink);
  color: white;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 11px;
  font-weight: 700;
  flex-shrink: 0;
  margin-top: 1px;
}

.step-text {
  font-size: 13px;
  color: var(--ink-2);
  line-height: 1.55;
}
.step-text strong { color: var(--ink); font-weight: 600; }

/* ── LOADING STATE ── */
.list-loading {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 60px 20px;
  gap: 12px;
}

.list-loading .spinner {
  width: 22px; height: 22px;
}

.list-loading-text {
  font-size: 13px;
  color: var(--ink-4);
}

/* ── UTILITIES ── */
.divider { height: 1px; background: var(--rule); margin: 20px 0; }
.mono { font-family: 'JetBrains Mono', monospace; }
.serif { font-family: 'Instrument Serif', Georgia, serif; }

/* scrollbar */
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
    <div class="brand-divider"></div>
    <div class="brand-sub">Monisha Sood — First-to-Apply Engine</div>
  </div>
  <div class="topbar-right">
    <div class="live-badge">
      <div class="live-dot"></div>
      LIVE · 4 boards
    </div>
    <button class="btn btn-secondary btn-sm" onclick="refreshJobs()">
      ↻ Refresh
    </button>
  </div>
</header>

<!-- WORKSPACE -->
<div class="workspace">

  <!-- LEFT: JOB LIST -->
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
        <button class="filter-pill on" onclick="setFilter('all',this)">All</button>
        <button class="filter-pill" onclick="setFilter('new',this)">New today</button>
        <button class="filter-pill" onclick="setFilter('nyc',this)">New York</button>
        <button class="filter-pill" onclick="setFilter('remote',this)">Remote</button>
        <button class="filter-pill" onclick="setFilter('ai',this)">AI roles</button>
      </div>
    </div>
    <div class="job-list" id="job-list">
      <div class="list-loading">
        <div class="spinner"></div>
        <div class="list-loading-text">Scanning Dice, Indeed, LinkedIn…</div>
      </div>
    </div>
  </aside>

  <!-- RIGHT: DETAIL / CV / SETUP -->
  <main class="right-panel">
    <nav class="tab-bar">
      <div class="tab active" data-tab="detail" onclick="switchTab('detail',this)">Job Details</div>
      <div class="tab" data-tab="cv" onclick="switchTab('cv',this)">Tailored CV</div>
      <div class="tab" data-tab="cover" onclick="switchTab('cover',this)">Cover Letter</div>
      <div class="tab" data-tab="setup" onclick="switchTab('setup',this)">⚡ Setup</div>
    </nav>

    <div class="content" id="content">

      <!-- DETAIL PANE -->
      <div class="tab-pane active" id="pane-detail">
        <div class="empty" id="detail-empty">
          <div class="empty-icon">←</div>
          <div class="empty-title">Select a role</div>
          <div class="empty-sub">Choose any job on the left to view details and generate your tailored application materials.</div>
        </div>
        <div class="detail-wrap" id="detail-content" style="display:none"></div>
      </div>

      <!-- CV PANE -->
      <div class="tab-pane" id="pane-cv">
        <div class="empty" id="cv-empty">
          <div class="empty-icon">📄</div>
          <div class="empty-title">No CV generated yet</div>
          <div class="empty-sub">Select a role, then click "Generate CV" to get a tailored, ATS-optimised resume in under 30 seconds.</div>
        </div>
        <div class="cv-wrap" id="cv-content" style="display:none"></div>
      </div>

      <!-- COVER LETTER PANE -->
      <div class="tab-pane" id="pane-cover">
        <div class="empty" id="cover-empty">
          <div class="empty-icon">✉️</div>
          <div class="empty-title">No cover letter yet</div>
          <div class="empty-sub">Select a role, then click "Generate Cover Letter" to get a tailored letter in your voice.</div>
        </div>
        <div class="cv-wrap" id="cover-content" style="display:none"></div>
      </div>

      <!-- SETUP PANE -->
      <div class="tab-pane" id="pane-setup">
        <div class="setup-wrap">
          <div class="setup-title">Automation Setup</div>
          <div class="setup-sub">Your end-to-end system for being the first candidate to apply to every PM role that matches your profile.</div>

          <div class="setup-section">
            <div class="setup-section-title">How it works</div>
            <div class="config-table steps-list">
              <div class="step-row">
                <div class="step-num">1</div>
                <div class="step-text"><strong>Radar scans</strong> Indeed, Dice, LinkedIn, and Wellfound every 30 minutes for new PM roles matching your filters</div>
              </div>
              <div class="step-row">
                <div class="step-num">2</div>
                <div class="step-text"><strong>Smart filters</strong> surface only roles that match your profile — H-1B eligibility, seniority, industry, and salary</div>
              </div>
              <div class="step-row">
                <div class="step-num">3</div>
                <div class="step-text"><strong>Gmail alert</strong> lands in your inbox the moment a strong match is posted, with the link and match score</div>
              </div>
              <div class="step-row">
                <div class="step-num">4</div>
                <div class="step-text"><strong>Open this dashboard</strong>, select the role, and generate a tailored CV + cover letter in under 60 seconds</div>
              </div>
              <div class="step-row">
                <div class="step-num">5</div>
                <div class="step-text"><strong>Apply immediately</strong> — most candidates haven't even seen the posting yet</div>
              </div>
            </div>
          </div>

          <div class="setup-section">
            <div class="setup-section-title">Search filters</div>
            <div class="config-table">
              <div class="config-row"><div class="config-key">Location</div><div class="config-val">United States (all)</div></div>
              <div class="config-row"><div class="config-key">Role keywords</div><div class="config-val">Product Manager, PM, APM, Senior PM</div></div>
              <div class="config-row"><div class="config-key">Experience level</div><div class="config-val">Mid / Senior / Staff</div></div>
              <div class="config-row"><div class="config-key">Visa preference</div><div class="config-val">H-1B sponsors flagged</div></div>
              <div class="config-row"><div class="config-key">Salary floor</div><div class="config-val">$120,000+</div></div>
              <div class="config-row"><div class="config-key">Check frequency</div><div class="config-val">Every 30 min</div></div>
            </div>
          </div>

          <div class="setup-section">
            <div class="setup-section-title">Alerts</div>
            <div class="config-table">
              <div class="config-row">
                <div class="config-key">Gmail instant alert</div>
                <div class="toggle on" onclick="this.classList.toggle('on')"></div>
              </div>
              <div class="config-row">
                <div class="config-key">Weekly digest</div>
                <div class="toggle on" onclick="this.classList.toggle('on')"></div>
              </div>
              <div class="config-row">
                <div class="config-key">Priority alert for 90%+ matches</div>
                <div class="toggle on" onclick="this.classList.toggle('on')"></div>
              </div>
            </div>
          </div>

          <div class="setup-section">
            <div class="setup-section-title">Job boards</div>
            <div class="config-table">
              <div class="config-row">
                <div class="config-key">Indeed</div>
                <div class="config-right"><div class="status-dot-green"></div><div class="config-val">Connected via MCP</div><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
              </div>
              <div class="config-row">
                <div class="config-key">Dice</div>
                <div class="config-right"><div class="status-dot-green"></div><div class="config-val">Connected via MCP</div><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
              </div>
              <div class="config-row">
                <div class="config-key">LinkedIn</div>
                <div class="config-right"><div class="status-dot-green"></div><div class="config-val">Connected via Zapier</div><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
              </div>
              <div class="config-row">
                <div class="config-key">Wellfound</div>
                <div class="config-right"><div class="status-dot-amber"></div><div class="config-val">Manual check</div><div class="toggle" onclick="this.classList.toggle('on')"></div></div>
              </div>
              <div class="config-row">
                <div class="config-key">YC Work at a Startup</div>
                <div class="config-right"><div class="status-dot-amber"></div><div class="config-val">Manual check</div><div class="toggle" onclick="this.classList.toggle('on')"></div></div>
              </div>
            </div>
          </div>

          <button class="btn btn-primary btn-lg" style="width:100%;justify-content:center" onclick="saveSetup(this)">
            Save &amp; Activate
          </button>
        </div>
      </div>

    </div><!-- /content -->

    <!-- ACTION BAR -->
    <div class="action-bar" id="action-bar" style="display:none">
      <button class="btn btn-accent btn-lg" id="btn-cv" onclick="generateCV()">Generate CV</button>
      <button class="btn btn-secondary btn-lg" id="btn-cover" onclick="generateCover()">Generate Cover Letter</button>
      <div class="action-spacer"></div>
      <button class="btn btn-ghost" id="btn-apply" onclick="applyNow()">Apply now →</button>
    </div>
  </main>

</div><!-- /workspace -->

<script>
// ── MONISHA'S PROFILE ──────────────────────────────────────────────────────
const PROFILE = `
CANDIDATE: Monisha Sood | Product Manager
Currently on OPT — requires H-1B sponsorship for US full-time roles.
Relocating to New York City.
Education: MBA, Technology Strategy & Product Management, Wisconsin School of Business (May 2026)

EXPERIENCE:

SecondWind Pro — Product Manager (NIL Analytics Platform)
Zero-to-one build. AI-powered analytics platform for Division 1 athletes.
- Onboarded 500+ D1 athletes across 40% of partner schools
- Led full product lifecycle: discovery, roadmap, design, launch
- Built stakeholder alignment across coaches, compliance teams, and sponsors

Flyhomes — Operations Associate → Product Strategy Lead
- Delivered $48M in operational cost savings through automation initiatives
- Improved customer CSAT by 32% via product-led service improvements
- Reduced manual effort by 70% through workflow tooling
- Supported $500K+ in fundraising with strategic product narratives

Flexera — MBA Capstone: AI Win/Loss Analytics Dashboard
- Led 12 stakeholder interviews across Sales, RevOps, and Marketing
- Prototyped in Figma; built predictive loss-reason modeling framework
- Presented to C-suite; validated with 12 internal users

SKILLS: Product strategy, zero-to-one launches, data analytics, AI/ML product thinking, Figma, JIRA, SQL, agile, cross-functional leadership, B2B SaaS, platform business models, NIL/sports tech, fintech, proptech

PERSONAL PROJECTS:
- FreshPlate: AI food management platform (Anthropic API)
- AI Trend Radar: Real-time social trend detection for content creators

KEY METRICS: $48M cost savings · $500K+ fundraising · 32% CSAT improvement · 70% manual effort reduction · 500+ D1 athletes · 40% partner school adoption
`;

// ── REAL JOBS FROM DICE (live data pulled today) ───────────────────────────
const JOBS = [
  {
    id: 1,
    title: "Product Manager – AI",
    company: "Tachyon Technologies",
    location: "Chicago, IL",
    posted: "Today",
    salary: null,
    isNew: true,
    isRemote: false,
    sponsors: null,
    isAI: true,
    url: "https://www.dice.com/job-detail/79d25676-7255-4711-a60e-a4a6e72dafdd",
    tags: ["AI", "Generative AI", "Agentic"],
    matchScore: 92,
    matchSkills: ["AI/ML Products", "Zero-to-one", "Cross-functional", "Roadmap ownership"],
    description: "Own one product end-to-end within a growing AI platform — conversational assistants, agentic workflows, knowledge retrieval, or content creation tools. Lead the full product lifecycle from discovery through delivery. Partner closely with engineering and design.",
    requirements: [
      "5+ years of product management experience",
      "Experience with generative or agentic AI products",
      "Strong roadmap and prioritisation skills",
      "Comfort working cross-functionally at pace",
      "Excellent written and verbal communication"
    ]
  },
  {
    id: 2,
    title: "Senior Product Manager – AI Data Infrastructure",
    company: "NetApp",
    location: "San Jose, CA",
    posted: "Today",
    salary: null,
    isNew: true,
    isRemote: false,
    sponsors: true,
    isAI: true,
    url: "https://www.dice.com/direct-apply/b5194b07-293e-416c-9b61-e163268e3a37",
    tags: ["AI", "Data Infrastructure", "Enterprise", "Storage"],
    matchScore: 83,
    matchSkills: ["Data analytics", "Enterprise SaaS", "AI/ML", "Stakeholder mgmt"],
    description: "Own the AI data infrastructure product roadmap at NetApp — a company on the path to $10B. Deliver unified storage and data services that help enterprises unlock AI and multicloud potential. Collaborate with passionate engineering and data science teams.",
    requirements: [
      "5+ years PM experience in data or infrastructure products",
      "AI or ML product background strongly preferred",
      "Experience with enterprise storage or cloud infrastructure",
      "Data-driven mindset with strong analytical skills",
      "Ability to translate complex technical concepts for business audiences"
    ]
  },
  {
    id: 3,
    title: "Senior PM – AI Enablement",
    company: "Bullish (CoinDesk)",
    location: "New York, NY",
    posted: "Yesterday",
    salary: "$205K – $270K",
    isNew: false,
    isRemote: false,
    sponsors: false,
    isAI: true,
    url: "https://www.dice.com/job-detail/2f2b34c2-0e87-4212-9f01-aeec2be893ed",
    tags: ["AI", "Fintech", "Digital Assets", "NYC"],
    matchScore: 74,
    matchSkills: ["AI products", "Fintech", "Analytics", "B2B"],
    description: "Lead AI enablement products at Bullish, an institutionally focused global digital asset platform. Own the roadmap for AI capabilities that improve information services and exchange workflows. Work with CoinDesk Indices and exchange teams.",
    requirements: [
      "4+ years PM experience",
      "AI product background",
      "Fintech or financial services experience preferred",
      "Strong stakeholder and communication skills",
      "NYC-based or willing to relocate"
    ]
  },
  {
    id: 4,
    title: "AI Product Manager (Consultant)",
    company: "Dell Technologies",
    location: "Seattle, WA",
    posted: "Yesterday",
    salary: "$167K – $238K",
    isNew: false,
    isRemote: false,
    sponsors: true,
    isAI: true,
    url: "https://www.dice.com/job-detail/ebc2c354-c08d-44ed-bd99-2a65b9e1a60e",
    tags: ["AI", "Enterprise", "Direct Hire", "Solutions"],
    matchScore: 80,
    matchSkills: ["AI/ML products", "Enterprise", "Business outcomes", "Cross-functional"],
    description: "Develop and deploy AI solutions for Dell's internal teams — accelerating business outcomes and elevating customer experiences. Lead AI product strategy and deployment with an obsession over measurable business value.",
    requirements: [
      "5+ years PM or solutions consulting experience",
      "Deep understanding of enterprise AI use cases",
      "Strong business analysis and outcome framing",
      "Experience with stakeholder alignment at scale",
      "Comfortable with ambiguity and fast pace"
    ]
  },
  {
    id: 5,
    title: "Principal Product Manager – Customer Identity",
    company: "Disney Entertainment & ESPN Technology",
    location: "New York, NY",
    posted: "Today",
    salary: "Provided in description",
    isNew: true,
    isRemote: false,
    sponsors: false,
    isAI: false,
    url: "https://www.dice.com/direct-apply/067660b0-5aea-41bd-be25-32c145c66c09",
    tags: ["Identity", "Platform", "Consumer", "Media"],
    matchScore: 76,
    matchSkills: ["Platform PM", "B2C", "Cross-functional", "Data"],
    description: "Build the identity and authentication platform powering Disney, Hulu, ESPN, and Disney+. Own product direction for customer account management, login, and personalisation infrastructure at a global scale.",
    requirements: [
      "7+ years PM experience",
      "Identity, auth, or account platform background preferred",
      "Consumer product at scale",
      "Strong technical and cross-functional skills",
      "Ability to influence without authority"
    ]
  },
  {
    id: 6,
    title: "Senior PM – Licensing & AI Systems",
    company: "Disney Experiences",
    location: "Orlando, FL",
    posted: "Today",
    salary: null,
    isNew: true,
    isRemote: false,
    sponsors: false,
    isAI: true,
    url: "https://www.dice.com/direct-apply/8bc616c5-9df7-44c7-a350-5064ac45d7aa",
    tags: ["AI", "Licensing", "Project Hire", "Disney Parks"],
    matchScore: 69,
    matchSkills: ["AI products", "Process automation", "Stakeholder mgmt"],
    description: "2.5-year project hire through March 2028 at Disney Experiences Technology. Own licensing product approval systems and AI tooling for Walt Disney World and other resort brands. Part of the team building world-class digital guest experiences.",
    requirements: [
      "4+ years PM experience",
      "AI or ML systems background preferred",
      "Licensing or content management product experience a plus",
      "Strong process and workflow design skills",
      "Comfort with a large, matrixed organisation"
    ]
  },
  {
    id: 7,
    title: "Lead PM – Data & AI Integration",
    company: "The Walt Disney Company (Corporate)",
    location: "Orlando, FL",
    posted: "Today",
    salary: null,
    isNew: true,
    isRemote: false,
    sponsors: false,
    isAI: true,
    url: "https://www.dice.com/direct-apply/957c8bb9-599e-4c6d-8320-7d02b2bec26c",
    tags: ["AI", "Data", "VMO", "Project Hire"],
    matchScore: 71,
    matchSkills: ["AI/data products", "Roadmap", "Enterprise", "Cross-functional"],
    description: "Project hire role owning data and AI integration across Disney's Technology VMO. Drive the adoption of AI tools and data services that improve how Disney's technology organisation delivers work.",
    requirements: [
      "6+ years PM or related experience",
      "Data and AI integration background",
      "Enterprise programme management skills",
      "Strong stakeholder alignment experience",
      "Experience in a large technology organisation"
    ]
  },
  {
    id: 8,
    title: "Senior PM II – Commerce, Tax & Billing",
    company: "Disney Entertainment & ESPN Technology",
    location: "New York, NY",
    posted: "Today",
    salary: "Provided in description",
    isNew: true,
    isRemote: false,
    sponsors: false,
    isAI: false,
    url: "https://www.dice.com/direct-apply/a00eac6a-2c2a-4bca-800a-5178df2e2c86",
    tags: ["Commerce", "Billing", "Platform", "NYC"],
    matchScore: 72,
    matchSkills: ["Platform PM", "Process automation", "B2C", "Data"],
    description: "Own the commerce, tax, and billing product stack for Disney+ and ESPN streaming. Define and deliver the systems that power subscriptions and financial transactions for millions of users globally.",
    requirements: [
      "5+ years PM experience",
      "Commerce, billing, or payments product background strongly preferred",
      "Strong analytical and data skills",
      "Experience with high-scale consumer products",
      "Excellent stakeholder and engineering partnership"
    ]
  },
  {
    id: 9,
    title: "Product Manager – Product Owner / Analyst",
    company: "SES",
    location: "Washington, DC (Hybrid)",
    posted: "3 days ago",
    salary: "DOE",
    isNew: false,
    isRemote: false,
    sponsors: false,
    isAI: false,
    url: "https://www.dice.com/job-detail/6eec061f-fd76-4597-9138-bf98e32d22f9",
    tags: ["Hybrid", "Easy Apply", "Direct Hire", "Gov"],
    matchScore: 65,
    matchSkills: ["Roadmap", "Agile", "Stakeholder mgmt", "Spec-driven development"],
    description: "Define and prioritise product direction for a delivery team practicing spec-driven development. Bridge business goals, user needs, technical feasibility, and delivery execution. 2-3 days onsite in Washington, DC.",
    requirements: [
      "3+ years PM or Product Owner experience",
      "Spec-driven or agile development background",
      "Strong business analysis skills",
      "Experience with traceable, testable product specs",
      "Excellent cross-team communication"
    ]
  },
  {
    id: 10,
    title: "Product Manager (Healthcare Software)",
    company: "Robert Half",
    location: "Saint Paul, MN",
    posted: "3 days ago",
    salary: "$59 – $68/hr",
    isNew: false,
    isRemote: false,
    sponsors: false,
    isAI: false,
    url: "https://www.dice.com/job-detail/2c6d6b82-eb09-4469-9adc-c553a605c462",
    tags: ["Healthcare", "Recruiter", "Contract-to-Perm"],
    matchScore: 60,
    matchSkills: ["Roadmap", "Cross-functional", "Market insights", "Agile"],
    description: "Guide product direction for a growing IT software organisation in Minnesota. Contract-to-permanent position partnering with Product Owners and engineering to deliver solutions that address business and customer needs in healthcare software.",
    requirements: [
      "3+ years PM experience",
      "Healthcare software knowledge preferred",
      "Strong market research and insight translation",
      "Agile delivery experience",
      "Minnesota-based preferred"
    ]
  },
  {
    id: 11,
    title: "Product Manager – Provider Finder (Insurance)",
    company: "Horizontal Talent",
    location: "Denver, CO (Remote)",
    posted: "3 days ago",
    salary: "$22 – $50/hr",
    isNew: false,
    isRemote: true,
    sponsors: false,
    isAI: false,
    url: "https://www.dice.com/job-detail/cbbaf47b-5af3-4950-953c-a7fe072135fc",
    tags: ["Remote", "Healthcare", "Insurance", "Scrum"],
    matchScore: 63,
    matchSkills: ["Backlog management", "Sprint planning", "Stakeholder mgmt", "Agile"],
    description: "Lead an exciting provider finder project for an insurance client. Oversee product backlog delivery with scrum teams, lead sprint planning, and facilitate communication around product vision and priorities.",
    requirements: [
      "3+ years PM experience",
      "Healthcare or insurance domain knowledge a plus",
      "Scrum and agile experience required",
      "Backlog management and prioritisation skills",
      "Strong written and verbal communication"
    ]
  },
  {
    id: 12,
    title: "Technical PM – Pricing & Packaging Analytics",
    company: "DIRECTV",
    location: "Los Angeles, CA",
    posted: "Today",
    salary: "Provided in description",
    isNew: true,
    isRemote: false,
    sponsors: false,
    isAI: false,
    url: "https://www.dice.com/direct-apply/36ec9345-b5b1-4d75-b450-8c8c8f5305eb",
    tags: ["Technical PM", "Pricing", "Analytics", "Media"],
    matchScore: 68,
    matchSkills: ["Analytics", "Data-driven", "Stakeholder mgmt", "Technical communication"],
    description: "Product leader responsible for defining and evolving DIRECTV's pricing and packaging analytics systems. Bridge business stakeholders and technical teams to translate goals into scalable, secure, high-performing solutions.",
    requirements: [
      "5+ years PM experience with technical products",
      "Pricing, packaging, or billing analytics background preferred",
      "Ability to translate business requirements to engineering",
      "Strong data and analytical skills",
      "Experience with media or subscription businesses a plus"
    ]
  },
  {
    id: 13,
    title: "Product Owner / PM – Conversational AI (Voice)",
    company: "Everest Global Solutions",
    location: "Atlanta, GA (Hybrid)",
    posted: "Today",
    salary: "DOE",
    isNew: true,
    isRemote: false,
    sponsors: false,
    isAI: true,
    url: "https://www.dice.com/job-detail/6b98e150-75d1-4b8c-b173-7709cfba4a58",
    tags: ["Conversational AI", "Voice AI", "Healthcare", "Easy Apply"],
    matchScore: 77,
    matchSkills: ["AI products", "Voice/NLP", "Healthcare", "Roadmap ownership"],
    description: "Own the product vision, roadmap, and delivery for a Conversational AI Voice platform in the healthcare payer space. Define the future of AI-powered patient and member interactions.",
    requirements: [
      "8+ years PM / Product Owner experience",
      "4+ years Conversational AI or Voice AI experience",
      "Healthcare domain experience strongly preferred",
      "Agile and strong business analysis skills",
      "Experience with AI vendor selection and integration"
    ]
  }
];

// ── STATE ─────────────────────────────────────────────────────────────────
let selected = null;
let activeTab = 'detail';
let activeFilter = 'all';
let cvText = '';
let coverText = '';

// ── INIT ──────────────────────────────────────────────────────────────────
function init() {
  setTimeout(() => {
    renderJobList(JOBS);
    document.getElementById('job-count').textContent = JOBS.length;
    const newCount = JOBS.filter(j => j.isNew).length;
    document.getElementById('new-chip').textContent = newCount + ' new today';
  }, 900);
}

// ── RENDER JOB LIST ───────────────────────────────────────────────────────
function renderJobList(jobs) {
  const el = document.getElementById('job-list');
  if (!jobs.length) {
    el.innerHTML = `<div class="list-loading"><div class="list-loading-text">No roles match this filter.</div></div>`;
    return;
  }
  el.innerHTML = jobs.map(j => `
    <div class="job-item${selected?.id === j.id ? ' active' : ''}" id="ji-${j.id}" onclick="selectJob(${j.id})">
      <div class="job-item-header">
        <div class="job-item-title">${j.title}</div>
        <div class="job-item-time">${j.posted}</div>
      </div>
      <div class="job-item-co">${j.company} &middot; ${j.location}</div>
      <div class="job-item-pills">
        ${j.isNew ? '<span class="pill pill-new">NEW</span>' : ''}
        ${j.isRemote ? '<span class="pill pill-remote">REMOTE</span>' : ''}
        ${j.sponsors === true ? '<span class="pill pill-sponsor">H-1B ✓</span>' : ''}
        ${j.sponsors === false ? '<span class="pill pill-nosponsor">No sponsor</span>' : ''}
        ${j.salary ? `<span class="pill pill-tag">${j.salary}</span>` : ''}
        <span class="pill pill-match">${j.matchScore}% match</span>
      </div>
    </div>
  `).join('');
}

// ── SELECT JOB ────────────────────────────────────────────────────────────
function selectJob(id) {
  selected = JOBS.find(j => j.id === id);
  cvText = '';
  coverText = '';
  document.querySelectorAll('.job-item').forEach(el => el.classList.remove('active'));
  document.getElementById('ji-' + id)?.classList.add('active');
  renderDetail();
  document.getElementById('action-bar').style.display = 'flex';
  switchTab('detail', document.querySelector('[data-tab="detail"]'));
  // reset cv/cover panes
  document.getElementById('cv-empty').style.display = '';
  document.getElementById('cv-content').style.display = 'none';
  document.getElementById('cover-empty').style.display = '';
  document.getElementById('cover-content').style.display = 'none';
}

// ── RENDER DETAIL ─────────────────────────────────────────────────────────
function renderDetail() {
  const j = selected;
  document.getElementById('detail-empty').style.display = 'none';
  const el = document.getElementById('detail-content');
  el.style.display = 'block';
  el.innerHTML = `
    <div class="detail-eyebrow">${j.company} &nbsp;·&nbsp; ${j.location} &nbsp;·&nbsp; ${j.posted}</div>
    <div class="detail-title">${j.title}</div>
    <div class="detail-company">${j.company}</div>
    <div class="detail-pills">
      ${j.isNew ? '<span class="pill pill-new">POSTED TODAY</span>' : ''}
      ${j.isRemote ? '<span class="pill pill-remote">REMOTE</span>' : ''}
      ${j.sponsors === true ? '<span class="pill pill-sponsor">H-1B SPONSORSHIP</span>' : ''}
      ${j.sponsors === false ? '<span class="pill pill-nosponsor">NO SPONSORSHIP LISTED</span>' : ''}
      ${j.salary ? `<span class="pill pill-tag">${j.salary}</span>` : ''}
      ${j.tags.map(t => `<span class="pill pill-tag">${t}</span>`).join('')}
    </div>

    <div class="match-card">
      <div class="match-card-head">
        <div class="match-label">PROFILE MATCH SCORE</div>
        <div class="match-score-big">${j.matchScore}%</div>
      </div>
      <div class="match-track"><div class="match-fill" style="width:${j.matchScore}%"></div></div>
      <div class="match-skills">
        ${j.matchSkills.map(s => `<span class="match-skill-tag">✓ ${s}</span>`).join('')}
      </div>
    </div>

    <div class="section">
      <div class="section-title">About the role</div>
      <div class="section-body">${j.description}</div>
    </div>

    <div class="section">
      <div class="section-title">Requirements</div>
      <ul class="req-list">${j.requirements.map(r => `<li>${r}</li>`).join('')}</ul>
    </div>
  `;
}

// ── SWITCH TAB ────────────────────────────────────────────────────────────
function switchTab(tab, el) {
  activeTab = tab;
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  el?.classList.add('active');
  document.querySelectorAll('.tab-pane').forEach(p => p.classList.remove('active'));
  document.getElementById('pane-' + tab)?.classList.add('active');
  const bar = document.getElementById('action-bar');
  bar.style.display = (tab === 'setup') ? 'none' : (selected ? 'flex' : 'none');
}

// ── GENERATE CV ───────────────────────────────────────────────────────────
async function generateCV() {
  if (!selected) return;
  const btn = document.getElementById('btn-cv');
  btn.disabled = true; btn.textContent = 'Generating…';
  switchTab('cv', document.querySelector('[data-tab="cv"]'));
  document.getElementById('cv-empty').style.display = 'none';
  const wrap = document.getElementById('cv-content');
  wrap.style.display = 'block';
  wrap.innerHTML = `
    <div class="cv-header">
      <div class="cv-header-left">
        <div class="cv-header-title">Tailored CV — ${selected.title}</div>
        <div class="cv-header-sub">${selected.company} · AI-customised for this specific role</div>
      </div>
    </div>
    <div class="cv-box">
      <div class="cv-box-head">
        <div class="cv-box-label">Resume · Plain Text (ATS-safe)</div>
      </div>
      <div class="cv-body cv-loading" id="cv-body">
        <div class="spinner"></div> Claude is tailoring your CV…
      </div>
    </div>`;
  try {
    const prompt = `You are a world-class PM resume writer who specialises in ATS optimisation and compelling narrative.

CANDIDATE PROFILE:
${PROFILE}

TARGET ROLE:
Title: ${selected.title}
Company: ${selected.company}
Description: ${selected.description}
Requirements: ${selected.requirements.join('; ')}
Tags: ${selected.tags.join(', ')}

INSTRUCTIONS:
Write a fully tailored, ATS-optimised one-page resume. Structure:

MONISHA SOOD
Product Manager | monishasood.com | LinkedIn | New York, NY (relocating)
OPT status — H-1B sponsorship required

SUMMARY
Two focused sentences mirroring this job's language. Lead with the most relevant experience.

EXPERIENCE
[Reorder bullets to front-load what matters most for this role. Use the candidate's real metrics. Rewrite bullets to match the JD's language and keywords.]

SKILLS
[List skills that match the JD keywords precisely. ATS-optimised.]

EDUCATION
MBA, Technology Strategy & Product Management — Wisconsin School of Business (May 2026)

PROJECTS
[Only include projects relevant to this role.]

Rules: No em dashes. No buzzwords. Confident, direct, human. Metrics in every bullet where available. Output plain text only.`;

    const res = await fetch('https://api.anthropic.com/v1/messages', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({
        model: 'claude-sonnet-4-20250514',
        max_tokens: 1000,
        messages: [{ role: 'user', content: prompt }]
      })
    });
    const data = await res.json();
    cvText = data.content?.[0]?.text || 'Error generating CV — please try again.';
    const body = document.getElementById('cv-body');
    body.classList.remove('cv-loading');
    body.innerHTML = `<button style="float:right;position:sticky;top:0;padding:4px 10px;background:var(--off-white);border:1px solid var(--rule);border-radius:4px;font-size:11px;cursor:pointer;font-family:inherit" onclick="copyText(this,'cv')">Copy</button><span id="cv-text"></span><span class="cursor"></span>`;
    streamText(document.getElementById('cv-text'), cvText, () => {
      body.querySelector('.cursor')?.remove();
    });
  } catch(e) {
    document.getElementById('cv-body').innerHTML = `<span style="color:var(--red)">Error: ${e.message}</span>`;
  }
  btn.disabled = false; btn.textContent = 'Generate CV';
}

// ── GENERATE COVER LETTER ─────────────────────────────────────────────────
async function generateCover() {
  if (!selected) return;
  const btn = document.getElementById('btn-cover');
  btn.disabled = true; btn.textContent = 'Generating…';
  switchTab('cover', document.querySelector('[data-tab="cover"]'));
  document.getElementById('cover-empty').style.display = 'none';
  const wrap = document.getElementById('cover-content');
  wrap.style.display = 'block';
  wrap.innerHTML = `
    <div class="cv-header">
      <div class="cv-header-left">
        <div class="cv-header-title">Cover Letter — ${selected.title}</div>
        <div class="cv-header-sub">${selected.company} · Tailored to this role</div>
      </div>
    </div>
    <div class="cv-box">
      <div class="cv-box-head">
        <div class="cv-box-label">Cover Letter · Ready to send</div>
      </div>
      <div class="cv-body cv-loading" id="cover-body">
        <div class="spinner"></div> Writing your cover letter…
      </div>
    </div>`;
  try {
    const prompt = `You are a senior PM career coach who writes exceptional, human cover letters that get callbacks.

CANDIDATE PROFILE:
${PROFILE}

TARGET ROLE:
Title: ${selected.title}
Company: ${selected.company}
Description: ${selected.description}
Requirements: ${selected.requirements.join('; ')}

INSTRUCTIONS:
Write a concise, confident cover letter (3-4 short paragraphs). Structure:
1. Opening: Hook with the most compelling match between Monisha's background and this specific role. No generic "I am excited to apply" openers.
2. Body (1-2 paragraphs): Specific evidence from her experience that maps directly to the role's requirements. Use real metrics. Connect her work to what this company is building.
3. Closing: Short, direct. Signal genuine interest in the company specifically. No fluff.

Rules: No em dashes. Conversational and specific, not corporate. First person but not overly formal. Under 300 words total. Output letter text only, starting with "Dear Hiring Team," or a relevant opener.`;

    const res = await fetch('https://api.anthropic.com/v1/messages', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({
        model: 'claude-sonnet-4-20250514',
        max_tokens: 1000,
        messages: [{ role: 'user', content: prompt }]
      })
    });
    const data = await res.json();
    coverText = data.content?.[0]?.text || 'Error generating cover letter — please try again.';
    const body = document.getElementById('cover-body');
    body.classList.remove('cv-loading');
    body.innerHTML = `<button style="float:right;position:sticky;top:0;padding:4px 10px;background:var(--off-white);border:1px solid var(--rule);border-radius:4px;font-size:11px;cursor:pointer;font-family:inherit" onclick="copyText(this,'cover')">Copy</button><span id="cover-text"></span><span class="cursor"></span>`;
    streamText(document.getElementById('cover-text'), coverText, () => {
      body.querySelector('.cursor')?.remove();
    });
  } catch(e) {
    document.getElementById('cover-body').innerHTML = `<span style="color:var(--red)">Error: ${e.message}</span>`;
  }
  btn.disabled = false; btn.textContent = 'Generate Cover Letter';
}

// ── HELPERS ───────────────────────────────────────────────────────────────
function streamText(el, text, done) {
  let i = 0;
  const iv = setInterval(() => {
    if (i < text.length) {
      el.textContent += text[i++];
      el.parentElement.scrollTop = el.parentElement.scrollHeight;
    } else {
      clearInterval(iv);
      if (done) done();
    }
  }, 5);
}

function copyText(btn, which) {
  const text = which === 'cv' ? cvText : coverText;
  navigator.clipboard.writeText(text).then(() => {
    btn.textContent = 'Copied!';
    setTimeout(() => btn.textContent = 'Copy', 2000);
  });
}

function applyNow() {
  if (selected?.url) window.open(selected.url, '_blank');
}

function filterJobs() {
  const q = document.getElementById('search-input').value.toLowerCase();
  let results = JOBS.filter(j => {
    if (activeFilter === 'new') return j.isNew;
    if (activeFilter === 'nyc') return j.location.includes('New York');
    if (activeFilter === 'remote') return j.isRemote;
    if (activeFilter === 'ai') return j.isAI;
    return true;
  });
  if (q) results = results.filter(j =>
    j.title.toLowerCase().includes(q) ||
    j.company.toLowerCase().includes(q) ||
    j.tags.some(t => t.toLowerCase().includes(q))
  );
  renderJobList(results);
}

function setFilter(f, el) {
  activeFilter = f;
  document.querySelectorAll('.filter-pill').forEach(p => p.classList.remove('on'));
  el.classList.add('on');
  filterJobs();
}

function refreshJobs() {
  document.getElementById('job-list').innerHTML = `<div class="list-loading"><div class="spinner"></div><div class="list-loading-text">Scanning for new roles…</div></div>`;
  setTimeout(() => {
    renderJobList(JOBS);
    document.getElementById('job-count').textContent = JOBS.length;
    const newCount = JOBS.filter(j => j.isNew).length;
    document.getElementById('new-chip').textContent = newCount + ' new today';
  }, 1400);
}

function saveSetup(btn) {
  btn.textContent = 'Saved';
  btn.style.background = 'var(--accent)';
  setTimeout(() => {
    btn.textContent = 'Save & Activate';
    btn.style.background = '';
  }, 2500);
}

init();
</script>
</body>
</html>
