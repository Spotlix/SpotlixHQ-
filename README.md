
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SpotlixHQ | The Elite Creator Ecosystem</title>
    <meta name="description" content="SpotlixHQ: The network for creators scaling from 1K to 100K. Join the squad for editors, strategy, and leverage.">
    <meta name="theme-color" content="#000000">

    <!-- FONTS -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700;900&family=Rajdhani:wght@400;500;600;700&display=swap" rel="stylesheet">
    
    <!-- ICONS -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        :root {
            --bg: #030303;
            --text-main: #ffffff;
            --neon-blue: #00F3FF;
            --neon-purple: #BC13FE;
            --neon-red: #FF2A2A;
            --border: rgba(0, 243, 255, 0.2);
            --font-hud: 'Orbitron', sans-serif;
            --font-body: 'Rajdhani', sans-serif;
        }

        /* --- 1. CORE & RESET --- */
        *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; -webkit-tap-highlight-color: transparent; }
        
        html { scroll-behavior: smooth; }
        
        body {
            background: var(--bg); color: var(--text-main); font-family: var(--font-body);
            overflow-x: hidden; width: 100%; min-height: 100vh;
            line-height: 1.6; -webkit-font-smoothing: antialiased;
        }

        a, button { cursor: pointer; pointer-events: auto !important; position: relative; z-index: 50; }
        a:focus-visible, button:focus-visible { outline: 2px solid var(--neon-blue); outline-offset: 4px; }

        /* Skip Link */
        .skip-link {
            position: absolute; top: -40px; left: 0; background: var(--neon-blue); color: #000;
            padding: 8px; z-index: 1000; font-weight: bold; transition: top 0.3s;
        }
        .skip-link:focus { top: 0; }

        /* --- 2. BACKGROUND LAYERS --- */
        #webgl-canvas {
            position: fixed; top: 0; left: 0; width: 100%; height: 100vh;
            z-index: 0; pointer-events: none; opacity: 0; transition: opacity 1s;
        }
        #webgl-canvas.active { opacity: 1; }

        .overlay-vignette {
            position: fixed; inset: 0; z-index: 1; pointer-events: none;
            background: radial-gradient(circle at center, transparent 0%, #000 120%);
        }

        /* --- 3. UI COMPONENTS --- */
        
        /* Header */
        .site-header {
            position: fixed; top: 0; width: 100%; height: 80px; z-index: 100;
            display: flex; justify-content: space-between; align-items: center; padding: 0 5%;
            background: rgba(0,0,0,0.9); backdrop-filter: blur(10px);
            border-bottom: 1px solid var(--border);
        }
        
        .logo {
            font-family: var(--font-hud); font-size: 1.5rem; font-weight: 800; letter-spacing: 1px;
            display: flex; align-items: center; gap: 10px; color: white; text-decoration: none;
        }
        .logo span { color: var(--neon-blue); }

        .header-controls { display: flex; align-items: center; gap: 20px; }

        .fx-toggle {
            background: transparent; border: 1px solid var(--border); color: #888;
            font-family: var(--font-hud); font-size: 0.7rem; padding: 5px 10px;
            cursor: pointer; text-transform: uppercase; transition: 0.3s;
        }
        .fx-toggle.active { color: var(--neon-blue); border-color: var(--neon-blue); box-shadow: 0 0 10px rgba(0,243,255,0.2); }

        /* Buttons */
        .cta-btn {
            padding: 0.8rem 1.5rem; background: rgba(0, 243, 255, 0.1);
            border: 1px solid var(--neon-blue); color: var(--neon-blue);
            font-family: var(--font-hud); font-size: 0.8rem; font-weight: 700;
            text-transform: uppercase; text-decoration: none; transition: 0.3s;
            clip-path: polygon(10px 0, 100% 0, 100% calc(100% - 10px), calc(100% - 10px) 100%, 0 100%, 0 10px);
            display: inline-flex; align-items: center; gap: 10px; justify-content: center;
        }
        .cta-btn:hover { background: var(--neon-blue); color: black; box-shadow: 0 0 30px var(--neon-blue); }

        /* New Social Mini Buttons */
        .social-row {
            display: flex; gap: 1rem; align-items: center; margin-top: 1.5rem;
        }
        .social-mini {
            width: 45px; height: 45px; border: 1px solid var(--border);
            display: flex; align-items: center; justify-content: center;
            color: #aaa; background: rgba(255,255,255,0.03); text-decoration: none;
            transition: 0.3s; clip-path: polygon(20% 0, 100% 0, 100% 80%, 80% 100%, 0 100%, 0 20%);
        }
        .social-mini:hover { color: var(--neon-blue); border-color: var(--neon-blue); background: rgba(0,243,255,0.1); transform: translateY(-3px); }
        .social-label {
            font-family: var(--font-hud); font-size: 0.7rem; color: #666; text-transform: uppercase; letter-spacing: 1px;
        }

        /* --- 4. SECTIONS --- */
        section {
            padding: 6rem 5%; min-height: 100vh; display: flex; flex-direction: column; justify-content: center;
            border-bottom: 1px solid rgba(255,255,255,0.05); position: relative; z-index: 5;
        }

        h1 {
            font-family: var(--font-hud); font-size: clamp(2.5rem, 7vw, 6rem);
            font-weight: 900; line-height: 1.1; text-transform: uppercase; margin-bottom: 1.5rem;
        }
        h2 { font-family: var(--font-hud); font-size: clamp(2rem, 5vw, 4rem); margin-bottom: 2rem; }
        
        .hero-sub {
            font-size: 1.2rem; color: #ccc; max-width: 650px; margin-bottom: 2.5rem;
            border-left: 3px solid var(--neon-blue); padding-left: 1.5rem;
        }

        .social-proof {
            display: flex; align-items: center; gap: 10px; margin-bottom: 1rem;
            font-family: var(--font-hud); font-size: 0.8rem; color: var(--neon-blue);
        }
        .proof-dot { width: 8px; height: 8px; background: var(--neon-blue); border-radius: 50%; box-shadow: 0 0 10px var(--neon-blue); }

        /* Features */
        .features-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; }
        .feature-card {
            background: rgba(10, 20, 30, 0.6); border: 1px solid var(--border); padding: 2.5rem;
            backdrop-filter: blur(5px);
        }
        .benefit-list { list-style: none; margin-top: 1rem; }
        .benefit-list li { margin-bottom: 0.8rem; padding-left: 1.5rem; position: relative; color: #aaa; }
        .benefit-list li::before { content: '>'; position: absolute; left: 0; color: var(--neon-blue); font-weight: bold; }

        /* Team */
        .team-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 3rem; margin-top: 2rem; }
        .profile-card {
            background: rgba(10, 15, 20, 0.8); border: 1px solid var(--border);
            display: flex; flex-direction: column; overflow: hidden;
        }
        .profile-img-box { height: 350px; overflow: hidden; width: 100%; border-bottom: 1px solid var(--border); }
        .profile-img { width: 100%; height: 100%; object-fit: cover; transition: 0.5s; filter: grayscale(100%); }
        .profile-card:hover .profile-img { filter: grayscale(0%); transform: scale(1.05); }
        
        .profile-info { padding: 1.5rem; flex: 1; display: flex; flex-direction: column; }
        .role-tag { font-size: 0.75rem; color: var(--neon-blue); letter-spacing: 1px; font-weight: 700; text-transform: uppercase; display: block; margin-bottom: 0.5rem; }
        .profile-name { font-family: var(--font-hud); font-size: 1.8rem; margin-bottom: 1rem; text-transform: uppercase; }
        .profile-bio { font-size: 0.95rem; color: #ccc; margin-bottom: 1.5rem; }

        .comms-row { margin-top: auto; display: flex; gap: 10px; border-top: 1px solid rgba(255,255,255,0.1); padding-top: 1rem; }
        .comm-link {
            flex: 1; padding: 0.5rem; border: 1px solid rgba(255,255,255,0.2);
            text-align: center; color: white; text-decoration: none; font-size: 0.8rem;
            text-transform: uppercase; display: flex; justify-content: center; align-items: center; gap: 8px;
            transition: 0.2s;
        }
        .comm-link:hover { background: var(--neon-blue); color: black; border-color: var(--neon-blue); }

        /* Footer */
        .site-footer {
            padding: 6rem 5%; text-align: center; background: black; border-top: 1px solid var(--border);
            position: relative; z-index: 10;
        }
        .footer-nav { display: flex; justify-content: center; gap: 2rem; margin: 3rem 0; flex-wrap: wrap; }
        .footer-nav a { color: #aaa; text-decoration: none; font-size: 0.9rem; transition:0.3s; }
        .footer-nav a:hover { color: var(--neon-blue); }

        /* Desktop Cursor */
        #cursor-dot {
            position: fixed; top: 0; left: 0; width: 8px; height: 8px; background: var(--neon-blue);
            border-radius: 50%; pointer-events: none; z-index: 9999; transform: translate(-50%, -50%);
            display: none;
        }
        
        /* Preloader */
        #boot-screen {
            position: fixed; inset: 0; background: black; z-index: 99999;
            display: flex; flex-direction: column; justify-content: center; align-items: center;
        }
        .loader-text { font-family: var(--font-hud); letter-spacing: 0.2em; color: var(--neon-blue); margin-bottom: 1rem; }
        .loader-bar { width: 150px; height: 2px; background: #333; overflow: hidden; }
        .loader-fill { width: 0%; height: 100%; background: var(--neon-blue); transition: width 0.1s; }

        @media (max-width: 768px) {
            .hero-btns { flex-direction: column; }
            .cta-btn { width: 100%; }
            .social-row { flex-wrap: wrap; }
        }

    </style>
</head>
<body>

    <a href="#main-content" class="skip-link">Skip to main content</a>

    <!-- PRELOADER -->
    <div id="boot-screen" aria-hidden="false">
        <div class="loader-text">INITIALIZING SYSTEM...</div>
        <div class="loader-bar"><div class="loader-fill"></div></div>
    </div>

    <!-- BACKGROUND -->
    <canvas id="webgl-canvas" aria-hidden="true"></canvas>
    <div class="overlay-vignette"></div>

    <!-- CURSOR -->
    <div id="cursor-dot"></div>

    <!-- HEADER -->
    <header class="site-header">
        <a href="#" class="logo" aria-label="SpotlixHQ Home">
            <span>SPOTLIX</span>HQ
        </a>
        
        <div class="header-controls">
            <button id="fx-toggle" class="fx-toggle active" aria-pressed="true" aria-label="Toggle Special Effects">
                FX: ON
            </button>
            <a href="https://t.me/SpotlixHQ" target="_blank" class="cta-btn">Join Telegram</a>
        </div>
    </header>

    <!-- MAIN CONTENT -->
    <main id="main-content">

        <!-- HERO -->
        <section aria-labelledby="hero-title">
            <div class="social-proof">
                <div class="proof-dot"></div>
                <span>27,000+ Creators Active Now</span>
            </div>
            
            <h1 id="hero-title">
                SCALE YOUR CHANNEL<br>
                <span style="color:var(--neon-blue)">FROM 1K TO 100K</span>
            </h1>
            
            <p class="hero-sub">
                Stop editing alone. SpotlixHQ provides the network, the blueprints, and the distribution leverage you need to go full-time.
            </p>

            <div class="hero-btns" style="display: flex; gap: 1rem; flex-wrap: wrap;">
                <a href="https://t.me/SpotlixHQ" target="_blank" class="cta-btn" style="font-size: 1rem; padding: 1rem 2.5rem;">
                    <i class="fa-brands fa-telegram"></i> Join the Creator Squad
                </a>
                <a href="#features" class="cta-btn" style="background: transparent; color: white; border-color: white;">
                    Explore System
                </a>
            </div>

            <!-- NEW: HERO SOCIAL CONNECTIVITY -->
            <div class="social-row">
                <span class="social-label">Uplink:</span>
                <a href="mailto:spotlixhq@gmail.com" class="social-mini" title="Email SpotlixHQ" aria-label="Email SpotlixHQ">
                    <i class="fa-solid fa-envelope"></i>
                </a>
                <a href="https://www.instagram.com/spotlixhq" target="_blank" class="social-mini" title="Instagram" aria-label="SpotlixHQ Instagram">
                    <i class="fa-brands fa-instagram"></i>
                </a>
                <a href="https://www.youtube.com/@SpotlixHQ" target="_blank" class="social-mini" title="YouTube" aria-label="SpotlixHQ YouTube">
                    <i class="fa-brands fa-youtube"></i>
                </a>
            </div>
        </section>

        <!-- FEATURES / BENEFITS -->
        <section id="features" aria-labelledby="features-title">
            <h2 id="features-title">SYSTEM CAPABILITIES</h2>
            
            <div class="features-grid">
                <div class="feature-card">
                    <i class="fa-solid fa-network-wired feature-icon" aria-hidden="true"></i>
                    <h3>The Network</h3>
                    <ul class="benefit-list">
                        <li>Instant access to verified editors & thumbnail artists.</li>
                        <li>Collaborate with creators in your niche.</li>
                        <li>No more cold DMs; instant connections.</li>
                    </ul>
                </div>
                <div class="feature-card">
                    <i class="fa-solid fa-graduation-cap feature-icon" aria-hidden="true"></i>
                    <h3>The Academy</h3>
                    <ul class="benefit-list">
                        <li>Weekly live teardowns of viral videos.</li>
                        <li>Templates for scripts and hooks.</li>
                        <li>Monetization roadmaps (AdSense to Brand Deals).</li>
                    </ul>
                </div>
                <div class="feature-card">
                    <i class="fa-solid fa-bolt feature-icon" aria-hidden="true"></i>
                    <h3>The Leverage</h3>
                    <ul class="benefit-list">
                        <li>Community cross-promotion engine.</li>
                        <li>Feedback loops to improve retention.</li>
                        <li>Direct access to industry tools.</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- TEAM -->
        <section id="team" aria-labelledby="team-title">
            <h2 id="team-title">THE ARCHITECTS</h2>
            <p>The team building the infrastructure for your growth.</p>

            <div class="team-grid">
                
                <!-- SURYANSH -->
                <article class="profile-card">
                    <div class="profile-img-box">
                        <img src="https://images.unsplash.com/photo-1519085360753-af0119f7cbe7?auto=format&fit=crop&w=800&q=80" alt="Portrait of Suryansh, Founder" class="profile-img">
                    </div>
                    <div class="profile-info">
                        <span class="role-tag">FOUNDER / STRATEGIST</span>
                        <h3 class="profile-name">Suryansh</h3>
                        <p class="profile-bio">The ecosystem architect. He designs the growth blueprints and infrastructure that allow creators to scale effortlessly.</p>
                        
                        <div class="comms-row">
                            <a href="mailto:suryanshy302@gmail.com" class="comm-link" aria-label="Email Suryansh"><i class="fa-solid fa-envelope"></i> Email</a>
                            <a href="https://www.instagram.com/suryansh_y09" target="_blank" class="comm-link" aria-label="Suryansh Instagram"><i class="fa-brands fa-instagram"></i> Instagram</a>
                        </div>
                    </div>
                </article>

                <!-- ANUP -->
                <article class="profile-card">
                    <div class="profile-img-box">
                        <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?auto=format&fit=crop&w=800&q=80" alt="Portrait of Anup, Operations" class="profile-img">
                    </div>
                    <div class="profile-info">
                        <span class="role-tag" style="color:var(--neon-red)">OPERATIONS LEAD</span>
                        <h3 class="profile-name">Anup</h3>
                        <p class="profile-bio">"Main Character Energy." He converts creative chaos into military-grade execution, ensuring every collab runs smoothly.</p>
                        
                        <div class="comms-row">
                            <a href="mailto:gurub0357@gmail.com" class="comm-link" aria-label="Email Anup"><i class="fa-solid fa-envelope"></i> Email</a>
                            <a href="https://www.instagram.com/anup_.45_45" target="_blank" class="comm-link" aria-label="Anup Instagram"><i class="fa-brands fa-instagram"></i> Instagram</a>
                        </div>
                    </div>
                </article>

                <!-- ADHAYAYAN -->
                <article class="profile-card">
                    <div class="profile-img-box">
                        <img src="https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?auto=format&fit=crop&w=800&q=80" alt="Portrait of Adhayayan, Creative Director" class="profile-img">
                    </div>
                    <div class="profile-info">
                        <span class="role-tag" style="color:var(--neon-purple)">CREATIVE DIRECTOR</span>
                        <h3 class="profile-name">Adhayayan</h3>
                        <p class="profile-bio">The visual alchemist. Guided by the principle of "Good over Bad," he ensures everything we ship looks world-class.</p>
                        
                        <div class="comms-row">
                            <a href="mailto:hindiaianimate@gmail.com" class="comm-link" aria-label="Email Adhayayan"><i class="fa-solid fa-envelope"></i> Email</a>
                            <a href="https://www.instagram.com/adhyayann_08" target="_blank" class="comm-link" aria-label="Adhayayan Instagram"><i class="fa-brands fa-instagram"></i> Instagram</a>
                        </div>
                    </div>
                </article>

            </div>
        </section>

    </main>

    <!-- FOOTER -->
    <footer class="site-footer">
        <h2 style="font-family:var(--font-hud); font-size:2rem; margin-bottom:1.5rem;">READY TO ASCEND?</h2>
        <a href="https://t.me/SpotlixHQ" target="_blank" class="cta-btn" style="font-size: 1.2rem; padding: 1.2rem 3rem;">
            Join the Squad on Telegram
        </a>
        
        <nav class="footer-nav" aria-label="Footer Links">
            <a href="mailto:spotlixhq@gmail.com">Email Us</a>
            <a href="https://www.instagram.com/spotlixhq" target="_blank">Instagram</a>
            <a href="https://www.youtube.com/@SpotlixHQ" target="_blank">YouTube</a>
        </nav>
        
        <p style="font-size:0.8rem; color:#555;">© 2025 SpotlixHQ. All Rights Reserved.</p>
    </footer>

    <!-- SCRIPTS -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>

    <script>
        // --- CONFIGURATION STATE ---
        const config = {
            isMobile: window.innerWidth <= 768,
            prefersReduced: window.matchMedia('(prefers-reduced-motion: reduce)').matches,
            fxEnabled: true // Default
        };

        // --- FX TOGGLE LOGIC ---
        const fxBtn = document.getElementById('fx-toggle');
        const cursor = document.getElementById('cursor-dot');
        const canvas = document.getElementById('webgl-canvas');

        function toggleFX() {
            config.fxEnabled = !config.fxEnabled;
            
            if (config.fxEnabled) {
                fxBtn.innerText = "FX: ON";
                fxBtn.classList.add('active');
                fxBtn.setAttribute('aria-pressed', 'true');
                if (!config.isMobile) cursor.style.display = 'block';
                canvas.style.opacity = '1';
                startThree(); // Restart animation
            } else {
                fxBtn.innerText = "FX: OFF";
                fxBtn.classList.remove('active');
                fxBtn.setAttribute('aria-pressed', 'false');
                cursor.style.display = 'none';
                canvas.style.opacity = '0';
            }
        }

        fxBtn.addEventListener('click', toggleFX);

        // Auto-disable FX on Reduced Motion preference
        if (config.prefersReduced) {
            toggleFX(); // Start off
        }

        // --- AUDIO ENGINE (Passive) ---
        const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
        
        function playHoverSound() {
            if (!config.fxEnabled || audioCtx.state === 'suspended') return;
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();
            osc.frequency.setValueAtTime(800, audioCtx.currentTime);
            osc.frequency.exponentialRampToValueAtTime(1200, audioCtx.currentTime + 0.1);
            gain.gain.setValueAtTime(0.01, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.1);
            osc.connect(gain);
            gain.connect(audioCtx.destination);
            osc.start();
            osc.stop(audioCtx.currentTime + 0.1);
        }

        // Initialize Audio Context on first click
        document.body.addEventListener('click', () => { if (audioCtx.state === 'suspended') audioCtx.resume(); }, { once: true });
        
        // Add sound to links
        document.querySelectorAll('a, button').forEach(el => {
            el.addEventListener('mouseenter', playHoverSound);
        });

        // --- CUSTOM CURSOR (Desktop Only) ---
        if (!config.isMobile && !config.prefersReduced) {
            cursor.style.display = 'block';
            window.addEventListener('mousemove', (e) => {
                if (config.fxEnabled) {
                    gsap.to(cursor, { x: e.clientX, y: e.clientY, duration: 0.1 });
                }
            });
        }

        // --- PRELOADER ---
        const fill = document.querySelector('.loader-fill');
        let load = 0;
        const interval = setInterval(() => {
            load += Math.random() * 20;
            if (load > 100) load = 100;
            fill.style.width = load + '%';
            if (load === 100) {
                clearInterval(interval);
                gsap.to('#boot-screen', { 
                    yPercent: -100, 
                    duration: 0.8, 
                    ease: "power2.inOut",
                    onComplete: () => {
                        document.getElementById('boot-screen').style.display = 'none';
                        if (config.fxEnabled) {
                            canvas.classList.add('active');
                            startThree();
                        }
                    }
                });
                initScrollAnim();
            }
        }, 100);

        // --- GSAP SCROLL ANIMATIONS ---
        function initScrollAnim() {
            if (config.prefersReduced) return;
            gsap.registerPlugin(ScrollTrigger);
            
            gsap.from('h1, .hero-sub, .social-proof, .hero-btns, .social-row', {
                y: 50, opacity: 0, stagger: 0.1, duration: 1, ease: "power3.out"
            });

            gsap.utils.toArray('.feature-card, .profile-card').forEach((el, i) => {
                gsap.from(el, {
                    y: 50, opacity: 0, duration: 0.8, delay: i * 0.1,
                    scrollTrigger: { trigger: el, start: "top 85%" }
                });
            });
        }

        // --- THREE.JS ENGINE ---
        let renderer, scene, camera, reactorGroup, animateId;

        function startThree() {
            if (animateId) return; // Already running
            
            const canvasEl = document.getElementById('webgl-canvas');
            scene = new THREE.Scene();
            camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000);
            
            renderer = new THREE.WebGLRenderer({ canvas: canvasEl, alpha: true, antialias: !config.isMobile });
            renderer.setSize(window.innerWidth, window.innerHeight);
            renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));

            // Reactor Ring (Torus)
            reactorGroup = new THREE.Group();
            scene.add(reactorGroup);

            const geo = new THREE.TorusGeometry(10, 0.5, 16, 100);
            const mat = new THREE.MeshBasicMaterial({ color: 0x00F3FF, wireframe: true, transparent: true, opacity: 0.15 });
            const ring = new THREE.Mesh(geo, mat);
            reactorGroup.add(ring);

            // Particles (Reduced count on mobile)
            const pCount = config.isMobile ? 400 : 1000;
            const pGeo = new THREE.BufferGeometry();
            const pArr = new Float32Array(pCount * 3);
            for(let i=0; i<pCount*3; i++) pArr[i] = (Math.random() - 0.5) * 50;
            pGeo.setAttribute('position', new THREE.BufferAttribute(pArr, 3));
            const pMat = new THREE.PointsMaterial({ size: 0.05, color: 0xffffff, transparent: true, opacity: 0.5 });
            const particles = new THREE.Points(pGeo, pMat);
            scene.add(particles);

            camera.position.z = 30;

            const animate = () => {
                if (!config.fxEnabled) {
                    cancelAnimationFrame(animateId);
                    animateId = null;
                    return;
                }
                
                animateId = requestAnimationFrame(animate);
                
                reactorGroup.rotation.z += 0.002;
                reactorGroup.rotation.x += 0.001;
                particles.rotation.y += 0.0005;
                
                renderer.render(scene, camera);
            };
            
            animate();
        }

        window.addEventListener('resize', () => {
            if(camera && renderer) {
                camera.aspect = window.innerWidth / window.innerHeight;
                camera.updateProjectionMatrix();
                renderer.setSize(window.innerWidth, window.innerHeight);
            }
        });

    </script>
</body>
</html>




