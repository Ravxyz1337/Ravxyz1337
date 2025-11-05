<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RAVXYZ1337 - Security Researcher</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #0a0e27 0%, #1a1a2e 50%, #0f3460 100%);
            color: #00ff88;
            font-family: 'Courier New', monospace;
            min-height: 100vh;
            padding: 40px 20px;
            position: relative;
            overflow-x: hidden;
        }

        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                repeating-linear-gradient(
                    0deg,
                    rgba(0, 255, 136, 0.03) 0px,
                    rgba(0, 255, 136, 0.03) 1px,
                    transparent 1px,
                    transparent 2px
                );
            pointer-events: none;
            animation: scanlines 8s linear infinite;
            z-index: 1;
        }

        @keyframes scanlines {
            0% { transform: translateY(0); }
            100% { transform: translateY(10px); }
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            position: relative;
            z-index: 2;
        }

        header {
            text-align: center;
            margin-bottom: 80px;
            animation: fadeInDown 1s ease-out;
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

        .title {
            font-size: 4em;
            font-weight: bold;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #00ff88, #00d4ff, #ff006e);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 30px rgba(0, 255, 136, 0.3);
            animation: glitch 3s infinite;
        }

        @keyframes glitch {
            0%, 100% { transform: translateX(0); }
            20% { transform: translateX(-2px); }
            40% { transform: translateX(2px); }
        }

        .subtitle {
            font-size: 1.3em;
            color: #00d4ff;
            margin-bottom: 30px;
            font-weight: bold;
            letter-spacing: 2px;
            animation: fadeIn 1.5s ease-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .typing {
            font-size: 1.1em;
            color: #ff006e;
            min-height: 30px;
            margin-bottom: 40px;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin: 60px 0;
            animation: fadeInUp 1.2s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .tech-badge {
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.1), rgba(0, 212, 255, 0.1));
            border: 2px solid #00ff88;
            padding: 15px 20px;
            text-align: center;
            border-radius: 5px;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .tech-badge::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 255, 136, 0.3), transparent);
            transition: left 0.5s;
        }

        .tech-badge:hover {
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.2), rgba(0, 212, 255, 0.2));
            box-shadow: 0 0 20px rgba(0, 255, 136, 0.5);
            border-color: #00d4ff;
            transform: translateY(-5px);
        }

        .tech-badge:hover::before {
            left: 100%;
        }

        .tech-name {
            font-weight: bold;
            font-size: 0.95em;
            color: #00ff88;
        }

        .stats {
            margin: 80px 0;
            text-align: center;
            animation: fadeIn 1.8s ease-out;
        }

        .stats h2 {
            font-size: 1.8em;
            color: #00d4ff;
            margin-bottom: 40px;
            text-transform: uppercase;
            letter-spacing: 3px;
        }

        .stat-box {
            display: inline-block;
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.05), rgba(255, 0, 110, 0.05));
            border: 2px solid #00d4ff;
            padding: 30px 50px;
            margin: 15px;
            border-radius: 5px;
            transition: all 0.3s ease;
        }

        .stat-box:hover {
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.15), rgba(255, 0, 110, 0.15));
            box-shadow: 0 0 30px rgba(0, 212, 255, 0.5);
            transform: scale(1.05);
        }

        .stat-number {
            font-size: 2.5em;
            color: #ff006e;
            font-weight: bold;
        }

        .stat-label {
            color: #00ff88;
            margin-top: 10px;
            font-size: 0.95em;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .social {
            text-align: center;
            margin: 60px 0;
        }

        .social-link {
            display: inline-block;
            margin: 0 15px;
            padding: 15px 30px;
            background: linear-gradient(135deg, #00ff88, #00d4ff);
            color: #0a0e27;
            text-decoration: none;
            font-weight: bold;
            border-radius: 5px;
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-size: 0.9em;
        }

        .social-link:hover {
            box-shadow: 0 0 30px rgba(0, 255, 136, 0.8);
            transform: translateY(-3px);
            animation: pulse 0.6s ease;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .divider {
            height: 2px;
            background: linear-gradient(90deg, transparent, #00ff88, #00d4ff, transparent);
            margin: 60px 0;
            animation: glow 2s ease-in-out infinite;
        }

        @keyframes glow {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 1; }
        }

        .footer {
            text-align: center;
            color: #00d4ff;
            font-size: 0.9em;
            margin-top: 80px;
            opacity: 0.7;
        }

        @media (max-width: 768px) {
            .title {
                font-size: 2.5em;
            }
            
            .tech-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .stat-box {
                padding: 20px 30px;
                margin: 10px;
            }

            .stat-number {
                font-size: 1.8em;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1 class="title">RAVXYZ1337</h1>
            <p class="subtitle">Security Researcher | Penetration Tester | Bug Hunter</p>
            <div class="typing">
                > Menemukan kerentanan untuk dunia yang lebih aman...
            </div>
        </header>

        <div class="divider"></div>

        <section class="tech-grid">
            <div class="tech-badge">
                <div class="tech-name">Penetration Testing</div>
            </div>
            <div class="tech-badge">
                <div class="tech-name">Vulnerability Assessment</div>
            </div>
            <div class="tech-badge">
                <div class="tech-name">Exploit Development</div>
            </div>
            <div class="tech-badge">
                <div class="tech-name">Network Security</div>
            </div>
            <div class="tech-badge">
                <div class="tech-name">Red Team Operations</div>
            </div>
            <div class="tech-badge">
                <div class="tech-name">Bug Bounty Hunting</div>
            </div>
        </section>

        <div class="divider"></div>

        <section class="tech-grid">
            <div class="tech-badge">
                <div class="tech-name">Bash Scripting</div>
            </div>
            <div class="tech-badge">
                <div class="tech-name">Python</div>
            </div>
            <div class="tech-badge">
                <div class="tech-name">Perl</div>
            </div>
            <div class="tech-badge">
                <div class="tech-name">Azure</div>
            </div>
            <div class="tech-badge">
                <div class="tech-name">MySQL</div>
            </div>
            <div class="tech-badge">
                <div class="tech-name">MongoDB</div>
            </div>
        </section>

        <div class="divider"></div>

        <section class="stats">
            <h2>GitHub Stats</h2>
            <div class="stat-box">
                <div class="stat-number">150+</div>
                <div class="stat-label">Repositories</div>
            </div>
            <div class="stat-box">
                <div class="stat-number">500+</div>
                <div class="stat-label">Contributions</div>
            </div>
            <div class="stat-box">
                <div class="stat-number">1K+</div>
                <div class="stat-label">Followers</div>
            </div>
        </section>

        <div class="divider"></div>

        <section class="social">
            <a href="https://instagram.com/rav_sec88" class="social-link">Instagram</a>
            <a href="https://github.com/ravxyz1337" class="social-link">GitHub</a>
        </section>

        <div class="footer">
            <p>> Ethical Hacking | Security Research | Defensive Security</p>
            <p style="margin-top: 10px; color: #00ff88;">chmod 777 security</p>
        </div>
    </div>
</body>
</html>
