<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Seu Nome - Portfólio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Reset e configurações básicas */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary-color: #2c3e50;
            --secondary-color: #3498db;
            --accent-color: #e74c3c;
            --light-color: #ecf0f1;
            --dark-color: #2c3e50;
            --text-color: #333;
            --text-light: #777;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            line-height: 1.6;
            color: var(--text-color);
            background-color: #f9f9f9;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
            position: relative;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--primary-color);
            display: inline-block;
            position: relative;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 70px;
            height: 3px;
            background-color: var(--secondary-color);
        }

        /* Header e Navegação */
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary-color);
            text-decoration: none;
        }

        .logo span {
            color: var(--secondary-color);
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 30px;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-color);
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: var(--secondary-color);
        }

        .menu-toggle {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            text-align: center;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            color: var(--primary-color);
        }

        .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 30px;
            color: var(--text-light);
        }

        .hero-content .highlight {
            color: var(--secondary-color);
            font-weight: 600;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background-color: var(--secondary-color);
            color: white;
            text-decoration: none;
            border-radius: 5px;
            font-weight: 500;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
        }

        .btn:hover {
            background-color: var(--primary-color);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        /* Sobre */
        .about-content {
            display: flex;
            align-items: center;
            gap: 50px;
        }

        .about-text {
            flex: 1;
        }

        .about-text h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--primary-color);
        }

        .about-text p {
            margin-bottom: 15px;
            color: var(--text-light);
        }

        .about-image {
            flex: 1;
            text-align: center;
        }

        .about-image img {
            max-width: 100%;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        /* Habilidades */
        .skills {
            background-color: var(--light-color);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 30px;
        }

        .skill-card {
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
        }

        .skill-card:hover {
            transform: translateY(-10px);
        }

        .skill-card i {
            font-size: 3rem;
            color: var(--secondary-color);
            margin-bottom: 20px;
        }

        .skill-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--primary-color);
        }

        /* Projetos */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }

        .project-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
        }

        .project-card:hover {
            transform: translateY(-10px);
        }

        .project-image {
            height: 200px;
            overflow: hidden;
        }

        .project-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .project-card:hover .project-image img {
            transform: scale(1.1);
        }

        .project-info {
            padding: 20px;
        }

        .project-info h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: var(--primary-color);
        }

        .project-info p {
            color: var(--text-light);
            margin-bottom: 15px;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 15px;
        }

        .project-tags span {
            background-color: var(--light-color);
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
            color: var(--text-light);
        }

        /* Contato */
        .contact {
            background-color: var(--light-color);
        }

        .contact-content {
            display: flex;
            gap: 50px;
        }

        .contact-info {
            flex: 1;
        }

        .contact-info h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--primary-color);
        }

        .contact-info p {
            margin-bottom: 20px;
            color: var(--text-light);
        }

        .contact-details {
            margin-top: 30px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }

        .contact-item i {
            font-size: 1.2rem;
            color: var(--secondary-color);
            margin-right: 15px;
            width: 20px;
        }

        .contact-form {
            flex: 1;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 500;
        }

        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
            transition: border 0.3s;
        }

        .form-control:focus {
            border-color: var(--secondary-color);
            outline: none;
        }

        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        /* Footer */
        footer {
            background-color: var(--dark-color);
            color: white;
            padding: 40px 0;
            text-align: center;
        }

        .social-links {
            display: flex;
            justify-content: center;
            margin-bottom: 20px;
        }

        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            margin: 0 10px;
            color: white;
            text-decoration: none;
            transition: all 0.3s;
        }

        .social-links a:hover {
            background-color: var(--secondary-color);
            transform: translateY(-5px);
        }

        .copyright {
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.9rem;
        }

        /* Responsividade */
        @media (max-width: 992px) {
            .about-content, .contact-content {
                flex-direction: column;
            }

            .about-image {
                order: -1;
            }
        }

        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
            }

            .nav-links {
                position: fixed;
                top: 70px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 70px);
                background-color: white;
                flex-direction: column;
                align-items: center;
                justify-content: flex-start;
                padding-top: 50px;
                transition: left 0.3s;
            }

            .nav-links.active {
                left: 0;
            }

            .nav-links li {
                margin: 15px 0;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .hero-content p {
                font-size: 1.2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header e Navegação -->
    <header>
        <div class="container">
            <nav>
                <a href="#" class="logo">Seu<span>Nome</span></a>
                <div class="menu-toggle" id="menuToggle">
                    <i class="fas fa-bars"></i>
                </div>
                <ul class="nav-links">
                    <li><a href="#home">Início</a></li>
                    <li><a href="#about">Sobre</a></li>
                    <li><a href="#skills">Habilidades</a></li>
                    <li><a href="#projects">Projetos</a></li>
                    <li><a href="#contact">Contato</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <h1>Olá, eu sou <span class="highlight">Seu Nome</span></h1>
                <p>Desenvolvedor Full Stack & Designer UI/UX</p>
                <a href="#projects" class="btn">Ver Meus Projetos</a>
            </div>
        </div>
    </section>

    <!-- Sobre -->
    <section id="about">
        <div class="container">
            <div class="section-title">
                <h2>Sobre Mim</h2>
            </div>
            <div class="about-content">
                <div class="about-text">
                    <h3>Desenvolvedor apaixonado por criar soluções digitais</h3>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
                    <p>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
                    <a href="#" class="btn">Download CV</a>
                </div>
                <div class="about-image">
                    <img src="https://via.placeholder.com/400x500" alt="Sua Foto">
                </div>
            </div>
        </div>
    </section>

    <!-- Habilidades -->
    <section class="skills" id="skills">
        <div class="container">
            <div class="section-title">
                <h2>Minhas Habilidades</h2>
            </div>
            <div class="skills-grid">
                <div class="skill-card">
                    <i class="fas fa-code"></i>
                    <h3>Desenvolvimento Web</h3>
                    <p>HTML, CSS, JavaScript, React, Node.js</p>
                </div>
                <div class="skill-card">
                    <i class="fas fa-mobile-alt"></i>
                    <h3>Design Responsivo</h3>
                    <p>Criação de interfaces adaptáveis para todos os dispositivos</p>
                </div>
                <div class="skill-card">
                    <i class="fas fa-palette"></i>
                    <h3>UI/UX Design</h3>
                    <p>Design de interfaces intuitivas e experiências de usuário</p>
                </div>
                <div class="skill-card">
                    <i class="fas fa-database"></i>
                    <h3>Banco de Dados</h3>
                    <p>MySQL, MongoDB, PostgreSQL</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Projetos -->
    <section id="projects">
        <div class="container">
            <div class="section-title">
                <h2>Meus Projetos</h2>
            </div>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-image">
                        <img src="https://via.placeholder.com/400x250" alt="Projeto 1">
                    </div>
                    <div class="project-info">
                        <h3>E-commerce Platform</h3>
                        <p>Plataforma de e-commerce completa com carrinho de compras e sistema de pagamento.</p>
                        <div class="project-tags">
                            <span>React</span>
                            <span>Node.js</span>
                            <span>MongoDB</span>
                        </div>
                        <a href="#" class="btn">Ver Detalhes</a>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">
                        <img src="https://via.placeholder.com/400x250" alt="Projeto 2">
                    </div>
                    <div class="project-info">
                        <h3>Task Management App</h3>
                        <p>Aplicativo para gerenciamento de tarefas com funcionalidades de colaboração em equipe.</p>
                        <div class="project-tags">
                            <span>Vue.js</span>
                            <span>Firebase</span>
                            <span>CSS3</span>
                        </div>
                        <a href="#" class="btn">Ver Detalhes</a>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">
                        <img src="https://via.placeholder.com/400x250" alt="Projeto 3">
                    </div>
                    <div class="project-info">
                        <h3>Weather Dashboard</h3>
                        <p>Dashboard interativo para visualização de dados meteorológicos em tempo real.</p>
                        <div class="project-tags">
                            <span>JavaScript</span>
                            <span>API</span>
                            <span>Chart.js</span>
                        </div>
                        <a href="#" class="btn">Ver Detalhes</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contato -->
    <section class="contact" id="contact">
        <div class="container">
            <div class="section-title">
                <h2>Entre em Contato</h2>
            </div>
            <div class="contact-content">
                <div class="contact-info">
                    <h3>Vamos trabalhar juntos!</h3>
                    <p>Estou sempre aberto a discutir novos projetos, ideias criativas ou oportunidades para fazer parte de suas visões.</p>
                    <div class="contact-details">
                        <div class="contact-item">
                            <i class="fas fa-envelope"></i>
                            <span>seuemail@exemplo.com</span>
                        </div>
                        <div class="contact-item">
                            <i class="fas fa-phone"></i>
                            <span>+55 (11) 99999-9999</span>
                        </div>
                        <div class="contact-item">
                            <i class="fas fa-map-marker-alt"></i>
                            <span>Sua Cidade, Seu Estado</span>
                        </div>
                    </div>
                </div>
                <div class="contact-form">
                    <form id="contactForm">
                        <div class="form-group">
                            <label for="name">Nome</label>
                            <input type="text" id="name" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="subject">Assunto</label>
                            <input type="text" id="subject" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="message">Mensagem</label>
                            <textarea id="message" class="form-control" required></textarea>
                        </div>
                        <button type="submit" class="btn">Enviar Mensagem</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="social-links">
                <a href="#"><i class="fab fa-github"></i></a>
                <a href="#"><i class="fab fa-linkedin-in"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-instagram"></i></a>
            </div>
            <p class="copyright">&copy; 2023 Seu Nome. Todos os direitos reservados.</p>
        </div>
    </footer>

    <script>
        // Menu toggle para mobile
        document.getElementById('menuToggle').addEventListener('click', function() {
            document.querySelector('.nav-links').classList.toggle('active');
        });

        // Fechar menu ao clicar em um link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                document.querySelector('.nav-links').classList.remove('active');
            });
        });

        // Form submission
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Obrigado pela mensagem! Entrarei em contato em breve.');
            this.reset();
        });

        // Scroll suave para âncoras
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 70,
                        behavior: 'smooth'
                    });
                }
            });
        });
    </script>
</body>
</html>
