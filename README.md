<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prime Solutions - Digital Agency</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background-color: #f9fafb;
            color: #1f2937;
            overflow-x: hidden;
        }

        /* Header / Navbar */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 50px;
            background-color: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
            position: sticky;
            top: 0;
            z-index: 1000;
            animation: slideDown 0.8s ease-in-out;
        }

        @keyframes slideDown {
            from { transform: translateY(-100%); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .logo {
            font-size: 24px;
            font-weight: bold;
            color: #2563eb;
            text-decoration: none;
            transition: transform 0.3s;
        }

        .logo:hover {
            transform: scale(1.05);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 25px;
        }

        nav ul li a {
            text-decoration: none;
            color: #4b5563;
            font-weight: 500;
            position: relative;
            transition: color 0.3s;
        }

        nav ul li a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background-color: #2563eb;
            transition: width 0.3s ease;
        }

        nav ul li a:hover::after {
            width: 100%;
        }

        nav ul li a:hover {
            color: #2563eb;
        }

        .cta-btn {
            background-color: #2563eb;
            color: white;
            padding: 10px 20px;
            border-radius: 6px;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            box-shadow: 0 4px 12px rgba(37, 99, 235, 0.2);
        }

        .cta-btn:hover {
            background-color: #1d4ed8;
            transform: translateY(-2px);
            box-shadow: 0 6px 16px rgba(37, 99, 235, 0.4);
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
            animation: fadeIn 1.2s ease-in-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .hero h1 {
            font-size: 52px;
            margin-bottom: 20px;
            animation: fadeInUp 1s ease-out;
        }

        .hero p {
            font-size: 18px;
            max-width: 650px;
            margin-bottom: 35px;
            line-height: 1.6;
            color: #e2e8f0;
            animation: fadeInUp 1.2s ease-out;
        }

        @keyframes fadeInUp {
            from { transform: translateY(30px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .hero-btn {
            background-color: #ffffff;
            color: #2563eb;
            padding: 14px 35px;
            border-radius: 30px;
            text-decoration: none;
            font-size: 16px;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }

        .hero-btn:hover {
            background-color: #f8fafc;
            transform: translateY(-4px) scale(1.05);
            box-shadow: 0 8px 25px rgba(0,0,0,0.3);
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
            background: white;
            padding: 25px;
            border-radius: 12px;
            text-align: center;
            box-shadow: 0 10px 25px rgba(0,0,0,0.06);
            border: 1px solid #e5e7eb;
        }

        .stat-card h3 {
            font-size: 32px;
            color: #2563eb;
            margin-bottom: 5px;
        }

        .stat-card p {
            color: #6b7280;
            font-size: 14px;
            font-weight: 500;
        }

        /* Services Section */
        .services, .portfolio, .contact {
            padding: 90px 50px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 36px;
            color: #1e3a8a;
            margin-bottom: 60px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            width: 80px;
            height: 4px;
            background-color: #2563eb;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 2px;
        }

        .services-grid, .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 35px;
        }

        .service-card, .portfolio-card {
            background: #ffffff;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 6px 20px rgba(0,0,0,0.04);
            border: 1px solid #e5e7eb;
            transition: all 0.4s cubic-bezier(0.165, 0.84, 0.44, 1);
        }

        .service-card img, .portfolio-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .service-card:hover, .portfolio-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(37, 99, 235, 0.12);
        }

        .service-card:hover img, .portfolio-card:hover img {
            transform: scale(1.1);
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
            color: #6b7280;
            line-height: 1.6;
            font-size: 15px;
            margin-bottom: 15px;
        }

        .project-link {
            display: inline-block;
            color: #2563eb;
            font-weight: 600;
            text-decoration: none;
            transition: color 0.3s;
        }

        .project-link:hover {
            color: #1d4ed8;
            text-decoration: underline;
        }

        /* Contact Section */
        .contact-container {
            background: white;
            padding: 50px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
            max-width: 700px;
            margin: 0 auto;
            border: 1px solid #e5e7eb;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: #374151;
        }

        .form-group input, .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #d1d5db;
            border-radius: 8px;
            font-size: 15px;
            outline: none;
            transition: border-color 0.3s;
        }

        .form-group input:focus, .form-group textarea:focus {
            border-color: #2563eb;
            box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
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
            transition: background-color 0.3s;
        }

        .submit-btn:hover {
            background-color: #1d4ed8;
        }

        /* Footer */
        footer {
            background-color: #1f2937;
            color: #9ca3af;
            text-align: center;
            padding: 40px 20px;
            margin-top: 80px;
        }

        footer p {
            font-size: 14px;
        }

        footer a {
            color: #60a5fa;
            text-decoration: none;
            transition: color 0.3s;
        }

        footer a:hover {
            color: #93c5fd;
            text-decoration: underline;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            header {
                padding: 15px 20px;
                flex-direction: column;
                gap: 15px;
            }

            nav ul {
                gap: 15px;
                flex-wrap: wrap;
                justify-content: center;
            }

            .hero h1 {
                font-size: 36px;
            }

            .services, .portfolio, .contact {
                padding: 50px 20px;
            }

            .contact-container {
                padding: 25px;
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
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
        <a href="#contact" class="cta-btn">Get Started</a>
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
                    <p>Custom, responsive, and high-performance websites built with modern technologies tailored to your brand[span_0](start_span)[span_0](end_span).</p>
                </div>
            </div>
            <div class="service-card">
                <img src="https://images.unsplash.com/photo-1581291518633-83b4ebd1d83e?auto=format&fit=crop&w=600&q=80" alt="UI/UX Design">
                <div class="card-content">
                    <h3>UI/UX Design</h3>
                    <p>Engaging user interfaces and seamless experiences designed to convert visitors into loyal customers[span_1](start_span)[span_1](end_span).</p>
                </div>
            </div>
            <div class="service-card">
                <img src="https://images.unsplash.com/photo-1551836022-d5d88e9218df?auto=format&fit=crop&w=600&q=80" alt="Digital Solutions">
                <div class="card-content">
                    <h3>Digital Solutions</h3>
                    <p>Scalable software integrations and automated workflows to boost your business efficiency and growth[span_2](start_span)[span_2](end_span).</p>
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
                    <a href="#" class="project-link">View Project &rarr;</a>
                </div>
            </div>
            <div class="portfolio-card">
                <img src="https://images.unsplash.com/photo-1507238691740-187a5b1d37b8?auto=format&fit=crop&w=600&q=80" alt="USHomeImprovements">
                <div class="card-content">
                    <h3>USHomeImprovements</h3>
                    <p>Professional home improvement landing page designed with clean HTML/CSS layouts and responsive elements.</p>
                    <a href="#" class="project-link">View Project &rarr;</a>
                </div>
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

    <!-- Footer -->
    <footer>
        <p>&copy; 2026 <a href="https://web-hub-code.github.io/primesolutions/" target="_blank">Prime Solutions</a>. All rights reserved.</p>
    </footer>

</body>
</html>
