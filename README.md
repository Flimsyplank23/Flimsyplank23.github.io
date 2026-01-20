<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flimsyplank23 - Developer Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #0a0e27;
            color: #e0e0e0;
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 40px 20px;
        }

        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 4px solid #00d9ff;
            margin: 0 auto 30px;
            background-image: url('https://i.postimg.cc/3wC5R7bR/G_GURU_1.jpg');
            background-size: cover;
            background-position: center;
            overflow: hidden;
        }

        h1 {
            font-size: 3rem;
            margin-bottom: 10px;
            background: linear-gradient(135deg, #00d9ff, #00ffa3);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .tagline {
            font-size: 1.5rem;
            color: #b0b0b0;
            margin-bottom: 30px;
        }

        .bio {
            font-size: 1.1rem;
            color: #d0d0d0;
            max-width: 600px;
            margin: 0 auto 40px;
        }

        /* Social Links */
        .social-links {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            margin-bottom: 40px;
        }

        .social-links a {
            color: #00d9ff;
            text-decoration: none;
            font-size: 1.1rem;
            padding: 10px 20px;
            border: 2px solid #00d9ff;
            border-radius: 5px;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .social-links a:hover {
            background: #00d9ff;
            color: #0a0e27;
            transform: translateY(-2px);
        }

        /* Skills Section */
        .skills {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
            margin-bottom: 60px;
        }

        .skill-badge {
            background: rgba(0, 217, 255, 0.1);
            border: 1px solid #00d9ff;
            padding: 8px 16px;
            border-radius: 20px;
            color: #00d9ff;
            font-size: 0.9rem;
        }

        /* Section Headers */
        .section {
            padding: 80px 20px;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 60px;
            color: #fff;
        }

        .divider {
            height: 1px;
            background: linear-gradient(90deg, transparent, #00d9ff, transparent);
            margin: 80px 0;
        }

        /* Projects Grid */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(0, 217, 255, 0.2);
            border-radius: 12px;
            overflow: hidden;
            transition: all 0.3s ease;
            position: relative;
        }

        .project-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-bottom: 1px solid rgba(0, 217, 255, 0.2);
        }

        .project-content {
            padding: 30px;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #00d9ff, #00ffa3);
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .project-card:hover::before {
            transform: scaleX(1);
        }

        .project-card:hover {
            transform: translateY(-5px);
            border-color: #00d9ff;
            box-shadow: 0 10px 30px rgba(0, 217, 255, 0.2);
        }

        .project-header {
            display: flex;
            justify-content: space-between;
            align-items: start;
            margin-bottom: 15px;
        }

        .project-title {
            font-size: 1.5rem;
            color: #00d9ff;
            margin-bottom: 5px;
        }

        .status-badge {
            padding: 4px 12px;
            border-radius: 12px;
            font-size: 0.8rem;
            font-weight: bold;
        }

        .status-active {
            background: rgba(0, 255, 163, 0.2);
            color: #00ffa3;
            border: 1px solid #00ffa3;
        }

        .status-finished {
            background: rgba(102, 126, 234, 0.2);
            color: #667eea;
            border: 1px solid #667eea;
        }

        .project-description {
            color: #b0b0b0;
            margin-bottom: 20px;
            line-height: 1.6;
        }

        .project-link {
            display: inline-block;
            color: #00d9ff;
            text-decoration: none;
            font-size: 0.9rem;
            margin-top: 10px;
            transition: all 0.3s ease;
        }

        .project-link:hover {
            color: #00ffa3;
            transform: translateX(5px);
        }

        /* Terminal Section */
        .terminal-section {
            background: rgba(255, 255, 255, 0.02);
            padding: 60px 20px;
            margin: 60px 0;
        }

        .terminal-title {
            text-align: center;
            font-size: 2rem;
            margin-bottom: 30px;
            color: #fff;
        }

        .terminal {
            max-width: 800px;
            margin: 0 auto;
            background: #1a1a2e;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
        }

        .terminal-header {
            background: #16213e;
            padding: 12px 20px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .terminal-button {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }

        .btn-red { background: #ff5f56; }
        .btn-yellow { background: #ffbd2e; }
        .btn-green { background: #27c93f; }

        .terminal-body {
            padding: 20px;
            font-family: 'Courier New', monospace;
            min-height: 400px;
            max-height: 600px;
            overflow-y: auto;
        }

        .terminal-output {
            margin-bottom: 20px;
            color: #b0b0b0;
        }

        .terminal-line {
            margin-bottom: 8px;
            word-wrap: break-word;
        }

        .terminal-prompt {
            color: #00d9ff;
            margin-right: 10px;
        }

        /* Styles for Banned/Locked State */
        .terminal-prompt.banned {
            color: #ff5f56;
        }
        
        .terminal-prompt.locked {
            color: #ffbd2e;
        }

        .terminal-input-line {
            display: flex;
            align-items: center;
        }

        .terminal-input {
            background: transparent;
            border: none;
            color: #e0e0e0;
            font-family: 'Courier New', monospace;
            font-size: 14px;
            outline: none;
            flex: 1;
            padding: 0;
        }

        /* Contact Section */
        .contact {
            text-align: center;
            padding: 80px 20px;
        }

        .contact-title {
            font-size: 2rem;
            margin-bottom: 30px;
        }

        .contact-links {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
            margin-bottom: 40px;
        }

        .contact-link {
            color: #00d9ff;
            text-decoration: none;
            font-size: 1.1rem;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: all 0.3s ease;
        }

        .contact-link:hover {
            color: #00ffa3;
            transform: translateX(5px);
        }

        @media (max-width: 768px) {
            h1 { font-size: 2rem; }
            .tagline { font-size: 1.2rem; }
            .projects-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <section class="hero">
        <div class="container">
            <div class="profile-img"></div>
            <h1>Flimsyplank23</h1>
            <p class="tagline">Software Engineer/Developer for fun</p>
            <p class="bio">Discord bot dev, Website developer and your local fun IT guy</p>
            
            <div class="social-links">
                <a href="https://github.com/Flimsyplank23" target="_blank">
                    <span>📊</span> GitHub
                </a>
                <a href="https://instagram.com/flyingflynn12" target="_blank">
                    <span>📷</span> Instagram
                </a>
                <a href="https://tiktok.com/@flynn.planespotting" target="_blank">
                    <span>🎵</span> TikTok
                </a>
                <a href="mailto:Flynn@thehanks.co.uk">
                    <span>✉️</span> Email
                </a>
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
                        <p class="project-description">
                            The premier GTA V PS5 community website dedicated to GTAMEN content, epic movie productions, and unforgettable events. Features a modern design with community integration.
                        </p>
                        <a href="https://gtamen-website.github.io" target="_blank" class="project-link">View Project →</a>
                    </div>
                </div>

                <div class="project-card">
                    <img src="https://i.postimg.cc/fb2S58cp/Screenshot_2026_01_17_at_6_57_20_pm.png" alt="GTAMEN Discord Bot" class="project-image">
                    <div class="project-content">
                        <div class="project-header">
                            <h3 class="project-title">GTAMEN Discord Bot</h3>
                            <span class="status-badge status-active">● Active</span>
                        </div>
                        <p class="project-description">
                            A custom Discord bot designed for the GTAMEN and LSN servers. Helps manage community features with commands like /training and /car-meet for organized events.
                        </p>
                    </div>
                </div>

                <div class="project-card">
                    <a href="https://supercoolalgebragames.github.io" target="_blank">
                        <img src="https://i.postimg.cc/tTsZcFkB/Screenshot_2026_01_17_at_6_50_44_pm.png" alt="Algebra Adventure" class="project-image">
                    </a>
                    <div class="project-content">
                        <div class="project-header">
                            <h3 class="project-title">Algebra Adventure</h3>
                            <span class="status-badge status-finished">● Finished</span>
                        </div>
                        <p class="project-description">
                            An interactive algebra games website featuring a sorting game and solve-for-x challenges. Master algebraic concepts through engaging gameplay with 120+ questions.
                        </p>
                        <a href="https://supercoolalgebragames.github.io" target="_blank" class="project-link">View Project →</a>
                    </div>
                </div>

                <div class="project-card">
                    <a href="https://supercoolmathgames-cool.github.io" target="_blank">
                        <img src="https://i.postimg.cc/6Qj4zMrS/Screenshot_2026_01_17_at_6_51_12_pm.png" alt="School Chat Website" class="project-image">
                    </a>
                    <div class="project-content">
                        <div class="project-header">
                            <h3 class="project-title">School Chat Website</h3>
                            <span class="status-badge status-active">● Active</span>
                        </div>
                        <p class="project-description">
                            A chat platform designed to bypass school network restrictions, enabling communication during lessons. Built with a focus on simplicity and accessibility.
                        </p>
                        <a href="https://supercoolmathgames-cool.github.io" target="_blank" class="project-link">View Project →</a>
                    </div>
                </div>

                <div class="project-card">
                    <a href="https://ahmedacademyphysics.github.io" target="_blank">
                        <img src="https://i.postimg.cc/hGyQM2LH/Screenshot_2026_01_17_at_6_51_21_pm.png" alt="Ahmed Academy Physics" class="project-image">
                    </a>
                    <div class="project-content">
                        <div class="project-header">
                            <h3 class="project-title">Ahmed Academy Physics</h3>
                            <span class="status-badge status-active">● Active</span>
                        </div>
                        <p class="project-description">
                            A comprehensive physics education website featuring slides, interactive modules, and question banks across topics like Thermodynamics, Mechanics, and Nuclear Physics.
                        </p>
                        <a href="https://ahmedacademyphysics.github.io" target="_blank" class="project-link">View Project →</a>
                    </div>
                </div>

                <div class="project-card">
                    <img src="https://i.postimg.cc/Zq7vjw8X/Screenshot_2026_01_17_at_6_56_59_pm.png" alt="RizzBot" class="project-image">
                    <div class="project-content">
                        <div class="project-header">
                            <h3 class="project-title">RizzBot</h3>
                            <span class="status-badge status-finished">● Finished</span>
                        </div>
                        <p class="project-description">
                            A fun Discord bot for those lacking charisma! Features commands like /rizz, /rizz random, and /rizz user to help users get a new partner or improve their game.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <div class="divider"></div>

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
                        <div class="terminal-line" style="margin-top: 10px;"></div>
                    </div>
                    <div class="terminal-input-line">
                        <span class="terminal-prompt" id="prompt">visitor@flimsyplank23:~$</span>
                        <input type="text" class="terminal-input" id="terminalInput" autofocus>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <div class="divider"></div>

    <section class="contact">
        <div class="container">
            <h2 class="contact-title">Feel like contacting me?</h2>
            <div class="contact-links">
                <a href="mailto:Flynn@thehanks.co.uk" class="contact-link">
                    <span>✉️</span> Flynn@thehanks.co.uk
                </a>
                <a href="https://github.com/Flimsyplank23" target="_blank" class="contact-link">
                    <span>📊</span> Flimsyplank23
                </a>
            </div>
        </div>
    </section>

    <script>
        const terminalInput = document.getElementById('terminalInput');
        const output = document.getElementById('output');
        const promptSpan = document.getElementById('prompt');
        let commandHistory = [];
        let historyIndex = -1;

        // --- IP BLOCKING SYSTEM & LOCK SYSTEM ---
        const ADMIN_PASSWORD = "flynn_is_best";
        let isBanned = localStorage.getItem('terminal_banned') === 'true';
        let isLocked = false;

        // Check ban status on load
        if (isBanned) {
            promptSpan.innerHTML = "🚫 BLOCKED@server:~$";
            promptSpan.classList.add('banned');
            setTimeout(() => {
                output.innerHTML += '<div class="terminal-line" style="color: #ff5f56; font-weight: bold;">⚠️ ACCESS DENIED: THIS TERMINAL HAS BEEN BLOCKED.</div>';
                output.innerHTML += '<div class="terminal-line" style="color: #ff5f56;">Type \'unblock [password]\' to restore access.</div>';
            }, 100);
        }

        const jokes = [
            "Why do programmers prefer dark mode? Because light attracts bugs! 🐛",
            "Why did the developer go broke? Because he used up all his cache! 💰",
            "How many programmers does it take to change a light bulb? None, that's a hardware problem! 💡",
            "Why do Java developers wear glasses? Because they don't C#! 👓",
            "What's a programmer's favorite hangout place? Foo Bar! 🍺",
            "Why did the programmer quit his job? Because he didn't get arrays! 📊"
        ];

        const facts = [
            "The first computer bug was an actual bug - a moth found in a computer in 1947! 🦋",
            "The password for the computer controls of nuclear missiles in the US was '00000000' for eight years! 😱",
            "The first 1GB hard drive, released in 1980, weighed over 500 pounds and cost $40,000! 💾",
            "More than 570 new websites are created every minute! 🌐",
            "The first computer mouse was made of wood! 🪵",
            "Python was named after Monty Python, not the snake! 🐍"
        ];

        // COMMANDS LIST
        const commands = {
            help: () => {
                return "🌟 AVAILABLE COMMANDS 🌟\n\n" +
                       "  help      - Show this menu\n" +
                       "  about     - Who is Flimsyplank23?\n" +
                       "  skills    - List technical skills\n" +
                       "  socials   - Display social links\n" +
                       "  joke      - Tell a random coding joke\n" +
                       "  fact      - Tell a random tech fact\n" +
                       "  goon      - 👹 Summon a Neko from the void\n" +
                       "  lock      - 🔒 Lock the terminal\n" +
                       "  banme     - 🚫 Block your own IP (Simulation)\n" +
                       "  clear     - Clear terminal screen";
            },
            about: () => "👋 Hi! I'm Flimsyplank23.\nI'm a software engineer, discord bot developer, and web enthusiast based in the UK.",
            skills: () => "💻 Tech Stack:\n- Python\n- HTML/CSS/JS\n- Discord.py\n- Web Development\n- Git/GitHub",
            socials: () => "🌐 Find me here:\n- GitHub: Flimsyplank23\n- Instagram: @flyingflynn12\n- TikTok: @flynn.planespotting",
            joke: () => jokes[Math.floor(Math.random() * jokes.length)],
            fact: () => facts[Math.floor(Math.random() * facts.length)],
            
            // THE GOON COMMAND - FETCHES IMAGE
            goon: async () => {
                try {
                    const response = await fetch('https://nekos.life/api/v2/img/neko');
                    const data = await response.json();
                    return `<div style="margin-top:10px;">
                                <div style="color: #ff5f56; margin-bottom: 5px;">👹 GOBLIN MODE ACTIVATED: Neko Summoned!</div>
                                <img src="${data.url}" alt="Random Neko" style="max-width: 300px; border-radius: 10px; border: 2px solid #ff5f56; box-shadow: 0 0 15px rgba(255, 95, 86, 0.3);">
                            </div>`;
                } catch (error) {
                    return `<span style="color: #ff5f56;">❌ Failed to summon: The Neko API is unavailable.</span>`;
                }
            },
            
            // LOCK COMMAND
            lock: () => {
                isLocked = true;
                promptSpan.innerHTML = "🔒 Password:";
                promptSpan.className = 'terminal-prompt locked';
                return "🔒 Terminal Locked. Enter password to unlock.";
            },

            // BLOCK COMMAND (SIMULATION)
            banme: () => {
                localStorage.setItem('terminal_banned', 'true');
                isBanned = true;
                promptSpan.innerHTML = "🚫 BLOCKED@server:~$";
                promptSpan.className = 'terminal-prompt banned';
                return "⚠️ SYSTEM ALERT: Your IP has been logged and blocked.\nConnection terminated.\nType 'unblock <password>' to restore access.";
            },

            // UNBLOCK COMMAND
            unblock: (args) => {
                // If not actually banned, just say so
                if (!isBanned) return "ℹ️ System Info: You are not currently blocked.";

                if (args[0] === ADMIN_PASSWORD) {
                    localStorage.removeItem('terminal_banned');
                    isBanned = false;
                    promptSpan.innerHTML = "visitor@flimsyplank23:~$";
                    promptSpan.classList.remove('banned');
                    return "✅ SUCCESS: IP Unblocked. Access restored.";
                } else {
                    return "❌ ERROR: Invalid Password. Access Denied.";
                }
            },
            
            clear: () => {
                output.innerHTML = '<div class="terminal-line">🎮 Welcome to Flimsyplank23 Fun Terminal! 🎮</div><div class="terminal-line">Type \'help\' to see fun commands</div><div class="terminal-line" style="margin-top: 10px;"></div>';
                return null;
            }
        };

        // History Navigation
        terminalInput.addEventListener('keydown', (e) => {
            if (e.key === 'ArrowUp') {
                e.preventDefault();
                if (commandHistory.length > 0 && historyIndex < commandHistory.length - 1) {
                    historyIndex++;
                    terminalInput.value = commandHistory[commandHistory.length - 1 - historyIndex];
                }
            } else if (e.key === 'ArrowDown') {
                e.preventDefault();
                if (historyIndex > 0) {
                    historyIndex--;
                    terminalInput.value = commandHistory[commandHistory.length - 1 - historyIndex];
                } else if (historyIndex === 0) {
                    historyIndex = -1;
                    terminalInput.value = '';
                }
            }
        });

        // Command Execution
        terminalInput.addEventListener('keypress', async (e) => {
            if (e.key === 'Enter') {
                const input = terminalInput.value.trim();
                
                // --- LOCK SYSTEM LOGIC ---
                if (isLocked) {
                    const commandLine = document.createElement('div');
                    commandLine.className = 'terminal-line';
                    // Mask the password in the output
                    commandLine.innerHTML = `<span class="terminal-prompt locked">🔒 Password:</span> ${'*'.repeat(input.length)}`;
                    output.appendChild(commandLine);

                    if (input === ADMIN_PASSWORD) {
                        isLocked = false;
                        promptSpan.innerHTML = "visitor@flimsyplank23:~$";
                        promptSpan.className = 'terminal-prompt';
                        
                        const msg = document.createElement('div');
                        msg.className = 'terminal-line';
                        msg.style.color = '#27c93f';
                        msg.textContent = "🔓 Access Granted. Terminal unlocked.";
                        output.appendChild(msg);
                    } else {
                        const msg = document.createElement('div');
                        msg.className = 'terminal-line';
                        msg.style.color = '#ff5f56';
                        msg.textContent = "❌ Access Denied.";
                        output.appendChild(msg);
                    }
                    terminalInput.value = '';
                    output.parentElement.scrollTop = output.parentElement.scrollHeight;
                    return; // Stop processing command
                }

                // --- STANDARD COMMAND LOGIC ---
                const parts = input.split(' ');
                const command = parts[0].toLowerCase();
                const args = parts.slice(1);
                
                const commandLine = document.createElement('div');
                commandLine.className = 'terminal-line';
                const promptHtml = isBanned ? 
                    `<span class="terminal-prompt banned">🚫 BLOCKED@server:~$</span>` : 
                    `<span class="terminal-prompt">visitor@flimsyplank23:~$</span>`;
                
                commandLine.innerHTML = `${promptHtml} ${terminalInput.value}`;
                output.appendChild(commandLine);

                if (input) {
                    commandHistory.push(input);
                    historyIndex = -1;

                    // --- BANNED LOGIC ---
                    if (isBanned && command !== 'unblock') {
                         const errorLine = document.createElement('div');
                         errorLine.className = 'terminal-line';
                         errorLine.style.color = '#ff5f56';
                         errorLine.textContent = `🚫 ACCESS DENIED: Terminal is blocked. Type 'unblock <password>' to unlock.`;
                         output.appendChild(errorLine);
                    } 
                    // --- NORMAL LOGIC ---
                    else if (commands[command]) {
                        // Show loading indicator
                        const loadingId = 'loading-' + Date.now();
                        const loadingLine = document.createElement('div');
                        loadingLine.className = 'terminal-line';
                        loadingLine.id = loadingId;
                        loadingLine.textContent = '...';
                        output.appendChild(loadingLine);
                        
                        try {
                            let result = await commands[command](args);
                            
                            const loader = document.getElementById(loadingId);
                            if (loader) loader.remove();

                            if (result) {
                                const resultLine = document.createElement('div');
                                resultLine.className = 'terminal-line';
                                resultLine.style.marginTop = '8px';
                                resultLine.innerHTML = result.replace(/\n/g, '<br>'); 
                                resultLine.style.color = (command === 'banme' || isBanned) ? '#ff5f56' : '#b0b0b0';
                                output.appendChild(resultLine);
                            }
                        } catch (err) {
                            const loader = document.getElementById(loadingId);
                            if (loader) loader.remove();
                            console.error(err);
                        }
                    } else {
                        const errorLine = document.createElement('div');
                        errorLine.className = 'terminal-line';
                        errorLine.style.color = '#ff5f56';
                        errorLine.textContent = `❌ Command not found: ${command}. Type 'help' for fun commands!`;
                        output.appendChild(errorLine);
                    }
                }

                const spacer = document.createElement('div');
                spacer.className = 'terminal-line';
                spacer.style.marginTop = '10px';
                output.appendChild(spacer);

                terminalInput.value = '';
                output.parentElement.scrollTop = output.parentElement.scrollHeight;
            }
        });

        // Keep focus on terminal input
        document.querySelector('.terminal-body').addEventListener('click', () => {
            terminalInput.focus();
        });
    </script>
</body>
</html>
