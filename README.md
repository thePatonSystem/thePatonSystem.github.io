<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>The Paton System</title>

  <style>
    :root {
      --bg: #0b1020;
      --panel: rgba(255,255,255,0.05);
      --text: #eef2ff;
      --muted: #b7c0e0;
      --line: rgba(255,255,255,0.12);
      --accent: #8fb7ff;
    }

    body {
      margin: 0;
      font-family: -apple-system, Segoe UI, Roboto, sans-serif;
      background: linear-gradient(180deg,#0a0f1f,#0d1430);
      color: var(--text);
    }

    .wrap {
      width: min(100% - 32px, 1100px);
      margin: auto;
    }

    header {
      border-bottom: 1px solid var(--line);
      padding: 16px 0;
      text-align: center;
      font-weight: 600;
      letter-spacing: .1em;
    }

    h1 {
      font-size: 3rem;
      margin: 40px 0 10px;
      text-align: center;
    }

    p {
      text-align: center;
      color: var(--muted);
    }

    .flow {
      margin: 30px auto;
      text-align: center;
      font-weight: bold;
      font-size: 1.2rem;
      padding: 15px;
      border: 1px solid var(--line);
      border-radius: 12px;
      width: fit-content;
    }

    .section {
      margin: 60px 0;
    }

    .grid {
      display: grid;
      gap: 20px;
    }

    .card {
      background: var(--panel);
      padding: 20px;
      border-radius: 16px;
      border: 1px solid var(--line);
    }

    a {
      color: var(--accent);
      text-decoration: none;
    }

    a:hover {
      color: white;
    }

    footer {
      border-top: 1px solid var(--line);
      padding: 30px 0;
      text-align: center;
      color: var(--muted);
      font-size: 0.9rem;
    }
  </style>
</head>

<body>

<header>
  THE PATON SYSTEM
</header>

<div class="wrap">

  <h1>The Paton System</h1>

  <p>
    A Unified Constraint-Based Architecture of Existence, Observation and Continuation
  </p>

  <div class="flow">
    Exist → Form → Observe → Continue → Limit
  </div>

  <!-- CORE -->
  <div class="section">
    <div class="grid">
      <div class="card">
        <strong>Minimal Core</strong><br><br>
        State ∈ System ⇔ Admissible ∧ Reachable<br>
        ℘ₙ = Cₙ (℘ₙ₋₁ + ℘ₙ₋₂)<br>
        Πₚₐ = 1 − (Σ Eₖ / Σ (Bₖ + ε))
      </div>

      <div class="card">
        <strong>Framework</strong><br><br>
        The Paton System defines when systems can exist, be observed, and continue.
      </div>
    </div>
  </div>

  <!-- TIERS -->
  <div class="section">
    <div class="card">
      <strong>Architecture</strong><br><br>
      Tier 0 — Availability<br>
      Tier 1 — Distinction<br>
      Tier 2 — Formation<br>
      Tier 3 — Admissibility<br>
      Tier 4 — Observation<br>
      Tier 5 — Continuation<br>
      Tier 6 — Structural Laws<br>
      Tier 7 — Domain Instantiation<br>
      Tier 8 — Boundary / Continuity Limit
    </div>
  </div>

  <!-- PAPERS -->
  <div class="section">
    <div class="card">
      <strong>Core Papers</strong><br><br>

      <a href="https://doi.org/10.5281/zenodo.19341703">The Paton System</a><br><br>
      <a href="https://doi.org/10.5281/zenodo.19341594">Non-Finality in Constrained Systems</a><br><br>

    </div>
  </div>

  <!-- LINKS -->
  <div class="section">
    <div class="grid">
      <div class="card">
        <strong>Zenodo</strong><br><br>
        <a href="https://zenodo.org/">Open Zenodo</a>
      </div>

      <div class="card">
        <strong>PhilPapers</strong><br><br>
        <a href="https://philpeople.org/profiles/andrew-john-paton/publications">
          View Publications
        </a>
      </div>

      <div class="card">
        <strong>Contact</strong><br><br>
        <a href="mailto:feedback_patonsystem@protonmail.com">
          feedback_patonsystem@protonmail.com
        </a>
      </div>
    </div>
  </div>

</div>

<footer>
  © Andrew John Paton — The Paton System<br><br>
  <a href="mailto:feedback_patonsystem@protonmail.com">
    feedback_patonsystem@protonmail.com
  </a>
</footer>

</body>
</html>
