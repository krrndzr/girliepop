<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="apple-mobile-web-app-title" content="PM Brief">
<title>PM Morning Brief</title>
<link href="https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
–bg: #f5f0e8;
–card: #fffdf8;
–border: #e0d8c8;
–ink: #1a1612;
–muted: #8a7e6e;
–accent: #c8431a;
–accent2: #1a6bc8;
–accent3: #2a8a4a;
–gold: #c8941a;
–rule: #d0c8b8;
}

html, body {
height: 100%;
background: var(–bg);
color: var(–ink);
font-family: ‘DM Mono’, monospace;
overflow-x: hidden;
}

body {
display: flex;
flex-direction: column;
align-items: center;
min-height: 100dvh;
padding: 32px 20px 40px;
position: relative;
}

/* Newspaper texture */
body::before {
content: ‘’;
position: fixed;
inset: 0;
background-image: url(“data:image/svg+xml,%3Csvg xmlns=‘http://www.w3.org/2000/svg’ width=‘4’ height=‘4’%3E%3Crect width=‘4’ height=‘4’ fill=’%23f5f0e8’/%3E%3Ccircle cx=‘1’ cy=‘1’ r=‘0.5’ fill=’%23d0c8b0’ opacity=‘0.3’/%3E%3C/svg%3E”);
pointer-events: none;
z-index: 0;
}

.content {
position: relative;
z-index: 1;
width: 100%;
max-width: 380px;
}

/* Masthead */
.masthead {
text-align: center;
border-top: 3px double var(–ink);
border-bottom: 3px double var(–ink);
padding: 14px 0 12px;
margin-bottom: 6px;
position: relative;
}

.masthead::before {
content: ‘★ DAILY INTELLIGENCE ★’;
position: absolute;
top: -9px;
left: 50%;
transform: translateX(-50%);
background: var(–bg);
padding: 0 10px;
font-size: 8px;
letter-spacing: 3px;
color: var(–muted);
white-space: nowrap;
}

.paper-name {
font-family: ‘Instrument Serif’, serif;
font-size: 36px;
line-height: 1;
letter-spacing: -1px;
color: var(–ink);
}

.paper-name span {
color: var(–accent);
}

.tagline {
font-size: 9px;
letter-spacing: 3px;
text-transform: uppercase;
color: var(–muted);
margin-top: 4px;
}

/* Date bar */
.datebar {
display: flex;
justify-content: space-between;
align-items: center;
padding: 6px 0;
border-bottom: 1px solid var(–rule);
margin-bottom: 20px;
font-size: 9px;
color: var(–muted);
letter-spacing: 1px;
}

/* Section cards */
.sections {
display: flex;
flex-direction: column;
gap: 0;
margin-bottom: 24px;
border: 1px solid var(–border);
border-radius: 4px;
overflow: hidden;
background: var(–card);
}

.section-item {
display: flex;
align-items: center;
gap: 14px;
padding: 13px 16px;
border-bottom: 1px solid var(–border);
position: relative;
}

.section-item:last-child {
border-bottom: none;
}

.section-tag {
font-size: 8px;
font-weight: 500;
letter-spacing: 2px;
text-transform: uppercase;
padding: 3px 7px;
border-radius: 2px;
flex-shrink: 0;
width: 72px;
text-align: center;
}

.tag-my { background: rgba(200,67,26,0.1); color: var(–accent); border: 1px solid rgba(200,67,26,0.2); }
.tag-sea { background: rgba(26,107,200,0.1); color: var(–accent2); border: 1px solid rgba(26,107,200,0.2); }
.tag-reg { background: rgba(200,148,26,0.1); color: var(–gold); border: 1px solid rgba(200,148,26,0.2); }
.tag-comp { background: rgba(42,138,74,0.1); color: var(–accent3); border: 1px solid rgba(42,138,74,0.2); }
.tag-ai { background: rgba(100,50,200,0.1); color: #6432c8; border: 1px solid rgba(100,50,200,0.2); }
.tag-macro { background: rgba(26,22,18,0.07); color: var(–ink); border: 1px solid rgba(26,22,18,0.15); }
.tag-pm { background: rgba(200,67,26,0.08); color: var(–accent); border: 1px solid rgba(200,67,26,0.15); }
.tag-global { background: rgba(26,107,200,0.08); color: var(–accent2); border: 1px solid rgba(26,107,200,0.15); }

.section-text {
font-size: 11px;
color: var(–ink);
line-height: 1.4;
opacity: 0.85;
}

/* CTA */
.cta-wrap {
margin-bottom: 20px;
}

.cta-btn {
width: 100%;
display: block;
text-decoration: none;
background: var(–ink);
color: var(–bg);
font-family: ‘Instrument Serif’, serif;
font-size: 20px;
font-style: italic;
text-align: center;
padding: 18px 24px;
border-radius: 3px;
cursor: pointer;
position: relative;
overflow: hidden;
transition: transform 0.12s ease, background 0.12s ease;
-webkit-tap-highlight-color: transparent;
border: none;
letter-spacing: 0.3px;
}

.cta-btn::before {
content: ‘’;
position: absolute;
inset: 3px;
border: 1px solid rgba(245,240,232,0.15);
border-radius: 1px;
pointer-events: none;
}

.cta-btn:active {
transform: scale(0.98);
background: #2a2420;
}

.cta-btn .btn-sub {
display: block;
font-family: ‘DM Mono’, monospace;
font-size: 9px;
font-style: normal;
opacity: 0.5;
letter-spacing: 2px;
text-transform: uppercase;
margin-top: 3px;
}

/* Divider */
.divider {
display: flex;
align-items: center;
gap: 10px;
margin: 4px 0 16px;
color: var(–muted);
font-size: 9px;
letter-spacing: 2px;
text-transform: uppercase;
}
.divider::before, .divider::after {
content: ‘’;
flex: 1;
height: 1px;
background: var(–rule);
}

/* Footer */
.footer {
text-align: center;
font-size: 9px;
color: var(–muted);
line-height: 1.9;
letter-spacing: 0.5px;
border-top: 1px solid var(–rule);
padding-top: 14px;
}

.footer a {
color: var(–accent);
text-decoration: none;
border-bottom: 1px solid rgba(200,67,26,0.3);
}

/* Overlay */
#overlay {
display: none;
position: fixed;
inset: 0;
background: rgba(26,22,18,0.93);
z-index: 100;
padding: 40px 24px;
overflow-y: auto;
}

.overlay-inner {
max-width: 360px;
margin: 0 auto;
color: #c8bfb0;
font-size: 12px;
line-height: 1.9;
}

.overlay-title {
font-family: ‘Instrument Serif’, serif;
font-size: 24px;
color: #f5f0e8;
margin-bottom: 20px;
}

.overlay-steps {
display: flex;
flex-direction: column;
gap: 12px;
padding-left: 0;
list-style: none;
}

.overlay-steps li {
display: flex;
gap: 12px;
align-items: flex-start;
}

.step-num {
width: 22px;
height: 22px;
border-radius: 50%;
border: 1px solid #c8431a;
color: #c8431a;
font-size: 10px;
display: flex;
align-items: center;
justify-content: center;
flex-shrink: 0;
margin-top: 2px;
}

.close-btn {
margin-top: 28px;
width: 100%;
padding: 14px;
background: #c8431a;
color: #f5f0e8;
border: none;
border-radius: 3px;
font-family: ‘Instrument Serif’, serif;
font-size: 18px;
font-style: italic;
cursor: pointer;
}

@keyframes fadeIn {
from { opacity: 0; transform: translateY(12px); }
to { opacity: 1; transform: translateY(0); }
}

.content > * {
animation: fadeIn 0.5s ease both;
}
.content > *:nth-child(1) { animation-delay: 0.05s; }
.content > *:nth-child(2) { animation-delay: 0.1s; }
.content > *:nth-child(3) { animation-delay: 0.15s; }
.content > *:nth-child(4) { animation-delay: 0.2s; }
.content > *:nth-child(5) { animation-delay: 0.25s; }
</style>

</head>
<body>

<div class="content">

  <div style="text-align:center; font-family:'Instrument Serif',serif; font-size:15px; font-style:italic; color:var(--accent); letter-spacing:0.5px; margin-bottom:14px; animation: fadeIn 0.4s ease both;">✦ Morning girlie pop ✦</div>

  <div class="masthead">
    <div class="paper-name">PM<span>.</span>Brief</div>
    <div class="tagline">Malaysian Digital Banking · Morning Intelligence</div>
  </div>

  <div class="datebar">
    <span id="dateStr">—</span>
    <span>🇲🇾 KUL</span>
    <span id="clockStr">—</span>
  </div>

  <div class="sections">
    <div class="section-item">
      <span class="section-tag tag-my">MY News</span>
      <span class="section-text">Malaysian fintech, banking & digital economy headlines</span>
    </div>
    <div class="section-item">
      <span class="section-tag tag-reg">BNM / SC</span>
      <span class="section-text">Regulations, policy updates & compliance changes</span>
    </div>
    <div class="section-item">
      <span class="section-tag tag-comp">Rivals</span>
      <span class="section-text">GXBank, Boost, TNG, MAE, CIMB Octo & more</span>
    </div>
    <div class="section-item">
      <span class="section-tag tag-sea">SEA</span>
      <span class="section-text">Regional moves: Singapore, Indonesia, Thailand, PH</span>
    </div>
    <div class="section-item">
      <span class="section-tag tag-global">Global</span>
      <span class="section-text">Global fintech trends worth watching</span>
    </div>
    <div class="section-item">
      <span class="section-tag tag-ai">AI</span>
      <span class="section-text">AI in banking — products, features & disruptions</span>
    </div>
    <div class="section-item">
      <span class="section-tag tag-macro">Macro</span>
      <span class="section-text">MYR rate, OPR, inflation & economic signals</span>
    </div>
    <div class="section-item">
      <span class="section-tag tag-pm">PM Intel</span>
      <span class="section-text">Product & UX inspiration from across the industry</span>
    </div>
  </div>

  <div class="cta-wrap">
    <a class="cta-btn" href="#" onclick="openBrief(event)">
      Get Today's PM Brief
      <span class="btn-sub">Opens Claude · One Tap</span>
    </a>
  </div>

  <div class="divider">Add to home screen</div>

  <div class="footer">
    Save this page to your iPhone Home Screen<br>
    for instant one-tap access every morning.<br><br>
    <a href="#" onclick="showInstructions(event)">How to add to Home Screen →</a>
  </div>

</div>

<!-- Instructions overlay -->

<div id="overlay">
  <div class="overlay-inner">
    <div class="overlay-title">Add to Home Screen</div>
    <ol class="overlay-steps">
      <li><span class="step-num">1</span><span>Open this page in <strong style="color:#f5f0e8">Safari</strong> (not Chrome)</span></li>
      <li><span class="step-num">2</span><span>Tap the <strong style="color:#f5f0e8">Share button</strong> — square with arrow at the bottom of Safari</span></li>
      <li><span class="step-num">3</span><span>Scroll and tap <strong style="color:#f5f0e8">"Add to Home Screen"</strong></span></li>
      <li><span class="step-num">4</span><span>Name it <strong style="color:#f5f0e8">PM Brief</strong> → tap <strong style="color:#f5f0e8">Add</strong></span></li>
      <li><span class="step-num">5</span><span>✅ Tap the icon every morning for your daily brief</span></li>
    </ol>
    <div style="margin-top:20px; padding:14px; background:rgba(245,240,232,0.06); border-radius:3px; font-size:10px; color:#8a7e6e; line-height:1.7;">
      You'll need to be logged into Claude.ai for the brief to run automatically.
    </div>
    <button class="close-btn" onclick="document.getElementById('overlay').style.display='none'">Got it ✓</button>
  </div>
</div>

<script>
  function updateTime() {
    const now = new Date();
    document.getElementById('clockStr').textContent = now.toLocaleTimeString('en-MY', {hour:'2-digit', minute:'2-digit'});
    document.getElementById('dateStr').textContent = now.toLocaleDateString('en-MY', {weekday:'short', day:'numeric', month:'short', year:'numeric'}).toUpperCase();
  }
  updateTime();
  setInterval(updateTime, 1000);

  const prompt = `Give me my Malaysian Digital Bank PM Morning Brief for today. Be sharp and concise — I want signal, not noise.

Cover these sections:

🇲🇾 MALAYSIA NEWS
Top 2-3 Malaysian fintech, digital banking, or financial news stories today. What happened and why it matters to a digital bank PM.

📋 BNM / SC REGULATIONS
Any new or upcoming Bank Negara Malaysia or Securities Commission regulations, policy updates, consultations, or compliance news. Flag anything I need to act on.

🏦 COMPETITOR INTEL
What are GXBank, Boost Bank, Touch 'n Go (TNG), MAE by Maybank, CIMB Octo, or any other Malaysian digital bank/fintech doing? New features, campaigns, partnerships, or strategic moves.

🌏 SEA REGION
1-2 notable moves from Singapore (GXS, MariBank, Grab), Indonesia, Thailand, or Philippines worth knowing as context for MY market.

🌍 GLOBAL FINTECH
1 global fintech or neobank trend or product move that's relevant to watch.

🤖 AI IN BANKING
Any notable AI product launches, features, or use cases in banking/fintech today — globally or locally.

📊 MACRO SIGNALS
MYR exchange rate today, any OPR or BNM rate news, inflation data, or macro conditions affecting consumer spending & digital banking.

💡 PM INSPIRATION
1 interesting product, UX pattern, or feature from any fintech/bank globally that I could learn from or adapt for the Malaysian market.

🎯 TODAY'S PRIORITY
Based on everything above — what's the ONE thing I should pay closest attention to today as a Malaysian digital bank PM?`;

  function openBrief(e) {
    e.preventDefault();
    const url = `https://claude.ai/new?q=${encodeURIComponent(prompt)}`;
    window.open(url, '_blank');
  }

  function showInstructions(e) {
    e.preventDefault();
    document.getElementById('overlay').style.display = 'block';
  }
</script>

</body>
</html>
