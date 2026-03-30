<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Nanda Sai | AI/ML Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=DM+Mono:wght@300;400;500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --card: #16161f;
    --accent: #7c6af7;
    --accent2: #4fd1c5;
    --accent3: #f6ad55;
    --text: #e8e8f0;
    --muted: #7a7a9a;
    --border: rgba(124,106,247,0.18);
    --glow: rgba(124,106,247,0.25);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* ── NOISE OVERLAY ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 9999;
    opacity: 0.4;
  }

  /* ── GRID BACKGROUND ── */
  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(124,106,247,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(124,106,247,0.04) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
  }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 1.2rem 4rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: rgba(10,10,15,0.8);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border);
  }

  .nav-logo {
    font-family: 'DM Mono', monospace;
    font-size: 0.85rem;
    color: var(--accent);
    letter-spacing: 0.15em;
    text-transform: uppercase;
  }

  .nav-links {
    display: flex;
    gap: 2.5rem;
    list-style: none;
  }

  .nav-links a {
    font-family: 'DM Mono', monospace;
    font-size: 0.75rem;
    color: var(--muted);
    text-decoration: none;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    transition: color 0.2s;
  }

  .nav-links a:hover { color: var(--accent); }

  /* ── SECTIONS ── */
  section { position: relative; z-index: 1; }

  /* ── HERO ── */
  #hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    padding: 8rem 4rem 4rem;
    gap: 4rem;
  }

  .hero-left { position: relative; }

  .hero-tag {
    font-family: 'DM Mono', monospace;
    font-size: 0.75rem;
    color: var(--accent);
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-bottom: 1.5rem;
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }

  .hero-tag::before {
    content: '';
    width: 2rem;
    height: 1px;
    background: var(--accent);
  }

  h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(3rem, 5vw, 5.5rem);
    font-weight: 900;
    line-height: 1.05;
    margin-bottom: 1.5rem;
  }

  h1 .highlight {
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-bio {
    font-size: 1.05rem;
    color: var(--muted);
    max-width: 480px;
    margin-bottom: 2.5rem;
    line-height: 1.8;
  }

  .hero-cta {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
  }

  .btn {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    padding: 0.85rem 2rem;
    border-radius: 3px;
    font-family: 'DM Mono', monospace;
    font-size: 0.8rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    text-decoration: none;
    transition: all 0.25s;
    cursor: pointer;
    border: none;
  }

  .btn-primary {
    background: var(--accent);
    color: #fff;
    box-shadow: 0 0 30px var(--glow);
  }

  .btn-primary:hover {
    background: #9585fa;
    box-shadow: 0 0 50px var(--glow);
    transform: translateY(-2px);
  }

  .btn-ghost {
    background: transparent;
    color: var(--text);
    border: 1px solid var(--border);
  }

  .btn-ghost:hover {
    border-color: var(--accent);
    color: var(--accent);
    transform: translateY(-2px);
  }

  /* ── HERO RIGHT – PHOTO CARD ── */
  .hero-right {
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
  }

  .photo-frame {
    position: relative;
    width: 340px;
    height: 400px;
  }

  .photo-frame::before {
    content: '';
    position: absolute;
    inset: -2px;
    background: linear-gradient(135deg, var(--accent), var(--accent2), var(--accent3));
    border-radius: 4px;
    z-index: 0;
  }

  .photo-frame::after {
    content: '';
    position: absolute;
    inset: -20px;
    background: radial-gradient(ellipse, var(--glow) 0%, transparent 70%);
    z-index: -1;
  }

  .photo-frame img {
    position: relative;
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center top;
    border-radius: 3px;
    z-index: 1;
    display: block;
  }

  .photo-badge {
    position: absolute;
    bottom: -16px;
    right: -20px;
    background: var(--card);
    border: 1px solid var(--border);
    padding: 0.75rem 1.25rem;
    border-radius: 4px;
    z-index: 2;
    box-shadow: 0 8px 32px rgba(0,0,0,0.4);
  }

  .photo-badge .stat {
    font-family: 'Playfair Display', serif;
    font-size: 1.8rem;
    font-weight: 700;
    color: var(--accent);
    line-height: 1;
  }

  .photo-badge .label {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    color: var(--muted);
    letter-spacing: 0.12em;
    text-transform: uppercase;
  }

  .floating-tag {
    position: absolute;
    top: -12px;
    left: -24px;
    background: var(--card);
    border: 1px solid rgba(79,209,197,0.3);
    padding: 0.6rem 1rem;
    border-radius: 4px;
    z-index: 2;
    box-shadow: 0 8px 32px rgba(0,0,0,0.4);
    font-family: 'DM Mono', monospace;
    font-size: 0.7rem;
    color: var(--accent2);
    letter-spacing: 0.1em;
  }

  /* ── SECTION COMMON ── */
  .section-inner {
    max-width: 1100px;
    margin: 0 auto;
    padding: 6rem 2rem;
  }

  .section-label {
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    color: var(--accent);
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-bottom: 0.75rem;
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 3.5vw, 3rem);
    font-weight: 700;
    margin-bottom: 3rem;
  }

  /* ── SKILLS ── */
  #skills { background: var(--surface); }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
  }

  .skill-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 1.75rem;
    transition: border-color 0.25s, transform 0.25s;
    position: relative;
    overflow: hidden;
  }

  .skill-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transform: scaleX(0);
    transition: transform 0.3s;
    transform-origin: left;
  }

  .skill-card:hover::before { transform: scaleX(1); }
  .skill-card:hover {
    border-color: rgba(124,106,247,0.4);
    transform: translateY(-4px);
  }

  .skill-icon {
    font-size: 1.75rem;
    margin-bottom: 1rem;
  }

  .skill-card h3 {
    font-family: 'DM Mono', monospace;
    font-size: 0.8rem;
    color: var(--accent);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 1rem;
  }

  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .tag {
    background: rgba(124,106,247,0.1);
    border: 1px solid rgba(124,106,247,0.2);
    color: var(--text);
    font-family: 'DM Mono', monospace;
    font-size: 0.7rem;
    padding: 0.3rem 0.75rem;
    border-radius: 2px;
    letter-spacing: 0.05em;
  }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(440px, 1fr));
    gap: 2rem;
  }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 2.5rem;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }

  .project-card::after {
    content: '';
    position: absolute;
    bottom: 0; right: 0;
    width: 120px; height: 120px;
    background: radial-gradient(circle, var(--glow) 0%, transparent 70%);
    pointer-events: none;
  }

  .project-card:hover {
    border-color: rgba(124,106,247,0.5);
    transform: translateY(-6px);
    box-shadow: 0 20px 60px rgba(0,0,0,0.4);
  }

  .project-number {
    font-family: 'Playfair Display', serif;
    font-size: 3.5rem;
    font-weight: 900;
    color: rgba(124,106,247,0.12);
    line-height: 1;
    margin-bottom: 0.5rem;
  }

  .project-card h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.4rem;
    font-weight: 700;
    margin-bottom: 0.5rem;
  }

  .project-tech {
    font-family: 'DM Mono', monospace;
    font-size: 0.7rem;
    color: var(--accent2);
    letter-spacing: 0.1em;
    margin-bottom: 1.25rem;
  }

  .project-card p {
    color: var(--muted);
    font-size: 0.95rem;
    line-height: 1.75;
  }

  .project-highlights {
    margin-top: 1.25rem;
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }

  .project-highlights li {
    display: flex;
    gap: 0.75rem;
    font-size: 0.9rem;
    color: var(--muted);
  }

  .project-highlights li::before {
    content: '→';
    color: var(--accent);
    flex-shrink: 0;
  }

  .project-metric {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    margin-top: 1.5rem;
    background: rgba(79,209,197,0.1);
    border: 1px solid rgba(79,209,197,0.25);
    padding: 0.5rem 1rem;
    border-radius: 2px;
    font-family: 'DM Mono', monospace;
    font-size: 0.75rem;
    color: var(--accent2);
  }

  /* ── EDUCATION ── */
  #education { background: var(--surface); }

  .edu-timeline {
    position: relative;
    padding-left: 2rem;
  }

  .edu-timeline::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 1px;
    background: linear-gradient(to bottom, var(--accent), var(--accent2), transparent);
  }

  .edu-item {
    position: relative;
    padding: 0 0 3rem 2.5rem;
  }

  .edu-item::before {
    content: '';
    position: absolute;
    left: -5px; top: 6px;
    width: 10px; height: 10px;
    background: var(--accent);
    border-radius: 50%;
    box-shadow: 0 0 16px var(--glow);
  }

  .edu-year {
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    color: var(--accent);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 0.5rem;
  }

  .edu-item h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.25rem;
    font-weight: 700;
    margin-bottom: 0.25rem;
  }

  .edu-item .institution {
    color: var(--muted);
    font-size: 0.9rem;
    margin-bottom: 0.5rem;
  }

  .edu-score {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    background: rgba(124,106,247,0.1);
    border: 1px solid var(--border);
    padding: 0.4rem 0.9rem;
    border-radius: 2px;
    font-family: 'DM Mono', monospace;
    font-size: 0.75rem;
    color: var(--accent);
  }

  /* ── CERTIFICATIONS ── */
  .certs-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 1rem;
  }

  .cert-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 1.5rem;
    display: flex;
    align-items: flex-start;
    gap: 1rem;
    transition: all 0.25s;
  }

  .cert-card:hover {
    border-color: rgba(246,173,85,0.4);
    transform: translateY(-3px);
  }

  .cert-icon {
    width: 36px; height: 36px;
    background: rgba(246,173,85,0.1);
    border: 1px solid rgba(246,173,85,0.3);
    border-radius: 3px;
    display: grid;
    place-items: center;
    font-size: 1.1rem;
    flex-shrink: 0;
  }

  .cert-card h4 {
    font-family: 'DM Mono', monospace;
    font-size: 0.78rem;
    color: var(--text);
    letter-spacing: 0.05em;
    margin-bottom: 0.25rem;
  }

  .cert-card p {
    font-size: 0.8rem;
    color: var(--muted);
  }

  /* ── ACHIEVEMENTS ── */
  #achievements { background: var(--surface); }

  .achieve-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 1.25rem;
  }

  .achieve-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 1.75rem;
    transition: all 0.25s;
    position: relative;
    overflow: hidden;
  }

  .achieve-card:hover {
    border-color: rgba(124,106,247,0.4);
    transform: translateY(-4px);
  }

  .achieve-num {
    font-family: 'Playfair Display', serif;
    font-size: 2.5rem;
    font-weight: 900;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    line-height: 1;
    margin-bottom: 0.5rem;
  }

  .achieve-card p {
    color: var(--muted);
    font-size: 0.9rem;
  }

  /* ── CONTACT ── */
  #contact {
    text-align: center;
    padding: 6rem 2rem;
  }

  .contact-inner {
    max-width: 600px;
    margin: 0 auto;
  }

  .contact-inner p {
    color: var(--muted);
    margin-bottom: 2.5rem;
    font-size: 1rem;
  }

  .contact-links {
    display: flex;
    justify-content: center;
    gap: 1rem;
    flex-wrap: wrap;
  }

  /* ── FOOTER ── */
  footer {
    border-top: 1px solid var(--border);
    padding: 1.5rem 4rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    z-index: 1;
  }

  footer p {
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    color: var(--muted);
    letter-spacing: 0.1em;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes pulse-glow {
    0%, 100% { box-shadow: 0 0 20px var(--glow); }
    50%       { box-shadow: 0 0 50px var(--glow); }
  }

  .hero-left > * {
    animation: fadeUp 0.6s ease both;
  }

  .hero-left .hero-tag    { animation-delay: 0.1s; }
  .hero-left h1           { animation-delay: 0.2s; }
  .hero-left .hero-bio    { animation-delay: 0.3s; }
  .hero-left .hero-cta    { animation-delay: 0.4s; }

  .hero-right {
    animation: fadeUp 0.6s 0.3s ease both;
  }

  .btn-primary { animation: pulse-glow 3s infinite 1s; }

  /* ── RESPONSIVE ── */
  @media (max-width: 768px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    #hero {
      grid-template-columns: 1fr;
      padding: 7rem 1.5rem 3rem;
      text-align: center;
    }
    .hero-tag { justify-content: center; }
    .hero-bio { margin: 0 auto 2rem; }
    .hero-cta { justify-content: center; }
    .hero-right { order: -1; }
    .photo-frame { width: 220px; height: 270px; }
    .projects-grid { grid-template-columns: 1fr; }
    footer { flex-direction: column; gap: 0.5rem; padding: 1.5rem; text-align: center; }
    .section-inner { padding: 4rem 1.5rem; }
  }
</style>
</head>
<body>

<!-- ── NAV ── -->
<nav>
  <div class="nav-logo">GNS.dev</div>
  <ul class="nav-links">
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#education">Education</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- ── HERO ── -->
<section id="hero">
  <div class="hero-left">
    <div class="hero-tag">AI / ML Engineer</div>
    <h1>Gorlamandala<br><span class="highlight">Nanda Sai</span></h1>
    <p class="hero-bio">
      Computer Science undergraduate specialising in Artificial Intelligence & Machine Learning — building real-time intelligent systems with Python, deep learning, and computer vision.
    </p>
    <div class="hero-cta">
      <a href="mailto:gorlamandhla@gmail.com" class="btn btn-primary">✉ Get in Touch</a>
      <a href="https://github.com/Nandasai2004" target="_blank" class="btn btn-ghost">⌥ GitHub</a>
      <a href="https://www.linkedin.com/in/gorlamandala-nanda-sai-3ab18b296" target="_blank" class="btn btn-ghost">in LinkedIn</a>
    </div>
  </div>

  <div class="hero-right">
    <div class="photo-frame">
      <img src="data:image/jpeg;base64,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" alt="Gorlamandala Nanda Sai" />
      <div class="photo-badge">
        <div class="stat">8.5</div>
        <div class="label">CGPA / 10</div>
      </div>
      <div class="floating-tag">📍 Bengaluru, India</div>
    </div>
  </div>
</section>

<!-- ── SKILLS ── -->
<section id="skills">
  <div class="section-inner">
    <div class="section-label">Technical Expertise</div>
    <h2 class="section-title">Skills & Technologies</h2>
    <div class="skills-grid">
      <div class="skill-card">
        <div class="skill-icon">🤖</div>
        <h3>Machine Learning</h3>
        <div class="skill-tags">
          <span class="tag">Supervised Learning</span>
          <span class="tag">Unsupervised Learning</span>
          <span class="tag">Feature Engineering</span>
          <span class="tag">Model Evaluation</span>
          <span class="tag">Data Preprocessing</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-icon">🐍</div>
        <h3>Programming</h3>
        <div class="skill-tags">
          <span class="tag">Python</span>
          <span class="tag">Java</span>
          <span class="tag">DSA</span>
          <span class="tag">OOP</span>
          <span class="tag">Problem Solving</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-icon">📚</div>
        <h3>Libraries & Frameworks</h3>
        <div class="skill-tags">
          <span class="tag">OpenCV</span>
          <span class="tag">NumPy</span>
          <span class="tag">Pandas</span>
          <span class="tag">Scikit-learn</span>
          <span class="tag">Flask</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-icon">🌐</div>
        <h3>Web & Databases</h3>
        <div class="skill-tags">
          <span class="tag">HTML5</span>
          <span class="tag">CSS3</span>
          <span class="tag">JavaScript</span>
          <span class="tag">SQL</span>
          <span class="tag">REST APIs</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-icon">🛠</div>
        <h3>Tools & Platforms</h3>
        <div class="skill-tags">
          <span class="tag">Git</span>
          <span class="tag">GitHub</span>
          <span class="tag">VS Code</span>
          <span class="tag">Jupyter Notebook</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ── PROJECTS ── -->
<section id="projects">
  <div class="section-inner">
    <div class="section-label">Work</div>
    <h2 class="section-title">Featured Projects</h2>
    <div class="projects-grid">

      <div class="project-card">
        <div class="project-number">01</div>
        <h3>VGG-AttendNet</h3>
        <div class="project-tech">Python · OpenCV · Deep Learning · Flask</div>
        <ul class="project-highlights">
          <li>Real-time multi-face recognition system using deep learning</li>
          <li>Facial embeddings with cosine similarity for identity verification</li>
          <li>Flask web app for user management and attendance automation</li>
          <li>Reduced manual attendance effort by 90%</li>
        </ul>
        <div class="project-metric">✦ 91.67% Recognition Accuracy</div>
      </div>

      <div class="project-card">
        <div class="project-number">02</div>
        <h3>Weather Web App</h3>
        <div class="project-tech">JavaScript · HTML5 · CSS3 · REST API</div>
        <ul class="project-highlights">
          <li>Responsive web app using OpenWeather API for real-time data</li>
          <li>Dynamic city search with live weather updates</li>
          <li>Mobile-first, fully responsive user interface</li>
        </ul>
        <div class="project-metric">✦ Live Real-Time Data</div>
      </div>

    </div>
  </div>
</section>

<!-- ── EDUCATION ── -->
<section id="education">
  <div class="section-inner">
    <div class="section-label">Academic Background</div>
    <h2 class="section-title">Education</h2>
    <div class="edu-timeline">

      <div class="edu-item">
        <div class="edu-year">2023 – Present</div>
        <h3>B.Tech — Computer Science (AI & ML)</h3>
        <p class="institution">JAIN (Deemed-to-be University), Bengaluru</p>
        <span class="edu-score">⬡ CGPA 8.5 / 10</span>
      </div>

      <div class="edu-item">
        <div class="edu-year">2021 – 2023</div>
        <h3>Pre-University Course (PCM)</h3>
        <p class="institution">Jain Pre-University College, Bengaluru</p>
        <span class="edu-score">⬡ 80%</span>
      </div>

      <div class="edu-item">
        <div class="edu-year">2021</div>
        <h3>Class X – Secondary School</h3>
        <p class="institution">Keshava Reddy EM High School</p>
        <span class="edu-score">⬡ 97%</span>
      </div>

    </div>
  </div>
</section>

<!-- ── CERTIFICATIONS ── -->
<section id="certs">
  <div class="section-inner">
    <div class="section-label">Credentials</div>
    <h2 class="section-title">Certifications</h2>
    <div class="certs-grid">
      <div class="cert-card">
        <div class="cert-icon">🏆</div>
        <div>
          <h4>Python Programming</h4>
          <p>Coursera</p>
        </div>
      </div>
      <div class="cert-card">
        <div class="cert-icon">☕</div>
        <div>
          <h4>Java Programming</h4>
          <p>IIT Kanpur (E & ICT Academy)</p>
        </div>
      </div>
      <div class="cert-card">
        <div class="cert-icon">🧠</div>
        <div>
          <h4>Machine Learning</h4>
          <p>EdigloBe</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ── ACHIEVEMENTS ── -->
<section id="achievements">
  <div class="section-inner">
    <div class="section-label">Highlights</div>
    <h2 class="section-title">Achievements</h2>
    <div class="achieve-grid">
      <div class="achieve-card">
        <div class="achieve-num">97%</div>
        <p>Scored in Class X — demonstrating outstanding academic performance</p>
      </div>
      <div class="achieve-card">
        <div class="achieve-num">91.67%</div>
        <p>Face recognition accuracy achieved in VGG-AttendNet project</p>
      </div>
      <div class="achieve-card">
        <div class="achieve-num">90%</div>
        <p>Reduction in manual attendance effort via automated system</p>
      </div>
      <div class="achieve-card">
        <div class="achieve-num">DSA</div>
        <p>Active competitive programmer on LeetCode with regular problem-solving</p>
      </div>
    </div>
  </div>
</section>

<!-- ── CONTACT ── -->
<section id="contact">
  <div class="contact-inner">
    <div class="section-label" style="justify-content:center; margin-bottom:0.75rem;">Let's Connect</div>
    <h2 class="section-title">Get In Touch</h2>
    <p>I'm open to internships, collaborations, and exciting AI/ML opportunities. Drop me a message!</p>
    <div class="contact-links">
      <a href="mailto:gorlamandhla@gmail.com" class="btn btn-primary">✉ gorlamandhla@gmail.com</a>
      <a href="tel:+919398452032" class="btn btn-ghost">📞 +91 93984 52032</a>
    </div>
    <div class="contact-links" style="margin-top:1rem;">
      <a href="https://github.com/Nandasai2004" target="_blank" class="btn btn-ghost">⌥ GitHub</a>
      <a href="https://www.linkedin.com/in/gorlamandala-nanda-sai-3ab18b296" target="_blank" class="btn btn-ghost">in LinkedIn</a>
    </div>
  </div>
</section>

<!-- ── FOOTER ── -->
<footer>
  <p>© 2026 Gorlamandala Nanda Sai</p>
  <p>Bengaluru, India · AI/ML Engineer</p>
</footer>

</body>
</html># Nandasai2004.github.io
