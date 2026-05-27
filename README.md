<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CSC 114 – Artificial Intelligence I</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Source+Sans+3:wght@300;400;600&display=swap" rel="stylesheet">
<style>
  :root {
    --burnt-orange: #e76f51;
    --coral: #f4a261;
    --warm-sand: #e9c46a;
    /* Dark mode defaults */
    --bg: #0f1a1f;
    --bg-card: #162027;
    --bg-card-hover: #1c2a33;
    --bg-code: #0a1318;
    --surface: #1e2f38;
    --border: rgba(244,162,97,0.15);
    --text-primary: #edf2f4;
    --text-secondary: #8faab5;
    --text-muted: #5a7a87;
    --hero-bg-a: #0a1318;
    --hero-bg-b: #0f1e26;
    --hero-bg-c: #132430;
    --prereq-bg: rgba(233,196,106,0.12);
    --prereq-border: rgba(233,196,106,0.3);
    --prereq-color: var(--warm-sand);
  }

  @media (prefers-color-scheme: light) {
    :root {
      --bg: #fdf6ec;
      --bg-card: #ffffff;
      --bg-card-hover: #fef9f3;
      --bg-code: #f0ece3;
      --surface: #f5ede0;
      --border: rgba(231,111,81,0.15);
      --text-primary: #264653;
      --text-secondary: #3a5a66;
      --text-muted: #5a7a87;
      --hero-bg-a: #264653;
      --hero-bg-b: #2d5566;
      --hero-bg-c: #3a6b7a;
      --prereq-bg: var(--warm-sand);
      --prereq-border: var(--warm-sand);
      --prereq-color: #264653;
    }
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background-color: var(--bg);
    color: var(--text-primary);
    font-family: 'Source Sans 3', sans-serif;
    font-weight: 400;
    line-height: 1.7;
  }

  /* HERO */
  .hero {
    background: linear-gradient(135deg, var(--hero-bg-a) 0%, var(--hero-bg-b) 50%, var(--hero-bg-c) 100%);
    padding: 72px 48px 56px;
    position: relative;
    overflow: hidden;
    border-bottom: 1px solid var(--border);
  }
  .hero::before {
    content: '';
    position: absolute;
    top: -80px; right: -80px;
    width: 500px; height: 500px;
    background: radial-gradient(circle, rgba(231,111,81,0.18) 0%, transparent 65%);
    border-radius: 50%;
  }
  .hero::after {
    content: '';
    position: absolute;
    bottom: -80px; left: 40px;
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(233,196,106,0.10) 0%, transparent 65%);
    border-radius: 50%;
  }
  .hero-badge {
    display: inline-block;
    background: var(--burnt-orange);
    color: #fff;
    font-weight: 600;
    font-size: 11px;
    letter-spacing: 2.5px;
    text-transform: uppercase;
    padding: 5px 14px;
    border-radius: 2px;
    margin-bottom: 20px;
  }
  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-weight: 900;
    font-size: 52px;
    color: var(--text-primary);
    line-height: 1.1;
    margin-bottom: 8px;
  }
  .hero h1 span { color: var(--coral); }
  .hero-subtitle {
    font-size: 17px;
    color: var(--text-secondary);
    font-weight: 300;
    margin-bottom: 32px;
  }
  .hero-meta { display: flex; gap: 32px; flex-wrap: wrap; }
  .hero-meta-item { display: flex; flex-direction: column; gap: 2px; }
  .hero-meta-label {
    font-size: 10px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--warm-sand);
    font-weight: 600;
  }
  .hero-meta-value {
    font-size: 15px;
    color: rgba(237,242,244,0.85);
  }

  /* LAYOUT */
  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 56px 48px;
  }

  /* SECTION */
  .section { margin-bottom: 56px; }
  .section-header {
    display: flex;
    align-items: center;
    gap: 14px;
    margin-bottom: 24px;
  }
  .section-icon {
    width: 36px; height: 36px;
    background: var(--burnt-orange);
    border-radius: 6px;
    display: flex; align-items: center; justify-content: center;
    font-size: 16px;
    flex-shrink: 0;
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-weight: 700;
    font-size: 26px;
    color: var(--text-primary);
  }
  .section-divider {
    height: 1px;
    background: linear-gradient(to right, var(--coral), var(--warm-sand), transparent);
    margin-bottom: 28px;
    opacity: 0.4;
  }

  /* ABOUT */
  .about-text { font-size: 16px; color: var(--text-secondary); line-height: 1.8; }
  .prereq-tag {
    display: inline-block;
    background: var(--prereq-bg);
    border: 1px solid var(--prereq-border);
    color: var(--prereq-color);
    font-size: 13px;
    font-weight: 600;
    padding: 4px 14px;
    border-radius: 20px;
    margin-top: 12px;
  }

  /* INSTRUCTORS */
  .instructor-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
  .instructor-card {
    background: var(--bg-card);
    border-radius: 10px;
    padding: 24px;
    border-left: 3px solid var(--burnt-orange);
    border: 1px solid var(--border);
    border-left: 3px solid var(--burnt-orange);
  }
  .instructor-name {
    font-family: 'Playfair Display', serif;
    font-weight: 700;
    font-size: 18px;
    color: var(--text-primary);
    margin-bottom: 12px;
  }
  .instructor-detail { font-size: 14px; color: var(--text-muted); margin-bottom: 4px; }
  .instructor-detail strong { color: var(--text-secondary); font-weight: 600; }
  .instructor-detail a { color: var(--coral); text-decoration: none; }
  .instructor-detail a:hover { text-decoration: underline; }

  /* OUTCOMES */
  .outcomes-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
  .outcome-item {
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px 18px;
    font-size: 14px;
    color: var(--text-secondary);
    display: flex;
    align-items: flex-start;
    gap: 10px;
  }
  .outcome-dot {
    width: 8px; height: 8px;
    background: var(--coral);
    border-radius: 50%;
    margin-top: 5px;
    flex-shrink: 0;
  }

  /* TEXTBOOK */
  .textbook-card {
    background: linear-gradient(135deg, #0d1b22 0%, #132430 100%);
    border: 1px solid rgba(231,111,81,0.25);
    border-radius: 12px;
    padding: 28px 32px;
    display: flex;
    align-items: center;
    gap: 28px;
  }
  .book-spine {
    width: 52px; height: 72px;
    background: linear-gradient(160deg, var(--burnt-orange), var(--coral));
    border-radius: 4px 2px 2px 4px;
    flex-shrink: 0;
    display: flex; align-items: center; justify-content: center;
    font-size: 22px;
    box-shadow: 4px 4px 20px rgba(231,111,81,0.3);
  }
  .textbook-title {
    font-family: 'Playfair Display', serif;
    font-weight: 700;
    font-size: 20px;
    color: var(--text-primary);
    margin-bottom: 6px;
  }
  .textbook-meta { font-size: 14px; color: var(--text-muted); line-height: 1.6; }
  .isbn-tag {
    display: inline-block;
    background: rgba(231,111,81,0.1);
    border: 1px solid rgba(231,111,81,0.25);
    color: var(--coral);
    font-family: monospace;
    font-size: 12px;
    padding: 3px 10px;
    border-radius: 3px;
    margin-top: 8px;
  }

  /* SCHEDULE TABLE */
  .schedule-table { width: 100%; border-collapse: collapse; font-size: 14px; }
  .schedule-table thead tr { background: var(--surface); }
  .schedule-table thead th {
    padding: 13px 16px;
    text-align: left;
    font-weight: 600;
    font-size: 11px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--text-secondary);
  }
  .schedule-table thead th:first-child { border-radius: 8px 0 0 0; }
  .schedule-table thead th:last-child { border-radius: 0 8px 0 0; }
  .schedule-table tbody tr {
    border-bottom: 1px solid rgba(255,255,255,0.04);
    transition: background 0.15s;
  }
  .schedule-table tbody tr:hover { background: var(--bg-card-hover); }
  .schedule-table tbody tr.final-row {
    background: rgba(231,111,81,0.06);
    font-weight: 600;
  }
  .schedule-table td { padding: 12px 16px; color: var(--text-secondary); }
  .schedule-table td:first-child {
    font-family: monospace;
    font-size: 13px;
    color: var(--burnt-orange);
    font-weight: 600;
  }
  .points-badge {
    display: inline-block;
    background: rgba(233,196,106,0.12);
    border: 1px solid rgba(233,196,106,0.25);
    color: var(--warm-sand);
    font-size: 12px;
    font-weight: 700;
    padding: 2px 10px;
    border-radius: 12px;
  }
  .points-badge.final {
    background: rgba(231,111,81,0.2);
    border-color: rgba(231,111,81,0.4);
    color: var(--coral);
  }
  .points-note { font-size: 11px; color: var(--text-muted); margin-left: 4px; }

  /* REPO STRUCTURE */
  .code-block {
    background: var(--bg-code);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 24px 28px;
    font-family: 'Courier New', monospace;
    font-size: 13.5px;
    line-height: 1.9;
    color: var(--text-secondary);
    overflow-x: auto;
  }
  .code-block .dir { color: var(--coral); }
  .code-block .comment { color: rgba(233,196,106,0.5); font-style: italic; }
  .code-block .tree { color: rgba(255,255,255,0.15); }

  /* SETUP */
  .setup-step {
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 22px 24px;
    margin-bottom: 16px;
    border-top: 2px solid var(--coral);
  }
  .setup-label {
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--burnt-orange);
    font-weight: 600;
    margin-bottom: 10px;
  }
  .setup-code {
    background: var(--bg-code);
    border-radius: 6px;
    padding: 14px 18px;
    font-family: 'Courier New', monospace;
    font-size: 13px;
    color: var(--text-secondary);
    line-height: 1.7;
    white-space: pre;
    overflow-x: auto;
  }
  .setup-code .cmd { color: var(--coral); }
  .setup-code .comment { color: var(--text-muted); font-style: italic; }

  /* POLICIES */
  .policy-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  .policy-card {
    background: var(--bg-card);
    border-radius: 10px;
    padding: 20px 22px;
    border: 1px solid var(--border);
  }
  .policy-card.warning { border-left: 3px solid var(--burnt-orange); }
  .policy-card.info { border-left: 3px solid var(--coral); }
  .policy-card-title {
    font-weight: 600;
    font-size: 14px;
    color: var(--text-primary);
    margin-bottom: 8px;
  }
  .policy-card-body { font-size: 13.5px; color: var(--text-muted); line-height: 1.6; }
  .policy-card-body strong { color: var(--text-secondary); }

  /* RESOURCES */
  .resource-list { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
  .resource-item {
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px 18px;
    display: flex;
    align-items: center;
    gap: 12px;
    font-size: 14px;
    color: var(--text-secondary);
  }
  .resource-icon {
    width: 32px; height: 32px;
    background: linear-gradient(135deg, var(--burnt-orange), var(--coral));
    border-radius: 6px;
    display: flex; align-items: center; justify-content: center;
    font-size: 14px;
    flex-shrink: 0;
  }
  .resource-item strong { color: var(--text-primary); }
  .resource-item a { color: var(--coral); text-decoration: none; font-weight: 600; }
  .resource-item a:hover { text-decoration: underline; }

  /* FOOTER */
  .footer {
    background: var(--bg-code);
    border-top: 1px solid var(--border);
    color: var(--text-muted);
    text-align: center;
    padding: 28px 48px;
    font-size: 13px;
  }
  .footer strong { color: var(--warm-sand); }

  @media (max-width: 640px) {
    .hero { padding: 48px 24px 40px; }
    .hero h1 { font-size: 36px; }
    .container { padding: 40px 24px; }
    .instructor-grid, .outcomes-grid, .policy-grid, .resource-list { grid-template-columns: 1fr; }
    .hero-meta { gap: 20px; }
    .textbook-card { flex-direction: column; }
  }
</style>
</head>
<body>

<div class="hero">
  <div class="hero-badge">Fayetteville Technical Community College</div>
  <h1>CSC 114 – <span>Artificial</span><br>Intelligence I</h1>
  <p class="hero-subtitle">Information Technology · Section 1001</p>
  <div class="hero-meta">
    <div class="hero-meta-item">
      <span class="hero-meta-label">Location</span>
      <span class="hero-meta-value">ATC 115</span>
    </div>
    <div class="hero-meta-item">
      <span class="hero-meta-label">Schedule</span>
      <span class="hero-meta-value">MW 10:00–11:50 AM</span>
    </div>
    <div class="hero-meta-item">
      <span class="hero-meta-label">Dates</span>
      <span class="hero-meta-value">May 26 – July 20, 2026</span>
    </div>
    <div class="hero-meta-item">
      <span class="hero-meta-label">Credit Hours</span>
      <span class="hero-meta-value">3.00</span>
    </div>
  </div>
</div>

<div class="container">

  <div class="section">
    <div class="section-header">
      <div class="section-icon">📖</div>
      <h2 class="section-title">About This Course</h2>
    </div>
    <div class="section-divider"></div>
    <p class="about-text">This repo contains coursework for CSC 114, covering the design of intelligent agents and rational decision-making systems. Topics span search techniques, optimization, logic, probabilistic reasoning, and machine learning — with hands-on work in Keras and PyTorch.</p>
    <span class="prereq-tag">Prerequisite: CSC-113</span>
  </div>

  <div class="section">
    <div class="section-header">
      <div class="section-icon">👩‍🏫</div>
      <h2 class="section-title">Instructors</h2>
    </div>
    <div class="section-divider"></div>
    <div class="instructor-grid">
      <div class="instructor-card">
        <div class="instructor-name">Mallory Milstead</div>
        <div class="instructor-detail"><strong>Office:</strong> ATC-113H</div>
        <div class="instructor-detail"><strong>Phone:</strong> 910-678-8572</div>
        <div class="instructor-detail"><strong>Email:</strong> <a href="mailto:milsteam@faytechcc.edu">milsteam@faytechcc.edu</a></div>
        <div class="instructor-detail" style="margin-top:8px;font-size:12px;color:#4a6a72;">Office hours by request (Summer)</div>
      </div>
      <div class="instructor-card">
        <div class="instructor-name">Andrew Norris</div>
        <div class="instructor-detail"><strong>Office:</strong> ATC-113C</div>
        <div class="instructor-detail"><strong>Phone:</strong> 910-486-3967</div>
        <div class="instructor-detail"><strong>Email:</strong> <a href="mailto:norrisa@faytechcc.edu">norrisa@faytechcc.edu</a></div>
        <div class="instructor-detail" style="margin-top:8px;font-size:12px;color:#4a6a72;">Office hours by request (Summer)</div>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-header">
      <div class="section-icon">🎯</div>
      <h2 class="section-title">Learning Outcomes</h2>
    </div>
    <div class="section-divider"></div>
    <div class="outcomes-grid">
      <div class="outcome-item"><div class="outcome-dot"></div>Build a custom intelligent agent</div>
      <div class="outcome-item"><div class="outcome-dot"></div>Apply AI frameworks — Keras &amp; PyTorch</div>
      <div class="outcome-item"><div class="outcome-dot"></div>Implement classification &amp; regression algorithms</div>
      <div class="outcome-item"><div class="outcome-dot"></div>Train a model using the full ML workflow</div>
      <div class="outcome-item"><div class="outcome-dot"></div>Apply computer vision fundamentals</div>
      <div class="outcome-item"><div class="outcome-dot"></div>Implement NLP algorithms</div>
      <div class="outcome-item"><div class="outcome-dot"></div>Demonstrate foundational deep learning knowledge</div>
      <div class="outcome-item"><div class="outcome-dot"></div>Use and optimize large language models</div>
    </div>
  </div>

  <div class="section">
    <div class="section-header">
      <div class="section-icon">📚</div>
      <h2 class="section-title">Required Textbook</h2>
    </div>
    <div class="section-divider"></div>
    <div class="textbook-card">
      <div class="book-spine">📘</div>
      <div>
        <div class="textbook-title">Deep Learning with Python, 3rd Edition</div>
        <div class="textbook-meta">François Chollet &amp; Matthew Watson<br>Manning Publications Co., 2026</div>
        <div class="isbn-tag">ISBN: 9781633436589</div>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-header">
      <div class="section-icon">📅</div>
      <h2 class="section-title">Assignment Schedule</h2>
    </div>
    <div class="section-divider"></div>
    <table class="schedule-table">
      <thead>
        <tr>
          <th>Due Date</th>
          <th>Assignment</th>
        </tr>
      </thead>
      <tbody>
        <tr><td>5/30/26</td><td>Module 0 Quiz</td></tr>
        <tr><td>6/7/26</td><td>Create a Custom Agent</td></tr>
        <tr><td>6/21/26</td><td>Apply AI Frameworks</td></tr>
        <tr><td>6/21/26</td><td>Assess AI Frameworks</td></tr>
        <tr><td>6/28/26</td><td>Apply Classification &amp; Regression</td></tr>
        <tr><td>6/28/26</td><td>Assess Classification &amp; Regression</td></tr>
        <tr><td>7/5/26</td><td>Apply Machine Learning Workflow</td></tr>
        <tr><td>7/5/26</td><td>Assess Machine Learning Workflow</td></tr>
        <tr><td>7/12/26</td><td>Apply Computer Vision</td></tr>
        <tr><td>7/12/26</td><td>Assess Computer Vision</td></tr>
        <tr><td>7/19/26</td><td>Apply NLP and LLMs</td></tr>
        <tr><td>7/19/26</td><td>Assess NLP and LLMs</td></tr>
        <tr class="final-row"><td>7/20/26</td><td>🏁 Final Project</td></tr>
      </tbody>
    </table>
  </div>

  <div class="section">
    <div class="section-header">
      <div class="section-icon">⚙️</div>
      <h2 class="section-title">Setup</h2>
    </div>
    <div class="section-divider"></div>
    <div class="setup-step">
      <div class="setup-label">Clone &amp; Navigate</div>
      <div class="setup-code"><span class="cmd">git clone</span> &lt;repo-url&gt;
<span class="cmd">cd</span> csc114-ai</div>
    </div>
    <div class="setup-step">
      <div class="setup-label">Virtual Environment</div>
      <div class="setup-code"><span class="cmd">python -m venv</span> .venv
<span class="cmd">source</span> .venv/bin/activate   <span class="comment"># Windows: .venv\Scripts\activate</span></div>
    </div>
    <div class="setup-step">
      <div class="setup-label">Install Dependencies</div>
      <div class="setup-code"><span class="cmd">pip install</span> torch tensorflow keras numpy pandas scikit-learn matplotlib</div>
    </div>
  </div>

  <div class="section">
    <div class="section-header">
      <div class="section-icon">📋</div>
      <h2 class="section-title">Policies</h2>
    </div>
    <div class="section-divider"></div>
    <div class="policy-grid">
      <div class="policy-card info">
        <div class="policy-card-title">⏰ Late Work</div>
        <div class="policy-card-body">–10 points per business day. Accepted up to <strong>2 weeks</strong> after due date. Hard cutoff: <strong>July 19, 2026</strong>.</div>
      </div>
      <div class="policy-card info">
        <div class="policy-card-title">📝 Extensions</div>
        <div class="policy-card-body">Request <strong>before</strong> the due date. Documentation required for extenuating circumstances. Computer/internet issues do not qualify.</div>
      </div>
      <div class="policy-card warning">
        <div class="policy-card-title">🚫 Academic Integrity</div>
        <div class="policy-card-body">Submitting <strong>AI-generated work</strong> (ChatGPT, etc.) as your own is plagiarism — zero, course failure, or further action.</div>
      </div>
      <div class="policy-card warning">
        <div class="policy-card-title">✅ Attendance</div>
        <div class="policy-card-body">Must participate <strong>on or before census date</strong> (first 10% of term) to avoid being dropped as a No Show.</div>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-header">
      <div class="section-icon">🏫</div>
      <h2 class="section-title">Resources</h2>
    </div>
    <div class="section-divider"></div>
    <div class="resource-list">
      <div class="resource-item">
        <div class="resource-icon">🛒</div>
        <div><strong>FTCC Bookstore</strong><br><a href="https://bookstore.faytechcc.edu/" target="_blank">bookstore.faytechcc.edu</a></div>
      </div>
      <div class="resource-item">
        <div class="resource-icon">💼</div>
        <div><strong>Microsoft 365</strong> (free)<br><a href="https://login.microsoftonline.com" target="_blank">login.microsoftonline.com</a></div>
      </div>
      <div class="resource-item">
        <div class="resource-icon">🎓</div>
        <div><strong>Canvas Support</strong><br>1-866-645-6305 (24/7)</div>
      </div>
      <div class="resource-item">
        <div class="resource-icon">♿</div>
        <div><strong>Disability Support Services</strong><br>ATC Tony Rand, Rm 127 · 910-678-8559</div>
      </div>
    </div>
  </div>

</div>

<div class="footer">
  <strong>CSC 114 – Artificial Intelligence I</strong> · Fayetteville Technical Community College · Section 1001<br>
  <span style="margin-top:6px;display:block;">Syllabus subject to change with notice via Canvas Announcements and student email.</span>
</div>

</body>
</html>
