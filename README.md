<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>The Paton System</title>
  <meta
    name="description"
    content="The Paton System — a viability-first structural framework governing admissibility continuation and bounded reasoning across domains."
  />
  <style>
    :root {
      --bg: #f5f7fb;
      --surface: #ffffff;
      --surface-2: #f0f4fa;
      --text: #0f172a;
      --muted: #475569;
      --line: #dbe3ee;
      --accent: #2563eb;
      --accent-dark: #1d4ed8;
      --shadow: 0 10px 30px rgba(15, 23, 42, 0.08);
      --radius: 18px;
      --max: 1080px;
    }

    * {
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      font-family: Arial, Helvetica, sans-serif;
      background:
        radial-gradient(circle at top left, rgba(37, 99, 235, 0.08), transparent 26%),
        radial-gradient(circle at top right, rgba(29, 78, 216, 0.06), transparent 24%),
        var(--bg);
      color: var(--text);
      line-height: 1.55;
    }

    a {
      color: var(--accent);
      text-decoration: none;
    }

    a:hover {
      color: var(--accent-dark);
      text-decoration: underline;
    }

    .wrap {
      width: min(100% - 28px, var(--max));
      margin: 0 auto;
    }

    .topbar {
      padding: 18px 0 8px;
    }

    .brand {
      display: inline-block;
      font-size: 1rem;
      font-weight: 700;
      letter-spacing: 0.02em;
      color: var(--accent);
    }

    .hero {
      padding: 18px 0 28px;
    }

    .hero-card {
      background: linear-gradient(180deg, #ffffff 0%, #f9fbff 100%);
      border: 1px solid var(--line);
      border-radius: 24px;
      box-shadow: var(--shadow);
      padding: 34px 24px 26px;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-size: 0.88rem;
      font-weight: 700;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: var(--accent);
      background: rgba(37, 99, 235, 0.08);
      border: 1px solid rgba(37, 99, 235, 0.14);
      padding: 8px 12px;
      border-radius: 999px;
      margin-bottom: 16px;
    }

    h1 {
      margin: 0 0 14px;
      font-size: clamp(2rem, 6vw, 4rem);
      line-height: 1.03;
      letter-spacing: -0.03em;
    }

    .hero-sub {
      margin: 0;
      font-size: clamp(1rem, 2.2vw, 1.3rem);
      color: var(--muted);
      max-width: 760px;
    }

    .button-row {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      margin-top: 24px;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      min-height: 46px;
      padding: 0 16px;
      border-radius: 12px;
      border: 1px solid var(--line);
      background: var(--surface);
      color: var(--text);
      font-weight: 700;
      transition: 0.18s ease;
      box-shadow: 0 4px 12px rgba(15, 23, 42, 0.04);
    }

    .btn:hover {
      transform: translateY(-1px);
      text-decoration: none;
    }

    .btn.primary {
      background: var(--accent);
      color: #ffffff;
      border-color: var(--accent);
    }

    .btn.primary:hover {
      background: var(--accent-dark);
    }

    .section {
      padding: 18px 0 10px;
    }

    .section-title {
      font-size: 1.35rem;
      margin: 0 0 14px;
      letter-spacing: -0.02em;
    }

    .section-sub {
      color: var(--muted);
      margin: 0 0 18px;
      max-width: 800px;
    }

    .spine {
      background: var(--surface);
      border: 1px solid var(--line);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      padding: 20px;
    }

    .spine-line {
      font-size: clamp(1rem, 2.1vw, 1.35rem);
      font-weight: 700;
      line-height: 1.6;
      color: var(--text);
    }

    .spine-line .arrow {
      color: var(--accent);
      font-weight: 700;
      padding: 0 6px;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(12, 1fr);
      gap: 16px;
    }

    .card {
      grid-column: span 12;
      background: var(--surface);
      border: 1px solid var(--line);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      padding: 18px 16px;
      position: relative;
      overflow: hidden;
    }

    .card::before {
      content: "";
      position: absolute;
      inset: 0 auto 0 0;
      width: 5px;
      background: linear-gradient(180deg, var(--accent), #60a5fa);
      opacity: 0.95;
    }

    .tier-label {
      margin: 0 0 8px;
      font-size: 1.18rem;
      letter-spacing: -0.02em;
    }

    .tier-desc {
      margin: 0;
      color: var(--muted);
      font-size: 1rem;
    }

    .tier-meta {
      margin-top: 12px;
      font-size: 0.9rem;
      color: var(--accent);
      font-weight: 700;
    }

    .statement {
      background: linear-gradient(180deg, #ffffff 0%, #f8fbff 100%);
      border: 1px solid var(--line);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      padding: 22px 20px;
    }

    .statement p {
      margin: 0;
      font-size: clamp(1.02rem, 2.1vw, 1.22rem);
      color: var(--text);
    }

    .links-card {
      background: var(--surface);
      border: 1px solid var(--line);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      padding: 20px;
    }

    .link-list {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 12px;
      margin-top: 14px;
    }

    .link-item {
      display: block;
      padding: 14px 14px;
      border-radius: 14px;
      background: var(--surface-2);
      border: 1px solid var(--line);
      color: var(--text);
      font-weight: 700;
    }

    .link-item small {
      display: block;
      font-weight: 400;
      color: var(--muted);
      margin-top: 4px;
    }

    .footer {
      padding: 30px 0 50px;
      color: var(--muted);
    }

    .footer-card {
      background: var(--surface);
      border: 1px solid var(--line);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      padding: 18px 20px;
    }

    .footer p {
      margin: 0 0 8px;
    }

    @media (min-width: 760px) {
      .card {
        grid-column: span 6;
      }
    }

    @media (min-width: 980px) {
      .card {
        grid-column: span 4;
      }
    }

    @media (max-width: 640px) {
      .hero-card {
        padding: 24px 18px 20px;
        border-radius: 18px;
      }

      .spine,
      .statement,
      .links-card,
      .footer-card,
      .card {
        border-radius: 16px;
      }

      .link-list {
        grid-template-columns: 1fr;
      }

      .button-row {
        flex-direction: column;
      }

      .btn {
        width: 100%;
      }

      .spine-line {
        font-size: 1rem;
      }
    }
  </style>
</head>
<body>
  <div class="wrap">
    <header class="topbar">
      <a class="brand" href="#">thePatonSystem</a>
    </header>

    <section class="hero">
      <div class="hero-card">
        <div class="eyebrow">Viability-first structural framework</div>
        <h1>THE PATON SYSTEM</h1>
        <p class="hero-sub">
          Positioned prior to modelling — governing admissibility, continuation,
          and bounded reasoning across domains.
        </p>

        <div class="button-row">
          <a class="btn primary" href="https://doi.org/10.5281/zenodo.19033299" target="_blank" rel="noopener noreferrer">Anchor Paper</a>
          <a class="btn" href="https://zenodo.org/search?q=Andrew%20John%20Paton" target="_blank" rel="noopener noreferrer">Zenodo Archive</a>
          <a class="btn" href="https://philpapers.org/s/Andrew%20John%20Paton" target="_blank" rel="noopener noreferrer">PhilPapers</a>
          <a class="btn" href="https://philpeople.org/profiles/andrew-john-paton/publications" target="_blank" rel="noopener noreferrer">PhilPeople</a>
        </div>
      </div>
    </section>

    <section class="section">
      <h2 class="section-title">Canonical Structural Spine</h2>
      <p class="section-sub">
        The minimal cycle describing how systems become distinguishable,
        admissible, observable, continuable, and bounded.
      </p>
      <div class="spine">
        <div class="spine-line">
          Boundary <span class="arrow">→</span>
          Availability <span class="arrow">→</span>
          Distinction <span class="arrow">→</span>
          Formation <span class="arrow">→</span>
          Admissibility <span class="arrow">→</span>
          Observation <span class="arrow">→</span>
          Continuation <span class="arrow">→</span>
          Persistence <span class="arrow">→</span>
          Termination <span class="arrow">→</span>
          Boundary
        </div>
      </div>
    </section>

    <section class="section">
      <h2 class="section-title">Tier Structure</h2>
      <p class="section-sub">
        Eight tiers describing structural progression from undivided availability
        to global stopping condition.
      </p>

      <div class="grid">
        <article class="card">
          <h3 class="tier-label">Tier 0 — Availability</h3>
          <p class="tier-desc">Undivided possibility.</p>
          <div class="tier-meta">Locked foundation</div>
        </article>

        <article class="card">
          <h3 class="tier-label">Tier 1 — Distinction</h3>
          <p class="tier-desc">Boundary emergence and first separation.</p>
          <div class="tier-meta">Locked foundation</div>
        </article>

        <article class="card">
          <h3 class="tier-label">Tier 2 — Formation</h3>
          <p class="tier-desc">Relations, structure, and constrained formation.</p>
          <div class="tier-meta">Locked foundation</div>
        </article>

        <article class="card">
          <h3 class="tier-label">Tier 3 — Admissibility</h3>
          <p class="tier-desc">Permission to exist and continue.</p>
          <div class="tier-meta">Gate layer</div>
        </article>

        <article class="card">
          <h3 class="tier-label">Tier 4 — Observation</h3>
          <p class="tier-desc">Measurement, representation, and datum-scale access.</p>
          <div class="tier-meta">Interface layer</div>
        </article>

        <article class="card">
          <h3 class="tier-label">Tier 5 — Continuation</h3>
          <p class="tier-desc">Recursive persistence through time.</p>
          <div class="tier-meta">Generative continuation</div>
        </article>

        <article class="card">
          <h3 class="tier-label">Tier 6 — Structural Framework</h3>
          <p class="tier-desc">Geometry, motion, control, breakdown, and law-like structure.</p>
          <div class="tier-meta">Framework layer</div>
        </article>

        <article class="card">
          <h3 class="tier-label">Tier 7 — Domain Systems</h3>
          <p class="tier-desc">Mathematics, physics, computation, AI, organisational, and economic systems.</p>
          <div class="tier-meta">Cross-domain instantiation</div>
        </article>

        <article class="card">
          <h3 class="tier-label">Tier 8 — Boundary Horizon</h3>
          <p class="tier-desc">Global limits and stopping condition.</p>
          <div class="tier-meta">Boundary knowledge</div>
        </article>
      </div>
    </section>

    <section class="section">
      <div class="statement">
        <p>
          The Paton System describes the structural conditions under which systems
          remain admissible, observable, continuable, and bounded across domains.
        </p>
      </div>
    </section>

    <section class="section">
      <h2 class="section-title">Core Access</h2>
      <div class="links-card">
        <p class="section-sub" style="margin-bottom: 0;">
          Direct entry points for papers, archive, and publication record.
        </p>

        <div class="link-list">
          <a class="link-item" href="https://doi.org/10.5281/zenodo.19033299" target="_blank" rel="noopener noreferrer">
            Admissibility Before Dynamics
            <small>Anchor paper</small>
          </a>

          <a class="link-item" href="https://doi.org/10.5281/zenodo.18644549" target="_blank" rel="noopener noreferrer">
            Paton Framework Core Definition
            <small>Minimal formal core</small>
          </a>

          <a class="link-item" href="https://zenodo.org/search?q=Andrew%20John%20Paton" target="_blank" rel="noopener noreferrer">
            Zenodo Archive
            <small>Publication archive</small>
          </a>

          <a class="link-item" href="https://philpapers.org/s/Andrew%20John%20Paton" target="_blank" rel="noopener noreferrer">
            PhilPapers
            <small>Index and records</small>
          </a>

          <a class="link-item" href="https://philpeople.org/profiles/andrew-john-paton/publications" target="_blank" rel="noopener noreferrer">
            PhilPeople Publications
            <small>Public profile</small>
          </a>

          <a class="link-item" href="mailto:feedback_patonsystem@protonmail.com">
            Contact
            <small>feedback_patonsystem@protonmail.com</small>
          </a>
        </div>
      </div>
    </section>

    <footer class="footer">
      <div class="footer-card">
        <p><strong>feedback_patonsystem@protonmail.com</strong></p>
        
        <p>Messages are reviewed on a triaged basis.</p>
        <p>Clear and well-structured emails are prioritised.</p>
      </div>
    </footer>
  </div>
</body>
</html>
