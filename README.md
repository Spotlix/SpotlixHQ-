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
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&family=Fraunces:opsz,wght@8..144,700&display=swap" rel="stylesheet">
  <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous" defer></script>

  <style>
    /* ==========================
       VARIABLES & BASE RESET
       ========================== */
    :root{
      --bg-1: #0f0c29;
      --bg-2: #302b63;
      --accent: #00fff7;
      --accent-2: #ff00ff;
      --glass: rgba(255,255,255,0.06);
      --card-bg: rgba(255,255,255,0.04);
      --muted: rgba(255,255,255,0.80);
      --max-width: 1200px;
      --radius: 18px;
      --nav-height: 78px;
      --transition: 280ms cubic-bezier(.2,.9,.2,1);
      --elev: 0 10px 30px rgba(3,10,18,0.6);
      --text: #f7f7f9;
      --glass-border: rgba(255,255,255,0.06);
      --success: #9fffe8;
    }

    /* Light theme */
    :root.light {
      --bg-1: #f5f7fb;
      --bg-2: #eef3fb;
      --accent: #006b66;
      --accent-2: #8a006b;
      --card-bg: rgba(255,255,255,0.65);
      --muted: rgba(14,20,30,0.72);
      --text: #0e141e;
      --glass: rgba(14,20,30,0.04);
      --glass-border: rgba(14,20,30,0.06);
      --elev: 0 10px 30px rgba(6,12,20,0.08);
    }

    *,*::before,*::after{box-sizing:border-box}
    html,body{height:100%;margin:0}
    html{scroll-behavior:smooth}
    body{
      font-family:'Poppins',system-ui,-apple-system,Segoe UI,Roboto,"Helvetica Neue",Arial;
      color:var(--text);
      background: radial-gradient(1200px 600px at 10% 10%, rgba(0,255,247,0.06), transparent),
                  linear-gradient(135deg,var(--bg-1),var(--bg-2) 60%);
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      min-height:100vh;
      overflow-x:hidden;
      line-height:1.45;
      transition: background 400ms ease, color 300ms ease;
    }

    @media (prefers-reduced-motion: reduce){
      *{animation-duration:0.001ms !important; animation-iteration-count:1 !important; transition:none !important}
    }

    /* ==========================
       NAVBAR (PROFESSIONAL)
       ========================== */
    header{position:fixed;top:18px;left:0;right:0;z-index:120;display:flex;justify-content:center;pointer-events:auto}
    nav[role="navigation"]{
      width:calc(100% - 40px);max-width:var(--max-width);
      display:flex;align-items:center;gap:1rem;padding:.7rem 1rem;border-radius:14px;
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      backdrop-filter: blur(8px) saturate(120%);
      border: 1px solid var(--glass-border);
      box-shadow: var(--elev);
      transition: transform 300ms ease, box-shadow 300ms ease, backdrop-filter 300ms ease;
    }
    nav.condensed{ transform: translateY(-6px) scale(.995); box-shadow: 0 4px 20px rgba(0,0,0,0.35); }

    .brand{display:flex;align-items:center;gap:.6rem;flex:0 0 auto;cursor:pointer}
    .brand svg{width:40px;height:40px;filter: drop-shadow(0 6px 20px rgba(0,0,0,0.2));}
    .brand .title{font-weight:800;letter-spacing:.4px;color:var(--accent);font-size:1.05rem}
    .brand .sub{display:block;font-size:.72rem;color:var(--muted);margin-top:-2px}

    .nav-links{display:flex;gap:.9rem;align-items:center;margin-left:16px}
    .nav-links a{color:var(--accent);text-decoration:none;font-weight:600;padding:.45rem .6rem;border-radius:8px;transition:all var(--transition)}
    .nav-links a:hover, .nav-links a:focus{transform:translateY(-3px); text-shadow:0 6px 20px rgba(0,255,247,0.06)}
    .nav-actions{margin-left:auto;display:flex;gap:.6rem;align-items:center}

    .btn {
      display:inline-flex;align-items:center;gap:.6rem;padding:.52rem .8rem;border-radius:10px;border:1px solid transparent;font-weight:700;cursor:pointer;background:linear-gradient(90deg,var(--accent),var(--accent-2));color:#081018;box-shadow:0 6px 20px rgba(0,0,0,0.25);
      transition: transform var(--transition), box-shadow var(--transition), opacity var(--transition);
    }
    .btn.ghost{background:transparent;color:var(--accent);border:1px solid var(--glass-border);box-shadow:none}
    .btn.small{padding:.35rem .55rem;font-weight:600;border-radius:8px}

    .icon-btn{display:inline-flex;align-items:center;justify-content:center;padding:.45rem;border-radius:10px;background:transparent;border:1px solid transparent;color:var(--accent);cursor:pointer}
    .icon-btn:focus{outline:2px solid rgba(0,255,247,0.08);outline-offset:2px}

    #language-select{background:transparent;border:1px solid rgba(255,255,255,0.03);padding:.28rem .46rem;border-radius:6px;color:var(--accent);font-weight:600}

    /* Mobile */
    .hamburger{display:none;background:transparent;border:0;color:var(--accent);font-size:1.2rem;padding:.4rem}
    @media (max-width:900px){
      .nav-links{display:none}
      .hamburger{display:inline-flex}
    }

    /* ==========================
       HERO — CINEMATIC + GLASS
       ========================== */
    .hero{
      min-height: calc(100vh - var(--nav-height));
      display:flex;align-items:center;justify-content:center;padding:20vh 18px 8vh;position:relative;z-index:2;
      overflow:visible;
    }

    /* cinematic background video */
    .hero-media{
      position:absolute;inset:0;z-index:0;overflow:hidden;border-radius:0;
    }
    .hero-media video{ width:100%; height:100%; object-fit:cover; opacity:.55; transform: scale(1.03); filter: saturate(1.05) contrast(.98); }
    .hero-overlay{
      position:absolute;inset:0; background: linear-gradient(180deg, rgba(6,8,15,0.28), rgba(3,3,12,0.5));
      mix-blend-mode: normal; z-index:1;
    }

    .hero-inner{ position:relative; z-index:2; max-width:var(--max-width); width:100%; padding:3rem; display:flex; gap:2rem; align-items:center; justify-content:center; }
    .hero-card{
      background: linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.02));
      border-radius:20px; padding:2.2rem; width:100%; max-width:960px;
      border: 1px solid var(--glass-border);
      backdrop-filter: blur(10px) saturate(120%);
      box-shadow: 0 18px 60px rgba(2,7,22,0.6);
      transform-origin:center;
      transition: transform 600ms cubic-bezier(.2,.9,.2,1), box-shadow 300ms;
    }
    .hero-card:hover{ transform: translateY(-6px) rotateX(1deg); box-shadow:0 30px 90px rgba(2,7,22,0.7) }

    .hero-title{ font-family:'Fraunces', Georgia, serif; font-weight:700; font-size:2.6rem; color:var(--accent); margin:0 0 .4rem; letter-spacing:.6px; text-shadow: 0 6px 30px rgba(0,255,247,0.06) }
    .hero-strap{ font-size:1.05rem; color:var(--muted); margin-bottom:1rem; max-width:70ch }
    .typing{ color:var(--accent); font-weight:700; height:36px; overflow:hidden; border-right:2px solid var(--accent); white-space:nowrap; animation: blink .8s step-end infinite; margin-bottom:1rem}
    @keyframes blink{50%{border-color:transparent}}

    .hero-ctas{ display:flex; gap:.8rem; margin-top:1.1rem; flex-wrap:wrap }
    .cta-primary { display:inline-flex; align-items:center; gap:.6rem }
    .cta-secondary { background:transparent; border:1px solid var(--glass-border); color:var(--accent); padding:.5rem .85rem; border-radius:10px }

    /* cinematic accent lines & floating cards */
    .accent-grid{ display:grid; grid-template-columns:repeat(3,1fr); gap:1rem; margin-top:1.2rem }
    .floating-card{
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius:14px; padding:1rem; border:1px solid rgba(255,255,255,0.03);
      transform: translateY(0);
      transition: transform 450ms var(--transition), box-shadow 450ms var(--transition);
      will-change:transform;
    }
    .floating-card:hover{ transform: translateY(-10px) rotateX(2deg); box-shadow: 0 18px 60px rgba(0,0,0,0.45) }

    /* hero visual note */
    .hero-visual { width:300px; height:160px; border-radius:10px; overflow:hidden; display:block; border:1px solid rgba(255,255,255,0.04); box-shadow: 0 10px 30px rgba(0,0,0,0.4) }

    /* ==========================
       SECTION CONTAINERS
       ========================== */
    main{padding-top: calc(var(--nav-height) + 28px)}
    section { padding:6rem 18px; display:block; position:relative; }
    .wrap{ max-width:var(--max-width); margin:0 auto; width:100% }

    .section-head { text-align:center; margin-bottom:2rem }
    .section-title { font-family:'Fraunces', serif; font-weight:700; font-size:1.6rem; color:var(--accent) }
    .section-sub { color:var(--muted); margin-top:.4rem; max-width:72ch; margin-left:auto; margin-right:auto }

    /* ==========================
       CONNECT CARDS (FLOATING)
       ========================== */
    .connect-grid{ display:grid; grid-template-columns:repeat(4,1fr); gap:1rem; margin-top:1.6rem }
    .connect-card{ background:linear-gradient(180deg, rgba(0,0,0,0.06), rgba(255,255,255,0.01)); border-radius:12px; padding:1.05rem; display:flex; gap:.9rem; align-items:center; border:1px solid rgba(255,255,255,0.03); transition: transform 260ms var(--transition), box-shadow 260ms }
    .connect-card:hover{ transform: translateY(-8px); box-shadow:0 18px 60px rgba(0,0,0,0.5) }
    .connect-card i{font-size:1.5rem; color:var(--accent)}
    .connect-card .meta{ color:var(--muted); font-weight:700 }

    @media (max-width:1100px){ .connect-grid{ grid-template-columns:repeat(2,1fr)} .accent-grid{ grid-template-columns:repeat(2,1fr) } }
    @media (max-width:640px){ .connect-grid{ grid-template-columns:1fr } }

    /* ==========================
       TEAM (3D HOVER)
       ========================== */
    .team-grid{ display:grid; grid-template-columns:repeat(4,1fr); gap:1rem; margin-top:1.2rem; align-items:start }
    .member-card{ background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); border-radius:14px; padding:1rem; text-align:center; transform-style:preserve-3d; perspective:1200px; transition: transform 480ms cubic-bezier(.2,.9,.2,1); border:1px solid rgba(255,255,255,0.03) }
    .member-card:hover{ transform: translateY(-8px) rotateX(4deg) scale(1.02); box-shadow:0 20px 60px rgba(0,0,0,0.45) }
    .member-avatar{ width:86px;height:86px;border-radius:14px;margin:0 auto 8px; background:linear-gradient(180deg,var(--accent),var(--accent-2)); display:flex;align-items:center;justify-content:center;font-weight:800;color:#061018 }
    .member-name{ font-weight:700; margin-top:.4rem; color:var(--accent) }
    .member-role{ font-size:.9rem; color:var(--muted); margin-top:.25rem }

    @media (max-width:980px){ .team-grid{ grid-template-columns:repeat(2,1fr)} }
    @media (max-width:560px){ .team-grid{ grid-template-columns:1fr } .connect-grid{ grid-template-columns:1fr } }

    /* ==========================
       TIMELINE / ROADMAP
       ========================== */
    .timeline{ margin-top:2rem; display:flex; flex-direction:column; gap:1.2rem; padding:1rem 0 }
    .timeline-item{ display:flex; gap:1rem; align-items:flex-start; padding:1rem; border-radius:12px; background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); border:1px solid rgba(255,255,255,0.03); }
    .timeline-item .dot{ width:14px; height:14px; border-radius:50%; background:var(--accent); margin-top:6px; flex:0 0 14px; box-shadow:0 4px 18px rgba(0,255,247,0.14) }
    .timeline-item h4{ margin:0; color:var(--accent); font-size:1rem }
    .timeline-item p{ margin:.3rem 0 0; color:var(--muted) }

    /* ==========================
       TESTIMONIALS (carousel simple)
       ========================== */
    .testimonials { display:flex; gap:1rem; margin-top:1rem; overflow:hidden; position:relative }
    .testimonial { min-width:320px; max-width:520px; background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); padding:1.1rem; border-radius:12px; border:1px solid rgba(255,255,255,0.03) }
    .testimonial p{ color:var(--muted) ; font-weight:600 }

    /* ==========================
       FOOTER
       ========================== */
    footer{ margin-top:3rem; padding:2.5rem 18px; color:var(--muted); border-top:1px solid rgba(255,255,255,0.03) }
    .footer-grid{ max-width:var(--max-width); margin:0 auto; display:grid; grid-template-columns:1fr 240px; gap:1rem; align-items:start }
    .footer-brand{ font-weight:700; color:var(--accent) }
    .footer-links a{ color:var(--muted); text-decoration:none; display:block; margin:.25rem 0 }
    @media (max-width:720px){ .footer-grid{ grid-template-columns:1fr; } }

    /* ==========================
       FLOATING CONTACT & SCROLL TOP
       ========================== */
    .floating-contact{ position:fixed; right:22px; bottom:92px; z-index:140; display:flex; gap:.6rem; flex-direction:column; align-items:center }
    .floating-contact .fab{ width:56px;height:56px;border-radius:14px;background:linear-gradient(90deg,var(--accent),var(--accent-2));display:flex;align-items:center;justify-content:center;color:#081018; font-weight:800; box-shadow:0 18px 40px rgba(0,0,0,0.35); border:none; cursor:pointer}
    .floating-contact .chat{ width:46px;height:46px;border-radius:12px;background:rgba(255,255,255,0.03);display:flex;align-items:center;justify-content:center;color:var(--accent); border:1px solid rgba(255,255,255,0.03) }

    .scroll-top{ position:fixed; right:22px; bottom:22px; width:52px; height:52px; border-radius:12px; display:flex; align-items:center; justify-content:center; background:rgba(255,255,255,0.02); border:1px solid rgba(255,255,255,0.03); color:var(--accent); cursor:pointer; opacity:0; visibility:hidden; transform:translateY(10px); transition:all 260ms }
    .scroll-top.show{ opacity:1; visibility:visible; transform:none }

    /* small helpers */
    .muted{ color:var(--muted) }
    .kpi{ font-weight:800; font-size:1.8rem; color:var(--accent) }

  </style>
</head>

<body>
  <!-- PRELOADER (custom loader) -->
  <div id="preloader" aria-hidden="false" style="position:fixed;inset:0;z-index:9999;display:flex;align-items:center;justify-content:center;background:linear-gradient(90deg,#050317,rgba(0,0,0,0.6));">
    <div style="display:flex;flex-direction:column;align-items:center;gap:.9rem">
      <svg width="84" height="84" viewBox="0 0 100 100" aria-hidden="true" style="filter:drop-shadow(0 10px 30px rgba(0,0,0,0.5));">
        <defs>
          <linearGradient id="g1" x1="0" x2="1"><stop offset="0" stop-color="#00fff7"/><stop offset="1" stop-color="#ff00ff"/></linearGradient>
        </defs>
        <circle cx="50" cy="50" r="38" stroke="url(#g1)" stroke-width="6" fill="none" stroke-linecap="round" stroke-dasharray="240" stroke-dashoffset="0" transform="rotate(-90 50 50)">
          <animateTransform attributeName="transform" type="rotate" from="0 50 50" to="360 50 50" dur="1.6s" repeatCount="indefinite"/>
        </circle>
      </svg>
      <div style="color:var(--muted);font-weight:700">SpotlixHQ — Loading creative universe...</div>
    </div>
  </div>

  <!-- HEADER / NAV -->
  <header>
    <nav role="navigation" aria-label="Main navigation" id="topNav">
      <div class="brand" tabindex="0" id="brandHome" role="button" aria-label="SpotlixHQ Home">
        <!-- Inline SVG brand (keeps site self-contained) -->
        <svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" focusable="false">
          <defs>
            <linearGradient id="lg" x1="0" x2="1"><stop offset="0" stop-color="#00fff7"/><stop offset="1" stop-color="#ff00ff"/></linearGradient>
          </defs>
          <circle cx="32" cy="32" r="28" fill="url(#lg)" opacity="0.14"/>
          <path d="M20 40c4-7 16-7 20 0" stroke="url(#lg)" stroke-width="3" stroke-linecap="round" fill="none"/>
          <circle cx="32" cy="24" r="6" fill="url(#lg)"/>
        </svg>
        <div>
          <div class="title">SpotlixHQ</div>
          <div class="sub">Spotlight Squad</div>
        </div>
      </div>

      <div class="nav-links" role="menubar" aria-label="Primary">
        <a href="#home" id="nav-home" role="menuitem">Home</a>
        <a href="#about" id="nav-about" role="menuitem">About</a>
        <a href="#community" id="nav-community" role="menuitem">Community</a>
        <a href="#team" id="nav-team" role="menuitem">Team</a>
        <a href="#roadmap" id="nav-roadmap" role="menuitem">Roadmap</a>
      </div>

      <div class="nav-actions" role="group" aria-label="Actions">
        <select id="language-select" aria-label="Select language" title="Select language">
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

        <button class="icon-btn" id="themeToggle" title="Toggle theme" aria-pressed="false" aria-label="Toggle theme">
          <i class="fas fa-adjust" aria-hidden="true"></i>
        </button>

        <button class="btn small" id="joinBtn" aria-haspopup="dialog">Join the Squad</button>
        <button class="hamburger" id="hamburger" aria-label="Open menu" aria-expanded="false"><i class="fas fa-bars"></i></button>
      </div>
    </nav>

    <!-- MOBILE MENU (overlay) -->
    <div id="mobileMenu" aria-hidden="true" style="display:none;position:fixed;inset:78px 12px auto 12px;z-index:130;background:linear-gradient(180deg, rgba(2,6,10,0.96), rgba(2,6,10,0.92));backdrop-filter:blur(8px);padding:1.2rem;border-radius:12px;">
      <a href="#home" role="menuitem" class="mobile-link">Home</a>
      <a href="#about" role="menuitem" class="mobile-link">About</a>
      <a href="#community" role="menuitem" class="mobile-link">Community</a>
      <a href="#team" role="menuitem" class="mobile-link">Team</a>
      <a href="#roadmap" role="menuitem" class="mobile-link">Roadmap</a>
      <div style="height:8px"></div>
      <a href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener">Instagram</a>
      <a href="https://t.me/SpotlixHQ" target="_blank" rel="noopener">Telegram</a>
      <a href="https://www.youtube.com/@SpotlixHQ" target="_blank" rel="noopener">YouTube</a>
      <a href="mailto:spotlixhq@gmail.com">Email</a>
    </div>
  </header>

  <main>
    <!-- HERO -->
    <section id="home" class="hero" aria-labelledby="homeHeading">
      <!-- cinematic media (replace src with your high quality loop) -->
      <div class="hero-media" aria-hidden="true">
        <!-- Replace the source with your static/background video (webm preferred for performance). If not available, video will not load and gradient will show. -->
        <video id="heroVideo" autoplay muted loop playsinline preload="metadata">
          <!-- Example: <source src="assets/spotlix-hero-loop.webm" type="video/webm"> -->
          <!-- Put your file path here for cinematic effect -->
          <!-- Fallback: no source -> gradient background used -->
        </video>
        <div class="hero-overlay" aria-hidden="true"></div>
      </div>

      <div class="hero-inner wrap">
        <div class="hero-card" role="region" aria-label="SpotlixHQ hero">
          <h1 id="homeHeading" class="hero-title">Stop working alone — Launch with a squad.</h1>
          <p class="hero-strap" id="heroStrap">SpotlixHQ (Spotlight Squad) is a premium creator community where collaborators find each other, build ideas fast, and turn projects into momentum.</p>

          <div id="typed" class="typing" aria-live="polite" aria-atomic="true"></div>

          <div class="hero-ctas">
            <button class="btn cta-primary" id="primaryJoin"><i class="fas fa-rocket" aria-hidden="true"></i> Join the Squad</button>
            <button class="btn ghost cta-secondary" id="openContact">Contact / Collaborate</button>
            <a class="btn small" href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener">Instagram</a>
          </div>

          <div class="accent-grid" aria-hidden="true">
            <div class="floating-card">
              <div style="font-weight:800;font-size:1.05rem;color:var(--accent)">Creators-first</div>
              <div class="muted" style="margin-top:.35rem">Curated collaborations & events</div>
            </div>
            <div class="floating-card">
              <div style="font-weight:800;font-size:1.05rem;color:var(--accent)">Premium Content</div>
              <div class="muted" style="margin-top:.35rem">Live talks, workshops & resources</div>
            </div>
            <div class="floating-card">
              <div style="font-weight:800;font-size:1.05rem;color:var(--accent)">Growth Engine</div>
              <div class="muted" style="margin-top:.35rem">Cross-promotion across channels</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ABOUT -->
    <section id="about" aria-labelledby="aboutTitle">
      <div class="wrap">
        <div class="section-head">
          <div id="aboutTitle" class="section-title">About SpotlixHQ</div>
          <div id="aboutSub" class="section-sub">We help creators find collaborators, sharpen projects, and amplify work across platforms — Instagram, Telegram, YouTube and beyond.</div>
        </div>

        <div style="display:grid;grid-template-columns:2fr 1fr;gap:1rem;align-items:start">
          <div>
            <article class="floating-card" style="padding:1.6rem;">
              <h3 style="margin:0 0 .6rem;font-size:1.15rem;color:var(--accent)">Our Vision</h3>
              <p class="muted">Build a creator-first ecosystem where ideas move from concept to creation quickly with accountability, mentorship and distribution support. Stop working alone — launch with a squad.</p>
              <div style="display:flex;gap:1rem;margin-top:1rem;flex-wrap:wrap">
                <div class="kpi" id="liveCount">0</div>
                <div class="muted">live subscribers</div>
              </div>
            </article>
          </div>

          <aside>
            <div class="floating-card">
              <h4 style="margin:0;color:var(--accent)">Quick Links</h4>
              <div style="margin-top:.6rem">
                <a href="mailto:spotlixhq@gmail.com" class="muted">spotlixhq@gmail.com</a>
                <div style="height:8px"></div>
                <a href="https://t.me/SpotlixHQ" target="_blank" rel="noopener" class="muted">Telegram</a><br/>
                <a href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener" class="muted">Instagram</a>
              </div>
            </div>
          </aside>
        </div>
      </div>
    </section>

    <!-- COMMUNITY / CONNECT -->
    <section id="community" aria-labelledby="communityTitle">
      <div class="wrap">
        <div class="section-head">
          <div id="communityTitle" class="section-title">Connect With Us</div>
          <div id="communitySub" class="section-sub">Join the squad on platforms you already use — or reach us via email for collabs and features.</div>
        </div>

        <div class="connect-grid" role="list" aria-label="Community platforms">
          <a class="connect-card" href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener" role="listitem">
            <i class="fab fa-instagram" aria-hidden="true"></i>
            <div>
              <div class="meta">Instagram</div>
              <div class="muted">Share posts & reels</div>
            </div>
          </a>
          <a class="connect-card" href="https://t.me/SpotlixHQ" target="_blank" rel="noopener" role="listitem">
            <i class="fab fa-telegram" aria-hidden="true"></i>
            <div>
              <div class="meta">Telegram</div>
              <div class="muted">Announcements & live chats</div>
            </div>
          </a>
          <a class="connect-card" href="https://www.youtube.com/@SpotlixHQ" target="_blank" rel="noopener" role="listitem">
            <i class="fab fa-youtube" aria-hidden="true"></i>
            <div>
              <div class="meta">YouTube</div>
              <div class="muted">Tutorials, talkshows & features</div>
            </div>
          </a>
          <a class="connect-card" href="mailto:spotlixhq@gmail.com" role="listitem">
            <i class="fas fa-envelope" aria-hidden="true"></i>
            <div>
              <div class="meta">Email</div>
              <div class="muted">Direct outreach</div>
            </div>
          </a>
        </div>
      </div>
    </section>

    <!-- TEAM -->
    <section id="team" aria-labelledby="teamTitle">
      <div class="wrap">
        <div class="section-head">
          <div id="teamTitle" class="section-title">Our Team</div>
          <div class="section-sub">A small but mighty core. We help creators find ideas, partners and growth paths.</div>
        </div>

        <div class="team-grid" role="list" aria-label="Team members">
          <div class="member-card" role="listitem" tabindex="0" aria-pressed="false" onclick="toggleBio(this)" onkeypress="if(event.key==='Enter'){toggleBio(this)}">
            <div class="member-avatar">SY</div>
            <div class="member-name">Suryansh</div>
            <div class="member-role">Founder</div>
            <div class="bio muted" style="margin-top:.6rem;display:none">
              Love creativity — <a href="https://www.instagram.com/suryansh_y09?igsh=MXIzNGhmMGtlZjY4eQ==" target="_blank" rel="noopener">Instagram</a> |
              <a href="mailto:suryanshy302@gmail.com">Email</a>
            </div>
          </div>

          <div class="member-card" role="listitem" tabindex="0" aria-pressed="false" onclick="toggleBio(this)" onkeypress="if(event.key==='Enter'){toggleBio(this)}">
            <div class="member-avatar">A</div>
            <div class="member-name">Anup</div>
            <div class="member-role">Team Member</div>
            <div class="bio muted" style="margin-top:.6rem;display:none">
              Not a backup plan — I’m the main character. <a href="https://www.instagram.com/anup_.45_45?igsh=cDhuY3plOGVxaXhw" target="_blank" rel="noopener">Instagram</a> |
              <a href="mailto:gurub0357@gmail.com">Email</a>
            </div>
          </div>

          <!-- Placeholder for future team additions -->
          <div class="member-card" role="listitem" tabindex="0">
            <div class="member-avatar">+</div>
            <div class="member-name">You</div>
            <div class="member-role">Creator / Collaborator</div>
            <div class="muted" style="margin-top:.6rem">Join the squad — share your profile</div>
          </div>

          <div class="member-card" role="listitem" tabindex="0">
            <div class="member-avatar">CM</div>
            <div class="member-name">Community</div>
            <div class="member-role">Moderation & Growth</div>
            <div class="muted" style="margin-top:.6rem">Keeping the squad healthy</div>
          </div>
        </div>
      </div>
    </section>

    <!-- ROADMAP -->
    <section id="roadmap" aria-labelledby="roadmapTitle">
      <div class="wrap">
        <div class="section-head">
          <div id="roadmapTitle" class="section-title">Roadmap & Timeline</div>
          <div class="section-sub">Where we're headed — an interactive timeline of our next milestones.</div>
        </div>

        <div class="timeline">
          <div class="timeline-item" tabindex="0">
            <div class="dot" aria-hidden="true"></div>
            <div>
              <h4>Q4 2025 — Creator Workshops</h4>
              <p class="muted">Monthly masterclasses with creators and industry pros. Live recording and resource packs for attendees.</p>
            </div>
          </div>

          <div class="timeline-item" tabindex="0">
            <div class="dot" aria-hidden="true"></div>
            <div>
              <h4>Q1 2026 — Collab Launchpad</h4>
              <p class="muted">A micro-grant and mentorship program to help teams produce their first collaborative piece.</p>
            </div>
          </div>

          <div class="timeline-item" tabindex="0">
            <div class="dot" aria-hidden="true"></div>
            <div>
              <h4>Q2 2026 — Spotlight Festival</h4>
              <p class="muted">An annual virtual festival showcasing community projects, panels and live jams.</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- TESTIMONIALS -->
    <section id="testimonials" aria-labelledby="testimonialsTitle">
      <div class="wrap">
        <div class="section-head">
          <div id="testimonialsTitle" class="section-title">Success Stories</div>
          <div class="section-sub">Creators who found momentum with the squad.</div>
        </div>

        <div class="testimonials" id="testimonialsList" aria-live="polite">
          <div class="testimonial">
            <strong style="color:var(--accent);display:block">Ria — Filmmaker</strong>
            <p class="muted">"Joined SpotlixHQ and found two collaborators in a week — our short doc reached 50k views in a month."</p>
          </div>
          <div class="testimonial">
            <strong style="color:var(--accent);display:block">Arjun — Music Producer</strong>
            <p class="muted">"The cross-promotion and creative feedback helped me publish a track that landed on curated playlists."</p>
          </div>
          <div class="testimonial">
            <strong style="color:var(--accent);display:block">Meera — Animator</strong>
            <p class="muted">"I got my first paid gig after a collab posted in the Telegram channel — real results."</p>
          </div>
        </div>
      </div>
    </section>
  </main>

  <!-- FLOATING CONTACT + JOIN CTA -->
  <div class="floating-contact" role="complementary" aria-label="Quick actions">
    <button class="fab" id="quickJoin" title="Join the Squad (quick)"><i class="fas fa-rocket" aria-hidden="true"></i></button>
    <button class="chat" id="quickMsg" title="Contact us"><i class="fas fa-comment-alt" aria-hidden="true" style="color:var(--accent)"></i></button>
  </div>

  <!-- SCROLL TO TOP -->
  <button class="scroll-top" id="scrollTop" aria-label="Back to top" title="Back to top">
    <i class="fas fa-chevron-up" aria-hidden="true"></i>
  </button>

  <!-- CONTACT / JOIN MODAL -->
  <div class="modal-backdrop" id="modalBackdrop" aria-hidden="true" style="display:none;position:fixed;inset:0;background:rgba(0,0,0,0.6);z-index:150;align-items:center;justify-content:center;">
    <div class="modal" role="dialog" aria-modal="true" aria-labelledby="contactTitle" style="background:var(--card-bg);padding:1.2rem;border-radius:12px;max-width:520px;width:92%;border:1px solid var(--glass-border);box-shadow:var(--elev)">
      <h3 id="contactTitle" style="margin:0 0 .6rem;color:var(--accent)">Join Spotlight Squad</h3>
      <p class="muted" style="margin:0 0 1rem">Quick onboarding — tell us where you are active and we'll recommend the best entry path.</p>

      <form id="joinForm" style="display:flex;flex-direction:column;gap:.6rem">
        <label class="muted" for="platform">Primary Platform</label>
        <select id="platform" aria-label="Primary platform">
          <option>Instagram</option>
          <option>Telegram</option>
          <option>YouTube</option>
          <option>Other</option>
        </select>

        <label class="muted" for="emailInput">Email (so we can reach out)</label>
        <input id="emailInput" type="email" placeholder="you@example.com" style="padding:.55rem;border-radius:8px;border:1px solid var(--glass-border);background:transparent;color:var(--text)"/>

        <div style="display:flex;gap:.6rem;justify-content:flex-end;margin-top:.6rem">
          <button type="button" class="btn" id="submitJoin">Continue</button>
          <button type="button" class="btn ghost" id="closeModal">Close</button>
        </div>
      </form>

      <div id="joinResult" style="display:none;margin-top:.8rem;color:var(--success)">Thanks — check your email for next steps ✓</div>
    </div>
  </div>

  <!-- FOOTER -->
  <footer role="contentinfo">
    <div class="footer-grid">
      <div>
        <div class="footer-brand">SpotlixHQ — Spotlight Squad</div>
        <div style="margin-top:.6rem;color:var(--muted)">A premium creator community focused on collaborations, growth and distribution across major platforms.</div>
        <div style="margin-top:1rem;color:var(--muted)">Email: <a href="mailto:spotlixhq@gmail.com" style="color:var(--muted)">spotlixhq@gmail.com</a></div>
      </div>

      <div>
        <div style="font-weight:700;color:var(--accent);margin-bottom:.6rem">Quick links</div>
        <div class="footer-links">
          <a href="#about">About</a>
          <a href="#community">Community</a>
          <a href="#team">Team</a>
          <a href="https://spotlix.github.io/SpotlixHQ-/" target="_blank" rel="noopener">Old site</a>
        </div>
      </div>
    </div>

    <div style="max-width:var(--max-width);margin:1.4rem auto 0;color:var(--muted);font-size:.95rem;display:flex;justify-content:space-between;align-items:center;gap:1rem;flex-wrap:wrap">
      <div>Proudly Indian Made 🌟 | © <span id="year">2025</span> SpotlixHQ. All rights reserved.</div>
      <div style="color:var(--muted)">Built with ❤️ for creators</div>
    </div>
  </footer>

  <!-- ==========================
       SCRIPTS (deferred/enhanced)
       ========================== -->
  <script>
    // ---------- INITIAL: preserve details & basic states ----------
    document.getElementById('year').textContent = new Date().getFullYear();

    // Simple utility
    const $ = (sel, ctx=document) => ctx.querySelector(sel);
    const $$ = (sel, ctx=document) => Array.from(ctx.querySelectorAll(sel));

    // ---------- PRELOADER fade out ----------
    window.addEventListener('load', () => {
      const p = document.getElementById('preloader');
      if(p){ p.style.transition = 'opacity .6s ease'; p.style.opacity = '0'; setTimeout(()=> p.remove(), 700); }
    });

    // ---------- NAV shrink on scroll ----------
    const nav = document.getElementById('topNav');
    let lastScroll = 0;
    window.addEventListener('scroll', () => {
      if(window.scrollY > 60) nav.classList.add('condensed');
      else nav.classList.remove('condensed');

      // scroll-top show
      const st = document.getElementById('scrollTop');
      if(window.scrollY > 320) st.classList.add('show'); else st.classList.remove('show');
    });

    // ---------- SCROLL TO TOP ----------
    const scrollTopBtn = document.getElementById('scrollTop');
    scrollTopBtn.addEventListener('click', ()=> window.scrollTo({top:0,behavior:'smooth'}));

    // ---------- TYPING animation (hero) ----------
    (function(){
      const phrases = [
        "Creators. Thinkers. Collaborators.",
        "Where Ideas Meet Action.",
        "Grow, Share, Connect.",
        "Made for community-first creators.",
        "Your next idea starts here."
      ];
      let i=0,j=0,isDeleting=false;
      const tEl = document.getElementById('typed');
      function loop(){
        if(!tEl) return;
        if(i >= phrases.length) i = 0;
        const cur = phrases[i];
        if(!isDeleting){
          tEl.textContent = cur.substring(0, j+1);
          j++;
          if(j === cur.length){ isDeleting = true; setTimeout(loop, 900); return; }
        } else {
          tEl.textContent = cur.substring(0, j-1);
          j--;
          if(j === 0){ isDeleting=false; i++; }
        }
        setTimeout(loop, isDeleting ? 45 : 95);
      }
      requestIdleCallback ? requestIdleCallback(loop) : setTimeout(loop, 300);
    })();

    // ---------- Toggle team bio ----------
    function toggleBio(card){
      const bio = card.querySelector('.bio');
      if(!bio) return;
      const shown = bio.style.display === 'block';
      bio.style.display = shown ? 'none' : 'block';
      card.setAttribute('aria-pressed', String(!shown));
    }
    window.toggleBio = toggleBio;

    // ---------- Modal logic (join/contact) ----------
    const modalBackdrop = document.getElementById('modalBackdrop');
    const joinBtn = document.getElementById('joinBtn');
    const primaryJoin = document.getElementById('primaryJoin');
    const openContact = document.getElementById('openContact');
    const closeModal = document.getElementById('closeModal');
    const submitJoin = document.getElementById('submitJoin');
    const joinForm = document.getElementById('joinForm');
    const joinResult = document.getElementById('joinResult');

    function openModal(){
      modalBackdrop.style.display = 'flex';
      modalBackdrop.setAttribute('aria-hidden','false');
      // trap focus simply
      const email = document.getElementById('emailInput');
      setTimeout(()=> email && email.focus(), 120);
    }
    function closeModalFunc(){
      modalBackdrop.style.display = 'none';
      modalBackdrop.setAttribute('aria-hidden','true');
      joinResult.style.display = 'none';
    }

    [joinBtn, primaryJoin].forEach(b => b && b.addEventListener('click', openModal));
    openContact && openContact.addEventListener('click', openModal);
    closeModal && closeModal.addEventListener('click', closeModalFunc);
    modalBackdrop && modalBackdrop.addEventListener('click', (e)=> { if(e.target === modalBackdrop) closeModalFunc(); });

    // handle form submit
    if(submitJoin){
      submitJoin.addEventListener('click', async ()=>{
        // minimal UX: validate email
        const email = document.getElementById('emailInput').value.trim();
        if(email && email.includes('@')){
          // show success (replace with real API call if available)
          joinForm.style.display = 'none';
          joinResult.style.display = 'block';
          // Simulate adding to subscribers (local)
          incrementLiveCount( Math.floor(Math.random()*3)+1 );
          setTimeout(()=> { closeModalFunc(); joinForm.style.display='flex'; }, 1400);
        } else {
          const emailEl = document.getElementById('emailInput');
          emailEl.focus();
          emailEl.style.outline = '2px solid rgba(255,64,64,0.12)';
          setTimeout(()=> emailEl.style.outline = 'none', 1200);
        }
      });
    }

    // allow escape to close modal & mobile menu
    document.addEventListener('keydown', (e)=> {
      if(e.key === 'Escape'){ closeModalFunc(); closeMobileMenu(); }
    });

    // ---------- MOBILE MENU ----------
    const hamburger = document.getElementById('hamburger');
    const mobileMenu = document.getElementById('mobileMenu');
    function closeMobileMenu(){ if(mobileMenu){ mobileMenu.style.display='none'; hamburger.setAttribute('aria-expanded','false'); mobileMenu.setAttribute('aria-hidden','true'); } }
    if(hamburger){
      hamburger.addEventListener('click', ()=> {
        const expanded = hamburger.getAttribute('aria-expanded') === 'true';
        hamburger.setAttribute('aria-expanded', String(!expanded));
        if(!expanded){ mobileMenu.style.display = 'block'; mobileMenu.setAttribute('aria-hidden','false'); const first = mobileMenu.querySelector('a'); first && first.focus(); }
        else closeMobileMenu();
      });
      // close mobile on link click
      $$('#mobileMenu a').forEach(a => a.addEventListener('click', closeMobileMenu));
    }

    // ---------- Language support (preserve translations) ----------
    const content = {
      en: {
        navHome: "Home", navAbout: "About", navCommunity: "Community", navTeam: "Team",
        aboutTitle: "About SpotlixHQ", aboutDesc: "SpotlixHQ is a community for creators, thinkers, and innovators to collaborate, share ideas, and grow together.",
        communityTitle: "Connect With Us", teamTitle: "Our Team", heroTitle: "Stop working alone — Launch with a squad.", heroStrap: "SpotlixHQ (Spotlight Squad) is a premium creator community where collaborators find each other, build ideas fast, and turn projects into momentum.", rtl:false
      },
      hi: {
        navHome: "होम", navAbout: "हमारे बारे में", navCommunity: "समुदाय", navTeam: "टीम",
        aboutTitle: "SpotlixHQ के बारे में", aboutDesc: "SpotlixHQ रचनाकारों, विचारकों और नवप्रवर्तकों के लिए एक समुदाय है जहाँ वे सहयोग कर सकते हैं, विचार साझा कर सकते हैं और साथ में आगे बढ़ सकते हैं।",
        communityTitle: "हमसे जुड़ें", teamTitle: "हमारी टीम", heroTitle: "अकेले काम बंद करें — स्क्वाड के साथ लॉन्च करें।", heroStrap: "SpotlixHQ (Spotlight Squad) एक प्रीमियम क्रिएटर समुदाय है जहाँ सहयोगी एक-दूसरे को ढूंढते हैं, विचार तेजी से बनाते हैं और परियोजनाओं को गति देते हैं।", rtl:false
      },
      de: {
        navHome: "Startseite", navAbout: "Über uns", navCommunity: "Community", navTeam: "Team",
        aboutTitle: "Über SpotlixHQ", aboutDesc: "SpotlixHQ ist eine Community für Kreative, Denker und Innovatoren, um zusammenzuarbeiten, Ideen zu teilen und gemeinsam zu wachsen.",
        communityTitle: "Vernetze dich mit uns", teamTitle: "Unser Team", heroTitle: "Hör auf, allein zu arbeiten — starte mit einem Squad.", heroStrap: "SpotlixHQ (Spotlight Squad) ist eine Premium-Creator-Community, in der sich Kollaborateure finden, Ideen schnell umsetzen und Projekte vorantreiben.", rtl:false
      },
      ja: {
        navHome: "ホーム", navAbout: "概要", navCommunity: "コミュニティ", navTeam: "チーム",
        aboutTitle: "SpotlixHQ について", aboutDesc: "SpotlixHQ は、クリエイターや思考家、イノベーターが協力し、アイデアを共有し、ともに成長するためのコミュニティです。",
        communityTitle: "私たちとつながる", teamTitle: "チーム紹介", heroTitle: "一人でやめよう — スクワッドでローンチしよう。", heroStrap: "SpotlixHQ（Spotlight Squad）は、コラボレーターが出会い、アイデアを素早く形にし、プロジェクトに勢いをつけるプレミアムコミュニティです。", rtl:false
      },
      es: {
        navHome: "Inicio", navAbout: "Acerca de", navCommunity: "Comunidad", navTeam: "Equipo",
        aboutTitle: "Acerca de SpotlixHQ", aboutDesc: "SpotlixHQ es una comunidad para creadores, pensadores e innovadores donde pueden colaborar, compartir ideas y crecer juntos.",
        communityTitle: "Conéctate con nosotros", teamTitle: "Nuestro equipo", heroTitle: "Deja de trabajar solo — lanza con un squad.", heroStrap: "SpotlixHQ (Spotlight Squad) es una comunidad premium para creadores donde los colaboradores se encuentran, construyen ideas rápidamente y convierten proyectos en impulso.", rtl:false
      },
      fr: {
        navHome: "Accueil", navAbout: "À propos", navCommunity: "Communauté", navTeam: "Équipe",
        aboutTitle: "À propos de SpotlixHQ", aboutDesc: "SpotlixHQ est une communauté pour les créateurs, penseurs et innovateurs afin de collaborer, partager des idées et grandir ensemble.",
        communityTitle: "Connectez-vous avec nous", teamTitle: "Notre équipe", heroTitle: "Arrêtez de travailler seul — lancez-vous avec une squad.", heroStrap: "SpotlixHQ (Spotlight Squad) est une communauté premium où les collaborateurs se rencontrent, concrétisent rapidement des idées et propulsent des projets.", rtl:false
      },
      ar: {
        navHome: "الرئيسية", navAbout: "من نحن", navCommunity: "المجتمع", navTeam: "الفريق",
        aboutTitle: "نبذة عن SpotlixHQ", aboutDesc: "SpotlixHQ هو مجتمع للمبدعين والمفكرين والمبتكرين للتعاون وتبادل الأفكار والنمو معًا.",
        communityTitle: "تواصل معنا", teamTitle: "فريقنا", heroTitle: "توقف عن العمل بمفردك — أطلق مع فريق.", heroStrap: "SpotlixHQ (Spotlight Squad) هي مجتمع متميز للمبدعين حيث يجد المتعاونون بعضهم البعض، يبنون الأفكار بسرعة، ويمنحون المشاريع زخمًا.", rtl:true
      },
      id: {
        navHome: "Beranda", navAbout: "Tentang", navCommunity: "Komunitas", navTeam: "Tim",
        aboutTitle: "Tentang SpotlixHQ", aboutDesc: "SpotlixHQ adalah komunitas bagi kreator, pemikir, dan inovator untuk berkolaborasi, berbagi ide, dan tumbuh bersama.",
        communityTitle: "Terhubung dengan kami", teamTitle: "Tim kami", heroTitle: "Berhenti bekerja sendirian — Luncurkan bersama squad.", heroStrap: "SpotlixHQ (Spotlight Squad) adalah komunitas kreator premium di mana kolaborator saling menemukan, membangun ide dengan cepat, dan mengubah proyek menjadi momentum.", rtl:false
      },
      bn: {
        navHome: "হোম", navAbout: "আমাদের সম্পর্কে", navCommunity: "কমিউনিটি", navTeam: "টিম",
        aboutTitle: "SpotlixHQ সম্পর্কে", aboutDesc: "SpotlixHQ হল সৃষ্টিশীল ব্যক্তি, চিন্তাবিদ এবং উদ্ভাবকদের জন্য একটি কমিউনিটি যেখানে তারা একসাথে কাজ করতে, আইডিয়া শেয়ার করতে এবং একসাথে বেড়ে উঠতে পারে।",
        communityTitle: "আমাদের সাথে যুক্ত হন", teamTitle: "আমাদের দল", heroTitle: "একলা কাজ বন্ধ করো — স্কোয়াডের সাথে লঞ্চ করো।", heroStrap: "SpotlixHQ (Spotlight Squad) হল একটি প্রিমিয়াম ক্রিয়েটর কমিউনিটি যেখানে সহযোগীরা একে অপরকে খুঁজে পায়, দ্রুত ধারণা তৈরি করে এবং প্রকল্পগুলিকে গতিতে নিয়ে যায়।", rtl:false
      },
      zh: {
        navHome: "首页", navAbout: "关于", navCommunity: "社区", navTeam: "团队",
        aboutTitle: "关于 SpotlixHQ", aboutDesc: "SpotlixHQ 是一个为创作者、思想者和创新者而建立的社区，在这里可以协作、分享想法并共同成长。",
        communityTitle: "与我们联系", teamTitle: "我们的团队", heroTitle: "别再单打独斗 — 与团队一起发布。", heroStrap: "SpotlixHQ（Spotlight Squad）是一个优质创作者社区，协作方可以在此相遇、快速构思并将项目推向势头。", rtl:false
      }
    };

    const langSelect = document.getElementById('language-select');
    const navHome = document.getElementById('nav-home');
    const navAbout = document.getElementById('nav-about');
    const navCommunity = document.getElementById('nav-community');
    const navTeam = document.getElementById('nav-team');
    const aboutTitleEl = document.getElementById('aboutTitle');
    const aboutSubEl = document.getElementById('aboutSub');
    const communityTitleEl = document.getElementById('communityTitle');
    const heroTitleEl = document.getElementById('homeHeading');
    const heroStrapEl = document.getElementById('heroStrap');

    function applyLanguage(lang){
      if(!content[lang]) lang='en';
      const t = content[lang];
      navHome.textContent = t.navHome;
      navAbout.textContent = t.navAbout;
      navCommunity.textContent = t.navCommunity;
      navTeam.textContent = t.navTeam;
      aboutTitleEl.textContent = t.aboutTitle;
      aboutSubEl.textContent = t.aboutDesc;
      communityTitleEl.textContent = t.communityTitle;
      heroTitleEl.textContent = t.heroTitle;
      heroStrapEl.textContent = t.heroStrap;
      document.documentElement.lang = lang;
      document.documentElement.dir = t.rtl ? 'rtl' : 'ltr';
      ['about','community','team','roadmap','testimonials'].forEach(id => {
        const el = document.getElementById(id);
        if(!el) return;
        if(t.rtl) el.classList.add('rtl'); else el.classList.remove('rtl');
      });
    }
    if(langSelect){
      langSelect.addEventListener('change', ()=> applyLanguage(langSelect.value));
      // set default from browser or saved preference
      const saved = localStorage.getItem('spotlix_lang') || (navigator.language ? navigator.language.split('-')[0] : 'en');
      if(content[saved]) langSelect.value = saved;
      applyLanguage(langSelect.value || 'en');
      langSelect.addEventListener('change', ()=> { localStorage.setItem('spotlix_lang', langSelect.value); });
    }

    // ---------- THEME: auto (system) + toggle ----------
    (function(){
      const root = document.documentElement;
      const saved = localStorage.getItem('spotlix_theme'); // 'light' | 'dark' | null
      function applyTheme(mode){
        if(mode === 'light'){ root.classList.add('light'); document.getElementById('themeToggle').setAttribute('aria-pressed','true'); }
        else { root.classList.remove('light'); document.getElementById('themeToggle').setAttribute('aria-pressed','false'); }
      }
      // initial: prefer system
      const prefersLight = window.matchMedia && window.matchMedia('(prefers-color-scheme: light)').matches;
      applyTheme(saved || (prefersLight ? 'light' : 'dark'));
      // toggle
      document.getElementById('themeToggle').addEventListener('click', ()=>{
        const isLight = document.documentElement.classList.contains('light');
        const newMode = isLight ? 'dark' : 'light';
        applyTheme(newMode);
        localStorage.setItem('spotlix_theme', newMode);
      });
    })();

    // ---------- Live subscriber count (simulated) ----------
    const liveCountEl = document.getElementById('liveCount');
    let liveCount = parseInt(localStorage.getItem('spotlix_live')) || (Math.floor(Math.random()*3500)+1200);
    function renderLiveCount(){ liveCountEl.textContent = liveCount.toLocaleString(); }
    function incrementLiveCount(n=1){
      liveCount += n; renderLiveCount();
      localStorage.setItem('spotlix_live', liveCount);
    }
    renderLiveCount();
    // gently increment over time to simulate live growth
    setInterval(()=> incrementLiveCount(Math.random()>0.65 ? Math.floor(Math.random()*3)+1 : 0), 4500);

    // ---------- Testimonials simple auto-scroll ----------
    (function(){
      const list = document.getElementById('testimonialsList');
      if(!list) return;
      let idx=0;
      const items = Array.from(list.children);
      function showNext(){
        idx = (idx+1) % items.length;
        const offset = items[idx].offsetLeft;
        list.scrollTo({left: offset, behavior:'smooth'});
      }
      // start after idle
      setTimeout(()=> setInterval(showNext, 4200), 1200);
    })();

    // ---------- IntersectionObserver for reveal animations (performance friendly) ----------
    (function(){
      const sections = document.querySelectorAll('main section, .floating-card, .connect-card, .member-card, .timeline-item, .testimonial');
      const io = new IntersectionObserver((entries)=>{
        entries.forEach(en=>{
          if(en.isIntersecting){
            en.target.style.transition = 'opacity .9s ease, transform .9s ease';
            en.target.style.opacity = 1;
            en.target.style.transform = 'none';
            io.unobserve(en.target);
          } else {
            // initial state
            // fallback handled in CSS (they already have opacity 1 by default)
          }
        });
      }, { threshold: 0.12 });
      sections.forEach(s => {
        s.style.opacity = 0; s.style.transform = 'translateY(30px)';
        io.observe(s);
      });
    })();

    // ---------- Minor perf: pause hero video on reduced power / small screens ----------
    (function(){
      const v = document.getElementById('heroVideo');
      if(!v) return;
      const rn = navigator;
      const prefersReduced = window.matchMedia && window.matchMedia('(prefers-reduced-motion: reduce)').matches;
      if(prefersReduced || window.innerWidth < 800) { v.pause(); v.style.display='none'; document.querySelector('.hero-overlay').style.background='linear-gradient(180deg, rgba(6,8,15,0.12), rgba(3,3,12,0.45))'; }
      // If video present but heavy, load on interaction
      document.addEventListener('scroll', ()=> { if(v.paused && window.scrollY > 40) { try{ v.play(); }catch(e){} } }, {passive:true});
    })();

    // ---------- Accessibility & keyboard helpers ----------
    // make nav links keyboard-friendly
    document.querySelectorAll('.nav-links a').forEach(a=> a.addEventListener('keydown', (e)=> { if(e.key === 'Enter' || e.key === ' ') a.click(); }));

    // ---------- Small analytics-friendly performance note ----------
    // Non-critical features are started with requestIdleCallback where available
    if('requestIdleCallback' in window){
      requestIdleCallback(function(){ /* placeholder for analytics or optional widgets */ }, {timeout:2000});
    }

    // ---------- Final: friendly hint for replacing video asset (console) ----------
    console.info('SpotlixHQ: index loaded. Replace hero <video> source with a high-quality loop (webm recommended). Email preserved: spotlixhq@gmail.com');
  </script>
</body>
</html>
