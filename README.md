<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
  <meta charset="utf-8" />
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

  <!-- Fonts & Icons -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&family=Playfair+Display:wght@600;700&display=swap" rel="stylesheet">
  <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous" defer></script>

  <style>
    /*
      SpotlixHQ – Upgraded Single-file CSS
      - Glassmorphism, Liquid gradients, Cinematic hero, Floating cards
      - Optimized for performance: critical CSS only, reduced layout shifts
      - Accessible focus outlines, prefers-reduced-motion respected
    */

    :root{
      /* palette refined */
      --bg-1:#061021;
      --bg-2:#151232;
      --accent-1:#00fff7;    /* cyan */
      --accent-2:#ff4dd2;    /* magenta */
      --glass: rgba(255,255,255,0.04);
      --panel: rgba(255,255,255,0.03);
      --muted: rgba(255,255,255,0.85);
      --card-radius:20px;
      --max-width:1200px;
      --easing: cubic-bezier(.16,.84,.3,1);
      --shadow-1: 0 6px 30px rgba(2,12,27,0.6);
      --glass-border: rgba(255,255,255,0.06);
      --success: #9fffe8;
      --danger: #ff6b6b;
      --font-sans: "Inter", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      --font-display: "Playfair Display", serif;
      --nav-height: 76px;
      --ui-scale: 1;
    }

    /* dark/light auto theme (prefers-color-scheme). user toggle applied via data-theme attr */
    :root[data-theme="light"]{
      --bg-1:#f6f8ff;
      --bg-2:#eef2ff;
      --panel: rgba(0,0,0,0.04);
      --glass: rgba(255,255,255,0.7);
      --muted: rgba(20,20,28,0.86);
      --shadow-1: 0 10px 40px rgba(10,20,40,0.08);
    }

    /* reduce motion */
    @media (prefers-reduced-motion: reduce){
      *{animation-duration:0.001ms !important; transition-duration:0.001ms !important}
    }

    /* base reset */
    *, *::before, *::after { box-sizing: border-box; }
    html,body { height:100%; }
    html { -webkit-font-smoothing:antialiased; -moz-osx-font-smoothing:grayscale; }
    body{
      margin:0;
      font-family: var(--font-sans);
      color: var(--muted);
      background: radial-gradient(1200px 800px at 10% 10%, rgba(0,255,247,0.06), transparent 6%),
                  radial-gradient(900px 700px at 90% 90%, rgba(255,77,210,0.05), transparent 8%),
                  linear-gradient(135deg, var(--bg-1), var(--bg-2));
      background-attachment: fixed;
      min-height:100vh;
      line-height:1.45;
      -webkit-text-size-adjust:100%;
      --safe-padding: clamp(12px, 2.2vw, 28px);
    }

    /* container */
    .wrap{ max-width: var(--max-width); margin: 0 auto; padding: 0 var(--safe-padding); }

    /* smart fluid scale for headings */
    h1,h2,h3{ margin:0; font-weight:700; color:var(--accent-1); }
    h1{ font-family: var(--font-display); font-size: clamp(32px, 4.2vw, 54px); line-height:1.02; color:var(--accent-1)}
    h2{ font-size: clamp(20px, 2.2vw, 28px); color: var(--muted) }
    p{ margin:0; color:var(--muted); }

    /* NAV: professional */
    header{ position:sticky; top:12px; z-index:140; display:flex; justify-content:center; pointer-events:auto; }
    nav.navbar{
      width: calc(100% - 2*var(--safe-padding));
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius: 14px;
      display:flex; align-items:center; gap:16px;
      padding: 12px 18px; align-items:center;
      box-shadow: var(--shadow-1);
      backdrop-filter: blur(10px) saturate(120%);
      border: 1px solid var(--glass-border);
      max-width: var(--max-width);
    }
    .brand{ display:flex; align-items:center; gap:12px; min-width:0; }
    .brand svg{ width:44px; height:44px; flex:0 0 44px; }
    .brand .title{ font-weight:800; font-family:var(--font-display); color:var(--accent-1); font-size:1rem; letter-spacing:0.4px; white-space:nowrap; overflow:hidden; text-overflow:ellipsis }
    .nav-links{ display:flex; gap:12px; margin-left:18px; align-items:center; }
    .nav-links a{
      color:var(--accent-1); text-decoration:none; padding:8px 12px; border-radius:10px; font-weight:600; transition: transform .28s var(--easing), box-shadow .28s var(--easing);
    }
    .nav-links a:hover, .nav-links a:focus{ transform: translateY(-3px); box-shadow: 0 8px 30px rgba(0,0,0,0.18); outline: none; }
    .nav-actions{ margin-left:auto; display:flex; gap:8px; align-items:center; }

    .socials a{ color:var(--accent-1); text-decoration:none; padding:8px; border-radius:8px; display:inline-flex; align-items:center; justify-content:center; }
    .socials a:hover{ color:var(--accent-2); transform:scale(1.06); }

    select#language-select{
      background:transparent; border:1px solid rgba(255,255,255,0.04); color:var(--accent-1); padding:.45rem .6rem; border-radius:8px; font-weight:600;
    }

    /* mobile */
    .hamburger{ display:none; background:transparent; border:0; color:var(--accent-1); font-size:22px; padding:8px; }
    .mobile-menu{ display:none; position:fixed; inset:84px 12px auto 12px; background:linear-gradient(180deg, rgba(0,0,0,0.6), rgba(0,0,0,0.45)); border-radius:12px; padding:12px; z-index:200; width:calc(100% - 24px); max-width:360px; }
    .mobile-menu a{ display:block; padding:10px 8px; color:var(--accent-1); text-decoration:none; font-weight:700; }

    /* HERO cinematic */
    .hero{
      padding: clamp(28px, 6vw, 88px) 0; display:grid; grid-template-columns: 1fr; gap:20px; align-items:center;
    }
    .hero-inner{ background: linear-gradient(135deg, rgba(255,255,255,0.02), rgba(0,0,0,0.08)); border-radius:24px; padding: clamp(22px, 3.5vw, 40px); box-shadow: var(--shadow-1); border:1px solid var(--glass-border); display:flex; gap:24px; flex-direction:column; }
    .hero-top{ display:flex; gap:18px; align-items:flex-start; }
    .hero-visual{
      min-height:230px; border-radius:16px; flex:0 0 46%; position:relative; overflow:hidden;
      background: radial-gradient(600px 200px at 10% 10%, rgba(0,255,247,0.08), transparent 8%), linear-gradient(120deg, rgba(0,255,247,0.04), rgba(255,77,210,0.03));
      border: 1px solid rgba(255,255,255,0.02);
      display:flex; align-items:center; justify-content:center;
    }
    .hero-caption{ flex:1; display:flex; flex-direction:column; gap:12px; justify-content:center; }
    .hero .kicker{ font-size:13px; font-weight:800; color:var(--accent-2); background: linear-gradient(90deg, rgba(255,77,210,0.08), rgba(0,255,247,0.06)); padding:6px 10px; border-radius:999px; display:inline-block; }
    .hero p.lead{ font-size: clamp(16px, 1.6vw, 18px); color:var(--muted); max-width:72ch; }

    /* floating cinematic overlay shapes */
    .float-shape{ position:absolute; pointer-events:none; filter: blur(36px); mix-blend-mode:screen; opacity:.12; }

    /* floating cards (community links) */
    .cards-grid{ display:grid; gap:14px; grid-template-columns: repeat(auto-fit, minmax(220px,1fr)); margin-top:18px; }
    .card-ui{
      border-radius:16px; padding:16px; background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border:1px solid rgba(255,255,255,0.03); display:flex; gap:12px; align-items:center; transition: transform .36s var(--easing), box-shadow .36s var(--easing);
      transform-style: preserve-3d;
    }
    .card-ui i{ font-size:20px; color:var(--accent-1); min-width:34px; text-align:center; }
    .card-ui:hover{ transform: translateY(-10px) rotateX(3deg) rotateY(-4deg) scale(1.02); box-shadow: 0 24px 60px rgba(0,0,0,0.45); }
    .card-ui .meta{ display:flex; flex-direction:column; gap:4px; }

    /* team */
    .team-grid{ display:grid; gap:16px; grid-template-columns: repeat(auto-fit, minmax(150px,1fr)); margin-top:12px; }
    .member{
      background: linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.01));
      padding:12px; border-radius:14px; border:1px solid rgba(255,255,255,0.03); text-align:center; transition: transform .3s var(--easing), box-shadow .3s var(--easing);
      cursor:pointer;
    }
    .member:hover{ transform: translateY(-8px); box-shadow: 0 18px 48px rgba(0,0,0,0.45); }
    .member strong{ display:block; margin-bottom:6px; color:var(--accent-1); }

    /* testimonial carousel (simple) */
    .testimonials{ margin-top:22px; display:flex; gap:12px; overflow:hidden; }
    .testimonial{ min-width:260px; padding:14px; border-radius:12px; border:1px solid rgba(255,255,255,0.03); background: linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.01)); box-shadow: 0 10px 30px rgba(0,0,0,0.45); }

    /* roadmap timeline */
    .timeline{ margin-top:18px; padding-left:6px; border-left:2px solid rgba(255,255,255,0.03); display:flex; flex-direction:column; gap:14px; }
    .timeline .item{ position:relative; padding-left:18px; }
    .timeline .dot{ position:absolute; left:-9px; top:6px; width:14px; height:14px; border-radius:50%; background:linear-gradient(90deg,var(--accent-1),var(--accent-2)); box-shadow: 0 6px 18px rgba(0,0,0,0.35); }

    /* modal & contact floating button */
    .floating-contact{
      position:fixed; right:20px; bottom:22px; z-index:200; width:60px; height:60px; border-radius:999px;
      display:flex; align-items:center; justify-content:center; background: linear-gradient(90deg,var(--accent-1),var(--accent-2));
      box-shadow: 0 14px 44px rgba(0,0,0,0.45); color:#071020; font-size:20px; cursor:pointer; border: 1px solid rgba(255,255,255,0.06);
    }
    .floating-contact:focus{ outline:3px solid rgba(255,255,255,0.06) }

    .modal-backdrop{ position:fixed; inset:0; display:none; align-items:center; justify-content:center; background: linear-gradient(180deg, rgba(0,0,0,0.6), rgba(0,0,0,0.8)); z-index:220; }
    .modal{ width:92%; max-width:520px; background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); border-radius:14px; padding:18px; border:1px solid rgba(255,255,255,0.03); box-shadow: var(--shadow-1) }

    /* footer */
    footer.site-footer{ margin-top:36px; padding:22px 0; text-align:center; color:var(--muted); border-top:1px solid rgba(255,255,255,0.03); background: linear-gradient(180deg, rgba(0,0,0,0.02), transparent); }

    /* scroll top */
    .scroll-top{ position:fixed; right:20px; bottom:96px; width:48px; height:48px; border-radius:10px; display:flex; align-items:center; justify-content:center; background:rgba(255,255,255,0.02); border:1px solid rgba(255,255,255,0.03); color:var(--accent-1); cursor:pointer; opacity:0; visibility:hidden; transition: all .3s var(--easing); z-index:180; }
    .scroll-top.show{ opacity:1; visibility:visible; transform: translateY(-6px); }

    /* preloader: custom animated rings */
    .preloader{
      position:fixed; inset:0; display:flex; align-items:center; justify-content:center; z-index:9999; background: linear-gradient(180deg, rgba(0,0,0,0.6), rgba(0,0,0,0.75));
    }
    .loader-wrap{ display:flex; align-items:center; gap:12px; flex-direction:column; color:var(--accent-1); }
    .loader-svg{ width:96px; height:96px; filter: drop-shadow(0 10px 40px rgba(0,0,0,0.6)); }
    .loader-tag{ font-weight:700; letter-spacing:0.6px; color:var(--muted) }

    /* responsive tweaks */
    @media (min-width:900px){
      .hero{ grid-template-columns: 60% 40%; }
      .hero-inner{ flex-direction:row; gap:28px; padding:36px; }
      .hero-visual{ min-height:320px; }
      .hero-caption{ padding-right:12px; }
    }
    @media (max-width:900px){
      .nav-links{ display:none; }
      .hamburger{ display:inline-block; }
      .mobile-menu{ display:none; }
    }

    /* tiny helpers */
    .muted{ color: var(--muted); }
    .accent-1{ color:var(--accent-1) }
    .btn{ padding:10px 14px; border-radius:10px; background: linear-gradient(90deg,var(--accent-1),var(--accent-2)); color:#071020; font-weight:800; border:0; cursor:pointer; box-shadow: 0 8px 30px rgba(0,0,0,0.28) }
    .btn.ghost{ background:transparent; border:1px solid rgba(255,255,255,0.04); color:var(--accent-1); font-weight:700 }
    a.card-link{ color:inherit; text-decoration:none; }

    /* accessibility focus */
    :focus{ outline: 3px solid rgba(0,255,247,0.12); outline-offset:3px; border-radius:6px }
  </style>
</head>
<body data-theme="dark">
  <!-- PRELOADER -->
  <div class="preloader" id="preloader" aria-hidden="false" role="status" aria-label="Loading">
    <div class="loader-wrap" role="presentation">
      <!-- small vector loader for crispness -->
      <svg class="loader-svg" viewBox="0 0 100 100" aria-hidden="true" focusable="false">
        <defs>
          <linearGradient id="lg1" x1="0" x2="1"><stop offset="0" stop-color="#00fff7"/><stop offset="1" stop-color="#ff4dd2"/></linearGradient>
        </defs>
        <g transform="translate(50,50)">
          <circle r="28" fill="none" stroke="rgba(255,255,255,0.03)" stroke-width="14"></circle>
          <path d="M -28 0 A 28 28 0 0 1 28 0" stroke="url(#lg1)" stroke-linecap="round" stroke-width="14" fill="none">
            <animateTransform attributeName="transform" type="rotate" from="0" to="360" dur="1.6s" repeatCount="indefinite"/>
          </path>
        </g>
      </svg>
      <div class="loader-tag">SpotlixHQ</div>
    </div>
  </div>

  <!-- NAVBAR -->
  <header class="wrap" aria-hidden="false">
    <nav class="navbar" role="navigation" aria-label="Main Navigation">
      <div class="brand" aria-hidden="false">
        <!-- inline svg logo -->
        <svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" focusable="false">
          <defs>
            <linearGradient id="g1" x1="0" x2="1"><stop offset="0" stop-color="#00fff7"/><stop offset="1" stop-color="#ff4dd2"/></linearGradient>
          </defs>
          <circle cx="32" cy="32" r="28" fill="url(#g1)" opacity="0.12"/>
          <path d="M20 40c4-7 16-7 20 0" stroke="url(#g1)" stroke-width="3" stroke-linecap="round" fill="none"/>
          <circle cx="32" cy="24" r="6" fill="url(#g1)"/>
        </svg>
        <div>
          <div class="title">SpotlixHQ</div>
          <div style="font-size:11px;color:var(--muted);margin-top:2px">Spotlight Squad • Creators & Collaborators</div>
        </div>
      </div>

      <div class="nav-links" role="menu" aria-label="Primary">
        <a href="#home" role="menuitem" id="link-home">Home</a>
        <a href="#about" role="menuitem" id="link-about">About</a>
        <a href="#community" role="menuitem" id="link-community">Community</a>
        <a href="#team" role="menuitem" id="link-team">Team</a>
        <a href="#contact" role="menuitem" id="link-contact">Contact</a>
      </div>

      <div class="nav-actions" role="group" aria-label="Utility actions">
        <div class="socials" aria-hidden="false">
          <a class="nav-social-link" href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener" aria-label="Instagram"><i class="fab fa-instagram" aria-hidden="true"></i></a>
          <a class="nav-social-link" href="https://t.me/SpotlixHQ" target="_blank" rel="noopener" aria-label="Telegram"><i class="fab fa-telegram" aria-hidden="true"></i></a>
          <a class="nav-social-link" href="https://www.youtube.com/@SpotlixHQ" target="_blank" rel="noopener" aria-label="YouTube"><i class="fab fa-youtube" aria-hidden="true"></i></a>
        </div>

        <select id="language-select" aria-label="Select language" title="Select Language">
          <option value="en">English</option>
          <option value="hi">हिंदी</option>
          <option value="de">Deutsch</option>
          <option value="ja">日本語</option>
          <option value="es">Español</option>
          <option value="fr">Français</option>
          <option value="ar">العربية</option>
          <option value="id">Bahasa Indonesia</option>
          <option value="bn">বাংলা</option>
          <option value="zh">中文</option>
        </select>

        <button id="themeToggle" title="Toggle theme" aria-pressed="false" style="background:transparent;border:0;color:var(--accent-1);padding:8px;margin-left:8px"><i class="fas fa-sun" aria-hidden="true"></i></button>

        <button class="hamburger" id="hamburger" aria-label="Open menu" aria-expanded="false"><i class="fas fa-bars" aria-hidden="true"></i></button>
      </div>
    </nav>

    <!-- mobile menu -->
    <div id="mobileMenu" class="mobile-menu" aria-hidden="true">
      <a href="#home">Home</a>
      <a href="#about">About</a>
      <a href="#community">Community</a>
      <a href="#team">Team</a>
      <a href="#contact">Contact</a>
      <hr style="border:none;height:1px;background:rgba(255,255,255,0.03);margin:8px 0">
      <a href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener">Instagram</a>
      <a href="https://t.me/SpotlixHQ" target="_blank" rel="noopener">Telegram</a>
      <a href="https://www.youtube.com/@SpotlixHQ" target="_blank" rel="noopener">YouTube</a>
      <a href="mailto:spotlixhq@gmail.com">Email</a>
    </div>
  </header>

  <main class="wrap" id="main" role="main">
    <!-- HERO -->
    <section id="home" class="hero" aria-labelledby="homeHeading">
      <div class="hero-inner" role="region" aria-label="Hero">
        <div class="hero-caption">
          <div class="kicker">Spotlight Squad</div>
          <h1 id="homeHeading">Creators. Thinkers. Collaborators.</h1>
          <p class="lead" id="hero-lead">A cinematic home for creators who want to build, collaborate and launch content with impact. We run collabs, tutorials, & creative sprints — all community-first.</p>

          <div style="display:flex;gap:12px;align-items:center;margin-top:8px;">
            <button class="btn" id="joinBtn">Join the Squad</button>
            <button class="btn ghost" id="viewRoadmap">View Roadmap</button>
            <div style="margin-left:auto; text-align:right;">
              <div style="font-size:12px; color:var(--muted)">Subscribers</div>
              <div id="subscriberCount" style="font-weight:800;font-size:18px;color:var(--accent-1)">—</div>
            </div>
          </div>

          <!-- dynamic typed headline -->
          <div style="margin-top:12px; font-weight:700; color:var(--accent-2)" id="typedText" aria-live="polite"></div>
        </div>

        <div class="hero-visual" aria-hidden="true">
          <!-- cinematic mock visual — can be replaced with hero image or Lottie -->
          <div style="width:88%; height:80%; border-radius:12px; background:
            linear-gradient(135deg, rgba(0,255,247,0.06), rgba(255,77,210,0.04));
            display:flex; align-items:center; justify-content:center; flex-direction:column; padding:16px;">
            <div style="width:80%; height:60%; border-radius:10px; background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); display:flex; align-items:center; justify-content:center; box-shadow: 0 12px 40px rgba(0,0,0,0.45);">
              <div style="text-align:center;">
                <div style="font-weight:800; font-size:20px; color:var(--accent-1)">SpotlixHQ</div>
                <div style="font-size:12px; color:var(--muted); margin-top:6px">Creative collabs, tutorials, and community growth</div>
              </div>
            </div>
          </div>

          <!-- cinematic floating shapes -->
          <div class="float-shape" style="width:180px;height:180px;background:linear-gradient(90deg,var(--accent-1),var(--accent-2));top:-20%;left:-10%;border-radius:50%;"></div>
          <div class="float-shape" style="width:240px;height:240px;background:linear-gradient(90deg,var(--accent-2),var(--accent-1));bottom:-20%;right:-10%;border-radius:28%;"></div>
        </div>

        <!-- cards under hero -->
        <div class="cards-grid" role="list" aria-label="Community links">
          <a class="card-ui card-link" href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener" role="listitem" aria-label="Instagram">
            <i class="fab fa-instagram" aria-hidden="true"></i>
            <div class="meta">
              <div style="font-weight:800">Instagram</div>
              <div style="font-size:13px;color:var(--muted)">Share reels, posts and be featured</div>
            </div>
          </a>

          <a class="card-ui card-link" href="https://t.me/SpotlixHQ" target="_blank" rel="noopener" role="listitem" aria-label="Telegram">
            <i class="fab fa-telegram" aria-hidden="true"></i>
            <div class="meta">
              <div style="font-weight:800">Telegram</div>
              <div style="font-size:13px;color:var(--muted)">Live chat, collab threads and announcements</div>
            </div>
          </a>

          <a class="card-ui card-link" href="https://www.youtube.com/@SpotlixHQ" target="_blank" rel="noopener" role="listitem" aria-label="YouTube">
            <i class="fab fa-youtube" aria-hidden="true"></i>
            <div class="meta">
              <div style="font-weight:800">YouTube</div>
              <div style="font-size:13px;color:var(--muted)">Tutorials, collab showcases & playlists</div>
            </div>
          </a>

          <a class="card-ui card-link" href="mailto:spotlixhq@gmail.com" role="listitem" aria-label="Email">
            <i class="fas fa-envelope" aria-hidden="true"></i>
            <div class="meta">
              <div style="font-weight:800">Email</div>
              <div style="font-size:13px;color:var(--muted)">Direct collaboration & press</div>
            </div>
          </a>

        </div>
      </div>
    </section>

    <!-- ABOUT (dedicated page feel) -->
    <section id="about" aria-labelledby="about-title" style="padding-top:24px;">
      <article class="container">
        <h2 id="about-title">About SpotlixHQ</h2>
        <p id="about-desc" style="margin-top:8px; max-width:70ch;">
          SpotlixHQ (Spotlight Squad) is a creator-first community where content makers, storytellers and innovators collaborate to build things that get noticed.
          We run creator collabs, weekly feedback sessions, and workshops — and we help members grow sustainably across platforms.
        </p>

        <div style="display:flex; gap:14px; margin-top:18px; flex-wrap:wrap; align-items:center;">
          <button class="btn" id="openContact">Contact Us</button>
          <a class="btn ghost" href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener">Follow on Instagram</a>

          <!-- vision + metrics card -->
          <div style="margin-left:auto; display:flex; gap:10px; align-items:center;">
            <div style="background:var(--panel); padding:12px; border-radius:12px; border:1px solid rgba(255,255,255,0.03)">
              <div style="font-size:12px;color:var(--muted)">Active members</div>
              <div style="font-weight:800; color:var(--accent-1); font-size:18px">1.2k+</div>
            </div>
            <div style="background:var(--panel); padding:12px; border-radius:12px; border:1px solid rgba(255,255,255,0.03)">
              <div style="font-size:12px;color:var(--muted)">Collabs/month</div>
              <div style="font-weight:800; color:var(--accent-2); font-size:18px">3–5</div>
            </div>
          </div>
        </div>

        <!-- roadmap -->
        <h3 style="margin-top:22px; color:var(--muted)">Roadmap</h3>
        <div class="timeline" aria-label="Roadmap timeline">
          <div class="item"><div class="dot"></div><strong>Q4 2025</strong> — Launch creator fellowship & monthly mini-grants.</div>
          <div class="item"><div class="dot"></div><strong>Q1 2026</strong> — Public events + collab marketplace beta.</div>
          <div class="item"><div class="dot"></div><strong>Q2 2026</strong> — Expand mentorship program; create resource hub.</div>
        </div>
      </article>
    </section>

    <!-- COMMUNITY -->
    <section id="community" aria-labelledby="community-title" style="padding-top:24px;">
      <article class="container">
        <h2 id="community-title">Connect With Us</h2>
        <p style="margin-top:8px; color:var(--muted)">Join where it fits you — we host content on Instagram, Telegram, YouTube and more.</p>

        <div class="cards-grid" style="margin-top:12px;">
          <!-- same 4 cards but bigger layouts -->
          <a class="card-ui card-link" href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener">
            <i class="fab fa-instagram"></i>
            <div class="meta"><div style="font-weight:800">Instagram</div><div style="font-size:13px;color:var(--muted)">Shorts, reels, features & spotlights</div></div>
          </a>

          <a class="card-ui card-link" href="https://t.me/SpotlixHQ" target="_blank" rel="noopener">
            <i class="fab fa-telegram"></i>
            <div class="meta"><div style="font-weight:800">Telegram</div><div style="font-size:13px;color:var(--muted)">Live chats, collab calls</div></div>
          </a>

          <a class="card-ui card-link" href="https://www.youtube.com/@SpotlixHQ" target="_blank" rel="noopener">
            <i class="fab fa-youtube"></i>
            <div class="meta"><div style="font-weight:800">YouTube</div><div style="font-size:13px;color:var(--muted)">Workshops & series</div></div>
          </a>

          <a class="card-ui card-link" href="mailto:spotlixhq@gmail.com">
            <i class="fas fa-envelope"></i>
            <div class="meta"><div style="font-weight:800">Email</div><div style="font-size:13px;color:var(--muted)">Proposals and collabs</div></div>
          </a>
        </div>

        <!-- Testimonials -->
        <h3 style="margin-top:20px;">Testimonials</h3>
        <div class="testimonials" aria-live="polite">
          <div class="testimonial">
            <div style="font-weight:800; color:var(--accent-1)">Riya — Creator</div>
            <div style="font-size:13px;color:var(--muted); margin-top:6px">“The collab I joined from Spotlix got my channel real traction — loved the feedback rounds.”</div>
          </div>
          <div class="testimonial">
            <div style="font-weight:800; color:var(--accent-2)">Aman — Filmmaker</div>
            <div style="font-size:13px;color:var(--muted);margin-top:6px">“Organised, creative and community-driven. The roadmap looks premium.”</div>
          </div>
        </div>
      </article>
    </section>

    <!-- TEAM -->
    <section id="team" aria-labelledby="team-title" style="padding-top:24px;">
      <article class="container">
        <h2 id="team-title">Our Team</h2>
        <p style="margin-top:8px; color:var(--muted)">Small core team, big ambitions.</p>

        <div class="team-grid">
          <div class="member" tabindex="0" role="button" aria-pressed="false" onclick="toggleBio(this)" onkeypress="if(event.key==='Enter'){toggleBio(this)}" aria-label="Suryansh, Founder">
            <strong>Suryansh</strong>
            <div style="font-size:.92rem;opacity:.9">Founder</div>
            <div class="bio" style="margin-top:8px; display:none; color:var(--accent-1); font-size:.9rem">
              Creative lead & community growth. <br />
              <a href="https://www.instagram.com/suryansh_y09?igsh=MXIzNGhmMGtlZjY4eQ==" target="_blank" rel="noopener">Instagram</a> |
              <a href="mailto:suryanshy302@gmail.com">Email</a>
            </div>
          </div>

          <div class="member" tabindex="0" role="button" aria-pressed="false" onclick="toggleBio(this)" onkeypress="if(event.key==='Enter'){toggleBio(this)}" aria-label="Anup, Team member">
            <strong>Anup</strong>
            <div style="font-size:.92rem;opacity:.9">Team Member</div>
            <div class="bio" style="margin-top:8px; display:none; color:var(--accent-1); font-size:.9rem">
              Production & ops. <br />
              <a href="https://www.instagram.com/anup_.45_45?igsh=cDhuY3plOGVxaXhw" target="_blank" rel="noopener">Instagram</a> |
              <a href="mailto:gurub0357@gmail.com">Email</a>
            </div>
          </div>

          <!-- Add more members easily -->
        </div>
      </article>
    </section>

    <!-- CONTACT / dedicated page -->
    <section id="contact" aria-labelledby="contact-title" style="padding-top:24px;">
      <article class="container">
        <h2 id="contact-title">Contact & Collaborate</h2>
        <p style="margin-top:8px; color:var(--muted)">Prefer email? Want to submit a collab? Use any method below.</p>

        <div style="display:flex; gap:12px; margin-top:12px; flex-wrap:wrap; align-items:center;">
          <a class="btn" href="mailto:spotlixhq@gmail.com">✉️ Email Us</a>
          <a class="btn ghost" target="_blank" rel="noopener" href="https://t.me/SpotlixHQ">💬 Telegram</a>
          <a class="btn ghost" target="_blank" rel="noopener" href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo">📸 Instagram</a>
        </div>

        <div style="margin-top:18px;">
          <label for="collabMessage" style="display:block;font-weight:700;margin-bottom:6px;color:var(--muted)">Quick message</label>
          <textarea id="collabMessage" rows="4" style="width:100%;border-radius:10px;padding:12px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:var(--muted)"></textarea>
          <div style="display:flex; gap:8px; margin-top:8px;">
            <button class="btn" id="sendMsg">Send</button>
            <div id="formStatus" style="align-self:center;color:var(--success);display:none">Message prepared (demo)</div>
          </div>
        </div>
      </article>
    </section>

    <!-- small footer info -->
    <footer class="site-footer">
      <div class="wrap" style="display:flex;flex-direction:column;gap:8px;align-items:center">
        <div style="font-weight:700">Proudly Indian Made 🌟</div>
        <div style="font-size:13px;color:var(--muted)">© <span id="year">2025</span> SpotlixHQ. All rights reserved.</div>
        <div style="font-size:12px;color:var(--muted); margin-top:8px">Built with love — <a href="https://spotlix.github.io/SpotlixHQ-/" target="_blank" rel="noopener" style="color:var(--accent-1)">spotlix.github.io</a></div>
      </div>
    </footer>
  </main>

  <!-- floating contact + scroll top -->
  <button class="floating-contact" id="floatingContact" aria-label="Contact SpotlixHQ" title="Contact us (quick)">
    <i class="fas fa-comment-dots" aria-hidden="true"></i>
  </button>
  <button class="scroll-top" id="scrollTop" aria-label="Back to top" title="Back to top"><i class="fas fa-chevron-up"></i></button>

  <!-- modal contact -->
  <div class="modal-backdrop" id="modalBackdrop" aria-hidden="true">
    <div class="modal" role="dialog" aria-modal="true" aria-labelledby="contactTitle">
      <h3 id="contactTitle">Contact SpotlixHQ</h3>
      <p>Reach us through any of the links or copy the email below:</p>
      <div style="display:flex;gap:.6rem;align-items:center;flex-wrap:wrap">
        <button class="btn" id="copyEmail" title="Copy email to clipboard">📧 Copy Email</button>
        <a class="btn" href="mailto:spotlixhq@gmail.com">✉️ Open Email</a>
        <a class="btn" target="_blank" rel="noopener" href="https://t.me/SpotlixHQ">💬 Telegram</a>
      </div>
      <div class="copy-success" id="copySuccess" role="status" aria-live="polite" style="display:none;margin-top:10px;color:var(--success)">Email copied to clipboard ✓</div>
      <div style="height:10px"></div>
      <div style="display:flex;gap:.5rem;justify-content:flex-end;">
        <button class="btn ghost" id="closeModal">Close</button>
      </div>
    </div>
  </div>

  <!-- Languages content object and minimal script -->
  <script>
    /* =========================
       SpotlixHQ — Upgraded JS
       - All original features preserved (languages, emails, mobile menu, team bios)
       - New: theme toggle, floating contact, smooth scroll, preloader, roadmap modal, subscriber widget
       - Clean, modular functions, comments included
       ========================= */

    // ---------- Helper selectors ----------
    const $ = (sel, root=document) => root.querySelector(sel);
    const $$ = (sel, root=document) => Array.from(root.querySelectorAll(sel));

    // set year
    document.getElementById('year').textContent = new Date().getFullYear();

    // ---------- Preloader fade ----------
    window.addEventListener('load', () => {
      const pre = $('#preloader');
      if(pre){
        pre.classList.add('hidden');
        pre.setAttribute('aria-hidden', 'true');
        setTimeout(()=> pre.remove(), 700);
      }
    });

    // ---------- Intersection observer for reveal animations ----------
    const sections = $$('main section');
    const io = new IntersectionObserver((entries)=>{
      entries.forEach(e=>{
        if(e.isIntersecting) e.target.classList.add('active');
      });
    }, { threshold: 0.18 });
    sections.forEach(s => io.observe(s));

    // ---------- Smooth scroll for internal nav ----------
    $$('#link-home, #link-about, #link-community, #link-team, #link-contact, .nav-links a').forEach(a=>{
      a.addEventListener('click', (ev)=>{
        const href = a.getAttribute('href')||'';
        if(href.startsWith('#')){
          ev.preventDefault();
          const el = document.querySelector(href);
          if(el) el.scrollIntoView({behavior:'smooth', block:'start'});
        }
        // close mobile menu on click
        if(window.innerWidth < 900){
          closeMobileMenu();
        }
      });
    });

    // ---------- Typing headline (hero) ----------
    const phrases = [
      "Creators. Thinkers. Collaborators.",
      "Where Ideas Meet Action.",
      "Grow, Share, Connect.",
      "Made for community-first creators.",
      "Your next idea starts here."
    ];
    let phI=0, phJ=0, phDeleting=false;
    const typedEl = document.getElementById('typedText');
    function typeLoop(){
      if(!typedEl) return;
      if(phI >= phrases.length) phI = 0;
      const cur = phrases[phI];
      if(!phDeleting){
        typedEl.textContent = cur.slice(0, phJ+1);
        phJ++;
        if(phJ === cur.length){ phDeleting=true; setTimeout(typeLoop, 1000); return; }
      } else {
        typedEl.textContent = cur.slice(0, phJ-1);
        phJ--;
        if(phJ === 0){ phDeleting=false; phI++; }
      }
      setTimeout(typeLoop, phDeleting ? 40 : 80);
    }
    if(typedEl) typeLoop();

    // ---------- Toggle team bios (preserve behavior) ----------
    function toggleBio(el){
      const bio = el.querySelector('.bio');
      if(!bio) return;
      const expanded = bio.classList.toggle('show-bio');
      bio.style.display = bio.classList.contains('show-bio') ? 'block' : 'none';
      el.setAttribute('aria-pressed', expanded ? 'true' : 'false');
    }
    window.toggleBio = toggleBio;

    // ---------- Scroll-to-top ----------
    const scrollTopBtn = $('#scrollTop');
    window.addEventListener('scroll', () => {
      if(window.scrollY > 300) scrollTopBtn.classList.add('show'); else scrollTopBtn.classList.remove('show');
    });
    scrollTopBtn.addEventListener('click', ()=> window.scrollTo({top:0, behavior:'smooth'}));

    // ---------- Mobile menu logic ----------
    const hamburger = $('#hamburger');
    const mobileMenu = $('#mobileMenu');
    function closeMobileMenu(){ if(mobileMenu){ mobileMenu.style.display='none'; mobileMenu.setAttribute('aria-hidden','true'); hamburger.setAttribute('aria-expanded','false'); } }
    if(hamburger){
      hamburger.addEventListener('click', ()=>{
        const expanded = hamburger.getAttribute('aria-expanded') === 'true';
        hamburger.setAttribute('aria-expanded', String(!expanded));
        if(!expanded){ mobileMenu.style.display='block'; mobileMenu.setAttribute('aria-hidden','false'); const first = mobileMenu.querySelector('a'); if(first) first.focus(); }
        else { closeMobileMenu(); }
      });
    }
    // close mobile menu when clicking a link (already handled earlier)

    // ---------- Contact modal & floating contact button ----------
    const modalBackdrop = $('#modalBackdrop');
    const openContact = $('#openContact');
    const closeModal = $('#closeModal');
    const copyEmailBtn = $('#copyEmail');
    const copySuccess = $('#copySuccess');
    const floatingContact = $('#floatingContact');

    function openModal(){ if(!modalBackdrop) return; modalBackdrop.style.display='flex'; modalBackdrop.setAttribute('aria-hidden','false'); setTimeout(()=> copyEmailBtn && copyEmailBtn.focus(), 120); }
    function closeModalFunc(){ if(!modalBackdrop) return; modalBackdrop.style.display='none'; modalBackdrop.setAttribute('aria-hidden','true'); openContact && openContact.focus(); copySuccess.style.display='none'; }
    if(openContact) openContact.addEventListener('click', openModal);
    if(closeModal) closeModal.addEventListener('click', closeModalFunc);
    if(modalBackdrop) modalBackdrop.addEventListener('click', (e)=>{ if(e.target === modalBackdrop) closeModalFunc(); });
    if(floatingContact) floatingContact.addEventListener('click', openModal);

    if(copyEmailBtn){
      copyEmailBtn.addEventListener('click', async ()=>{
        try{
          await navigator.clipboard.writeText('spotlixhq@gmail.com');
          copySuccess.style.display = 'block';
          setTimeout(()=> copySuccess.style.display = 'none', 2600);
        } catch(e){
          copySuccess.textContent = 'Could not copy — please copy manually.';
          copySuccess.style.display = 'block';
          setTimeout(()=> { copySuccess.style.display = 'none'; copySuccess.textContent = 'Email copied to clipboard ✓'; }, 2600);
        }
      });
    }

    // ---------- Contact quick send (demo) ----------
    const sendMsg = $('#sendMsg');
    const formStatus = $('#formStatus');
    if(sendMsg){
      sendMsg.addEventListener('click', ()=>{
        // demo behaviour; implement server endpoint to actually send
        if(formStatus){ formStatus.style.display='block'; setTimeout(()=> formStatus.style.display='none', 2400); }
      });
    }

    // ---------- Theme toggle (auto + manual) ----------
    const themeToggle = $('#themeToggle');
    function setTheme(theme){
      document.documentElement.setAttribute('data-theme', theme);
      themeToggle.setAttribute('aria-pressed', theme==='light' ? 'true' : 'false');
      themeToggle.innerHTML = theme==='light' ? '<i class="fas fa-moon"></i>' : '<i class="fas fa-sun"></i>';
      localStorage.setItem('spotlix_theme', theme);
    }

    // initialization: check saved or system preference
    const savedTheme = localStorage.getItem('spotlix_theme');
    if(savedTheme) setTheme(savedTheme);
    else {
      const prefersLight = window.matchMedia && window.matchMedia('(prefers-color-scheme: light)').matches;
      setTheme(prefersLight ? 'light' : 'dark');
    }

    if(themeToggle){
      themeToggle.addEventListener('click', ()=>{
        const current = document.documentElement.getAttribute('data-theme') || 'dark';
        setTheme(current === 'dark' ? 'light' : 'dark');
      });
    }

    // ---------- Keyboard accessibility (Escape closes menus/modals) ----------
    document.addEventListener('keydown', (e)=>{
      if(e.key === 'Escape'){
        if(mobileMenu && mobileMenu.style.display === 'block') closeMobileMenu();
        if(modalBackdrop && modalBackdrop.style.display === 'flex') closeModalFunc();
      }
    });

    // ---------- Tiny progressive enhancement: keyboard nav for nav-links ----------
    $$('.nav-links a').forEach(a=> a.addEventListener('keydown', (e)=>{ if(e.key==='Enter'||e.key===' ') a.click(); }));

    // ---------- Subscriber counter (live or simulated) ----------
    // Two modes:
    // 1) If you provide YOUTUBE_API_KEY and YOUTUBE_CHANNEL_ID below, the live count will fetch from YouTube Data API v3.
    //    See instructions: https://developers.google.com/youtube/v3/docs/channels/list
    // 2) Else it uses a smooth animated simulated counter for demo/visual effect.

    // --- CONFIGURATION: replace with real values to enable live fetch ---
    const YOUTUBE_API_KEY = ''; // <-- paste your YouTube Data API key here (optional)
    const YOUTUBE_CHANNEL_ID = ''; // <-- paste channel id (optional), e.g. UCxxxxx
    // If both are set, the page will attempt to fetch live subscribers. Otherwise, simulated.

    const subscriberEl = document.getElementById('subscriberCount');

    async function fetchYouTubeSubs(){
      if(!YOUTUBE_API_KEY || !YOUTUBE_CHANNEL_ID) return null;
      const url = `https://www.googleapis.com/youtube/v3/channels?part=statistics&id=${encodeURIComponent(YOUTUBE_CHANNEL_ID)}&key=${encodeURIComponent(YOUTUBE_API_KEY)}`;
      try{
        const res = await fetch(url);
        if(!res.ok) throw new Error('YT fetch error');
        const data = await res.json();
        const count = data.items && data.items[0] && data.items[0].statistics && data.items[0].statistics.subscriberCount;
        return Number(count);
      } catch(err){
        console.warn('YouTube API fetch failed:', err);
        return null;
      }
    }

    // Simulated counter animation for fallback
    function animateCounter(target, start=8000, duration=2000){
      const startVal = start;
      const endVal = target;
      const startTime = performance.now();
      function step(now){
        const t = Math.min(1, (now - startTime) / duration);
        const eased = t < 0.5 ? 2*t*t : -1 + (4 - 2*t)*t; // mild ease
        const current = Math.floor(startVal + (endVal - startVal) * eased);
        subscriberEl.textContent = current.toLocaleString();
        if(t < 1) requestAnimationFrame(step);
      }
      requestAnimationFrame(step);
    }

    async function initSubscriberWidget(){
      subscriberEl.textContent = '—';
      // try live
      if(YOUTUBE_API_KEY && YOUTUBE_CHANNEL_ID){
        const live = await fetchYouTubeSubs();
        if(live !== null){
          animateCounter(live, Math.max(1000, Math.floor(live*0.86)), 1500);
          // refresh periodically (e.g., every 5 min)
          setInterval(async ()=> {
            const updated = await fetchYouTubeSubs();
            if(updated) animateCounter(updated, Number(subscriberEl.textContent.replace(/,/g,'')), 900);
          }, 5*60*1000);
          return;
        }
      }
      // else simulated nice count
      const simulated = 12000 + Math.floor(Math.random()*6000); // 12k-18k
      animateCounter(simulated, 8800, 1500);
      // add gentle random ticks to feel alive
      setInterval(()=> {
        const curr = Number(subscriberEl.textContent.replace(/,/g,'')) || 12000;
        const inc = Math.floor(Math.random()*7);
        subscriberEl.textContent = (curr+inc).toLocaleString();
      }, 8000 + Math.random()*8000);
    }
    initSubscriberWidget();

    // ---------- Roadmap modal quick jump ----------
    const viewRoadmap = $('#viewRoadmap');
    if(viewRoadmap){
      viewRoadmap.addEventListener('click', ()=> {
        window.location.href = '#about';
        setTimeout(()=> {
          const tl = document.querySelector('.timeline');
          if(tl) tl.scrollIntoView({behavior:'smooth', block:'start'});
        }, 400);
      });
    }

    // ---------- Copy email by clicking footer or anywhere (extra helper) ----------
    $$('.card-link[href^="mailto:"]').forEach(el=>{
      el.addEventListener('click', ()=> {
        // keep default behaviour; but we also track or show micro-feedback if needed
      });
    });

    // ---------- Tiny perf improvements (defer heavy tasks) ----------
    // Defer non-critical UI (e.g., testimonial auto-scroll)
    setTimeout(()=> {
      // rotate testimonials gently (basic)
      const tWrap = document.querySelector('.testimonials');
      if(tWrap){
        let idx=0;
        setInterval(()=> {
          idx = (idx+1) % (tWrap.children.length || 1);
          tWrap.scrollTo({ left: idx * (tWrap.children[0]?.offsetWidth || 260), behavior:'smooth' });
        }, 4200);
      }
    }, 1000);

    // ---------- Language translations object (keeps previous translations) ----------
    const content = {
      en: {
        navHome: "Home", navAbout: "About", navCommunity: "Community", navTeam: "Team", navContact: "Contact",
        aboutTitle: "About SpotlixHQ",
        aboutDesc: "SpotlixHQ is a community for creators, thinkers, and innovators to collaborate, share ideas, and grow together.",
        communityTitle: "Connect With Us", teamTitle: "Our Team", rtl:false
      },
      hi: {
        navHome: "होम", navAbout: "हमारे बारे में", navCommunity: "समुदाय", navTeam: "टीम", navContact: "संपर्क",
        aboutTitle: "SpotlixHQ के बारे में",
        aboutDesc: "SpotlixHQ रचनाकारों, विचारकों और नवप्रवर्तकों के लिए एक समुदाय है जहाँ वे सहयोग कर सकते हैं, विचार साझा कर सकते हैं और साथ में आगे बढ़ सकते हैं।",
        communityTitle: "हमसे जुड़ें", teamTitle: "हमारी टीम", rtl:false
      },
      de: {
        navHome: "Startseite", navAbout: "Über uns", navCommunity: "Community", navTeam: "Team", navContact: "Kontakt",
        aboutTitle: "Über SpotlixHQ",
        aboutDesc: "SpotlixHQ ist eine Community für Kreative, Denker und Innovatoren, um zusammenzuarbeiten, Ideen zu teilen und gemeinsam zu wachsen.",
        communityTitle: "Vernetze dich mit uns", teamTitle: "Unser Team", rtl:false
      },
      ja: {
        navHome: "ホーム", navAbout: "概要", navCommunity: "コミュニティ", navTeam: "チーム", navContact: "コンタクト",
        aboutTitle: "SpotlixHQ について",
        aboutDesc: "SpotlixHQ は、クリエイターや思考家、イノベーターが協力し、アイデアを共有し、ともに成長するためのコミュニティです。",
        communityTitle: "私たちとつながる", teamTitle: "チーム紹介", rtl:false
      },
      es: {
        navHome: "Inicio", navAbout: "Acerca de", navCommunity: "Comunidad", navTeam: "Equipo", navContact: "Contacto",
        aboutTitle: "Acerca de SpotlixHQ",
        aboutDesc: "SpotlixHQ es una comunidad para creadores, pensadores e innovadores donde pueden colaborar, compartir ideas y crecer juntos.",
        communityTitle: "Conéctate con nosotros", teamTitle: "Nuestro equipo", rtl:false
      },
      fr: {
        navHome: "Accueil", navAbout: "À propos", navCommunity: "Communauté", navTeam: "Équipe", navContact: "Contact",
        aboutTitle: "À propos de SpotlixHQ",
        aboutDesc: "SpotlixHQ est une communauté pour les créateurs, penseurs et innovateurs afin de collaborer, partager des idées et grandir ensemble.",
        communityTitle: "Connectez-vous avec nous", teamTitle: "Notre équipe", rtl:false
      },
      ar: {
        navHome: "الرئيسية", navAbout: "من نحن", navCommunity: "المجتمع", navTeam: "الفريق", navContact: "اتصل",
        aboutTitle: "نبذة عن SpotlixHQ",
        aboutDesc: "SpotlixHQ هو مجتمع للمبدعين والمفكرين والمبتكرين للتعاون وتبادل الأفكار والنمو معًا.",
        communityTitle: "تواصل معنا", teamTitle: "فريقنا", rtl:true
      },
      id: {
        navHome: "Beranda", navAbout: "Tentang", navCommunity: "Komunitas", navTeam: "Tim", navContact: "Kontak",
        aboutTitle: "Tentang SpotlixHQ",
        aboutDesc: "SpotlixHQ adalah komunitas bagi kreator, pemikir, dan inovator untuk berkolaborasi, berbagi ide, dan tumbuh bersama.",
        communityTitle: "Terhubung dengan kami", teamTitle: "Tim kami", rtl:false
      },
      bn: {
        navHome: "হোম", navAbout: "আমাদের সম্পর্কে", navCommunity: "কমিউনিটি", navTeam: "টিম", navContact: "যোগাযোগ",
        aboutTitle: "SpotlixHQ সম্পর্কে",
        aboutDesc: "SpotlixHQ হল সৃষ্টিশীল ব্যক্তি, চিন্তাবিদ এবং উদ্ভাবকদের জন্য একটি কমিউনিটি যেখানে তারা একসাথে কাজ করতে, আইডিয়া শেয়ার করতে এবং একসাথে বেড়ে উঠতে পারে।",
        communityTitle: "আমাদের সাথে যুক্ত হন", teamTitle: "আমাদের দল", rtl:false
      },
      zh: {
        navHome: "首页", navAbout: "关于", navCommunity: "社区", navTeam: "团队", navContact: "联系",
        aboutTitle: "关于 SpotlixHQ",
        aboutDesc: "SpotlixHQ 是一个为创作者、思想者和创新者而建立的社区，在这里可以协作、分享想法并共同成长。",
        communityTitle: "与我们联系", teamTitle: "我们的团队", rtl:false
      }
    };

    const langSelect = document.getElementById('language-select');
    const navHome = document.getElementById('link-home');
    const navAbout = document.getElementById('link-about');
    const navCommunity = document.getElementById('link-community');
    const navTeam = document.getElementById('link-team');
    const navContact = document.getElementById('link-contact');
    const aboutTitleEl = document.getElementById('about-title');
    const aboutDescEl = document.getElementById('about-desc');
    const communityTitleEl = document.getElementById('community-title');
    const teamTitleEl = document.getElementById('team-title');

    function applyLanguage(lang){
      if(!content[lang]) lang='en';
      const t = content[lang];
      if(navHome) navHome.textContent = t.navHome;
      if(navAbout) navAbout.textContent = t.navAbout;
      if(navCommunity) navCommunity.textContent = t.navCommunity;
      if(navTeam) navTeam.textContent = t.navTeam;
      if(navContact) navContact.textContent = t.navContact || 'Contact';
      if(aboutTitleEl) aboutTitleEl.textContent = t.aboutTitle;
      if(aboutDescEl) aboutDescEl.textContent = t.aboutDesc;
      if(communityTitleEl) communityTitleEl.textContent = t.communityTitle;
      if(teamTitleEl) teamTitleEl.textContent = t.teamTitle;
      document.documentElement.lang = lang;
      document.documentElement.dir = t.rtl ? 'rtl' : 'ltr';
      ['about','community','team'].forEach(id=>{
        const el = document.getElementById(id);
        if(!el) return;
        if(t.rtl) el.classList.add('rtl'); else el.classList.remove('rtl');
      });
    }
    if(langSelect){
      langSelect.addEventListener('change', ()=> applyLanguage(langSelect.value));
      // initialize from browser or default
      const browserLang = navigator.language?.slice(0,2) || 'en';
      const initial = content[browserLang] ? browserLang : 'en';
      langSelect.value = initial;
      applyLanguage(initial);
    }

    // ---------- small UX: animated anchor focus on tabbing to in-page content ----------
    window.addEventListener('hashchange', ()=> {
      const el = document.getElementById(location.hash.replace('#',''));
      if(el) el.scrollIntoView({behavior:'smooth', block:'start'});
    });

    // ---------- Performance note: avoid heavy layout thrash ----------
    // Keep event listeners few and delegated where appropriate.

    // End of script
  </script>
</body>
</html>
