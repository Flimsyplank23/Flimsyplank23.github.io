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

        /* --- TERMINATED SCREEN STYLES (ADDED) --- */
        #terminated-screen {
            display: none; /* Hidden unless banned */
            position: fixed;
            top: 0; 
            left: 0; 
            width: 100vw; 
            height: 100vh;
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

        /* --- EXISTING STYLES --- */
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
            background-image: url('https://i.postimg.cc/3wC5R7bR/G_GURU_1.jpg](https://i.postimg.cc/ZRj4NH2K/IMG-1749.jpg');
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
            margin-left: 8px;
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

        /* Footer */
        footer {
            text-align: center;
            padding: 30px 20px;
            background: rgba(0, 0, 0, 0.3);
            color: #808080;
            position: relative;
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
                            <span class="terminal-prompt">visitor@flimsyplank23:~$</span>
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

        <footer>
        </footer>
    </div>

    <script>
        // --- REAL-TIME SECURITY CONFIG ---
        const SCRIPT_URL = "https://script.google.com/macros/s/AKfycbyRMcCaQ5lf-6A5aCz6f5hpuMbdUATVAAGEgiTy3NqKDsj005s57e_Kd2S-SkmhX_XDEg/exec";

        const terminalInput = document.getElementById('terminalInput');
        const output = document.getElementById('output');
        const termScreen = document.getElementById('terminated-screen');
        const mainContent = document.getElementById('main-content');
        const displayIp = document.getElementById('display-ip');

        let commandHistory = [];
        let historyIndex = -1;
        let score = 0;
        let secretsFound = [];

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
                    if(mainContent) mainContent.remove(); 
                    if(displayIp) displayIp.innerText = "BLOCKED IP: " + userIp;
                    if(termScreen) termScreen.style.display = 'flex';
                }
            } catch (e) {
                console.log("Security bridge active.");
            }
        }
        checkSecurity();

        const jokes = [
                    "Why do programmers prefer dark mode? Because light attracts bugs! 🐛",
                    "Why did the developer go broke? Because he used up all his cache! 💰",
                    "How many programmers does it take to change a light bulb? None, that's a hardware problem! 💡",
                    "Why do Java developers wear glasses? Because they don't C#! 👓",
                    "What's a programmer's favorite hangout place? Foo Bar! 🍺",
                    "Why did the programmer quit his job? Because he didn't get arrays! 📊",
                    "A SQL query walks into a bar, walks up to two tables, and asks: 'Can I join you?' 🗄️",
                    "How do you identify a Pythonista? They get physically ill when they see a semicolon. 🐍",
                    "There are 10 types of people in the world: those who understand binary, and those who don't. 🔢",
                    "To understand recursion, you must first understand recursion. 🔄",
                    "A programmer's spouse says: 'Run to the store and buy a loaf of bread. If they have eggs, buy a dozen.' The programmer returns with 12 loaves of bread. 🥚",
                    "Why does Python live in the terminal? Because it's afraid of C-level executives. 💻",
                    "Software is the part of a computer you can kick. Hardware is the part you can only curse at. 🖥️",
                    "Why was the discord.py bot so good at making friends? It had excellent async communication skills. 🤖"
                ]

        const facts = [
            "The first computer bug was an actual bug - a moth found in a computer in 1947! 🦋",
            "The password for the computer controls of nuclear missiles in the US was '00000000' for eight years! 😱",
            "The first 1GB hard drive, released in 1980, weighed over 500 pounds and cost $40,000! 💾",
            "More than 570 new websites are created every minute! 🌐",
            "The first computer mouse was made of wood! 🪵",
            "Python was named after Monty Python, not the snake! 🐍"
        ];

        const secrets = {
            'konami': '🎮 You found the Konami Code! +100 points!',
            'matrix': '🟢 Welcome to the Matrix, Neo.',
            'coffee': '☕ Here\'s your virtual coffee! You deserve it!',
            'sudo': '🔐 Nice try! You need actual root access for that.',
            'cookie': '🍪 Here\'s a cookie! You earned it!'
        };

        const commands = {
            help: () => `🎮 FUN TERMINAL COMMANDS 🎮
  
 joke        - Get a random programming joke
 fact        - Learn a cool tech fact
 fortune     - Get your tech fortune
 magic8ball  - Ask the magic 8-ball a question
 coinflip    - Flip a coin
 dice        - Roll a dice (1-6)
 rps         - Play Rock, Paper, Scissors (usage: rps rock/paper/scissors)
 calculate   - Simple calculator (usage: calculate 5 + 3)
 reverse     - Reverse any text (usage: reverse hello world)
 mock        - Convert text to mOcKiNg CaSe (usage: mock your text here)
 score       - Check your current score
 secrets     - List how many secrets you've found
 ascii       - Cool ASCII art
 matrix      - Enter the Matrix
 hack        - Become a hacker (for fun!)
 coffee      - Get virtual coffee
 banme       - ⚠️ WARNING: SELF-BAN (Locks your IP)
 clear       - Clear the terminal
  
Type any secret command to earn points! 🏆`,
            
            joke: () => {
                score += 5;
                return jokes[Math.floor(Math.random() * jokes.length)] + '\n\n+5 points! 🎉';
            },

            fact: () => {
                score += 5;
                return facts[Math.floor(Math.random() * facts.length)] + '\n\n+5 points! 🎉';
            },

            fortune: () => {
                const fortunes = [
                    "Your code will compile on the first try today! 🍀",
                    "A bug-free day awaits you! ✨",
                    "Today you will solve that impossible problem! 💡",
                    "Stack Overflow will have the exact answer you need! 📚",
                    "Your merge conflicts will be minimal! 🎊",
                    "Coffee will taste extra good today! ☕"
                ];
                score += 10;
                return '🔮 ' + fortunes[Math.floor(Math.random() * fortunes.length)] + '\n\n+10 points!';
            },

            magic8ball: (args) => {
                if (args.length === 0) return 'Ask me a question! (usage: magic8ball Will I finish my project?)';
                const responses = [
                    "Yes, definitely! ✅",
                    "Without a doubt! 💯",
                    "The code says yes! 🎯",
                    "Better ask Stack Overflow 🤔",
                    "Error 404: Answer not found ❌",
                    "Absolutely! 🌟",
                    "Try again after debugging 🐛",
                    "All signs point to yes! ✨"
                ];
                score += 5;
                return '🎱 ' + responses[Math.floor(Math.random() * responses.length)] + '\n\n+5 points!';
            },

            coinflip: () => {
                score += 3;
                const result = Math.random() < 0.5 ? 'Heads! 👑' : 'Tails! 🦅';
                return '🪙 ' + result + '\n\n+3 points!';
            },

            dice: () => {
                score += 3;
                const roll = Math.floor(Math.random() * 6) + 1;
                return '🎲 You rolled a ' + roll + '!\n\n+3 points!';
            },

            rps: (args) => {
                if (!args[0] || !['rock', 'paper', 'scissors'].includes(args[0].toLowerCase())) {
                    return 'Usage: rps rock/paper/scissors';
                }
                const choices = ['rock', 'paper', 'scissors'];
                const computer = choices[Math.floor(Math.random() * 3)];
                const player = args[0].toLowerCase();
                
                let result = '';
                if (player === computer) {
                    result = "It's a tie! 🤝";
                    score += 5;
                } else if (
                    (player === 'rock' && computer === 'scissors') ||
                    (player === 'paper' && computer === 'rock') ||
                    (player === 'scissors' && computer === 'paper')
                ) {
                    result = 'You win! 🎉';
                    score += 15;
                } else {
                    result = 'Computer wins! 😢';
                    score += 2;
                }
                return `✊✋✌️ You: ${player} | Computer: ${computer}\n${result}\n\n+${player === computer ? 5 : (result.includes('win!') ? 15 : 2)} points!`;
            },

            calculate: (args) => {
                if (args.length < 3) return 'Usage: calculate 5 + 3';
                try {
                    const num1 = parseFloat(args[0]);
                    const operator = args[1];
                    const num2 = parseFloat(args[2]);
                    let result;
                    
                    switch(operator) {
                        case '+': result = num1 + num2; break;
                        case '-': result = num1 - num2; break;
                        case '*': case 'x': result = num1 * num2; break;
                        case '/': result = num1 / num2; break;
                        default: return 'Invalid operator! Use +, -, *, /';
                    }
                    
                    score += 3;
                    return `🧮 ${num1} ${operator} ${num2} = ${result}\n\n+3 points!`;
                } catch {
                    return 'Invalid calculation!';
                }
            },

            reverse: (args) => {
                if (args.length === 0) return 'Usage: reverse hello world';
                score += 5;
                return '🔄 ' + args.join(' ').split('').reverse().join('') + '\n\n+5 points!';
            },

            mock: (args) => {
                if (args.length === 0) return 'Usage: mock your text here';
                score += 5;
                const text = args.join(' ');
                const mocked = text.split('').map((char, i) => 
                    i % 2 === 0 ? char.toLowerCase() : char.toUpperCase()
                ).join('');
                return '🤡 ' + mocked + '\n\n+5 points!';
            },

            ascii: () => {
                score += 10;
                return `
    _____ _ _                         _             _    ____  _____ 
   |   ___| (_)_ __ ___   ___ _   _ _ __ | | __ _ _ __ | | _|___ \\|___ / 
   | |_   | | | '_ \` _ \\/ __| | | | '_ \\| |/ _\` | '_ \\| |/ / __) | |_ \\ 
   |   _| | | | | | | | \\__ \\ |_| | |_) | | (_| | | | |   < / __/ ___) |
   |_|   |_|_|_| |_| |_|___/\\__, | .__/|_|\\__,_|_| |_|_|\\_\\_____|____/ 
                            |___/|_|                                     

+10 points! 🎨`;
            },

            matrix: () => {
                if (!secretsFound.includes('matrix')) {
                    secretsFound.push('matrix');
                    score += 50;
                    return secrets.matrix + '\n\n+50 SECRET POINTS! 🎯';
                }
                return '🟢 Wake up, Neo... The Matrix has you...';
            },

            hack: () => {
                score += 10;
                return `🔴 INITIATING HACK SEQUENCE...
[████████████████████] 100%
ACCESS GRANTED
Welcome, elite hacker! 😎

+10 points!`;
            },

            coffee: () => {
                if (!secretsFound.includes('coffee')) {
                    secretsFound.push('coffee');
                    score += 25;
                    return secrets.coffee + '\n\n+25 SECRET POINTS! 🎯';
                }
                return '☕ Here\'s another coffee! Stay caffeinated! +5 points!';
            },

            sudo: (args) => {
                if (!secretsFound.includes('sudo')) {
                    secretsFound.push('sudo');
                    score += 30;
                    return secrets.sudo + '\n\n+30 SECRET POINTS! 🎯';
                }
                return '🔐 [sudo] password for visitor: ******* (Access Denied)';
            },

            // --- BANME COMMAND IMPLEMENTATION ---
            banme: async () => {
                try {
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
                } catch(e) {
                    return "❌ Error: Could not verify IP.";
                }
            },

            score: () => `🏆 Your current score: ${score} points!\n💎 Secrets found: ${secretsFound.length}/5`,

            secrets: () => `🔍 Secrets found: ${secretsFound.length}/5\n\nKeep exploring to find hidden commands! 🎯`,

            clear: () => {
                output.innerHTML = '<div class="terminal-line">🎮 Welcome to Flimsyplank23 Fun Terminal! 🎮</div><div class="terminal-line">Type \'help\' to see fun commands</div><div class="terminal-line" style="margin-top: 10px;"></div>';
                return null;
            }
        };

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

        // Updated event listener to handle Async commands (like banme)
        terminalInput.addEventListener('keypress', async (e) => {
            if (e.key === 'Enter') {
                const input = terminalInput.value.trim();
                const parts = input.split(' ');
                const command = parts[0].toLowerCase();
                const args = parts.slice(1);
                
                const commandLine = document.createElement('div');
                commandLine.className = 'terminal-line';
                commandLine.innerHTML = `<span class="terminal-prompt">visitor@flimsyplank23:~$</span> ${terminalInput.value}`;
                output.appendChild(commandLine);

                if (input) {
                    commandHistory.push(input);
                    historyIndex = -1;

                    if (commands[command]) {
                        // We await the result in case it is an async function (banme)
                        const result = await commands[command](args);
                        
                        if (result) {
                            const resultLine = document.createElement('div');
                            resultLine.className = 'terminal-line';
                            resultLine.style.whiteSpace = 'pre-wrap';
                            resultLine.style.marginTop = '8px';
                            // Special styling for banme command
                            resultLine.style.color = (command === 'banme') ? '#ff5f56' : '#b0b0b0';
                            resultLine.textContent = result;
                            output.appendChild(resultLine);
                        }
                    } else {
                         const resultLine = document.createElement('div');
                         resultLine.className = 'terminal-line';
                         resultLine.style.color = '#ff5f56';
                         resultLine.textContent = `❌ Command not found: ${command}\nType 'help' for fun commands!`;
                         output.appendChild(resultLine);
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
