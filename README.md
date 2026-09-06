<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prime Solutions - Digital Agency</title>
    <style>
        :root {
            --bg-color: #f9fafb;
            --text-color: #1f2937;
            --card-bg: #ffffff;
            --header-bg: rgba(255, 255, 255, 0.95);
            --border-color: #e5e7eb;
            --muted-color: #6b7280;
        }

        [data-theme="dark"] {
            --bg-color: #0f172a;
            --text-color: #f8fafc;
            --card-bg: #1e293b;
            --header-bg: rgba(15, 23, 42, 0.95);
            --border-color: #334155;
            --muted-color: #94a3b8;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            scroll-behavior: smooth;
            transition: background-color 0.3s, color 0.3s;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            overflow-x: hidden;
        }

        /* Header / Navbar */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 50px;
            background-color: var(--header-bg);
            backdrop-filter: blur(10px);
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .logo {
            font-size: 24px;
            font-weight: bold;
            color: #2563eb;
            text-decoration: none;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 20px;
            align-items: center;
        }

        nav ul li a {
            text-decoration: none;
            color: var(--muted-color);
            font-weight: 500;
            transition: color 0.3s;
        }

        nav ul li a:hover {
            color: #2563eb;
        }

        .nav-actions {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .theme-toggle {
            background: none;
            border: 1px solid var(--border-color);
            color: var(--text-color);
            padding: 8px 12px;
            border-radius: 6px;
            cursor: pointer;
            font-size: 14px;
        }

        .cta-btn {
            background-color: #2563eb;
            color: white;
            padding: 10px 20px;
            border-radius: 6px;
            text-decoration: none;
            font-weight: 500;
            transition: background-color 0.3s;
        }

        .cta-btn:hover {
            background-color: #1d4ed8;
        }

        /* Hero Section */
        .hero {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 140px 20px;
            background: linear-gradient(rgba(30, 58, 138, 0.8), rgba(30, 58, 138, 0.9)), url('https://images.unsplash.com/photo-1522071820081-009f0129c71c?auto=format&fit=crop&w=1920&q=80') no-repeat center center/cover;
            color: white;
        }

        .hero h1 {
            font-size: 52px;
            margin-bottom: 20px;
        }

        .hero p {
            font-size: 18px;
            max-width: 650px;
            margin-bottom: 35px;
            line-height: 1.6;
            color: #e2e8f0;
        }

        .hero-btn {
            background-color: #ffffff;
            color: #2563eb;
            padding: 14px 35px;
            border-radius: 30px;
            text-decoration: none;
            font-size: 16px;
            font-weight: bold;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }

        /* Stats Section */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            max-width: 1000px;
            margin: -50px auto 0 auto;
            position: relative;
            z-index: 10;
            padding: 0 20px;
        }

        .stat-card {
            background: var(--card-bg);
            padding: 25px;
            border-radius: 12px;
            text-align: center;
            box-shadow: 0 10px 25px rgba(0,0,0,0.06);
            border: 1px solid var(--border-color);
        }

        .stat-card h3 {
            font-size: 32px;
            color: #2563eb;
            margin-bottom: 5px;
        }

        .stat-card p {
            color: var(--muted-color);
            font-size: 14px;
        }

        /* Content Sections */
        .services, .portfolio, .testimonials, .contact {
            padding: 90px 50px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 36px;
            color: #2563eb;
            margin-bottom: 60px;
        }

        .services-grid, .portfolio-grid, .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 35px;
        }

        .service-card, .portfolio-card, .testimonial-card {
            background: var(--card-bg);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 6px 20px rgba(0,0,0,0.04);
            border: 1px solid var(--border-color);
        }

        .service-card img, .portfolio-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .card-content {
            padding: 25px;
        }

        .card-content h3 {
            font-size: 22px;
            color: #2563eb;
            margin-bottom: 12px;
        }

        .card-content p {
            color: var(--muted-color);
            line-height: 1.6;
            font-size: 15px;
            margin-bottom: 15px;
        }

        .project-link {
            color: #2563eb;
            font-weight: 600;
            text-decoration: none;
        }

        /* Testimonials */
        .testimonial-card {
            padding: 30px;
            text-align: center;
        }

        .testimonial-card p {
            font-style: italic;
            color: var(--muted-color);
            margin-bottom: 15px;
        }

        .testimonial-card h4 {
            color: #2563eb;
            font-size: 16px;
        }

        /* Contact Section */
        .contact-container {
            background: var(--card-bg);
            padding: 50px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
            max-width: 700px;
            margin: 0 auto;
            border: 1px solid var(--border-color);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--text-color);
        }

        .form-group input, .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid var(--border-color);
            background: var(--bg-color);
            color: var(--text-color);
            border-radius: 8px;
            font-size: 15px;
        }

        .submit-btn {
            background-color: #2563eb;
            color: white;
            border: none;
            padding: 14px 30px;
            font-size: 16px;
            font-weight: bold;
            border-radius: 8px;
            cursor: pointer;
            width: 100%;
        }

        /* AI Chatbot Floating Widget */
        .chatbot-container {
            position: fixed;
            bottom: 20px;
            right: 20px;
            z-index: 1001;
        }

        .chatbot-btn {
            background-color: #2563eb;
            color: white;
            border: none;
            width: 55px;
            height: 55px;
            border-radius: 50%;
            font-size: 22px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(37, 99, 235, 0.3);
        }

        .chatbot-box {
            display: none;
            position: absolute;
            bottom: 70px;
            right: 0;
            width: 300px;
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
            overflow: hidden;
        }

        .chatbot-header {
            background: #2563eb;
            color: white;
            padding: 15px;
            font-weight: bold;
        }

        .chatbot-body {
            padding: 15px;
            height: 200px;
            font-size: 14px;
            color: var(--muted-color);
        }

        /* Footer */
        footer {
            background-color: #1f2937;
            color: #9ca3af;
            text-align: center;
            padding: 40px 20px;
            margin-top: 80px;
        }

        footer a {
            color: #60a5fa;
            text-decoration: none;
        }

        @media (max-width: 768px) {
            header {
                padding: 15px 20px;
                flex-direction: column;
                gap: 15px;
            }
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
            .hero h1 {
                font-size: 36px;
            }
            .services, .portfolio, .testimonials, .contact {
                padding: 50px 20px;
            }
        }
    </style>
</head>
<body>

    <!-- Header / Navbar -->
    <header>
        <a href="https://web-hub-code.github.io/primesolutions/" class="logo" target="_blank">Prime Solutions</a>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#portfolio">Portfolio</a></li>
                <li><a href="#testimonials">Testimonials</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
        <div class="nav-actions">
            <button class="theme-toggle" onclick="toggleTheme()">🌙 Mode</button>
            <a href="#contact" class="cta-btn">Get Started</a>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <h1>Welcome to Prime Solutions</h1>
        <p>We provide the best digital solutions to help your business grow and succeed in the modern competitive world.</p>
        <a href="#services" class="hero-btn">Explore Services</a>
    </section>

    <!-- Stats Counter Section -->
    <div class="stats">
        <div class="stat-card">
            <h3>50+</h3>
            <p>Projects Completed</p>
        </div>
        <div class="stat-card">
            <h3>100%</h3>
            <p>Client Satisfaction</p>
        </div>
        <div class="stat-card">
            <h3>24/7</h3>
            <p>Support & Maintenance</p>
        </div>
    </div>

    <!-- Services Section -->
    <section class="services" id="services">
        <h2 class="section-title">What We Offer</h2>
        <div class="services-grid">
            <div class="service-card">
                <img src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?auto=format&fit=crop&w=600&q=80" alt="Web Development">
                <div class="card-content">
                    <h3>Web Development</h3>
                    <p>Custom, responsive, and high-performance websites built with modern technologies tailored to your brand.</p>
                </div>
            </div>
            <div class="service-card">
                <img src="https://images.unsplash.com/photo-1581291518633-83b4ebd1d83e?auto=format&fit=crop&w=600&q=80" alt="UI/UX Design">
                <div class="card-content">
                    <h3>UI/UX Design</h3>
                    <p>Engaging user interfaces and seamless experiences designed to convert visitors into loyal customers.</p>
                </div>
            </div>
            <div class="service-card">
                <img src="https://images.unsplash.com/photo-1551836022-d5d88e9218df?auto=format&fit=crop&w=600&q=80" alt="Digital Solutions">
                <div class="card-content">
                    <h3>Digital Solutions</h3>
                    <p>Scalable software integrations and automated workflows to boost your business efficiency and growth.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Portfolio Section -->
    <section class="portfolio" id="portfolio">
        <h2 class="section-title">Our Featured Work</h2>
        <div class="portfolio-grid">
            <div class="portfolio-card">
                <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?auto=format&fit=crop&w=600&q=80" alt="Vestify Pro">
                <div class="card-content">
                    <h3>Vestify Pro</h3>
                    <p>Investment and earning management platform featuring secure database logic and automated daily returns.</p>
                    <a href="https://web-hub-code.github.io/primesolutions/" target="_blank" class="project-link">View Project &rarr;</a>
                </div>
            </div>
            <div class="portfolio-card">
                <img src="https://images.unsplash.com/photo-1507238691740-187a5b1d37b8?auto=format&fit=crop&w=600&q=80" alt="USHomeImprovements">
                <div class="card-content">
                    <h3>USHomeImprovements</h3>
                    <p>Professional home improvement landing page designed with clean HTML/CSS layouts and responsive elements.</p>
                    <a href="https://web-hub-code.github.io/primesolutions/" target="_blank" class="project-link">View Project &rarr;</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="testimonials" id="testimonials">
        <h2 class="section-title">Client Testimonials</h2>
        <div class="testimonial-grid">
            <div class="testimonial-card">
                <p>"Prime Solutions delivered an exceptional website for our business ahead of schedule. Highly professional team!"</p>
                <h4>- Sarah Johnson</h4>
            </div>
            <div class="testimonial-card">
                <p>"Their attention to responsive design and UI/UX completely transformed our online conversion rates."</p>
                <h4>- Michael Brown</h4>
            </div>
        </div>
    </section>

    <!-- Contact Form Section -->
    <section class="contact" id="contact">
        <h2 class="section-title">Get In Touch</h2>
        <div class="contact-container">
            <form>
                <div class="form-group">
                    <label for="name">Your Name</label>
                    <input type="text" id="name" placeholder="Enter your name" required>
                </div>
                <div class="form-group">
                    <label for="email">Your Email</label>
                    <input type="email" id="email" placeholder="Enter your email" required>
                </div>
                <div class="form-group">
                    <label for="message">Your Message</label>
                    <textarea id="message" rows="5" placeholder="Write your message here..." required></textarea>
                </div>
                <button type="submit" class="submit-btn">Send Message</button>
            </form>
        </div>
    </section>

    <!-- AI Chatbot Widget -->
    <div class="chatbot-container">
        <div class="chatbot-box" id="chatbotBox">
            <div class="chatbot-header">Prime AI Assistant</div>
            <div class="chatbot-body">Hello! How can I help you scale your business today?</div>
        </div>
        <button class="chatbot-btn" onclick="toggleChat()">💬</button>
    </div>

    <!-- Footer -->
    <footer>
        <p>&copy; 2026 <a href="https://web-hub-code.github.io/primesolutions/" target="_blank">Prime Solutions</a>. All rights reserved.</p>
    </footer>

    <script>
        function toggleTheme() {
            const body = document.body;
            const currentTheme = body.getAttribute('data-theme');
            body.setAttribute('data-theme', currentTheme === 'dark' ? 'light' : 'dark');
        }

        function toggleChat() {
            const box = document.getElementById('chatbotBox');
            box.style.display = box.style.display === 'block' ? 'none' : 'block';
        }
    </script>

</body>
</html>
