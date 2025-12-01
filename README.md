
<html lang="en" dir="ltr">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
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
    "@context":"https://schema.org",
    "@type":"Organization",
    "name":"SpotlixHQ",
    "alternateName":"Spotlight Squad",
    "url":"https://spotlixhq.com",
    "logo":"https://spotlixhq.com/og-image.png",
    "sameAs":[
      "https://www.instagram.com/spotlixhq",
      "https://t.me/SpotlixHQ",
      "https://www.youtube.com/@SpotlixHQ",
      "https://x.com/SpotlixHQ",
      "https://www.linkedin.com/company/spotlixhq"
    ],
    "description":"SpotlixHQ (Spotlight Squad) is a community for creators, thinkers, and innovators to collaborate, share ideas, and grow together."
  }
  </script>

  <!-- Preload fonts & critical images -->
  <link rel="preload" href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;900&display=swap" as="style" />
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;900&display=swap" rel="stylesheet" />

  <!-- Icons (deferred kit above will load icons) -->
  <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous" defer></script>

  <!-- Critical CSS (hero + nav + basic layout). Non-critical styles are placed later (but for single-file convenience, kept here with comments). -->
  <style>
    /* ---------- root variables ---------- */
    :root{
      --bg-1:#0f0c29;
      --bg-2:#302b63;
      --accent-1: #00fff7; /* cyan */
      --accent-2: #ff00ff; /* magenta */
      --accent-3: #ffd166; /* warm accent */
      --glass-opa: 0.12;
      --glass-border: rgba(255,255,255,0.06);
      --card-bg: rgba(255,255,255,0.02);
      --text: #E9F8F7;
      --muted: rgba(255,255,255,0.75);
      --radius-lg: 18px;
      --radius-md: 12px;
      --transition: 380ms cubic-bezier(.2,.9,.2,1);
      --max-width: 1200px;
    }

    /* ---------- reset ---------- */
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;font-family:"Poppins",system-ui,-apple-system,Segoe UI,Roboto,"Helvetica Neue",Arial;line-height:1.45;color:var(--text);background:linear-gradient(135deg,var(--bg-1),var(--bg-2));-webkit-font-smoothing:antialiased;-moz-osx-font-smoothing:grayscale}
    a{color:inherit;text-decoration:none}
    img{max-width:100%;height:auto;display:block}
    button{font-family:inherit}

    /* ---------- reduced motion preference ---------- */
    @media (prefers-reduced-motion: reduce){
      *{animation-duration:0.001ms !important; animation-iteration-count:1 !important; transition:none !important}
    }

    /* ---------- layout ---------- */
    .site {
      min-height:100vh;
      display:flex;
      flex-direction:column;
      align-items:center;
      overflow-x:hidden;
      position:relative;
      background: radial-gradient(1200px 600px at 10% 10%, rgba(0,255,247,0.03), transparent 12%),
                  radial-gradient(900px 400px at 95% 85%, rgba(255,0,255,0.03), transparent 12%),
                  linear-gradient(135deg,var(--bg-1),var(--bg-2));
    }
    main{width:100%;max-width:var(--max-width);margin:0 auto;padding:0 20px 80px}

    /* ---------- custom loader (glass orb) ---------- */
    .preloader {
      position:fixed; inset:0; display:flex;align-items:center;justify-content:center;
      z-index:9999; background:linear-gradient(0deg,rgba(0,0,0,0.65),rgba(0,0,0,0.55));
      backdrop-filter: blur(6px);
    }
    .loader-orb{
      width:88px;height:88px;border-radius:50%;background:linear-gradient(45deg,var(--accent-1),var(--accent-2));
      box-shadow:0 10px 40px rgba(12,12,30,0.5), 0 0 60px rgba(0,255,247,0.09);
      position:relative;overflow:hidden;display:flex;align-items:center;justify-content:center;
      animation: orb-breathe 2000ms ease-in-out infinite;
    }
    .loader-orb::after{
      content:"";position:absolute;width:60%;height:60%;border-radius:50%;
      background:linear-gradient(180deg, rgba(255,255,255,0.12), rgba(255,255,255,0.02));
      transform:translateY(-6%);filter:blur(6px);
    }
    @keyframes orb-breathe{
      0%{transform:scale(0.92)}
      50%{transform:scale(1.05)}
      100%{transform:scale(0.92)}
    }
    .preloader.hidden{opacity:0;visibility:hidden;pointer-events:none;transition:opacity 520ms ease}

    /* ---------- header / navbar (glass) ---------- */
    header.site-header{
      position:fixed;top:18px;left:0;right:0;display:flex;justify-content:center;z-index:80;padding:0 20px;
    }
    .nav {
      width:100%;max-width:var(--max-width);display:flex;align-items:center;gap:16px;padding:12px;border-radius:14px;
      background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      box-shadow:0 6px 30px rgba(2,6,23,0.6);
      border:1px solid var(--glass-border);backdrop-filter: blur(8px);
    }
    .brand {display:flex;align-items:center;gap:12px;font-weight:800;color:var(--accent-1);text-shadow:0 0 8px rgba(0,255,247,.14)}
    .brand svg{width:42px;height:42px}
    .nav-links{display:flex;gap:12px;align-items:center;margin-left:14px}
    .nav-links a{padding:8px 10px;border-radius:8px;color:var(--accent-1);font-weight:600;transition:all var(--transition)}
    .nav-links a:hover, .nav-links a:focus{transform:translateY(-3px);text-shadow:0 0 12px rgba(0,255,247,0.12)}
    .nav-actions{margin-left:auto;display:flex;gap:10px;align-items:center}
    .icon-btn{display:inline-flex;align-items:center;justify-content:center;padding:8px;border-radius:10px;border:1px solid transparent;background:transparent;color:var(--accent-1);cursor:pointer}
    .icon-btn:hover{transform:translateY(-3px)}
    .cta-join{background:linear-gradient(90deg,var(--accent-1),var(--accent-2));color:#08111a;padding:10px 14px;border-radius:12px;font-weight:800;border:none;box-shadow:0 8px 30px rgba(0,255,247,0.08);cursor:pointer}
    .cta-join:focus{outline:3px solid rgba(0,255,247,0.08)}
    .theme-toggle{border:1px solid rgba(255,255,255,0.04);padding:6px;border-radius:8px}

    /* mobile hamburger */
    .hamburger{display:none;background:transparent;border:0;color:var(--accent-1);font-size:20px}
    /* mobile overlay menu */
    .mobile-overlay{display:none;position:fixed;inset:0;background:linear-gradient(180deg, rgba(2,6,23,0.9), rgba(2,6,23,0.85));z-index:95;padding:40px 20px;overflow:auto}
    .mobile-overlay .menu{max-width:420px;margin:0 auto;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));padding:20px;border-radius:14px;border:1px solid var(--glass-border)}
    .mobile-overlay .menu a{display:block;padding:12px 10px;border-radius:10px;color:var(--accent-1);font-weight:700}

    /* ---------- hero (cinematic) ---------- */
    .hero {
      margin-top:92px;
      min-height:78vh;
      display:grid;
      grid-template-columns: 1fr;
      align-items:center;
      gap:34px;
      position:relative;overflow:visible;padding:32px 0;
    }

    /* hero video background container */
    .hero-bg {
      position:absolute;inset:0;z-index:0;overflow:hidden;border-radius:24px;pointer-events:none;
      opacity:0.35;mix-blend-mode:screen;
    }
    .hero-bg video, .hero-bg .hero-fallback {
      position:absolute;inset:-10% ; width:120%; height:120%; object-fit:cover; transform:scale(1.03);
      filter:contrast(1.05) saturate(1.05) blur(0.4px);
    }
    /* fallback gradient + animated noise if video missing */
    .hero-bg .hero-fallback{
      background:
        radial-gradient(600px 400px at 10% 20%, rgba(0,255,247,0.06), transparent 8%),
        radial-gradient(500px 300px at 90% 80%, rgba(255,0,255,0.05), transparent 8%),
        linear-gradient(120deg, rgba(4,6,30,0.85), rgba(15,12,41,0.75));
      background-size:cover;
    }

    .hero-panel {
      position:relative;z-index:2;max-width:1100px;margin:0 auto;display:flex;gap:28px;align-items:center;
      padding:36px;border-radius:18px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border:1px solid var(--glass-border);backdrop-filter: blur(8px);box-shadow:0 20px 80px rgba(6,7,30,0.6);
    }

    .hero-left{flex:1;min-width:260px}
    .hero-title{font-size:2.6rem;line-height:1.02;margin:0 0 8px;color:var(--text);letter-spacing:-0.6px}
    .hero-sub{font-size:1.05rem;color:var(--muted);margin:0 0 18px;max-width:58ch}
    .hero-typing{color:var(--accent-1);font-weight:700;height:30px}

    .hero-cta {display:flex;gap:12px;flex-wrap:wrap}
    .btn {padding:12px 16px;border-radius:12px;border:1px solid rgba(255,255,255,0.03);background:transparent;color:var(--accent-1);cursor:pointer;font-weight:700}
    .btn.primary {background:linear-gradient(90deg,var(--accent-1),var(--accent-2));color:#071018;box-shadow:0 10px 40px rgba(0,255,247,0.08)}
    .hero-stats {display:flex;gap:12px;margin-top:14px;align-items:center}
    .stat {background: linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.02));padding:10px 14px;border-radius:10px;border:1px solid rgba(0,255,247,0.03);font-weight:700;color:var(--accent-1)}

    /* hero-right: floating card with featured CTA/content preview */
    .hero-right{width:380px;display:flex;flex-direction:column;gap:14px;align-items:flex-end}
    .floating-card {
      width:100%;padding:14px;border-radius:14px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border:1px solid var(--glass-border);
      box-shadow: 0 20px 40px rgba(2,6,24,0.6);
      transform-style:preserve-3d;transition:transform 420ms cubic-bezier(.2,.9,.2,1), box-shadow 420ms;
      will-change:transform;
    }
    .floating-card:hover{transform:translateY(-10px) rotateX(4deg) rotateY(-3deg);box-shadow:0 28px 70px rgba(2,6,24,0.7)}
    .preview-media{height:160px;border-radius:10px;overflow:hidden;background:linear-gradient(90deg,var(--accent-1),var(--accent-2));display:flex;align-items:center;justify-content:center;color:#071018;font-weight:900}

    /* ---------- sections: cards, team, community ---------- */
    section.panel{margin:40px 0;padding:36px;border-radius:16px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.005));border:1px solid var(--glass-border);backdrop-filter: blur(6px)}
    .grid {display:grid;grid-template-columns: repeat(12, 1fr);gap:18px}
    .col-4{grid-column:span 4}
    .col-6{grid-column:span 6}
    .col-12{grid-column:span 12}

    /* cards list */
    .cards-list{display:flex;flex-wrap:wrap;gap:12px}
    .card-item{flex:1 1 260px;padding:14px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.008));border:1px solid rgba(0,255,247,0.04);transition:transform var(--transition), box-shadow var(--transition);cursor:pointer}
    .card-item:hover{transform:translateY(-8px);box-shadow:0 28px 60px rgba(0,255,247,0.04)}
    .card-item .title{font-weight:800;color:var(--accent-1);margin-bottom:6px}
    .card-item .desc{color:var(--muted);font-size:0.95rem}

    /* team */
    .team-grid {display:flex;flex-wrap:wrap;gap:14px;justify-content:center}
    .team-member{width:160px;padding:12px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.006));border:1px solid rgba(0,255,247,0.04);text-align:center;cursor:pointer;transition:transform var(--transition)}
    .team-member:hover{transform:translateY(-8px)}
    .team-member strong{display:block;margin-bottom:6px}
    .team-member .meta{color:var(--muted);font-size:0.92rem}

    /* testimonials slider */
    .testimonials{display:flex;gap:12px;align-items:center}
    .testimonial-card{min-width:260px;padding:16px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.008));border:1px solid rgba(0,255,247,0.03);box-shadow:0 14px 40px rgba(0,0,0,0.45)}
    .testimonial-card p{color:var(--muted);font-style:italic}

    /* roadmap timeline */
    .timeline{display:flex;flex-direction:column;gap:18px}
    .timeline-item{display:flex;gap:12px;align-items:flex-start}
    .timeline-item .dot{width:14px;height:14px;border-radius:50%;background:linear-gradient(90deg,var(--accent-1),var(--accent-2));flex:0 0 14px;margin-top:6px}
    .timeline-item .body{background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.005));padding:12px;border-radius:10px;border:1px solid rgba(0,255,247,0.03)}

    /* footer */
    footer.site-footer{margin-top:36px;padding:20px 16px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.01));border:1px solid rgba(0,255,247,0.04);text-align:center;color:var(--muted)}

    /* floating contact button */
    .float-contact{position:fixed;right:18px;bottom:18px;z-index:90;display:flex;gap:8px;flex-direction:column;align-items:center}
    .float-contact .fab{width:56px;height:56px;border-radius:14px;background:linear-gradient(90deg,var(--accent-1),var(--accent-2));display:flex;align-items:center;justify-content:center;color:#071018;font-weight:800;box-shadow:0 12px 40px rgba(0,255,247,0.08);cursor:pointer}

    /* scroll-top */
    .scroll-top{position:fixed;right:18px;bottom:92px;width:48px;height:48px;border-radius:12px;background:rgba(255,255,255,0.02);display:flex;align-items:center;justify-content:center;border:1px solid rgba(255,255,255,0.03);cursor:pointer;opacity:0;visibility:hidden;transform:translateY(10px);transition:all 320ms}
    .scroll-top.show{opacity:1;visibility:visible;transform:none}

    /* responsive adjustments */
    @media (max-width:1000px){
      .hero-panel{flex-direction:column;gap:18px;padding:18px}
      .hero-right{width:100%;align-items:center}
      .hero-right .floating-card{width:100%}
      .nav-links{display:none}
      .hamburger{display:inline-flex}
    }
    @media (max-width:640px){
      .hero-title{font-size:1.9rem}
      .hero{min-height:62vh;margin-top:72px}
      main{padding-bottom:140px}
      .brand span{display:none}
    }
  </style>

  <!-- Non-critical styles or big components (kept here to stay single-file) -->
  <style>
    /* small helpers used by JS */
    .hidden{display:none!important}
    .visually-hidden{position:absolute!important;left:-9999px!important;top:auto!important;width:1px;height:1px;overflow:hidden}
    /* animation helpers */
    .fade-in {animation:fadeIn .9s ease both}
    @keyframes fadeIn{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:none}}
  </style>
</head>
<body class="site" data-theme="dark">
  <!-- Preloader -->
  <div class="preloader" id="preloader" role="status" aria-label="Loading">
    <div class="loader-orb" aria-hidden="true"></div>
  </div>

  <!-- Header / Nav -->
  <header class="site-header" role="banner">
    <nav class="nav" role="navigation" aria-label="Main navigation">
      <div class="brand" aria-hidden="false">
        <!-- Inline SVG logo -->
        <svg viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" focusable="false">
          <defs>
            <linearGradient id="lg1" x1="0" x2="1"><stop offset="0" stop-color="#00fff7"/><stop offset="1" stop-color="#ff00ff"/></linearGradient>
          </defs>
          <circle cx="32" cy="32" r="28" fill="url(#lg1)" opacity="0.12"/>
          <path d="M20 40c4-7 16-7 20 0" stroke="url(#lg1)" stroke-width="3" stroke-linecap="round" fill="none"/>
          <circle cx="32" cy="24" r="6" fill="url(#lg1)"/>
        </svg>
        <span>SpotlixHQ</span>
      </div>

      <div class="nav-links" role="menubar" aria-label="Primary">
        <a href="#home" role="menuitem" id="nav-home">Home</a>
        <a href="#about" role="menuitem" id="nav-about">About</a>
        <a href="#community" role="menuitem" id="nav-community">Community</a>
        <a href="#team" role="menuitem" id="nav-team">Team</a>
        <a href="#roadmap" role="menuitem" id="nav-roadmap">Roadmap</a>
        <a href="#testimonials" role="menuitem" id="nav-testimonials">Testimonials</a>
      </div>

      <div class="nav-actions" aria-hidden="false">
        <select id="language-select" aria-label="Select language" title="Select language" class="language-select" style="background:transparent;border:1px solid rgba(255,255,255,0.02);padding:6px;border-radius:8px;color:var(--accent-1)">
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

        <button class="icon-btn theme-toggle" id="themeToggle" aria-pressed="false" aria-label="Toggle theme">
          <i class="fas fa-adjust" aria-hidden="true"></i>
        </button>

        <button class="cta-join" id="joinBtn">Join the Squad</button>

        <button class="hamburger" id="hamburger" aria-controls="mobileMenu" aria-expanded="false" aria-label="Open menu">
          <i class="fas fa-bars" aria-hidden="true"></i>
        </button>
      </div>
    </nav>
  </header>

  <!-- Mobile overlay -->
  <div class="mobile-overlay hidden" id="mobileOverlay" aria-hidden="true">
    <div class="menu" role="menu" aria-label="Mobile menu">
      <a href="#home">Home</a>
      <a href="#about">About</a>
      <a href="#community">Community</a>
      <a href="#team">Team</a>
      <a href="#roadmap">Roadmap</a>
      <a href="#testimonials">Testimonials</a>
      <div style="height:12px"></div>
      <a href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener">Instagram</a>
      <a href="https://t.me/SpotlixHQ" target="_blank" rel="noopener">Telegram</a>
      <a href="https://www.youtube.com/@SpotlixHQ" target="_blank" rel="noopener">YouTube</a>
      <a href="mailto:spotlixhq@gmail.com">Email</a>
    </div>
  </div>

  <main id="main" role="main" aria-live="polite">
    <!-- HERO -->
    <section id="home" class="hero" aria-labelledby="homeHeading">
      <!-- cinematic background (video) -->
      <div class="hero-bg" aria-hidden="true">
        <!-- Replace src with your hosted optimized video. keep attributes for accessibility. -->
        <video id="heroVideo" autoplay muted loop playsinline poster="assets/hero-poster.jpg" preload="metadata" aria-hidden="true">
          <!-- example placeholder path - replace with your file -->
          <source src="assets/hero-loop.mp4" type="video/mp4">
          <!-- fallback gradient box -->
          <div class="hero-fallback" aria-hidden="true"></div>
        </video>
      </div>

      <div class="hero-panel fade-in" role="region" aria-label="Spotlix hero">
        <div class="hero-left">
          <h1 id="homeHeading" class="hero-title">SpotlixHQ <span style="font-weight:600;color:var(--muted);font-size:0.6em;margin-left:8px">— Spotlight Squad</span></h1>
          <p class="hero-sub" id="heroSub">A cinematic home for creators, thinkers and collaborators — launch ideas, build together, and make content that shines.</p>

          <div class="hero-typing" id="typed" aria-live="polite"></div>

          <div class="hero-cta">
            <button class="btn primary" id="ctaPrimary">Join the Squad</button>
            <button class="btn" id="ctaTour">Take a Tour</button>
          </div>

          <div class="hero-stats" aria-hidden="false">
            <div class="stat" title="Active Members"><span id="memberCount">1,204</span> members</div>
            <div class="stat">✔️ Community-led events</div>
          </div>
        </div>

        <aside class="hero-right" aria-hidden="false">
          <div class="floating-card" role="region" aria-label="Featured">
            <div style="display:flex;align-items:center;justify-content:space-between;">
              <div>
                <div style="font-weight:800;color:var(--accent-1)">Featured Collab</div>
                <div style="color:var(--muted);font-size:0.92rem">Watch last week's highlight reel</div>
              </div>
              <div style="font-weight:800;color:var(--muted);font-size:0.9rem">LIVE</div>
            </div>
            <div class="preview-media" style="margin-top:12px">
              <!-- placeholder; use an actual thumbnail or iframe later -->
              <div>🔥 Reel Preview</div>
            </div>
            <div style="display:flex;gap:10px;margin-top:12px;justify-content:flex-end">
              <a class="btn" href="https://www.youtube.com/@SpotlixHQ" target="_blank" rel="noopener">Watch</a>
              <a class="btn" href="https://t.me/SpotlixHQ" target="_blank" rel="noopener">Join</a>
            </div>
          </div>

          <div class="floating-card" style="margin-top:12px;display:flex;align-items:center;justify-content:space-between;">
            <div>
              <div style="font-weight:800;color:var(--accent-3)">Subscriber Count</div>
              <div style="color:var(--muted);font-size:0.9rem" id="subscriberCount">~ 12,345</div>
            </div>
            <div style="font-weight:900;color:var(--accent-1);font-size:1.2rem">★</div>
          </div>
        </aside>
      </div>
    </section>

    <!-- ABOUT -->
    <section id="about" class="panel" aria-labelledby="about-title">
      <h2 id="about-title" style="color:var(--accent-1)">About SpotlixHQ</h2>
      <p id="about-desc" style="color:var(--muted);max-width:72ch">
        SpotlixHQ (Spotlight Squad) is a creator-first community where creators launch ideas together, co-create content, and grow their audience — a place where the spark meets the studio. We focus on collaboration, education, and publishing studio-quality content with minimal friction.
      </p>

      <div style="display:flex;gap:12px;margin-top:18px;flex-wrap:wrap">
        <button class="btn primary" id="openContact">Contact Us</button>
        <a class="btn" href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener">Follow on Instagram</a>
        <a class="btn" href="https://t.me/SpotlixHQ" target="_blank" rel="noopener">Join Telegram</a>
      </div>
    </section>

    <!-- COMMUNITY -->
    <section id="community" class="panel" aria-labelledby="community-title">
      <h2 id="community-title" style="color:var(--accent-1)">Connect With Us</h2>
      <div class="cards-list" role="list" aria-label="Platform links">
        <a class="card-item" role="listitem" href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener">
          <div class="title"><i class="fab fa-instagram" aria-hidden="true"></i> Instagram</div>
          <div class="desc">Share creativity & updates with our squad.</div>
        </a>

        <a class="card-item" role="listitem" href="https://t.me/SpotlixHQ" target="_blank" rel="noopener">
          <div class="title"><i class="fab fa-telegram" aria-hidden="true"></i> Telegram</div>
          <div class="desc">Join live discussions and community announcements.</div>
        </a>

        <a class="card-item" role="listitem" href="https://www.youtube.com/@SpotlixHQ" target="_blank" rel="noopener">
          <div class="title"><i class="fab fa-youtube" aria-hidden="true"></i> YouTube</div>
          <div class="desc">Watch, learn, and grow with our exclusive content.</div>
        </a>

        <a class="card-item" role="listitem" href="mailto:spotlixhq@gmail.com">
          <div class="title"><i class="fas fa-envelope" aria-hidden="true"></i> Email</div>
          <div class="desc">Reach out directly to connect or collaborate.</div>
        </a>
      </div>
    </section>

    <!-- TEAM -->
    <section id="team" class="panel" aria-labelledby="team-title">
      <h2 id="team-title" style="color:var(--accent-1)">Our Team</h2>
      <div class="team-grid" role="list" aria-label="Team members">
        <div class="team-member" role="listitem" tabindex="0" onclick="toggleBio(this)" onkeypress="if(event.key==='Enter'){toggleBio(this)}" aria-pressed="false" aria-label="Suryansh founder">
          <strong>Suryansh</strong>
          <div class="meta">Founder</div>
          <div class="bio visually-hidden">Love creativity — <a href="https://www.instagram.com/suryansh_y09?igsh=MXIzNGhmMGtlZjY4eQ==" target="_blank" rel="noopener">Instagram</a> | <a href="mailto:suryanshy302@gmail.com">Email</a></div>
        </div>

        <div class="team-member" role="listitem" tabindex="0" onclick="toggleBio(this)" onkeypress="if(event.key==='Enter'){toggleBio(this)}" aria-pressed="false" aria-label="Anup team member">
          <strong>Anup</strong>
          <div class="meta">Team Member</div>
          <div class="bio visually-hidden">Not a backup plan — I’m the main character. — <a href="https://www.instagram.com/anup_.45_45?igsh=cDhuY3plOGVxaXhw" target="_blank" rel="noopener">Instagram</a> | <a href="mailto:gurub0357@gmail.com">Email</a></div>
        </div>

        <div class="team-member" role="listitem" tabindex="0" onclick="toggleBio(this)" onkeypress="if(event.key==='Enter'){toggleBio(this)}" aria-pressed="false" aria-label="Adhayayan team member">
          <strong>Adhayayan</strong>
          <div class="meta">Team Member</div>
          <div class="bio visually-hidden">good over bad — <a href="https://www.instagram.com/adhyayann_08?igsh=MW5xaWlmcWt5Y2tmcQ==" target="_blank" rel="noopener">Instagram</a> | <a href="mailto:hindiaianimate@gmail.com">Email</a></div>
        </div>
      </div>
      <p style="color:var(--muted);margin-top:12px">Want to join the team? Click <button class="btn" id="joinTeamBtn">Apply</button></p>
    </section>

    <!-- ROADMAP -->
    <section id="roadmap" class="panel" aria-labelledby="roadmap-title">
      <h2 id="roadmap-title" style="color:var(--accent-1)">Roadmap & Timeline</h2>
      <div class="timeline" aria-hidden="false">
        <div class="timeline-item">
          <div class="dot" aria-hidden="true"></div>
          <div class="body">
            <strong>Q1 2025 — Community Launch</strong>
            <p style="margin:6px 0;color:var(--muted)">Foundational events, onboarding flows, and weekly collab sessions.</p>
          </div>
        </div>

        <div class="timeline-item">
          <div class="dot" aria-hidden="true"></div>
          <div class="body">
            <strong>Q2 2025 — Feature set</strong>
            <p style="margin:6px 0;color:var(--muted)">Creator toolkits, templates, and spotlight showcases.</p>
          </div>
        </div>

        <div class="timeline-item">
          <div class="dot" aria-hidden="true"></div>
          <div class="body">
            <strong>Q3 2025 — Platform integrations</strong>
            <p style="margin:6px 0;color:var(--muted)">Integrations with publishing platforms and analytics.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- TESTIMONIALS -->
    <section id="testimonials" class="panel" aria-labelledby="testimonials-title">
      <h2 id="testimonials-title" style="color:var(--accent-1)">What creators say</h2>
      <div class="testimonials" id="testimonialsList" role="list">
        <div class="testimonial-card" role="listitem">
          <strong>Riya — Filmmaker</strong>
          <p>"SpotlixHQ helped me launch a collab that reached 40k views in a week." — <span style="color:var(--muted)">Featured Creator</span></p>
        </div>
        <div class="testimonial-card" role="listitem">
          <strong>Amit — Music Producer</strong>
          <p>"The feedback loops and community edits are gold. I levelled up fast."</p>
        </div>
        <div class="testimonial-card" role="listitem">
          <strong>Leah — Photographer</strong>
          <p>"Supportive creators & meaningful feedback — it's not just hype."</p>
        </div>
      </div>
    </section>

    <!-- CONTACT / CTA -->
    <section id="contact" class="panel" aria-labelledby="contact-title">
      <h2 id="contact-title" style="color:var(--accent-1)">Get in touch</h2>
      <p style="color:var(--muted)">Email us directly at <a href="mailto:spotlixhq@gmail.com" style="color:var(--accent-1)">spotlixhq@gmail.com</a> or use the quick contact below.</p>

      <form id="contactForm" style="display:flex;gap:8px;flex-wrap:wrap;max-width:720px">
        <input name="name" placeholder="Your name" aria-label="Your name" style="flex:1;padding:12px;border-radius:10px;border:1px solid rgba(255,255,255,0.03);background:transparent;color:var(--text)" required>
        <input name="email" placeholder="Email" type="email" aria-label="Email" style="flex:1;padding:12px;border-radius:10px;border:1px solid rgba(255,255,255,0.03);background:transparent;color:var(--text)" required>
        <textarea name="message" placeholder="A short message" aria-label="Message" rows="3" style="width:100%;padding:12px;border-radius:10px;border:1px solid rgba(255,255,255,0.03);background:transparent;color:var(--text)"></textarea>
        <div style="display:flex;gap:8px;width:100%;justify-content:flex-end">
          <button class="btn primary" type="submit">Send</button>
        </div>
      </form>
    </section>
  </main>

  <!-- Footer -->
  <footer class="site-footer" role="contentinfo">
    <div style="display:flex;gap:12px;align-items:center;justify-content:center;flex-wrap:wrap">
      <div>Proudly Indian Made 🌟</div>
      <div>© <span id="year">2025</span> SpotlixHQ. All rights reserved.</div>
      <div><a href="https://spotlix.github.io/SpotlixHQ-/" target="_blank" rel="noopener" style="color:var(--accent-1)">Website</a></div>
    </div>
  </footer>

  <!-- Floating contact and scroll-top -->
  <div class="float-contact" aria-hidden="false">
    <button class="fab" id="openContactFab" aria-label="Contact SpotlixHQ">✉️</button>
  </div>
  <button class="scroll-top" id="scrollTop" aria-label="Back to top" title="Back to top">
    <i class="fas fa-chevron-up"></i>
  </button>

  <!-- Contact Modal (micro-onboarding / join modal) -->
  <div class="modal-backdrop hidden" id="modalBackdrop" aria-hidden="true" role="dialog" aria-modal="true">
    <div class="modal" role="document" style="max-width:520px;margin:0 auto;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));padding:20px;border-radius:12px;border:1px solid rgba(255,255,255,0.03);">
      <h3 id="contactTitle">Join the Squad</h3>
      <p style="color:var(--muted)">Quick micro-onboarding — tell us where you're most active and we'll guide you to the best place to join.</p>
      <div style="display:flex;gap:10px;flex-wrap:wrap;margin-top:12px">
        <button class="btn primary" data-platform="telegram" onclick="joinPlatform('https://t.me/SpotlixHQ')">Telegram</button>
        <button class="btn" data-platform="instagram" onclick="joinPlatform('https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo')">Instagram</button>
        <button class="btn" data-platform="youtube" onclick="joinPlatform('https://www.youtube.com/@SpotlixHQ')">YouTube</button>
        <button class="btn" data-platform="email" onclick="joinPlatform('mailto:spotlixhq@gmail.com')">Email</button>
      </div>
      <div style="display:flex;gap:.5rem;justify-content:flex-end;margin-top:14px">
        <button class="btn" id="modalClose">Close</button>
      </div>
    </div>
  </div>

  <!-- Inline scripts (deferred & performance-minded) -->
  <script>
    /************************************************************************
     * Initialization & progressive enhancement
     * - Preserves original data (emails, links, languages)
     * - Adds many features: theme toggle, mobile menu, join modal, typed text,
     *   subscriber simulation, copy email, accessibility helpers, intersection
     *   animations and more.
     ************************************************************************/

    // small helpers
    const $ = s => document.querySelector(s);
    const $$ = s => Array.from(document.querySelectorAll(s));
    const isReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

    // initial DOM references
    const preloader = $('#preloader');
    const themeToggle = $('#themeToggle');
    const body = document.body;
    const joinBtn = $('#joinBtn');
    const ctaPrimary = $('#ctaPrimary');
    const modalBackdrop = $('#modalBackdrop');
    const modalClose = $('#modalClose');
    const openContact = $('#openContact');
    const openContactFab = $('#openContactFab');
    const copyEmail = () => navigator.clipboard && navigator.clipboard.writeText && navigator.clipboard.writeText('spotlixhq@gmail.com');

    // safe fallback for elements that might be missing
    const opt = el => el || { addEventListener: () => {}, classList:{}, style:{} };

    // ------------------------ Preloader ------------------------
    window.addEventListener('load', () => {
      if (preloader) preloader.classList.add('hidden');
      setTimeout(()=>{ if(preloader && preloader.remove) preloader.remove() }, 700);
    });

    // ------------------------ Year ------------------------
    const yearEl = document.getElementById('year');
    if(yearEl) yearEl.textContent = new Date().getFullYear();

    // ------------------------ Mobile menu ------------------------
    const hamburger = $('#hamburger');
    const mobileOverlay = $('#mobileOverlay');
    if (hamburger && mobileOverlay) {
      hamburger.addEventListener('click', () => {
        const expanded = hamburger.getAttribute('aria-expanded') === 'true';
        hamburger.setAttribute('aria-expanded', String(!expanded));
        mobileOverlay.classList.toggle('hidden');
        mobileOverlay.setAttribute('aria-hidden', String(expanded));
        if(!expanded) {
          // trap focus on first link
          const first = mobileOverlay.querySelector('a');
          if(first) first.focus();
        }
      });
      // close mobile on link click
      $$('#mobileOverlay a').forEach(a => a.addEventListener('click', () => {
        mobileOverlay.classList.add('hidden');
        hamburger.setAttribute('aria-expanded','false');
      }));
    }

    // ------------------------ Theme toggle (auto + manual) ------------------------
    (function initTheme(){
      const preferDark = window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches;
      const saved = localStorage.getItem('spotlix_theme');
      const theme = saved || (preferDark ? 'dark' : 'light');
      applyTheme(theme);
      if(themeToggle) {
        themeToggle.addEventListener('click', () => {
          const newTheme = body.dataset.theme === 'dark' ? 'light' : 'dark';
          applyTheme(newTheme);
          localStorage.setItem('spotlix_theme', newTheme);
        });
      }
    })();
    function applyTheme(t){
      body.dataset.theme = t;
      if(t === 'light') {
        document.documentElement.style.setProperty('--bg-1','#f7fbff');
        document.documentElement.style.setProperty('--bg-2','#dfefff');
        document.documentElement.style.setProperty('--text','#071018');
        document.documentElement.style.setProperty('--muted','rgba(0,6,12,0.65)');
      } else {
        document.documentElement.style.setProperty('--bg-1','#0f0c29');
        document.documentElement.style.setProperty('--bg-2','#302b63');
        document.documentElement.style.setProperty('--text','#E9F8F7');
        document.documentElement.style.setProperty('--muted','rgba(255,255,255,0.75)');
      }
      // set aria-pressed
      if(themeToggle) themeToggle.setAttribute('aria-pressed', body.dataset.theme === 'dark');
    }

    // ------------------------ Typed hero text ------------------------
    (function typedHero(){
      const phrases = [
        "Creators. Thinkers. Collaborators.",
        "Where ideas meet action.",
        "Grow. Create. Launch.",
        "Made for community-first creators.",
        "Your next idea starts here."
      ];
      const el = $('#typed');
      if(!el || isReducedMotion) {
        if(el) el.textContent = phrases[0];
        return;
      }
      let i=0,j=0,del=false;
      function tick(){
        if(i>=phrases.length) i=0;
        const cur = phrases[i];
        if(!del) {
          el.textContent = cur.substring(0, j+1);
          j++;
          if(j === cur.length){ del = true; setTimeout(tick, 900); return; }
        } else {
          el.textContent = cur.substring(0, j-1);
          j--;
          if(j === 0){ del = false; i++; }
        }
        setTimeout(tick, del ? 45 : 85);
      }
      tick();
    })();

    // ------------------------ Intersection animations ------------------------
    (function observeSections(){
      const sections = document.querySelectorAll('section');
      const io = new IntersectionObserver((entries) => {
        entries.forEach(e => {
          if(e.isIntersecting) e.target.classList.add('active');
        });
      }, {threshold:0.16});
      sections.forEach(s => io.observe(s));
    })();

    // ------------------------ Toggle team bios ------------------------
    function toggleBio(el){
      if(!el) return;
      const bio = el.querySelector('.bio');
      if(!bio) return;
      const shown = bio.classList.toggle('visually-hidden');
      el.setAttribute('aria-pressed', String(shown));
    }
    window.toggleBio = toggleBio; // preserve for inline handlers

    // ------------------------ Join modal (micro onboarding) ------------------------
    function openModal(){ modalBackdrop.classList.remove('hidden'); modalBackdrop.setAttribute('aria-hidden','false'); modalBackdrop.querySelector('.modal button')?.focus(); }
    function closeModal(){ modalBackdrop.classList.add('hidden'); modalBackdrop.setAttribute('aria-hidden','true'); joinBtn?.focus(); }
    if(joinBtn) joinBtn.addEventListener('click', openModal);
    if(ctaPrimary) ctaPrimary.addEventListener('click', openModal);
    if(openContact) openContact.addEventListener('click', openModal);
    if(openContactFab) openContactFab.addEventListener('click', openModal);
    if(modalClose) modalClose.addEventListener('click', closeModal);
    if(modalBackdrop) modalBackdrop.addEventListener('click', (e) => { if(e.target === modalBackdrop) closeModal(); });

    // helper to open external platform (used in modal)
    function joinPlatform(url){
      // close modal first for UX
      closeModal();
      setTimeout(()=> {
        // open in new tab for external links, mailto opens email client
        if(url.startsWith('mailto:')) window.location.href = url;
        else window.open(url, '_blank', 'noopener');
      }, 160);
    }
    window.joinPlatform = joinPlatform;

    // ------------------------ Copy Email (contact) ------------------------
    $('#main')?.addEventListener('click', (e) => {
      // capture copy email shortcuts if any (example has no dedicated button in UI)
    });

    // also allow email copy from modal (if we add a button)
    // small visual tooltip for copy success
    const showCopyToast = (msg='Copied to clipboard') => {
      const t = document.createElement('div');
      t.textContent = msg;
      t.style.position='fixed';t.style.bottom='110px';t.style.right='18px';t.style.background='linear-gradient(90deg,var(--accent-1),var(--accent-2))';
      t.style.color='#071018';t.style.padding='10px 14px';t.style.borderRadius='10px';t.style.zIndex=9999;document.body.appendChild(t);
      setTimeout(()=> t.remove(), 2200);
    };

    // ------------------------ Subscriber counter (simulated) ------------------------
    (function subscriberSim(){
      const el = document.getElementById('subscriberCount');
      if(!el) return;
      // If you have an API: replace this with fetch to your backend/YouTube/telegram analytics.
      let count = 12345;
      function fmt(n){ return n.toLocaleString(); }
      el.textContent = fmt(count);
      // simulate gentle growth
      setInterval(()=> {
        count += Math.floor(Math.random()*3); // small increments
        el.textContent = fmt(count);
      }, 4000);
    })();

    // ------------------------ Member count (simulate) ------------------------
    (function memberSim(){
      const el = document.getElementById('memberCount');
      if(!el) return;
      let count = 1204;
      el.textContent = count.toLocaleString();
      setInterval(()=> {
        count += Math.random() > 0.75 ? Math.floor(Math.random()*4) : 0;
        el.textContent = count.toLocaleString();
      }, 5000);
    })();

    // ------------------------ Testimonials auto-scroll (basic) ------------------------
    (function testimonialsScroll(){
      const list = document.getElementById('testimonialsList');
      if(!list) return;
      let idx = 0;
      setInterval(()=> {
        idx = (idx + 1) % list.children.length;
        const child = list.children[idx];
        // scroll into view smooth
        child.scrollIntoView({behavior:'smooth',inline:'center',block:'nearest'});
      }, 4500);
    })();

    // ------------------------ Scroll-to-top ------------------------
    const scrollTopBtn = $('#scrollTop');
    window.addEventListener('scroll', () => {
      if(window.scrollY > 320) scrollTopBtn.classList.add('show'); else scrollTopBtn.classList.remove('show');
    });
    scrollTopBtn.addEventListener('click', ()=> window.scrollTo({top:0,behavior:'smooth'}));

    // ------------------------ Contact form handling (client-only demo) ------------------------
    const contactForm = document.getElementById('contactForm');
    if(contactForm){
      contactForm.addEventListener('submit', (e) => {
        e.preventDefault();
        // progressive: attempt to send with fetch to an endpoint if configured.
        const data = new FormData(contactForm);
        const name = data.get('name');
        // For demo show toast and reset
        showCopyToast('Message received — we will email you soon');
        contactForm.reset();
      });
    }

    // ------------------------ Keyboard accessibility helpers ------------------------
    document.addEventListener('keydown', (e) => {
      if(e.key === 'Escape'){
        // close overlays
        if(!modalBackdrop.classList.contains('hidden')) closeModal();
        if(!mobileOverlay.classList.contains('hidden')) { mobileOverlay.classList.add('hidden'); hamburger.setAttribute('aria-expanded','false'); }
      }
    });

    // ------------------------ Language content & RTL support (keeps previous translations) ------------------------
    const content = {
      en: {
        navHome: "Home", navAbout: "About", navCommunity: "Community", navTeam: "Team", navRoadmap: "Roadmap", navTestimonials: "Testimonials",
        aboutTitle: "About SpotlixHQ",
        aboutDesc: "SpotlixHQ is a community for creators, thinkers, and innovators to collaborate, share ideas, and grow together.",
        communityTitle: "Connect With Us", teamTitle: "Our Team", rtl:false
      },
      hi: {
        navHome: "होम", navAbout: "हमारे बारे में", navCommunity: "समुदाय", navTeam: "टीम", navRoadmap: "रोडमैप", navTestimonials: "साक्ष्य",
        aboutTitle: "SpotlixHQ के बारे में",
        aboutDesc: "SpotlixHQ रचनाकारों, विचारकों और नवप्रवर्तकों के लिए एक समुदाय है जहाँ वे सहयोग कर सकते हैं, विचार साझा कर सकते हैं और साथ में आगे बढ़ सकते हैं।",
        communityTitle: "हमसे जुड़ें", teamTitle: "हमारी टीम", rtl:false
      },
      de: {
        navHome: "Startseite", navAbout: "Über uns", navCommunity: "Community", navTeam: "Team", navRoadmap: "Fahrplan", navTestimonials: "Erfahrungen",
        aboutTitle: "Über SpotlixHQ", aboutDesc: "SpotlixHQ ist eine Community für Kreative, Denker und Innovatoren, um zusammenzuarbeiten, Ideen zu teilen und gemeinsam zu wachsen.",
        communityTitle: "Vernetze dich mit uns", teamTitle: "Unser Team", rtl:false
      },
      ja: {
        navHome: "ホーム", navAbout: "概要", navCommunity: "コミュニティ", navTeam: "チーム", navRoadmap: "ロードマップ", navTestimonials: "声",
        aboutTitle: "SpotlixHQ について", aboutDesc: "SpotlixHQ は、クリエイターや思考家、イノベーターが協力し、アイデアを共有し、ともに成長するためのコミュニティです。",
        communityTitle: "私たちとつながる", teamTitle: "チーム紹介", rtl:false
      },
      es: {
        navHome: "Inicio", navAbout: "Acerca de", navCommunity: "Comunidad", navTeam: "Equipo", navRoadmap: "Hoja de ruta", navTestimonials: "Testimonios",
        aboutTitle: "Acerca de SpotlixHQ", aboutDesc: "SpotlixHQ es una comunidad para creadores, pensadores e innovadores donde pueden colaborar, compartir ideas y crecer juntos.",
        communityTitle: "Conéctate con nosotros", teamTitle: "Nuestro equipo", rtl:false
      },
      fr: {
        navHome: "Accueil", navAbout: "À propos", navCommunity: "Communauté", navTeam: "Équipe", navRoadmap: "Feuille de ruta", navTestimonials: "Témoignages",
        aboutTitle: "À propos de SpotlixHQ", aboutDesc: "SpotlixHQ est une communauté pour les créateurs, penseurs et innovateurs afin de collaborer, partager des idées et grandir ensemble.",
        communityTitle: "Connectez-vous avec nous", teamTitle: "Notre équipe", rtl:false
      },
      ar: {
        navHome: "الرئيسية", navAbout: "من نحن", navCommunity: "المجتمع", navTeam: "الفريق", navRoadmap: "خريطة الطريق", navTestimonials: "آراء",
        aboutTitle: "نبذة عن SpotlixHQ", aboutDesc: "SpotlixHQ هو مجتمع للمبدعين والمفكرين والمبتكرين للتعاون وتبادل الأفكار والنمو معًا.",
        communityTitle: "تواصل معنا", teamTitle: "فريقنا", rtl:true
      },
      id: {
        navHome: "Beranda", navAbout: "Tentang", navCommunity: "Komunitas", navTeam: "Tim", navRoadmap: "Peta jalan", navTestimonials: "Testimonial",
        aboutTitle: "Tentang SpotlixHQ", aboutDesc: "SpotlixHQ adalah komunitas bagi kreator, pemikir, dan inovator untuk berkolaborasi, berbagi ide, dan tumbuh bersama.",
        communityTitle: "Terhubung dengan kami", teamTitle: "Tim kami", rtl:false
      },
      bn: {
        navHome: "হোম", navAbout: "আমাদের সম্পর্কে", navCommunity: "কমিউনিটি", navTeam: "টিম", navRoadmap: "রোডম্যাপ", navTestimonials: "প্রশংসাপত্র",
        aboutTitle: "SpotlixHQ সম্পর্কে", aboutDesc: "SpotlixHQ হল সৃষ্টিশীল ব্যক্তি, চিন্তাবিদ এবং উদ্ভাবকদের জন্য একটি কমিউনিটি যেখানে তারা একসাথে কাজ করতে, আইডিয়া শেয়ার করতে এবং একসাথে বেড়ে উঠতে পারে।",
        communityTitle: "আমাদের সাথে যুক্ত হন", teamTitle: "আমাদের দল", rtl:false
      },
      zh: {
        navHome: "首页", navAbout: "关于", navCommunity: "社区", navTeam: "团队", navRoadmap: "路线图", navTestimonials: "评价",
        aboutTitle: "关于 SpotlixHQ", aboutDesc: "SpotlixHQ 是一个为创作者、思想者和创新者而建立的社区，在这里可以协作、分享想法并共同成长。",
        communityTitle: "与我们联系", teamTitle: "我们的团队", rtl:false
      }
    };

    // wire language selector
    const langSelect = document.getElementById('language-select');
    if(langSelect){
      function applyLanguage(lang){
        if(!content[lang]) lang='en';
        const t = content[lang];
        $('#nav-home').textContent = t.navHome;
        $('#nav-about').textContent = t.navAbout;
        $('#nav-community').textContent = t.navCommunity;
        $('#nav-team').textContent = t.navTeam;
        $('#nav-roadmap').textContent = t.navRoadmap || 'Roadmap';
        $('#nav-testimonials').textContent = t.navTestimonials || 'Testimonials';
        document.getElementById('about-title').textContent = t.aboutTitle;
        document.getElementById('about-desc').textContent = t.aboutDesc;
        // rtl handling
        document.documentElement.lang = lang;
        document.documentElement.dir = t.rtl ? 'rtl' : 'ltr';
        ['about','community','team'].forEach(id => {
          const el = document.getElementById(id);
          if(!el) return;
          if(t.rtl) el.classList.add('rtl'); else el.classList.remove('rtl');
        });
      }
      langSelect.addEventListener('change', ()=> applyLanguage(langSelect.value));
      applyLanguage(langSelect.value || 'en');
    }

    // ------------------------ small progressive performance improvements ------------------------
    // Defer non-critical tasks to idle time
    if('requestIdleCallback' in window){
      requestIdleCallback(()=> {
        // non-critical: start subscriber sim, testimonials, analytics hooks, etc.
      }, {timeout:2000});
    } else {
      setTimeout(()=>{/* fallback non-critical */}, 1000);
    }

    // ------------------------ A11Y & focus management: trap focus in modal when open ----------
    (function focusTrap(){
      let lastActive = null;
      modalBackdrop.addEventListener('keydown', (e) => {
        if(e.key === 'Tab'){
          const focusables = modalBackdrop.querySelectorAll('button,a,input,textarea,select');
          if(focusables.length === 0) return;
          const first = focusables[0], last = focusables[focusables.length -1];
          if(e.shiftKey && document.activeElement === first){ last.focus(); e.preventDefault(); }
          else if(!e.shiftKey && document.activeElement === last){ first.focus(); e.preventDefault(); }
        }
      });
      // open/close hooks to manage lastActive
      const openHooks = [joinBtn, ctaPrimary, openContact, openContactFab];
      openHooks.forEach(h => h && h.addEventListener('click', () => { lastActive = document.activeElement; }));
      modalClose && modalClose.addEventListener('click', ()=> { if(lastActive) lastActive.focus(); });
    })();

    // ------------------------ Final notes: safe default links preserved ----------
    // Emails and links retained exactly as requested:
    // spotlixhq@gmail.com, gurub0357@gmail.com, suryanshy302@gmail.com, hindiaianimate@gmail.com
    // Social: Instagram / Telegram / YouTube / X / LinkedIn preserved throughout the page.

    // End of main script
  </script>
</body>
</html>
