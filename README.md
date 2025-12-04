<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>SpotlixHQ | SENTIENT INTERFACE</title>
    <meta name="theme-color" content="#000000">

    <!-- FONTS -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;700;900&family=Rajdhani:wght@300;500;600;700&display=swap" rel="stylesheet">
    
    <!-- ICONS -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        :root {
            --bg: #020204;
            --arc-blue: #00F0FF;
            --arc-dim: rgba(0, 240, 255, 0.1);
            --danger: #FF3333;
            --gold: #FFD700;
            --font-hud: 'Orbitron', sans-serif;
            --font-tech: 'Rajdhani', sans-serif;
            --cursor-size: 40px;
        }

        /* --- CORE --- */
        *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; cursor: none; }
        
        body {
            background: var(--bg); color: white; font-family: var(--font-tech);
            overflow-x: hidden; width: 100%; min-height: 100vh;
            -webkit-font-smoothing: antialiased;
            perspective: 1000px; /* For global tilt */
        }

        /* --- LAYERS --- */
        #webgl-canvas {
            position: fixed; top: 0; left: 0; width: 100%; height: 100vh;
            z-index: 0; pointer-events: none; opacity: 0; transition: opacity 1s ease;
        }
        #webgl-canvas.loaded { opacity: 1; }
        
        #ui-layer { position: relative; z-index: 5; transform-style: preserve-3d; transition: transform 0.1s ease-out; }

        .scanlines {
            position: fixed; inset: 0; z-index: 2; pointer-events: none;
            background: linear-gradient(rgba(0,240,255,0.03) 50%, transparent 50%);
            background-size: 100% 4px;
        }
        
        .vignette {
            position: fixed; inset: 0; z-index: 3; pointer-events: none;
            background: radial-gradient(circle, transparent 60%, rgba(0,0,0,0.8) 100%);
        }

        /* --- HUD --- */
        .hud-overlay { position: fixed; inset: 0; z-index: 10; pointer-events: none; }
        .hud-corner { position: absolute; width: 100px; height: 100px; border: 2px solid transparent; opacity: 0.6; transition: 0.3s; }
        .tl { top: 30px; left: 30px; border-top: 2px solid var(--arc-blue); border-left: 2px solid var(--arc-blue); }
        .tr { top: 30px; right: 30px; border-top: 2px solid var(--arc-blue); border-right: 2px solid var(--arc-blue); text-align: right; }
        .bl { bottom: 30px; left: 30px; border-bottom: 2px solid var(--arc-blue); border-left: 2px solid var(--arc-blue); display: flex; align-items: flex-end; }
        .br { bottom: 30px; right: 30px; border-bottom: 2px solid var(--arc-blue); border-right: 2px solid var(--arc-blue); display: flex; align-items: flex-end; justify-content: flex-end; }
        
        .hud-data { font-family: var(--font-hud); font-size: 0.7rem; color: var(--arc-blue); margin: 5px; text-shadow: 0 0 5px var(--arc-blue); }

        /* --- TYPOGRAPHY --- */
        h1 {
            font-family: var(--font-hud); font-weight: 900; text-transform: uppercase;
            font-size: clamp(3rem, 9vw, 9rem); line-height: 0.9;
            color: white; text-shadow: 0 0 10px rgba(0,240,255,0.3);
            position: relative;
        }
        
        .glitch-wrapper { display: inline-block; position: relative; }
        .glitch-wrapper::before, .glitch-wrapper::after {
            content: attr(data-text); position: absolute; top: 0; left: 0; width: 100%; height: 100%; opacity: 0.8;
        }
        .glitch-wrapper::before { color: #f0f; z-index: -1; animation: glitch-effect 3s infinite; }
        .glitch-wrapper::after { color: #0ff; z-index: -2; animation: glitch-effect 2s infinite reverse; }
        
        @keyframes glitch-effect {
            0% { transform: translate(0); }
            20% { transform: translate(-2px, 2px); }
            40% { transform: translate(-2px, -2px); }
            60% { transform: translate(2px, 2px); }
            80% { transform: translate(2px, -2px); }
            100% { transform: translate(0); }
        }

        .subtitle { color: var(--arc-blue); letter-spacing: 0.3em; font-size: 0.8rem; margin-bottom: 1rem; display: block; }

        /* --- NAV --- */
        nav {
            position: fixed; top: 0; width: 100%; height: 80px; z-index: 100;
            display: flex; justify-content: space-between; align-items: center; padding: 0 4rem;
            background: linear-gradient(180deg, rgba(0,0,0,0.8) 0%, transparent 100%);
            border-bottom: 1px solid rgba(0,240,255,0.1);
            backdrop-filter: blur(5px);
        }
        .brand { font-family: var(--font-hud); font-size: 1.4rem; color: white; display: flex; align-items: center; gap: 12px; }
        .reactor-mini {
            width: 24px; height: 24px; border: 2px solid var(--arc-blue); border-radius: 50%;
            background: radial-gradient(circle, white 10%, var(--arc-blue) 60%, transparent 100%);
            box-shadow: 0 0 15px var(--arc-blue); animation: pulse 2s infinite;
        }

        /* --- BUTTONS --- */
        .btn-tech {
            position: relative; padding: 1rem 2.5rem; background: rgba(0, 240, 255, 0.05);
            border: 1px solid var(--arc-blue); color: var(--arc-blue);
            font-family: var(--font-hud); font-size: 0.8rem; font-weight: 700;
            letter-spacing: 0.15em; text-transform: uppercase; text-decoration: none;
            clip-path: polygon(15px 0, 100% 0, 100% calc(100% - 15px), calc(100% - 15px) 100%, 0 100%, 0 15px);
            transition: 0.3s; display: inline-block;
        }
        .btn-tech:hover {
            background: var(--arc-blue); color: black; box-shadow: 0 0 40px var(--arc-blue);
        }
        .btn-tech::after {
            content: ''; position: absolute; bottom: 0; right: 0; width: 10px; height: 10px;
            background: white; clip-path: polygon(100% 0, 0 100%, 100% 100%);
        }

        /* --- SECTIONS --- */
        section { min-height: 100vh; padding: 0 10vw; display: flex; flex-direction: column; justify-content: center; position: relative; }

        /* Social Matrix */
        .social-grid { display: flex; gap: 1rem; margin-top: 3rem; flex-wrap: wrap; }
        .social-node {
            width: 60px; height: 60px; border: 1px solid rgba(0,240,255,0.3);
            display: flex; align-items: center; justify-content: center;
            color: var(--arc-blue); font-size: 1.2rem; background: rgba(0,0,0,0.5);
            transition: 0.3s; position: relative; overflow: hidden; text-decoration: none;
        }
        .social-node::before {
            content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 2px;
            background: var(--arc-blue); transform: translateX(-100%); transition: 0.3s;
        }
        .social-node:hover { color: white; background: rgba(0,240,255,0.1); box-shadow: 0 0 20px rgba(0,240,255,0.2); }
        .social-node:hover::before { transform: translateX(0); }

        /* Team Cards */
        .team-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 3rem; margin-top: 5rem; }
        
        .holocard {
            position: relative; height: 520px; border: 1px solid var(--arc-dim);
            background: rgba(5, 10, 15, 0.6); transition: 0.4s; overflow: hidden;
            display: flex; flex-direction: column;
        }
        .holocard:hover { border-color: var(--arc-blue); transform: translateY(-10px); box-shadow: 0 10px 40px rgba(0,240,255,0.1); }
        
        .holocard-visual { width: 100%; height: 50%; position: relative; overflow: hidden; border-bottom: 1px solid var(--arc-dim); }
        .holocard-img { width: 100%; height: 100%; object-fit: cover; filter: grayscale(1) sepia(1) hue-rotate(180deg) saturate(1.5); transition: 0.5s; opacity: 0.8; }
        .holocard:hover .holocard-img { filter: none; opacity: 1; transform: scale(1.05); }
        
        .scanner {
            position: absolute; top: 0; left: 0; width: 100%; height: 2px;
            background: var(--arc-blue); box-shadow: 0 0 15px var(--arc-blue);
            opacity: 0; pointer-events: none; z-index: 5;
        }
        .holocard:hover .scanner { animation: scan 2s linear infinite; opacity: 1; }
        
        .holocard-data { padding: 1.5rem; flex: 1; display: flex; flex-direction: column; }
        .id-badge { font-size: 0.7rem; color: var(--arc-blue); letter-spacing: 0.1em; margin-bottom: 0.5rem; }
        .holo-name { font-family: var(--font-hud); font-size: 1.8rem; margin-bottom: 0.5rem; }
        .holo-role { color: #888; font-size: 0.9rem; margin-bottom: 1rem; text-transform: uppercase; }
        
        .comms-array { margin-top: auto; display: flex; gap: 10px; border-top: 1px solid var(--arc-dim); padding-top: 1rem; }
        .comm-link {
            flex: 1; padding: 0.5rem; border: 1px solid var(--arc-dim);
            display: flex; align-items: center; justify-content: center; gap: 8px;
            color: var(--arc-blue); text-decoration: none; font-size: 0.8rem;
            text-transform: uppercase; transition: 0.3s;
        }
        .comm-link:hover { background: var(--arc-blue); color: black; }

        /* FOOTER */
        footer {
            border-top: 1px solid var(--arc-blue); padding: 6rem 10vw; text-align: center;
            background: radial-gradient(circle at center, #111 0%, #000 100%);
        }

        /* CURSOR SYSTEM */
        #cursor {
            position: fixed; top: 0; left: 0; z-index: 9999; pointer-events: none;
            transform: translate(-50%, -50%); mix-blend-mode: screen;
        }
        .cursor-reticle {
            width: var(--cursor-size); height: var(--cursor-size);
            border: 1px dashed var(--arc-blue); border-radius: 50%;
            transition: width 0.2s, height 0.2s, border-color 0.2s;
            animation: rotate 10s linear infinite;
        }
        .cursor-dot {
            width: 4px; height: 4px; background: var(--arc-blue); border-radius: 50%;
            position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);
        }
        .cursor-lock .cursor-reticle {
            width: 60px; height: 60px; border-style: solid; border-width: 2px;
            border-color: var(--danger); animation: lockOn 0.3s forwards;
            background: rgba(255, 50, 50, 0.1);
        }
        .cursor-lock .cursor-dot { background: var(--danger); }

        /* PARTICLES */
        .particle {
            position: fixed; pointer-events: none; background: var(--arc-blue);
            border-radius: 50%; mix-blend-mode: screen; z-index: 9998;
        }

        /* ANIMATIONS */
        @keyframes scan { 0% { top: 0; } 50% { top: 100%; } 100% { top: 0; } }
        @keyframes rotate { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }
        @keyframes lockOn { 0% { transform: scale(1.5) rotate(0deg); } 100% { transform: scale(1) rotate(45deg); } }
        @keyframes pulse { 0%, 100% { box-shadow: 0 0 15px var(--arc-blue); } 50% { box-shadow: 0 0 30px var(--arc-blue); } }

        /* PRELOADER */
        #boot-screen {
            position: fixed; inset: 0; background: black; z-index: 99999;
            display: flex; flex-direction: column; justify-content: center; align-items: center;
        }
        .loader-ring {
            width: 80px; height: 80px; border: 4px solid rgba(0,240,255,0.1);
            border-top: 4px solid var(--arc-blue); border-radius: 50%;
            animation: rotate 1s linear infinite; box-shadow: 0 0 30px var(--arc-blue);
        }

        @media (max-width: 768px) {
            h1 { font-size: 3.5rem; }
            .team-grid { grid-template-columns: 1fr; }
            nav { padding: 0 2rem; }
            .hud-corner { width: 50px; height: 50px; }
        }
    </style>
</head>
<body>

    <!-- AUDIO ENGINE (Hidden) -->
    <!-- Sound will be generated via Web Audio API script below -->

    <!-- PRELOADER -->
    <div id="boot-screen">
        <div class="loader-ring"></div>
        <div style="margin-top:20px; font-family:var(--font-hud); color:var(--arc-blue); font-size:0.8rem; letter-spacing:0.2em;">SYSTEM INITIALIZING...</div>
        <div style="margin-top:10px; font-family:var(--font-tech); color:#555; font-size:0.7rem;">CLICK TO ENGAGE AUDIO</div>
    </div>

    <!-- HUD LAYERS -->
    <div class="scanlines"></div>
    <div class="vignette"></div>
    <div class="hud-overlay">
        <div class="hud-corner tl">
            <div class="hud-data">SYS: ONLINE</div>
            <div class="hud-data">AUD: STANDBY</div>
        </div>
        <div class="hud-corner tr">
            <div class="hud-data" id="time">00:00</div>
        </div>
        <div class="hud-corner bl">
            <div class="hud-data">PWR: 100%</div>
        </div>
        <div class="hud-corner br">
            <div class="hud-data">TGT: <span id="coords">0,0</span></div>
        </div>
    </div>

    <!-- CANVAS -->
    <canvas id="webgl-canvas"></canvas>

    <!-- CURSOR -->
    <div id="cursor">
        <div class="cursor-reticle"></div>
        <div class="cursor-dot"></div>
    </div>

    <!-- UI LAYER -->
    <div id="ui-layer">
        <nav>
            <div class="brand trigger-audio-hover">
                <div class="reactor-mini"></div>
                SPOTLIX<span style="color:var(--arc-blue)">HQ</span>
            </div>
            <a href="https://t.me/SpotlixHQ" target="_blank" class="btn-tech trigger-audio-hover">Access Protocol</a>
        </nav>

        <div id="smooth-wrapper">
            <div id="smooth-content">

                <!-- HERO -->
                <section class="hero">
                    <span class="subtitle fade-up">// PROTOCOL: OMEGA</span>
                    <h1>
                        <div class="glitch-wrapper decrypt-text" data-text="ASSEMBLE">ASSEMBLE</div><br>
                        <div class="glitch-wrapper decrypt-text" data-text="THE SQUAD" style="color:transparent; -webkit-text-stroke:2px white;">THE SQUAD</div>
                    </h1>
                    
                    <p style="margin-top:2rem; max-width:600px; color:#aaa; border-left:2px solid var(--arc-blue); padding-left:1rem;" class="fade-up">
                        SpotlixHQ is the advanced ecosystem for digital architects. We provide the infrastructure to upgrade your creative output from amateur to industrial-grade.
                    </p>

                    <div class="social-grid fade-up">
                        <a href="mailto:spotlixhq@gmail.com" class="social-node trigger-audio-hover" title="Email"><i class="fa-solid fa-envelope"></i></a>
                        <a href="https://t.me/SpotlixHQ" target="_blank" class="social-node trigger-audio-hover" title="Telegram"><i class="fa-brands fa-telegram"></i></a>
                        <a href="https://www.instagram.com/spotlixhq" target="_blank" class="social-node trigger-audio-hover" title="Instagram"><i class="fa-brands fa-instagram"></i></a>
                        <a href="https://www.youtube.com/@SpotlixHQ" target="_blank" class="social-node trigger-audio-hover" title="YouTube"><i class="fa-brands fa-youtube"></i></a>
                    </div>
                </section>

                <!-- MISSION -->
                <section>
                    <div style="color:var(--danger); font-family:var(--font-hud); letter-spacing:0.2em; margin-bottom:1rem;">// THREAT ANALYSIS</div>
                    <h2 style="font-family:var(--font-hud); font-size:3rem; margin-bottom:2rem;">SOLO PLAY IS <span style="color:var(--danger)">OBSOLETE</span></h2>
                    <p style="font-size:1.5rem; line-height:1.4; max-width:1200px; color:#ddd;">
                        The creative landscape is a warzone. SpotlixHQ is your vibranium armor.
                        We provide the <strong style="color:var(--arc-blue)">Network</strong>, the <strong style="color:var(--arc-blue)">Tools</strong>, and the <strong style="color:var(--arc-blue)">Leverage</strong> to dominate.
                    </p>
                </section>

                <!-- ROSTER -->
                <section id="roster">
                    <div style="font-family:var(--font-hud); color:var(--arc-blue); letter-spacing:0.2em; margin-bottom:1rem;">// PERSONNEL DATABASE</div>
                    <h2 style="font-family:var(--font-hud); font-size:4rem; margin-bottom:2rem;">THE AVENGERS</h2>

                    <div class="team-grid">
                        
                        <!-- SURYANSH -->
                        <div class="holocard trigger-audio-hover">
                            <div class="holocard-visual">
                                <div class="scanner"></div>
                                <img src="https://images.unsplash.com/photo-1519085360753-af0119f7cbe7?auto=format&fit=crop&w=800&q=80" alt="Suryansh" class="holocard-img">
                            </div>
                            <div class="holocard-data">
                                <span class="id-badge">ID: 001 // LVL: ALPHA</span>
                                <div class="holo-name">SURYANSH</div>
                                <div class="holo-role">Founder / Strategist</div>
                                <p style="font-size:0.85rem; color:#888;">The "Tony Stark". Builds the infrastructure. Sees the future before it renders.</p>
                                <div class="comms-array">
                                    <a href="mailto:suryanshy302@gmail.com" class="comm-link trigger-audio-hover"><i class="fa-solid fa-envelope"></i> Email</a>
                                    <a href="https://www.instagram.com/suryansh_y09" target="_blank" class="comm-link trigger-audio-hover"><i class="fa-brands fa-instagram"></i> Feed</a>
                                </div>
                            </div>
                        </div>

                        <!-- ANUP -->
                        <div class="holocard trigger-audio-hover">
                            <div class="holocard-visual">
                                <div class="scanner"></div>
                                <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?auto=format&fit=crop&w=800&q=80" alt="Anup" class="holocard-img">
                            </div>
                            <div class="holocard-data">
                                <span class="id-badge">ID: 002 // LVL: BETA</span>
                                <div class="holo-name">ANUP</div>
                                <div class="holo-role" style="color:var(--danger)">Operations / Enforcer</div>
                                <p style="font-size:0.85rem; color:#888;">The "Captain". Converts chaos into order. Ensures mission success parameters are met.</p>
                                <div class="comms-array">
                                    <a href="mailto:gurub0357@gmail.com" class="comm-link trigger-audio-hover"><i class="fa-solid fa-envelope"></i> Email</a>
                                    <a href="https://www.instagram.com/anup_.45_45" target="_blank" class="comm-link trigger-audio-hover"><i class="fa-brands fa-instagram"></i> Feed</a>
                                </div>
                            </div>
                        </div>

                        <!-- ADHAYAYAN -->
                        <div class="holocard trigger-audio-hover">
                            <div class="holocard-visual">
                                <div class="scanner"></div>
                                <img src="https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?auto=format&fit=crop&w=800&q=80" alt="Adhayayan" class="holocard-img">
                            </div>
                            <div class="holocard-data">
                                <span class="id-badge">ID: 003 // LVL: BETA</span>
                                <div class="holo-name">ADHAYAYAN</div>
                                <div class="holo-role" style="color:#bf00ff">Creative / Visionary</div>
                                <p style="font-size:0.85rem; color:#888;">The "Strange". Bends reality with visual alchemy. Prioritizes aesthetics over physics.</p>
                                <div class="comms-array">
                                    <a href="mailto:hindiaianimate@gmail.com" class="comm-link trigger-audio-hover"><i class="fa-solid fa-envelope"></i> Email</a>
                                    <a href="https://www.instagram.com/adhyayann_08" target="_blank" class="comm-link trigger-audio-hover"><i class="fa-brands fa-instagram"></i> Feed</a>
                                </div>
                            </div>
                        </div>

                    </div>
                </section>

                <!-- FOOTER -->
                <footer style="margin-top:5rem;">
                    <div style="font-family:var(--font-hud); letter-spacing:0.2em; color:var(--danger); margin-bottom:2rem;">// TERMINATING SESSION</div>
                    <a href="https://t.me/SpotlixHQ" target="_blank" class="btn-tech trigger-audio-hover" style="font-size:2rem; padding:2rem 4rem;">JOIN THE SQUAD</a>
                    <div style="margin-top:4rem; color:#444; font-size:0.8rem;">SPOTLIXHQ IND. © 2025 // SECURE SERVER</div>
                </footer>

            </div>
        </div>
    </div>

    <!-- SCRIPTS -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
    <script src="https://unpkg.com/@studio-freight/lenis@1.0.29/dist/lenis.min.js"></script>

    <script>
        // --- 1. PROCEDURAL AUDIO ENGINE (THE SENTIENT PART) ---
        const AudioEngine = {
            ctx: null,
            init: function() {
                window.AudioContext = window.AudioContext || window.webkitAudioContext;
                this.ctx = new AudioContext();
            },
            playTone: function(freq, type, duration, vol) {
                if(!this.ctx) return;
                const osc = this.ctx.createOscillator();
                const gain = this.ctx.createGain();
                osc.type = type;
                osc.frequency.setValueAtTime(freq, this.ctx.currentTime);
                gain.gain.setValueAtTime(vol, this.ctx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.01, this.ctx.currentTime + duration);
                osc.connect(gain);
                gain.connect(this.ctx.destination);
                osc.start();
                osc.stop(this.ctx.currentTime + duration);
            },
            hoverSound: function() {
                // High pitch UI blip
                this.playTone(800, 'sine', 0.1, 0.05);
                this.playTone(1200, 'triangle', 0.05, 0.02);
            },
            clickSound: function() {
                // Mechanical lock sound
                this.playTone(150, 'sawtooth', 0.2, 0.1);
                this.playTone(60, 'square', 0.3, 0.1);
            },
            bootSound: function() {
                // Power up sound
                if(!this.ctx) return;
                const osc = this.ctx.createOscillator();
                const gain = this.ctx.createGain();
                osc.frequency.setValueAtTime(50, this.ctx.currentTime);
                osc.frequency.exponentialRampToValueAtTime(1000, this.ctx.currentTime + 1);
                gain.gain.setValueAtTime(0, this.ctx.currentTime);
                gain.gain.linearRampToValueAtTime(0.1, this.ctx.currentTime + 0.5);
                gain.gain.linearRampToValueAtTime(0, this.ctx.currentTime + 1.5);
                osc.connect(gain);
                gain.connect(this.ctx.destination);
                osc.start();
                osc.stop(this.ctx.currentTime + 1.5);
            }
        };

        // Initialize Audio on First Interaction
        let audioInit = false;
        document.body.addEventListener('click', () => {
            if(!audioInit) {
                AudioEngine.init();
                AudioEngine.bootSound();
                audioInit = true;
                document.querySelector('.hud-corner.tl .hud-data:last-child').innerText = "AUD: ACTIVE";
            }
        });

        // Attach Audio Triggers
        document.querySelectorAll('.trigger-audio-hover').forEach(el => {
            el.addEventListener('mouseenter', () => AudioEngine.hoverSound());
            el.addEventListener('mousedown', () => AudioEngine.clickSound());
        });

        // --- 2. BOOT SEQUENCE ---
        window.onload = () => {
            setTimeout(() => {
                gsap.to('#boot-screen', { yPercent: -100, duration: 1, ease: "power4.inOut" });
                document.getElementById('webgl-canvas').classList.add('loaded');
                initThree();
                initAnimations();
            }, 2000);
        };

        // --- 3. HUD UPDATES ---
        setInterval(() => {
            document.getElementById('time').innerText = new Date().toLocaleTimeString();
        }, 1000);

        window.addEventListener('mousemove', (e) => {
            document.getElementById('coords').innerText = `${e.clientX},${e.clientY}`;
            
            // Global Tilt
            const x = (e.clientX / window.innerWidth - 0.5) * 20;
            const y = (e.clientY / window.innerHeight - 0.5) * 20;
            document.getElementById('ui-layer').style.transform = `rotateY(${x * 0.5}deg) rotateX(${-y * 0.5}deg)`;
            
            // Cursor
            gsap.to('#cursor', { x: e.clientX, y: e.clientY, duration: 0.1 });
            
            // Create Particle
            createParticle(e.clientX, e.clientY);
        });

        function createParticle(x, y) {
            const p = document.createElement('div');
            p.classList.add('particle');
            document.body.appendChild(p);
            
            const size = Math.random() * 4 + 2;
            p.style.width = `${size}px`;
            p.style.height = `${size}px`;
            p.style.left = `${x}px`;
            p.style.top = `${y}px`;
            
            gsap.to(p, {
                x: (Math.random() - 0.5) * 30,
                y: (Math.random() - 0.5) * 30,
                opacity: 0,
                duration: 0.8,
                onComplete: () => p.remove()
            });
        }

        // --- 4. TARGET LOCK ---
        document.querySelectorAll('.trigger-audio-hover').forEach(el => {
            el.addEventListener('mouseenter', () => document.getElementById('cursor').classList.add('cursor-lock'));
            el.addEventListener('mouseleave', () => document.getElementById('cursor').classList.remove('cursor-lock'));
        });

        // --- 5. SMOOTH SCROLL ---
        const lenis = new Lenis({ duration: 1.5, smooth: true });
        function raf(time) { lenis.raf(time); requestAnimationFrame(raf); }
        requestAnimationFrame(raf);

        // --- 6. ANIMATIONS ---
        function initAnimations() {
            gsap.registerPlugin(ScrollTrigger);
            
            // Decrypt Text
            const chars = "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";
            document.querySelectorAll('.decrypt-text').forEach(el => {
                const original = el.getAttribute('data-text');
                let iterations = 0;
                const interval = setInterval(() => {
                    el.innerText = original.split("").map((letter, index) => {
                        if(index < iterations) return original[index];
                        return chars[Math.floor(Math.random() * chars.length)];
                    }).join("");
                    if(iterations >= original.length) clearInterval(interval);
                    iterations += 1/3;
                }, 30);
            });

            gsap.utils.toArray('.fade-up').forEach(el => {
                gsap.from(el, {
                    y: 30, opacity: 0, duration: 1, scrollTrigger: { trigger: el, start: "top 85%" }
                });
            });
        }

        // --- 7. THREE.JS REACTOR ---
        function initThree() {
            const canvas = document.getElementById('webgl-canvas');
            const scene = new THREE.Scene();
            const camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000);
            const renderer = new THREE.WebGLRenderer({ canvas: canvas, alpha: true, antialias: true });
            
            renderer.setSize(window.innerWidth, window.innerHeight);
            renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));

            // Reactor Geometry
            const geo = new THREE.TorusKnotGeometry(10, 2, 120, 16, 2, 5);
            const mat = new THREE.MeshBasicMaterial({ color: 0x00F0FF, wireframe: true, transparent: true, opacity: 0.1 });
            const reactor = new THREE.Mesh(geo, mat);
            scene.add(reactor);

            // Core Glow
            const glowGeo = new THREE.SphereGeometry(3, 32, 32);
            const glowMat = new THREE.MeshBasicMaterial({ color: 0x00F0FF });
            const core = new THREE.Mesh(glowGeo, glowMat);
            scene.add(core);

            // Particles
            const pGeo = new THREE.BufferGeometry();
            const pCount = 800;
            const pArr = new Float32Array(pCount * 3);
            for(let i=0; i<pCount*3; i++) pArr[i] = (Math.random()-0.5)*50;
            pGeo.setAttribute('position', new THREE.BufferAttribute(pArr, 3));
            const pMat = new THREE.PointsMaterial({ size: 0.1, color: 0xffffff });
            const stars = new THREE.Points(pGeo, pMat);
            scene.add(stars);

            camera.position.z = 35;
            
            const clock = new THREE.Clock();
            
            function animate() {
                requestAnimationFrame(animate);
                const t = clock.getElapsedTime();
                
                reactor.rotation.z = t * 0.1;
                stars.rotation.y = t * 0.05;
                
                // Audio Pulse Simulation (since we don't have real frequency data)
                const pulse = 1 + Math.sin(t * 5) * 0.05;
                core.scale.set(pulse, pulse, pulse);

                renderer.render(scene, camera);
            }
            animate();
            
            window.addEventListener('resize', () => {
                camera.aspect = window.innerWidth / window.innerHeight;
                camera.updateProjectionMatrix();
                renderer.setSize(window.innerWidth, window.innerHeight);
            });
            
            // Reactor Surge on Click
            document.addEventListener('mousedown', () => {
                gsap.to(reactor.scale, { x: 1.5, y: 1.5, z: 1.5, duration: 0.1, yoyo: true, repeat: 1 });
                gsap.to(mat, { opacity: 0.5, duration: 0.1, yoyo: true, repeat: 1 });
            });
        }
    </script>
</body>
</html>


