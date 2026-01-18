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
        }

        .terminal-output {
            margin-bottom: 20px;
            color: #b0b0b0;
        }

        .terminal-line {
            margin-bottom: 8px;
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

        /* Music Player */
        .music-player {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: rgba(26, 26, 46, 0.95);
            border: 2px solid #00d9ff;
            border-radius: 50px;
            padding: 12px 20px;
            display: flex;
            align-items: center;
            gap: 12px;
            z-index: 1000;
            backdrop-filter: blur(10px);
            box-shadow: 0 8px 32px rgba(0, 217, 255, 0.3);
        }

        .music-toggle {
            background: transparent;
            border: none;
            color: #00d9ff;
            font-size: 24px;
            cursor: pointer;
            transition: all 0.3s ease;
            padding: 0;
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .music-toggle:hover {
            transform: scale(1.2);
            color: #00ffa3;
        }

        .music-info {
            color: #b0b0b0;
            font-size: 0.9rem;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .music-visualizer {
            display: flex;
            gap: 3px;
            align-items: flex-end;
            height: 20px;
        }

        .music-visualizer span {
            width: 3px;
            background: #00d9ff;
            animation: visualize 0.6s ease-in-out infinite;
            border-radius: 2px;
        }

        .music-visualizer span:nth-child(1) { animation-delay: 0s; }
        .music-visualizer span:nth-child(2) { animation-delay: 0.1s; }
        .music-visualizer span:nth-child(3) { animation-delay: 0.2s; }
        .music-visualizer span:nth-child(4) { animation-delay: 0.3s; }

        @keyframes visualize {
            0%, 100% { height: 5px; }
            50% { height: 20px; }
        }

        .music-visualizer.paused span {
            animation: none;
            height: 5px;
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
    <!-- Hero Section -->
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
                <div class="skill-badge">Discord.js</div>
                <div class="skill-badge">Web Development</div>
            </div>
        </div>
    </section>

    <div class="divider"></div>

    <!-- Projects Section -->
    <section class="section">
        <div class="container">
            <h2 class="section-title">Projects</h2>
            <div class="projects-grid">
                <!-- GTAMEN Website -->
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

                <!-- GTAMEN Discord Bot -->
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

                <!-- Algebra Adventure -->
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

                <!-- Chat Website -->
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

                <!-- Ahmed Academy Physics -->
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

                <!-- RizzBot -->
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

    <!-- Terminal Section -->
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

    <!-- Contact Section -->
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

    <!-- Footer -->
    <footer>
    </footer>

    <!-- Music Player -->
    <div class="music-player">
        <button class="music-toggle" id="musicToggle">▶️</button>
        <div class="music-info">
            <div class="music-visualizer paused" id="visualizer">
                <span></span>
                <span></span>
                <span></span>
                <span></span>
            </div>
            <span id="musicStatus">Click to play music</span>
        </div>
    </div>

    <audio id="bgMusic" loop>
        <source src="background-music.mp3" type="audio/mpeg">
    </audio>

    <script>
        const terminalInput = document.getElementById('terminalInput');
        const output = document.getElementById('output');
        let commandHistory = [];
        let historyIndex = -1;
        let score = 0;
        let secretsFound = [];

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
    _____ _ _                            _             _    ____  _____ 
   |  ___| (_)_ __ ___  ___ _   _ _ __ | | __ _ _ __ | | _|___ \\|___ / 
   | |_  | | | '_ \` _ \\/ __| | | | '_ \\| |/ _\` | '_ \\| |/ / __) | |_ \\ 
   |  _| | | | | | | | \\__ \\ |_| | |_) | | (_| | | | |   < / __/ ___) |
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

        terminalInput.addEventListener('keypress', (e) => {
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

                    const result = commands[command] ? commands[command](args) : `❌ Command not found: ${command}\nType 'help' for fun commands!`;
                    if (result) {
                        const resultLine = document.createElement('div');
                        resultLine.className = 'terminal-line';
                        resultLine.style.whiteSpace = 'pre-wrap';
                        resultLine.style.marginTop = '8px';
                        resultLine.textContent = result;
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

        // Music Player
        const musicToggle = document.getElementById('musicToggle');
        const bgMusic = document.getElementById('bgMusic');
        const musicStatus = document.getElementById('musicStatus');
        const visualizer = document.getElementById('visualizer');
        let isPlaying = false;

        musicToggle.addEventListener('click', () => {
            if (isPlaying) {
                bgMusic.pause();
                musicToggle.textContent = '▶️';
                musicStatus.textContent = 'Click to play music';
                visualizer.classList.add('paused');
                isPlaying = false;
            } else {
                bgMusic.play().then(() => {
                    musicToggle.textContent = '⏸️';
                    musicStatus.textContent = 'Now playing...';
                    visualizer.classList.remove('paused');
                    isPlaying = true;
                }).catch((error) => {
                    console.error('Audio play failed:', error);
                    musicStatus.textContent = 'Failed to load audio';
                    alert('Could not play audio. Please make sure "background-music.mp3" is uploaded to your repository.');
                });
            }
        });

        // Check if audio file exists
        bgMusic.addEventListener('error', (e) => {
            console.error('Audio file error:', e);
            musicStatus.textContent = 'Audio file not found';
        });

        bgMusic.addEventListener('loadeddata', () => {
            console.log('Audio file loaded successfully');
        });

        // Set volume to 30% by default
        bgMusic.volume = 0.3;
    </script>
</body>
</html>
