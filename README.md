<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
  <meta charset="utf-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge"/>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>SpotlixHQ – Creators, Thinkers, Collaborators</title>

  <!-- Basic SEO -->
  <meta name="description" content="SpotlixHQ (Spotlight Squad) — a vibrant creator community for collaboration, content and growth. Connect via Instagram, Telegram, YouTube or Email." />
  <meta name="keywords" content="SpotlixHQ, Spotlight Squad, creators community, collaboration, Instagram, Telegram, YouTube" />
  <meta name="theme-color" content="#0f0c29" />

  <!-- Open Graph -->
  <meta property="og:title" content="SpotlixHQ – Creators, Thinkers, Collaborators" />
  <meta property="og:description" content="SpotlixHQ (Spotlight Squad) — a vibrant creator community for collaboration and growth." />
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://spotlixhq.com/" />
  <meta property="og:image" content="https://spotlixhq.com/og-image.png" />
  <meta property="og:locale" content="en_US" />

  <!-- Twitter -->
  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:title" content="SpotlixHQ – Creators, Thinkers, Collaborators" />
  <meta name="twitter:description" content="SpotlixHQ (Spotlight Squad) — a vibrant creator community for collaboration and growth." />
  <meta name="twitter:image" content="https://spotlixhq.com/og-image.png" />

  <!-- Structured Data -->
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "Organization",
    "name": "SpotlixHQ",
    "alternateName": "Spotlight Squad",
    "url": "https://spotlixhq.com",
    "logo": "https://spotlixhq.com/og-image.png",
    "sameAs": [
      "https://www.instagram.com/spotlixhq",
      "https://t.me/SpotlixHQ",
      "https://www.youtube.com/@SpotlixHQ",
      "https://x.com/SpotlixHQ",
      "https://www.linkedin.com/company/spotlixhq"
    ],
    "description": "SpotlixHQ (Spotlight Squad) is a community for creators, thinkers, and innovators to collaborate, share ideas, and grow together."
  }
  </script>

  <!-- Fonts & icons -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&family=Playfair+Display:wght@500;700&display=swap" rel="stylesheet">
  <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous" defer></script>

  <!-- CRITICAL STYLES (inline for fast FCP) -->
  <style>
    /* ---------- Root variables (themeable) ---------- */
    :root{
      --bg-1: #08040a;
      --bg-2: #1b1830;
      --glass: rgba(255,255,255,0.04);
      --glass-2: rgba(255,255,255,0.02);
      --accent: #00fff7;
      --accent-2: #ff00ff;
      --muted: rgba(255,255,255,0.85);
      --card: rgba(7,7,8,0.45);
      --radius: 16px;
      --max-width: 1200px;
      --ease: cubic-bezier(.16,.84,.3,1);
      --text: #ffffff;
      --shadow-neon: 0 6px 40px rgba(0,255,247,0.06);
      --glass-border: rgba(255,255,255,0.06);
      --glass-blur: 10px;
      --tt-1: 'Playfair Display', serif;
      --tt-2: 'Poppins', system-ui, sans-serif;
    }

    /* Dark / light auto theme (prefers) */
    @media (prefers-color-scheme: light){
      :root{
        --bg-1: #f7fbff;
        --bg-2: #e6f2ff;
        --card: rgba(255,255,255,0.65);
        --text: #07101a;
        --glass: rgba(0,0,0,0.03);
        --glass-border: rgba(0,0,0,0.05);
        --shadow-neon: 0 6px 40px rgba(0,0,0,0.06);
      }
    }

    /* Reduced motion */
    @media (prefers-reduced-motion: reduce){
      *{animation-duration:0.001ms !important; transition:none !important}
    }

    /* ---------- Reset ---------- */
    *, *::before, *::after { box-sizing: border-box; -webkit-font-smoothing:antialiased; -moz-osx-font-smoothing:grayscale; }
    html, body { height: 100%; }
    body{
      margin:0;
      font-family: var(--tt-2);
      color: var(--text);
      background: linear-gradient(135deg, var(--bg-1) 0%, var(--bg-2) 100%);
      min-height:100vh;
      overflow-x:hidden;
      line-height:1.45;
    }

    /* ---------- layout helpers ---------- */
    .wrap { width:100%; max-width:var(--max-width); margin:0 auto; padding: 0 20px; }
    .flex { display:flex; gap:12px; align-items:center; }
    .stack { display:flex; flex-direction:column; gap:12px; }

    /* ---------- loader (custom) ---------- */
    .preloader {
      position: fixed; inset: 0; display:flex; align-items:center; justify-content:center;
      background: linear-gradient(180deg, rgba(0,0,0,0.85), rgba(0,0,0,0.95));
      z-index: 99999;
    }
    .loader-wrap { display:flex; gap:18px; align-items:center; flex-direction:column; }
    .loader-brand { display:flex; gap:8px; align-items:center; }
    .loader-dot { width:18px; height:18px; border-radius:50%; background:linear-gradient(90deg,var(--accent),var(--accent-2)); box-shadow: 0 6px 24px rgba(0,255,247,0.12); animation: loaderPop 900ms var(--ease) infinite; }
    .loader-dot:nth-child(2){ animation-delay:120ms }
    .loader-dot:nth-child(3){ animation-delay:240ms }
    .loader-caption { margin-top:8px; color:var(--muted); font-weight:600; }
    @keyframes loaderPop {
      0%{ transform: translateY(0) scale(.9); opacity:.6 }
      50%{ transform: translateY(-8px) scale(1.15); opacity:1 }
      100%{ transform: translateY(0) scale(.95); opacity:.8 }
    }

    /* ---------- header / navbar ---------- */
    header {
      position: fixed; top: 18px; left: 0; right:0; z-index: 80; display:flex; justify-content:center; pointer-events:auto;
    }
    nav[role="navigation"]{
      width: calc(100% - 40px); max-width: var(--max-width); display:flex; align-items:center; gap:12px;
      padding: 12px 16px; border-radius:14px;
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      backdrop-filter: blur(var(--glass-blur));
      border: 1px solid var(--glass-border);
      box-shadow: 0 8px 30px rgba(0,0,0,0.3);
    }
    .brand { display:flex; align-items:center; gap:10px; font-weight:800; color:var(--accent); font-family: var(--tt-1); letter-spacing:.6px; font-size:1.05rem; }
    .brand svg{ height:36px; width:36px; filter: drop-shadow(0 6px 24px rgba(0,255,247,0.06)); }
    .nav-links { margin-left: 14px; display:flex; gap: 12px; align-items:center; flex:1; }
    .nav-links a { color: var(--accent); text-decoration:none; padding:.35rem .6rem; border-radius:8px; font-weight:600; transition: transform .28s var(--ease), box-shadow .28s var(--ease); }
    .nav-links a:hover, .nav-links a:focus { transform: translateY(-3px); box-shadow: var(--shadow-neon); outline: none; }
    .nav-actions { display:flex; gap:10px; align-items:center; }

    .btn {
      display:inline-flex; align-items:center; gap:.6rem; padding:.52rem .7rem; border-radius:10px; cursor:pointer; border:1px solid transparent;
      background: linear-gradient(90deg,var(--accent),var(--accent-2)); color:#07101a; font-weight:700; box-shadow: 0 6px 30px rgba(0,255,247,0.08);
    }
    .btn.ghost { background:transparent; color:var(--accent); border: 1px solid rgba(255,255,255,0.04); font-weight:700; padding:.45rem .6rem; }
    .icon-btn { background:transparent; color:var(--accent); border:0; font-size:1.05rem; padding:.4rem; border-radius:8px }

    .theme-toggle { display:inline-flex; align-items:center; gap:8px; padding:.4rem; border-radius:8px; background:transparent; border:1px solid rgba(255,255,255,0.03); color:var(--muted); }

    /* responsive nav */
    .hamburger { display:none; background:transparent; border:0; color:var(--accent); font-size:1.1rem; padding:.45rem; border-radius:8px; }
    @media(max-width:900px){
      .nav-links{ display:none; }
      .hamburger { display:inline-flex; }
    }

    /* ---------- hero cinematic ---------- */
    .hero {
      position: relative; height: calc(100vh - 60px); min-height: 560px; display:flex; align-items:center; justify-content:center;
      padding-top:80px;
      overflow:hidden;
    }
    /* video background: replace src with your cinematic loop (local or CDN) */
    .hero-video-wrap {
      position:absolute; inset:0; z-index:0; overflow:hidden;
      display:flex; align-items:center; justify-content:center;
      background: linear-gradient(135deg, rgba(0,0,0,0.25), rgba(0,0,0,0.45));
    }
    .hero video { width:100%; height:100%; object-fit:cover; opacity:.85; filter: saturate(1.05) contrast(1.02); }

    /* Liquid gradient layer */
    .liquid-overlay {
      position:absolute; inset:-20% -10% -20% -10%; z-index:1; pointer-events:none;
      background: radial-gradient(60% 40% at 10% 20%, rgba(0,255,247,0.08), transparent 10%),
                  radial-gradient(50% 40% at 90% 80%, rgba(255,0,255,0.06), transparent 12%);
      mix-blend-mode: screen;
      transform: translateZ(0);
      animation: floatLiquid 22s ease-in-out infinite;
    }
    @keyframes floatLiquid {
      0%{ transform: translateY(0px) rotate(0deg); }
      50%{ transform: translateY(-40px) rotate(8deg); }
      100%{ transform: translateY(0px) rotate(0deg); }
    }

    /* hero content card (glassmorphism) */
    .hero-card {
      z-index: 2; width: min(1100px, 94%); padding: 40px; border-radius:20px; display:flex; gap:24px; align-items:center;
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border: 1px solid var(--glass-border); backdrop-filter: blur(18px) saturate(120%);
      box-shadow: 0 30px 80px rgba(2,6,23,0.6);
      transform-style: preserve-3d;
    }
    .hero-left { flex:1; min-width:240px; color:var(--text); }
    .hero-right { width:420px; max-width:44%; display:flex; flex-direction:column; gap:14px; align-items:center; }

    .hero h1 {
      font-family:var(--tt-1); font-size: clamp(1.9rem, 4vw, 3.6rem); line-height:1.02; margin:0 0 8px 0;
      text-shadow: 0 8px 40px rgba(0,0,0,0.6);
    }
    .hero p.lead { margin:0 0 18px 0; color:var(--muted); font-weight:600; max-width:680px; }

    .cta-row { display:flex; gap:12px; align-items:center; margin-top:8px; }
    .secondary { background: linear-gradient(90deg, rgba(0,0,0,0.35), rgba(255,255,255,0.02)); padding:.6rem .9rem; border-radius:10px; color:var(--muted); border:1px solid rgba(255,255,255,0.03); }

    /* floating cards example */
    .floating-cards { display:flex; gap:14px; margin-top:18px; flex-wrap:wrap; }
    .float-card {
      width: 185px; padding:12px; border-radius:14px;
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border:1px solid rgba(255,255,255,0.03); color:var(--accent);
      transform-origin:center; transition: transform .55s var(--ease), box-shadow .4s var(--ease);
      box-shadow: 0 14px 40px rgba(0,0,0,0.45);
    }
    .float-card:hover { transform: translateY(-12px) rotateX(6deg) rotateY(3deg); box-shadow: 0 28px 70px rgba(0,0,0,0.55); }

    /* subscriber counter */
    .subscriber {
      display:flex; align-items:center; gap:12px; background: linear-gradient(90deg, rgba(0,0,0,0.15), rgba(255,255,255,0.01)); padding:.6rem .8rem; border-radius:12px; border:1px solid rgba(255,255,255,0.03);
      color:var(--muted);
    }
    .subscriber strong { color: var(--accent); font-size:1.2rem; font-weight:800; }

    /* ---------- sections ---------- */
    section { padding: 90px 0; position:relative; z-index:2; }
    .section-title { font-family:var(--tt-1); color:var(--accent); margin-bottom:12px; font-size:1.2rem; letter-spacing:.6px; }
    .section-sub { font-size:1.18rem; color:var(--muted); margin-bottom:20px; max-width:920px; }

    /* features / cards grid */
    .grid { display:grid; grid-template-columns: repeat(3,1fr); gap:18px; align-items:start; }
    .card-glass { padding:18px; border-radius:14px; background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); border:1px solid rgba(255,255,255,0.03); box-shadow:var(--shadow-neon); transition: transform .45s var(--ease);}
    .card-glass:hover { transform: translateY(-12px) scale(1.02); }

    @media(max-width:1000px){
      .grid{ grid-template-columns: repeat(2,1fr) }
      .hero-right{ display:none }
      .hero-card { padding:28px; flex-direction:column; }
      .float-card{ width:45% }
    }
    @media(max-width:640px){
      .grid{ grid-template-columns: 1fr }
      .brand span{ display:none }
      .nav-links{ display:none }
      .hero { padding-top: 100px; min-height:620px; }
      .preloader { align-items:flex-end }
      .wrap { padding: 0 14px; }
      .floating-cards{ justify-content:center }
    }

    /* testimonials carousel (simple) */
    .testimonials { display:flex; gap:14px; align-items:center; overflow:hidden; padding: 10px 0; }
    .testimonial { min-width: 320px; max-width: 420px; padding:16px; border-radius:12px; background: linear-gradient(180deg, rgba(0,0,0,0.3), rgba(0,0,0,0.15)); border:1px solid rgba(255,255,255,0.04); }
    .testimonial small { display:block; margin-top:10px; color:var(--muted); font-weight:600; }

    /* roadmap timeline */
    .timeline { display:flex; gap:24px; align-items:flex-start; justify-content:space-between; flex-wrap:wrap; }
    .timeline .milestone { flex:1; min-width:220px; padding:18px; border-radius:12px; background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); border:1px solid rgba(255,255,255,0.03); }
    .timeline .milestone time { font-weight:800; color:var(--accent); display:block; margin-bottom:8px; }

    /* team cards (3d) */
    .team-grid { display:grid; grid-template-columns: repeat(3,1fr); gap:16px; }
    .team-member{ padding:14px; border-radius:12px; background: linear-gradient(180deg, rgba(0,0,0,0.2), rgba(255,255,255,0.01)); border:1px solid rgba(255,255,255,0.03); transform-style:preserve-3d; transition: transform .45s var(--ease), box-shadow .45s var(--ease);}
    .team-member:hover { transform: perspective(900px) translateY(-10px) rotateX(4deg); box-shadow: 0 30px 80px rgba(0,0,0,0.6); }

    /* footer */
    footer { padding:30px 0; border-top:1px solid rgba(255,255,255,0.03); text-align:center; color:var(--muted); background: linear-gradient(180deg, rgba(0,0,0,0.02), transparent); }
    footer .small { font-size:.92rem; opacity:.9; }

    /* floating contact button */
    .float-contact {
      position: fixed; right: 20px; bottom: 20px; z-index:90; display:flex; gap:10px; flex-direction:column; align-items:flex-end;
    }
    .float-contact .fc-btn { background: linear-gradient(90deg,var(--accent),var(--accent-2)); color:#07101a; padding:.8rem .9rem; border-radius:12px; box-shadow: 0 10px 40px rgba(0,255,247,0.08); border:0; cursor:pointer; font-weight:800; }
    .float-contact .fc-icon { background: transparent; color:var(--accent); border-radius:50%; padding:.6rem; border:1px solid rgba(255,255,255,0.03); }

    /* small utilities */
    .muted { color:var(--muted); }
    .center { text-align:center; }
    .kbd { font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, monospace; background: rgba(0,0,0,0.18); padding:.12rem .36rem; border-radius:6px; font-size:.86rem; }
  </style>
  <!-- End critical CSS -->
</head>
<body>
  <!-- =========================
       PRELOADER (custom)
       Replace or remove after testing
       ========================= -->
  <div class="preloader" id="preloader" role="status" aria-live="polite" aria-label="Loading SpotlixHQ">
    <div class="loader-wrap" aria-hidden="false">
      <div class="loader-brand">
        <!-- small inline svg mark; replace later with your full logo asset if needed -->
        <svg width="34" height="34" viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" focusable="false">
          <defs><linearGradient id="lg1" x1="0" x2="1"><stop offset="0" stop-color="#00fff7"/><stop offset="1" stop-color="#ff00ff"/></linearGradient></defs>
          <circle cx="32" cy="32" r="28" fill="url(#lg1)" opacity="0.12"/>
          <circle cx="32" cy="24" r="6" fill="url(#lg1)"/>
        </svg>
        <div style="font-weight:700; color:var(--accent); font-family:var(--tt-1)">SpotlixHQ</div>
      </div>
      <div style="display:flex; gap:8px; margin-top:14px;">
        <div class="loader-dot" style="--i:1"></div>
        <div class="loader-dot" style="--i:2"></div>
        <div class="loader-dot" style="--i:3"></div>
      </div>
      <div class="loader-caption">Building your spotlight…</div>
    </div>
  </div>

  <!-- =========================
       HEADER / NAV
       ========================= -->
  <header>
    <nav role="navigation" aria-label="Main navigation">
      <div class="brand" aria-hidden="false">
        <svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" focusable="false">
          <defs><linearGradient id="lg2" x1="0" x2="1"><stop offset="0" stop-color="#00fff7"/><stop offset="1" stop-color="#ff00ff"/></linearGradient></defs>
          <circle cx="32" cy="32" r="28" fill="url(#lg2)" opacity="0.12"/>
          <path d="M20 40c4-7 16-7 20 0" stroke="url(#lg2)" stroke-width="3" stroke-linecap="round" fill="none"/>
          <circle cx="32" cy="24" r="6" fill="url(#lg2)"/>
        </svg>
        <span>SpotlixHQ <span style="font-weight:600; color:var(--muted); font-size:.88rem; margin-left:8px">— Spotlight Squad</span></span>
      </div>

      <div class="nav-links" role="menubar" aria-label="Primary">
        <a href="#home" id="nav-home" role="menuitem">Home</a>
        <a href="#about" id="nav-about" role="menuitem">About</a>
        <a href="#community" id="nav-community" role="menuitem">Community</a>
        <a href="#team" id="nav-team" role="menuitem">Team</a>
        <a href="#roadmap" id="nav-roadmap" role="menuitem">Roadmap</a>
      </div>

      <div class="nav-actions">
        <div class="subscriber" aria-hidden="false" title="Live subscriber-ish">
          <i class="fa fa-user" aria-hidden="true" style="color:var(--accent)"></i>
          <div style="display:flex;flex-direction:column;line-height:1">
            <small class="muted">Subscribers</small>
            <strong id="subscriberCount">—</strong>
          </div>
        </div>

        <button class="btn ghost" id="openJoin" aria-haspopup="dialog" title="Join the Squad">Join the Squad</button>
        <button class="theme-toggle" id="themeToggle" title="Toggle theme" aria-pressed="false" aria-label="Toggle theme">
          <i class="fa fa-adjust" aria-hidden="true"></i> Theme
        </button>

        <button class="hamburger" id="hamburger" aria-label="Open menu" aria-expanded="false">
          <i class="fa fa-bars" aria-hidden="true"></i>
        </button>
      </div>
    </nav>
  </header>

  <!-- mobile overlay menu -->
  <div id="mobileOverlay" aria-hidden="true" style="display:none; position:fixed; inset:72px 12px auto 12px; z-index:95;">
    <div style="background:linear-gradient(180deg, rgba(0,0,0,0.6), rgba(0,0,0,0.5)); padding:12px; border-radius:12px; backdrop-filter:blur(8px);">
      <a href="#home" class="mobile-link">Home</a><br/>
      <a href="#about" class="mobile-link">About</a><br/>
      <a href="#community" class="mobile-link">Community</a><br/>
      <a href="#team" class="mobile-link">Team</a><br/>
      <a href="#roadmap" class="mobile-link">Roadmap</a><br/>
      <div style="height:8px"></div>
      <a href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener">Instagram</a><br/>
      <a href="https://t.me/SpotlixHQ" target="_blank" rel="noopener">Telegram</a><br/>
      <a href="https://www.youtube.com/@SpotlixHQ" target="_blank" rel="noopener">YouTube</a><br/>
      <a href="mailto:spotlixhq@gmail.com">Email</a><br/>
    </div>
  </div>

  <main>
    <!-- =========================
         HERO - Cinematic
         Replace the video src with your high-quality loop in /assets or CDN
         ========================= -->
    <section id="home" class="hero" aria-labelledby="homeHeading">
      <div class="hero-video-wrap" aria-hidden="true">
        <!-- Placeholder video: replace with your own cinematic loop -->
        <video id="heroVideo" autoplay muted loop playsinline poster="" crossorigin="anonymous" preload="auto">
          <source src="assets/hero-loop.mp4" type="video/mp4">
          <!-- fallback gradient already visible -->
        </video>
      </div>

      <div class="liquid-overlay" aria-hidden="true"></div>

      <div class="hero-card wrap" role="region" aria-label="Hero">
        <div class="hero-left">
          <h1 id="homeHeading">Stop working alone. Launch with a squad.</h1>
          <p class="lead">SpotlixHQ (Spotlight Squad) is a premium creator community where creators, thinkers and collaborators come together to make better content, learn faster, and launch bigger projects — across Instagram, Telegram and YouTube.</p>

          <div class="cta-row">
            <button class="btn" id="joinPrimary" aria-haspopup="dialog">Join the Squad</button>
            <button class="btn ghost" id="watchTour" title="Preview">Watch Tour</button>
            <div style="flex:1"></div>
            <div class="subscriber" style="padding:6px 10px; border-radius:10px;">
              <i class="fa fa-bolt" aria-hidden="true" style="color:var(--accent)"></i>
              <div style="display:flex; flex-direction:column; line-height:1">
                <small class="muted">Active members</small>
                <strong id="activeMembers">—</strong>
              </div>
            </div>
          </div>

          <div class="floating-cards" role="list" aria-hidden="false">
            <div class="float-card" role="listitem"><strong>Collabs</strong><div class="muted">Team up for weekly shoots</div></div>
            <div class="float-card" role="listitem"><strong>Workshops</strong><div class="muted">Skill sprints & critiques</div></div>
            <div class="float-card" role="listitem"><strong>Resources</strong><div class="muted">Templates & presets</div></div>
          </div>
        </div>

        <aside class="hero-right" aria-hidden="false">
          <div style="width:100%; border-radius:12px; padding:12px; text-align:left; background: linear-gradient(180deg, rgba(0,0,0,0.2), rgba(255,255,255,0.01)); border:1px solid rgba(255,255,255,0.03);">
            <div style="display:flex; justify-content:space-between; align-items:center;">
              <div>
                <div style="font-size:.9rem; color:var(--muted)">Spotlight Score</div>
                <div style="font-weight:800; font-size:1.6rem; color:var(--accent)">92</div>
              </div>
              <div style="font-size:.8rem; color:var(--muted)">Since <time>2023</time></div>
            </div>
            <div style="height:10px"></div>
            <div style="background:linear-gradient(90deg,var(--accent),var(--accent-2)); height:6px; border-radius:10px; overflow:hidden"><div style="width:92%; height:100%; background: rgba(7,7,8,0.05)"></div></div>
          </div>

          <div style="height:12px"></div>

          <div style="width:100%; border-radius:12px; padding:12px; text-align:center; border:1px solid rgba(255,255,255,0.03);">
            <div style="font-weight:700; color:var(--accent)">Featured Collab</div>
            <div class="muted" style="font-size:.95rem">"Night Lights — short film"</div>
            <div style="height:10px"></div>
            <a class="btn" href="https://www.youtube.com/@SpotlixHQ" target="_blank" rel="noopener">Watch</a>
          </div>
        </aside>
      </div>
    </section>

    <!-- =========================
         ABOUT
         ========================= -->
    <section id="about" aria-labelledby="about-title" class="wrap">
      <div style="max-width:1200px; margin:0 auto; display:grid; grid-template-columns: 1fr 400px; gap:26px; align-items:start;">
        <div>
          <div class="section-title">About SpotlixHQ</div>
          <h2 class="section-sub">A creator-first community that helps you plan, film, and publish better work with a team.</h2>
          <p class="muted">We built Spotlight Squad because making content alone is slow, lonely, and sometimes directionless. We connect creators with teammates, feedback, and short sprints that ship results. Our members get access to premium templates, weekly critiques, live workshops and featured distribution on our channel.</p>

          <div style="height:18px"></div>

          <div class="grid" role="list" aria-label="Why join">
            <div class="card-glass" role="listitem">
              <h3 style="margin:0 0 6px 0">Fast Collabs</h3>
              <p class="muted" style="margin:0">Find creators in your niche and start a collab in 48 hours.</p>
            </div>
            <div class="card-glass" role="listitem">
              <h3 style="margin:0 0 6px 0">Workshops</h3>
              <p class="muted" style="margin:0">Weekly masterclasses from creators & industry pros.</p>
            </div>
            <div class="card-glass" role="listitem">
              <h3 style="margin:0 0 6px 0">Distribution</h3>
              <p class="muted" style="margin:0">Featured placements across SpotlixHQ channels and partners.</p>
            </div>
          </div>
        </div>

        <!-- right column: testimonials + CTA -->
        <aside>
          <div style="border-radius:14px; padding:14px; border:1px solid rgba(255,255,255,0.03); background: linear-gradient(180deg, rgba(0,0,0,0.2), rgba(255,255,255,0.01))">
            <div style="display:flex; justify-content:space-between; align-items:center;">
              <div>
                <div class="muted">Community</div>
                <div style="font-weight:800; font-size:1.2rem; color:var(--accent)">Spotlight Squad</div>
              </div>
              <div style="font-size:.9rem" class="muted">Free & Premium tiers</div>
            </div>

            <div style="height:12px"></div>

            <div class="testimonials" id="testimonials" aria-live="polite">
              <div class="testimonial">
                "I doubled my reach in 3 weeks thanks to a collab I found here." <small>— Aisha, filmmaker</small>
              </div>
              <div class="testimonial">
                "The critique sessions are brutal but kind — content improved quickly." <small>— Rohit, vlogger</small>
              </div>
              <div class="testimonial">
                "Templates saved me days of editing time." <small>— Maya, creator</small>
              </div>
            </div>

            <div style="height:12px"></div>
            <div style="display:flex; gap:8px;">
              <button class="btn" id="joinFromAbout">Join - Free</button>
              <button class="btn ghost" id="seePlans">See Plans</button>
            </div>
          </div>

          <div style="height:16px"></div>

          <div class="card-glass">
            <div class="muted">Contact</div>
            <div style="display:flex; gap:8px; margin-top:8px;">
              <a class="btn ghost" href="mailto:spotlixhq@gmail.com">Email</a>
              <a class="btn" href="https://t.me/SpotlixHQ" target="_blank" rel="noopener">Telegram</a>
            </div>
          </div>
        </aside>
      </div>
    </section>

    <!-- =========================
         COMMUNITY (links)
         ========================= -->
    <section id="community" aria-labelledby="community-title" class="wrap">
      <div style="max-width:1100px; margin:0 auto;">
        <div class="section-title">Connect With Us</div>
        <h3 class="section-sub">Find us across platforms — join live discussions, watch workshops, and submit collabs.</h3>

        <div style="display:grid; grid-template-columns: repeat(4, 1fr); gap:14px;">
          <a class="card-glass" href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener" role="link">
            <strong>Instagram</strong><div class="muted">Share reels, updates & features</div>
          </a>
          <a class="card-glass" href="https://t.me/SpotlixHQ" target="_blank" rel="noopener">
            <strong>Telegram</strong><div class="muted">Announcements & live discussions</div>
          </a>
          <a class="card-glass" href="https://www.youtube.com/@SpotlixHQ" target="_blank" rel="noopener">
            <strong>YouTube</strong><div class="muted">Watch workshops & shorts</div>
          </a>
          <a class="card-glass" href="mailto:spotlixhq@gmail.com" target="_blank" rel="noopener">
            <strong>Email</strong><div class="muted">Contact for partnerships</div>
          </a>
        </div>
      </div>
    </section>

    <!-- =========================
         TEAM
         ========================= -->
    <section id="team" aria-labelledby="team-title" class="wrap">
      <div style="max-width:1100px; margin:0 auto;">
        <div class="section-title">Our Team</div>
        <h3 class="section-sub">Passionate people behind the spotlight.</h3>

        <div class="team-grid" role="list">
          <div class="team-member" role="listitem" tabindex="0" onclick="toggleBio(this)" onkeypress="if(event.key==='Enter'){ toggleBio(this) }" aria-pressed="false" aria-label="Suryansh, Founder">
            <strong>Suryansh</strong>
            <div class="muted">Founder</div>
            <div class="bio" style="display:none; margin-top:10px; color:var(--accent);">
              Love creativity<br/>
              <a href="https://www.instagram.com/suryansh_y09?igsh=MXIzNGhmMGtlZjY4eQ==" target="_blank" rel="noopener">Instagram</a> |
              <a href="mailto:suryanshy302@gmail.com">Email</a>
            </div>
          </div>

          <div class="team-member" role="listitem" tabindex="0" onclick="toggleBio(this)" onkeypress="if(event.key==='Enter'){ toggleBio(this) }" aria-pressed="false" aria-label="Anup, Team member">
            <strong>Anup</strong>
            <div class="muted">Team Member</div>
            <div class="bio" style="display:none; margin-top:10px; color:var(--accent);">
              Not a backup plan — I’m the main character.<br/>
              <a href="https://www.instagram.com/anup_.45_45?igsh=cDhuY3plOGVxaXhw" target="_blank" rel="noopener">Instagram</a> |
              <a href="mailto:gurub0357@gmail.com">Email</a>
            </div>
          </div>

          <div class="team-member" role="listitem" tabindex="0" aria-label="Open roles">
            <strong>Want to join?</strong>
            <div class="muted">We're hiring contributors & community managers — say hello.</div>
            <div style="height:8px"></div>
            <a class="btn ghost" href="mailto:spotlixhq@gmail.com">Contact</a>
          </div>
        </div>
      </div>
    </section>

    <!-- =========================
         ROADMAP / TIMELINE
         ========================= -->
    <section id="roadmap" aria-labelledby="roadmap-title" class="wrap">
      <div style="max-width:1100px; margin:0 auto;">
        <div class="section-title">Roadmap</div>
        <h3 class="section-sub">What’s next for Spotlight Squad — a short-term roadmap.</h3>

        <div class="timeline" role="list">
          <div class="milestone" role="listitem">
            <time>Q4 2025</time>
            <div style="font-weight:800">Public Workshops</div>
            <p class="muted">Monthly 2-hour masterclasses with industry guests.</p>
          </div>
          <div class="milestone" role="listitem">
            <time>Q1 2026</time>
            <div style="font-weight:800">Creator Grants</div>
            <p class="muted">Micro-grants for high-impact community projects.</p>
          </div>
          <div class="milestone" role="listitem">
            <time>Q2 2026</time>
            <div style="font-weight:800">Spotlix Studio</div>
            <p class="muted">Collab space & production resources for members.</p>
          </div>
        </div>
      </div>
    </section>

  </main>

  <!-- Floating contact & quick join -->
  <div class="float-contact" aria-hidden="false">
    <button class="fc-btn" id="quickJoin">Join Spotlight</button>
    <a class="fc-icon" href="https://t.me/SpotlixHQ" target="_blank" rel="noopener" aria-label="Open Telegram">
      <i class="fab fa-telegram"></i>
    </a>
  </div>

  <!-- Contact / Join modal -->
  <div class="modal-backdrop" id="modalBackdrop" aria-hidden="true" style="display:none; position:fixed; inset:0; z-index:100; align-items:center; justify-content:center; background: rgba(0,0,0,0.6);">
    <div role="dialog" aria-modal="true" aria-labelledby="contactTitle" class="modal" style="width:92%; max-width:520px; border-radius:14px; padding:18px; background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); border:1px solid rgba(255,255,255,0.03);">
      <h3 id="contactTitle" style="color:var(--accent); margin:0 0 6px 0;">Join the Squad</h3>
      <p class="muted" style="margin:0 0 12px 0">Tell us where you hang out most — we'll connect you to the right onboarding flow.</p>

      <div style="display:flex; gap:10px; flex-wrap:wrap; margin-bottom:12px;">
        <button class="btn" data-platform="telegram" onclick="openExternal('https://t.me/SpotlixHQ')">Telegram</button>
        <button class="btn ghost" data-platform="instagram" onclick="openExternal('https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo')">Instagram</button>
        <button class="btn ghost" data-platform="youtube" onclick="openExternal('https://www.youtube.com/@SpotlixHQ')">YouTube</button>
        <button class="btn ghost" data-platform="email" onclick="document.location='mailto:spotlixhq@gmail.com'">Email</button>
      </div>

      <label for="platformInput" class="muted">Or leave your email for updates</label>
      <div style="display:flex; gap:8px; margin-top:8px;">
        <input id="platformInput" type="email" placeholder="you@domain.com" style="flex:1; padding:.6rem; border-radius:10px; border:1px solid rgba(255,255,255,0.04); background:transparent; color:var(--text)">
        <button class="btn" id="submitEmail">Send</button>
      </div>

      <div style="height:10px"></div>
      <div style="display:flex; justify-content:flex-end; gap:8px;">
        <button class="btn ghost" id="closeModal">Close</button>
      </div>
    </div>
  </div>

  <!-- footer -->
  <footer>
    <div class="wrap">
      <div style="display:flex; justify-content:space-between; gap:16px; align-items:center; flex-wrap:wrap;">
        <div>
          <div style="font-weight:800; color:var(--accent)">SpotlixHQ</div>
          <div class="muted small">Community for creators, thinkers, and innovators. Reach out: <a href="mailto:spotlixhq@gmail.com" style="color:var(--accent); text-decoration:none;">spotlixhq@gmail.com</a></div>
        </div>
        <div class="muted small">Proudly Indian Made 🌟 | © <span id="year">2025</span> SpotlixHQ. All rights reserved.</div>
      </div>
    </div>
  </footer>

  <!-- =========================
       SCRIPTS
       Keep minimal & performant.
       ========================= -->
  <script>
    // ---------- small helpers & initial state ----------
    document.getElementById('year').textContent = new Date().getFullYear();

    // Remove preloader after load (small delay for smoothness)
    window.addEventListener('load', () => {
      const pre = document.getElementById('preloader');
      if(pre){ pre.style.transition = 'opacity .6s ease'; pre.style.opacity = '0'; setTimeout(()=> pre.remove(), 650); }
      // After load, start non-critical animations
      startSimulations();
    });

    // ---------- simple subscriber simulation ----------
    function formatNum(n){
      return n.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
    }
    function startSimulations(){
      const subEl = document.getElementById('subscriberCount');
      const activeEl = document.getElementById('activeMembers');

      // Simulated baseline
      let base = 12500 + Math.floor(Math.random()*5000);
      let active = 420 + Math.floor(Math.random()*180);

      // animate to base
      animateCount(subEl, base, 1400);
      animateCount(activeEl, active, 1100);

      // small periodic bumps
      setInterval(()=>{
        const bump = Math.floor(Math.random()*3);
        base += bump;
        active += (bump>0?1:0);
        animateCount(subEl, base, 900);
        animateCount(activeEl, active, 800);
      }, 4500);
    }

    function animateCount(el, target, ms){
      if(!el) return;
      const start = +el.textContent.replace(/,/g,'') || 0;
      const diff = target - start;
      const steps = Math.min(60, Math.max(12, Math.floor(ms/16)));
      let i = 0;
      const step = () => {
        i++;
        const val = Math.round(start + (diff * (i/steps)));
        el.textContent = formatNum(val);
        if(i < steps) requestAnimationFrame(step);
      };
      requestAnimationFrame(step);
    }

    // ---------- Modal logic ----------
    const modalBackdrop = document.getElementById('modalBackdrop');
    const openJoin = document.getElementById('openJoin');
    const openJoin2 = document.getElementById('joinPrimary');
    const quickJoin = document.getElementById('quickJoin');
    const closeModalEl = document.getElementById('closeModal');
    const submitEmail = document.getElementById('submitEmail');

    function openModal(){
      modalBackdrop.style.display = 'flex';
      modalBackdrop.setAttribute('aria-hidden','false');
      // trap focus
      setTimeout(()=> document.getElementById('platformInput').focus(), 80);
    }
    function closeModal(){
      modalBackdrop.style.display = 'none';
      modalBackdrop.setAttribute('aria-hidden','true');
    }
    if(openJoin) openJoin.addEventListener('click', openModal);
    if(openJoin2) openJoin2.addEventListener('click', openModal);
    if(quickJoin) quickJoin.addEventListener('click', openModal);
    if(closeModalEl) closeModalEl.addEventListener('click', closeModal);
    modalBackdrop.addEventListener('click', (e)=> { if(e.target === modalBackdrop) closeModal(); });

    if(submitEmail){
      submitEmail.addEventListener('click', () => {
        const input = document.getElementById('platformInput');
        if(!input || !input.value) {
          input && (input.placeholder = 'Please enter a valid email');
          return;
        }
        // simulate success
        submitEmail.textContent = 'Sent ✓';
        setTimeout(()=>{ submitEmail.textContent = 'Send'; closeModal(); }, 1200);
      });
    }

    function openExternal(url){
      window.open(url, '_blank', 'noopener');
    }

    // ---------- Mobile menu ----------
    const hamburger = document.getElementById('hamburger');
    const mobileOverlay = document.getElementById('mobileOverlay');
    if(hamburger){
      hamburger.addEventListener('click', () => {
        const opened = hamburger.getAttribute('aria-expanded') === 'true';
        hamburger.setAttribute('aria-expanded', String(!opened));
        if(!opened){ mobileOverlay.style.display = 'block'; mobileOverlay.setAttribute('aria-hidden','false'); }
        else { mobileOverlay.style.display = 'none'; mobileOverlay.setAttribute('aria-hidden','true'); }
      });
      // close when links clicked
      mobileOverlay.querySelectorAll('a').forEach(a => a.addEventListener('click', ()=> {
        mobileOverlay.style.display = 'none';
        hamburger.setAttribute('aria-expanded','false');
      }));
    }

    // ---------- theme toggle ----------
    const themeToggle = document.getElementById('themeToggle');
    let theme = localStorage.getItem('spotlixTheme') || (window.matchMedia && window.matchMedia('(prefers-color-scheme: light)').matches ? 'light' : 'dark');
    applyTheme(theme);
    if(themeToggle){
      themeToggle.addEventListener('click', ()=>{
        theme = (theme === 'dark' ? 'light' : 'dark');
        applyTheme(theme);
      });
    }
    function applyTheme(t){
      if(t === 'light'){
        document.documentElement.style.setProperty('--bg-1','#f7fbff');
        document.documentElement.style.setProperty('--bg-2','#e6f2ff');
        document.documentElement.style.setProperty('--card','rgba(255,255,255,0.65)');
        document.documentElement.style.setProperty('--text','#07101a');
        document.documentElement.style.setProperty('--glass','rgba(0,0,0,0.03)');
      } else {
        document.documentElement.style.setProperty('--bg-1','#08040a');
        document.documentElement.style.setProperty('--bg-2','#1b1830');
        document.documentElement.style.setProperty('--card','rgba(7,7,8,0.45)');
        document.documentElement.style.setProperty('--text','#ffffff');
        document.documentElement.style.setProperty('--glass','rgba(255,255,255,0.04)');
      }
      localStorage.setItem('spotlixTheme', t);
      themeToggle && themeToggle.setAttribute('aria-pressed', String(t==='dark'));
    }

    // ---------- team bio toggle (keeps original details) ----------
    function toggleBio(member){
      const bio = member.querySelector('.bio');
      if(!bio) return;
      const isShown = bio.style.display === 'block';
      bio.style.display = isShown ? 'none' : 'block';
      member.setAttribute('aria-pressed', String(!isShown));
    }
    window.toggleBio = toggleBio;

    // ---------- intersection observer for section reveal ----------
    const sections = document.querySelectorAll('main section');
    const io = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if(entry.isIntersecting) entry.target.classList.add('active');
      });
    }, { threshold: 0.18 });
    sections.forEach(s => io.observe(s));

    // ---------- keyboard accessibility ----------
    document.addEventListener('keydown', (e) => {
      if(e.key === 'Escape') {
        // close modal
        if(modalBackdrop.style.display === 'flex') closeModal();
        if(mobileOverlay.style.display === 'block'){ mobileOverlay.style.display = 'none'; hamburger.setAttribute('aria-expanded','false'); }
      }
    });

    // ---------- small testimonial auto-scroll (non-blocking) ----------
    (function carouselTestimonials(){
      const el = document.getElementById('testimonials');
      if(!el) return;
      let idx = 0;
      const total = el.children.length;
      setInterval(()=>{
        idx = (idx + 1) % total;
        el.style.transform = `translateX(-${idx * 340}px)`;
        el.style.transition = 'transform .7s ease';
      }, 4200);
    })();

    // ---------- small perf note ----------
    // Non-critical heavy features (analytics, real subscriber API) should be loaded here after first paint.
  </script>

  <!-- =========================
       MULTILINGUAL CONTENT (10 languages) - non-blocking
       Replaces nav / about / community / team titles & some UI copy.
       ========================= -->
  <script>
    // content: 10 languages kept from your previous version
    const content = {
      en: {
        navHome: "Home", navAbout: "About", navCommunity: "Community", navTeam: "Team", navRoadmap: "Roadmap",
        aboutTitle: "About SpotlixHQ", aboutDesc: "SpotlixHQ is a community for creators, thinkers, and innovators to collaborate, share ideas, and grow together.",
        communityTitle: "Connect With Us", teamTitle: "Our Team", rtl:false
      },
      hi: {
        navHome: "होम", navAbout: "हमारे बारे में", navCommunity: "समुदाय", navTeam: "टीम", navRoadmap: "रोडमैप",
        aboutTitle: "SpotlixHQ के बारे में", aboutDesc: "SpotlixHQ रचनाकारों, विचारकों और नवप्रवर्तकों के लिए एक समुदाय है जहाँ वे सहयोग कर सकते हैं, विचार साझा कर सकते हैं और साथ में आगे बढ़ सकते हैं।",
        communityTitle: "हमसे जुड़ें", teamTitle: "हमारी टीम", rtl:false
      },
      de: {
        navHome: "Startseite", navAbout: "Über uns", navCommunity: "Community", navTeam: "Team", navRoadmap: "Roadmap",
        aboutTitle: "Über SpotlixHQ", aboutDesc: "SpotlixHQ ist eine Community für Kreative, Denker und Innovatoren, um zusammenzuarbeiten, Ideen zu teilen und gemeinsam zu wachsen.",
        communityTitle: "Vernetze dich mit uns", teamTitle: "Unser Team", rtl:false
      },
      ja: {
        navHome: "ホーム", navAbout: "概要", navCommunity: "コミュニティ", navTeam: "チーム", navRoadmap: "ロードマップ",
        aboutTitle: "SpotlixHQ について", aboutDesc: "SpotlixHQ は、クリエイターや思考家、イノベーターが協力し、アイデアを共有し、ともに成長するためのコミュニティです。",
        communityTitle: "私たちとつながる", teamTitle: "チーム紹介", rtl:false
      },
      es: {
        navHome: "Inicio", navAbout: "Acerca de", navCommunity: "Comunidad", navTeam: "Equipo", navRoadmap: "Hoja de ruta",
        aboutTitle: "Acerca de SpotlixHQ", aboutDesc: "SpotlixHQ es una comunidad para creadores, pensadores e innovadores donde pueden colaborar, compartir ideas y crecer juntos.",
        communityTitle: "Conéctate con nosotros", teamTitle: "Nuestro equipo", rtl:false
      },
      fr: {
        navHome: "Accueil", navAbout: "À propos", navCommunity: "Communauté", navTeam: "Équipe", navRoadmap: "Feuille de route",
        aboutTitle: "À propos de SpotlixHQ", aboutDesc: "SpotlixHQ est une communauté pour les créateurs, penseurs et innovateurs afin de collaborer, partager des idées et grandir ensemble.",
        communityTitle: "Connectez-vous avec nous", teamTitle: "Notre équipe", rtl:false
      },
      ar: {
        navHome: "الرئيسية", navAbout: "من نحن", navCommunity: "المجتمع", navTeam: "الفريق", navRoadmap: "خارطة الطريق",
        aboutTitle: "نبذة عن SpotlixHQ", aboutDesc: "SpotlixHQ هو مجتمع للمبدعين والمفكرين والمبتكرين للتعاون وتبادل الأفكار والنمو معًا.",
        communityTitle: "تواصل معنا", teamTitle: "فريقنا", rtl:true
      },
      id: {
        navHome: "Beranda", navAbout: "Tentang", navCommunity: "Komunitas", navTeam: "Tim", navRoadmap: "Peta jalan",
        aboutTitle: "Tentang SpotlixHQ", aboutDesc: "SpotlixHQ adalah komunitas bagi kreator, pemikir, dan inovator untuk berkolaborasi, berbagi ide, dan tumbuh bersama.",
        communityTitle: "Terhubung dengan kami", teamTitle: "Tim kami", rtl:false
      },
      bn: {
        navHome: "হোম", navAbout: "আমাদের সম্পর্কে", navCommunity: "কমিউনিটি", navTeam: "টিম", navRoadmap: "রোডম্যাপ",
        aboutTitle: "SpotlixHQ সম্পর্কে", aboutDesc: "SpotlixHQ হল সৃষ্টিশীল ব্যক্তি, চিন্তাবিদ এবং উদ্ভাবকদের জন্য একটি কমিউনিটি যেখানে তারা একসাথে কাজ করতে, আইডিয়া শেয়ার করতে এবং একসাথে বেড়ে উঠতে পারে।",
        communityTitle: "আমাদের সাথে যুক্ত হন", teamTitle: "আমাদের দল", rtl:false
      },
      zh: {
        navHome: "首页", navAbout: "关于", navCommunity: "社区", navTeam: "团队", navRoadmap: "路线图",
        aboutTitle: "关于 SpotlixHQ", aboutDesc: "SpotlixHQ 是一个为创作者、思想者和创新者而建立的社区，在这里可以协作、分享想法并共同成长。",
        communityTitle: "与我们联系", teamTitle: "我们的团队", rtl:false
      }
    };

    // wire language select
    const langSelect = document.querySelector('#language-select');
    if(langSelect){
      // populate current (already had options, but ensure)
      langSelect.addEventListener('change', () => applyLanguage(langSelect.value));
      applyLanguage(langSelect.value || 'en');
    }

    function applyLanguage(lang){
      if(!content[lang]) lang = 'en';
      const t = content[lang];

      document.getElementById('nav-home').textContent = t.navHome;
      document.getElementById('nav-about').textContent = t.navAbout;
      document.getElementById('nav-community').textContent = t.navCommunity;
      document.getElementById('nav-team').textContent = t.navTeam;
      const rnav = document.getElementById('nav-roadmap');
      if(rnav) rnav.textContent = t.navRoadmap || 'Roadmap';

      // about section headings
      const aboutTitle = document.getElementById('about-title');
      const aboutDesc = document.getElementById('about-desc');
      if(aboutTitle) aboutTitle.textContent = t.aboutTitle;
      if(aboutDesc) aboutDesc.textContent = t.aboutDesc;

      // community & team headings
      const communityTitle = document.getElementById('community-title');
      const teamTitle = document.getElementById('team-title');
      if(communityTitle) communityTitle.textContent = t.communityTitle;
      if(teamTitle) teamTitle.textContent = t.teamTitle;

      // RTL support
      document.documentElement.lang = lang;
      document.documentElement.dir = t.rtl ? 'rtl' : 'ltr';
      ['about','community','team'].forEach(id=>{
        const el = document.getElementById(id);
        if(!el) return;
        if(t.rtl) el.classList.add('rtl'); else el.classList.remove('rtl');
      });
    }
  </script>

  <!-- End body -->
</body>
</html>
