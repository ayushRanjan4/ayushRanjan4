<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ayush Ranjan - Backend Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #00d084;
            --secondary: #0055ff;
            --dark: #0f172a;
            --darker: #020817;
            --accent: #ff006e;
            --text-light: #e0e7ff;
            --text-muted: #a1aecb;
        }

        body {
            background: linear-gradient(135deg, var(--darker) 0%, #1a1f3a 100%);
            color: var(--text-light);
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen', 'Ubuntu', 'Cantarell', sans-serif;
            min-height: 100vh;
            overflow-x: hidden;
        }

        /* Animated Background */
        .background-orbs {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: 0;
            pointer-events: none;
        }

        .orb {
            position: absolute;
            border-radius: 50%;
            filter: blur(80px);
            opacity: 0.15;
            animation: float 20s infinite ease-in-out;
        }

        .orb1 {
            width: 400px;
            height: 400px;
            background: var(--primary);
            top: -200px;
            left: -200px;
            animation-delay: 0s;
        }

        .orb2 {
            width: 300px;
            height: 300px;
            background: var(--secondary);
            bottom: -150px;
            right: -150px;
            animation-delay: 5s;
        }

        .orb3 {
            width: 350px;
            height: 350px;
            background: var(--accent);
            top: 50%;
            right: -100px;
            animation-delay: 10s;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0) rotate(0deg); }
            33% { transform: translate(30px, -30px) rotate(120deg); }
            66% { transform: translate(-20px, 20px) rotate(240deg); }
        }

        /* Main Content */
        .container {
            position: relative;
            z-index: 1;
            max-width: 900px;
            margin: 0 auto;
            padding: 80px 40px;
        }

        /* Header */
        .header {
            text-align: center;
            margin-bottom: 80px;
            animation: slideDown 0.8s ease-out;
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .header h1 {
            font-size: 3.5em;
            font-weight: 800;
            margin-bottom: 10px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: -2px;
        }

        .tagline {
            font-size: 1.3em;
            color: var(--text-muted);
            margin-bottom: 30px;
            font-weight: 300;
        }

        .status-badge {
            display: inline-block;
            padding: 8px 16px;
            background: rgba(0, 208, 132, 0.1);
            border: 1px solid var(--primary);
            border-radius: 50px;
            font-size: 0.9em;
            color: var(--primary);
            margin-bottom: 20px;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }

        /* About Section */
        .section {
            margin-bottom: 60px;
            animation: fadeInUp 0.8s ease-out;
            animation-fill-mode: both;
        }

        .section:nth-child(2) { animation-delay: 0.2s; }
        .section:nth-child(3) { animation-delay: 0.4s; }
        .section:nth-child(4) { animation-delay: 0.6s; }
        .section:nth-child(5) { animation-delay: 0.8s; }

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

        .section-title {
            font-size: 1.8em;
            font-weight: 700;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--text-light);
        }

        .section-title::after {
            content: '';
            flex: 1;
            height: 2px;
            background: linear-gradient(90deg, var(--primary), transparent);
            max-width: 100px;
        }

        /* Cards */
        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .card {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(0, 208, 132, 0.2);
            border-radius: 12px;
            padding: 25px;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200px;
            height: 200px;
            background: radial-gradient(circle, var(--primary), transparent);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .card:hover {
            border-color: var(--primary);
            background: rgba(0, 208, 132, 0.1);
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 208, 132, 0.1);
        }

        .card:hover::before {
            opacity: 0.1;
        }

        .card-title {
            font-size: 1.2em;
            font-weight: 700;
            margin-bottom: 10px;
            color: var(--primary);
        }

        .card-description {
            font-size: 0.95em;
            color: var(--text-muted);
            line-height: 1.6;
        }

        /* Stats */
        .stats-container {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            margin-top: 20px;
        }

        .stat {
            background: rgba(0, 208, 132, 0.05);
            border: 1px solid rgba(0, 208, 132, 0.2);
            border-radius: 12px;
            padding: 20px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .stat:hover {
            background: rgba(0, 208, 132, 0.1);
            border-color: var(--primary);
            transform: scale(1.05);
        }

        .stat-number {
            font-size: 2.2em;
            font-weight: 800;
            color: var(--primary);
            margin-bottom: 5px;
        }

        .stat-label {
            font-size: 0.9em;
            color: var(--text-muted);
        }

        /* Text Content */
        .text-content {
            font-size: 1.05em;
            line-height: 1.8;
            color: var(--text-light);
        }

        .text-content strong {
            color: var(--primary);
        }

        .highlight-box {
            background: rgba(0, 208, 132, 0.1);
            border-left: 4px solid var(--primary);
            padding: 20px;
            border-radius: 8px;
            margin: 20px 0;
        }

        /* Action Links */
        .action-links {
            display: flex;
            gap: 15px;
            margin-top: 25px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 12px 24px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: var(--dark);
            text-decoration: none;
            border-radius: 8px;
            font-weight: 600;
            transition: all 0.3s ease;
            cursor: pointer;
            border: none;
            font-size: 0.95em;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(0, 208, 132, 0.3);
        }

        .btn-secondary {
            background: transparent;
            border: 2px solid var(--primary);
            color: var(--primary);
        }

        .btn-secondary:hover {
            background: rgba(0, 208, 132, 0.1);
        }

        /* Footer */
        .footer {
            text-align: center;
            padding-top: 40px;
            border-top: 1px solid rgba(0, 208, 132, 0.2);
            color: var(--text-muted);
            margin-top: 80px;
            animation: fadeIn 1s ease-out 1s both;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .footer-emoji {
            font-size: 1.5em;
            display: inline-block;
            margin: 0 5px;
            animation: bounce 1s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-5px); }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .container {
                padding: 40px 20px;
            }

            .header h1 {
                font-size: 2.5em;
            }

            .stats-container {
                grid-template-columns: 1fr;
            }

            .action-links {
                justify-content: flex-start;
            }

            .section-title::after {
                display: none;
            }
        }
    </style>
</head>
<body>
    <!-- Animated Background -->
    <div class="background-orbs">
        <div class="orb orb1"></div>
        <div class="orb orb2"></div>
        <div class="orb orb3"></div>
    </div>

    <!-- Main Content -->
    <div class="container">
        <!-- Header -->
        <div class="header">
            <div class="status-badge">🚀 Currently Hiring</div>
            <h1>Ayush Ranjan</h1>
            <p class="tagline">Backend Engineer | Spring Boot Specialist | Problem Solver</p>
        </div>

        <!-- About Section -->
        <div class="section">
            <h2 class="section-title">👨‍💻 About Me</h2>
            <div class="text-content">
                I'm a passionate <strong>backend engineer</strong> specializing in <strong>Java</strong> and <strong>Spring Boot</strong>, with a deep commitment to clean architecture and performance optimization. I thrive on solving complex algorithmic challenges and building robust REST APIs that scale.
            </div>
            <div class="highlight-box">
                With <strong>238+ LeetCode problems</strong> conquered and consistent competitive programming experience on <strong>Codeforces</strong>, I bring a problem-solving mindset to every project. My goal: crafting systems that are not just functional, but <em>elegant</em>.
            </div>
        </div>

        <!-- Skills Section -->
        <div class="section">
            <h2 class="section-title">🎯 Core Competencies</h2>
            <div class="cards-grid">
                <div class="card">
                    <div class="card-title">☕ Languages & Frameworks</div>
                    <div class="card-description">Java (Advanced), Spring Boot, REST APIs, Microservices, Spring Data JPA, Spring Security</div>
                </div>
                <div class="card">
                    <div class="card-title">🧠 Problem-Solving</div>
                    <div class="card-description">Data Structures, Algorithms, Competitive Programming (Codeforces), System Design</div>
                </div>
                <div class="card">
                    <div class="card-title">🗄️ Databases</div>
                    <div class="card-description">SQL, JPA/Hibernate, MySQL, PostgreSQL, Database Design Patterns</div>
                </div>
                <div class="card">
                    <div class="card-title">🛠️ Tools & Tech</div>
                    <div class="card-description">Maven, Git, Docker, Postman, Agile/Scrum, CI/CD Pipelines</div>
                </div>
            </div>
        </div>

        <!-- Achievements Section -->
        <div class="section">
            <h2 class="section-title">🏆 Achievements</h2>
            <div class="stats-container">
                <div class="stat">
                    <div class="stat-number">238+</div>
                    <div class="stat-label">LeetCode Problems Solved</div>
                </div>
                <div class="stat">
                    <div class="stat-number">5+</div>
                    <div class="stat-label">Spring Boot Projects</div>
                </div>
                <div class="stat">
                    <div class="stat-number">∞</div>
                    <div class="stat-label">Codeforces Grind</div>
                </div>
                <div class="stat">
                    <div class="stat-number">10+</div>
                    <div class="stat-label">REST APIs Built</div>
                </div>
            </div>
        </div>

        <!-- Currently Doing Section -->
        <div class="section">
            <h2 class="section-title">💡 Currently</h2>
            <div class="cards-grid">
                <div class="card">
                    <div class="card-title">🔨 Building</div>
                    <div class="card-description">Scalable microservices with Spring Boot and cloud deployment strategies</div>
                </div>
                <div class="card">
                    <div class="card-title">📚 Learning</div>
                    <div class="card-description">Advanced system design patterns, distributed systems, and backend optimization</div>
                </div>
                <div class="card">
                    <div class="card-title">🎯 Competing</div>
                    <div class="card-description">Regular competitive programming challenges to sharpen algorithmic skills</div>
                </div>
                <div class="card">
                    <div class="card-title">🤝 Open Source</div>
                    <div class="card-description">Contributing to Java and Spring Boot community projects</div>
                </div>
            </div>
        </div>

        <!-- Connect Section -->
        <div class="section">
            <h2 class="section-title">🤝 Let's Connect</h2>
            <div class="text-content">
                I'm always excited to collaborate on challenging backend projects and discuss system design patterns. Let's build something amazing together!
            </div>
            <div class="action-links">
                <a href="#" class="btn">
                    💼 LinkedIn
                </a>
                <a href="#" class="btn">
                    🔗 GitHub
                </a>
                <a href="#" class="btn btn-secondary">
                    📧 Email Me
                </a>
            </div>
        </div>

        <!-- Footer -->
        <div class="footer">
            <p>
                <span class="footer-emoji">✨</span>
                Always learning. Always building. Always optimizing.
                <span class="footer-emoji">✨</span>
            </p>
            <p style="margin-top: 20px; font-size: 0.9em;">
                Last Updated: March 2026 | Continuous Improvement Mode <strong>ON</strong> 🔄
            </p>
        </div>
    </div>
</body>
</html>
