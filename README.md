<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Gajula Indra Karan — GenAI & Full Stack Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;1,9..40,300&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0a0a0f;
    --bg2: #111118;
    --bg3: #16161f;
    --border: rgba(255,255,255,0.07);
    --border2: rgba(255,255,255,0.12);
    --text: #e8e8f0;
    --muted: #8888a0;
    --accent: #7c6fee;
    --accent2: #4dc8a0;
    --accent3: #f07060;
    --card: #13131c;
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }
  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--bg);
    color: var(--text);
    font-size: 16px;
    line-height: 1.7;
    overflow-x: hidden;
  }
  /* Noise overlay */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 0;
    opacity: 0.4;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1rem 2.5rem;
    background: rgba(10,10,15,0.85);
    backdrop-filter: blur(16px);
    border-bottom: 0.5px solid var(--border);
  }
  .nav-logo { font-size: 15px; font-weight: 500; letter-spacing: -0.01em; color: var(--text); }
  .nav-logo span { color: var(--accent); }
  .nav-links { display: flex; gap: 2rem; }
  .nav-links a {
    font-size: 13px; color: var(--muted); text-decoration: none;
    transition: color 0.2s; letter-spacing: 0.02em;
  }
  .nav-links a:hover { color: var(--text); }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex; flex-direction: column; justify-content: center;
    padding: 8rem 2.5rem 4rem;
    max-width: 900px; margin: 0 auto;
    position: relative;
  }
  .hero-tag {
    display: inline-flex; align-items: center; gap: 8px;
    background: rgba(124,111,238,0.1); border: 0.5px solid rgba(124,111,238,0.3);
    border-radius: 100px; padding: 4px 14px;
    font-size: 12px; color: var(--accent); letter-spacing: 0.06em;
    margin-bottom: 2rem; text-transform: uppercase;
  }
  .hero-tag::before { content: ''; width: 6px; height: 6px; border-radius: 50%; background: var(--accent); animation: pulse 2s infinite; }
  @keyframes pulse { 0%,100% { opacity: 1; } 50% { opacity: 0.3; } }
  h1 {
    font-size: clamp(3rem, 7vw, 5.5rem);
    font-weight: 300;
    letter-spacing: -0.03em;
    line-height: 1.05;
    margin-bottom: 1.5rem;
    color: var(--text);
  }
  h1 em { font-style: italic; color: var(--accent); font-weight: 300; }
  h1 strong { font-weight: 500; }
  .hero-sub {
    font-size: 18px; color: var(--muted); max-width: 560px;
    line-height: 1.6; margin-bottom: 2.5rem;
  }
  .hero-cta { display: flex; gap: 1rem; flex-wrap: wrap; }
  .btn {
    display: inline-flex; align-items: center; gap: 8px;
    padding: 10px 22px; border-radius: 8px;
    font-size: 14px; font-weight: 500; text-decoration: none;
    transition: all 0.2s; cursor: pointer; border: none;
  }
  .btn-primary {
    background: var(--accent); color: #fff;
  }
  .btn-primary:hover { background: #6a5fd6; transform: translateY(-1px); }
  .btn-ghost {
    background: transparent; color: var(--text);
    border: 0.5px solid var(--border2);
  }
  .btn-ghost:hover { background: var(--bg3); transform: translateY(-1px); }
  .hero-stats {
    display: flex; gap: 3rem; margin-top: 4rem;
    padding-top: 2.5rem; border-top: 0.5px solid var(--border);
    flex-wrap: wrap;
  }
  .stat-item {}
  .stat-num {
    font-family: 'DM Mono', monospace;
    font-size: 2rem; font-weight: 500; color: var(--text);
    letter-spacing: -0.04em;
  }
  .stat-num span { color: var(--accent); font-size: 1.2rem; }
  .stat-label { font-size: 12px; color: var(--muted); letter-spacing: 0.04em; margin-top: 2px; }

  /* SECTIONS */
  section { padding: 5rem 2.5rem; max-width: 900px; margin: 0 auto; }
  .section-header {
    display: flex; align-items: baseline; gap: 1rem;
    margin-bottom: 3rem;
  }
  .section-num {
    font-family: 'DM Mono', monospace;
    font-size: 12px; color: var(--accent); letter-spacing: 0.08em;
  }
  h2 {
    font-size: 2rem; font-weight: 300; letter-spacing: -0.02em; color: var(--text);
  }
  h2 strong { font-weight: 500; }

  /* SKILLS */
  .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1rem; }
  .skill-card {
    background: var(--card); border: 0.5px solid var(--border);
    border-radius: 12px; padding: 1.25rem;
    transition: border-color 0.2s, transform 0.2s;
  }
  .skill-card:hover { border-color: var(--border2); transform: translateY(-2px); }
  .skill-icon { font-size: 18px; margin-bottom: 0.75rem; opacity: 0.7; }
  .skill-title { font-size: 13px; font-weight: 500; color: var(--text); margin-bottom: 0.75rem; }
  .tags { display: flex; flex-wrap: wrap; gap: 6px; }
  .tag {
    font-size: 11px; padding: 3px 9px; border-radius: 100px;
    background: rgba(255,255,255,0.05); color: var(--muted);
    border: 0.5px solid var(--border); letter-spacing: 0.02em;
  }
  .tag.new { background: rgba(77,200,160,0.1); color: var(--accent2); border-color: rgba(77,200,160,0.25); }

  /* EXPERIENCE */
  .exp-card {
    background: var(--card); border: 0.5px solid var(--border);
    border-radius: 12px; padding: 1.75rem;
    border-left: 2px solid var(--accent);
  }
  .exp-header { display: flex; justify-content: space-between; align-items: flex-start; flex-wrap: wrap; gap: 0.5rem; margin-bottom: 1rem; }
  .exp-title { font-size: 16px; font-weight: 500; color: var(--text); }
  .exp-company { font-size: 13px; color: var(--accent); margin-top: 2px; }
  .exp-date { font-family: 'DM Mono', monospace; font-size: 12px; color: var(--muted); }
  .exp-card ul { list-style: none; padding: 0; display: flex; flex-direction: column; gap: 0.5rem; }
  .exp-card li { font-size: 14px; color: var(--muted); padding-left: 1rem; position: relative; line-height: 1.6; }
  .exp-card li::before { content: '→'; position: absolute; left: 0; color: var(--accent); font-size: 12px; top: 3px; }
  .exp-card li strong { color: var(--text); font-weight: 500; }
  .tech-stack { display: flex; flex-wrap: wrap; gap: 6px; margin-top: 1rem; padding-top: 1rem; border-top: 0.5px solid var(--border); }

  /* PROJECTS */
  .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(400px, 1fr)); gap: 1rem; }
  .proj-card {
    background: var(--card); border: 0.5px solid var(--border);
    border-radius: 12px; padding: 1.5rem;
    transition: border-color 0.2s, transform 0.2s;
    display: flex; flex-direction: column; gap: 0.75rem;
  }
  .proj-card:hover { border-color: rgba(124,111,238,0.3); transform: translateY(-2px); }
  .proj-header { display: flex; justify-content: space-between; align-items: flex-start; }
  .proj-icon { font-size: 22px; }
  .proj-badge {
    font-size: 10px; padding: 3px 8px; border-radius: 100px;
    background: rgba(77,200,160,0.1); color: var(--accent2);
    border: 0.5px solid rgba(77,200,160,0.25); letter-spacing: 0.05em; text-transform: uppercase;
  }
  .proj-title { font-size: 15px; font-weight: 500; color: var(--text); }
  .proj-desc { font-size: 13px; color: var(--muted); line-height: 1.6; }
  .proj-metrics { display: flex; gap: 1rem; flex-wrap: wrap; }
  .metric {
    display: flex; flex-direction: column;
    background: rgba(255,255,255,0.03); border: 0.5px solid var(--border);
    border-radius: 8px; padding: 6px 12px; min-width: 60px;
  }
  .metric-val { font-family: 'DM Mono', monospace; font-size: 14px; font-weight: 500; color: var(--text); }
  .metric-label { font-size: 10px; color: var(--muted); letter-spacing: 0.04em; }

  /* POSITIONS */
  .pos-grid { display: flex; flex-direction: column; gap: 1rem; }
  .pos-card {
    background: var(--card); border: 0.5px solid var(--border);
    border-radius: 12px; padding: 1.5rem;
    display: grid; grid-template-columns: 1fr auto;
    gap: 0.5rem 1rem; align-items: start;
  }
  .pos-title { font-size: 15px; font-weight: 500; color: var(--text); }
  .pos-period { font-family: 'DM Mono', monospace; font-size: 12px; color: var(--muted); text-align: right; }
  .pos-highlight {
    font-family: 'DM Mono', monospace; font-size: 11px;
    background: rgba(124,111,238,0.1); border: 0.5px solid rgba(124,111,238,0.25);
    color: var(--accent); border-radius: 6px; padding: 4px 10px;
    display: inline-block; margin-top: 0.5rem;
  }
  .pos-card ul { list-style: none; padding: 0; grid-column: 1 / -1; display: flex; flex-direction: column; gap: 4px; margin-top: 0.25rem; }
  .pos-card li { font-size: 13px; color: var(--muted); padding-left: 1rem; position: relative; }
  .pos-card li::before { content: '–'; position: absolute; left: 0; color: var(--border2); }

  /* EDUCATION */
  .edu-grid { display: flex; flex-direction: column; gap: 0.75rem; }
  .edu-card {
    background: var(--card); border: 0.5px solid var(--border);
    border-radius: 12px; padding: 1.25rem 1.5rem;
    display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 0.5rem;
  }
  .edu-left {}
  .edu-inst { font-size: 14px; font-weight: 500; color: var(--text); }
  .edu-prog { font-size: 13px; color: var(--muted); margin-top: 2px; }
  .edu-right { text-align: right; }
  .edu-grade { font-family: 'DM Mono', monospace; font-size: 16px; font-weight: 500; color: var(--accent); }
  .edu-year { font-size: 12px; color: var(--muted); margin-top: 2px; }

  /* ACHIEVEMENTS */
  .ach-list { display: flex; flex-direction: column; gap: 0.75rem; }
  .ach-item {
    display: flex; align-items: flex-start; gap: 1rem;
    background: var(--card); border: 0.5px solid var(--border);
    border-radius: 10px; padding: 1rem 1.25rem;
  }
  .ach-num {
    font-family: 'DM Mono', monospace; font-size: 11px;
    color: var(--accent); min-width: 28px; padding-top: 2px;
  }
  .ach-text { font-size: 14px; color: var(--muted); line-height: 1.5; }
  .ach-text strong { color: var(--text); font-weight: 500; }

  /* CONTACT */
  .contact-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1rem; }
  .contact-card {
    display: flex; align-items: center; gap: 12px;
    background: var(--card); border: 0.5px solid var(--border);
    border-radius: 12px; padding: 1.25rem;
    text-decoration: none; color: var(--text);
    transition: border-color 0.2s, transform 0.2s;
  }
  .contact-card:hover { border-color: var(--accent); transform: translateY(-2px); }
  .contact-icon { font-size: 20px; opacity: 0.6; }
  .contact-label { font-size: 11px; color: var(--muted); letter-spacing: 0.04em; margin-bottom: 2px; text-transform: uppercase; }
  .contact-val { font-size: 13px; font-weight: 500; color: var(--text); }

  /* FOOTER */
  footer {
    max-width: 900px; margin: 0 auto;
    padding: 2rem 2.5rem 3rem;
    border-top: 0.5px solid var(--border);
    display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 1rem;
  }
  footer p { font-size: 12px; color: var(--muted); }

  @media (max-width: 680px) {
    nav { padding: 1rem 1.25rem; }
    .nav-links { display: none; }
    section { padding: 3.5rem 1.25rem; }
    .hero { padding: 7rem 1.25rem 3rem; }
    .projects-grid { grid-template-columns: 1fr; }
    h1 { font-size: 2.8rem; }
    .hero-stats { gap: 2rem; }
    footer { padding: 2rem 1.25rem; }
  }
</style>
</head>
<body>

<nav>
  <div class="nav-logo"><span>G</span>ajula Indra Karan</div>
  <div class="nav-links">
    <a href="#skills">Skills</a>
    <a href="#experience">Experience</a>
    <a href="#projects">Projects</a>
    <a href="#positions">Leadership</a>
    <a href="#education">Education</a>
    <a href="#contact">Contact</a>
  </div>
</nav>

<!-- HERO -->
<div class="hero" id="home">
  <div class="hero-tag">Open to internships &amp; full-time roles</div>
  <h1>Gajula<br/><em>Indra</em> <strong>Karan</strong></h1>
  <p class="hero-sub">
    GenAI &amp; Full Stack Engineer at IIT Madras. Building intelligent systems — from fine-tuned LLMs and agentic pipelines to production full-stack applications.
  </p>
  <div class="hero-cta">
    <a href="#projects" class="btn btn-primary">View Projects</a>
    <a href="https://github.com/Indrakaran1411" target="_blank" class="btn btn-ghost">GitHub →</a>
    <a href="https://linkedin.com/in/indrakarangajula" target="_blank" class="btn btn-ghost">LinkedIn →</a>
  </div>
  <div class="hero-stats">
    <div class="stat-item">
      <div class="stat-num">0.3<span>%</span></div>
      <div class="stat-label">JEE Mains Percentile</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">98<span>%</span></div>
      <div class="stat-label">Peak Model Accuracy</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">₹1<span>Cr+</span></div>
      <div class="stat-label">Budget Managed</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">6<span>+</span></div>
      <div class="stat-label">AI / Full Stack Projects</div>
    </div>
  </div>
</div>

<!-- SKILLS -->
<section id="skills">
  <div class="section-header">
    <span class="section-num">01</span>
    <h2><strong>Skills</strong> &amp; Technologies</h2>
  </div>
  <div class="skills-grid">
    <div class="skill-card">
      <div class="skill-icon">🌐</div>
      <div class="skill-title">Full Stack Development</div>
      <div class="tags">
        <span class="tag">React.js</span><span class="tag">Node.js</span><span class="tag">Express.js</span>
        <span class="tag">Next.js</span><span class="tag">HTML/CSS</span><span class="tag">JavaScript</span>
        <span class="tag">REST APIs</span><span class="tag">JWT Auth</span><span class="tag">WebSockets</span>
      </div>
    </div>
    <div class="skill-card">
      <div class="skill-icon">🤖</div>
      <div class="skill-title">ML / Deep Learning</div>
      <div class="tags">
        <span class="tag">PyTorch</span><span class="tag">Scikit-learn</span><span class="tag">HuggingFace</span>
        <span class="tag">XGBoost</span><span class="tag">NumPy</span><span class="tag">Pandas</span>
        <span class="tag">MLflow</span><span class="tag">Airflow</span><span class="tag">NLTK</span><span class="tag">PySpark</span>
      </div>
    </div>
    <div class="skill-card">
      <div class="skill-icon">🧠</div>
      <div class="skill-title">Agentic AI</div>
      <div class="tags">
        <span class="tag new">LangChain</span><span class="tag new">LangGraph</span>
        <span class="tag new">ReAct Agents</span><span class="tag new">Multi-Agent</span>
        <span class="tag new">Tool Use</span><span class="tag new">Prompt Eng.</span>
      </div>
    </div>
    <div class="skill-card">
      <div class="skill-icon">✨</div>
      <div class="skill-title">Generative AI</div>
      <div class="tags">
        <span class="tag new">Google Gemini</span><span class="tag new">Mistral</span>
        <span class="tag new">QLoRA</span><span class="tag new">RAG Pipelines</span>
        <span class="tag new">Qdrant</span><span class="tag new">FAISS</span>
        <span class="tag new">Gradio</span><span class="tag new">Streamlit</span>
      </div>
    </div>
    <div class="skill-card">
      <div class="skill-icon">⚙️</div>
      <div class="skill-title">Infrastructure &amp; Tools</div>
      <div class="tags">
        <span class="tag">Docker</span><span class="tag">FastAPI</span><span class="tag">AWS EC2</span>
        <span class="tag">GCP</span><span class="tag">PostgreSQL</span><span class="tag">MongoDB</span>
        <span class="tag">MySQL</span><span class="tag">Git</span><span class="tag">Power BI</span>
      </div>
    </div>
    <div class="skill-card">
      <div class="skill-icon">💬</div>
      <div class="skill-title">Languages</div>
      <div class="tags">
        <span class="tag">Python</span><span class="tag">SQL</span><span class="tag">JavaScript</span>
        <span class="tag">TypeScript</span><span class="tag">C</span><span class="tag">HTML</span><span class="tag">CSS</span>
      </div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="section-header">
    <span class="section-num">02</span>
    <h2><strong>Professional</strong> Experience</h2>
  </div>
  <div class="exp-card">
    <div class="exp-header">
      <div>
        <div class="exp-title">Machine Learning Intern</div>
        <div class="exp-company">Prodigy Infotech</div>
      </div>
      <div class="exp-date">Aug – Sep 2025</div>
    </div>
    <ul>
      <li>Built an end-to-end ML pipeline to predict <strong>customer churn</strong> using historical usage and demographic data.</li>
      <li>Performed data cleaning, feature engineering, and handled class imbalance using <strong>SMOTE</strong>. Implemented Scikit-learn Pipelines to prevent data leakage; deployed on FastAPI.</li>
      <li>Trained and optimized Logistic Regression, Random Forest, and XGBoost models using <strong>GridSearchCV</strong> — achieved <strong>92% accuracy</strong> and <strong>0.89 ROC-AUC</strong>.</li>
    </ul>
    <div class="tech-stack">
      <span class="tag">Python</span><span class="tag">Pandas</span><span class="tag">XGBoost</span>
      <span class="tag">SMOTE</span><span class="tag">FastAPI</span><span class="tag">GridSearchCV</span><span class="tag">Git</span>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="section-header">
    <span class="section-num">03</span>
    <h2><strong>Featured</strong> Projects</h2>
  </div>
  <div class="projects-grid">

    <div class="proj-card">
      <div class="proj-header">
        <span class="proj-icon">🔬</span>
        <span class="proj-badge">LLM Fine-tuning</span>
      </div>
      <div class="proj-title">Fine-Tuned Mistral LLM</div>
      <div class="proj-desc">Fine-tuned Mistral-7B-v0.1 on MedAlpaca medical dataset using QLoRA + PEFT. Reduced memory footprint by 65% via 4-bit NF4 quantisation. Built interactive Gradio interface for real-time medical Q&A with CUDA &amp; MPS support.</div>
      <div class="proj-metrics">
        <div class="metric"><div class="metric-val">0.89</div><div class="metric-label">Train Loss</div></div>
        <div class="metric"><div class="metric-val">65%</div><div class="metric-label">Memory ↓</div></div>
        <div class="metric"><div class="metric-val">5 GB</div><div class="metric-label">Footprint</div></div>
      </div>
      <div class="tags" style="margin-top:auto;">
        <span class="tag">PyTorch</span><span class="tag">HuggingFace</span><span class="tag">QLoRA</span><span class="tag">Gradio</span><span class="tag">WandB</span>
      </div>
    </div>

    <div class="proj-card">
      <div class="proj-header">
        <span class="proj-icon">🤝</span>
        <span class="proj-badge">Agentic AI</span>
      </div>
      <div class="proj-title">Agentic Customer Service Platform</div>
      <div class="proj-desc">Multi-agent LangGraph pipeline with specialised agents for intent classification, query routing, auto-response generation, and escalation. React.js chat frontend with real-time WebSocket communication and JWT auth.</div>
      <div class="proj-metrics">
        <div class="metric"><div class="metric-val">Multi</div><div class="metric-label">Agent</div></div>
        <div class="metric"><div class="metric-val">RT</div><div class="metric-label">WebSocket</div></div>
        <div class="metric"><div class="metric-val">JWT</div><div class="metric-label">Auth</div></div>
      </div>
      <div class="tags" style="margin-top:auto;">
        <span class="tag">LangGraph</span><span class="tag">React.js</span><span class="tag">FastAPI</span><span class="tag">Docker</span><span class="tag">PostgreSQL</span>
      </div>
    </div>

    <div class="proj-card">
      <div class="proj-header">
        <span class="proj-icon">📄</span>
        <span class="proj-badge">RAG</span>
      </div>
      <div class="proj-title">Insurance Policy RAG Assistant</div>
      <div class="proj-desc">Production-ready RAG system using LangChain + Google Gemini enabling accurate natural-language Q&amp;A over insurance policy documents. Semantic search with Qdrant Cloud achieving sub-second retrieval latency with dynamic collection creation.</div>
      <div class="proj-metrics">
        <div class="metric"><div class="metric-val">&lt;1s</div><div class="metric-label">Retrieval</div></div>
        <div class="metric"><div class="metric-val">RAG</div><div class="metric-label">Pipeline</div></div>
        <div class="metric"><div class="metric-val">REST</div><div class="metric-label">API</div></div>
      </div>
      <div class="tags" style="margin-top:auto;">
        <span class="tag">LangChain</span><span class="tag">Gemini</span><span class="tag">Qdrant</span><span class="tag">FastAPI</span>
      </div>
    </div>

    <div class="proj-card">
      <div class="proj-header">
        <span class="proj-icon">🩺</span>
        <span class="proj-badge">MLOps</span>
      </div>
      <div class="proj-title">Diabetes Risk Assessment System</div>
      <div class="proj-desc">Autoencoder-based nonlinear feature extraction combined with Random Forest classifier. GridSearchCV + 5-fold cross-validation. Containerised with Docker and deployed on AWS EC2 with Elastic IP.</div>
      <div class="proj-metrics">
        <div class="metric"><div class="metric-val">98%</div><div class="metric-label">Accuracy</div></div>
        <div class="metric"><div class="metric-val">5-fold</div><div class="metric-label">Cross-val</div></div>
        <div class="metric"><div class="metric-val">AWS</div><div class="metric-label">Deployed</div></div>
      </div>
      <div class="tags" style="margin-top:auto;">
        <span class="tag">PyTorch</span><span class="tag">Scikit-learn</span><span class="tag">FastAPI</span><span class="tag">Docker</span><span class="tag">AWS EC2</span>
      </div>
    </div>

  </div>
</section>

<!-- POSITIONS -->
<section id="positions">
  <div class="section-header">
    <span class="section-num">04</span>
    <h2><strong>Leadership</strong> &amp; Positions</h2>
  </div>
  <div class="pos-grid">

    <div class="pos-card">
      <div>
        <div class="pos-title">Saarang Finance Manager</div>
        <div class="pos-highlight">₹1Cr+ budget managed</div>
      </div>
      <div class="pos-period">2024–25</div>
      <ul>
        <li>Led end-to-end budgeting of ₹26L, driving ₹4.6L cost optimisation through strategic cross-utilisation of resources.</li>
        <li>Primary financial POC for 100+ events, overseeing ₹20L+ in event budgets during Saarang fest operations.</li>
        <li>Independently managed ₹1Cr+ Proshows budget — the largest financial responsibility within Saarang.</li>
      </ul>
    </div>

    <div class="pos-card">
      <div>
        <div class="pos-title">Saarang Finance Coordinator</div>
        <div class="pos-highlight">30% remediation time reduction</div>
      </div>
      <div class="pos-period">2023–24</div>
      <ul>
        <li>Designed Saarang's first-ever digitised finance portal with fully automated approval and audit workflows.</li>
        <li>Expanded cuisine diversity by 52%, generating ₹20L in food stall revenue through optimised vendor onboarding.</li>
        <li>Improved operational efficiency and financial transparency by aligning demand patterns with real-time execution.</li>
      </ul>
    </div>

    <div class="pos-card">
      <div>
        <div class="pos-title">Sathi Mentor &amp; AEA Events Coordinator</div>
      </div>
      <div class="pos-period">2023–24</div>
      <ul>
        <li>Conducted structured 1:1 mentorship sessions strengthening problem-solving, decision-making, and leadership skills.</li>
        <li>Coordinated multiple technical and cultural events under the Aerospace Engineering Association.</li>
        <li>Collaborated with faculty and industry professionals to organise workshops, seminars, and competitions.</li>
      </ul>
    </div>

  </div>
</section>

<!-- EDUCATION -->
<section id="education">
  <div class="section-header">
    <span class="section-num">05</span>
    <h2><strong>Academic</strong> Background</h2>
  </div>
  <div class="edu-grid">
    <div class="edu-card">
      <div class="edu-left">
        <div class="edu-inst">Indian Institute of Technology Madras</div>
        <div class="edu-prog">B.Tech — Aerospace Engineering · AE22B031</div>
      </div>
      <div class="edu-right">
        <div class="edu-grade">6.64 CGPA</div>
        <div class="edu-year">2022–26</div>
      </div>
    </div>
    <div class="edu-card">
      <div class="edu-left">
        <div class="edu-inst">Jawhar Navodaya Vidyalaya, Warangal</div>
        <div class="edu-prog">Class XII · TSBIE</div>
      </div>
      <div class="edu-right">
        <div class="edu-grade">75.0%</div>
        <div class="edu-year">2022</div>
      </div>
    </div>
    <div class="edu-card">
      <div class="edu-left">
        <div class="edu-inst">Laser High School, Warangal</div>
        <div class="edu-prog">Class X · BSEAP</div>
      </div>
      <div class="edu-right">
        <div class="edu-grade">10 / 10</div>
        <div class="edu-year">2020</div>
      </div>
    </div>
  </div>

  <div style="margin-top: 2.5rem;">
    <h3 style="font-size: 16px; font-weight: 500; color: var(--text); margin-bottom: 1rem; letter-spacing: -0.01em;">Scholastic Achievements</h3>
    <div class="ach-list">
      <div class="ach-item"><div class="ach-num">01</div><div class="ach-text"><strong>Top 0.3 percentile</strong> in JEE Mains 2022 among 1.2 million+ candidates</div></div>
      <div class="ach-item"><div class="ach-num">02</div><div class="ach-text"><strong>National Runner-up (2nd Prize)</strong> in Abacus &amp; Mental Arithmetic — 2,000+ participants</div></div>
      <div class="ach-item"><div class="ach-num">03</div><div class="ach-text"><strong>Top 0.2%</strong> in EAMCET among 3.5 lakh+ applicants</div></div>
      <div class="ach-item"><div class="ach-num">04</div><div class="ach-text"><strong>Top 0.05 percentile</strong> in TS-POLYCET statewide</div></div>
      <div class="ach-item"><div class="ach-num">05</div><div class="ach-text">Represented in <strong>U17 SQAY Martial Arts</strong> at 64th National School Games, Punjab (2018–19)</div></div>
      <div class="ach-item"><div class="ach-num">06</div><div class="ach-text">Selected among top athletes for <strong>NSO Athletics</strong> at IIT Madras</div></div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="section-header">
    <span class="section-num">06</span>
    <h2><strong>Let's</strong> Connect</h2>
  </div>
  <p style="font-size: 15px; color: var(--muted); margin-bottom: 2rem; max-width: 480px;">
    Open to internship and full-time roles in GenAI, Full Stack AI, and software engineering. Feel free to reach out.
  </p>
  <div class="contact-grid">
    <a href="mailto:indrakaran1411@gmail.com" class="contact-card">
      <span class="contact-icon">✉️</span>
      <div>
        <div class="contact-label">Email</div>
        <div class="contact-val">indrakaran1411@gmail.com</div>
      </div>
    </a>
    <a href="tel:+919989759504" class="contact-card">
      <span class="contact-icon">📞</span>
      <div>
        <div class="contact-label">Phone</div>
        <div class="contact-val">+91 99897 59504</div>
      </div>
    </a>
    <a href="https://linkedin.com/in/indrakarangajula" target="_blank" class="contact-card">
      <span class="contact-icon">💼</span>
      <div>
        <div class="contact-label">LinkedIn</div>
        <div class="contact-val">indrakarangajula</div>
      </div>
    </a>
    <a href="https://github.com/Indrakaran1411" target="_blank" class="contact-card">
      <span class="contact-icon">⌨️</span>
      <div>
        <div class="contact-label">GitHub</div>
        <div class="contact-val">Indrakaran1411</div>
      </div>
    </a>
  </div>
</section>

<footer>
  <p>Crafted with precision · Gajula Indra Karan · AE22B031 · IIT Madras · 2026</p>
  <p style="font-family: 'DM Mono', monospace; font-size: 11px;">GenAI · Full Stack · MLOps</p>
</footer>

</body>
</html>
