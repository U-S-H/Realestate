<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prime Solutions</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #f9f9f9;
            color: #333;
        }

        /* Header / Navbar */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 50px;
            background-color: #ffffff;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        .logo {
            font-size: 24px;
            font-weight: bold;
            color: #2563eb;
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
            border-radius: 5px;
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
            padding: 100px 20px;
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
        }

        .hero-btn {
            background-color: #2563eb;
            color: white;
            padding: 12px 30px;
            border-radius: 5px;
            text-decoration: none;
            font-size: 16px;
            font-weight: bold;
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
        }
    </style>
</head>
<body>

    <header>
        <div class="logo">Prime Solutions</div>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">Services</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
        <a href="#" class="cta-btn">Get Started</a>
    </header>

    <section class="hero">
        <h1>Welcome to Prime Solutions</h1>
        <p>We provide the best digital solutions to help your business grow and succeed in the modern world.</p>
        <a href="#" class="hero-btn">Explore Services</a>
    </section>

</body>
</html>
