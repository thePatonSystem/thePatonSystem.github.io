<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>The Paton System</title>
  <meta
    name="description"
    content="The Paton System — A structural framework defining what can exist, be observed, and continue."
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

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }

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

    a { color: var(--accent-2); text-decoration: none; }
    a:hover { color: #ffffff; }

    .wrap { width: min(100% - 32px, var(--max)); margin: 0 auto; }

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
    }

    .nav { display: flex; gap: 16px; }
    .nav a { color: var(--muted); font-size: 0.95rem; }
    .nav a:hover { color: #fff; }

    .hero { padding: 88px 0 64px; }

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
    }

    .actions { display: flex; gap: 14px; margin-top: 28px; }

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
    }

    .btn.primary {
      background: linear-gradient(180deg, rgba(143,183,255,0.35), rgba(143,183,255,0.16));
      border-color: rgba(143,183,255,0.42);
    }

    section { padding: 24px 0 40px; }

    .section-title { font-size: 1.8rem; }
    .section-intro { color: var(--muted); max-width: 760px; }

    .card {
      background: var(--panel);
      border: 1px solid var(--line);
      border-radius: var(--radius);
      padding: 24px;
      box-shadow: var(--shadow);
    }

    .tier-list {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 10px;
      list-style: none;
      padding: 0;
    }

    .tier-list li {
      padding: 10px;
      border-radius: 12px;
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
    }

    .papers { display: grid; gap: 12px; }

    .paper {
      padding: 16px;
      border-radius: 14px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.04);
    }

    .quote {
      font-size: 1.3rem;
      color: #fff;
    }

    .footer {
      padding: 28px 0 56px;
      color: var(--muted);
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
        A structural framework defining what can exist, be observed, and continue.
      </p>

      <div class="flow">Possibility → Admissibility → Observation → Continuation → Boundary</div>

      <div class="actions">
        <a class="btn primary" href="#papers">Core Papers</a>
        <a class="btn" href="#architecture">Architecture</a>
        <a class="btn" href="#links">Links</a>
      </div>
    </div>
  </div>
</section>

<section id="framework">
  <div class="wrap">
    <h2 class="section-title">Framework</h2>
    <p class="section-intro">
      The Paton System defines the condition that must be satisfied before any system can exist, be observed, or continue.
    </p>

    <div class="card">
      State ∈ System ⇔ Admissible ∧ Reachable<br />
      ℘ₙ = Cₙ (℘ₙ₋₁ + ℘ₙ₋₂)<br />
      Πₚₐ = 1 − (Σ Eₖ / Σ (Bₖ + ε))
    </div>
  </div>
</section>

<section id="architecture">
  <div class="wrap">
    <h2 class="section-title">Architecture</h2>
    <div class="card">
      <ul class="tier-list">
        <li><strong>Tier 0</strong> Availability</li>
        <li><strong>Tier 1</strong> Distinction</li>
        <li><strong>Tier 2</strong> Formation</li>
        <li><strong>Tier 3</strong> Admissibility</li>
        <li><strong>Tier 4</strong> Observation</li>
        <li><strong>Tier 5</strong> Continuation</li>
        <li><strong>Tier 6</strong> Structural Laws</li>
        <li><strong>Tier 7</strong> Domains</li>
        <li><strong>Tier 8</strong> Boundary</li>
      </ul>
    </div>
  </div>
</section>

<section id="papers">
  <div class="wrap">
    <h2 class="section-title">Core Papers</h2>

    <div class="papers">
      <div class="paper">The Paton System</div>
      <div class="paper">Tier-4 Observation as a Constrained Interface</div>
      <div class="paper">Big Bang — A Structural Interpretation</div>
      <div class="paper">Non-Finality in Constrained Systems</div>
      <div class="paper">From System to Domain</div>
    </div>
  </div>
</section>

<section>
  <div class="wrap">
    <div class="card">
      <p class="quote">
        The Paton System does not replace scientific theories.  
        It defines the condition under which systems can exist, be observed, and continue.
      </p>
    </div>
  </div>
</section>

<section id="links">
  <div class="wrap">
    <h2 class="section-title">Links</h2>

    <div class="card">
      <p>
        Zenodo / PhilPapers / Contact<br />
        https://thepatonsystem.github.io/
      </p>
    </div>
  </div>
</section>

</main>

<footer class="footer">
  <div class="wrap">
    © Andrew John Paton — The Paton System
  </div>
</footer>

</body>
</html>
