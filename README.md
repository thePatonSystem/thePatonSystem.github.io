<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="theme-color" content="#0b1020" />
  <title>The PATON System</title>
  <meta
    name="description"
    content="The PATON System — a structural framework for availability, distinction, relation, admissibility, observation, continuation, structural law, domain expression, and boundary limits."
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
      --teal: #74d7c4;
      --gold: #f2cc7d;
      --rose: #f2a5b9;
      --green: #9add9d;
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
        radial-gradient(circle at top right, rgba(116, 215, 196, 0.11), transparent 28%),
        linear-gradient(180deg, #0a0f1f 0%, #0b1020 55%, #0d1430 100%);
      line-height: 1.65;
    }

    img { max-width: 100%; height: auto; }
    a { color: var(--accent-2); text-decoration: none; }
    a:hover { color: #ffffff; }

    .wrap {
      width: min(100% - 32px, var(--max));
      margin: 0 auto;
    }

    .topbar {
      position: sticky;
      top: 0;
      z-index: 50;
      backdrop-filter: blur(14px);
      background: rgba(11, 16, 32, 0.82);
      border-bottom: 1px solid var(--line);
    }

    .topbar-inner {
      min-height: 68px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 18px;
    }

    .brand {
      color: #fff;
      font-weight: 800;
      letter-spacing: 0.055em;
      font-size: 0.95rem;
      white-space: nowrap;
    }

    .nav {
      display: flex;
      flex-wrap: wrap;
      justify-content: flex-end;
      gap: 14px;
    }

    .nav a {
      color: var(--muted);
      font-size: 0.9rem;
    }

    .nav a:hover { color: #fff; }

    .menu-button {
      display: none;
      min-width: 44px;
      min-height: 42px;
      border-radius: 12px;
      border: 1px solid var(--line);
      color: #fff;
      background: rgba(255,255,255,0.06);
      font: inherit;
      font-weight: 700;
      cursor: pointer;
    }

    .hero { padding: 84px 0 54px; }

    .hero-card {
      padding: 48px 34px 34px;
      border-radius: 32px;
      border: 1px solid var(--line);
      background: linear-gradient(180deg, rgba(255,255,255,0.075), rgba(255,255,255,0.038));
      box-shadow: var(--shadow);
    }

    .eyebrow {
      display: inline-block;
      margin-bottom: 20px;
      padding: 8px 12px;
      border-radius: 999px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.08);
      color: var(--muted);
      font-size: 0.84rem;
    }

    h1 {
      margin: 0 0 16px;
      font-size: clamp(2.35rem, 4vw, 4.4rem);
      line-height: 1.03;
      letter-spacing: -0.035em;
    }

    h2, h3, h4 { line-height: 1.25; }

    .subtitle {
      max-width: 900px;
      margin: 0;
      color: var(--muted);
      font-size: clamp(1.04rem, 1.8vw, 1.24rem);
    }

    .flow {
      margin-top: 28px;
      padding: 18px 20px;
      border-radius: 18px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.05);
      color: #fff;
      font-weight: 700;
      font-size: clamp(0.98rem, 2vw, 1.16rem);
      overflow-wrap: anywhere;
    }

    .actions {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      margin-top: 26px;
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
      font-weight: 700;
    }

    .btn.primary {
      background: linear-gradient(180deg, rgba(143,183,255,0.35), rgba(143,183,255,0.16));
      border-color: rgba(143,183,255,0.42);
    }

    section { padding: 26px 0 42px; scroll-margin-top: 88px; }

    .section-title {
      margin: 0 0 10px;
      font-size: clamp(1.75rem, 3vw, 2.2rem);
    }

    .section-intro {
      max-width: 900px;
      margin: 0 0 24px;
      color: var(--muted);
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(12, minmax(0, 1fr));
      gap: 18px;
    }

    .card {
      grid-column: span 12;
      padding: 24px;
      border-radius: var(--radius);
      border: 1px solid var(--line);
      background: var(--panel);
      box-shadow: var(--shadow);
    }

    .span-4 { grid-column: span 4; }
    .span-6 { grid-column: span 6; }
    .span-8 { grid-column: span 8; }

    .subhead {
      margin: 0 0 12px;
      color: #fff;
      font-size: 1.12rem;
    }

    .plain-copy p:first-child { margin-top: 0; }
    .plain-copy p:last-child { margin-bottom: 0; }
    .muted { color: var(--muted); }

    .callout {
      padding: 18px 20px;
      border-left: 4px solid var(--accent);
      border-radius: 14px;
      background: rgba(143,183,255,0.08);
      color: var(--accent-2);
    }

    .start-steps {
      display: grid;
      grid-template-columns: repeat(4, minmax(0, 1fr));
      gap: 14px;
      margin-top: 18px;
    }

    .step {
      padding: 18px;
      border-radius: 18px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.04);
    }

    .step-number {
      width: 34px;
      height: 34px;
      display: inline-grid;
      place-items: center;
      margin-bottom: 10px;
      border-radius: 50%;
      background: rgba(143,183,255,0.18);
      color: #fff;
      font-weight: 800;
    }

    .step strong { display: block; color: #fff; margin-bottom: 4px; }
    .step span { color: var(--muted); font-size: 0.94rem; }

    .spine-grid {
      display: grid;
      grid-template-columns: repeat(9, minmax(120px, 1fr));
      gap: 10px;
      overflow-x: auto;
      padding-bottom: 6px;
    }

    .spine-node {
      position: relative;
      min-height: 112px;
      padding: 16px 14px;
      border-radius: 16px;
      border: 1px solid rgba(255,255,255,0.12);
      background: rgba(255,255,255,0.045);
    }

    .spine-node:not(:last-child)::after {
      content: "→";
      position: absolute;
      top: 42%;
      right: -12px;
      z-index: 2;
      color: var(--accent);
      font-weight: 900;
    }

    .spine-node strong { display: block; color: #fff; margin-bottom: 6px; }
    .spine-node span { color: var(--muted); font-size: 0.88rem; }

    .tree-overview {
      display: grid;
      grid-template-columns: 1fr 1.4fr 1fr;
      gap: 16px;
      align-items: stretch;
    }

    .tree-column {
      padding: 20px;
      border-radius: 20px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.035);
    }

    .tree-column h3 { margin: 0 0 12px; color: #fff; }
    .tree-column ul { margin: 0; padding-left: 20px; color: var(--muted); }
    .tree-column li + li { margin-top: 7px; }

    .tree-trunk {
      border-color: rgba(143,183,255,0.35);
      background: linear-gradient(180deg, rgba(143,183,255,0.11), rgba(255,255,255,0.035));
    }

    .status-legend {
      display: grid;
      grid-template-columns: repeat(5, minmax(0, 1fr));
      gap: 10px;
      margin-top: 16px;
    }

    .status-item {
      padding: 14px;
      border-radius: 14px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.035);
    }

    .status-badge {
      display: inline-grid;
      place-items: center;
      width: 30px;
      height: 30px;
      margin-bottom: 8px;
      border-radius: 50%;
      color: #09101f;
      font-weight: 900;
    }

    .badge-f { background: var(--green); }
    .badge-d { background: var(--accent); }
    .badge-a { background: var(--gold); }
    .badge-o { background: var(--rose); }
    .badge-s { background: var(--teal); }

    details.tier,
    details.tree-tier,
    details.method-detail {
      overflow: hidden;
      border-radius: 16px;
      border: 1px solid rgba(255,255,255,0.08);
      background: rgba(255,255,255,0.04);
    }

    .tiers-stack { display: grid; gap: 12px; }

    details summary {
      list-style: none;
      cursor: pointer;
      padding: 16px 18px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 16px;
      color: #fff;
      font-weight: 800;
    }

    details summary::-webkit-details-marker { display: none; }

    .tier-label {
      display: block;
      margin-top: 2px;
      color: var(--muted);
      font-size: 0.94rem;
      font-weight: 500;
    }

    .tier-arrow {
      flex-shrink: 0;
      color: var(--muted);
      transition: transform 0.2s ease;
    }

    details[open] .tier-arrow { transform: rotate(90deg); }

    .tier-content {
      padding: 0 18px 18px;
      border-top: 1px solid rgba(255,255,255,0.08);
      color: var(--muted);
    }

    .tier-content p:last-child { margin-bottom: 0; }

    .logic-note,
    .meta-line {
      padding: 14px 16px;
      border-radius: 16px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.04);
      color: var(--muted);
      font-size: 0.95rem;
    }

    .logic-note { margin-top: 16px; }
    .tree-meta { display: grid; gap: 12px; margin-bottom: 18px; }

    .method-flow {
      display: grid;
      grid-template-columns: repeat(5, minmax(150px, 1fr));
      gap: 12px;
      overflow-x: auto;
      padding: 6px 2px 10px;
    }

    .method-stage {
      position: relative;
      min-height: 190px;
      padding: 18px;
      border-radius: 18px;
      border: 1px solid rgba(143,183,255,0.24);
      background: rgba(143,183,255,0.07);
    }

    .method-stage:not(:last-child)::after {
      content: "→";
      position: absolute;
      right: -13px;
      top: 44%;
      z-index: 2;
      color: var(--accent);
      font-weight: 900;
    }

    .method-stage .code {
      display: inline-block;
      margin-bottom: 10px;
      padding: 5px 9px;
      border-radius: 999px;
      background: rgba(255,255,255,0.08);
      color: #fff;
      font-size: 0.82rem;
      font-weight: 900;
      letter-spacing: 0.04em;
    }

    .method-stage strong { display: block; color: #fff; line-height: 1.3; }
    .method-stage p { margin: 10px 0 0; color: var(--muted); font-size: 0.92rem; }

    .method-output {
      margin-top: 14px;
      padding: 14px 16px;
      border-radius: 14px;
      border: 1px solid rgba(116,215,196,0.28);
      background: rgba(116,215,196,0.08);
      color: #e8fff9;
      font-weight: 700;
    }

    .tool-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 16px;
    }

    .tool-card {
      padding: 20px;
      border-radius: 19px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.04);
    }

    .tool-card h3 { margin: 0 0 8px; color: #fff; }
    .tool-card p { margin: 0 0 12px; color: var(--muted); }
    .mechanic-line { color: var(--accent-2); font-size: 0.9rem; font-weight: 700; }

    .support-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }

    .support-tag {
      padding: 9px 12px;
      border-radius: 999px;
      border: 1px solid rgba(116,215,196,0.22);
      background: rgba(116,215,196,0.07);
      color: #ddfff7;
      font-size: 0.9rem;
    }

    .figure-card {
      padding: 14px;
      border-radius: 22px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.04);
      box-shadow: var(--shadow);
    }

    .figure-card img {
      display: block;
      width: 100%;
      border-radius: 15px;
      background: #fff;
    }

    .figure-card figcaption {
      padding: 12px 8px 2px;
      color: var(--muted);
      font-size: 0.92rem;
    }

    .plain-page {
      max-width: 920px;
      padding: 28px;
      border-radius: 22px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.045);
      box-shadow: var(--shadow);
    }

    .plain-page h3 { margin-top: 0; color: #fff; }
    .plain-page h4 { margin-bottom: 6px; color: var(--accent-2); }
    .plain-page p { margin-top: 0; color: var(--muted); }

    .development-grid,
    .domain-grid,
    .validation-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 16px;
    }

    .branch-card,
    .validation-card {
      padding: 20px;
      border-radius: 18px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.04);
    }

    .branch-card h3,
    .validation-card h3 { margin: 0 0 8px; color: #fff; }
    .branch-card p,
    .validation-card p { margin: 0; color: var(--muted); }

    .mini-label {
      display: inline-block;
      margin-bottom: 10px;
      padding: 5px 9px;
      border-radius: 999px;
      background: rgba(255,255,255,0.08);
      color: var(--accent-2);
      font-size: 0.8rem;
      font-weight: 800;
    }

    .papers { display: grid; gap: 14px; }

    .paper {
      display: block;
      padding: 18px;
      border-radius: 18px;
      border: 1px solid var(--line);
      background: rgba(255,255,255,0.04);
    }

    .paper:hover { background: rgba(255,255,255,0.07); }

    .paper-title {
      display: block;
      margin-bottom: 4px;
      color: #fff;
      font-weight: 800;
    }

    .paper-note { color: var(--muted); font-size: 0.95rem; }

    .links-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 18px;
    }

    .link-card {
      padding: 24px;
      border-radius: var(--radius);
      border: 1px solid var(--line);
      background: var(--panel);
      box-shadow: var(--shadow);
    }

    .link-card-title {
      margin-bottom: 8px;
      color: #fff;
      font-size: 1.05rem;
      font-weight: 800;
    }

    .link-card p { margin: 0 0 10px; color: var(--muted); font-size: 0.95rem; }

    .quote {
      margin: 0;
      color: #fff;
      font-size: clamp(1.15rem, 2vw, 1.35rem);
    }

    .footer { padding: 28px 0 56px; color: var(--muted); }

    .footer-line {
      padding-top: 20px;
      border-top: 1px solid var(--line);
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 16px;
    }

    @media (max-width: 980px) {
      .span-4, .span-6, .span-8 { grid-column: span 12; }
      .start-steps { grid-template-columns: repeat(2, minmax(0, 1fr)); }
      .tree-overview { grid-template-columns: 1fr; }
      .status-legend { grid-template-columns: repeat(2, minmax(0, 1fr)); }
      .tool-grid,
      .development-grid,
      .domain-grid,
      .validation-grid,
      .links-grid { grid-template-columns: repeat(2, minmax(0, 1fr)); }
    }

    @media (max-width: 760px) {
      .topbar-inner { align-items: flex-start; padding: 12px 0; }
      .menu-button { display: inline-flex; align-items: center; justify-content: center; }
      .nav {
        display: none;
        position: absolute;
        top: 68px;
        left: 16px;
        right: 16px;
        padding: 14px;
        border-radius: 16px;
        border: 1px solid var(--line);
        background: rgba(11,16,32,0.97);
        box-shadow: var(--shadow);
      }
      .nav.open { display: grid; }
      .nav a { padding: 8px 4px; }
      .hero { padding-top: 56px; }
      .hero-card { padding: 34px 20px 24px; border-radius: 24px; }
      .start-steps,
      .tool-grid,
      .development-grid,
      .domain-grid,
      .validation-grid,
      .links-grid,
      .status-legend { grid-template-columns: 1fr; }
      .plain-page { padding: 22px 18px; }
      .footer-line { flex-direction: column; }
    }
  </style>
</head>

<body>

<header class="topbar">
  <div class="wrap topbar-inner">
    <div class="brand">THE PATON SYSTEM</div>

    <button class="menu-button" type="button" aria-expanded="false" aria-controls="main-navigation">
      Menu
    </button>

    <nav class="nav" id="main-navigation" aria-label="Primary navigation">
      <a href="#start-here">Start Here</a>
      <a href="#system-tree">System Tree</a>
      <a href="#architecture">Tiers</a>
      <a href="#methods">Methods</a>
      <a href="#sfm21">SFM 2.1</a>
      <a href="#domains">Domains</a>
      <a href="#validation">Validation</a>
      <a href="#papers">Papers</a>
      <a href="#links">Links</a>
    </nav>
  </div>
</header>

<main>

<section class="hero">
  <div class="wrap">
    <div class="hero-card">
      <div class="eyebrow">Continuation is not automatic</div>
      <h1>THE PATON SYSTEM</h1>
      <p class="subtitle">
        A structural framework for identifying what is available, what can be distinguished, what may relate, what is admissible, what can be observed, and what may continue under constraint.
      </p>

      <div class="flow">
        Availability → Distinction → Relation → Admissibility → Observation → Recursive Continuation → Structural Law → Domain Expression → Boundary Horizon
      </div>

      <div class="actions">
        <a class="btn primary" href="#start-here">Start here</a>
        <a class="btn" href="#system-tree">View the complete tree</a>
        <a class="btn" href="#methods">View methods and tools</a>
        <a class="btn" href="#papers">Read core papers</a>
      </div>
    </div>
  </div>
</section>

<section id="start-here">
  <div class="wrap">
    <h2 class="section-title">Start Here</h2>
    <p class="section-intro">
      The PATON System is easiest to understand by beginning with the whole structure rather than entering through one application branch. The system begins with the conditions required for structure to become distinguishable, relational, admissible, observable, and continuous.
    </p>

    <div class="grid">
      <div class="card span-8 plain-copy">
        <h3 class="subhead">What the PATON System does</h3>
        <p>
          The PATON System examines a system before optimisation, prediction, or explanation. It asks what must remain structurally available for the system to exist, what boundaries and relations are present, what constraints apply, and whether continuation is still viable.
        </p>
        <p>
          It does not replace physics, biology, cognitive science, engineering, economics, or other domain theories. It provides a structural way to compare persistence, breakdown, recovery, scale handover, and admissibility across them without claiming that the domains are identical.
        </p>
        <div class="callout">
          The central principle is simple: a system does not continue merely because a next state can be imagined. The next state must remain admissible and reachable from the current one.
        </div>
      </div>

      <div class="card span-4">
        <h3 class="subhead">Author</h3>
        <p style="margin:0; color:#fff; font-weight:800;">Andrew John Paton</p>
        <p class="muted" style="margin:4px 0 0;">
          Founder and Principal Architect — The PATON System<br />
          Independent Researcher, Australia
        </p>
      </div>
    </div>

    <div class="start-steps">
      <div class="step">
        <div class="step-number">1</div>
        <strong>See the complete tree</strong>
        <span>Understand the root, tier spine, methods, laws, applications, and boundary controls.</span>
      </div>
      <div class="step">
        <div class="step-number">2</div>
        <strong>Read the tier architecture</strong>
        <span>Follow the structural order from availability through the Tier 8 stopping boundary.</span>
      </div>
      <div class="step">
        <div class="step-number">3</div>
        <strong>Open the methods</strong>
        <span>See SFM 2.0, its five internal stages, and the standalone PATON tools.</span>
      </div>
      <div class="step">
        <div class="step-number">4</div>
        <strong>Enter a domain branch</strong>
        <span>Move into physics, cognition, AI, care, engineering, governance, finance, or validation.</span>
      </div>
    </div>
  </div>
</section>

<section id="framework">
  <div class="wrap">
    <h2 class="section-title">The Central Structural Spine</h2>
    <p class="section-intro">
      The spine gives the order of dependency. Later stages depend on earlier structural conditions; they are not interchangeable labels.
    </p>

    <div class="card">
      <div class="spine-grid" aria-label="PATON System central structural spine">
        <div class="spine-node"><strong>Availability</strong><span>There must first be something structurally available to distinguish.</span></div>
        <div class="spine-node"><strong>Distinction</strong><span>A difference or boundary makes separate reference possible.</span></div>
        <div class="spine-node"><strong>Relation</strong><span>Distinguished elements may enter candidate relations.</span></div>
        <div class="spine-node"><strong>Admissibility</strong><span>Constraints determine which relations may persist or continue.</span></div>
        <div class="spine-node"><strong>Observation</strong><span>Only an admissible interface becomes available as a datum.</span></div>
        <div class="spine-node"><strong>Recursive Continuation</strong><span>Persistence must be renewed across sequential states.</span></div>
        <div class="spine-node"><strong>Structural Law</strong><span>Repeated admissible behaviour forms cross-system structural rules.</span></div>
        <div class="spine-node"><strong>Domain Expression</strong><span>The structure is instantiated within specific fields and systems.</span></div>
        <div class="spine-node"><strong>Boundary Horizon</strong><span>Responsible description stops where admissible continuation or evidence ends.</span></div>
      </div>

      <div class="logic-note">
        <strong style="color:#fff;">Plain-language sequence:</strong>
        something must be available before it can be distinguished; distinction allows relation; relation is filtered by constraint; admissible structure becomes observable; continuation must then be renewed rather than assumed.
      </div>
    </div>
  </div>
</section>

<section id="system-tree">
  <div class="wrap">
    <h2 class="section-title">The Complete PATON System Tree</h2>
    <p class="section-intro">
      The tree shows where the foundational architecture, full methods, structural laws, domain applications, verification procedures, and open development work belong in relation to one another.
    </p>

    <div class="tree-overview">
      <div class="tree-column">
        <h3>Roots and foundations</h3>
        <ul>
          <li>Original Datum and availability</li>
          <li>Distinction and boundary formation</li>
          <li>Relational possibility</li>
          <li>Boundary–Relation–Persistence</li>
          <li>Reachability and admissibility</li>
          <li>Unified Datum Line</li>
          <li>PATON Viability Principle</li>
          <li>Minimal formal core</li>
        </ul>
      </div>

      <div class="tree-column tree-trunk">
        <h3>Trunk and working mechanics</h3>
        <ul>
          <li>Tier 0 → Tier 8 structural spine</li>
          <li>SFM 2.0 umbrella method</li>
          <li>PFA → PLM → AIT → RCG ↔ LCTM</li>
          <li>PATON Assist and viability certification</li>
          <li>PATON Compass and LiDAR PATON Compass</li>
          <li>PATON Admissibility Lens</li>
          <li>Structural mapping and independent testing</li>
          <li>Recursive continuation, closure, compression, and scale handover</li>
        </ul>
      </div>

      <div class="tree-column">
        <h3>Branches and horizon</h3>
        <ul>
          <li>Philosophy of science</li>
          <li>Physics and cosmology</li>
          <li>Cognitive systems</li>
          <li>AI and computation</li>
          <li>Engineering and instrumentation</li>
          <li>Biology, care, and accessibility</li>
          <li>Organisations, governance, and society</li>
          <li>Finance and economics</li>
          <li>Validation, audit, and communication</li>
          <li>Tier 8 stopping and scope boundary</li>
        </ul>
      </div>
    </div>

    <div class="card" style="margin-top:18px;">
      <h3 class="subhead">Structural placement is not the same as evidentiary maturity</h3>
      <p class="muted">
        The tree can show a branch in its correct structural position without claiming that every branch has the same level of formalisation, testing, physical correspondence, or independent replication.
      </p>

      <div class="status-legend">
        <div class="status-item"><span class="status-badge badge-f">F</span><strong style="display:block;color:#fff;">Formally worked</strong><span class="muted">Explicit rules, equations, or worked constructions are present.</span></div>
        <div class="status-item"><span class="status-badge badge-d">D</span><strong style="display:block;color:#fff;">Developed architecture</strong><span class="muted">The structure is defined and internally organised.</span></div>
        <div class="status-item"><span class="status-badge badge-a">A</span><strong style="display:block;color:#fff;">Applied or conceptual</strong><span class="muted">The framework is being used to interpret a domain or problem.</span></div>
        <div class="status-item"><span class="status-badge badge-o">O</span><strong style="display:block;color:#fff;">Open or prospective</strong><span class="muted">Interfaces, physical mappings, or validation work remain open.</span></div>
        <div class="status-item"><span class="status-badge badge-s">S</span><strong style="display:block;color:#fff;">Support or scope control</strong><span class="muted">The item clarifies use, testing, boundaries, or non-claims.</span></div>
      </div>
    </div>
  </div>
</section>

<section id="architecture">
  <div class="wrap">
    <h2 class="section-title">Tier 0–8 Architecture</h2>
    <p class="section-intro">
      Open each tier for its present whole-system meaning. The tier structure is the vertical spine; methods and domains are placed within it rather than replacing it.
    </p>

    <div class="card">
      <div class="tiers-stack">

        <details class="tier">
          <summary>
            <div>Tier 0 <span class="tier-label">Availability / Original Datum</span></div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            <p>Undivided availability: the condition from which distinguishable structure may emerge. Tier 0 does not yet contain a formed object, metric, or domain-specific entity.</p>
          </div>
        </details>

        <details class="tier">
          <summary>
            <div>Tier 1 <span class="tier-label">Distinction / Boundary</span></div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            <p>The first separation. A boundary allows one condition, region, or datum to be distinguished from another.</p>
          </div>
        </details>

        <details class="tier">
          <summary>
            <div>Tier 2 <span class="tier-label">Relational Possibility</span></div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            <p>Candidate relations, mappings, symmetries, and formations become possible. Possibility alone does not guarantee physical existence or continued viability.</p>
          </div>
        </details>

        <details class="tier">
          <summary>
            <div>Tier 3 <span class="tier-label">Admissibility / BRP / Reachability</span></div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            <p>The governing gate. Boundary, Relation, Persistence, constraint, and reachability determine which candidate structures may be admitted.</p>
          </div>
        </details>

        <details class="tier">
          <summary>
            <div>Tier 4 <span class="tier-label">Datum / Observation / Knowledge Interface</span></div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            <p>Admissible structure becomes available through an observational or knowledge interface. Observation reveals a constrained datum, not the whole of all possible structure.</p>
          </div>
        </details>

        <details class="tier">
          <summary>
            <div>Tier 5 <span class="tier-label">Recursive Continuation / Generative Machinery</span></div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            <p>Continuation is renewed across successive states. This tier contains recurrence, memory, recursive generation, historical dependence, and continuation gates.</p>
          </div>
        </details>

        <details class="tier">
          <summary>
            <div>Tier 6 <span class="tier-label">Structural Laws / Constraint Geometry</span></div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            <p>Persistent cross-system behaviours are expressed as structural laws, corridors, closures, tolerances, trajectories, limits, reciprocal constraints, and scale-handover rules.</p>
          </div>
        </details>

        <details class="tier">
          <summary>
            <div>Tier 7 <span class="tier-label">Domain Instantiation</span></div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            <p>The framework is applied within specific domains. Each application must retain the domain’s own evidence, definitions, and validation requirements.</p>
          </div>
        </details>

        <details class="tier">
          <summary>
            <div>Tier 8 <span class="tier-label">Boundary Horizon / Responsible Stopping Condition</span></div>
            <span class="tier-arrow">▶</span>
          </summary>
          <div class="tier-content">
            <p>The point beyond which responsible continuation, refinement, inference, or description must stop. Tier 8 is a boundary control, not permission to invent what lies beyond the evidence or admissible structure.</p>
          </div>
        </details>

      </div>

      <div class="logic-note">
        <strong style="color:#fff;">Architecture rule:</strong>
        lower tiers provide preconditions for higher tiers. A domain application may be sophisticated while still depending on unresolved earlier interfaces.
      </div>
    </div>
  </div>
</section>

<section id="methods">
  <div class="wrap">
    <h2 class="section-title">Full Methods and Standalone Tools</h2>
    <p class="section-intro">
      The PATON System contains one complete umbrella method, five internal SFM stages, six main standalone methods or instruments, and a set of supporting gates and components.
    </p>

    <div class="card">
      <h3 class="subhead">SFM 2.0 — the full umbrella method</h3>
      <p class="muted">
        The Structural Fingerprint Method reduces a complex system to the smallest structure needed to show what recurs, what is locked, what relations are admissible, where continuity may move, and which route was actually taken.
      </p>

      <div class="method-flow">
        <div class="method-stage">
          <span class="code">PFA</span>
          <strong>Persistence Fingerprint Analysis</strong>
          <p>Finds recurring features, relations, behaviours, or constraints that may be carrying continuity.</p>
        </div>
        <div class="method-stage">
          <span class="code">PLM</span>
          <strong>Persistence Locking Mechanism</strong>
          <p>Tests what is genuinely retained and separates the locked structural core from temporary features.</p>
        </div>
        <div class="method-stage">
          <span class="code">AIT</span>
          <strong>Admissibility Interrogation Topology</strong>
          <p>Examines candidate relations and separates admitted, rejected, blocked, unresolved, and unreachable pathways.</p>
        </div>
        <div class="method-stage">
          <span class="code">RCG</span>
          <strong>Recursive Continuity Geometry</strong>
          <p>Maps active paths, branching, closure, failure regions, recovery routes, and scale transitions.</p>
        </div>
        <div class="method-stage">
          <span class="code">LCTM</span>
          <strong>Lineal Continuity Traversal Mathematics</strong>
          <p>Records the actual ordered route through the mapped continuity field, including passes, failures, stops, and re-entry.</p>
        </div>
      </div>

      <div class="method-output">Output: a structural fingerprint together with a traceable continuity account.</div>
    </div>

    <div class="tool-grid" style="margin-top:18px;">
      <article class="tool-card">
        <h3>PATON Assist</h3>
        <p>Evaluates whether a system remains viable without taking control of it. It checks BRP, remaining tolerance, current load, historical strain, viability debt, and boundary proximity.</p>
        <div class="mechanic-line">Current datum → BRP check → viability margin → viability debt → Assist Index → viability certificate</div>
      </article>

      <article class="tool-card">
        <h3>PATON Compass</h3>
        <p>Identifies the most admissible direction from the present datum. It orients before optimisation and may recommend movement, re-entry, holding position, more information, or stopping.</p>
        <div class="mechanic-line">Current datum → objective → constraint field → frontier gate → admissible direction</div>
      </article>

      <article class="tool-card">
        <h3>LiDAR PATON Compass</h3>
        <p>Uses small probes and observable return patterns to map an admissible direction when communication, movement, processing, or explanation capacity is limited.</p>
        <div class="mechanic-line">Small probe → return signal → repeated pattern → admissible envelope → low-burden orientation</div>
      </article>

      <article class="tool-card">
        <h3>PATON Admissibility Lens</h3>
        <p>Evaluates a claim, model, system, or proposed action through boundary, relation, persistence, reachability, breakdown, evidence, and scope.</p>
        <div class="mechanic-line">Claim or system → BRP → reachability → breakdown → scope → admissibility result</div>
      </article>

      <article class="tool-card">
        <h3>PATON Structural Mapping Tool</h3>
        <p>Builds a visible map of the active datum, boundaries, candidate relations, admitted and rejected paths, corridors, closures, failures, re-entry routes, and scale handovers.</p>
        <div class="mechanic-line">Datum → boundary → relations → constraints → corridors → closure → re-entry / handover map</div>
      </article>

      <article class="tool-card">
        <h3>PATON Independent Test Kit</h3>
        <p>Allows another person to reproduce, challenge, compare, or falsify a PATON construction using declared inputs, rules, expected results, failure cases, and thresholds.</p>
        <div class="mechanic-line">Declared input → rule → expected passes and rejections → failure cases → reproducible verdict</div>
      </article>
    </div>

    <div class="card" style="margin-top:18px;">
      <h3 class="subhead">Supporting components — not separate full methods</h3>
      <p class="muted">These components perform specific jobs inside the methods, instruments, or validation process.</p>
      <div class="support-tags">
        <span class="support-tag">BRP Gate</span>
        <span class="support-tag">PATON Viability Principle</span>
        <span class="support-tag">Admissibility Gate</span>
        <span class="support-tag">Reachability Gate</span>
        <span class="support-tag">Structural Honesty Gate</span>
        <span class="support-tag">Constraint Corridor</span>
        <span class="support-tag">Tier 8 Boundary Gate</span>
        <span class="support-tag">PATON Assist Index</span>
        <span class="support-tag">PATON-BRP Interface Certificate</span>
        <span class="support-tag">PFL-X Symbolic Language</span>
        <span class="support-tag">Mass–Size–State Gate</span>
        <span class="support-tag">Detector and Reconstruction Overlays</span>
      </div>
    </div>

    <figure class="figure-card" style="margin:18px 0 0;">
      <img
        src="assets/paton-methods-mechanics.png"
        alt="Infographic showing SFM 2.0, the five internal method stages, six standalone PATON tools, and supporting components"
        loading="lazy"
      />
      <figcaption>
        Mechanics of the PATON methods. The image file must remain in <strong>assets/paton-methods-mechanics.png</strong> beside this page.
      </figcaption>
    </figure>
  </div>
</section>

<section id="plain-english">
  <div class="wrap">
    <h2 class="section-title">Plain-English Companion to the Methods Image</h2>
    <p class="section-intro">
      This section explains the mechanics image without requiring the reader to know the abbreviations first.
    </p>

    <article class="plain-page">
      <h3>How the PATON methods work</h3>
      <p>
        The PATON System uses one main structural method, supported by several standalone tools and a smaller set of gates and components. Its purpose is to take a complex system, identify what is holding it together, show where continuity is possible, and determine whether the system can responsibly continue.
      </p>

      <h4>1. The main method — SFM 2.0</h4>
      <p>
        The Structural Fingerprint Method is the umbrella method. PFA first looks for features and relations that keep recurring. PLM then tests which of those features are genuinely necessary and remain locked into the system. AIT examines the possible relations and pathways around that locked core and separates what is admitted, rejected, blocked, unresolved, or unreachable. RCG maps the wider shape of continuity, including branches, closures, failure regions, recovery routes, and changes of scale. LCTM finally records the actual route taken through that map.
      </p>
      <p>
        Together, these five stages produce a structural fingerprint and a traceable account of how continuity operates within the system.
      </p>

      <h4>2. The standalone methods and tools</h4>
      <p>
        PATON Assist checks whether a system remains viable and records remaining tolerance, current strain, viability debt, and proximity to failure. The PATON Compass identifies the most admissible direction from the present position. The LiDAR PATON Compass uses small probes and observable responses when full communication or processing is difficult. The PATON Admissibility Lens checks whether a claim, model, system, or proposed action stays within its evidence, scope, and breakdown limits. The PATON Structural Mapping Tool converts the structure into a visible map. The PATON Independent Test Kit allows another person to reproduce, challenge, or falsify the construction.
      </p>

      <h4>3. The supporting components</h4>
      <p>
        The remaining items are not separate full methods. They perform specific jobs inside the methods and tools. These include the BRP Gate, the PATON Viability Principle, admissibility and reachability gates, the Structural Honesty Gate, the Constraint Corridor, the Tier 8 Boundary Gate, certificates, indexes, symbolic language, physical gates, and detector or reconstruction overlays.
      </p>

      <h4>The overall logic</h4>
      <p>
        SFM reveals what the system is doing. The standalone tools help determine what can be done with that understanding. The supporting components prevent the methods from being used beyond what the structure, evidence, and declared boundaries allow.
      </p>
    </article>
  </div>
</section>

<section id="sfm21">
  <div class="wrap">
    <h2 class="section-title">SFM 2.1 — Current Development Architecture</h2>
    <p class="section-intro">
      SFM 2.1 extends the structural method into pre-metric relational proposal, worked admission and rejection, recursive compression, renewed expansion, and open physical-interface testing. It is presented as a development architecture, not as a completed physical theory.
    </p>

    <div class="development-grid">
      <article class="branch-card">
        <span class="mini-label">Developed architecture</span>
        <h3>Pre-Planck Structural Proposal</h3>
        <p>Moves from the Original Datum and Unified Datum Line through pre-metric relational proposal toward, but not automatically across, the Tier 3 admissibility gate.</p>
      </article>

      <article class="branch-card">
        <span class="mini-label">Formally worked core</span>
        <h3>Five-Datum Admission Example</h3>
        <p>Demonstrates candidate relations, admitted and rejected pairs, persistence, ordering, separation, uniformity, controlled failures, and a declared hierarchical certificate.</p>
      </article>

      <article class="branch-card">
        <span class="mini-label">Scale architecture</span>
        <h3>Many–One–Many</h3>
        <p>Shows how multiple lower-scale relations may close into one next-scale datum, which then becomes the basis for fresh relational expansion at the new scale.</p>
      </article>

      <article class="branch-card">
        <span class="mini-label">Verification</span>
        <h3>Computational Testing</h3>
        <p>Checks admission, rejection, recurrence, locking, traversal order, failure cases, thresholds, and reproducibility rather than relying only on verbal interpretation.</p>
      </article>

      <article class="branch-card">
        <span class="mini-label">Open interface</span>
        <h3>Relational-to-Refinement Mapping</h3>
        <p>The map from relational structure to a defined refinement structure remains an explicit interface requiring further definition and testing.</p>
      </article>

      <article class="branch-card">
        <span class="mini-label">Open interface</span>
        <h3>Physical Observable Mapping</h3>
        <p>Physical encoding, Lorentzian signature, dimensional correspondence, and GR, QM, or QFT mapping remain open until independently defined and validated.</p>
      </article>
    </div>

    <div class="logic-note">
      <strong style="color:#fff;">Development distinction:</strong>
      SFM 2.0 is the current complete umbrella method. SFM 2.1 is the active extension architecture containing worked structural advances together with declared open interfaces.
    </div>
  </div>
</section>

<section id="domains">
  <div class="wrap">
    <h2 class="section-title">Major Domain Branches</h2>
    <p class="section-intro">
      Domain branches use the common structural spine while retaining their own evidence, terminology, measurements, and validation standards.
    </p>

    <div class="domain-grid">
      <article class="branch-card"><h3>Philosophy of Science</h3><p>Admissibility before truth-claims, model validity before breakdown, boundary knowledge, ontology discipline, structural placement, and responsible non-claim.</p></article>
      <article class="branch-card"><h3>Physics and Cosmology</h3><p>Constraint geometry, physical-scale closure, reciprocal constraint closure, mass–size–state gating, signal structure, CMB formation, confinement, matter handover, and cosmological applications.</p></article>
      <article class="branch-card"><h3>Cognitive Systems</h3><p>Recursive traversal, cognitive transduction, environmental load, accommodation overhead, interruption, re-entry, alarm override, memory-line weakening, and continuity empathy.</p></article>
      <article class="branch-card"><h3>AI and Computation</h3><p>Admissible recursion, memory, structural persistence, governance separation, model progression, verification, architecture comparison, and boundary-aware system design.</p></article>
      <article class="branch-card"><h3>Engineering and Instrumentation</h3><p>Detector architectures, reconstruction overlays, LiDAR orientation, tolerance monitoring, weakest-axis diagnosis, path mapping, and viability-aware instrumentation.</p></article>
      <article class="branch-card"><h3>Biology, Care, and Accessibility</h3><p>Continuity under variable capacity, low-burden communication, local stabilisation islands, dementia and care support, routine preservation, and re-entry-oriented assistance.</p></article>
      <article class="branch-card"><h3>Organisations, Governance, and Society</h3><p>Institutional continuity, cohesion, role and boundary clarity, governance constraints, decision admissibility, responsibility, communication, and social-system breakdown.</p></article>
      <article class="branch-card"><h3>Finance and Economics</h3><p>Viability debt, tolerance envelopes, constraint propagation, recursive instability, decision corridors, systemic exposure, and continuity under accumulated load.</p></article>
      <article class="branch-card"><h3>Validation, Audit, and Communication</h3><p>Independent replication, falsification, regression testing, threshold sensitivity, maturity labelling, diagrams, plain-language companions, and publication indexing.</p></article>
    </div>
  </div>
</section>

<section id="validation">
  <div class="wrap">
    <h2 class="section-title">Validation, Audit, and Boundaries</h2>
    <p class="section-intro">
      The PATON System separates internal structural work from physical correspondence, external replication, domain validation, and public explanatory material.
    </p>

    <div class="validation-grid">
      <article class="validation-card">
        <h3>Reproducibility</h3>
        <p>Inputs, rules, thresholds, admitted and rejected cases, expected outputs, and failure conditions should be stated clearly enough for another person to reproduce the result.</p>
      </article>

      <article class="validation-card">
        <h3>Falsification</h3>
        <p>A method must state what outcome would show that its claimed lock, traversal, viability certificate, or structural mapping is wrong.</p>
      </article>

      <article class="validation-card">
        <h3>Physical Validation Register</h3>
        <p>Formal structures with established physical correspondence must be distinguished from proposed mappings, conceptual analogies, and currently open interfaces.</p>
      </article>

      <article class="validation-card">
        <h3>Threshold Sensitivity</h3>
        <p>Results should be tested against changes in admissibility, persistence, tolerance, or viability thresholds rather than treated as independent of their chosen settings.</p>
      </article>

      <article class="validation-card">
        <h3>Structural Honesty</h3>
        <p>Claims must stop where the evidence, mapping, declared scope, or admissible continuation stops. A complete tree is not a claim of complete proof.</p>
      </article>

      <article class="validation-card">
        <h3>Independent Replication</h3>
        <p>External researchers should be able to reproduce, challenge, compare, or reject a construction without depending on the original author’s private interpretation.</p>
      </article>
    </div>
  </div>
</section>

<section id="papers">
  <div class="wrap">
    <h2 class="section-title">Core Papers and Current Reference Works</h2>
    <p class="section-intro">
      Verified DOI links from the existing website are retained below. Newer structural papers and internal reference works can be linked as their final public records are confirmed.
    </p>

    <div class="card" style="margin-bottom:18px;">
      <h3 class="subhead">Core entry papers</h3>
      <div class="papers">
        <a class="paper" href="https://doi.org/10.5281/zenodo.19695588" target="_blank" rel="noopener noreferrer">
          <span class="paper-title">PATON System — Cognitive Clarifications: Master Index (Series I–IV)</span>
          <span class="paper-note">Interpretive entry point for admissibility, observation, continuation, collapse, stability, and decision.</span>
        </a>

        <a class="paper" href="https://doi.org/10.5281/zenodo.19693759" target="_blank" rel="noopener noreferrer">
          <span class="paper-title">The PATON System — Canonical Equations I–X</span>
          <span class="paper-note">Earlier canonical equation spine retained as a core publication record.</span>
        </a>
      </div>
    </div>

    <div class="papers">
      <a class="paper" href="https://doi.org/10.5281/zenodo.19447197" target="_blank" rel="noopener noreferrer">
        <span class="paper-title">The PATON System — Unified Life Structure</span>
        <span class="paper-note">Unified architecture across Tier 0 → Tier 8.</span>
      </a>

      <a class="paper" href="https://doi.org/10.5281/zenodo.19463366" target="_blank" rel="noopener noreferrer">
        <span class="paper-title">The PATON System — Global Continuity Statement</span>
        <span class="paper-note">Tier 8 continuity anchor.</span>
      </a>

      <a class="paper" href="https://doi.org/10.5281/zenodo.19446738" target="_blank" rel="noopener noreferrer">
        <span class="paper-title">Tier 6 — Structural Admissibility Geometry</span>
        <span class="paper-note">Unified Tier 6 structural integration.</span>
      </a>

      <a class="paper" href="https://doi.org/10.5281/zenodo.19446993" target="_blank" rel="noopener noreferrer">
        <span class="paper-title">Recursive Admissibility and System Correctness</span>
        <span class="paper-note">Tier 3 admissibility connected to Tier 5 recursion.</span>
      </a>

      <a class="paper" href="https://doi.org/10.5281/zenodo.19463403" target="_blank" rel="noopener noreferrer">
        <span class="paper-title">PATON System — Canonical Boundary Diagram (Dual Representation)</span>
        <span class="paper-note">Tier 4 ↔ Tier 6 visual bridge.</span>
      </a>

      <a class="paper" href="https://doi.org/10.5281/zenodo.19463907" target="_blank" rel="noopener noreferrer">
        <span class="paper-title">Fractals — Structure, Resonance, and Tier Transition</span>
        <span class="paper-note">Tier 4 visibility and fractal expression layer.</span>
      </a>
    </div>

    <div class="card" style="margin-top:18px;">
      <h3 class="subhead">Current structural reference set</h3>
      <div class="papers">
        <div class="paper">
          <span class="paper-title">The PATON System — Full Methods and Standalone Tools</span>
          <span class="paper-note">Internal reference paper covering SFM 2.0, its internal mechanics, standalone tools, supporting components, and combined workflow.</span>
        </div>
        <div class="paper">
          <span class="paper-title">PATON System Canonical Structural Tree</span>
          <span class="paper-note">Whole-system placement of foundations, methods, laws, domains, validation, communication, SFM 2.1, and Tier 8 scope control.</span>
        </div>
        <div class="paper">
          <span class="paper-title">SFM 2.1 Pre-Planck Structural Proposal</span>
          <span class="paper-note">Pre-metric relational proposal, worked admission construction, controlled failures, and declared open physical interfaces.</span>
        </div>
        <div class="paper">
          <span class="paper-title">Recursive Compression and Renewed Expansion Across Scale — The Many–One–Many Scale Architecture</span>
          <span class="paper-note">Consolidates closure, compression, new-datum formation, renewed expansion, inherited continuity, and non-unique prehistory.</span>
        </div>
      </div>
    </div>
  </div>
</section>

<section>
  <div class="wrap">
    <div class="card">
      <p class="quote">
        The PATON System does not replace domain-specific scientific theories. It identifies the structural conditions under which a system, model, observation, or proposed continuation remains admissible.
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
        <p>Primary archive for published papers and DOI-linked records.</p>
        <a href="https://zenodo.org/" target="_blank" rel="noopener noreferrer">Open Zenodo</a>
      </div>

      <div class="link-card">
        <div class="link-card-title">PhilPeople / PhilPapers</div>
        <p>Philosophy-facing profile and publication index.</p>
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
      © Andrew John Paton — The PATON System<br />
      Founder and Principal Architect — The PATON System<br />
      Independent Researcher, Australia<br />
      <a href="mailto:feedback_patonsystem@protonmail.com">feedback_patonsystem@protonmail.com</a>
    </div>
    <div>Constraint before continuation</div>
  </div>
</footer>

<script>
  document.addEventListener('DOMContentLoaded', function () {
    const menuButton = document.querySelector('.menu-button');
    const nav = document.querySelector('.nav');

    if (menuButton && nav) {
      menuButton.addEventListener('click', function () {
        const isOpen = nav.classList.toggle('open');
        menuButton.setAttribute('aria-expanded', String(isOpen));
      });

      nav.querySelectorAll('a').forEach(function (link) {
        link.addEventListener('click', function () {
          nav.classList.remove('open');
          menuButton.setAttribute('aria-expanded', 'false');
        });
      });
    }

    const groups = [
      document.querySelectorAll('.tier'),
      document.querySelectorAll('.tree-tier'),
      document.querySelectorAll('.method-detail')
    ];

    groups.forEach(function (collection) {
      collection.forEach(function (item) {
        item.addEventListener('toggle', function () {
          if (this.open) {
            collection.forEach(function (other) {
              if (other !== item) {
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

