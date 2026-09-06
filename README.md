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
        }

        /* Header / Navbar */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 50px;
            background-color: #ffffff;
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
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
            gap: 30px;
        }

        nav ul li a {
            text-decoration: none;
            color: #4b5563;
            font-weight: 500;
            transition: color 0.3s;
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
            padding: 120px 20px;
            background: linear-gradient(135deg, #eff6ff 0%, #dbeafe 100%);
        }

        .hero h1 {
            font-size: 48px;
            color: #1e3a8a;
            margin-bottom: 20px;
        }

        .hero p {
            font-size: 18px;
            color: #4b5563;
            max-width: 600px;
            margin-bottom: 30px;
            line-height: 1.6;
        }

        .hero-btn {
            background-color: #2563eb;
            color: white;
            padding: 12px 30px;
            border-radius: 6px;
            text-decoration: none;
            font-size: 16px;
            font-weight: bold;
            transition: background 0.3s;
        }

        .hero-btn:hover {
            background-color: #1d4ed8;
        }

        /* Services Section */
        .services {
            padding: 80px 50px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 32px;
            color: #1e3a8a;
            margin-bottom: 50px;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .service-card {
            background: #ffffff;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.02);
            border: 1px solid #e5e7eb;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .service-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px rgba(0,0,0,0.05);
        }

        .service-card h3 {
            font-size: 20px;
            color: #2563eb;
            margin-bottom: 15px;
        }

        .service-card p {
            color: #6b7280;
            line-height: 1.5;
        }

        /* Footer */
        footer {
            background-color: #1f2937;
            color: #9ca3af;
            text-align: center;
            padding: 30px 20px;
            margin-top: 50px;
        }

        footer p {
            font-size: 14px;
        }

        footer a {
            color: #60a5fa;
            text-decoration: none;
        }

        footer a:hover {
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
            }

            .hero h1 {
                font-size: 32px;
            }

            .services {
                padding: 40px 20px;
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
                <li><a href="#">About</a></li>
                <li><a href="#services">Contact</a></li>
            </ul>
        </nav>
        <a href="#services" class="cta-btn">Get Started</a>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <h1>Welcome to Prime Solutions</h1>
        <p>We provide the best digital solutions to help your business grow and succeed in the modern competitive world.</p>
        <a href="#services" class="hero-btn">Explore Services</a>
    </section>

    <!-- Services Section -->
    <section class="services" id="services">
        <h2 class="section-title">What We Offer</h2>
        <div class="services-grid">
            <div class="service-card">
                <h3>Web Development</h3>
                <p>Custom, responsive, and high-performance websites built with modern technologies tailored to your brand[span_0](start_span)[span_0](end_span).</p>
            </div>
            <div class="service-card">
                <h3>UI/UX Design</h3>
                <p>Engaging user interfaces and seamless experiences designed to convert visitors into loyal customers[span_1](start_span)[span_1](end_span).</p>
            </div>
            <div class="service-card">
                <h3>Digital Solutions</h3>
                <p>Scalable software integrations and automated workflows to boost your business efficiency and growth[span_2](start_span)[span_2](end_span).</p>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2026 <a href="https://web-hub-code.github.io/primesolutions/" target="_blank">Prime Solutions</a>. All rights reserved.</p>
    </footer>

</body>
</html>
