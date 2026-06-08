<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>PM Job Radar — Monisha Sood</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=DM+Mono:wght@400;500&family=Sora:wght@300;400;600;700&display=swap');
  * { margin: 0; padding: 0; box-sizing: border-box; }
  :root {
    --bg: #0a0a0f; --surface: #111118; --surface2: #1a1a26;
    --border: #2a2a3d; --accent: #7c6aff; --accent2: #ff6ab0;
    --green: #4dffa6; --text: #e8e8f0;
  }
  body { background: var(--bg); font-family: 'Sora', sans-serif; color: var(--text); min-height: 100vh; padding: 24px; font-size: 14px; }
  .header { display: flex; align-items: center; justify-content: space-between; margin-bottom: 28px; padding-bottom: 20px; border-bottom: 1px solid var(--border); }
  .logo { display: flex; align-items: center; gap: 12px; }
  .logo-icon { width: 36px; height: 36px; background: linear-gradient(135deg, var(--accent), var(--accent2)); border-radius: 10px; display: flex; align-items: center; justify-content: center; font-size: 18px; }
  .logo-text { font-size: 18px; font-weight: 700; letter-spacing: -0.5px; }
  .logo-sub { font-size: 11px; color: #555; font-family: 'DM Mono', monospace; margin-top: 2px; }
  .status-bar { display: flex; gap: 12px; align-items: center; }
  .status-dot { width: 8px; height: 8px; border-radius: 50%; background: var(--green); box-shadow: 0 0 8px var(--green); animation: pulse 2s infinite; }
  @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:.4} }
  .status-text { font-size: 12px; color: var(--green); font-family: 'DM Mono', monospace; }
  .btn { padding: 8px 16px; border-radius: 8px; border: none; cursor: pointer; font-family: 'Sora', sans-serif; font-size: 13px; font-weight: 600; transition: all .2s; }
  .btn-primary { background: var(--accent); color: white; }
  .btn-primary:hover { background: #6a58ee; transform: translateY(-1px); }
  .btn-ghost { background: transparent; color: var(--text); border: 1px solid var(--border); }
  .btn-ghost:hover { border-color: var(--accent); color: var(--accent); }
  .btn-sm { padding: 5px 12px; font-size: 12px; border-radius: 6px; }
  .btn:disabled { opacity: .5; cursor: not-allowed; transform: none; }
  .grid { display: grid; grid-template-columns: 380px 1fr; gap: 20px; height: calc(100vh - 130px); }
  .panel { background: var(--surface); border: 1px solid var(--border); border-radius: 14px; overflow: hidden; display: flex; flex-direction: column; }
  .panel-header { padding: 16px 20px; border-bottom: 1px solid var(--border); display: flex; align-items: center; justify-content: space-between; background: var(--surface2); }
  .panel-title { font-size: 13px; font-weight: 600; display: flex; align-items: center; gap: 8px; }
  .panel-title span { color: #44445a; font-weight: 400; }
  .search-bar { padding: 12px 16px; border-bottom: 1px solid var(--border); display: flex; gap: 8px; }
  .search-input { flex:1; background: var(--bg); border: 1px solid var(--border); border-radius: 8px; padding: 8px 12px; color: var(--text); font-family: 'Sora', sans-serif; font-size: 13px; outline: none; }
  .search-input:focus { border-color: var(--accent); }
  .search-input::placeholder { color: #33334a; }
  .filter-row { padding: 10px 16px; border-bottom: 1px solid var(--border); display: flex; gap: 6px; flex-wrap: wrap; }
  .filter-chip { padding: 4px 10px; border-radius: 20px; border: 1px solid var(--border); background: transparent; color: #666; font-size: 11px; cursor: pointer; transition: all .15s; font-family: 'Sora', sans-serif; }
  .filter-chip.active { background: var(--accent); border-color: var(--accent); color: white; }
  .filter-chip:hover:not(.active) { border-color: var(--accent); color: var(--accent); }
  .jobs-list { flex:1; overflow-y: auto; scrollbar-width: thin; scrollbar-color: var(--border) transparent; }
  .job-card { padding: 14px 16px; border-bottom: 1px solid var(--border); cursor: pointer; transition: background .15s; }
  .job-card:hover { background: var(--surface2); }
  .job-card.selected { background: rgba(124,106,255,.08); border-left: 3px solid var(--accent); }
  .job-card-top { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 6px; }
  .job-title { font-size: 13px; font-weight: 600; line-height: 1.3; }
  .job-company { font-size: 12px; color: #777; margin-top: 2px; }
  .job-meta { display: flex; gap: 6px; flex-wrap: wrap; margin-top: 8px; }
  .tag { padding: 2px 8px; border-radius: 4px; font-size: 10px; font-family: 'DM Mono', monospace; font-weight: 500; }
  .tag-new { background: rgba(77,255,166,.1); color: var(--green); border: 1px solid rgba(77,255,166,.2); }
  .tag-remote { background: rgba(124,106,255,.1); color: var(--accent); border: 1px solid rgba(124,106,255,.2); }
  .tag-sponsor { background: rgba(255,106,176,.1); color: var(--accent2); border: 1px solid rgba(255,106,176,.2); }
  .tag-salary { background: rgba(255,255,255,.05); color: #888; border: 1px solid var(--border); }
  .tag-match { background: rgba(124,106,255,.08); color: var(--accent); border: 1px solid rgba(124,106,255,.2); }
  .posted-time { font-size: 10px; color: #333; font-family: 'DM Mono', monospace; white-space: nowrap; }
  .right-panel { display: flex; flex-direction: column; }
  .tabs { display: flex; border-bottom: 1px solid var(--border); padding: 0 24px; background: var(--surface2); }
  .tab { padding: 12px 16px; font-size: 13px; cursor: pointer; color: #555; border-bottom: 2px solid transparent; transition: all .15s; font-weight: 500; }
  .tab.active { color: var(--accent); border-bottom-color: var(--accent); }
  .tab:hover:not(.active) { color: #888; }
  .detail-scroll { flex:1; overflow-y: auto; padding: 24px; scrollbar-width: thin; scrollbar-color: var(--border) transparent; }
  .empty-state { display: flex; flex-direction: column; align-items: center; justify-content: center; height: 100%; gap: 12px; }
  .empty-icon { font-size: 48px; opacity: .25; }
  .jd-title { font-size: 22px; font-weight: 700; letter-spacing: -.5px; margin-bottom: 6px; }
  .jd-company { font-size: 15px; color: #777; margin-bottom: 14px; }
  .jd-tags { display: flex; gap: 8px; flex-wrap: wrap; margin-bottom: 20px; }
  .match-bar { background: var(--surface2); border: 1px solid var(--border); border-radius: 10px; padding: 14px 16px; margin-bottom: 20px; }
  .match-bar-top { display: flex; justify-content: space-between; margin-bottom: 10px; }
  .match-label { font-size: 11px; color: #555; font-family: 'DM Mono', monospace; letter-spacing:.5px; }
  .match-score { font-size: 13px; font-weight: 700; color: var(--green); }
  .progress-track { height: 4px; background: var(--border); border-radius: 2px; overflow: hidden; }
  .progress-fill { height: 100%; border-radius: 2px; background: linear-gradient(90deg, var(--accent), var(--green)); transition: width .8s ease; }
  .match-skills { display: flex; gap: 6px; flex-wrap: wrap; margin-top: 10px; }
  .skill-match { padding: 3px 8px; border-radius: 4px; font-size: 11px; background: rgba(77,255,166,.08); color: var(--green); border: 1px solid rgba(77,255,166,.15); }
  .jd-section { margin-bottom: 20px; }
  .jd-section-title { font-size: 11px; font-family: 'DM Mono', monospace; color: #444; text-transform: uppercase; letter-spacing: 1px; margin-bottom: 10px; }
  .jd-text { font-size: 13px; color: #999; line-height: 1.7; }
  .jd-list { list-style: none; }
  .jd-list li { font-size: 13px; color: #999; line-height: 1.6; padding: 3px 0 3px 16px; position: relative; }
  .jd-list li::before { content: "→"; position: absolute; left: 0; color: var(--accent); font-size: 11px; top: 4px; }
  .action-bar { padding: 16px 24px; border-top: 1px solid var(--border); display: flex; gap: 10px; align-items: center; background: var(--surface2); }
  .cv-output { background: var(--bg); border: 1px solid var(--border); border-radius: 10px; padding: 16px; margin-top: 16px; font-family: 'DM Mono', monospace; font-size: 12px; line-height: 1.8; color: #ccc; white-space: pre-wrap; position: relative; max-height: 500px; overflow-y: auto; }
  .spinner { display: inline-block; width: 20px; height: 20px; border: 2px solid var(--border); border-top-color: var(--accent); border-radius: 50%; animation: spin .8s linear infinite; }
  @keyframes spin { to { transform: rotate(360deg); } }
  .streaming-cursor { display: inline-block; width: 2px; height: 14px; background: var(--accent); margin-left: 2px; animation: blink .7s step-end infinite; vertical-align: text-bottom; }
  @keyframes blink { 50%{opacity:0} }
  .copy-btn { padding: 4px 10px; background: var(--surface2); border: 1px solid var(--border); border-radius: 6px; color: #777; cursor: pointer; font-size: 11px; font-family: 'Sora', sans-serif; transition: all .15s; float: right; position: sticky; top: 0; }
  .copy-btn:hover { color: var(--accent); border-color: var(--accent); }
  .alert-config { background: var(--surface2); border: 1px solid var(--border); border-radius: 10px; padding: 4px 16px; margin-bottom: 16px; }
  .config-row { display: flex; align-items: center; justify-content: space-between; padding: 12px 0; border-bottom: 1px solid rgba(255,255,255,.03); }
  .config-row:last-child { border-bottom: none; }
  .config-label { font-size: 13px; color: #999; }
  .config-value { font-size: 12px; color: var(--accent); font-family: 'DM Mono', monospace; }
  .toggle { width: 36px; height: 20px; background: var(--border); border-radius: 10px; position: relative; cursor: pointer; transition: background .2s; flex-shrink: 0; }
  .toggle.on { background: var(--accent); }
  .toggle::after { content:''; position: absolute; top: 3px; left: 3px; width: 14px; height: 14px; background: white; border-radius: 50%; transition: left .2s; }
  .toggle.on::after { left: 19px; }
  .nbadge { background: var(--accent2); color: white; font-size: 10px; padding: 2px 6px; border-radius: 10px; font-weight: 700; font-family: 'DM Mono', monospace; }
  .section-label { font-size: 13px; font-weight: 600; color: #666; margin-bottom: 10px; margin-top: 20px; }
  .how-to-section { background: var(--surface2); border: 1px solid var(--border); border-radius: 10px; padding: 16px; margin-bottom: 20px; }
  .how-to-step { display: flex; gap: 12px; padding: 8px 0; border-bottom: 1px solid rgba(255,255,255,.03); }
  .how-to-step:last-child { border-bottom: none; }
  .step-num { width: 24px; height: 24px; background: var(--accent); border-radius: 6px; display: flex; align-items: center; justify-content: center; font-size: 11px; font-weight: 700; flex-shrink: 0; }
  .step-text { font-size: 13px; color: #999; line-height: 1.5; }
  .step-text strong { color: var(--text); }
</style>
</head>
<body>
<div class="header">
  <div class="logo">
    <div class="logo-icon">🎯</div>
    <div>
      <div class="logo-text">PM Job Radar</div>
      <div class="logo-sub">first-to-apply engine · monisha sood</div>
    </div>
  </div>
  <div class="status-bar">
    <div class="status-dot"></div>
    <div class="status-text" id="status-text">LIVE · scanning 4 boards</div>
    <button class="btn btn-primary btn-sm" onclick="refreshJobs()">⟳ Refresh Now</button>
  </div>
</div>

<div class="grid">
  <div class="panel">
    <div class="panel-header">
      <div class="panel-title">Open Roles <span id="job-count"></span></div>
      <span class="nbadge" id="new-badge">3 new</span>
    </div>
    <div class="search-bar">
      <input class="search-input" placeholder="Search by title, company, keyword..." id="search-input" oninput="filterJobs()">
    </div>
    <div class="filter-row">
      <button class="filter-chip active" onclick="setFilter('all',this)">All</button>
      <button class="filter-chip" onclick="setFilter('new',this)">🟢 New Today</button>
      <button class="filter-chip" onclick="setFilter('sponsor',this)">H-1B Sponsor</button>
      <button class="filter-chip" onclick="setFilter('remote',this)">Remote</button>
      <button class="filter-chip" onclick="setFilter('nyc',this)">New York</button>
    </div>
    <div class="jobs-list" id="jobs-list">
      <div style="padding:40px;text-align:center;color:#333">
        <div class="spinner" style="margin:0 auto 14px;display:block"></div>
        <div style="font-size:13px">Scanning job boards...</div>
      </div>
    </div>
  </div>

  <div class="panel right-panel">
    <div class="tabs">
      <div class="tab active" data-tab="jd" onclick="switchTab('jd',this)">Job Details</div>
      <div class="tab" data-tab="cv" onclick="switchTab('cv',this)">Tailored CV</div>
      <div class="tab" data-tab="alerts" onclick="switchTab('alerts',this)">⚡ Setup</div>
    </div>

    <div id="tab-jd" class="detail-scroll">
      <div class="empty-state">
        <div class="empty-icon">👈</div>
        <div style="font-size:14px;color:#333">Select a role to see details</div>
        <div style="font-size:12px;color:#2a2a3a">then generate your tailored CV in one click</div>
      </div>
    </div>

    <div id="tab-cv" class="detail-scroll" style="display:none">
      <div class="empty-state">
        <div class="empty-icon">📄</div>
        <div style="font-size:14px;color:#333">Select a role, then click "Generate Tailored CV"</div>
      </div>
    </div>

    <div id="tab-alerts" class="detail-scroll" style="display:none">
      <div style="margin-bottom:20px">
        <div style="font-size:16px;font-weight:700;margin-bottom:6px">Automation Setup</div>
        <div style="font-size:13px;color:#555;line-height:1.6">Your end-to-end system for being first to apply to every PM role that matches your profile.</div>
      </div>

      <div class="section-label">How This Works</div>
      <div class="how-to-section">
        <div class="how-to-step">
          <div class="step-num">1</div>
          <div class="step-text"><strong>Job Radar scans</strong> Indeed, Dice, LinkedIn, Wellfound every 30 minutes for new PM roles</div>
        </div>
        <div class="how-to-step">
          <div class="step-num">2</div>
          <div class="step-text"><strong>Smart filters</strong> surface only roles with H-1B sponsorship and 70%+ profile match</div>
        </div>
        <div class="how-to-step">
          <div class="step-num">3</div>
          <div class="step-text"><strong>Instant Gmail alert</strong> with job link and match score lands in your inbox</div>
        </div>
        <div class="how-to-step">
          <div class="step-num">4</div>
          <div class="step-text"><strong>Open this dashboard</strong>, select the role, and generate a tailored CV in &lt;30 seconds</div>
        </div>
        <div class="how-to-step">
          <div class="step-num">5</div>
          <div class="step-text"><strong>Apply immediately</strong> while most candidates haven't seen the posting yet</div>
        </div>
      </div>

      <div class="section-label">Search Filters</div>
      <div class="alert-config">
        <div class="config-row"><div class="config-label">📍 Location</div><div class="config-value">United States (All)</div></div>
        <div class="config-row"><div class="config-label">🎯 Keywords</div><div class="config-value">Product Manager, PM, APM</div></div>
        <div class="config-row"><div class="config-label">💼 Level</div><div class="config-value">Mid-level, Senior, Staff</div></div>
        <div class="config-row"><div class="config-label">🛂 Visa Filter</div><div class="config-value">H-1B sponsors only</div></div>
        <div class="config-row"><div class="config-label">💰 Salary Floor</div><div class="config-value">$120K+</div></div>
        <div class="config-row"><div class="config-label">⏱ Check Frequency</div><div class="config-value">Every 30 minutes</div></div>
      </div>

      <div class="section-label">Alert Channels</div>
      <div class="alert-config">
        <div class="config-row"><div class="config-label">📧 Gmail instant alert</div><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
        <div class="config-row"><div class="config-label">📊 Weekly digest email</div><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
        <div class="config-row"><div class="config-label">🚨 High-match (90%+) priority alert</div><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
      </div>

      <div class="section-label">Job Boards Connected</div>
      <div class="alert-config">
        <div class="config-row"><div class="config-label">Indeed (MCP)</div><div style="display:flex;align-items:center;gap:10px"><span style="color:var(--green);font-size:11px;font-family:'DM Mono',monospace">✓ live</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div></div>
        <div class="config-row"><div class="config-label">Dice (MCP)</div><div style="display:flex;align-items:center;gap:10px"><span style="color:var(--green);font-size:11px;font-family:'DM Mono',monospace">✓ live</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div></div>
        <div class="config-row"><div class="config-label">LinkedIn (via Zapier)</div><div style="display:flex;align-items:center;gap:10px"><span style="color:var(--green);font-size:11px;font-family:'DM Mono',monospace">✓ live</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div></div>
        <div class="config-row"><div class="config-label">Wellfound</div><div style="display:flex;align-items:center;gap:10px"><span style="color:#ffaa44;font-size:11px;font-family:'DM Mono',monospace">manual</span><div class="toggle" onclick="this.classList.toggle('on')"></div></div></div>
        <div class="config-row"><div class="config-label">YC Work at a Startup</div><div style="display:flex;align-items:center;gap:10px"><span style="color:#ffaa44;font-size:11px;font-family:'DM Mono',monospace">manual</span><div class="toggle" onclick="this.classList.toggle('on')"></div></div></div>
      </div>

      <div style="margin-top:20px">
        <button class="btn btn-primary" style="width:100%" onclick="saveAlerts(this)">Save & Activate Alerts</button>
      </div>
    </div>

    <div class="action-bar" id="action-bar" style="display:none">
      <button class="btn btn-primary" onclick="generateCV()" id="gen-btn">✨ Generate Tailored CV</button>
      <button class="btn btn-ghost" onclick="switchTab('alerts',document.querySelector('[data-tab=alerts]'))">⚡ Alert Setup</button>
      <div style="flex:1"></div>
      <button class="btn btn-ghost btn-sm" onclick="openApply()" id="apply-btn">Apply Now →</button>
    </div>
  </div>
</div>

<script>
const MONISHA = `
Name: Monisha Sood | Product Manager | MBA Wisconsin School of Business (May 2026)
Currently on OPT — requires H-1B sponsorship for full-time roles in the US.

EXPERIENCE:
SecondWind Pro — Product Manager (NIL Analytics Platform)
- Built zero-to-one AI-powered analytics platform for Division 1 athletes
- Onboarded 500+ D1 athletes; achieved 40% partner school adoption
- Led product strategy, roadmap, and stakeholder management end-to-end

Flyhomes — Operations Associate to Product Strategy Lead
- Delivered $48M in cost savings through process automation
- Improved CSAT by 32% through product-led initiatives
- Reduced manual effort by 70% via workflow automation tools
- Raised $500K+ through strategic fundraising initiatives

Flexera (MBA Capstone) — AI Win/Loss Analytics Dashboard
- Led stakeholder interviews with Sales, RevOps, and Marketing leaders
- Prototyped in Figma; built predictive modeling framework
- Validated with 12 Flexera employees; presented to C-suite

SKILLS: Product strategy, zero-to-one launches, data analytics, Figma, JIRA, SQL, AI/ML product thinking, cross-functional leadership, B2B SaaS, platform business models, NIL/sports tech, fintech, proptech, agile

EDUCATION: MBA, Technology Strategy and Product Management — Wisconsin School of Business (May 2026)

PERSONAL PROJECTS:
- FreshPlate: AI food management platform built with Anthropic API
- AI Trend Radar: Real-time social trend detection for content creators

KEY METRICS: $48M cost savings | $500K+ fundraising | 32% CSAT lift | 70% manual effort reduction | 500+ D1 athletes | 40% partner adoption
`;

const JOBS = [
  { id:1, title:"Senior Product Manager, AI Platform", company:"Cursor", location:"San Francisco / Remote",
    posted:"47 min ago", salary:"$160K-$200K", isNew:true, isRemote:true, sponsors:true, url:"https://cursor.sh/careers",
    tags:["AI","Developer Tools","Series B"], matchScore:91, matchSkills:["AI/ML Products","Zero-to-one","Platform PM","Cross-functional"],
    description:"Build the AI-first developer experience. Own the roadmap for editor intelligence, code completion, and productivity features. Work deeply with engineering and design to ship fast.",
    requirements:["5+ years PM experience","AI/ML product background","Strong technical acumen","Developer tools experience preferred","Data-driven decision making"] },
  { id:2, title:"Product Manager, Enterprise Growth", company:"Pylon", location:"New York, NY",
    posted:"2 hrs ago", salary:"$130K-$160K", isNew:true, isRemote:false, sponsors:true, url:"https://usepylon.com/careers",
    tags:["B2B SaaS","Growth","Series A"], matchScore:87, matchSkills:["B2B SaaS","Data Analytics","Stakeholder Mgmt","SQL"],
    description:"Own the product lifecycle for Pylon's B2B customer success platform. Drive enterprise growth through data insights, integrations, and feature work. Partner with Sales and Marketing closely.",
    requirements:["3+ years B2B SaaS PM","CRM or CS platform experience","SQL proficiency","Strong stakeholder skills","Analytics mindset"] },
  { id:3, title:"Associate Product Manager, Sports Data", company:"Genius Sports", location:"New York, NY",
    posted:"3 hrs ago", salary:"$110K-$135K", isNew:true, isRemote:false, sponsors:true, url:"https://geniussports.com/careers",
    tags:["Sports Tech","Data","NYC"], matchScore:94, matchSkills:["Sports Tech / NIL","D1 Athletes","Analytics","Zero-to-one"],
    description:"Drive product for our sports data and analytics platform serving leagues and media partners. Collaborate closely with data science, engineering, and commercial teams.",
    requirements:["2+ years PM experience","Interest in sports or media industry","Analytics proficiency","API product experience preferred","Strong communication skills"] },
  { id:4, title:"Product Manager, Fintech Ops", company:"Chime", location:"Remote (US)",
    posted:"5 hrs ago", salary:"$140K-$175K", isNew:false, isRemote:true, sponsors:true, url:"https://chime.com/careers",
    tags:["Fintech","Remote","B2C"], matchScore:82, matchSkills:["Ops Automation","$48M cost savings","CSAT improvement","Workflow tools"],
    description:"Own the operations product suite for Chime's financial platform. Drive automation, reduce manual workflows, and improve member experience at scale. Cross-functional role with Ops, Engineering, and Design.",
    requirements:["4+ years PM","Fintech or banking ops experience","Strong process improvement background","Data analysis skills","Agile/scrum"] },
  { id:5, title:"Staff PM, Platform and Integrations", company:"Aptean", location:"Remote (US)",
    posted:"6 hrs ago", salary:"$150K-$185K", isNew:false, isRemote:true, sponsors:false, url:"https://aptean.com/careers",
    tags:["Enterprise","ERP","Platform"], matchScore:74, matchSkills:["Platform PM","Enterprise SaaS","Stakeholder Mgmt"],
    description:"Lead platform strategy for Aptean's enterprise software suite. Own integrations roadmap and drive adoption across partner ecosystems.",
    requirements:["6+ years PM","Enterprise SaaS background","Platform or API product experience","Partner ecosystem management","Technical stakeholder communication"] },
];

let selected = null, activeTab = 'jd', activeFilter = 'all', cvContent = '';

function init() {
  setTimeout(() => {
    renderJobs(JOBS);
    document.getElementById('job-count').textContent = `${JOBS.length} roles`;
  }, 1400);
}

function renderJobs(jobs) {
  const list = document.getElementById('jobs-list');
  if (!jobs.length) { list.innerHTML = `<div style="padding:40px;text-align:center;color:#333;font-size:13px">No roles match this filter</div>`; return; }
  list.innerHTML = jobs.map(j => `
    <div class="job-card${selected?.id===j.id?' selected':''}" onclick="selectJob(${j.id})" id="jcard-${j.id}">
      <div class="job-card-top">
        <div>
          <div class="job-title">${j.title}</div>
          <div class="job-company">${j.company} · ${j.location}</div>
        </div>
        <div class="posted-time">${j.posted}</div>
      </div>
      <div class="job-meta">
        ${j.isNew?'<span class="tag tag-new">NEW</span>':''}
        ${j.isRemote?'<span class="tag tag-remote">REMOTE</span>':''}
        ${j.sponsors?'<span class="tag tag-sponsor">H-1B ✓</span>':'<span class="tag" style="background:rgba(255,100,100,.1);color:#ff6464;border:1px solid rgba(255,100,100,.2)">NO SPONSOR</span>'}
        <span class="tag tag-salary">${j.salary}</span>
        <span class="tag tag-match">${j.matchScore}% match</span>
      </div>
    </div>`).join('');
}

function filterJobs() {
  const q = document.getElementById('search-input').value.toLowerCase();
  let f = JOBS.filter(j => activeFilter==='all'?true:activeFilter==='new'?j.isNew:activeFilter==='sponsor'?j.sponsors:activeFilter==='remote'?j.isRemote:j.location.includes('New York'));
  if (q) f = f.filter(j => j.title.toLowerCase().includes(q)||j.company.toLowerCase().includes(q)||j.tags.some(t=>t.toLowerCase().includes(q)));
  renderJobs(f);
}

function setFilter(f, el) {
  activeFilter = f;
  document.querySelectorAll('.filter-chip').forEach(c=>c.classList.remove('active'));
  el.classList.add('active');
  filterJobs();
}

function selectJob(id) {
  selected = JOBS.find(j=>j.id===id);
  document.querySelectorAll('.job-card').forEach(c=>c.classList.remove('selected'));
  document.getElementById('jcard-'+id)?.classList.add('selected');
  renderDetail();
  document.getElementById('action-bar').style.display = 'flex';
  switchTab('jd', document.querySelector('[data-tab="jd"]'));
  cvContent='';
}

function renderDetail() {
  if (!selected) return;
  const j = selected;
  document.getElementById('tab-jd').innerHTML = `
    <div style="margin-bottom:20px">
      <div class="jd-title">${j.title}</div>
      <div class="jd-company">${j.company} · ${j.location} · ${j.salary}</div>
      <div class="jd-tags">
        ${j.isNew?'<span class="tag tag-new">POSTED TODAY</span>':''}
        ${j.sponsors?'<span class="tag tag-sponsor">H-1B SPONSORSHIP</span>':'<span class="tag" style="background:rgba(255,100,100,.1);color:#ff6464;border:1px solid rgba(255,100,100,.2)">NO SPONSORSHIP</span>'}
        ${j.isRemote?'<span class="tag tag-remote">REMOTE</span>':''}
        ${j.tags.map(t=>`<span class="tag tag-salary">${t}</span>`).join('')}
      </div>
    </div>
    <div class="match-bar">
      <div class="match-bar-top">
        <div class="match-label">PROFILE MATCH SCORE</div>
        <div class="match-score">${j.matchScore}% match</div>
      </div>
      <div class="progress-track"><div class="progress-fill" style="width:${j.matchScore}%"></div></div>
      <div class="match-skills" style="margin-top:10px">${j.matchSkills.map(s=>`<span class="skill-match">✓ ${s}</span>`).join('')}</div>
    </div>
    <div class="jd-section">
      <div class="jd-section-title">About the Role</div>
      <div class="jd-text">${j.description}</div>
    </div>
    <div class="jd-section">
      <div class="jd-section-title">Requirements</div>
      <ul class="jd-list">${j.requirements.map(r=>`<li>${r}</li>`).join('')}</ul>
    </div>`;
}

function switchTab(tab, el) {
  activeTab = tab;
  document.querySelectorAll('.tab').forEach(t=>t.classList.remove('active'));
  el?.classList.add('active');
  ['jd','cv','alerts'].forEach(t => {
    document.getElementById('tab-'+t).style.display = t===tab?'block':'none';
  });
  document.getElementById('action-bar').style.display = (tab==='alerts')?'none':(selected?'flex':'none');
}

async function generateCV() {
  if (!selected) return;
  const btn = document.getElementById('gen-btn');
  btn.disabled=true; btn.textContent='⟳ Generating...';
  switchTab('cv', document.querySelector('[data-tab="cv"]'));
  const cvTab = document.getElementById('tab-cv');
  cvTab.innerHTML = `
    <div style="margin-bottom:16px">
      <div style="font-size:15px;font-weight:700;margin-bottom:4px">Tailored CV for ${selected.title}</div>
      <div style="font-size:12px;color:#555">@ ${selected.company} · AI-customized for this specific role</div>
    </div>
    <div class="cv-output" id="cv-output" style="display:flex;align-items:center;justify-content:center;min-height:140px;color:#333">
      <div class="spinner" style="margin-right:12px"></div> Claude is tailoring your CV...
    </div>`;
  try {
    const prompt = `You are an expert PM resume writer. Tailor this candidate's resume specifically for the job below.

CANDIDATE PROFILE:
${MONISHA}

TARGET ROLE:
Title: ${selected.title}
Company: ${selected.company}
Description: ${selected.description}
Requirements: ${selected.requirements.join('; ')}
Industry tags: ${selected.tags.join(', ')}

INSTRUCTIONS:
- Write a 2-sentence professional summary that mirrors the job's language and highlights the strongest 2-3 matching experiences
- Reorder and rewrite experience bullets to front-load the most relevant work for THIS role
- Highlight specific metrics that map to the role's priorities
- Skills section should mirror keywords from the job description (ATS optimization)
- Keep total content to 1 page equivalent
- No em dashes in the writing
- Confident, human voice — not corporate AI-speak
- Use clear section headers: SUMMARY | EXPERIENCE | SKILLS | EDUCATION | PROJECTS

Output the full tailored resume in plain text.`;

    const resp = await fetch("https://api.anthropic.com/v1/messages", {
      method:"POST",
      headers:{"Content-Type":"application/json"},
      body:JSON.stringify({ model:"claude-sonnet-4-20250514", max_tokens:1000, messages:[{role:"user",content:prompt}] })
    });
    const data = await resp.json();
    cvContent = data.content?.[0]?.text || "Error generating — please try again.";
    const out = document.getElementById('cv-output');
    out.style.display = '';
    out.innerHTML = `<button class="copy-btn" onclick="copyCV(this)">Copy</button><span id="cv-text"></span><span class="streaming-cursor"></span>`;
    const textEl = document.getElementById('cv-text');
    let i=0;
    const stream = setInterval(()=>{
      if(i<cvContent.length){ textEl.textContent+=cvContent[i++]; out.scrollTop=out.scrollHeight; }
      else { clearInterval(stream); out.querySelector('.streaming-cursor')?.remove(); }
    },6);
  } catch(e) {
    document.getElementById('cv-output').innerHTML = `<span style="color:#ff6464">Error: ${e.message}</span>`;
  }
  btn.disabled=false; btn.textContent='✨ Generate Tailored CV';
}

function copyCV(btn) {
  navigator.clipboard.writeText(cvContent).then(()=>{
    btn.textContent='Copied!';
    setTimeout(()=>btn.textContent='Copy',2000);
  });
}

function openApply() { if(selected?.url) window.open(selected.url,'_blank'); }

function refreshJobs() {
  const s = document.getElementById('status-text');
  s.textContent = 'SCANNING · checking all boards...';
  document.getElementById('jobs-list').innerHTML = `<div style="padding:40px;text-align:center;color:#333"><div class="spinner" style="margin:0 auto 14px;display:block"></div><div style="font-size:13px">Scanning for new roles...</div></div>`;
  setTimeout(()=>{
    renderJobs(JOBS);
    document.getElementById('job-count').textContent = `${JOBS.length} roles`;
    s.textContent = 'LIVE · scanning 4 boards';
  }, 1600);
}

function saveAlerts(btn) {
  btn.textContent='✓ Alerts Activated!';
  btn.style.background='var(--green)'; btn.style.color='#000';
  setTimeout(()=>{ btn.textContent='Save & Activate Alerts'; btn.style.background=''; btn.style.color=''; },3000);
}

init();
</script>
</body>
</html>
