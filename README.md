<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tajawaz Solutions - GitHub Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Consolas', 'Monaco', monospace;
            background: #0a0e27;
            color: #e0e0e0;
            overflow-x: hidden;
        }

        /* Animated Background */
        .matrix-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            opacity: 0.1;
        }

        .container {
            position: relative;
            z-index: 1;
            max-width: 900px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        /* Header Animation */
        header {
            text-align: center;
            margin-bottom: 60px;
            animation: fadeInDown 1s ease;
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        h1 {
            font-size: 3em;
            color: #5f2ded;
            margin-bottom: 10px;
            text-shadow: 0 0 20px rgba(95, 45, 237, 0.5);
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from {
                text-shadow: 0 0 10px rgba(95, 45, 237, 0.5);
            }
            to {
                text-shadow: 0 0 30px rgba(95, 45, 237, 0.8);
            }
        }

        .typing-text {
            font-size: 1.3em;
            color: #a0a0a0;
            border-right: 3px solid #5f2ded;
            padding-right: 5px;
            white-space: nowrap;
            overflow: hidden;
            display: inline-block;
            animation: typing 3s steps(40) infinite, blink 0.7s infinite;
        }

        @keyframes typing {
            0%, 100% { width: 0; }
            50% { width: 100%; }
        }

        @keyframes blink {
            50% { border-color: transparent; }
        }

        /* Terminal Style Card */
        .terminal-card {
            background: rgba(20, 20, 40, 0.8);
            border: 2px solid #5f2ded;
            border-radius: 10px;
            padding: 20px;
            margin-bottom: 30px;
            box-shadow: 0 0 30px rgba(95, 45, 237, 0.3);
            animation: slideIn 0.8s ease;
            position: relative;
            overflow: hidden;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .terminal-header {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px solid #5f2ded;
        }

        .terminal-dots {
            display: flex;
            gap: 8px;
        }

        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            animation: pulse 2s infinite;
        }

        .dot:nth-child(1) { background: #ff5f57; animation-delay: 0s; }
        .dot:nth-child(2) { background: #ffbd2e; animation-delay: 0.2s; }
        .dot:nth-child(3) { background: #28c840; animation-delay: 0.4s; }

        @keyframes pulse {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.5; transform: scale(0.9); }
        }

        .terminal-title {
            margin-left: 15px;
            color: #5f2ded;
            font-weight: bold;
        }

        /* Code Block Animation */
        .code-block {
            background: rgba(10, 10, 30, 0.5);
            padding: 20px;
            border-radius: 8px;
            border-left: 4px solid #5f2ded;
            margin: 20px 0;
            font-family: 'Courier New', monospace;
            position: relative;
        }

        .code-line {
            margin: 8px 0;
            opacity: 0;
            animation: fadeInLine 0.5s ease forwards;
        }

        .code-line:nth-child(1) { animation-delay: 0.1s; }
        .code-line:nth-child(2) { animation-delay: 0.2s; }
        .code-line:nth-child(3) { animation-delay: 0.3s; }
        .code-line:nth-child(4) { animation-delay: 0.4s; }
        .code-line:nth-child(5) { animation-delay: 0.5s; }
        .code-line:nth-child(6) { animation-delay: 0.6s; }

        @keyframes fadeInLine {
            to {
                opacity: 1;
            }
        }

        .keyword { color: #ff79c6; }
        .string { color: #50fa7b; }
        .number { color: #bd93f9; }
        .comment { color: #6272a4; font-style: italic; }

        /* Dropdown Section */
        .dropdown-section {
            margin: 30px 0;
        }

        .dropdown-header {
            background: linear-gradient(135deg, #5f2ded 0%, #7e3ff2 100%);
            padding: 15px 20px;
            cursor: pointer;
            border-radius: 8px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: all 0.3s ease;
            user-select: none;
        }

        .dropdown-header:hover {
            transform: translateX(5px);
            box-shadow: 0 5px 20px rgba(95, 45, 237, 0.4);
        }

        .dropdown-icon {
            font-size: 1.5em;
            transition: transform 0.3s ease;
        }

        .dropdown-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s ease, padding 0.3s ease;
            padding: 0 20px;
        }

        .dropdown-content.active {
            max-height: 1000px;
            padding: 20px;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin-top: 15px;
        }

        .tech-item {
            background: rgba(95, 45, 237, 0.1);
            padding: 12px;
            border-radius: 8px;
            text-align: center;
            border: 1px solid rgba(95, 45, 237, 0.3);
            transition: all 0.3s ease;
            opacity: 0;
            animation: popIn 0.5s ease forwards;
        }

        .tech-item:nth-child(1) { animation-delay: 0.1s; }
        .tech-item:nth-child(2) { animation-delay: 0.15s; }
        .tech-item:nth-child(3) { animation-delay: 0.2s; }
        .tech-item:nth-child(4) { animation-delay: 0.25s; }
        .tech-item:nth-child(5) { animation-delay: 0.3s; }
        .tech-item:nth-child(6) { animation-delay: 0.35s; }

        @keyframes popIn {
            from {
                opacity: 0;
                transform: scale(0.5) rotate(-5deg);
            }
            to {
                opacity: 1;
                transform: scale(1) rotate(0deg);
            }
        }

        .tech-item:hover {
            transform: translateY(-5px) scale(1.05);
            background: rgba(95, 45, 237, 0.2);
            border-color: #5f2ded;
            box-shadow: 0 5px 20px rgba(95, 45, 237, 0.3);
        }

        .tech-icon {
            font-size: 2em;
            margin-bottom: 8px;
        }

        /* Project Cards */
        .project-card {
            background: rgba(20, 20, 40, 0.6);
            padding: 20px;
            border-radius: 10px;
            border-left: 4px solid #5f2ded;
            margin: 15px 0;
            transition: all 0.3s ease;
            animation: slideInRight 0.8s ease;
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .project-card:hover {
            transform: translateX(10px);
            box-shadow: -5px 5px 30px rgba(95, 45, 237, 0.3);
            border-left-width: 8px;
        }

        .project-title {
            color: #5f2ded;
            font-size: 1.3em;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-top: 10px;
        }

        .tag {
            background: rgba(95, 45, 237, 0.2);
            padding: 4px 12px;
            border-radius: 15px;
            font-size: 0.85em;
            border: 1px solid rgba(95, 45, 237, 0.4);
        }

        /* Social Links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 40px 0;
            flex-wrap: wrap;
        }

        .social-btn {
            background: linear-gradient(135deg, #5f2ded 0%, #7e3ff2 100%);
            color: white;
            padding: 12px 25px;
            border-radius: 25px;
            text-decoration: none;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            box-shadow: 0 4px 15px rgba(95, 45, 237, 0.3);
        }

        .social-btn:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 8px 25px rgba(95, 45, 237, 0.5);
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 30px 0;
            color: #6272a4;
            animation: fadeIn 2s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .heart {
            color: #ff79c6;
            animation: heartbeat 1.5s infinite;
            display: inline-block;
        }

        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.2); }
        }

        /* Floating Particles */
        .particle {
            position: fixed;
            width: 4px;
            height: 4px;
            background: #5f2ded;
            border-radius: 50%;
            pointer-events: none;
            opacity: 0;
            animation: float 4s infinite;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) scale(0);
                opacity: 0;
            }
            50% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) scale(1);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <canvas class="matrix-bg" id="matrix"></canvas>

    <div class="container">
        <header>
            <h1>👨‍💻 TAJAWAZ SOLUTIONS</h1>
            <div class="typing-text">Full Stack Developer | Vibe Coding Enthusiast</div>
        </header>

        <!-- About Section -->
        <div class="terminal-card">
            <div class="terminal-header">
                <div class="terminal-dots">
                    <div class="dot"></div>
                    <div class="dot"></div>
                    <div class="dot"></div>
                </div>
                <div class="terminal-title">tajawaz@solutions:~$ whoami</div>
            </div>
            <div class="code-block">
                <div class="code-line"><span class="keyword">const</span> developer = {</div>
                <div class="code-line">  name: <span class="string">"Tajawaz Solutions"</span>,</div>
                <div class="code-line">  website: <span class="string">"www.tajawaz.my.id"</span>,</div>
                <div class="code-line">  location: <span class="string">"Parung, West Java 🇮🇩"</span>,</div>
                <div class="code-line">  passion: <span class="string">"Vibe Coding & Innovation"</span>,</div>
                <div class="code-line">  status: <span class="string">"Building the future ✨"</span></div>
                <div class="code-line">};</div>
            </div>
        </div>

        <!-- Tech Stack Dropdown -->
        <div class="dropdown-section">
            <div class="dropdown-header" onclick="toggleDropdown('frontend')">
                <span>💻 Frontend Technologies</span>
                <span class="dropdown-icon" id="icon-frontend">▼</span>
            </div>
            <div class="dropdown-content" id="content-frontend">
                <div class="tech-grid">
                    <div class="tech-item">
                        <div class="tech-icon">⚛️</div>
                        <div>React</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">▲</div>
                        <div>Next.js</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">💚</div>
                        <div>Vue.js</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">🔷</div>
                        <div>TypeScript</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">🎨</div>
                        <div>Tailwind CSS</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">💎</div>
                        <div>SASS</div>
                    </div>
                </div>
            </div>
        </div>

        <div class="dropdown-section">
            <div class="dropdown-header" onclick="toggleDropdown('backend')">
                <span>⚙️ Backend Technologies</span>
                <span class="dropdown-icon" id="icon-backend">▼</span>
            </div>
            <div class="dropdown-content" id="content-backend">
                <div class="tech-grid">
                    <div class="tech-item">
                        <div class="tech-icon">🟢</div>
                        <div>Node.js</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">🚂</div>
                        <div>Express</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">🐍</div>
                        <div>Python</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">🐘</div>
                        <div>PHP</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">🔥</div>
                        <div>FastAPI</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">🎸</div>
                        <div>Django</div>
                    </div>
                </div>
            </div>
        </div>

        <div class="dropdown-section">
            <div class="dropdown-header" onclick="toggleDropdown('database')">
                <span>🗄️ Database & Storage</span>
                <span class="dropdown-icon" id="icon-database">▼</span>
            </div>
            <div class="dropdown-content" id="content-database">
                <div class="tech-grid">
                    <div class="tech-item">
                        <div class="tech-icon">🍃</div>
                        <div>MongoDB</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">🐘</div>
                        <div>PostgreSQL</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">🐬</div>
                        <div>MySQL</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">🔥</div>
                        <div>Firebase</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">⚡</div>
                        <div>Redis</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">🚀</div>
                        <div>Supabase</div>
                    </div>
                </div>
            </div>
        </div>

        <div class="dropdown-section">
            <div class="dropdown-header" onclick="toggleDropdown('tools')">
                <span>🛠️ Tools & DevOps</span>
                <span class="dropdown-icon" id="icon-tools">▼</span>
            </div>
            <div class="dropdown-content" id="content-tools">
                <div class="tech-grid">
                    <div class="tech-item">
                        <div class="tech-icon">📦</div>
                        <div>Git</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">🐳</div>
                        <div>Docker</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">💻</div>
                        <div>VS Code</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">🎨</div>
                        <div>Figma</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">☁️</div>
                        <div>AWS</div>
                    </div>
                    <div class="tech-item">
                        <div class="tech-icon">▲</div>
                        <div>Vercel</div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Featured Projects -->
        <div class="terminal-card">
            <div class="terminal-header">
                <div class="terminal-dots">
                    <div class="dot"></div>
                    <div class="dot"></div>
                    <div class="dot"></div>
                </div>
                <div class="terminal-title">tajawaz@solutions:~$ ls projects/</div>
            </div>

            <div class="project-card">
                <div class="project-title">🌟 Project Alpha</div>
                <p>Modern e-commerce platform with cutting-edge features</p>
                <div class="project-tags">
                    <span class="tag">React</span>
                    <span class="tag">TypeScript</span>
                    <span class="tag">Tailwind</span>
                    <span class="tag">Firebase</span>
                </div>
            </div>

            <div class="project-card">
                <div class="project-title">🎨 Project Beta</div>
                <p>AI-powered design tool with real-time collaboration</p>
                <div class="project-tags">
                    <span class="tag">Next.js</span>
                    <span class="tag">OpenAI</span>
                    <span class="tag">PostgreSQL</span>
                </div>
            </div>

            <div class="project-card">
                <div class="project-title">🌐 Project Gamma</div>
                <p>Social media dashboard with advanced analytics</p>
                <div class="project-tags">
                    <span class="tag">Vue.js</span>
                    <span class="tag">Node.js</span>
                    <span class="tag">MongoDB</span>
                </div>
            </div>
        </div>

        <!-- Social Links -->
        <div class="social-links">
            <a href="https://www.tajawaz.my.id" class="social-btn">🌐 Website</a>
            <a href="mailto:contact@tajawaz.my.id" class="social-btn">📧 Email</a>
            <a href="https://github.com/YOUR_USERNAME" class="social-btn">💻 GitHub</a>
            <a href="https://linkedin.com/in/YOUR_LINKEDIN" class="social-btn">💼 LinkedIn</a>
        </div>

        <footer>
            <p>💜 "Code with purpose, design with soul"</p>
            <p>Made with <span class="heart">❤️</span> by Tajawaz Solutions</p>
            <p>© 2024 - Building the future, one commit at a time</p>
        </footer>
    </div>

    <script>
        // Matrix Rain Effect
        const canvas = document.getElementById('matrix');
        const ctx = canvas.getContext('2d');

        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        const chars = '01アイウエオカキクケコサシスセソタチツテトナニヌネノハヒフヘホ';
        const fontSize = 14;
        const columns = canvas.width / fontSize;
        const drops = Array(Math.floor(columns)).fill(1);

        function drawMatrix() {
            ctx.fillStyle = 'rgba(10, 14, 39, 0.05)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);

            ctx.fillStyle = '#5f2ded';
            ctx.font = fontSize + 'px monospace';

            for (let i = 0; i < drops.length; i++) {
                const text = chars[Math.floor(Math.random() * chars.length)];
                ctx.fillText(text, i * fontSize, drops[i] * fontSize);

                if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
                    drops[i] = 0;
                }
                drops[i]++;
            }
        }

        setInterval(drawMatrix, 50);

        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });

        // Dropdown Toggle Function
        function toggleDropdown(id) {
            const content = document.getElementById('content-' + id);
            const icon = document.getElementById('icon-' + id);
            
            content.classList.toggle('active');
            
            if (content.classList.contains('active')) {
                icon.style.transform = 'rotate(180deg)';
            } else {
                icon.style.transform = 'rotate(0deg)';
            }
        }

        // Create Floating Particles
        function createParticle() {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * window.innerWidth + 'px';
            particle.style.animationDuration = (Math.random() * 3 + 2) + 's';
            particle.style.animationDelay = Math.random() * 2 + 's';
            document.body.appendChild(particle);

            setTimeout(() => {
                particle.remove();
            }, 5000);
        }

        setInterval(createParticle, 300);

        // Typing Animation for Code Block
        const codeLines = document.querySelectorAll('.code-line');
        codeLines.forEach((line, index) => {
            line.style.animationDelay = (index * 0.1) + 's';
        });
    </script>
</body>
</html>
