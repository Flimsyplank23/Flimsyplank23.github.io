<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flimsyplank23 - Developer Portfolio</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #0a0e27;
            color: #e0e0e0;
            line-height: 1.6;
        }

        /* --- TERMINATED SCREEN STYLES --- */
        #terminated-screen {
            display: none; /* Hidden unless banned */
            position: fixed;
            top: 0; left: 0; width: 100vw; height: 100vh;
            background: #000;
            color: #ff0000;
            z-index: 999999;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            font-family: 'Courier New', monospace;
            text-align: center;
            padding: 20px;
        }

        .red-alert-img {
            width: 300px;
            max-width: 80%;
            border: 4px solid #ff0000;
            box-shadow: 0 0 30px #ff0000;
            margin-bottom: 30px;
            animation: glitch 0.2s infinite;
        }

        @keyframes glitch {
            0% { transform: translate(0); }
            20% { transform: translate(-2px, 2px); }
            40% { transform: translate(-2px, -2px); }
            60% { transform: translate(2px, 2px); }
            80% { transform: translate(2px, -2px); }
            100% { transform: translate(0); }
        }

        /* --- ORIGINAL STYLES --- */
        .container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }
        .hero { min-height: 100vh; display: flex; align-items: center; justify-content: center; text-align: center; padding: 40px 20px; }
        .profile-img { width: 150px; height: 150px; border-radius: 50%; border: 4px solid #00d9ff; margin: 0 auto 30px; background-image: url('https://i.postimg.cc/3wC5R7bR/G_GURU_1.jpg'); background-size: cover; background-position: center; overflow: hidden; }
        h1 { font-size: 3rem; margin-bottom: 10px; background: linear-gradient(135deg, #00d9ff, #00ffa3); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; }
        .tagline { font-size: 1.5rem; color: #b0b0b0; margin-bottom: 30px; }
        .bio { font-size: 1.1rem; color: #d0d0d0; max-width: 600px; margin: 0 auto 40px; }
        .social-links { display: flex; gap: 20px; justify-content: center; flex-wrap: wrap; margin-bottom: 40px; }
        .social-links a { color: #00d9ff; text-decoration: none; font-size: 1.1rem; padding: 10px 20px; border: 2px solid #00d9ff; border-radius: 5px; transition: all 0.3s ease; display: flex; align-items: center; gap: 8px; }
        .social-links a:hover { background: #00d9ff; color: #0a0e27; transform: translateY(-2px); }
        .skills { display: flex; gap: 15px; justify-content: center; flex-wrap: wrap; margin-bottom: 60px; }
        .skill-badge { background: rgba(0, 217, 255, 0.1); border: 1px solid #00d9ff; padding: 8px 16px; border-radius: 20px; color: #00d9ff; font-size: 0.9rem; }
        .section { padding: 80px 20px; }
        .section-title { font-size: 2.5rem; text-align: center; margin-bottom: 60px; color: #fff; }
        .divider { height: 1px; background: linear-gradient(90deg, transparent, #00d9ff, transparent); margin: 80px 0; }
        .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(350px, 1fr)); gap: 30px; margin-bottom: 40px; }
        .project-card { background: rgba(255, 255, 255, 0.03); border: 1px solid rgba(0, 217, 255, 0.2); border-radius: 12px; overflow: hidden; transition: all 0.3s ease; position: relative; }
        .project-image { width: 100%; height: 200px; object-fit: cover; border-bottom: 1px solid rgba(0, 217, 255, 0.2); }
        .project-content { padding: 30px; }
        .project-card:hover { transform: translateY(-5px); border-color: #00d9ff; box-shadow: 0 10px 30px rgba(0, 217, 255, 0.2); }
        .project-title { font-size: 1.5rem; color: #00d9ff; margin-bottom: 5px; }
        .status-badge { padding: 4px 12px; border-radius: 12px; font-size: 0.8rem; font-weight: bold; border: 1px solid; }
        .status-active { background: rgba(0, 255, 163, 0.2); color: #00ffa3; border-color: #00ffa3; }
        .status-finished { background: rgba(102, 126, 234, 0.2); color: #667eea; border-color: #667eea; }
        .project-link { display: inline-block; color: #00d9ff; text-decoration: none; font-size: 0.9rem; margin-top: 10px; transition: all 0.3s ease; }
        .project-link:hover { color: #00ffa3; transform: translateX(5px); }
        .terminal-section { background: rgba(255, 255, 255, 0.02); padding: 60px 20px; margin: 60px 0; }
        .terminal { max-width: 800px; margin: 0 auto; background: #1a1a2e; border-radius: 8px; overflow: hidden; box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5); }
        .terminal-header { background: #16213e; padding: 12px 20px; display: flex; align-items: center; gap: 8px; }
        .terminal-button { width: 12px; height: 12px; border-radius: 50%; }
        .btn-red { background: #ff5f56; } .btn-yellow { background: #ffbd2e; } .btn-green { background: #27c93f; }
        .terminal-body { padding: 20px; font-family: 'Courier New', monospace; min-height: 400px; max-height: 600px; overflow-y: auto; }
        .terminal-output { margin-bottom: 20px; color: #b0b0b0; }
        .terminal-line { margin-bottom: 8px; word-wrap: break-word; }
        .terminal-prompt { color: #00d9ff; margin-right: 10px; }
        .terminal-prompt.banned { color: #ff5f56; }
        .terminal-input-line { display: flex; align-items: center; }
        .terminal-input { background: transparent; border: none; color: #e0e0e0; font-family: 'Courier New', monospace; font-size: 14px; outline: none; flex: 1; padding: 0; }
        .contact { text-align: center; padding: 80px 20px; }
        .contact-link { color: #00d9ff; text-decoration: none; font-size: 1.1rem; display: flex; align-items: center; gap: 10px; transition: all 0.3s ease; justify-content: center; }
        .contact-link:hover { color: #00ffa3; transform: translateX(5px); }
    </style>
</head>
<body>

    <div id="terminated-screen">
        <img src="https://i.postimg.cc/mD3m8vY0/terminated-red.png" class="red-alert-img" alt="TERMINATED">
        <h1 style="font-size: 3rem; margin-bottom: 10px;">ACCESS TERMINATED</h1>
        <p id="display-ip" style="font-size: 1.2rem; margin-bottom: 20px; color: #fff;"></p>
        <p style="letter-spacing: 2px;">YOUR IP HAS BEEN BLACKLISTED. CONNECTION REFUSED.</p>
    </div>

    <div id="main-content">
        <section class="hero">
            <div class="container">
                <div class="profile-img"></div>
                <h1>Flimsyplank23</h1>
                <p class="tagline">Software Engineer/Developer for fun</p>
                <p class="bio">Discord bot dev, Website developer and your local fun IT guy</p>
                <div class="social-links">
                    <a href="https://github.com/Flimsyplank23" target="_blank"><span>📊</span> GitHub</a>
                    <a href="https://instagram.com/flyingflynn12" target="_blank"><span>📷</span> Instagram</a>
                    <a href="https://tiktok.com/@flynn.planespotting" target="_blank"><span>🎵</span> TikTok</a>
                    <a href="mailto:Flynn@thehanks.co.uk"><span>✉️</span> Email</a>
                </div>
                <div class="skills">
                    <div class="skill-badge">Python</div>
                    <div class="skill-badge">HTML</div>
                    <div class="skill-badge">CSS</div>
                    <div class="skill-badge">Discord.py</div>
                    <div class="skill-badge">Web Development</div>
                </div>
            </div>
        </section>

        <div class="divider"></div>

        <section class="section">
            <div class="container">
                <h2 class="section-title">Projects</h2>
                <div class="projects-grid">
                    <div class="project-card">
                        <a href="https://gtamen-website.github.io" target="_blank">
                            <img src="https://i.postimg.cc/50XYr8gn/Screenshot_2026_01_17_at_6_50_29_pm.png" alt="GTAMEN Website" class="project-image">
                        </a>
                        <div class="project-content">
                            <div class="project-header">
                                <h3 class="project-title">GTAMEN Website</h3>
                                <span class="status-badge status-active">● Active</span>
                            </div>
                            <p class="project-description">Premier GTA V PS5 community website for GTAMEN content.</p>
                            <a href="https://gtamen-website.github.io" target="_blank" class="project-link">View Project →</a>
                        </div>
                    </div>
                    </div>
            </div>
        </section>

        <section class="terminal-section">
            <div class="container">
                <h2 class="terminal-title">Try the interactive shell!</h2>
                <div class="terminal">
                    <div class="terminal-header">
                        <div class="terminal-button btn-red"></div>
                        <div class="terminal-button btn-yellow"></div>
                        <div class="terminal-button btn-green"></div>
                    </div>
                    <div class="terminal-body">
                        <div class="terminal-output" id="output">
                            <div class="terminal-line">🎮 Welcome to Flimsyplank23 Fun Terminal! 🎮</div>
                            <div class="terminal-line">Type 'help' to see fun commands</div>
                        </div>
                        <div class="terminal-input-line">
                            <span class="terminal-prompt" id="prompt">visitor@flimsyplank23:~$</span>
                            <input type="text" class="terminal-input" id="terminalInput" autofocus>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="contact">
            <div class="container">
                <h2 class="contact-title">Feel like contacting me?</h2>
                <a href="mailto:Flynn@thehanks.co.uk" class="contact-link">✉️ Flynn@thehanks.co.uk</a>
            </div>
        </section>
    </div>

    <script>
        // --- REAL-TIME SECURITY CONFIG ---
        const SCRIPT_URL = "https://script.google.com/macros/s/AKfycbyRMcCaQ5lf-6A5aCz6f5hpuMbdUATVAAGEgiTy3NqKDsj005s57e_Kd2S-SkmhX_XDEg/exec";

        const terminalInput = document.getElementById('terminalInput');
        const output = document.getElementById('output');
        const promptSpan = document.getElementById('prompt');
        const termScreen = document.getElementById('terminated-screen');
        const mainContent = document.getElementById('main-content');
        const displayIp = document.getElementById('display-ip');

        let commandHistory = [];
        let historyIndex = -1;

        // 1. THE GATEKEEPER: Check ban status immediately on load
        async function checkSecurity() {
            try {
                // Get user's real IP
                const ipRes = await fetch('https://api.ipify.org?format=json');
                const ipData = await ipRes.json();
                const userIp = ipData.ip;

                // Check Google Sheet via your Script URL
                const check = await fetch(`${SCRIPT_URL}?ip=${userIp}`);
                const status = await check.json();

                if (status.banned) {
                    // DESTROY THE SITE CONTENT (Security measure)
                    mainContent.remove(); 
                    displayIp.innerText = "BLOCKED IP: " + userIp;
                    termScreen.style.display = 'flex';
                }
            } catch (e) {
                console.log("Security bridge active.");
            }
        }
        checkSecurity();

        // 2. TERMINAL COMMANDS
        const jokes = ["Why do programmers prefer dark mode? Because light attracts bugs! 🐛", "How many programmers does it take to change a light bulb? None, that's a hardware problem! 💡"];
        const facts = ["The first computer bug was an actual bug - a moth found in 1947! 🦋", "Python was named after Monty Python, not the snake! 🐍"];

        const commands = {
            help: () => "🌟 AVAILABLE COMMANDS: help, about, skills, joke, fact, goon, banme, clear",
            about: () => "👋 Hi! I'm Flimsyplank23. I'm a software engineer and discord bot developer.",
            skills: () => "💻 Tech Stack: Python, HTML/CSS/JS, Discord.py, Git.",
            joke: () => jokes[Math.floor(Math.random() * jokes.length)],
            fact: () => facts[Math.floor(Math.random() * facts.length)],
            
            goon: async () => {
                try {
                    const response = await fetch('https://nekos.life/api/v2/img/neko');
                    const data = await response.json();
                    return `<img src="${data.url}" style="max-width: 300px; border-radius: 10px; border: 2px solid #ff5f56;">`;
                } catch (e) { return "❌ Neko API Unavailable."; }
            },

            // REAL BANME COMMAND
            banme: async () => {
                const ipRes = await fetch('https://api.ipify.org?format=json');
                const ipData = await ipRes.json();
                const userIp = ipData.ip;

                // POST to Google Sheet
                fetch(SCRIPT_URL, {
                    method: 'POST',
                    mode: 'no-cors',
                    body: JSON.stringify({ ip: userIp })
                });

                setTimeout(() => { location.reload(); }, 2000);
                return "⚠️ SECURITY ALERT: IP " + userIp + " blacklisted. System locking...";
            },
            
            clear: () => { output.innerHTML = ''; return null; }
        };

        // 3. TERMINAL EVENT LISTENER
        terminalInput.addEventListener('keypress', async (e) => {
            if (e.key === 'Enter') {
                const input = terminalInput.value.trim().toLowerCase();
                
                const commandLine = document.createElement('div');
                commandLine.className = 'terminal-line';
                commandLine.innerHTML = `<span class="terminal-prompt">visitor@flimsyplank23:~$</span> ${terminalInput.value}`;
                output.appendChild(commandLine);

                if (commands[input]) {
                    const result = await commands[input]();
                    if (result) {
                        const resLine = document.createElement('div');
                        resLine.className = 'terminal-line';
                        resLine.style.color = (input === 'banme') ? '#ff5f56' : '#b0b0b0';
                        resLine.innerHTML = result;
                        output.appendChild(resLine);
                    }
                } else if (input !== '') {
                    const errLine = document.createElement('div');
                    errLine.className = 'terminal-line';
                    errLine.style.color = '#ff5f56';
                    errLine.textContent = `❌ Command not found: ${input}`;
                    output.appendChild(errLine);
                }

                terminalInput.value = '';
                output.parentElement.scrollTop = output.parentElement.scrollHeight;
            }
        });

        document.querySelector('.terminal-body').addEventListener('click', () => terminalInput.focus());
    </script>
</body>
</html>
