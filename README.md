<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio - Développeur Full Stack</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Courier New', monospace;
            background: #0a0e27;
            color: #e0e0e0;
            line-height: 1.6;
        }
        
        header {
            background: #111825;
            border-bottom: 2px solid #00d9ff;
            padding: 60px 20px;
            text-align: center;
            animation: fadeInDown 0.8s ease;
        }
        
        header h1 {
            font-size: 2.8em;
            color: #00d9ff;
            margin-bottom: 10px;
            letter-spacing: 2px;
        }
        
        header p {
            font-size: 1.1em;
            color: #888;
            letter-spacing: 1px;
        }
        
        nav {
            background: #0f1320;
            padding: 20px;
            text-align: center;
            border-bottom: 1px solid #1a1f3a;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        nav a {
            color: #00d9ff;
            text-decoration: none;
            display: inline-block;
            padding: 10px 20px;
            margin: 0 10px;
            transition: all 0.3s;
            border: 1px solid transparent;
            cursor: pointer;
        }
        
        nav a:hover {
            color: #fff;
            border-bottom: 2px solid #00d9ff;
            text-shadow: 0 0 10px #00d9ff;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 50px 20px;
        }
        
        section {
            margin-bottom: 60px;
            animation: fadeInUp 0.8s ease;
            opacity: 0;
            animation-fill-mode: forwards;
        }
        
        section:nth-child(1) { animation-delay: 0.1s; }
        section:nth-child(2) { animation-delay: 0.3s; }
        section:nth-child(3) { animation-delay: 0.5s; }
        
        h2 {
            color: #00d9ff;
            font-size: 2em;
            margin-bottom: 30px;
            border-left: 4px solid #00d9ff;
            padding-left: 15px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        
        .about-box {
            background: #111825;
            padding: 30px;
            border: 1px solid #1a1f3a;
            border-left: 4px solid #00d9ff;
            border-radius: 4px;
            transition: all 0.3s;
        }
        
        .about-box:hover {
            border-left: 4px solid #00ff88;
            box-shadow: 0 0 20px rgba(0, 217, 255, 0.1);
        }
        
        .about-box p {
            font-size: 1em;
            color: #b0b0b0;
            margin-bottom: 15px;
        }
        
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }
        
        .skill {
            background: #0f1320;
            padding: 15px;
            border: 1px solid #1a1f3a;
            border-radius: 4px;
            text-align: center;
            color: #00d9ff;
            font-weight: bold;
            transition: all 0.3s;
            cursor: pointer;
        }
        
        .skill:hover {
            background: #1a1f3a;
            border-color: #00d9ff;
            box-shadow: 0 0 15px rgba(0, 217, 255, 0.2);
            transform: translateY(-3px);
        }
        
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }
        
        .project-card {
            background: #111825;
            border: 1px solid #1a1f3a;
            padding: 25px;
            border-radius: 4px;
            transition: all 0.4s;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }
        
        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, transparent, #00d9ff, transparent);
            transition: left 0.5s;
        }
        
        .project-card:hover::before {
            left: 100%;
        }
        
        .project-card:hover {
            border-color: #00d9ff;
            box-shadow: 0 0 25px rgba(0, 217, 255, 0.15);
            transform: translateY(-5px);
        }
        
        .project-card h3 {
            color: #00d9ff;
            margin-bottom: 12px;
            font-size: 1.3em;
        }
        
        .project-card p {
            color: #999;
            margin-bottom: 15px;
            line-height: 1.5;
        }
        
        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }
        
        .tech {
            background: #0a0e27;
            color: #00ff88;
            padding: 4px 10px;
            border-radius: 3px;
            font-size: 0.85em;
            border: 1px solid #00ff88;
        }
        
        .contact-box {
            background: #111825;
            padding: 40px;
            border: 2px solid #00d9ff;
            border-radius: 4px;
            text-align: center;
        }
        
        .contact-box p {
            color: #b0b0b0;
            margin-bottom: 25px;
            font-size: 1.05em;
        }
        
        .contact-links {
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
            margin-bottom: 20px;
        }
        
        .contact-links a {
            background: #0a0e27;
            color: #00d9ff;
            padding: 12px 25px;
            border: 1px solid #00d9ff;
            border-radius: 4px;
            text-decoration: none;
            transition: all 0.3s;
            font-weight: bold;
            cursor: pointer;
        }
        
        .contact-links a:hover {
            background: #00d9ff;
            color: #0a0e27;
            box-shadow: 0 0 20px rgba(0, 217, 255, 0.4);
        }
        
        .info-line {
            color: #666;
            font-size: 0.95em;
            margin-top: 15px;
        }
        
        .info-line strong {
            color: #00d9ff;
        }
        
        footer {
            background: #0f1320;
            color: #666;
            text-align: center;
            padding: 25px;
            border-top: 1px solid #1a1f3a;
            margin-top: 60px;
            font-size: 0.9em;
        }
        
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .glow-on-scroll {
            opacity: 0;
            animation: fadeInUp 0.6s ease forwards;
        }
    </style>
</head>
<body>
    <header>
        <h1>&lt; Full Stack Developer /&gt;</h1>
        <p>> PHP | MySQL | HTML | CSS | JavaScript</p>
    </header>
    
    <nav>
        <a href="#about">About</a>
        <a href="#skills">Skills</a>
        <a href="#projects">Projects</a>
        <a href="#contact">Contact</a>
    </nav>
    
    <div class="container">
        <!-- ABOUT SECTION -->
        <section id="about">
            <h2>$ About Me</h2>
            <div class="about-box">
                <p>Développeur Full Stack passionné spécialisé en PHP et MySQL. Je crée des solutions web performantes, maintenables et faciles à utiliser.</p>
                <p>Mes domaines : sites vitrines, systèmes de gestion, formulaires dynamiques, bases de données. Code propre. Livraison rapide. Client-focused.</p>
            </div>
        </section>
        
        <!-- SKILLS SECTION -->
        <section id="skills">
            <h2>$ Technical Skills</h2>
            <div class="skills-grid">
                <div class="skill">PHP</div>
                <div class="skill">MySQL</div>
                <div class="skill">HTML5</div>
                <div class="skill">CSS3</div>
                <div class="skill">JavaScript</div>
                <div class="skill">Responsive</div>
            </div>
        </section>
        
        <!-- PROJECTS SECTION -->
        <section id="projects">
            <h2>$ Recent Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3>📱 Site Vitrine</h3>
                    <p>Site responsive moderne avec formulaire de contact et intégration email. Design épuré, performance optimisée.</p>
                    <div class="tech-stack">
                        <span class="tech">HTML5</span>
                        <span class="tech">CSS3</span>
                        <span class="tech">PHP</span>
                    </div>
                </div>
                
                <div class="project-card">
                    <h3>💾 Système de Gestion</h3>
                    <p>Application web complète avec base de données MySQL. Panneau d'administration intuitif pour gestion de contenu.</p>
                    <div class="tech-stack">
                        <span class="tech">PHP</span>
                        <span class="tech">MySQL</span>
                        <span class="tech">JavaScript</span>
                    </div>
                </div>
                
                <div class="project-card">
                    <h3>📋 Formulaire Sécurisé</h3>
                    <p>Formulaire avancé avec validation côté serveur et client. Sauvegarde en base de données et confirmation par email.</p>
                    <div class="tech-stack">
                        <span class="tech">JavaScript</span>
                        <span class="tech">PHP</span>
                        <span class="tech">MySQL</span>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- CONTACT SECTION -->
        <section id="contact">
            <div class="contact-box">
                <h2 style="text-align: left; margin-bottom: 20px;">$ Get In Touch</h2>
                <p>Vous avez un projet web ? Je suis disponible pour discuter et proposer une solution adaptée.</p>
                <div class="contact-links">
                    <a href="mailto:lienard.lorenzo@gmail.com">Email</a>
                    <a href="https://www.malt.fr/profile/lorenzolienard?overview" target="_blank">Malt</a>
                    <a href="https://github.com" target="_blank">GitHub</a>
                </div>
                <div class="info-line">
                    <strong>Tarif :</strong> 28-35€/h | <strong>Délai :</strong> Devis sur demande<br>
                    Livraison rapide • Code professionnel • Support client
                </div>
            </div>
        </section>
    </div>
    
    <footer>
        <p> $copy 2025 Full Stack Developer | Code is Poetry</p>
    </footer>
    
    <script>
        // Animation au scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('glow-on-scroll');
                }
            });
        }, observerOptions);
        
        document.querySelectorAll('.project-card').forEach(card => {
            observer.observe(card);
        });
        
        // Smooth scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });
    </script>
</body>
</html>
