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
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
  <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous" defer></script>

  <style>
    /* ---------- Variables & reset ---------- */
    :root{
      --neon:#00fff7;
      --neon-2:#ff00ff;
      --bg-1:#0f0c29;
      --bg-2:#302b63;
      --card-bg: rgba(0,0,0,0.65);
      --glass: rgba(255,255,255,0.02);
      --max-width:1100px;
      --radius:16px;
      --transition: 0.32s cubic-bezier(.2,.9,.2,1);
      --accent-contrast: rgba(255,255,255,0.92);
      --muted: rgba(255,255,255,0.85);
    }
    *,*::before,*::after{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family:'Poppins',system-ui,-apple-system,Segoe UI,Roboto,"Helvetica Neue",Arial;
      color:#fff;
      background: linear-gradient(-45deg,var(--bg-1),var(--bg-2),#24243e,#1f1c2c);
      background-size:400% 400%; animation: bgAnim 20s linear infinite;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      overflow-x:hidden;
      line-height:1.45;
    }
    @keyframes bgAnim{0%{background-position:0 50%}50%{background-position:100% 50%}100%{background-position:0 50%}}

    /* Respect reduced motion */
    @media (prefers-reduced-motion: reduce){
      *{animation-duration:0.001ms !important; animation-iteration-count:1 !important; transition:none !important}
    }

    /* ---------- Preloader ---------- */
    .preloader{
      position:fixed; inset:0; display:flex; align-items:center; justify-content:center; z-index:9999;
      background: linear-gradient(90deg,#050317,rgba(0,0,0,0.6));
    }
    .preloader.hidden{opacity:0;visibility:hidden;pointer-events:none;transition:opacity .6s}
    .loader{
      width:68px;height:68px;border-radius:50%;border:4px solid rgba(0,255,247,0.18);
      border-top:4px solid var(--neon); animation:spin 900ms linear infinite; box-shadow:0 0 30px rgba(0,255,247,0.08);
    }
    @keyframes spin{to{transform:rotate(360deg)}}

    /* ---------- Particles & neon shapes ---------- */
    .particle{position:absolute;width:6px;height:6px;border-radius:50%;background:var(--neon);opacity:.7;filter:drop-shadow(0 0 6px rgba(0,255,247,.25)); will-change:transform}
    .neon-shape{position:absolute;border-radius:50%;opacity:.12;filter:blur(60px);mix-blend-mode:screen;will-change:transform}

    /* ---------- Header / nav ---------- */
    header{position:fixed;top:12px;left:0;right:0;z-index:60;display:flex;justify-content:center}
    nav[role="navigation"]{
      width:calc(100% - 32px); max-width:var(--max-width); display:flex;align-items:center;gap:.75rem;padding:.75rem 1rem;
      align-items:center;backdrop-filter: blur(8px);background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius:12px;
    }
    .nav-left{display:flex;align-items:center;gap:1rem;flex:1;min-width:0}
    .nav-logo{display:flex;align-items:center;gap:.6rem;font-weight:700;color:var(--neon);font-size:1.12rem;text-shadow:0 0 8px var(--neon);outline: none}
    .nav-logo svg{height:34px;width:34px}
    .nav-links{display:flex;gap:1rem;align-items:center;flex-wrap:wrap}
    .nav-links a{color:var(--neon);text-decoration:none;font-weight:600;padding:.35rem .4rem;border-radius:8px;position:relative;transition:var(--transition)}
    .nav-links a:focus{outline:2px solid rgba(0,255,247,.12);outline-offset:2px}
    .nav-links a:hover{transform:translateY(-3px);text-shadow:0 0 10px var(--neon)}
    .nav-socials{display:flex;gap:.45rem;align-items:center;margin-left:auto}
    .nav-socials a{padding:.35rem;border-radius:8px;color:var(--neon);text-decoration:none;display:inline-flex;align-items:center;justify-content:center}
    .nav-socials a:focus{outline:2px solid rgba(255,255,255,0.04)}
    .nav-socials a:hover i{transform:scale(1.08);color:var(--neon-2)}
    #language-select{background:transparent;border:1px solid rgba(255,255,255,.06);padding:.28rem .46rem;border-radius:6px;color:var(--neon);font-weight:600}

    /* Mobile hamburger */
    .hamburger{display:none;background:transparent;border:0;color:var(--neon);font-size:1.2rem;padding:.4rem;margin-left:.3rem}
    .mobile-menu{display:none;position:fixed;inset:76px 12px auto 12px;background:linear-gradient(180deg, rgba(0,0,0,0.6), rgba(0,0,0,0.5));backdrop-filter:blur(8px);border-radius:12px;padding:1rem;z-index:62}
    .mobile-menu a{display:block;padding:.6rem 0;color:var(--neon);font-weight:600}

    /* ---------- Main ---------- */
    main{padding-top:120px;max-width:var(--max-width);margin:0 auto;padding-bottom:100px}
    section{min-height:calc(100vh - 140px);display:flex;align-items:center;justify-content:center;padding:2rem;position:relative;opacity:0;transform:translateY(40px);transition:opacity .9s ease, transform .9s ease}
    section.active{opacity:1;transform:none}

    .container{width:100%;max-width:900px;padding:2.2rem;border-radius:var(--radius);background:var(--card-bg);box-shadow:0 10px 40px rgba(0,0,0,0.5), 0 0 60px rgba(0,255,247,0.04);border:1px solid rgba(0,255,247,0.06);position:relative;z-index:2}

    /* Hero */
    .logo{font-size:2.6rem;font-weight:800;color:var(--neon);letter-spacing:.6px;text-shadow:0 0 8px var(--neon)}
    .tagline{margin:.6rem 0 1rem;color:var(--muted);font-weight:600}
    .typing{color:var(--neon);font-weight:700;font-size:1.05rem;height:36px;overflow:hidden;border-right:2px solid var(--neon);white-space:nowrap;animation: blink 700ms step-end infinite}
    @keyframes blink{50%{border-color:transparent}}

    /* cards */
    .cards{display:flex;flex-direction:column;gap:1rem;margin-top:1rem}
    .card{display:flex;align-items:center;gap:12px;padding:1rem;border-radius:12px;background:linear-gradient(180deg, rgba(0,255,247,0.03), rgba(0,255,247,0.01));border:1px solid rgba(0,255,247,0.06);color:var(--neon);font-weight:700;text-decoration:none;transition:var(--transition)}
    .card i{font-size:1.2rem;min-width:28px;text-align:center}
    .card:hover{transform:translateY(-6px);box-shadow:0 8px 30px rgba(0,255,247,0.06), 0 0 40px rgba(0,255,247,0.03)}

    /* team */
    .team{display:flex;flex-wrap:wrap;gap:1rem;margin-top:1rem;justify-content:center}
    .member{width:160px;padding:1rem;border-radius:12px;background:linear-gradient(180deg, rgba(0,255,247,0.02), rgba(255,255,255,0.01));border:1px solid rgba(0,255,247,0.04);text-align:center;cursor:pointer;user-select:none}
    .member:focus{outline:2px solid rgba(0,255,247,0.08)}
    .member strong{display:block;margin-bottom:.25rem}
    .bio{display:none;color:var(--neon);font-size:.9rem;margin-top:.5rem}
    .show-bio{display:block}

    /* scroll indicator */
    .scroll-indicator{position:absolute;bottom:18px;left:50%;transform:translateX(-50%);width:28px;height:44px;border:2px solid var(--neon);border-radius:14px;display:flex;align-items:flex-start;justify-content:center;padding-top:6px}
    .scroll-indicator::after{content:'';width:7px;height:7px;background:var(--neon);border-radius:50%;animation:scrollBounce 1.5s infinite}
    @keyframes scrollBounce{0%{transform:translateY(0)}50%{transform:translateY(18px)}100%{transform:translateY(0)}}

    /* footer */
    footer{margin-top:2rem;text-align:center;color:var(--neon);opacity:.9;padding:1rem;border-top:1px solid rgba(0,255,247,0.04);border-radius:8px}

    /* scroll top */
    .scroll-top{position:fixed;right:24px;bottom:24px;width:52px;height:52px;border-radius:50%;display:flex;align-items:center;justify-content:center;border:2px solid rgba(0,255,247,0.08);background:transparent;color:var(--neon);cursor:pointer;opacity:0;visibility:hidden;transition:var(--transition);z-index:60}
    .scroll-top.show{opacity:1;visibility:visible;transform:translateY(0)}
    .scroll-top:hover{transform:translateY(-6px) scale(1.04);background:var(--neon);color:#0f0c29;box-shadow:0 6px 30px rgba(0,255,247,0.08)}

    /* modal */
    .modal-backdrop{position:fixed;inset:0;background:rgba(0,0,0,0.6);display:none;align-items:center;justify-content:center;z-index:80}
    .modal{background:var(--card-bg);padding:1.4rem;border-radius:14px;max-width:420px;width:92%;border:1px solid rgba(0,255,247,0.05)}
    .modal h3{color:var(--neon);margin-bottom:.5rem}
    .btn{display:inline-flex;gap:.5rem;align-items:center;padding:.5rem .7rem;border-radius:8px;border:0;font-weight:700;cursor:pointer;background:rgba(0,255,247,0.08);color:var(--neon)}
    .btn.primary{background:var(--neon);color:#0f0c29}
    .copy-success{font-size:.9rem;color:#9fffe8;margin-top:.4rem;display:none}

    /* RTL helper */
    .rtl{direction:rtl;text-align:right}

    /* responsive */
    @media (max-width:900px){
      .nav-links{display:none}
      .hamburger{display:inline-block}
      .nav-logo{font-size:1.05rem}
      .container{padding:1.6rem}
      .logo{font-size:2rem}
    }
    @media (max-width:560px){
      .member{width:130px}
      .typing{font-size:.95rem}
      .logo{font-size:1.8rem}
      .nav-socials{display:none}
      nav[role="navigation"]{padding:.6rem}
      .mobile-menu{inset:72px 10px auto 10px}
    }
  </style>
</head>
<body>
  <!-- Preloader -->
  <div class="preloader" id="preloader" role="status" aria-label="Loading">
    <div class="loader" aria-hidden="true"></div>
  </div>

  <!-- Particles (original positions preserved) -->
  <div class="particle" style="top:10%; left:20%; animation-duration:12s;"></div>
  <div class="particle" style="top:50%; left:80%; animation-duration:15s;"></div>
  <div class="particle" style="top:70%; left:40%; animation-duration:18s;"></div>
  <div class="particle" style="top:20%; left:60%; animation-duration:20s;"></div>
  <div class="particle" style="top:80%; left:10%; animation-duration:22s;"></div>
  <div class="particle" style="top:30%; left:30%; animation-duration:19s;"></div>

  <!-- Neon shapes -->
  <div class="neon-shape" style="width:200px;height:200px;background:var(--neon);top:10%;left:5%;animation-duration:25s;"></div>
  <div class="neon-shape" style="width:300px;height:300px;background:var(--neon-2);top:40%;left:60%;animation-duration:35s;"></div>
  <div class="neon-shape" style="width:150px;height:150px;background:#00ff00;top:20%;left:70%;animation-duration:30s;"></div>
  <div class="neon-shape" style="width:250px;height:250px;background:#ff9900;top:60%;left:10%;animation-duration:40s;"></div>

  <!-- Header / nav -->
  <header>
    <nav role="navigation" aria-label="Main navigation">
      <div class="nav-left" style="gap:.9rem">
        <div class="nav-logo" tabindex="0" aria-label="SpotlixHQ - Spotlight Squad">
          <!-- Inline SVG logo -->
          <svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" focusable="false">
            <defs>
              <linearGradient id="g" x1="0" x2="1" y1="0" y2="1">
                <stop offset="0" stop-color="#00fff7"/>
                <stop offset="1" stop-color="#ff00ff"/>
              </linearGradient>
            </defs>
            <circle cx="32" cy="32" r="28" fill="url(#g)" opacity="0.15"/>
            <path d="M20 40c4-7 16-7 20 0" stroke="url(#g)" stroke-width="3" stroke-linecap="round" fill="none"/>
            <circle cx="32" cy="24" r="6" fill="url(#g)"/>
          </svg>
          <span>SpotlixHQ</span>
        </div>

        <div class="nav-links" id="navLinks">
          <a href="#home" id="nav-home">Home</a>
          <a href="#about" id="nav-about">About</a>
          <a href="#community" id="nav-community">Community</a>
          <a href="#team" id="nav-team">Team</a>
        </div>
      </div>

      <!-- Social icons -->
      <div class="nav-socials" role="group" aria-label="Social links">
        <a class="nav-social-link" href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener" aria-label="Instagram">
          <i class="fab fa-instagram" aria-hidden="true"></i>
        </a>
        <a class="nav-social-link" href="https://t.me/SpotlixHQ" target="_blank" rel="noopener" aria-label="Telegram">
          <i class="fab fa-telegram" aria-hidden="true"></i>
        </a>
        <a class="nav-social-link" href="https://www.youtube.com/@SpotlixHQ" target="_blank" rel="noopener" aria-label="YouTube">
          <i class="fab fa-youtube" aria-hidden="true"></i>
        </a>
        <a class="nav-social-link" href="mailto:spotlixhq@gmail.com" aria-label="Email">
          <i class="fas fa-envelope" aria-hidden="true"></i>
        </a>
        <a class="nav-social-link" href="https://x.com/SpotlixHQ" target="_blank" rel="noopener" aria-label="X">
          <i class="fa fa-twitter" aria-hidden="true"></i>
        </a>
        <a class="nav-social-link" href="https://www.linkedin.com/company/spotlixhq" target="_blank" rel="noopener" aria-label="LinkedIn">
          <i class="fa fa-linkedin" aria-hidden="true"></i>
        </a>
      </div>

      <select id="language-select" title="Select Language" aria-label="Select language">
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

      <!-- Hamburger for small screens -->
      <button class="hamburger" id="hamburger" aria-label="Open menu" aria-expanded="false" aria-controls="mobileMenu">
        <i class="fas fa-bars" aria-hidden="true"></i>
      </button>
    </nav>

    <!-- Mobile menu -->
    <div class="mobile-menu" id="mobileMenu" role="menu" aria-hidden="true">
      <a href="#home" role="menuitem">Home</a>
      <a href="#about" role="menuitem">About</a>
      <a href="#community" role="menuitem">Community</a>
      <a href="#team" role="menuitem">Team</a>
      <div style="height:8px"></div>
      <a href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener">Instagram</a>
      <a href="https://t.me/SpotlixHQ" target="_blank" rel="noopener">Telegram</a>
      <a href="https://www.youtube.com/@SpotlixHQ" target="_blank" rel="noopener">YouTube</a>
      <a href="mailto:spotlixhq@gmail.com">Email</a>
    </div>
  </header>

  <main>
    <!-- HOME -->
    <section id="home" aria-labelledby="homeHeading">
      <article class="container" role="region" aria-labelledby="homeHeading">
        <h1 id="homeHeading" class="logo">SpotlixHQ <span style="font-weight:600;color:rgba(255,255,255,.9);font-size:.55em;margin-left:.5rem">— Spotlight Squad</span></h1>
        <p class="tagline">Spotlight Squad is a vibrant creator community shining across platforms. Along with its members — collaborate, create and grow.</p>
        <p id="typed" class="typing" aria-live="polite"></p>

        <div class="scroll-indicator" aria-hidden="true"></div>
      </article>
    </section>

    <!-- ABOUT -->
    <section id="about" aria-labelledby="about-title">
      <article class="container" role="region">
        <h2 id="about-title" style="color:var(--neon);margin-bottom:.6rem">About SpotlixHQ</h2>
        <p id="about-desc" class="tagline" style="max-width:700px;margin:0 auto 10px">
          SpotlixHQ (Spotlight Squad) is a community for creators, thinkers, and innovators to collaborate, share ideas, test new formats and grow together across Instagram, Telegram and YouTube.
        </p>

        <div style="display:flex;gap:1rem;flex-wrap:wrap;justify-content:center;margin-top:.8rem">
          <button class="btn" id="openContact" aria-haspopup="dialog">Contact Us</button>
          <a class="btn" href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener">Follow on Instagram</a>
        </div>
      </article>
    </section>

    <!-- COMMUNITY -->
    <section id="community" aria-labelledby="community-title">
      <article class="container" role="region">
        <h2 id="community-title" style="color:var(--neon);margin-bottom:.6rem">Connect With Us</h2>
        <div class="cards" role="list">
          <a class="card" href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener" role="listitem">
            <i class="fab fa-instagram" aria-hidden="true"></i>
            <div>Instagram – Share your creativity & updates with our squad.</div>
          </a>

          <a class="card" href="https://t.me/SpotlixHQ" target="_blank" rel="noopener" role="listitem">
            <i class="fab fa-telegram" aria-hidden="true"></i>
            <div>Telegram – Join live discussions and community announcements.</div>
          </a>

          <a class="card" href="https://www.youtube.com/@SpotlixHQ" target="_blank" rel="noopener" role="listitem">
            <i class="fab fa-youtube" aria-hidden="true"></i>
            <div>YouTube – Watch, learn, and grow with our exclusive content.</div>
          </a>

          <a class="card" href="mailto:spotlixhq@gmail.com" role="listitem">
            <i class="fas fa-envelope" aria-hidden="true"></i>
            <div>Email – Reach out directly to connect or collaborate.</div>
          </a>
        </div>
      </article>
    </section>

    <!-- TEAM -->
    <section id="team" aria-labelledby="team-title">
      <article class="container" role="region">
        <h2 id="team-title" style="color:var(--neon);margin-bottom:.6rem">Our Team</h2>
        <div class="team" role="list">
          <div class="member" tabindex="0" role="button" aria-pressed="false" onclick="toggleBio(this)" onkeypress="if(event.key==='Enter'){toggleBio(this)}" aria-label="Suryansh, Founder">
            <strong>Suryansh</strong>
            <div style="font-size:.92rem;opacity:.9">Founder</div>
            <div class="bio">
              Love creativity<br />
              <a href="https://www.instagram.com/suryansh_y09?igsh=MXIzNGhmMGtlZjY4eQ==" target="_blank" rel="noopener">Instagram</a> |
              <a href="mailto:suryanshy302@gmail.com">Email</a>
            </div>
          </div>

          <div class="member" tabindex="0" role="button" aria-pressed="false" onclick="toggleBio(this)" onkeypress="if(event.key==='Enter'){toggleBio(this)}" aria-label="Anup, Team member">
            <strong>Anup</strong>
            <div style="font-size:.92rem;opacity:.9">Team Member</div>
            <div class="bio">
              Not a backup plan — I’m the main character.<br />
              <a href="https://www.instagram.com/anup_.45_45?igsh=cDhuY3plOGVxaXhw" target="_blank" rel="noopener">Instagram</a> |
              <a href="mailto:gurub0357@gmail.com">Email</a>
            </div>
          </div>
        </div>
      </article>
    </section>
  </main>

  <footer role="contentinfo">
    Proudly Indian Made 🌟 | © <span id="year">2025</span> SpotlixHQ. All rights reserved.
  </footer>

  <!-- Scroll to top button -->
  <button class="scroll-top" id="scrollTop" aria-label="Back to top" title="Back to top">
    <i class="fas fa-chevron-up" aria-hidden="true"></i>
  </button>

  <!-- Contact modal -->
  <div class="modal-backdrop" id="modalBackdrop" aria-hidden="true">
    <div class="modal" role="dialog" aria-modal="true" aria-labelledby="contactTitle">
      <h3 id="contactTitle">Contact SpotlixHQ</h3>
      <p>Reach us through any of the links or copy the email below:</p>
      <div style="display:flex;gap:.6rem;align-items:center;flex-wrap:wrap">
        <button class="btn" id="copyEmail" title="Copy email to clipboard">📧 Copy Email</button>
        <a class="btn" href="mailto:spotlixhq@gmail.com">✉️ Open Email</a>
        <a class="btn" target="_blank" rel="noopener" href="https://t.me/SpotlixHQ">💬 Telegram</a>
      </div>
      <div class="copy-success" id="copySuccess" role="status" aria-live="polite">Email copied to clipboard ✓</div>
      <div style="height:10px"></div>
      <div style="display:flex;gap:.5rem;justify-content:flex-end;">
        <button class="btn" id="closeModal">Close</button>
      </div>
    </div>
  </div>

  <script>
    // ---------- small helpers & initial values ----------
    document.getElementById('year').textContent = new Date().getFullYear();

    // ---------- Preloader ----------
    window.addEventListener('load', () => {
      const pre = document.getElementById('preloader');
      if(pre){ pre.classList.add('hidden'); setTimeout(()=>pre.remove(), 700); }
    });

    // ---------- Intersection observer for sections ----------
    const sections = document.querySelectorAll('main section');
    const observer = new IntersectionObserver((entries)=>{
      entries.forEach(entry=>{
        if(entry.isIntersecting) entry.target.classList.add('active');
      });
    }, {threshold:0.18});
    sections.forEach(s => observer.observe(s));

    // ---------- Typing animation ----------
    const phrases = [
      "Creators. Thinkers. Collaborators.",
      "Where Ideas Meet Action.",
      "Grow, Share, Connect.",
      "Made for community-first creators.",
      "Your next idea starts here."
    ];
    let tI = 0, tJ = 0, isDeleting = false;
    const typedEl = document.getElementById('typed');
    function typeLoop(){
      if(!typedEl) return;
      if(tI >= phrases.length) tI = 0;
      const current = phrases[tI];
      if(!isDeleting){
        typedEl.textContent = current.substring(0, tJ + 1);
        tJ++;
        if(tJ === current.length){ isDeleting = true; setTimeout(typeLoop, 1000); return; }
      } else {
        typedEl.textContent = current.substring(0, tJ - 1);
        tJ--;
        if(tJ === 0){ isDeleting = false; tI++; }
      }
      setTimeout(typeLoop, isDeleting ? 50 : 100);
    }
    if(typedEl) typeLoop();

    // ---------- Toggle bio ----------
    function toggleBio(el){
      const bio = el.querySelector('.bio');
      if(!bio) return;
      const expanded = bio.classList.toggle('show-bio');
      el.setAttribute('aria-pressed', expanded ? 'true' : 'false');
    }
    window.toggleBio = toggleBio;

    // ---------- Scroll-to-top logic ----------
    const scrollTopBtn = document.getElementById('scrollTop');
    window.addEventListener('scroll', () => {
      if(window.scrollY > 300) scrollTopBtn.classList.add('show');
      else scrollTopBtn.classList.remove('show');
    });
    scrollTopBtn.addEventListener('click', ()=> window.scrollTo({top:0,behavior:'smooth'}));

    // ---------- Mobile menu ----------
    const hamburger = document.getElementById('hamburger');
    const mobileMenu = document.getElementById('mobileMenu');
    if(hamburger){
      hamburger.addEventListener('click', () => {
        const expanded = hamburger.getAttribute('aria-expanded') === 'true';
        hamburger.setAttribute('aria-expanded', String(!expanded));
        if(!expanded){
          mobileMenu.style.display = 'block';
          mobileMenu.setAttribute('aria-hidden','false');
          // trap focus on first mobile menu link
          const first = mobileMenu.querySelector('a');
          if(first) first.focus();
        } else {
          mobileMenu.style.display = 'none';
          mobileMenu.setAttribute('aria-hidden','true');
        }
      });
    }
    // close mobile menu when clicking a link
    mobileMenu.querySelectorAll('a').forEach(a => a.addEventListener('click', ()=>{
      mobileMenu.style.display = 'none';
      hamburger.setAttribute('aria-expanded','false');
    }));

    // ---------- Contact modal & copy email ----------
    const modalBackdrop = document.getElementById('modalBackdrop');
    const openContact = document.getElementById('openContact');
    const closeModal = document.getElementById('closeModal');
    const copyEmailBtn = document.getElementById('copyEmail');
    const copySuccess = document.getElementById('copySuccess');

    function openModal(){
      modalBackdrop.style.display = 'flex';
      modalBackdrop.setAttribute('aria-hidden','false');
      // focus management
      setTimeout(()=> copyEmailBtn.focus(), 120);
    }
    function closeModalFunc(){
      modalBackdrop.style.display = 'none';
      modalBackdrop.setAttribute('aria-hidden','true');
      if(openContact) openContact.focus();
      copySuccess.style.display = 'none';
    }
    if(openContact) openContact.addEventListener('click', openModal);
    if(closeModal) closeModal.addEventListener('click', closeModalFunc);
    modalBackdrop.addEventListener('click', (e)=>{
      if(e.target === modalBackdrop) closeModalFunc();
    });

    if(copyEmailBtn){
      copyEmailBtn.addEventListener('click', async () => {
        try{
          await navigator.clipboard.writeText('spotlixhq@gmail.com');
          copySuccess.style.display = 'block';
          setTimeout(()=> copySuccess.style.display = 'none', 2400);
        } catch(e){
          copySuccess.textContent = 'Could not copy — please copy manually.';
          copySuccess.style.display = 'block';
          setTimeout(()=> { copySuccess.style.display = 'none'; copySuccess.textContent = 'Email copied to clipboard ✓'; }, 2400);
        }
      });
    }

    // ---------- Language content & RTL support ----------
    const content = {
      en: {
        navHome: "Home", navAbout: "About", navCommunity: "Community", navTeam: "Team",
        aboutTitle: "About SpotlixHQ", aboutDesc: "SpotlixHQ is a community for creators, thinkers, and innovators to collaborate, share ideas, and grow together.",
        communityTitle: "Connect With Us", teamTitle: "Our Team", rtl:false
      },
      hi: {
        navHome: "होम", navAbout: "हमारे बारे में", navCommunity: "समुदाय", navTeam: "टीम",
        aboutTitle: "SpotlixHQ के बारे में", aboutDesc: "SpotlixHQ रचनाकारों, विचारकों और नवप्रवर्तकों के लिए एक समुदाय है जहाँ वे सहयोग कर सकते हैं, विचार साझा कर सकते हैं और साथ में आगे बढ़ सकते हैं।",
        communityTitle: "हमसे जुड़ें", teamTitle: "हमारी टीम", rtl:false
      },
      de: {
        navHome: "Startseite", navAbout: "Über uns", navCommunity: "Community", navTeam: "Team",
        aboutTitle: "Über SpotlixHQ", aboutDesc: "SpotlixHQ ist eine Community für Kreative, Denker und Innovatoren, um zusammenzuarbeiten, Ideen zu teilen und gemeinsam zu wachsen.",
        communityTitle: "Vernetze dich mit uns", teamTitle: "Unser Team", rtl:false
      },
      ja: {
        navHome: "ホーム", navAbout: "概要", navCommunity: "コミュニティ", navTeam: "チーム",
        aboutTitle: "SpotlixHQ について", aboutDesc: "SpotlixHQ は、クリエイターや思考家、イノベーターが協力し、アイデアを共有し、ともに成長するためのコミュニティです。",
        communityTitle: "私たちとつながる", teamTitle: "チーム紹介", rtl:false
      },
      es: {
        navHome: "Inicio", navAbout: "Acerca de", navCommunity: "Comunidad", navTeam: "Equipo",
        aboutTitle: "Acerca de SpotlixHQ", aboutDesc: "SpotlixHQ es una comunidad para creadores, pensadores e innovadores donde pueden colaborar, compartir ideas y crecer juntos.",
        communityTitle: "Conéctate con nosotros", teamTitle: "Nuestro equipo", rtl:false
      },
      fr: {
        navHome: "Accueil", navAbout: "À propos", navCommunity: "Communauté", navTeam: "Équipe",
        aboutTitle: "À propos de SpotlixHQ", aboutDesc: "SpotlixHQ est une communauté pour les créateurs, penseurs et innovateurs afin de collaborer, partager des idées et grandir ensemble.",
        communityTitle: "Connectez-vous avec nous", teamTitle: "Notre équipe", rtl:false
      },
      ar: {
        navHome: "الرئيسية", navAbout: "من نحن", navCommunity: "المجتمع", navTeam: "الفريق",
        aboutTitle: "نبذة عن SpotlixHQ", aboutDesc: "SpotlixHQ هو مجتمع للمبدعين والمفكرين والمبتكرين للتعاون وتبادل الأفكار والنمو معًا.",
        communityTitle: "تواصل معنا", teamTitle: "فريقنا", rtl:true
      },
      id: {
        navHome: "Beranda", navAbout: "Tentang", navCommunity: "Komunitas", navTeam: "Tim",
        aboutTitle: "Tentang SpotlixHQ", aboutDesc: "SpotlixHQ adalah komunitas bagi kreator, pemikir, dan inovator untuk berkolaborasi, berbagi ide, dan tumbuh bersama.",
        communityTitle: "Terhubung dengan kami", teamTitle: "Tim kami", rtl:false
      },
      bn: {
        navHome: "হোম", navAbout: "আমাদের সম্পর্কে", navCommunity: "কমিউনিটি", navTeam: "টিম",
        aboutTitle: "SpotlixHQ সম্পর্কে", aboutDesc: "SpotlixHQ হল সৃষ্টিশীল ব্যক্তি, চিন্তাবিদ এবং উদ্ভাবকদের জন্য একটি কমিউনিটি যেখানে তারা একসাথে কাজ করতে, আইডিয়া শেয়ার করতে এবং একসাথে বেড়ে উঠতে পারে।",
        communityTitle: "আমাদের সাথে যুক্ত হন", teamTitle: "আমাদের দল", rtl:false
      },
      zh: {
        navHome: "首页", navAbout: "关于", navCommunity: "社区", navTeam: "团队",
        aboutTitle: "关于 SpotlixHQ", aboutDesc: "SpotlixHQ 是一个为创作者、思想者和创新者而建立的社区，在这里可以协作、分享想法并共同成长。",
        communityTitle: "与我们联系", teamTitle: "我们的团队", rtl:false
      }
    };

    const langSelect = document.getElementById('language-select');
    const navHome = document.getElementById('nav-home');
    const navAbout = document.getElementById('nav-about');
    const navCommunity = document.getElementById('nav-community');
    const navTeam = document.getElementById('nav-team');
    const aboutTitle = document.getElementById('about-title');
    const aboutDesc = document.getElementById('about-desc');
    const communityTitle = document.getElementById('community-title');
    const teamTitle = document.getElementById('team-title');

    function applyLanguage(lang){
      if(!content[lang]) lang='en';
      const t = content[lang];
      navHome.textContent = t.navHome;
      navAbout.textContent = t.navAbout;
      navCommunity.textContent = t.navCommunity;
      navTeam.textContent = t.navTeam;
      aboutTitle.textContent = t.aboutTitle;
      aboutDesc.textContent = t.aboutDesc;
      communityTitle.textContent = t.communityTitle;
      teamTitle.textContent = t.teamTitle;
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
      applyLanguage(langSelect.value || 'en');
    }

    // ---------- Accessibility: close mobile/modal with Escape ----------
    document.addEventListener('keydown', (e)=>{
      if(e.key === 'Escape'){
        if(mobileMenu.style.display === 'block'){ mobileMenu.style.display = 'none'; hamburger.setAttribute('aria-expanded','false'); }
        if(modalBackdrop.style.display === 'flex') closeModalFunc();
      }
    });

    // ---------- Small progressive enhancement: keyboard nav for nav-links ---------- 
    document.querySelectorAll('.nav-links a').forEach(a=>{
      a.addEventListener('keydown', e=>{
        if(e.key === 'Enter' || e.key === ' ') a.click();
      });
    });

    // ---------- End of script (all original features preserved & enhanced) ----------
  </script>
</body>
</html>
