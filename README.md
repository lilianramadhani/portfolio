
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lilian Ramadhani Putri — Portofolio</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0d0c0a;
    --surface: #161410;
    --card: #1c1a17;
    --gold: #c9a96e;
    --gold-light: #e8c98a;
    --gold-dim: #8a6f42;
    --cream: #f5f0e8;
    --text: #e8e0d0;
    --muted: #8a8070;
    --accent: #d4854a;
  }

  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
  }

  /* ── NOISE OVERLAY ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 1000;
    opacity: 0.5;
  }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.5rem 4rem;
    background: linear-gradient(to bottom, rgba(13,12,10,0.95), transparent);
  }
  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.1rem;
    color: var(--gold);
    letter-spacing: 0.05em;
  }
  .nav-links { display: flex; gap: 2.5rem; }
  .nav-links a {
    text-decoration: none;
    color: var(--muted);
    font-size: 0.8rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    transition: color 0.3s;
  }
  .nav-links a:hover { color: var(--gold); }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    padding: 8rem 4rem 4rem;
    position: relative;
    overflow: hidden;
  }

  .hero::after {
    content: '';
    position: absolute;
    top: -20%;
    right: -10%;
    width: 60vw;
    height: 60vw;
    background: radial-gradient(ellipse, rgba(201,169,110,0.07) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-text { position: relative; z-index: 2; }
  .hero-eyebrow {
    font-size: 0.75rem;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1.5rem;
    display: flex;
    align-items: center;
    gap: 1rem;
  }
  .hero-eyebrow::before {
    content: '';
    width: 3rem;
    height: 1px;
    background: var(--gold);
  }

  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(3rem, 5vw, 5.5rem);
    line-height: 1.05;
    font-weight: 900;
    margin-bottom: 1rem;
  }
  .hero h1 em {
    font-style: italic;
    color: var(--gold);
  }

  .hero-sub {
    font-size: 1.05rem;
    color: var(--muted);
    line-height: 1.7;
    max-width: 38ch;
    margin-bottom: 2.5rem;
  }

  .hero-cta {
    display: flex;
    gap: 1.2rem;
    flex-wrap: wrap;
  }

  .btn-primary {
    background: var(--gold);
    color: #0d0c0a;
    text-decoration: none;
    padding: 0.85rem 2rem;
    font-size: 0.8rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    font-weight: 500;
    transition: background 0.3s, transform 0.2s;
  }
  .btn-primary:hover { background: var(--gold-light); transform: translateY(-2px); }

  .btn-secondary {
    border: 1px solid var(--gold-dim);
    color: var(--gold);
    text-decoration: none;
    padding: 0.85rem 2rem;
    font-size: 0.8rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    transition: border-color 0.3s, transform 0.2s;
  }
  .btn-secondary:hover { border-color: var(--gold); transform: translateY(-2px); }

  /* Hero right side — stat grid */
  .hero-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;
    padding-left: 4rem;
    position: relative;
    z-index: 2;
  }
  .stat-card {
    background: var(--card);
    border: 1px solid rgba(201,169,110,0.12);
    padding: 1.8rem;
    position: relative;
    overflow: hidden;
    animation: fadeUp 0.8s ease both;
  }
  .stat-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 2px; height: 100%;
    background: linear-gradient(to bottom, var(--gold), transparent);
  }
  .stat-number {
    font-family: 'Playfair Display', serif;
    font-size: 2.5rem;
    font-weight: 900;
    color: var(--gold);
    line-height: 1;
    margin-bottom: 0.4rem;
  }
  .stat-label {
    font-size: 0.75rem;
    letter-spacing: 0.1em;
    color: var(--muted);
    text-transform: uppercase;
  }
  .stat-card:nth-child(2) { animation-delay: 0.1s; }
  .stat-card:nth-child(3) { animation-delay: 0.2s; }
  .stat-card:nth-child(4) { animation-delay: 0.3s; }

  /* ── SECTION COMMON ── */
  section { padding: 6rem 4rem; }

  .section-header {
    display: flex;
    align-items: baseline;
    gap: 1.5rem;
    margin-bottom: 4rem;
  }
  .section-number {
    font-family: 'Playfair Display', serif;
    font-size: 0.9rem;
    color: var(--gold-dim);
    font-style: italic;
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 3vw, 2.8rem);
    font-weight: 700;
    position: relative;
  }
  .section-title::after {
    content: '';
    position: absolute;
    bottom: -0.5rem; left: 0;
    width: 3rem; height: 2px;
    background: var(--gold);
  }

  /* ── ABOUT ── */
  .about-grid {
    display: grid;
    grid-template-columns: 3fr 2fr;
    gap: 5rem;
    align-items: start;
  }
  .about-text p {
    font-size: 1.05rem;
    line-height: 1.85;
    color: var(--text);
    margin-bottom: 1.5rem;
  }
  .about-text p span { color: var(--gold); font-weight: 500; }

  .about-sidebar {}
  .info-row {
    display: flex;
    justify-content: space-between;
    padding: 1rem 0;
    border-bottom: 1px solid rgba(255,255,255,0.05);
    font-size: 0.85rem;
  }
  .info-label { color: var(--muted); letter-spacing: 0.05em; }
  .info-val { color: var(--text); text-align: right; }

  /* ── SKILLS ── */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
  }
  .skill-group {
    background: var(--card);
    border: 1px solid rgba(201,169,110,0.1);
    padding: 2rem;
    position: relative;
  }
  .skill-group-title {
    font-size: 0.7rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1.2rem;
  }
  .skill-pills { display: flex; flex-wrap: wrap; gap: 0.5rem; }
  .pill {
    font-size: 0.78rem;
    padding: 0.35rem 0.75rem;
    background: rgba(201,169,110,0.07);
    border: 1px solid rgba(201,169,110,0.15);
    color: var(--cream);
    transition: background 0.2s;
  }
  .pill:hover { background: rgba(201,169,110,0.18); }

  .lang-grid { display: flex; flex-direction: column; gap: 0.8rem; }
  .lang-row { display: flex; justify-content: space-between; align-items: center; }
  .lang-name { font-size: 0.85rem; color: var(--text); }
  .lang-level {
    font-size: 0.7rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--gold-dim);
  }

  /* ── EXPERIENCE ── */
  .timeline { position: relative; }
  .timeline::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 1px;
    background: linear-gradient(to bottom, var(--gold-dim), transparent);
  }

  .timeline-item {
    padding-left: 3rem;
    padding-bottom: 3.5rem;
    position: relative;
  }
  .timeline-item::before {
    content: '';
    position: absolute;
    left: -4px; top: 0.4rem;
    width: 8px; height: 8px;
    background: var(--gold);
    transform: rotate(45deg);
  }

  .tl-meta {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    margin-bottom: 0.3rem;
  }
  .tl-company {
    font-family: 'Playfair Display', serif;
    font-size: 1.2rem;
    font-weight: 700;
    color: var(--cream);
  }
  .tl-date {
    font-size: 0.75rem;
    letter-spacing: 0.1em;
    color: var(--gold-dim);
    text-transform: uppercase;
  }
  .tl-role {
    font-size: 0.8rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1rem;
  }
  .tl-bullets { list-style: none; display: flex; flex-direction: column; gap: 0.5rem; }
  .tl-bullets li {
    font-size: 0.88rem;
    line-height: 1.6;
    color: var(--muted);
    padding-left: 1.2rem;
    position: relative;
  }
  .tl-bullets li::before {
    content: '—';
    position: absolute;
    left: 0;
    color: var(--gold-dim);
  }
  .tl-bullets li strong { color: var(--text); font-weight: 500; }

  /* ── HIGHLIGHTS ── */
  .highlights-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1.5rem;
  }
  .hl-card {
    background: var(--card);
    border: 1px solid rgba(201,169,110,0.1);
    padding: 2rem 1.5rem;
    text-align: center;
    position: relative;
    overflow: hidden;
    transition: transform 0.3s, border-color 0.3s;
  }
  .hl-card:hover {
    transform: translateY(-4px);
    border-color: rgba(201,169,110,0.35);
  }
  .hl-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(to right, transparent, var(--gold), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .hl-card:hover::after { opacity: 1; }

  .hl-icon { font-size: 1.8rem; margin-bottom: 1rem; }
  .hl-value {
    font-family: 'Playfair Display', serif;
    font-size: 2.2rem;
    font-weight: 900;
    color: var(--gold);
    margin-bottom: 0.4rem;
  }
  .hl-desc { font-size: 0.8rem; color: var(--muted); line-height: 1.5; }

  /* ── CERTIFICATIONS ── */
  .cert-list {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
  }
  .cert-item {
    display: flex;
    align-items: center;
    gap: 1.2rem;
    background: var(--card);
    border: 1px solid rgba(201,169,110,0.1);
    padding: 1.2rem 1.5rem;
    transition: border-color 0.3s;
  }
  .cert-item:hover { border-color: rgba(201,169,110,0.3); }
  .cert-dot {
    width: 8px; height: 8px;
    background: var(--gold);
    transform: rotate(45deg);
    flex-shrink: 0;
  }
  .cert-name { font-size: 0.85rem; color: var(--text); }
  .cert-year { font-size: 0.75rem; color: var(--gold-dim); margin-top: 0.2rem; }

  /* ── CONTACT ── */
  .contact-strip {
    background: var(--card);
    border-top: 1px solid rgba(201,169,110,0.1);
    border-bottom: 1px solid rgba(201,169,110,0.1);
    padding: 5rem 4rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;
  }
  .contact-left h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 3vw, 3rem);
    font-weight: 900;
    margin-bottom: 1rem;
  }
  .contact-left h2 em { color: var(--gold); font-style: italic; }
  .contact-left p { font-size: 0.95rem; color: var(--muted); line-height: 1.7; }

  .contact-right { display: flex; flex-direction: column; gap: 1rem; }
  .contact-link {
    display: flex;
    align-items: center;
    gap: 1.2rem;
    text-decoration: none;
    color: var(--text);
    padding: 1rem 1.5rem;
    border: 1px solid rgba(201,169,110,0.1);
    transition: border-color 0.3s, color 0.3s;
    font-size: 0.88rem;
  }
  .contact-link:hover { border-color: var(--gold); color: var(--gold); }
  .contact-icon { font-size: 1.1rem; }

  /* ── FOOTER ── */
  footer {
    padding: 2rem 4rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-top: 1px solid rgba(255,255,255,0.05);
  }
  footer span {
    font-size: 0.75rem;
    color: var(--muted);
    letter-spacing: 0.05em;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .hero-text { animation: fadeUp 0.9s ease both; }
  .hero h1 em { animation: fadeUp 0.9s ease 0.15s both; }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    nav { padding: 1.5rem 2rem; }
    .nav-links { display: none; }
    .hero { grid-template-columns: 1fr; padding: 7rem 2rem 3rem; }
    .hero-stats { display: grid; grid-template-columns: 1fr 1fr; padding-left: 0; margin-top: 3rem; }
    section { padding: 4rem 2rem; }
    .about-grid { grid-template-columns: 1fr; gap: 2.5rem; }
    .skills-grid { grid-template-columns: 1fr; }
    .highlights-grid { grid-template-columns: 1fr 1fr; }
    .cert-list { grid-template-columns: 1fr; }
    .contact-strip { grid-template-columns: 1fr; padding: 3rem 2rem; }
    footer { flex-direction: column; gap: 1rem; text-align: center; padding: 2rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">Lilian R. P.</div>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#experience">Experience</a>
    <a href="#contact">Contact</a>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-text">
    <div class="hero-eyebrow">Virtual Assistant & Data Specialist</div>
    <h1>Lilian<br><em>Ramadhani</em><br>Putri</h1>
    <p class="hero-sub">Punctual, organized, and proactive — with 5+ years bridging IT administration, data analytics, and digital operations.</p>
    <div class="hero-cta">
      <a href="mailto:lilramadha@gmail.com" class="btn-primary">Hire Me</a>
      <a href="https://www.notion.so/LILIAN-RAMADHANI-PUTRI-Virtual-Assistant-Data-Annotator31453b0fd6e280c9821bdaedebc58aae" target="_blank" class="btn-secondary">View Portfolio</a>
    </div>
  </div>
  <div class="hero-stats">
    <div class="stat-card">
      <div class="stat-number">5+</div>
      <div class="stat-label">Years Experience</div>
    </div>
    <div class="stat-card">
      <div class="stat-number">95%</div>
      <div class="stat-label">Accuracy Rate</div>
    </div>
    <div class="stat-card">
      <div class="stat-number">40%</div>
      <div class="stat-label">Efficiency Gained</div>
    </div>
    <div class="stat-card">
      <div class="stat-number">4.9★</div>
      <div class="stat-label">Customer Rating</div>
    </div>
  </div>
</section>

<!-- HIGHLIGHTS -->
<section style="padding: 2rem 4rem 5rem;">
  <div class="highlights-grid">
    <div class="hl-card">
      <div class="hl-icon">📊</div>
      <div class="hl-value">40%</div>
      <div class="hl-desc">Complaint retrieval time reduction via Customer Management System</div>
    </div>
    <div class="hl-card">
      <div class="hl-icon">⭐</div>
      <div class="hl-value">85%</div>
      <div class="hl-desc">Customer satisfaction rate achieved in digital store operations</div>
    </div>
    <div class="hl-card">
      <div class="hl-icon">📈</div>
      <div class="hl-value">50+</div>
      <div class="hl-desc">Images annotated per hour with 95% accuracy at Dataplus</div>
    </div>
    <div class="hl-card">
      <div class="hl-icon">🚀</div>
      <div class="hl-value">30%</div>
      <div class="hl-desc">Sales increase through targeted copywriting and social media campaigns</div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="section-header">
    <span class="section-number">01</span>
    <h2 class="section-title">About Me</h2>
  </div>
  <div class="about-grid">
    <div class="about-text">
      <p>I'm a versatile professional with a strong foundation in <span>IT administration, data annotation, and digital marketing</span>. My journey spans from managing enterprise IT operations at PT YKK API to building my own e-commerce business, teaching English internationally, and contributing to AI training datasets.</p>
      <p>What makes me distinctive is the ability to move fluidly between <span>technical and human-facing work</span> — I can analyze a database, write compelling copy, and resolve a customer complaint with equal confidence. I bring structured thinking to every task, and a genuine curiosity for continuous learning.</p>
      <p>Currently deepening expertise in <span>SQL, Excel, and Data Automation</span> while actively contributing to AI/ML projects through data annotation. I'm passionate about making the technical human and telling authentic stories through data and words.</p>
    </div>
    <div class="about-sidebar">
      <div class="info-row"><span class="info-label">Location</span><span class="info-val">Tangerang, Indonesia</span></div>
      <div class="info-row"><span class="info-label">Education</span><span class="info-val">S1 Information Systems<br>Telkom University</span></div>
      <div class="info-row"><span class="info-label">Email</span><span class="info-val">lilramadha@gmail.com</span></div>
      <div class="info-row"><span class="info-label">Phone</span><span class="info-val">+62 813 8367 5130</span></div>
      <div class="info-row"><span class="info-label">LinkedIn</span><span class="info-val">linkedin.com/in/lilianramadhani</span></div>
      <div class="info-row"><span class="info-label">Availability</span><span class="info-val" style="color: var(--gold);">Open to Work</span></div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills" style="background: var(--surface);">
  <div class="section-header">
    <span class="section-number">02</span>
    <h2 class="section-title">Skills & Languages</h2>
  </div>
  <div class="skills-grid">
    <div class="skill-group">
      <div class="skill-group-title">Areas of Expertise</div>
      <div class="skill-pills">
        <span class="pill">Virtual Assistant</span>
        <span class="pill">Data Annotation</span>
        <span class="pill">Copywriting</span>
        <span class="pill">Blog Writing</span>
        <span class="pill">Social Media Strategy</span>
        <span class="pill">Marketing Campaigns</span>
        <span class="pill">Administrative Support</span>
        <span class="pill">Customer Service</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">Technical Skills</div>
      <div class="skill-pills">
        <span class="pill">MS Excel</span>
        <span class="pill">MS Word / PowerPoint</span>
        <span class="pill">MySQL</span>
        <span class="pill">PHP CI</span>
        <span class="pill">Python</span>
        <span class="pill">HTML / Bootstrap</span>
        <span class="pill">Figma</span>
        <span class="pill">Canva</span>
        <span class="pill">Make.com</span>
        <span class="pill">Data Automation</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">Languages</div>
      <div class="lang-grid">
        <div class="lang-row"><span class="lang-name">🇮🇩 Indonesian</span><span class="lang-level">Native</span></div>
        <div class="lang-row"><span class="lang-name">🇬🇧 English</span><span class="lang-level">TOEFL 500</span></div>
        <div class="lang-row"><span class="lang-name">🇩🇪 German</span><span class="lang-level">B1</span></div>
        <div class="lang-row"><span class="lang-name">🇰🇷 Korean</span><span class="lang-level">Beginner</span></div>
        <div class="lang-row"><span class="lang-name">🇨🇳 Mandarin</span><span class="lang-level">Beginner</span></div>
      </div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="section-header">
    <span class="section-number">03</span>
    <h2 class="section-title">Experience</h2>
  </div>
  <div class="timeline">

    <div class="timeline-item">
      <div class="tl-meta">
        <span class="tl-company">Dataplus / Appen / Alignerr</span>
        <span class="tl-date">2025 – 2026</span>
      </div>
      <div class="tl-role">Data Annotator</div>
      <ul class="tl-bullets">
        <li>Annotated 50+ images per hour with <strong>95% accuracy</strong>, consistently meeting daily targets.</li>
        <li>Completed 750-sentence audio recordings in both English and German within 2 days each.</li>
        <li>Transcribed and labelled text, image, and conversational data across multiple AI training platforms.</li>
        <li>Collaborated with QA teams to maintain quality standards and accelerate review cycles.</li>
      </ul>
    </div>

    <div class="timeline-item">
      <div class="tl-meta">
        <span class="tl-company">Business Owner (Shopee, Tokopedia, TikTok Shop)</span>
        <span class="tl-date">Apr 2021 – Present</span>
      </div>
      <div class="tl-role">Digital Marketing Specialist</div>
      <ul class="tl-bullets">
        <li>Grew customer base by <strong>50%</strong> through targeted marketing and data-driven product strategies.</li>
        <li>Maintained a <strong>4.9/5 star</strong> customer satisfaction rating across all platforms.</li>
        <li>Leveraged AI tools (ChatGPT) for sales recommendations and campaign optimization.</li>
        <li>Handled a <strong>200% surge</strong> in orders during peak seasons without compromising quality.</li>
        <li>Increased sales by <strong>30%</strong> through strategic product copywriting and social media content.</li>
      </ul>
    </div>

    <div class="timeline-item">
      <div class="tl-meta">
        <span class="tl-company">Speakz Up Telegram Channel</span>
        <span class="tl-date">Jun 2021 – May 2023</span>
      </div>
      <div class="tl-role">Online English Teacher & Assistant</div>
      <ul class="tl-bullets">
        <li>Bridged communication between Indonesian students and native English teachers.</li>
        <li>Improved student scores by up to <strong>30%</strong> through tailored one-on-one sessions.</li>
        <li>Led e-learning platform implementation and conducted student outreach campaigns.</li>
      </ul>
    </div>

    <div class="timeline-item">
      <div class="tl-meta">
        <span class="tl-company">PT Sumber Karya</span>
        <span class="tl-date">Sep 2021 – Mar 2022</span>
      </div>
      <div class="tl-role">Project Leader & Back-End Developer — PO System</div>
      <ul class="tl-bullets">
        <li>Designed and deployed a full Purchase Order system using <strong>PHP, MySQL, and Bootstrap</strong>.</li>
        <li>Reduced defect rates by <strong>20%</strong> through systematic bug reporting within one month of launch.</li>
        <li>Implemented user authentication and role-based access for security compliance.</li>
      </ul>
    </div>

    <div class="timeline-item" style="padding-bottom: 0;">
      <div class="tl-meta">
        <span class="tl-company">PT YKK API</span>
        <span class="tl-date">Nov 2014 – Dec 2019</span>
      </div>
      <div class="tl-role">IT Administrative Assistant</div>
      <ul class="tl-bullets">
        <li>Produced data visualizations for Top Management with a <strong>95% satisfaction rate</strong>.</li>
        <li>Introduced a Customer Complaint Management System, cutting retrieval time by <strong>40%</strong>.</li>
        <li>Prepared documentation for <strong>ISO 9001 & 27001</strong> audits.</li>
        <li>Reduced paper usage by <strong>40%</strong> by championing digital communication as IT helpdesk.</li>
        <li>Maintained a <strong>90% client satisfaction rate</strong> in appointment and correspondence management.</li>
      </ul>
    </div>

  </div>
</section>

<!-- CERTIFICATIONS -->
<section style="background: var(--surface);">
  <div class="section-header">
    <span class="section-number">04</span>
    <h2 class="section-title">Certifications</h2>
  </div>
  <div class="cert-list">
    <div class="cert-item">
      <div class="cert-dot"></div>
      <div>
        <div class="cert-name">Oracle AI Vector Search Certified Professional</div>
        <div class="cert-year">2025</div>
      </div>
    </div>
    <div class="cert-item">
      <div class="cert-dot"></div>
      <div>
        <div class="cert-name">Data Automation — Make.com</div>
        <div class="cert-year">2025</div>
      </div>
    </div>
    <div class="cert-item">
      <div class="cert-dot"></div>
      <div>
        <div class="cert-name">Jayjay UX Writer Trainee</div>
        <div class="cert-year">2022</div>
      </div>
    </div>
    <div class="cert-item">
      <div class="cert-dot"></div>
      <div>
        <div class="cert-name">RevoU System Analyst Trainee</div>
        <div class="cert-year">2022</div>
      </div>
    </div>
    <div class="cert-item">
      <div class="cert-dot"></div>
      <div>
        <div class="cert-name">ISO 27001 Seminar Participant</div>
        <div class="cert-year">2019</div>
      </div>
    </div>
    <div class="cert-item">
      <div class="cert-dot"></div>
      <div>
        <div class="cert-name">ISO 9001 Seminar Participant</div>
        <div class="cert-year">2018</div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<div class="contact-strip" id="contact">
  <div class="contact-left">
    <h2>Let's Work<br><em>Together</em></h2>
    <p>Looking for a reliable, multi-skilled virtual assistant or data specialist? I'm available for freelance and remote opportunities. Let's connect!</p>
  </div>
  <div class="contact-right">
    <a href="mailto:lilramadha@gmail.com" class="contact-link">
      <span class="contact-icon">✉</span>
      lilramadha@gmail.com
    </a>
    <a href="tel:+6281383675130" class="contact-link">
      <span class="contact-icon">📞</span>
      +62 813 8367 5130
    </a>
    <a href="https://linkedin.com/in/lilianramadhani" target="_blank" class="contact-link">
      <span class="contact-icon">💼</span>
      linkedin.com/in/lilianramadhani
    </a>
    <a href="https://www.notion.so/LILIAN-RAMADHANI-PUTRI-Virtual-Assistant-Data-Annotator31453b0fd6e280c9821bdaedebc58aae" target="_blank" class="contact-link">
      <span class="contact-icon">🌐</span>
      notion.so — Full Portfolio
    </a>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <span>© 2026 Lilian Ramadhani Putri</span>
  <span>Tangerang, Indonesia · Open to Remote Work</span>
</footer>

</body>
</html>
