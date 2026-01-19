<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>flimsyplank23 | Terminal</title>
    <style>
        :root {
            --bg-color: #0d0d0d;
            --text-color: #00ff41;
            --prompt-color: #ff00ff;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            font-family: 'Courier New', Courier, monospace;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
        }

        .terminal {
            width: 80%;
            max-width: 800px;
            height: 60vh;
            background: rgba(0, 0, 0, 0.9);
            border: 2px solid var(--text-color);
            box-shadow: 0 0 20px rgba(0, 255, 65, 0.2);
            display: flex;
            flex-direction: column;
            padding: 20px;
        }

        .terminal-header {
            border-bottom: 1px solid var(--text-color);
            padding-bottom: 10px;
            margin-bottom: 10px;
            font-weight: bold;
        }

        .terminal-body {
            flex-grow: 1;
            overflow-y: auto;
            margin-bottom: 10px;
        }

        .terminal-input-area {
            display: flex;
            align-items: center;
        }

        .terminal-prompt {
            color: var(--prompt-color);
            margin-right: 10px;
        }

        #terminalInput {
            background: transparent;
            border: none;
            color: var(--text-color);
            font-family: inherit;
            font-size: 1rem;
            outline: none;
            flex-grow: 1;
        }

        .terminal-line { margin: 5px 0; line-height: 1.4; }
        
        .terminal-body::-webkit-scrollbar { width: 8px; }
        .terminal-body::-webkit-scrollbar-thumb { background: var(--text-color); }
    </style>
</head>
<body>

    <div class="terminal">
        <div class="terminal-header">flimsyplank23 - OS v1.0.0</div>
        <div class="terminal-body" id="output">
            <div class="terminal-line">Welcome back, visitor.</div>
            <div class="terminal-line">Type 'help' to see available commands.</div>
        </div>
        <div class="terminal-input-area">
            <span class="terminal-prompt">visitor@flimsyplank23:~$</span>
            <input type="text" id="terminalInput" autofocus autocomplete="off">
        </div>
    </div>

    <script>
        const output = document.getElementById('output');
        const terminalInput = document.getElementById('terminalInput');
        
        let score = 0;
        let secretsFound = [];
        let commandHistory = [];
        let historyIndex = -1;

        const secrets = {
            'konami': "⬆️⬆️⬇️⬇️⬅️➡️⬅️➡️ B A START: God Mode Enabled (Just kidding, but here's some points!)",
            'cookie': "🍪 Om nom nom! You found the hidden cookie."
        };

        const commands = {
            'help': () => `
Available Commands:
- about: Learn about me
- stack: My coding languages (Updated to discord.py!)
- joke: Get a random dev joke
- clear: Clear the terminal
- status: Check your secret hunter score`,
            
            'about': () => "I'm flimsyplank23. A developer exploring the digital void.",
            
            'stack': () => "Primary Stack: Python (discord.py), HTML/CSS, JavaScript.",
            
            'joke': () => {
                const jokes = [
                    "Why do programmers prefer dark mode? Because light attracts bugs.",
                    "Real programmers count from 0.",
                    "A SQL query walks into a bar, walks up to two tables, and asks: 'Can I join you?'"
                ];
                return jokes[Math.floor(Math.random() * jokes.length)];
            },

            'status': () => `Score: ${score} | Secrets Found: ${secretsFound.length > 0 ? secretsFound.join(', ') : 'None'}`,

            'clear': () => {
                output.innerHTML = '';
                return null;
            }
        };

        terminalInput.addEventListener('keydown', (e) => {
            if (e.key === 'Enter') {
                const rawInput = terminalInput.value;
                const input = rawInput.trim();
                const parts = input.split(' ');
                const command = parts[0].toLowerCase();
                const args = parts.slice(1);
                
                const commandLine = document.createElement('div');
                commandLine.className = 'terminal-line';
                commandLine.innerHTML = `<span class="terminal-prompt">visitor@flimsyplank23:~$</span> ${rawInput}`;
                output.appendChild(commandLine);

                if (input) {
                    commandHistory.push(input);
                    historyIndex = -1;

                    let result = "";

                    if (commands[command]) {
                        result = commands[command](args);
                    } else if (secrets[command]) {
                        if (!secretsFound.includes(command)) {
                            secretsFound.push(command);
                            score += 50;
                            result = `${secrets[command]}\n\n+50 SECRET POINTS! 🎯`;
                        } else {
                            result = `${secrets[command]}\n(You already found this secret!)`;
                        }
                    } else {
                        result = `❌ Command not found: ${command}\nType 'help' for available commands.`;
                    }

                    if (result) {
                        const resultLine = document.createElement('div');
                        resultLine.className = 'terminal-line';
                        resultLine.style.whiteSpace = 'pre-wrap';
                        resultLine.style.marginTop = '8px';
                        resultLine.textContent = result;
                        output.appendChild(resultLine);
                    }
                }

                terminalInput.value = '';
                const terminalBody = document.querySelector('.terminal-body');
                terminalBody.scrollTop = terminalBody.scrollHeight;
            }
        });

        document.querySelector('.terminal').addEventListener('click', () => {
            terminalInput.focus();
        });
    </script>
</body>
</html>
