<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>The Paton System</title>
  <meta
    name="description"
    content="The Paton System — A Unified Constraint-Based Architecture of Existence, Observation and Continuation."
  />
  <style>
    :root {
      --bg: #0b1020;
      --bg-soft: #111936;
      --panel: rgba(255, 255, 255, 0.06);
      --panel-strong: rgba(255, 255, 255, 0.1);
      --text: #eef2ff;
      --muted: #b7c0e0;
      --line: rgba(255, 255, 255, 0.12);
      --accent: #8fb7ff;
      --accent-2: #d6e4ff;
      --shadow: 0 20px 60px rgba(0, 0, 0, 0.35);
      --max: 1120px;
      --radius: 22px;
    }

    * {
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
      color: var(--text);
      background:
        radial-gradient(circle at top left, rgba(143, 183, 255, 0.16), transparent 30%),
        radial-gradient(circle at top right, rgba(214, 228, 255, 0.12), transparent 28%),
        linear-gradient(180deg, #0a0f1f 0%, #0b1020 55%, #0d1430 100%);
      line-height: 1.6;
    }

    a {
      color: var(--accent-2);
      text-decoration: none;
    }

    a:hover {
      color: #ffffff;
    }

    .wrap {
      width: min(100% - 32px, var(--max));
      margin: 0 auto;
    }

    .topbar {
      position: sticky;
      top: 0;
      z-index: 20;
      backdrop-filter: blur(14px);
      background: rgba(11, 16, 32, 0.72);
      border-bottom: 1px solid var(--line);
    }

    .topbar-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      min-height: 68px;
    }

    .brand {
      font-weight: 700;
      letter-spacing: 0.04em;
      font-size: 0.96rem;
      color: #fff;
      white-space: nowrap;
    }

    .nav {
      display: flex;
      flex-wrap: wrap;
      gap: 16px;
    }

    .nav a {
      color: var(--muted);
      font-size: 0.95rem;
    }

    .nav a:hover {
      color: #fff;
    }

    .hero {
      padding: 88px 0 64px;
    }

    .hero-card {
      background: linear-gradient(180deg, rgba(255,255,255,0.07), rgba(255,255,255,0.04));
      border: 1px solid var(--line);
      border-radius: 32px;
      box-shadow: var(--shadow);
      padding: 48px 32px 34px;
    }

    .eyebrow {
      display: inline-block;
      padding: 8px 12px;
      border-radius: 999px;
      background: rgba(255,255,255,0.08);
      border: 1px solid var(--line);
      color: var(--muted);
      font-size: 0.84rem;
      letter-spacing: 0.03em;
      margin-bottom: 20px;
    }

    h1 {
      margin: 0 0 16px;
      font-size: clamp(2.2rem, 4vw, 4.3rem);
      line-height: 1.04;
      letter-spacing: -0.03em;
    }

    .subtitle {
      margin: 0;
      max-width: 780px;
      color: var(--muted);
      font-size: clamp(1.04rem, 1.8vw, 1.24rem);
    }

    .flow {
      margin: 28px 0 0;
      padding: 18px 20px;
      background: rgba(255,255,255,0.05);
      border: 1px solid var(--line);
      border-radius: 18px;
      font-weight: 600;
      color: #fff;
      font-size: clamp(1rem, 2vw, 1.2rem);
      letter-spacing: 0.01em;
    }

    .actions {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
      margin-top: 28px;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      min-height: 46px;
      padding: 0 18px;
      border-radius: 14px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.06);
      color: #fff;
      font-weight: 600;
      transition: transform 0.15s ease, background 0.15s ease, border-color 0.15s ease;
    }

    .btn:hover {
      transform: translateY(-1px);
      background: rgba(255,255,255,0.1);
      border-color: rgba(255,255,255,0.22);
    }

    .btn.primary {
      background: linear-gradient(180deg, rgba(143,183,255,0.35), rgba(143,183,255,0.16));
      border-color: rgba(143,183,255,0.42);
    }

    section {
      padding: 24px 0 40px;
    }

    .section-title {
      margin: 0 0 12px;
      font-size: clamp(1.55rem, 2vw, 2rem);
      letter-spacing: -0.02em;
    }

    .section-intro {
      margin: 0 0 24px;
      color: var(--muted);
      max-width: 760px;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(12, 1fr);
      gap: 18px;
    }

    .card {
      grid-column: span 12;
      background: var(--panel);
      border: 1px solid var(--line);
      border-radius: var(--radius);
      padding: 24px;
      box-shadow: var(--shadow);
    }

    .card h3 {
      margin: 0 0 10px;
      font-size: 1.1rem;
      letter-spacing: -0.01em;
    }

    .card p {
      margin: 0;
      color: var(--muted);
    }

    .mini {
      margin-top: 14px;
      color: #fff;
      font-weight: 600;
      font-size: 0.98rem;
    }

    .tier-list {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 12px 18px;
      margin: 0;
      padding: 0;
      list-style: none;
    }

    .tier-list li {
      padding: 12px 14px;
      border-radius: 14px;
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
      color: var(--muted);
    }

    .tier-list strong {
      display: block;
      color: #fff;
      margin-bottom: 2px;
      font-size: 0.96rem;
    }

    .papers {
      display: grid;
      gap: 14px;
    }

    .paper {
      display: block;
      padding: 18px 18px;
      border-radius: 18px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.04);
      transition: transform 0.15s ease, background 0.15s ease;
    }

    .paper:hover {
      transform: translateY(-1px);
      background: rgba(255,255,255,0.08);
    }

    .paper-title {
      display: block;
      color: #fff;
      font-weight: 700;
      margin-bottom: 4px;
    }

    .paper-note {
      color: var(--muted);
      font-size: 0.95rem;
    }

    .quote {
      font-size: clamp(1.15rem, 2vw, 1.42rem);
      line-height: 1.5;
      color: #fff;
      margin: 0;
    }

    .footer {
      padding: 28px 0 56px;
      color: var(--muted);
      font-size: 0.94rem;
    }

    .footer-line {
      border-top: 1px solid var(--line);
      padding-top: 20px;
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      gap: 12px;
    }

    @media (min-width: 860px) {
      .span-4 { grid-column: span 4; }
      .span-5 { grid-column: span 5; }
      .span-6 { grid-column: span 6; }
      .span-7 { grid-column: span 7; }
      .span-8 { grid-column: span 8; }
      .span-12 { grid-column: span 12; }
    }

    @media (max-width: 700px) {
      .hero-card {
        padding: 34px 20px 24px;
        border-radius: 24px;
      }

      .tier-list {
        grid-template-columns: 1fr;
      }

      .nav {
        display: none;
      }

      .footer-line {
        flex-direction: column;
      }
    }
  </style>
</head>
<body>
  <header class="topbar">
    <div class="wrap topbar-inner">
      <div class="brand">THE PATON SYSTEM</div>
      <nav class="nav">
        <a href="#framework">Framework</a>
        <a href="#architecture">Architecture</a>
        <a href="#papers">Core Papers</a>
        <a href="#links">Links</a>
      </nav>
    </div>
  </header>

  <main>
    <section class="hero">
      <div class="wrap">
        <div class="hero-card">
          <div class="eyebrow">Constraint before continuation</div>
          <h1>THE PATON SYSTEM</h1>
          <p class="subtitle">
            A Unified Constraint-Based Architecture of Existence, Observation and Continuation.
          </p>

          <div class="flow">Exist → Form → Observe → Continue → Limit</div>

          <div class="actions">
            <a class="btn primary" href="#papers">Read the core papers</a>
            <a class="btn" href="#architecture">View architecture</a>
            <a class="btn" href="#links">Zenodo / PhilPapers / Contact</a>
          </div>
        </div>
      </div>
    </section>

    <section id="framework">
      <div class="wrap">
        <h2 class="section-title">Framework</h2>
        <p class="section-intro">
          The Paton System is a pre-theoretical structural framework. It does not introduce new physical laws. It defines the conditions under which systems are permitted to exist, be observed, and continue.
        </p>

        <div class="grid">
          <article class="card span-7">
            <h3>Minimal core</h3>
            <p>
              State ∈ System ⇔ Admissible ∧ Reachable<br />
              ℘ₙ = Cₙ (℘ₙ₋₁ + ℘ₙ₋₂)<br />
              Πₚₐ = 1 − (Σ Eₖ / Σ (Bₖ + ε))
            </p>
            <div class="mini">Existence → Formation → Continuation</div>
          </article>

          <article class="card span-5">
            <h3>What it does</h3>
            <p>
              It constrains when description, observation, and continuation remain valid. Domains differ in constraint, not in underlying structural logic.
            </p>
          </article>
        </div>
      </div>
    </section>

    <section id="architecture">
      <div class="wrap">
        <h2 class="section-title">Architecture</h2>
        <p class="section-intro">
          The framework is organised as a tiered structural hierarchy, from undivided availability through to continuity limits and boundary conditions.
        </p>

        <div class="card">
          <ul class="tier-list">
            <li><strong>Tier 0</strong>Availability</li>
            <li><strong>Tier 1</strong>Distinction</li>
            <li><strong>Tier 2</strong>Formation</li>
            <li><strong>Tier 3</strong>Admissibility</li>
            <li><strong>Tier 4</strong>Observation</li>
            <li><strong>Tier 5</strong>Continuation</li>
            <li><strong>Tier 6</strong>Structural Laws</li>
            <li><strong>Tier 7</strong>Domain Instantiation</li>
            <li><strong>Tier 8</strong>Boundary / Continuity Limit</li>
          </ul>
        </div>
      </div>
    </section>

    <section id="papers">
      <div class="wrap">
        <h2 class="section-title">Core papers</h2>
        <p class="section-intro">
          A minimal entry path through the system. Keep this section tight and current.
        </p>

        <div class="papers">
          <a class="paper" href="https://doi.org/10.5281/zenodo.19341703" target="_blank" rel="noopener noreferrer">
            <span class="paper-title">The Paton System</span>
            <span class="paper-note">System anchor / capstone entry paper</span>
          </a>

          <a class="paper" href="https://doi.org/10.5281/zenodo.19326055" target="_blank" rel="noopener noreferrer">
            <span class="paper-title">Tier-4 Observation as a Constrained Interface</span>
            <span class="paper-note">Observation as bounded interface, not full access</span>
          </a>

          <a class="paper" href="https://doi.org/10.5281/zenodo.19325006" target="_blank" rel="noopener noreferrer">
            <span class="paper-title">Big Bang — A Structural Interpretation</span>
            <span class="paper-note">Boundary of admissible reconstruction</span>
          </a>

          <a class="paper" href="https://doi.org/10.5281/zenodo.19341594" target="_blank" rel="noopener noreferrer">
            <span class="paper-title">Non-Finality in Constrained Systems</span>
            <span class="paper-note">Recursive re-emergence and limits of observation</span>
          </a>

          <a class="paper" href="https://doi.org/10.5281/zenodo.19325727" target="_blank" rel="noopener noreferrer">
            <span class="paper-title">From System to Domain</span>
            <span class="paper-note">Structural invariance across constraint environments</span>
          </a>
        </div>
      </div>
    </section>

    <section>
      <div class="wrap">
        <div class="card">
          <p class="quote">
            “The Paton System does not replace scientific theories. It defines the conditions under which systems can exist, be observed, and continue.”
          </p>
        </div>
      </div>
    </section>

    <section id="links">
      <div class="wrap">
        <h2 class="section-title">Links</h2>
        <p class="section-intro">
          Keep the outward layer simple. Let the site orient. Let the papers carry the depth.
        </p>

        <div class="grid">
          <article class="card span-4">
            <h3>Zenodo</h3>
            <p>
              Primary archive for papers and DOI records.<br /><br />
              <a href="https://zenodo.org/" target="_blank" rel="noopener noreferrer">Open Zenodo</a>
            </p>
          </article>

          <article class="card span-4">
            <h3>PhilPapers / PhilPeople</h3>
            <p>
              Publication index and external clustering of the research program.<br /><br />
              <a href="https://philpeople.org/profiles/andrew-john-paton/publications" target="_blank" rel="noopener noreferrer">Open PhilPeople publications</a>
            </p>
          </article>

          <article class="card span-4">
            <h3>Contact</h3>
            <p>
              Direct contact for discussion, collaboration, or review.<br /><br />
              <a href="mailto:feedback_patonsystem@protonmail.com">feedback_patonsystem@protonmail.com</a>
            </p>
          </article>
        </div>
      </div>
    </section>
  </main>

  <footer class="footer">
    <div class="wrap footer-line">
      <div>
        © Andrew John Paton — The Paton System<br />
        <a href="mailto:feedback_patonsystem@protonmail.com">feedback_patonsystem@protonmail.com</a>
      </div>
      <div>Constraint-based architecture of existence, observation and continuation</div>
    </div>
  </footer>
</body>
</html>
