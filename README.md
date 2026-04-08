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
      --max: 1180px;
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
      max-width: 860px;
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
    }

    .btn.primary {
      background: linear-gradient(180deg, rgba(143,183,255,0.35), rgba(143,183,255,0.16));
      border-color: rgba(143,183,255,0.42);
    }

    section { padding: 24px 0 40px; }

    .section-title {
      font-size: 1.8rem;
      margin: 0 0 12px;
    }

    .section-intro {
      color: var(--muted);
      max-width: 860px;
      margin: 0 0 24px;
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

    .framework-formulas {
      font-size: 1.06rem;
      line-height: 1.9;
      color: #fff;
    }

    .tiers-stack {
      display: grid;
      gap: 12px;
    }

    details.tier,
    details.tree-tier {
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: 16px;
      overflow: hidden;
    }

    details.tier summary,
    details.tree-tier summary {
      list-style: none;
      cursor: pointer;
      padding: 16px 18px;
      font-weight: 700;
      color: #fff;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 16px;
    }

    details.tier summary::-webkit-details-marker,
    details.tree-tier summary::-webkit-details-marker {
      display: none;
    }

    .tier-label {
      display: block;
      color: var(--muted);
      font-weight: 500;
      font-size: 0.95rem;
      margin-top: 2px;
    }

    .tier-arrow {
      color: var(--muted);
      font-size: 0.95rem;
      transition: transform 0.2s ease;
      flex-shrink: 0;
    }

    details[open] .tier-arrow {
      transform: rotate(90deg);
    }

    .tier-content {
      padding: 0 18px 18px 18px;
      color: var(--muted);
      border-top: 1px solid rgba(255,255,255,0.08);
    }

    .logic-note {
      margin-top: 16px;
      padding: 14px 16px;
      border-radius: 16px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.04);
      color: var(--muted);
      font-size: 0.95rem;
    }

    .tree-meta {
      display: grid;
      gap: 12px;
      margin-bottom: 18px;
    }

    .meta-line {
      padding: 14px 16px;
      border-radius: 16px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.04);
      color: var(--muted);
      font-size: 0.95rem;
    }

    .link-list {
      display: grid;
      gap: 10px;
      margin-top: 10px;
    }

    .link-item {
      padding: 14px 16px;
      border-radius: 16px;
      border: 1px solid rgba(255,255,255,0.08);
      background: rgba(255,255,255,0.03);
    }

    .link-item strong {
      color: #fff;
      display: block;
      margin-bottom: 3px;
    }

    .link-item span {
      color: var(--muted);
      font-size: 0.94rem;
    }

    .subhead {
      margin: 0 0 12px;
      font-size: 1.08rem;
      color: #fff;
    }

    .papers {
      display: grid;
      gap: 14px;
    }

    .paper {
      display: block;
      padding: 18px;
      border-radius: 18px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.04);
    }

    .paper-title {
      font-weight: 700;
      display: block;
      color: #fff;
      margin-bottom: 4px;
    }

    .paper-note {
      color: var(--muted);
      font-size: 0.95rem;
    }

    .quote {
      font-size: 1.3rem;
      color: #fff;
      margin: 0;
    }

    .links-grid {
      display: grid;
      grid-template-columns: repeat(12, 1fr);
      gap: 18px;
    }

    .link-card {
      grid-column: span 4;
      background: var(--panel);
      border: 1px solid var(--line);
      border-radius: var(--radius);
      padding: 24px;
      box-shadow: var(--shadow);
    }

    .link-card-title {
      font-size: 1.05rem;
      color: #fff;
      font-weight: 700;
      margin-bottom: 8px;
    }

    .link-card p {
      margin: 0 0 10px;
      color: var(--muted);
      font-size: 0.95rem;
    }

    .footer {
      padding: 28px 0 56px;
      color: var(--muted);
    }

    .footer-line {
      border-top: 1px solid var(--line);
      padding-top: 20px;
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 12px;
    }

    @media (max-width: 900px) {
      .link-card {
        grid-column: span 12;
      }
    }

    @media (max-width: 700px) {
      .hero-card {
        padding: 34px 20px 24px;
        border-radius: 24px;
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
      <a href="#logic-tree">Structural Link Tree</a>
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
        A structural framework defining what can exist, be observed, and continue. The full system is tiered, linked by necessity, and organised so that logical relations can be seen directly rather than inferred loosely by theme.
      </p>

      <div class="flow">Possibility → Admissibility → Observation → Continuation → Structure → Domain → Continuity</div>

      <div class="actions">
        <a class="btn primary" href="#logic-tree">View full structural linkage</a>
        <a class="btn" href="#architecture">View tier architecture</a>
        <a class="btn" href="#papers">Read core papers</a>
      </div>
    </div>
  </div>
</section>

<section id="framework">
  <div class="wrap">
    <h2 class="section-title">Framework</h2>
    <p class="section-intro">
      The Paton System defines the condition that must be satisfied before any system can exist, be observed, or continue. It is a pre-theoretical constraint framework rather than a replacement for domain-specific scientific theory.
    </p>

    <div class="grid">
      <div class="card">
        <div class="framework-formulas">
          State ∈ System ⇔ Admissible ∧ Reachable<br />
          ℘ₙ = Cₙ (℘ₙ₋₁ + ℘ₙ₋₂)<br />
          Πₚₐ = 1 − (Σ Eₖ / Σ (Bₖ + ε))
        </div>
      </div>
    </div>
  </div>
</section>

<section id="architecture">
  <div class="wrap">
    <h2 class="section-title">Architecture</h2>
    <p class="section-intro">
      The system is organised as a tiered structural hierarchy. Open each tier for a short meaning.
    </p>

    <div class="card">
      <div class="tiers-stack">

        <details class="tier">
          <summary>
            <div>
              Tier 0
              <span class="tier-label">Availability</span>
            </div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            Undivided availability. The pre-distinguished condition from which structure can emerge.
          </div>
        </details>

        <details class="tier">
          <summary>
            <div>
              Tier 1
              <span class="tier-label">Distinction</span>
            </div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            Boundary emergence. The first distinction that allows something to be set apart from undivided availability.
          </div>
        </details>

        <details class="tier">
          <summary>
            <div>
              Tier 2
              <span class="tier-label">Formation</span>
            </div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            Structured possibility. Relations, symmetries, and candidate formations can arise, but are not yet guaranteed to exist physically.
          </div>
        </details>

        <details class="tier">
          <summary>
            <div>
              Tier 3
              <span class="tier-label">Admissibility</span>
            </div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            The gate condition. Only configurations that satisfy governing constraints are permitted to exist or continue.
          </div>
        </details>

        <details class="tier">
          <summary>
            <div>
              Tier 4
              <span class="tier-label">Observation</span>
            </div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            Constrained interface. Observation does not reveal all structure, only what remains admissible to resolution.
          </div>
        </details>

        <details class="tier">
          <summary>
            <div>
              Tier 5
              <span class="tier-label">Continuation</span>
            </div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            Recursive persistence. A system continues only while admissibility is preserved across sequential states.
          </div>
        </details>

        <details class="tier">
          <summary>
            <div>
              Tier 6
              <span class="tier-label">Structural Laws</span>
            </div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            Cross-domain structural conditions such as compatibility, viability, field behaviour, curvature, trajectories, regions, and boundary rules.
          </div>
        </details>

        <details class="tier">
          <summary>
            <div>
              Tier 7
              <span class="tier-label">Domain Instantiation</span>
            </div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            Domain-specific realisations of the framework in physics, AI, biology, engineering, organisations, and other systems.
          </div>
        </details>

        <details class="tier">
          <summary>
            <div>
              Tier 8
              <span class="tier-label">Boundary / Continuity Limit</span>
            </div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            The outer continuity horizon. The limiting condition where admissible continuation fails or reaches its final boundary.
          </div>
        </details>

      </div>

      <div class="logic-note">
        <strong style="color:#fff;">Structural rule:</strong> Tier 4 shows. Tier 6 explains. Papers are linked only when one is structurally necessary for another.
      </div>
    </div>
  </div>
</section>

<section id="logic-tree">
  <div class="wrap">
    <h2 class="section-title">Structural Link Tree</h2>
    <p class="section-intro">
      This section shows how the full Paton System relates internally. Links are made by necessity, not by loose thematic similarity. If removing a linked paper breaks the mechanism of another paper, the link remains. If not, it does not belong.
    </p>

    <div class="card">
      <div class="tree-meta">
        <div class="meta-line">
          <strong style="color:#fff;">Linking rule:</strong> Link by necessity. Not by relevance.
        </div>
        <div class="meta-line">
          <strong style="color:#fff;">Interpretive rule:</strong> Tier 4 shows. Tier 6 explains. Tier 7 applies. Tier 8 integrates.
        </div>
      </div>

      <div class="tiers-stack">

        <details class="tree-tier">
          <summary>
            <div>
              Tier 0–3 Foundation
              <span class="tier-label">Availability, distinction, formation, admissibility</span>
            </div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            <div class="link-list">
              <div class="link-item">
                <strong>Tier 0 — Availability</strong>
                <span>Undivided condition from which structure can emerge.</span>
              </div>
              <div class="link-item">
                <strong>Tier 1 — Distinction</strong>
                <span>First separation and boundary emergence.</span>
              </div>
              <div class="link-item">
                <strong>Tier 2 — Formation / Possibility</strong>
                <span>Structured possibility, candidate trajectories, relations.</span>
              </div>
              <div class="link-item">
                <strong>Tier 3 — Admissibility / Filtering</strong>
                <span>Constraint gate determining what may exist and continue.</span>
              </div>
              <div class="link-item">
                <strong>Boundary admission condition</strong>
                <span>The precondition separating continuation from non-continuation.</span>
              </div>
            </div>
          </div>
        </details>

        <details class="tree-tier">
          <summary>
            <div>
              Tier 4 Visibility / Observation
              <span class="tier-label">What becomes visible after admissibility filtering</span>
            </div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            <div class="link-list">
              <div class="link-item">
                <strong>Tier 2 → Tier 3 → Tier 4: Mapping Possibilities to Observed Datum</strong>
                <span>Maps possibility through admissibility into observed datum.</span>
              </div>
              <div class="link-item">
                <strong>Fractals — Structure, Resonance, and Tier Transition</strong>
                <span>Depends on Tier 2 formation and Tier 3 admissibility filtering. Fractals are visible recursion under constraint, not origin structure.</span>
              </div>
              <div class="link-item">
                <strong>Paton System — Canonical Boundary Diagram (Dual Representation)</strong>
                <span>Visualises Tier 4 visibility and bridges Tier 4 ↔ Tier 6 boundary behaviour.</span>
              </div>
            </div>
          </div>
        </details>

        <details class="tree-tier">
          <summary>
            <div>
              Tier 5 Continuation / Recursion
              <span class="tier-label">Recursive persistence under admissibility</span>
            </div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            <div class="link-list">
              <div class="link-item">
                <strong>Recursive Admissibility and System Correctness</strong>
                <span>Formalises recursion as gated continuation under Tier 3 admissibility.</span>
              </div>
              <div class="link-item">
                <strong>Internal Admissibility Practice</strong>
                <span>Shows the Paton System applying recursively to its own paper generation and validation.</span>
              </div>
            </div>
          </div>
        </details>

        <details class="tree-tier">
          <summary>
            <div>
              Tier 6 Structural Integration / Boundary Behaviour
              <span class="tier-label">Geometry, limits, fields, trajectories, compatibility</span>
            </div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            <div class="link-list">
              <div class="link-item">
                <strong>Fit, Form, and Function</strong>
                <span>Local admissibility condition.</span>
              </div>
              <div class="link-item">
                <strong>Admissible Trajectories and Constraint Filtering</strong>
                <span>Defines path persistence under admissibility.</span>
              </div>
              <div class="link-item">
                <strong>Admissible Regions and Boundary Geometry</strong>
                <span>Defines the structural space in which states may continue.</span>
              </div>
              <div class="link-item">
                <strong>Boundary Inversion Under Forced Continuation</strong>
                <span>Defines behavioural inversion at limits when force exceeds admissibility.</span>
              </div>
              <div class="link-item">
                <strong>Boundary Emergence and Boundary Inversion</strong>
                <span>Combines inference constraint at model limits with required system response.</span>
              </div>
              <div class="link-item">
                <strong>Admissibility-Limited Systems — Unified Explanation of Boundary Behaviour</strong>
                <span>Clarifies information persistence versus access at boundaries.</span>
              </div>
              <div class="link-item">
                <strong>Unified Structural Lens</strong>
                <span>Integrates persistence, access, recursion, and non-invertibility across the structure.</span>
              </div>
              <div class="link-item">
                <strong>Tier 6 — Structural Admissibility Geometry</strong>
                <span>Consolidates Tier 6 into one geometry stack: local condition, paths, regions, and limits.</span>
              </div>
            </div>
          </div>
        </details>

        <details class="tree-tier">
          <summary>
            <div>
              Tier 7 Domain Instantiations / Applied Systems
              <span class="tier-label">Applied papers using the framework in domains</span>
            </div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            <div class="link-list">
              <div class="link-item">
                <strong>Paton System — Life Integration</strong>
                <span>Depends on Tier 2 formation, Tier 3 admissibility, and Tier 4 realised datum.</span>
              </div>
              <div class="link-item">
                <strong>Temperature as Propagation Under Constraint</strong>
                <span>Domain application of propagation limits and admissible energy movement.</span>
              </div>
              <div class="link-item">
                <strong>Cosmic Lifecycle as Admissibility Reduction</strong>
                <span>Applies admissibility reduction across cosmological evolution.</span>
              </div>
              <div class="link-item">
                <strong>Constraint Dominance and Admissibility Reduction</strong>
                <span>Bridges Tier 7 cosmological evolution to Tier 8 fate condition.</span>
              </div>
              <div class="link-item">
                <strong>The Paton System — Optical Vortex</strong>
                <span>Applies admissible directionality to light and optical structure.</span>
              </div>
              <div class="link-item">
                <strong>Tier 7 linking rule</strong>
                <span>Domain papers link only to Tier 3 (admissibility), Tier 5 (recursion), or Tier 6 (structure). They do not link sideways by theme alone.</span>
              </div>
            </div>
          </div>
        </details>

        <details class="tree-tier">
          <summary>
            <div>
              Tier 8 Global Continuity / Whole-System Outcome
              <span class="tier-label">Full-system continuity without fixed origin or termination</span>
            </div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            <div class="link-list">
              <div class="link-item">
                <strong>The Paton System — Global Continuity Statement</strong>
                <span>Integrates Tier 2 formation, Tier 3 admissibility, Tier 5 recursion, Tier 6 structural integration, and Tier 7 domain instantiations into one continuous system.</span>
              </div>
              <div class="link-item">
                <strong>Tier 8 definition</strong>
                <span>Defines the continuous system without fixed origin or terminal ending. What changes is not existence, but access and admissible continuity.</span>
              </div>
            </div>
          </div>
        </details>

      </div>
    </div>
  </div>
</section>

<section id="papers">
  <div class="wrap">
    <h2 class="section-title">Core Papers</h2>
    <p class="section-intro">
      Selected anchor papers. These are entry points into the wider system archive.
    </p>

    <div class="papers">
      <a class="paper" href="https://doi.org/10.5281/zenodo.19447197" target="_blank" rel="noopener noreferrer">
        <span class="paper-title">The Paton System — Unified Life Structure</span>
        <span class="paper-note">Unified architecture across Tier 0 → Tier 8</span>
      </a>

      <a class="paper" href="https://doi.org/10.5281/zenodo.19463366" target="_blank" rel="noopener noreferrer">
        <span class="paper-title">The Paton System — Global Continuity Statement</span>
        <span class="paper-note">Tier 8 continuity anchor</span>
      </a>

      <a class="paper" href="https://doi.org/10.5281/zenodo.19446738" target="_blank" rel="noopener noreferrer">
        <span class="paper-title">Tier 6 — Structural Admissibility Geometry</span>
        <span class="paper-note">Unified Tier 6 structural integration</span>
      </a>

      <a class="paper" href="https://doi.org/10.5281/zenodo.19446993" target="_blank" rel="noopener noreferrer">
        <span class="paper-title">Recursive Admissibility and System Correctness</span>
        <span class="paper-note">Tier 3 PAT ↔ Tier 5 recursion proof</span>
      </a>

      <a class="paper" href="https://doi.org/10.5281/zenodo.19463403" target="_blank" rel="noopener noreferrer">
        <span class="paper-title">Paton System — Canonical Boundary Diagram (Dual Representation)</span>
        <span class="paper-note">Tier 4 ↔ Tier 6 visual bridge</span>
      </a>

      <a class="paper" href="https://doi.org/10.5281/zenodo.19463907" target="_blank" rel="noopener noreferrer">
        <span class="paper-title">Fractals — Structure, Resonance, and Tier Transition</span>
        <span class="paper-note">Tier 4 visibility / fractal expression layer</span>
      </a>
    </div>
  </div>
</section>

<section>
  <div class="wrap">
    <div class="card">
      <p class="quote">
        The Paton System does not replace scientific theories.<br />
        It defines the condition under which systems can exist, be observed, and continue.
      </p>
    </div>
  </div>
</section>

<section id="links">
  <div class="wrap">
    <h2 class="section-title">Links</h2>

    <div class="links-grid">
      <div class="link-card">
        <div class="link-card-title">Zenodo</div>
        <p>Primary archive of published papers and DOI-linked records.</p>
        <a href="https://zenodo.org/" target="_blank" rel="noopener noreferrer">Open Zenodo</a>
      </div>

      <div class="link-card">
        <div class="link-card-title">PhilPapers</div>
        <p>Philosophy-facing publication index and profile record.</p>
        <a href="https://philpeople.org/profiles/andrew-john-paton/publications" target="_blank" rel="noopener noreferrer">Open publications</a>
      </div>

      <div class="link-card">
        <div class="link-card-title">Contact</div>
        <p>Direct feedback and correspondence.</p>
        <a href="mailto:feedback_patonsystem@protonmail.com">feedback_patonsystem@protonmail.com</a>
      </div>
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
    <div>Constraint-based structure of existence, observation, continuation, and continuity</div>
  </div>
</footer>

<script>
  document.addEventListener('DOMContentLoaded', function () {
    const groups = [
      document.querySelectorAll('.tier'),
      document.querySelectorAll('.tree-tier')
    ];

    groups.forEach((collection) => {
      collection.forEach((item) => {
        item.addEventListener('toggle', function () {
          if (this.open) {
            collection.forEach((other) => {
              if (other !== this) {
                other.open = false;
              }
            });
          }
        });
      });
    });
  });
</script>

</body>
</html>
