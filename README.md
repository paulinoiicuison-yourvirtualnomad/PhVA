# PhVA<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Paulino Cuison — Executive Virtual Assistant</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --navy: #0B1120;
    --navy-mid: #152035;
    --navy-soft: #1E2F4A;
    --gold: #C9A84C;
    --gold-light: #E8C97A;
    --gold-pale: #F5E9C8;
    --cream: #F8F4EC;
    --white: #FFFFFF;
    --text-muted: #8A99B0;
    --text-body: #D0D8E8;
    --border: rgba(201,168,76,0.18);
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }
  body {
    background: var(--navy);
    color: var(--text-body);
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.25rem 4rem;
    background: rgba(11,17,32,0.92);
    backdrop-filter: blur(12px);
    border-bottom: 0.5px solid var(--border);
  }
  .nav-logo {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.25rem;
    font-weight: 600;
    color: var(--gold);
    letter-spacing: 0.08em;
    text-transform: uppercase;
    text-decoration: none;
  }
  .nav-links { display: flex; gap: 2.5rem; list-style: none; }
  .nav-links a {
    color: var(--text-muted);
    text-decoration: none;
    font-size: 0.8rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    font-weight: 400;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--gold-light); }
  .nav-cta {
    background: transparent;
    border: 0.5px solid var(--gold);
    color: var(--gold);
    padding: 0.55rem 1.5rem;
    font-size: 0.75rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    text-decoration: none;
    font-family: 'DM Sans', sans-serif;
    font-weight: 400;
    cursor: pointer;
    transition: all 0.2s;
  }
  .nav-cta:hover { background: var(--gold); color: var(--navy); }

  /* ── HERO ── */
  #home {
    min-height: 100vh;
    display: flex; align-items: center;
    padding: 8rem 4rem 5rem;
    position: relative;
    overflow: hidden;
  }
  .hero-grid-bg {
    position: absolute; inset: 0;
    background-image:
      linear-gradient(rgba(201,168,76,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(201,168,76,0.04) 1px, transparent 1px);
    background-size: 60px 60px;
  }
  .hero-glow {
    position: absolute;
    width: 600px; height: 600px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(201,168,76,0.07) 0%, transparent 70%);
    top: -100px; right: -100px;
    pointer-events: none;
  }
  .hero-inner {
    position: relative; z-index: 1;
    max-width: 1100px; margin: 0 auto; width: 100%;
  }
  .hero-eyebrow {
    display: inline-flex; align-items: center; gap: 0.75rem;
    font-size: 0.72rem; letter-spacing: 0.18em; text-transform: uppercase;
    color: var(--gold); font-weight: 400; margin-bottom: 2rem;
    opacity: 0; animation: fadeUp 0.8s 0.2s forwards;
  }
  .hero-eyebrow::before {
    content: ''; display: block;
    width: 32px; height: 0.5px; background: var(--gold);
  }
  .hero-h1 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(3rem, 7vw, 6rem);
    font-weight: 300;
    line-height: 1.08;
    color: var(--white);
    margin-bottom: 1.5rem;
    opacity: 0; animation: fadeUp 0.8s 0.4s forwards;
  }
  .hero-h1 em { font-style: italic; color: var(--gold-light); }
  .hero-sub {
    font-size: 1rem; color: var(--text-muted);
    max-width: 560px; line-height: 1.8;
    margin-bottom: 2.5rem;
    opacity: 0; animation: fadeUp 0.8s 0.6s forwards;
  }
  .hero-actions {
    display: flex; gap: 1rem; flex-wrap: wrap;
    opacity: 0; animation: fadeUp 0.8s 0.8s forwards;
  }
  .btn-primary {
    background: var(--gold);
    color: var(--navy);
    padding: 0.85rem 2.25rem;
    font-size: 0.8rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    text-decoration: none;
    font-family: 'DM Sans', sans-serif;
    font-weight: 500;
    transition: all 0.2s;
    display: inline-block;
  }
  .btn-primary:hover { background: var(--gold-light); }
  .btn-outline {
    border: 0.5px solid rgba(255,255,255,0.2);
    color: var(--text-body);
    padding: 0.85rem 2.25rem;
    font-size: 0.8rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    text-decoration: none;
    font-family: 'DM Sans', sans-serif;
    font-weight: 400;
    transition: all 0.2s;
    display: inline-block;
  }
  .btn-outline:hover { border-color: var(--gold); color: var(--gold); }
  .hero-stats {
    display: flex; gap: 3rem; margin-top: 4rem;
    padding-top: 2.5rem;
    border-top: 0.5px solid var(--border);
    opacity: 0; animation: fadeUp 0.8s 1s forwards;
  }
  .hero-stat-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 2.5rem; font-weight: 300;
    color: var(--gold-light); line-height: 1;
    margin-bottom: 0.25rem;
  }
  .hero-stat-label {
    font-size: 0.72rem; text-transform: uppercase;
    letter-spacing: 0.1em; color: var(--text-muted);
  }

  /* ── SECTIONS SHARED ── */
  section { padding: 7rem 4rem; }
  .section-inner { max-width: 1100px; margin: 0 auto; }
  .section-tag {
    display: inline-flex; align-items: center; gap: 0.75rem;
    font-size: 0.72rem; letter-spacing: 0.18em;
    text-transform: uppercase; color: var(--gold);
    margin-bottom: 1.25rem;
  }
  .section-tag::before {
    content: ''; width: 24px; height: 0.5px; background: var(--gold);
  }
  .section-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(2rem, 4vw, 3.25rem);
    font-weight: 300;
    color: var(--white); line-height: 1.15;
    margin-bottom: 1.25rem;
  }
  .section-title em { font-style: italic; color: var(--gold-light); }

  /* ── ABOUT ── */
  #about { background: var(--navy-mid); }
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1.6fr;
    gap: 5rem; align-items: start;
  }
  .about-left { position: sticky; top: 8rem; }
  .about-avatar {
    width: 100%; aspect-ratio: 3/4;
    background: var(--navy-soft);
    border: 0.5px solid var(--border);
    display: flex; align-items: center; justify-content: center;
    margin-bottom: 1.5rem;
    position: relative; overflow: hidden;
  }
  .avatar-initials {
    font-family: 'Cormorant Garamond', serif;
    font-size: 5rem; font-weight: 300;
    color: var(--gold); letter-spacing: 0.05em;
  }
  .avatar-note {
    position: absolute; bottom: 1rem; left: 1rem; right: 1rem;
    font-size: 0.7rem; color: var(--text-muted);
    text-align: center; letter-spacing: 0.08em;
  }
  .creds-list { list-style: none; }
  .creds-list li {
    padding: 0.6rem 0;
    border-bottom: 0.5px solid var(--border);
    font-size: 0.8rem; color: var(--text-muted);
    display: flex; align-items: center; gap: 0.75rem;
  }
  .creds-list li::before {
    content: '—'; color: var(--gold); font-size: 0.7rem;
  }
  .about-body p {
    font-size: 1rem; line-height: 1.85;
    color: var(--text-body); margin-bottom: 1.5rem;
  }
  .about-body p.lead {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.35rem; font-weight: 300;
    font-style: italic; color: var(--white);
    line-height: 1.6;
  }
  .skills-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 1rem; margin-top: 2.5rem;
  }
  .skill-item {
    padding: 1rem 1.25rem;
    border: 0.5px solid var(--border);
    background: rgba(201,168,76,0.03);
  }
  .skill-name {
    font-size: 0.8rem; font-weight: 500;
    color: var(--gold-light); margin-bottom: 0.25rem;
  }
  .skill-desc { font-size: 0.75rem; color: var(--text-muted); }

  /* ── SERVICES ── */
  #services { background: var(--navy); }
  .services-intro {
    max-width: 620px; margin-bottom: 4rem;
  }
  .services-intro p { color: var(--text-muted); font-size: 0.95rem; }
  .services-grid {
    display: grid; grid-template-columns: repeat(2, 1fr);
    gap: 1.5px; background: var(--border);
  }
  .service-card {
    background: var(--navy);
    padding: 2.5rem 2rem;
    position: relative; overflow: hidden;
    transition: background 0.3s;
  }
  .service-card:hover { background: var(--navy-soft); }
  .service-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0;
    height: 2px; background: var(--gold);
    transform: scaleX(0); transform-origin: left;
    transition: transform 0.3s;
  }
  .service-card:hover::before { transform: scaleX(1); }
  .service-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 3.5rem; font-weight: 300;
    color: rgba(201,168,76,0.1); line-height: 1;
    margin-bottom: 1.25rem;
  }
  .service-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.5rem; font-weight: 400;
    color: var(--white); margin-bottom: 1rem;
    line-height: 1.25;
  }
  .service-desc {
    font-size: 0.85rem; color: var(--text-muted);
    line-height: 1.75; margin-bottom: 1.75rem;
  }
  .service-list { list-style: none; }
  .service-list li {
    font-size: 0.78rem; color: var(--text-body);
    padding: 0.4rem 0;
    border-bottom: 0.5px solid rgba(201,168,76,0.08);
    display: flex; gap: 0.6rem;
  }
  .service-list li::before { content: '›'; color: var(--gold); }
  .service-tag {
    margin-top: 1.75rem;
    display: inline-block;
    font-size: 0.7rem; letter-spacing: 0.1em;
    text-transform: uppercase; color: var(--gold);
    border: 0.5px solid var(--border);
    padding: 0.35rem 0.85rem;
  }

  .additional-support {
    margin-top: 3rem;
    border: 0.5px solid var(--border);
    padding: 2rem 2.5rem;
    background: rgba(201,168,76,0.02);
  }
  .additional-support-title {
    font-size: 0.72rem; letter-spacing: 0.16em;
    text-transform: uppercase; color: var(--gold);
    margin-bottom: 1.5rem;
    display: flex; align-items: center; gap: 0.75rem;
  }
  .additional-support-title::after {
    content: ''; flex: 1; height: 0.5px; background: var(--border);
  }
  .additional-grid {
    display: grid; grid-template-columns: repeat(2, 1fr);
    gap: 1.25rem 3rem;
  }
  .additional-item {
    display: flex; gap: 0.75rem; align-items: flex-start;
  }
  .additional-icon {
    color: var(--gold); font-size: 1rem; line-height: 1.4; flex-shrink: 0;
  }
  .additional-name {
    font-size: 0.82rem; font-weight: 500;
    color: var(--white); margin-bottom: 0.2rem;
  }
  .additional-desc {
    font-size: 0.75rem; color: var(--text-muted); line-height: 1.6;
  }

  /* ── WHY ME ── */
  #why { background: var(--navy-mid); }
  .why-grid {
    display: grid; grid-template-columns: 1.4fr 1fr;
    gap: 5rem; align-items: center;
  }
  .differentiator {
    display: flex; gap: 1.5rem;
    padding: 1.75rem 0;
    border-bottom: 0.5px solid var(--border);
  }
  .diff-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 2rem; font-weight: 300;
    color: var(--gold); flex-shrink: 0;
    line-height: 1;
  }
  .diff-title {
    font-size: 0.9rem; font-weight: 500;
    color: var(--white); margin-bottom: 0.4rem;
  }
  .diff-text { font-size: 0.82rem; color: var(--text-muted); line-height: 1.7; }
  .cert-block {
    background: var(--navy-soft);
    border: 0.5px solid var(--border);
    padding: 2rem;
  }
  .cert-block-title {
    font-size: 0.7rem; text-transform: uppercase;
    letter-spacing: 0.12em; color: var(--gold);
    margin-bottom: 1.5rem;
  }
  .cert-item {
    padding: 0.85rem 0;
    border-bottom: 0.5px solid var(--border);
    font-size: 0.82rem; color: var(--text-body);
  }
  .cert-item:last-child { border-bottom: none; }
  .cert-item span { display: block; font-size: 0.7rem; color: var(--text-muted); margin-top: 2px; }

  /* ── CONTACT ── */
  #contact { background: var(--navy); }
  .contact-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 5rem; align-items: start;
  }
  .contact-left p {
    font-size: 0.9rem; color: var(--text-muted);
    line-height: 1.8; margin-bottom: 2rem;
  }
  .contact-detail {
    display: flex; align-items: flex-start; gap: 1rem;
    margin-bottom: 1.25rem;
  }
  .contact-detail-label {
    font-size: 0.7rem; text-transform: uppercase;
    letter-spacing: 0.1em; color: var(--gold);
    min-width: 70px; padding-top: 2px;
  }
  .contact-detail-val {
    font-size: 0.85rem; color: var(--text-body);
  }
  .contact-form {
    display: flex; flex-direction: column; gap: 1rem;
  }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  .form-group { display: flex; flex-direction: column; gap: 0.4rem; }
  .form-label {
    font-size: 0.7rem; text-transform: uppercase;
    letter-spacing: 0.1em; color: var(--text-muted);
  }
  .form-input, .form-select, .form-textarea {
    background: var(--navy-soft);
    border: 0.5px solid var(--border);
    color: var(--text-body);
    padding: 0.75rem 1rem;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.85rem;
    font-weight: 300;
    outline: none;
    transition: border-color 0.2s;
    width: 100%;
  }
  .form-input:focus, .form-select:focus, .form-textarea:focus {
    border-color: var(--gold);
  }
  .form-textarea { resize: vertical; min-height: 120px; }
  .form-select { appearance: none; cursor: pointer; }
  .form-submit {
    background: var(--gold);
    color: var(--navy);
    border: none;
    padding: 1rem 2.5rem;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.8rem;
    font-weight: 500;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    cursor: pointer;
    transition: background 0.2s;
    align-self: flex-start;
  }
  .form-submit:hover { background: var(--gold-light); }
  .form-note { font-size: 0.75rem; color: var(--text-muted); margin-top: 0.25rem; }

  /* ── FOOTER ── */
  footer {
    padding: 2.5rem 4rem;
    border-top: 0.5px solid var(--border);
    display: flex; align-items: center; justify-content: space-between;
    flex-wrap: wrap; gap: 1rem;
  }
  .footer-logo {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1rem; font-weight: 600;
    color: var(--gold); letter-spacing: 0.08em;
    text-transform: uppercase;
  }
  .footer-copy { font-size: 0.75rem; color: var(--text-muted); }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .reveal {
    opacity: 0; transform: translateY(28px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .reveal.visible { opacity: 1; transform: translateY(0); }

  /* ── MOBILE ── */
  @media (max-width: 900px) {
    nav { padding: 1.25rem 1.5rem; }
    .nav-links { display: none; }
    section { padding: 5rem 1.5rem; }
    #home { padding: 7rem 1.5rem 4rem; }
    .about-grid, .why-grid, .contact-grid { grid-template-columns: 1fr; gap: 2.5rem; }
    .about-left { position: static; }
    .services-grid { grid-template-columns: 1fr; }
    .additional-grid { grid-template-columns: 1fr; }
    .skills-grid { grid-template-columns: 1fr; }
    .hero-stats { flex-wrap: wrap; gap: 1.5rem; }
    .form-row { grid-template-columns: 1fr; }
    footer { padding: 2rem 1.5rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#home">P. Cuison</a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#why">Why Me</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a class="nav-cta" href="#contact">Book a Call</a>
</nav>

<!-- HERO -->
<section id="home">
  <div class="hero-grid-bg"></div>
  <div class="hero-glow"></div>
  <div class="hero-inner">
    <div class="hero-eyebrow">Executive Virtual Assistant</div>
    <h1 class="hero-h1">
      You need more than<br>
      a task-taker.<br>
      You need <em>a strategic<br>partner.</em>
    </h1>
    <p class="hero-sub">
      I'm Paulino — an Executive VA with 10+ years in project management, BPO operations, and stakeholder engagement. I help executives, business owners, and founders reclaim their time and grow their pipeline — without the overhead of a full-time hire.
    </p>
    <div class="hero-actions">
      <a class="btn-primary" href="#contact">Let's Work Together</a>
      <a class="btn-outline" href="#services">See My Services</a>
    </div>
    <div class="hero-stats">
      <div>
        <div class="hero-stat-num">10+</div>
        <div class="hero-stat-label">Years of Experience</div>
      </div>
      <div>
        <div class="hero-stat-num">3</div>
        <div class="hero-stat-label">Core Service Areas</div>
      </div>
      <div>
        <div class="hero-stat-num">LSS</div>
        <div class="hero-stat-label">Lean Six Sigma Certified</div>
      </div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="section-inner">
    <div class="about-grid">
      <div class="about-left reveal">
        <div class="about-avatar" style="padding:0; overflow:hidden; background:#0B1120;">
          <img src="data:image/jpeg;base64,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" alt="Paulino Cuison" style="width:100%; height:100%; object-fit:cover; object-position:center top; display:block;">
        </div>
        <ul class="creds-list">
          <li>BA Communication — UP Baguio, 2012</li>
          <li>MA Filipino (Units) — UP Diliman</li>
          <li>Lean Six Sigma Yellow Belt</li>
          <li>ICMI L&D Certification</li>
          <li>iAspire Leadership Program</li>
          <li>Senior Project Coordinator — IDC</li>
          <li>Learning Services Lead — TELUS Int'l</li>
        </ul>
      </div>
      <div class="about-body reveal">
        <div class="section-tag">About Me</div>
        <h2 class="section-title">I didn't start as a<br><em>virtual assistant.</em><br>I started as a project leader.</h2>
        <p class="lead">"The best support isn't reactive — it's anticipatory. I deliver results before you realise you needed them."</p>
        <p>Over the past decade, I've managed complex programs, led cross-functional teams across BPO and market research environments, and advised C-suite executives on strategy, transitions, and operational readiness. I've prepared boardroom briefings and handled the operational details that made those decisions possible.</p>
        <p>Now I bring that same executive-level discipline to founders and leaders who need a right hand they can trust — someone who thinks ahead, communicates clearly, and delivers without micromanagement.</p>
        <p>My background in Learning & Development means I don't just execute your processes. I refine them. My project management experience means I don't just manage tasks. I manage outcomes.</p>
        <div class="skills-grid">
          <div class="skill-item">
            <div class="skill-name">Stakeholder Management</div>
            <div class="skill-desc">Executive briefings, client presentations, cross-functional alignment</div>
          </div>
          <div class="skill-item">
            <div class="skill-name">Risk Management</div>
            <div class="skill-desc">Proactive identification and mitigation across projects</div>
          </div>
          <div class="skill-item">
            <div class="skill-name">Process Improvement</div>
            <div class="skill-desc">Lean Six Sigma methodology applied to every workflow</div>
          </div>
          <div class="skill-item">
            <div class="skill-name">Strategic Communication</div>
            <div class="skill-desc">Clear, precise written and verbal communication across levels</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="services">
  <div class="section-inner">
    <div class="services-intro reveal">
      <div class="section-tag">Services</div>
      <h2 class="section-title">Four areas. <em>One trusted partner.</em></h2>
      <p>Every service I offer is built around one goal: giving you back your time while moving your business forward.</p>
    </div>
    <div class="services-grid">
      <div class="service-card reveal">
        <div class="service-num">01</div>
        <div class="service-name">General Administrative Assistance</div>
        <p class="service-desc">The backbone of a well-run operation. I keep your day-to-day organised, responsive, and running smoothly so you can focus on what only you can do.</p>
        <ul class="service-list">
          <li>Email inbox management &amp; organisation</li>
          <li>Calendar management &amp; scheduling</li>
          <li>Meeting &amp; appointment coordination</li>
          <li>Data entry, research &amp; document organisation</li>
          <li>Client communication &amp; follow-ups</li>
          <li>Project updates &amp; task coordination</li>
        </ul>
        <div class="service-tag">Best for: Executives &amp; Business Owners</div>
      </div>
      <div class="service-card reveal">
        <div class="service-num">02</div>
        <div class="service-name">Lead Generation &amp; Pipeline Building</div>
        <p class="service-desc">I identify, qualify, and organise prospect lists so your sales pipeline stays full — without you spending hours on research.</p>
        <ul class="service-list">
          <li>Targeted prospect research &amp; list building</li>
          <li>Lead qualification &amp; scoring</li>
          <li>CRM management &amp; database updates</li>
          <li>Outreach list preparation</li>
          <li>Pipeline reporting &amp; tracking</li>
        </ul>
        <div class="service-tag">Best for: Founders &amp; Sales Teams</div>
      </div>
      <div class="service-card reveal">
        <div class="service-num">03</div>
        <div class="service-name">Email Marketing Support</div>
        <p class="service-desc">From campaign planning to scheduling and reporting, I manage your email marketing so your audience stays engaged and your offers convert.</p>
        <ul class="service-list">
          <li>Campaign strategy &amp; planning</li>
          <li>List management &amp; segmentation</li>
          <li>Basic content setup &amp; scheduling</li>
          <li>Performance tracking &amp; reporting</li>
          <li>Automation setup support</li>
        </ul>
        <div class="service-tag">Best for: Coaches &amp; SMB Owners</div>
      </div>
      <div class="service-card reveal">
        <div class="service-num">04</div>
        <div class="service-name">Client Pre-Screening &amp; Interview Coordination</div>
        <p class="service-desc">I handle the intake process so you only meet candidates and clients who are already a strong fit — saving time and improving conversion quality.</p>
        <ul class="service-list">
          <li>Application &amp; inquiry screening</li>
          <li>Discovery call facilitation</li>
          <li>Evaluation using your criteria</li>
          <li>Scheduling &amp; coordination</li>
          <li>Summary reports for your review</li>
        </ul>
        <div class="service-tag">Best for: Agencies &amp; Executives</div>
      </div>
    </div>

    <!-- ADDITIONAL SUPPORT -->
    <div class="additional-support reveal">
      <div class="additional-support-title">Additional Support Areas</div>
      <div class="additional-grid">
        <div class="additional-item">
          <div class="additional-icon">›</div>
          <div>
            <div class="additional-name">Project Management Assistance</div>
            <div class="additional-desc">Task tracking, milestone coordination, and progress reporting</div>
          </div>
        </div>
        <div class="additional-item">
          <div class="additional-icon">›</div>
          <div>
            <div class="additional-name">CRM Management</div>
            <div class="additional-desc">Database updates, contact maintenance, and record accuracy</div>
          </div>
        </div>
        <div class="additional-item">
          <div class="additional-icon">›</div>
          <div>
            <div class="additional-name">Reporting &amp; Metrics Tracking</div>
            <div class="additional-desc">Creating reports and tracking the KPIs that matter to your business</div>
          </div>
        </div>
        <div class="additional-item">
          <div class="additional-icon">›</div>
          <div>
            <div class="additional-name">Process Documentation</div>
            <div class="additional-desc">Workflow improvements, SOPs, and operational documentation</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- WHY ME -->
<section id="why">
  <div class="section-inner">
    <div class="why-grid">
      <div class="reveal">
        <div class="section-tag">Why Work With Me</div>
        <h2 class="section-title">The VA who thinks <em>like your most trusted executive.</em></h2>
        <div class="differentiator">
          <div class="diff-num">01</div>
          <div>
            <div class="diff-title">Project-Grade Execution</div>
            <div class="diff-text">Most VAs complete tasks. I deliver outcomes. My PM background means every engagement comes with accountability systems, risk awareness, and governance — not just a to-do list.</div>
          </div>
        </div>
        <div class="differentiator">
          <div class="diff-num">02</div>
          <div>
            <div class="diff-title">Executive-Level Communication</div>
            <div class="diff-text">I've prepared C-suite briefings, led stakeholder presentations, and managed multi-level communication across large organisations. Your clients and partners will be in good hands.</div>
          </div>
        </div>
        <div class="differentiator">
          <div class="diff-num">03</div>
          <div>
            <div class="diff-title">Process Improvement Built In</div>
            <div class="diff-text">As a Lean Six Sigma practitioner, I don't just follow your workflows — I identify inefficiencies and recommend improvements that compound over time.</div>
          </div>
        </div>
        <div class="differentiator">
          <div class="diff-num">04</div>
          <div>
            <div class="diff-title">No Micromanagement Needed</div>
            <div class="diff-text">A decade of managing cross-functional teams has made me deeply self-directed. You brief me once; I deliver consistently.</div>
          </div>
        </div>
      </div>
      <div class="reveal">
        <div class="cert-block">
          <div class="cert-block-title">Credentials &amp; Background</div>
          <div class="cert-item">
            Senior Project Coordinator
            <span>IDC Market Research Philippines — 2024 to Present</span>
          </div>
          <div class="cert-item">
            Learning &amp; Development Lead
            <span>Cloud Nine Solutions — 2024</span>
          </div>
          <div class="cert-item">
            Learning Services Lead
            <span>TELUS International Philippines — 2014 to 2023</span>
          </div>
          <div class="cert-item">
            Lean Six Sigma — Yellow Belt
            <span>TELUS International Philippines</span>
          </div>
          <div class="cert-item">
            ICMI Learning &amp; Development Certification
            <span>International certification in L&D</span>
          </div>
          <div class="cert-item">
            iAspire Accelerated Leadership Program
            <span>Leadership Development Training</span>
          </div>
          <div class="cert-item">
            BA Communication
            <span>University of the Philippines Baguio, 2012</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="section-inner">
    <div class="contact-grid">
      <div class="reveal">
        <div class="section-tag">Contact</div>
        <h2 class="section-title">Ready to delegate <em>with confidence?</em></h2>
        <p>Let's start with a 30-minute discovery call — no pressure, no commitment. We'll talk about your needs, your goals, and whether we're a good fit.</p>
        <div class="contact-detail">
          <div class="contact-detail-label">Email</div>
          <div class="contact-detail-val">paulinoii.cuison@gmail.com</div>
        </div>
        <div class="contact-detail">
          <div class="contact-detail-label">Phone</div>
          <div class="contact-detail-val">+63 969 047 2344</div>
        </div>
        <div class="contact-detail">
          <div class="contact-detail-label">Location</div>
          <div class="contact-detail-val">Dagupan City, Pangasinan, Philippines</div>
        </div>
        <div class="contact-detail">
          <div class="contact-detail-label">Availability</div>
          <div class="contact-detail-val">Open to project-based and retainer engagements</div>
        </div>
      </div>
      <div class="reveal">
        <form class="contact-form" id="contactForm" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
          <input type="hidden" name="_subject" value="New Inquiry from Portfolio Website">
          <input type="hidden" name="_replyto" value="">
          <div class="form-row">
            <div class="form-group">
              <label class="form-label">First Name</label>
              <input class="form-input" type="text" name="first_name" placeholder="Jane" required>
            </div>
            <div class="form-group">
              <label class="form-label">Last Name</label>
              <input class="form-input" type="text" name="last_name" placeholder="Smith" required>
            </div>
          </div>
          <div class="form-group">
            <label class="form-label">Email Address</label>
            <input class="form-input" type="email" name="email" placeholder="jane@company.com" required>
          </div>
          <div class="form-group">
            <label class="form-label">I'm interested in</label>
            <select class="form-select form-input" name="service">
              <option value="">Select a service...</option>
              <option>General Administrative Assistance</option>
              <option>Lead Generation &amp; Pipeline Building</option>
              <option>Email Marketing Support</option>
              <option>Client Pre-Screening &amp; Interview Coordination</option>
              <option>Project Management Assistance</option>
              <option>CRM Management</option>
              <option>Reporting &amp; Metrics Tracking</option>
              <option>Process Documentation &amp; Workflow Improvements</option>
              <option>Multiple Services</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label">Tell me about your needs</label>
            <textarea class="form-textarea" name="message" placeholder="A brief overview of your project or requirements..."></textarea>
          </div>
          <button class="form-submit" type="submit" id="submitBtn">Send Message</button>
          <p class="form-note" id="formNote">I typically respond within 24 hours.</p>
          <div id="formSuccess" style="display:none; margin-top:1rem; padding:1rem 1.25rem; border:0.5px solid rgba(74,156,111,0.4); background:rgba(74,156,111,0.06); font-size:0.83rem; color:#6bcfa0; line-height:1.6;">
            Thank you for reaching out! Your message has been sent to paulinoii.cuison@gmail.com. I'll be in touch within 24 hours.
          </div>
          <div id="formError" style="display:none; margin-top:1rem; padding:1rem 1.25rem; border:0.5px solid rgba(226,75,74,0.4); background:rgba(226,75,74,0.06); font-size:0.83rem; color:#f09595; line-height:1.6;">
            Something went wrong. Please try again or email me directly at paulinoii.cuison@gmail.com
          </div>
        </form>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">Paulino II A. Cuison</div>
  <div class="footer-copy">© 2025 Paulino Cuison. Executive Virtual Assistant.</div>
</footer>

<script>
  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 80);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1 });
  reveals.forEach(el => observer.observe(el));

  // Formspree async submission
  const form = document.getElementById('contactForm');
  const submitBtn = document.getElementById('submitBtn');
  const formSuccess = document.getElementById('formSuccess');
  const formError = document.getElementById('formError');
  const formNote = document.getElementById('formNote');

  form.addEventListener('submit', async function(e) {
    e.preventDefault();
    submitBtn.textContent = 'Sending...';
    submitBtn.disabled = true;
    submitBtn.style.opacity = '0.7';
    formSuccess.style.display = 'none';
    formError.style.display = 'none';

    const data = new FormData(form);

    try {
      const response = await fetch(form.action, {
        method: 'POST',
        body: data,
        headers: { 'Accept': 'application/json' }
      });

      if (response.ok) {
        formSuccess.style.display = 'block';
        formNote.style.display = 'none';
        form.reset();
        submitBtn.textContent = 'Message Sent';
        submitBtn.style.background = '#4a9c6f';
        submitBtn.style.color = '#fff';
        submitBtn.style.opacity = '1';
        setTimeout(() => {
          submitBtn.textContent = 'Send Message';
          submitBtn.style.background = '';
          submitBtn.style.color = '';
          submitBtn.disabled = false;
          formNote.style.display = 'block';
        }, 5000);
      } else {
        throw new Error('Form submission failed');
      }
    } catch (err) {
      formError.style.display = 'block';
      submitBtn.textContent = 'Send Message';
      submitBtn.disabled = false;
      submitBtn.style.opacity = '1';
    }
  });
</script>
</body>
</html>
