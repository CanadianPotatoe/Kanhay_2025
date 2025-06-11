<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kanhay Patil - Engineering Student</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: white;
            color: #333;
            line-height: 1.6;
        }

        /* Simple animated dots background */
        .dots-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: radial-gradient(circle, rgba(21, 153, 87, 0.1) 1px, transparent 1px);
            background-size: 30px 30px;
            animation: dotMove 20s linear infinite;
            pointer-events: none;
        }

        @keyframes dotMove {
            0% { transform: translate(0, 0); }
            100% { transform: translate(30px, 30px); }
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            text-align: center;
            padding: 2rem 0;
        }

        .hero-title {
            font-size: clamp(2.5rem, 6vw, 4rem);
            font-weight: 700;
            color: #159957;
            margin-bottom: 1rem;
            opacity: 0;
            animation: slideUp 0.8s ease 0.2s forwards;
        }

        .hero-subtitle {
            font-size: 1.2rem;
            color: #666;
            max-width: 600px;
            margin: 0 auto 2rem;
            opacity: 0;
            animation: slideUp 0.8s ease 0.4s forwards;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            opacity: 0;
            animation: slideUp 0.8s ease 0.6s forwards;
        }

        .btn {
            display: inline-block;
            padding: 12px 24px;
            background: white;
            border: 2px solid #159957;
            color: #159957;
            text-decoration: none;
            font-weight: 500;
            border-radius: 6px;
            transition: all 0.3s ease;
        }

        .btn:hover {
            background: #159957;
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(21, 153, 87, 0.3);
        }

        @keyframes slideUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero-title,
        .hero-subtitle,
        .hero-buttons {
            transform: translateY(30px);
        }

        /* Projects Section */
        .projects {
            padding: 4rem 0;
        }

        .section-title {
            font-size: 2rem;
            font-weight: 600;
            color: #159957;
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 2px;
            background: #159957;
        }

        .project {
            background: white;
            border: 1px solid #e1e5e9;
            border-radius: 12px;
            padding: 2rem;
            margin-bottom: 2rem;
            transition: all 0.3s ease;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.04);
        }

        .project:hover {
            border-color: #159957;
            box-shadow: 0 8px 24px rgba(21, 153, 87, 0.1);
            transform: translateY(-4px);
        }

        .project-title {
            font-size: 1.4rem;
            font-weight: 600;
            color: #159957;
            margin-bottom: 1rem;
        }

        .project-description {
            color: #555;
            margin-bottom: 1.5rem;
            line-height: 1.7;
        }

        .project-links {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .project-link {
            color: #159957;
            text-decoration: none;
            font-weight: 500;
            padding: 6px 12px;
            border: 1px solid #159957;
            border-radius: 4px;
            font-size: 0.9rem;
            transition: all 0.3s ease;
        }

        .project-link:hover {
            background: #159957;
            color: white;
        }

        /* Contact Section */
        .contact {
            text-align: center;
            padding: 3rem 0 4rem;
            background: #f8f9fa;
            margin: 2rem -20px 0;
            border-radius: 16px;
        }

        .contact-title {
            font-size: 1.8rem;
            font-weight: 600;
            color: #159957;
            margin-bottom: 1rem;
        }

        .contact-text {
            color: #666;
            margin-bottom: 2rem;
            font-size: 1.1rem;
        }

        .contact-email {
            display: inline-block;
            color: #159957;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            padding: 12px 24px;
            border: 2px solid #159957;
            border-radius: 6px;
            transition: all 0.3s ease;
        }

        .contact-email:hover {
            background: #159957;
            color: white;
            transform: translateY(-2px);
        }

        /* Remove scroll animations - keep elements visible */
        .fade-in {
            opacity: 1;
            transform: translateY(0);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .container {
                padding: 0 15px;
            }

            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }

            .btn {
                width: 200px;
                text-align: center;
            }

            .project {
                padding: 1.5rem;
            }

            .project-links {
                flex-direction: column;
            }

            .project-link {
                text-align: center;
            }

            .contact {
                margin-left: -15px;
                margin-right: -15px;
                padding: 2rem 1rem 3rem;
            }
        }
    </style>
</head>
<body>
    <div class="dots-bg"></div>

    <div class="container">
        <!-- Hero Section -->
        <section class="hero">
            <h1 class="hero-title">Kanhay Patil</h1>
            <p class="hero-subtitle">
                Engineering student at Del Norte High School, passionate about mechanical and electrical engineering through the lens of computer science.
            </p>
            
            <div class="hero-buttons">
                <a href="https://www.linkedin.com/in/kanhay-patil-048a89368/" class="btn">LinkedIn Profile</a>
                <a href="/Kanhay_2025/csp/thelastone" class="btn">Experience</a>
                <a href="/Kanhay_2025/csp/showcase" class="btn">Showcases</a>
                <a href="/Kanhay_2025/csp/finalhomework" class="btn">Certificates</a>
            </div>
        </section>

        <!-- Projects Section -->
        <section class="projects">
            <h2 class="section-title fade-in">Featured Projects</h2>
            
            <div class="project fade-in">
                <h3 class="project-title">CrossWise</h3>
                <p class="project-description">
                    A smart web application providing intelligent border wait time predictions for San Ysidro and Otay Mesa ports. Uses machine learning algorithms trained on historical data to help users plan efficient border crossings. I developed the weather prediction component and designed a clean frontend interface for accessible data visualization.
                </p>
                <div class="project-links">
                    <a href="https://github.com/illuminati1618/CrossWise" class="project-link">Frontend Repository</a>
                    <a href="https://github.com/illuminati1618/CrossWise_backend" class="project-link">Backend Repository</a>
                </div>
            </div>

            <div class="project fade-in">
                <h3 class="project-title">Neptune</h3>
                <p class="project-description">
                    A comprehensive CRUD system with real-time theme customization capabilities. Built dynamic JavaScript interfaces, custom CSS generation, Flask route handling, and database integration. Features automated theme creation on user signup and live updates through asynchronous requests, deployed on AWS infrastructure.
                </p>
                <div class="project-links">
                    <a href="https://github.com/DNHS-Neptune/neptune_frontend" class="project-link">Frontend Repository</a>
                    <a href="https://github.com/DNHS-Neptune/neptune_backend" class="project-link">Backend Repository</a>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section class="contact fade-in">
            <h2 class="contact-title">Get in Touch</h2>
            <p class="contact-text">
                Interested in collaborating or learning more about my projects? Let's connect!
            </p>
            <a href="mailto:kanhay.patil@gmail.com" class="contact-email">kanhay.patil@gmail.com</a>
        </section>
    </div>

    <script>
        // Script section kept minimal - no scroll animations
    </script>
</body>
</html>