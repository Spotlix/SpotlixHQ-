<!doctype html>
<html lang="en" dir="ltr">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>SpotlixHQ — Spotlight Squad | Creators, Thinkers, Collaborators</title>

  <!-- Basic SEO -->
  <meta name="description" content="SpotlixHQ (Spotlight Squad) — a premium creator community for collaboration, content and growth. Join on Instagram, Telegram or YouTube." />
  <meta name="keywords" content="SpotlixHQ, Spotlight Squad, creators community, collaboration, Instagram, Telegram, YouTube" />
  <meta name="theme-color" content="#0f0c29" />

  <!-- Open Graph -->
  <meta property="og:title" content="SpotlixHQ — Spotlight Squad" />
  <meta property="og:description" content="SpotlixHQ — a community for creators, thinkers and innovators." />
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://spotlixhq.com/" />
  <meta property="og:image" content="https://spotlixhq.com/og-image.png" />

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
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&family=Playfair+Display:wght@600;700&display=swap" rel="stylesheet">
  <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous" defer></script>

  <!-- Critical CSS (keeps above-the-fold styling minimal for fast FCP) -->
  <style>
    :root{
      --bg-1: #0f0c29;
      --bg-2: #302b63;
      --accent-a: #00fff7;
      --accent-b: #ff00ff;
      --glass: rgba(255,255,255,0.06);
      --glass-2: rgba(255,255,255,0.03);
      --card-bg: rgba(255,255,255,0.03);
      --text-strong: #e9fbff;
      --muted: rgba(233,251,255,0.75);
      --radius: 18px;
      --maxw: 1200px;
      --shadow: 0 10px 40px rgba(0,0,0,.6);
      --transition: 280ms cubic-bezier(.2,.9,.2,1);
      --glass-border: rgba(255,255,255,0.06);
    }

    /* Reset */
    *,*::before,*::after{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family:"Poppins",system-ui,-apple-system,"Segoe UI",Roboto,"Helvetica Neue",Arial;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      color:var(--text-strong);
      background: linear-gradient(135deg,var(--bg-1),var(--bg-2) 40%, #1f1c2c);
      background-attachment: fixed;
    }

    /* Main layout */
    .wrap{max-width:var(--maxw);margin:0 auto;padding:28px;position:relative;min-height:100vh;}
    header{position:sticky;top:14px;z-index:120;display:flex;justify-content:center}
    nav{width:100%;display:flex;align-items:center;gap:12px;justify-content:space-between;padding:.7rem 1rem;border-radius:14px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));backdrop-filter: blur(8px);border:1px solid var(--glass-border);box-shadow:var(--shadow)}
    .brand{display:flex;align-items:center;gap:.6rem;font-weight:700;letter-spacing:.3px}
    .brand svg{width:38px;height:38px;flex-shrink:0}
    .brand span{font-family:"Playfair Display",serif;font-size:1.05rem;color:var(--accent-a)}

    .nav-links{display:flex;gap:.6rem;align-items:center}
    .nav-links a{color:var(--accent-a);text-decoration:none;font-weight:600;padding:.35rem .6rem;border-radius:10px;transition:var(--transition);font-size:.95rem}
    .nav-links a:hover{transform:translateY(-3px);text-shadow:0 6px 20px rgba(0,255,247,.06)}

    .nav-actions{display:flex;gap:.5rem;align-items:center}
    .btn{display:inline-flex;align-items:center;gap:.6rem;padding:.6rem .9rem;border-radius:12px;background:linear-gradient(90deg,var(--accent-a),var(--accent-b));color:#07121a;font-weight:700;border:0;cursor:pointer;box-shadow:0 6px 24px rgba(0,0,0,0.4);transition:transform .25s}
    .btn.ghost{background:transparent;border:1px solid rgba(255,255,255,0.06);color:var(--accent-a)}
    .btn:active{transform:translateY(1px) scale(.998)}

    /* Hero cinematic */
    .hero{
      position:relative;border-radius:20px;overflow:clip;margin-top:18px;min-height:62vh;display:grid;align-items:center;
      grid-template-columns: 1fr; box-shadow: 0 30px 120px rgba(0,0,0,.65);
      border:1px solid rgba(255,255,255,0.03);
    }
    /* video background */
    .hero video{position:absolute;inset:0;width:100%;height:100%;object-fit:cover;z-index:0;filter:contrast(.98) saturate(1.05)}
    .hero .overlay{
      position:absolute;inset:0;background:linear-gradient(180deg, rgba(10,10,15,0.35), rgba(10,10,15,0.55) 65%);z-index:1
    }

    .hero-content{
      position:relative;z-index:2;padding:48px 36px;display:flex;flex-direction:column;gap:18px;max-width:880px;margin-left:clamp(16px,6vw,56px);
    }
    .eyebrow{font-weight:600;color:var(--muted);text-transform:uppercase;letter-spacing:1.6px;font-size:.8rem}
    .hero-title{font-family:"Playfair Display",serif;font-size:clamp(28px,4.6vw,56px);line-height:1.02;margin:0;color:transparent;background:linear-gradient(90deg,var(--accent-a),var(--accent-b));-webkit-background-clip:text;background-clip:text;text-shadow:0 10px 40px rgba(0,0,0,0.6)}
    .hero-lead{font-size:clamp(14px,1.6vw,18px);color:var(--muted);max-width:760px}
    .hero-cta{display:flex;gap:.6rem;align-items:center}
    .hero-stats{display:flex;gap:12px;align-items:center;color:var(--muted);font-weight:600}

    /* Floating cards row */
    .features-row{display:flex;gap:18px;margin-top:30px;flex-wrap:wrap;z-index:2;position:relative;padding-left:16px}
    .card-float{
      min-width:220px;padding:16px;border-radius:14px;background:linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.02));
      border:1px solid rgba(255,255,255,0.04);backdrop-filter:blur(8px);box-shadow:0 10px 40px rgba(0,0,0,0.5);
      transform-style: preserve-3d;transition:transform .45s var(--transition), box-shadow .45s;
    }
    .card-float:hover{transform:translateY(-12px) rotateX(6deg) rotateY(-4deg);box-shadow:0 30px 60px rgba(0,0,0,0.6)}
    .card-float h4{margin:0 0 .4rem;color:var(--text-strong)}
    .card-float p{margin:0;color:var(--muted);font-size:.95rem}

    /* Sections */
    section{padding:72px 0}
    .section-head{display:flex;align-items:center;gap:14px;margin-bottom:18px}
    .section-head h3{margin:0;font-size:1.5rem;color:var(--accent-a)}
    .section-sub{color:var(--muted);margin:0}

    /* Team grid */
    .team-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(160px,1fr));gap:14px;margin-top:18px}
    .team-member{padding:14px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border:1px solid rgba(255,255,255,0.04);text-align:center;transition:transform .35s, box-shadow .35s;cursor:pointer}
    .team-member:hover{transform:translateY(-8px);box-shadow:0 20px 40px rgba(0,0,0,0.55)}
    .team-member img{width:72px;height:72px;border-radius:50%;object-fit:cover;border:2px solid rgba(255,255,255,0.04)}
    .team-member strong{display:block;margin-top:8px}
    .member-role{font-size:.9rem;color:var(--muted)}

    /* Testimonials carousel (simple) */
    .testimonials{display:flex;gap:12px;overflow:hidden}
    .testimonial{min-width:280px;padding:16px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border:1px solid rgba(255,255,255,0.04)}

    /* Roadmap */
    .timeline{display:flex;flex-direction:column;gap:12px;margin-top:12px}
    .timeline-item{display:flex;gap:12px;align-items:flex-start}
    .timeline-dot{width:12px;height:12px;border-radius:50%;background:linear-gradient(90deg,var(--accent-a),var(--accent-b));flex-shrink:0;margin-top:6px}

    /* Floating contact and scroll top */
    .float-actions{position:fixed;right:18px;bottom:18px;display:flex;flex-direction:column;gap:12px;z-index:140}
    .circle-btn{width:56px;height:56px;border-radius:50%;display:flex;align-items:center;justify-content:center;background:linear-gradient(90deg,var(--accent-a),var(--accent-b));border:0;color:#07121a;box-shadow:0 12px 30px rgba(0,0,0,.5);cursor:pointer}

    /* Modal */
    .modal-backdrop{position:fixed;inset:0;background:rgba(0,0,0,0.65);display:none;align-items:center;justify-content:center;z-index:200}
    .modal{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));padding:18px;border-radius:12px;max-width:520px;width:92%;border:1px solid rgba(255,255,255,0.04);backdrop-filter:blur(6px)}

    /* Footer */
    footer{margin-top:60px;padding:28px;border-top:1px solid rgba(255,255,255,0.03);text-align:center;color:var(--muted)}

    /* Responsive */
    @media (max-width:900px){
      .hero-content{padding:34px 20px}
      .features-row{justify-content:center}
      nav{padding:.6rem}
      .nav-links{display:none}
      .hamburger{display:inline-flex}
    }
    @media (max-width:520px){
      .hero{min-height:54vh}
      .hero-content{margin-left:16px;padding:20px}
      .brand span{display:none}
      .card-float{min-width:180px}
    }
  </style>
</head>
<body>
  <div class="wrap" id="pageRoot">
    <!-- Header / Nav -->
    <header aria-label="Primary">
      <nav role="navigation" aria-label="Main navigation">
        <div class="nav-left" style="display:flex;align-items:center;gap:12px">
          <div class="brand" aria-hidden="true">
            <!-- SVG mark (keeps self-contained) -->
            <svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg" role="img" aria-hidden="true">
              <defs>
                <linearGradient id="g1" x1="0" x2="1"><stop offset="0" stop-color="#00fff7"/><stop offset="1" stop-color="#ff00ff"/></linearGradient>
              </defs>
              <circle cx="32" cy="32" r="28" fill="url(#g1)" opacity="0.13"></circle>
              <path d="M20 40c4-7 16-7 20 0" stroke="url(#g1)" stroke-width="3" stroke-linecap="round" fill="none"/>
              <circle cx="32" cy="24" r="6" fill="url(#g1)"/>
            </svg>
            <span>SpotlixHQ</span>
          </div>

          <div class="nav-links" role="menubar" aria-label="Primary links">
            <a href="#home" id="nav-home" role="menuitem">Home</a>
            <a href="#about" id="nav-about" role="menuitem">About</a>
            <a href="#community" id="nav-community" role="menuitem">Community</a>
            <a href="#team" id="nav-team" role="menuitem">Team</a>
            <a href="#roadmap" id="nav-roadmap" role="menuitem">Roadmap</a>
          </div>
        </div>

        <div class="nav-actions" aria-hidden="false">
          <div id="subscriberBadge" style="font-weight:700;color:var(--muted);font-size:.95rem">Subscribers • <span id="subscriberCount">—</span></div>
          <select id="language-select" aria-label="Choose language" title="Choose language" style="background:transparent;border:1px solid rgba(255,255,255,0.04);padding:.3rem;border-radius:8px;color:var(--accent-a)">
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

          <button class="btn" id="joinBtn" aria-haspopup="dialog">Join the Squad</button>
          <button class="hamburger btn ghost" id="mobileToggle" aria-label="Open menu" aria-expanded="false" style="display:none"><i class="fas fa-bars" aria-hidden="true"></i></button>
        </div>
      </nav>
    </header>

    <!-- HERO -->
    <main>
      <section id="home" class="hero" aria-labelledby="homeHeading">
        <!-- Use a looped silent video as cinematic background. Replace 'assets/hero.mp4' with your actual video.
             Video falls back to a gradient + poster for mobile or low bandwidth. -->
        <video id="heroVideo" playsinline muted autoplay loop preload="metadata" poster="assets/hero-poster.jpg" aria-hidden="true">
          <source src="assets/hero.mp4" type="video/mp4">
          <!-- Fallback image if video not supported -->
        </video>
        <div class="overlay" aria-hidden="true"></div>

        <div class="hero-content" role="region" aria-label="Hero">
          <div class="eyebrow" id="homeEyebrow">Spotlight Squad</div>
          <h1 id="homeHeading" class="hero-title">Stop creating alone. Launch with a squad.</h1>
          <p class="hero-lead" id="heroLead">SpotlixHQ is a premium creator community — cinematic collabs, workflow templates, workshop drops, cross-platform boosts. Join members building content that moves people.</p>

          <div class="hero-cta">
            <button class="btn" id="primaryCta">Join the Squad</button>
            <button class="btn ghost" id="watchTour">Watch tour</button>
            <div style="flex:1"></div>

            <div class="hero-stats" aria-hidden="true">
              <span id="liveCountMini">Live • <strong id="liveCount">—</strong></span>
            </div>
          </div>

          <!-- Floating small feature cards -->
          <div class="features-row" aria-hidden="false">
            <div class="card-float" title="Creators support creators">
              <h4>Collab Channels</h4>
              <p>Match with creators in minutes and co-create videos, reels, and podcasts.</p>
            </div>
            <div class="card-float" title="Growth toolkit">
              <h4>Growth Toolkits</h4>
              <p>Templates, briefs and viral-first frameworks used by our top creators.</p>
            </div>
            <div class="card-float" title="Workshops">
              <h4>Weekly Workshops</h4>
              <p>Live training from creators + guest pros — design, editing, monetization.</p>
            </div>
          </div>
        </div>
      </section>

      <!-- ABOUT -->
      <section id="about" aria-labelledby="about-title">
        <article class="container">
          <div class="section-head">
            <h3 id="about-title">About SpotlixHQ</h3>
            <p class="section-sub">A cinematic creator hub where ideas become projects and projects become careers.</p>
          </div>

          <div style="display:grid;grid-template-columns:1fr 320px;gap:22px;align-items:start">
            <div>
              <p id="about-desc" style="color:var(--muted)">SpotlixHQ (Spotlight Squad) brings creators together across Instagram, Telegram and YouTube to collaborate, test new formats, and amplify real work. We focus on creative alignment, simple onboarding, and tangible cross-promotion — so your next idea finds an audience fast.</p>

              <div style="margin-top:18px;display:flex;gap:12px;flex-wrap:wrap">
                <button class="btn" id="openContact">Contact</button>
                <a class="btn ghost" href="https://t.me/SpotlixHQ" target="_blank" rel="noopener">Join Telegram</a>
              </div>
            </div>

            <aside style="padding:16px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border:1px solid rgba(255,255,255,0.04);">
              <h4 style="margin:0 0 .6rem;color:var(--accent-a)">Brand Vision</h4>
              <p style="margin:0;color:var(--muted)">Create, collaborate and launch with a squad that ships. We help creators go from idea → audience → revenue, together.</p>
            </aside>
          </div>
        </article>
      </section>

      <!-- COMMUNITY -->
      <section id="community" aria-labelledby="community-title">
        <article class="container">
          <div class="section-head">
            <h3 id="community-title">Connect With Us</h3>
            <p class="section-sub">Pick your platform — we'll meet you there.</p>
          </div>

          <div class="cards" style="display:flex;gap:12px;flex-wrap:wrap">
            <a class="card-float" href="https://www.instagram.com/spotlixhq?igsh=anVtYmNqcGZ5aGFo" target="_blank" rel="noopener">
              <h4>Instagram</h4>
              <p>Share reels & collaborations — we repost standout work.</p>
            </a>
            <a class="card-float" href="https://t.me/SpotlixHQ" target="_blank" rel="noopener">
              <h4>Telegram</h4>
              <p>Announcements, collab pings and rapid feedback loops.</p>
            </a>
            <a class="card-float" href="https://www.youtube.com/@SpotlixHQ" target="_blank" rel="noopener">
              <h4>YouTube</h4>
              <p>Workshops, case studies and long-form creator journeys.</p>
            </a>
            <a class="card-float" href="mailto:spotlixhq@gmail.com">
              <h4>Email</h4>
              <p>spotlixhq@gmail.com — business & creator partnerships.</p>
            </a>
          </div>
        </article>
      </section>

      <!-- TEAM -->
      <section id="team" aria-labelledby="team-title">
        <article class="container">
          <div class="section-head">
            <h3 id="team-title">Our Team</h3>
            <p class="section-sub">Founders, curators and community leads powering the squad.</p>
          </div>

          <div class="team-grid" role="list">
            <!-- Suryansh -->
            <div class="team-member" role="listitem" tabindex="0" onclick="toggleBio(this)">
              <img src="assets/suryansh.jpg" alt="Suryansh — Founder (avatar)" onerror="this.style.opacity=.6" />
              <strong>Suryansh</strong>
              <div class="member-role">Founder</div>
              <div class="bio" hidden>
                Love creativity<br />
                <a href="https://www.instagram.com/suryansh_y09?igsh=MXIzNGhmMGtlZjY4eQ==" target="_blank" rel="noopener">Instagram</a> |
                <a href="mailto:suryanshy302@gmail.com">suryanshy302@gmail.com</a>
              </div>
            </div>

            <!-- Anup -->
            <div class="team-member" role="listitem" tabindex="0" onclick="toggleBio(this)">
              <img src="assets/anup.jpg" alt="Anup — Team member" onerror="this.style.opacity=.6" />
              <strong>Anup</strong>
              <div class="member-role">Team Member</div>
              <div class="bio" hidden>
                Not a backup plan — I'm the main character.<br />
                <a href="https://www.instagram.com/anup_.45_45?igsh=cDhuY3plOGVxaXhw" target="_blank" rel="noopener">Instagram</a> |
                <a href="mailto:gurub0357@gmail.com">gurub0357@gmail.com</a>
              </div>
            </div>

            <!-- Adhayayan (new) -->
            <div class="team-member" role="listitem" tabindex="0" onclick="toggleBio(this)">
              <img src="assets/adhayayan.jpg" alt="Adhayayan — Team member" onerror="this.style.opacity=.6" />
              <strong>Adhayayan</strong>
              <div class="member-role">Community</div>
              <div class="bio" hidden>
                good over bad<br />
                <a href="https://www.instagram.com/adhyayann_08?igsh=MW5xaWlmcWt5Y2tmcQ==" target="_blank" rel="noopener">Instagram</a> |
                <a href="mailto:hindiaianimate@gmail.com">hindiaianimate@gmail.com</a>
              </div>
            </div>

            <!-- placeholder for more members -->
          </div>
        </article>
      </section>

      <!-- TESTIMONIALS -->
      <section id="testimonials" aria-labelledby="test-title">
        <article class="container">
          <div class="section-head">
            <h3 id="test-title">Testimonials</h3>
            <p class="section-sub">What creators say after joining</p>
          </div>

          <div class="testimonials" id="testimonialsRow" aria-live="polite">
            <div class="testimonial">
              <strong>Riya • Filmmaker</strong>
              <p style="color:var(--muted);margin-top:8px">"I found 3 collab partners in a week. Our joint reel hit 200k views."</p>
            </div>
            <div class="testimonial">
              <strong>Arjun • Podcaster</strong>
              <p style="color:var(--muted);margin-top:8px">"Workshops helped me get sponsorship-ready creative decks."</p>
            </div>
            <div class="testimonial">
              <strong>Meera • Editor</strong>
              <p style="color:var(--muted);margin-top:8px">"The growth toolkits are gold — saves me hours per edit."</p>
            </div>
          </div>
        </article>
      </section>

      <!-- ROADMAP -->
      <section id="roadmap" aria-labelledby="roadmap-title">
        <article class="container">
          <div class="section-head">
            <h3 id="roadmap-title">Roadmap</h3>
            <p class="section-sub">Where we're heading</p>
          </div>

          <div class="timeline" role="list">
            <div class="timeline-item">
              <div class="timeline-dot" aria-hidden="true"></div>
              <div>
                <strong>Q1 — Creator Bootcamps</strong>
                <p style="margin:6px 0;color:var(--muted)">Small cohorts with hands-on briefs and guest mentors.</p>
              </div>
            </div>
            <div class="timeline-item">
              <div class="timeline-dot" aria-hidden="true"></div>
              <div>
                <strong>Q2 — Creator Marketplace</strong>
                <p style="margin:6px 0;color:var(--muted)">Connect brands and micro-creators with simplified contracts.</p>
              </div>
            </div>
            <div class="timeline-item">
              <div class="timeline-dot" aria-hidden="true"></div>
              <div>
                <strong>Q3 — Creator Residency</strong>
                <p style="margin:6px 0;color:var(--muted)">Local meetups, funded projects, and showcase events.</p>
              </div>
            </div>
          </div>
        </article>
      </section>
    </main>

    <!-- Footer -->
    <footer>
      <div style="display:flex;flex-direction:column;gap:8px;align-items:center">
        <div>Proudly Indian Made 🌟</div>
        <div style="color:var(--muted)">© <span id="year">2025</span> SpotlixHQ — All rights reserved</div>
        <div style="margin-top:8px;color:var(--muted)">Email: <a href="mailto:spotlixhq@gmail.com" style="color:var(--accent-a)">spotlixhq@gmail.com</a></div>
      </div>
    </footer>

    <!-- Floating actions -->
    <div class="float-actions" aria-hidden="false">
      <button class="circle-btn" id="contactFloat" aria-label="Contact SpotlixHQ"><i class="fas fa-envelope" aria-hidden="true"></i></button>
      <button class="circle-btn" id="scrollTopBtn" aria-label="Scroll to top"><i class="fas fa-arrow-up" aria-hidden="true"></i></button>
    </div>

    <!-- Modal: Join / Contact -->
    <div class="modal-backdrop" id="modalBackdrop" aria-hidden="true">
      <div class="modal" role="dialog" aria-modal="true" aria-labelledby="contactTitle">
        <h3 id="contactTitle">Join the Squad</h3>
        <p style="color:var(--muted)">Tell us where you're most active — we'll guide you to the best place to start.</p>

        <form id="joinForm" style="display:grid;gap:10px;margin-top:8px">
          <label>
            <span style="color:var(--muted);font-weight:600">Name</span>
            <input name="name" type="text" required placeholder="Your name" style="width:100%;padding:.6rem;border-radius:8px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:var(--text-strong)">
          </label>

          <label>
            <span style="color:var(--muted);font-weight:600">Email</span>
            <input name="email" type="email" required placeholder="you@domain.com" style="width:100%;padding:.6rem;border-radius:8px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:var(--text-strong)">
          </label>

          <label>
            <span style="color:var(--muted);font-weight:600">Preferred platform</span>
            <select name="platform" style="width:100%;padding:.6rem;border-radius:8px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:var(--text-strong)">
              <option value="telegram">Telegram</option>
              <option value="instagram">Instagram</option>
              <option value="youtube">YouTube</option>
            </select>
          </label>

          <div style="display:flex;gap:8px;justify-content:flex-end">
            <button type="button" class="btn ghost" id="closeModal">Cancel</button>
            <button type="submit" class="btn">Request Invite</button>
          </div>

          <div id="formStatus" aria-live="polite" style="color:var(--muted);font-size:.95rem;display:none"></div>
        </form>
      </div>
    </div>
  </div>

  <!-- Minimal JS — performance-minded -->
  <script>
    // Keep initial DOM operations lightweight.
    (function(){
      // small helpers
      const $ = (sel, ctx=document) => ctx.querySelector(sel);
      const $$ = (sel, ctx=document) => Array.from(ctx.querySelectorAll(sel));

      // set year
      document.getElementById('year').textContent = new Date().getFullYear();

      // subscriber & live counters (simulated)
      const subscriberCountEl = $('#subscriberCount');
      const liveCountEl = $('#liveCount');

      // Simulate fetching subscriber count (replace with real API later)
      function formatNum(n){
        if(n>=1e6) return (n/1e6).toFixed(2)+'M';
        if(n>=1e3) return (n/1e3).toFixed(1)+'k';
        return String(n);
      }
      // simulate initial fetch
      let subs = 42100;
      let live = 12;
      function tickCounts(){
        // gentle random walk
        subs += Math.floor(Math.random()*3);
        live = Math.max(2, Math.min(300, live + Math.floor(Math.random()*3)-1));
        if(subscriberCountEl) subscriberCountEl.textContent = formatNum(subs);
        if(liveCountEl) liveCountEl.textContent = live;
        if($('#liveCountMini')) $('#liveCountMini').querySelector('#liveCount')?.textContent = live;
      }
      tickCounts();
      // run every 4s in background
      setInterval(tickCounts, 4000);

      // Hero video: pause on mobile for perf, autoplay otherwise
      const heroVideo = $('#heroVideo');
      function adaptVideo(){
        const isMobile = /Mobi|Android/i.test(navigator.userAgent);
        if(!heroVideo) return;
        if(isMobile || window.innerWidth < 700){
          heroVideo.pause();
          heroVideo.style.display = 'none';
        } else {
          heroVideo.style.display = 'block';
          heroVideo.play().catch(()=>{/* autoplay blocked */});
        }
      }
      adaptVideo();
      window.addEventListener('resize', () => { clearTimeout(window._resizeT); window._resizeT = setTimeout(adaptVideo,220); });

      // Intersection Observer small enhancement: reveal sections
      const io = new IntersectionObserver((entries)=>{
        entries.forEach(e=>{
          if(e.isIntersecting) e.target.classList.add('active');
        });
      }, {threshold:0.14});
      document.querySelectorAll('main section').forEach(s => io.observe(s));

      // Toggle team bios
      window.toggleBio = function(el){
        const bio = el.querySelector('.bio');
        if(!bio) return;
        const shown = !(bio.hidden);
        bio.hidden = shown;
        el.setAttribute('aria-pressed', String(!shown));
      };

      // Floating actions
      $('#scrollTopBtn').addEventListener('click', ()=> window.scrollTo({top:0,behavior:'smooth'}));
      $('#contactFloat').addEventListener('click', ()=> openModal());

      // Modal open/close & form submit (progressive)
      const modal = $('#modalBackdrop');
      const openButtons = Array.from(document.querySelectorAll('#openContact, #primaryCta, #joinBtn'));
      openButtons.forEach(b=>b && b.addEventListener('click', openModal));
      $('#closeModal').addEventListener('click', closeModalFunc);

      function openModal(){
        modal.style.display = 'flex';
        modal.setAttribute('aria-hidden','false');
        // focus first input
        setTimeout(()=> modal.querySelector('input')?.focus(), 120);
      }
      function closeModalFunc(){
        modal.style.display = 'none';
        modal.setAttribute('aria-hidden','true');
      }

      // Form submit (fake)
      $('#joinForm').addEventListener('submit', function(e){
        e.preventDefault();
        const status = $('#formStatus');
        status.style.display = 'block';
        status.textContent = 'Sending request…';
        // simulate network
        setTimeout(()=>{
          status.textContent = 'Thanks — we sent you the invite steps to your email (simulated).';
        }, 900);
      });

      // Mobile toggle behavior
      const mobileToggle = $('#mobileToggle');
      const navLinks = document.querySelector('.nav-links');
      function showMobileMenu(){
        const expanded = mobileToggle.getAttribute('aria-expanded') === 'true';
        mobileToggle.setAttribute('aria-expanded', String(!expanded));
        if(!expanded){
          // show menu as overlay
          const menu = document.createElement('div');
          menu.className = 'mobile-overlay';
          menu.style.position = 'fixed';
          menu.style.inset = '72px 12px auto 12px';
          menu.style.background = 'linear-gradient(180deg, rgba(0,0,0,0.7), rgba(0,0,0,0.5))';
          menu.style.backdropFilter = 'blur(8px)';
          menu.style.padding = '12px';
          menu.style.borderRadius = '12px';
          menu.style.zIndex = 999;
          menu.innerHTML = navLinks.innerHTML + '<div style="height:8px"></div><a href="https://t.me/SpotlixHQ" target="_blank">Telegram</a>';
          document.body.appendChild(menu);
          mobileToggle._menu = menu;
          menu.addEventListener('click', (ev)=> {
            if(ev.target.tagName === 'A') {
              // close after click
              menu.remove();
              mobileToggle.setAttribute('aria-expanded','false');
            }
          });
        } else {
          if(mobileToggle._menu) mobileToggle._menu.remove();
        }
      }
      if(mobileToggle) mobileToggle.addEventListener('click', showMobileMenu);

      // keyboard accessibility: close modal/mobile menu with Escape
      document.addEventListener('keydown', (e)=>{
        if(e.key === 'Escape'){
          if(modal.style.display === 'flex') closeModalFunc();
          if(mobileToggle && mobileToggle.getAttribute('aria-expanded') === 'true') {
            mobileToggle._menu?.remove();
            mobileToggle.setAttribute('aria-expanded','false');
          }
        }
      });

      // Language translations (same texts as your previous content)
      const content = {
        en: {
          navHome: "Home", navAbout: "About", navCommunity: "Community", navTeam: "Team",
          aboutTitle: "About SpotlixHQ",
          aboutDesc: "SpotlixHQ is a community for creators, thinkers, and innovators to collaborate, share ideas, and grow together.",
          communityTitle: "Connect With Us", teamTitle: "Our Team", rtl:false
        },
        hi: {
          navHome: "होम", navAbout: "हमारे बारे में", navCommunity: "समुदाय", navTeam: "टीम",
          aboutTitle: "SpotlixHQ के बारे में",
          aboutDesc: "SpotlixHQ रचनाकारों, विचारकों और नवप्रवर्तकों के लिए एक समुदाय है जहाँ वे सहयोग कर सकते हैं, विचार साझा कर सकते हैं और साथ में आगे बढ़ सकते हैं।",
          communityTitle: "हमसे जुड़ें", teamTitle: "हमारी टीम", rtl:false
        },
        de: {
          navHome: "Startseite", navAbout: "Über uns", navCommunity: "Community", navTeam: "Team",
          aboutTitle: "Über SpotlixHQ",
          aboutDesc: "SpotlixHQ ist eine Community für Kreative, Denker und Innovatoren, um zusammenzuarbeiten, Ideen zu teilen und gemeinsam zu wachsen.",
          communityTitle: "Vernetze dich mit uns", teamTitle: "Unser Team", rtl:false
        },
        ja: {
          navHome: "ホーム", navAbout: "概要", navCommunity: "コミュニティ", navTeam: "チーム",
          aboutTitle: "SpotlixHQ について",
          aboutDesc: "SpotlixHQ は、クリエイターや思考家、イノベーターが協力し、アイデアを共有し、ともに成長するためのコミュニティです。",
          communityTitle: "私たちとつながる", teamTitle: "チーム紹介", rtl:false
        },
        es: {
          navHome: "Inicio", navAbout: "Acerca de", navCommunity: "Comunidad", navTeam: "Equipo",
          aboutTitle: "Acerca de SpotlixHQ",
          aboutDesc: "SpotlixHQ es una comunidad para creadores, pensadores e innovadores donde pueden colaborar, compartir ideas y crecer juntos.",
          communityTitle: "Conéctate con nosotros", teamTitle: "Nuestro equipo", rtl:false
        },
        fr: {
          navHome: "Accueil", navAbout: "À propos", navCommunity: "Communauté", navTeam: "Équipe",
          aboutTitle: "À propos de SpotlixHQ",
          aboutDesc: "SpotlixHQ est une communauté pour les créateurs, penseurs et innovateurs afin de collaborer, partager des idées et grandir ensemble.",
          communityTitle: "Connectez-vous avec nous", teamTitle: "Notre équipe", rtl:false
        },
        ar: {
          navHome: "الرئيسية", navAbout: "من نحن", navCommunity: "المجتمع", navTeam: "الفريق",
          aboutTitle: "نبذة عن SpotlixHQ",
          aboutDesc: "SpotlixHQ هو مجتمع للمبدعين والمفكرين والمبتكرين للتعاون وتبادل الأفكار والنمو معًا.",
          communityTitle: "تواصل معنا", teamTitle: "فريقنا", rtl:true
        },
        id: {
          navHome: "Beranda", navAbout: "Tentang", navCommunity: "Komunitas", navTeam: "Tim",
          aboutTitle: "Tentang SpotlixHQ",
          aboutDesc: "SpotlixHQ adalah komunitas bagi kreator, pemikir, dan inovator untuk berkolaborasi, berbagi ide, dan tumbuh bersama.",
          communityTitle: "Terhubung dengan kami", teamTitle: "Tim kami", rtl:false
        },
        bn: {
          navHome: "হোম", navAbout: "আমাদের সম্পর্কে", navCommunity: "কমিউনিটি", navTeam: "টিম",
          aboutTitle: "SpotlixHQ সম্পর্কে",
          aboutDesc: "SpotlixHQ হল সৃষ্টিশীল ব্যক্তি, চিন্তাবিদ এবং উদ্ভাবকদের জন্য একটি কমিউনিটি যেখানে তারা একসাথে কাজ করতে, আইডিয়া শেয়ার করতে এবং একসাথে বেড়ে উঠতে পারে।",
          communityTitle: "আমাদের সাথে যুক্ত হন", teamTitle: "আমাদের দল", rtl:false
        },
        zh: {
          navHome: "首页", navAbout: "关于", navCommunity: "社区", navTeam: "团队",
          aboutTitle: "关于 SpotlixHQ",
          aboutDesc: "SpotlixHQ 是一个为创作者、思想者和创新者而建立的社区，在这里可以协作、分享想法并共同成长。",
          communityTitle: "与我们联系", teamTitle: "我们的团队", rtl:false
        }
      };

      // Apply language
      const langSelect = $('#language-select');
      function applyLanguage(lang){
        if(!content[lang]) lang='en';
        const t = content[lang];
        $('#nav-home').textContent = t.navHome;
        $('#nav-about').textContent = t.navAbout;
        $('#nav-community').textContent = t.navCommunity;
        $('#nav-team').textContent = t.navTeam;
        $('#about-title').textContent = t.aboutTitle;
        $('#about-desc').textContent = t.aboutDesc;
        $('#community-title').textContent = t.communityTitle;
        $('#team-title').textContent = t.teamTitle;
        document.documentElement.lang = lang;
        document.documentElement.dir = t.rtl ? 'rtl' : 'ltr';
      }
      if(langSelect){
        langSelect.addEventListener('change', ()=> applyLanguage(langSelect.value));
        applyLanguage(langSelect.value || 'en');
      }

      // small performance: defer non-critical visual effects until idle
      window.addEventListener('load', ()=>{
        if('requestIdleCallback' in window){
          requestIdleCallback(initNonCritical, {timeout:1200});
        } else {
          setTimeout(initNonCritical, 600);
        }
      });

      function initNonCritical(){
        // subtle parallax on mouse move (spotlight)
        document.addEventListener('mousemove', (e)=>{
          const rx = (e.clientX / window.innerWidth) - 0.5;
          const ry = (e.clientY / window.innerHeight) - 0.5;
          // tilt some hero cards
          $$('.card-float').forEach((el,i)=>{
            el.style.transform = `translateY(${ -6 - (ry*6) }px) rotateX(${(ry*6).toFixed(2)}deg) rotateY(${(rx*6).toFixed(2)}deg)`;
          });
        });

        // basic carousel auto-scroll for testimonials
        const tRow = $('#testimonialsRow');
        if(tRow){
          let offset = 0;
          setInterval(()=>{
            offset = (offset + 1) % Math.max(1, tRow.children.length);
            tRow.style.transform = `translateX(-${offset*300}px)`;
            tRow.style.transition = 'transform 600ms ease';
          }, 4200);
        }
      }

      // accessibility helpers: keyboard nav on nav links
      $$('.nav-links a').forEach(a => a.addEventListener('keydown', (e) => {
        if(e.key === 'Enter' || e.key === ' ') { e.preventDefault(); a.click(); }
      }));

      // graceful fallback: if JS disabled, hide video (already fine)

      // End of IIFE
    })();
  </script>

  <!-- End body -->
</body>
</html>
