# username.github.io-
[Building Website with Prompts.html](https://github.com/user-attachments/files/25081738/Building.Website.with.Prompts.html)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Irving Lopez — Systems Consultant & Product Manager</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@300;400;500;600&family=Urbanist:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --color-black: #0a0a0a;
            --color-charcoal: #1a1a1a;
            --color-grey-dark: #404040;
            --color-grey-mid: #909090;
            --color-grey-light: #d4d4d4;
            --color-white: #fafafa;
            --color-accent: #2a2a2a;
            
            --font-display: 'Urbanist', sans-serif;
            --font-body: 'DM Sans', sans-serif;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            font-family: var(--font-body);
            background: var(--color-black);
            color: var(--color-white);
            line-height: 1.6;
            font-weight: 300;
            overflow-x: hidden;
        }
        
        /* Animated grain texture overlay */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                radial-gradient(circle at 20% 50%, rgba(42, 42, 42, 0.03) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(255, 255, 255, 0.02) 0%, transparent 50%);
            pointer-events: none;
            z-index: 1;
        }
        
        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 0 2rem;
            position: relative;
            z-index: 2;
        }
        
        /* Header / Hero Section */
        header {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            padding: 8rem 0 4rem;
        }
        
        .hero-content {
            opacity: 0;
            animation: fadeInUp 1.2s ease-out 0.3s forwards;
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
        
        .label {
            font-size: 0.75rem;
            letter-spacing: 0.2em;
            text-transform: uppercase;
            color: var(--color-grey-mid);
            font-weight: 400;
            margin-bottom: 1.5rem;
            display: inline-block;
        }
        
        h1 {
            font-family: var(--font-display);
            font-size: clamp(3rem, 8vw, 5.5rem);
            font-weight: 300;
            letter-spacing: -0.03em;
            line-height: 1.1;
            margin-bottom: 1.5rem;
            color: var(--color-white);
        }
        
        h1 strong {
            font-weight: 700;
        }
        
        .subtitle {
            font-size: clamp(1.1rem, 2vw, 1.4rem);
            color: var(--color-grey-light);
            max-width: 700px;
            margin-bottom: 2rem;
            font-weight: 300;
            line-height: 1.7;
        }
        
        .location {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            color: var(--color-grey-mid);
            font-size: 0.95rem;
            margin-bottom: 3rem;
        }
        
        .location::before {
            content: '';
            width: 6px;
            height: 6px;
            background: var(--color-grey-mid);
            border-radius: 50%;
        }
        
        /* Expertise Tags */
        .expertise {
            display: flex;
            flex-wrap: wrap;
            gap: 0.75rem;
            margin-bottom: 4rem;
        }
        
        .tag {
            padding: 0.5rem 1.25rem;
            background: var(--color-charcoal);
            border: 1px solid var(--color-grey-dark);
            border-radius: 2rem;
            font-size: 0.9rem;
            color: var(--color-grey-light);
            font-weight: 400;
            transition: all 0.3s ease;
        }
        
        .tag:hover {
            background: var(--color-accent);
            border-color: var(--color-grey-mid);
            color: var(--color-white);
            transform: translateY(-2px);
        }
        
        /* CTA Button */
        .cta-button {
            display: inline-flex;
            align-items: center;
            gap: 0.75rem;
            padding: 1rem 2rem;
            background: var(--color-white);
            color: var(--color-black);
            text-decoration: none;
            font-weight: 500;
            border-radius: 0.5rem;
            transition: all 0.3s ease;
            font-size: 1rem;
        }
        
        .cta-button:hover {
            background: var(--color-grey-light);
            transform: translateX(4px);
        }
        
        .cta-button::after {
            content: '→';
            font-size: 1.2rem;
            transition: transform 0.3s ease;
        }
        
        .cta-button:hover::after {
            transform: translateX(4px);
        }
        
        /* Section Styling */
        section {
            padding: 6rem 0;
            border-top: 1px solid var(--color-grey-dark);
        }
        
        h2 {
            font-family: var(--font-display);
            font-size: clamp(2rem, 4vw, 2.8rem);
            font-weight: 600;
            letter-spacing: -0.02em;
            margin-bottom: 2.5rem;
            color: var(--color-white);
        }
        
        .about-content {
            max-width: 750px;
            font-size: 1.1rem;
            line-height: 1.8;
            color: var(--color-grey-light);
        }
        
        .about-content p {
            margin-bottom: 1.5rem;
        }
        
        .about-content ul {
            list-style: none;
            margin: 2rem 0;
            padding-left: 0;
        }
        
        .about-content li {
            padding-left: 2rem;
            position: relative;
            margin-bottom: 1rem;
        }
        
        .about-content li::before {
            content: '—';
            position: absolute;
            left: 0;
            color: var(--color-grey-mid);
        }
        
        /* Services Grid */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }
        
        .service-card {
            padding: 2.5rem;
            background: var(--color-charcoal);
            border: 1px solid var(--color-grey-dark);
            border-radius: 1rem;
            transition: all 0.4s ease;
        }
        
        .service-card:hover {
            background: var(--color-accent);
            border-color: var(--color-grey-mid);
            transform: translateY(-8px);
        }
        
        .service-card h3 {
            font-family: var(--font-display);
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 1rem;
            color: var(--color-white);
        }
        
        .service-card p {
            color: var(--color-grey-light);
            line-height: 1.7;
        }
        
        /* Social Links */
        .social-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-top: 3rem;
        }
        
        .social-link {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1.5rem;
            background: var(--color-charcoal);
            border: 1px solid var(--color-grey-dark);
            border-radius: 0.75rem;
            text-decoration: none;
            color: var(--color-white);
            transition: all 0.3s ease;
        }
        
        .social-link:hover {
            background: var(--color-accent);
            border-color: var(--color-grey-mid);
            transform: translateX(8px);
        }
        
        .social-icon {
            width: 40px;
            height: 40px;
            background: var(--color-grey-dark);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 600;
            font-size: 0.9rem;
            flex-shrink: 0;
        }
        
        .social-details {
            flex: 1;
        }
        
        .social-name {
            font-weight: 500;
            font-size: 1rem;
            margin-bottom: 0.25rem;
        }
        
        .social-handle {
            font-size: 0.85rem;
            color: var(--color-grey-mid);
        }
        
        /* Footer */
        footer {
            padding: 4rem 0 3rem;
            border-top: 1px solid var(--color-grey-dark);
            text-align: center;
        }
        
        .footer-content {
            color: var(--color-grey-mid);
            font-size: 0.9rem;
        }
        
        .footer-content a {
            color: var(--color-grey-light);
            text-decoration: none;
            border-bottom: 1px solid transparent;
            transition: border-color 0.3s ease;
        }
        
        .footer-content a:hover {
            border-bottom-color: var(--color-grey-light);
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .container {
                padding: 0 1.5rem;
            }
            
            header {
                padding: 6rem 0 3rem;
            }
            
            section {
                padding: 4rem 0;
            }
            
            .services-grid,
            .social-grid {
                grid-template-columns: 1fr;
            }
            
            .expertise {
                gap: 0.5rem;
            }
            
            .tag {
                font-size: 0.85rem;
                padding: 0.4rem 1rem;
            }
        }
        
        /* Scroll reveal animations */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease-out;
        }
        
        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="hero-content">
                <span class="label">Systems Consultant & Product Manager</span>
                <h1>Irving <strong>Lopez</strong></h1>
                <p class="subtitle">
                    Build workflows that scale, eliminate bottlenecks, and drive real results through monday.com implementation and systems design for growing businesses.
                </p>
                <div class="location">
                    <span>Nashville, TN</span>
                </div>
                <div class="expertise">
                    <span class="tag">monday.com Expert</span>
                    <span class="tag">Product Management</span>
                    <span class="tag">Workflow Automation</span>
                    <span class="tag">Systems Design</span>
                    <span class="tag">Process Optimization</span>
                </div>
                <a href="#contact" class="cta-button">Let's Connect</a>
            </div>
        </div>
    </header>

    <section id="about">
        <div class="container">
            <div class="about-content reveal">
                <h2>About Me</h2>
                <p>
                    I'm Irving Lopez — a systems consultant based in Nashville specializing in monday.com implementations and operational optimization. I help businesses across the U.S. build custom work management systems that eliminate chaos and create clarity.
                </p>
                <p>
                    From project tracking to workflow automation, I design monday.com workspaces that scale with your business — backed by AI tools and integrations that actually deliver results.
                </p>
                <p>
                    As a product manager at Ramsey Solutions, I'm passionate about helping businesses thrive by solving real customer problems, boosting efficiency, and driving revenue growth. I also run <strong>Streamline</strong>, where I create workflows and integrations for businesses to simplify operations and empower teams to do their best work.
                </p>
                <p>
                    Originally from New Mexico, I now call Tennessee home, where I live with my beautiful wife and two incredible kiddos, embracing a bit of southern charm while staying true to our roots.
                </p>
                
                <h3 style="margin-top: 3rem; margin-bottom: 1.5rem; font-size: 1.5rem; font-weight: 600;">How I Can Help</h3>
                <ul>
                    <li>Build smart, efficient workflows that make work simpler</li>
                    <li>Create solutions that meet real needs and support business growth</li>
                    <li>Use tech and process improvements to save time and drive results</li>
                </ul>
                
                <p style="margin-top: 2rem;">
                    If you'd like to talk about product, explore how Streamline can help, or just connect, let's chat and see how we can create clarity and success for your business!
                </p>
            </div>
        </div>
    </section>

    <section id="services" style="background: var(--color-charcoal);">
        <div class="container">
            <h2 class="reveal">What I Do</h2>
            <div class="services-grid">
                <div class="service-card reveal">
                    <h3>monday.com Implementation</h3>
                    <p>Custom workspace design, automation setup, and integration that transforms how your team collaborates and delivers results.</p>
                </div>
                <div class="service-card reveal">
                    <h3>Systems Design</h3>
                    <p>Build scalable operational frameworks that eliminate bottlenecks and create sustainable growth for your business.</p>
                </div>
                <div class="service-card reveal">
                    <h3>Product Management</h3>
                    <p>Strategic product development focused on solving real customer problems while driving efficiency and revenue.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="contact">
        <div class="container">
            <h2 class="reveal">Connect With Me</h2>
            <div class="social-grid">
                <a href="https://www.linkedin.com/in/irving-lop" target="_blank" rel="noopener" class="social-link reveal">
                    <div class="social-icon">in</div>
                    <div class="social-details">
                        <div class="social-name">LinkedIn</div>
                        <div class="social-handle">irving-lop</div>
                    </div>
                </a>
                
                <a href="https://www.upwork.com/freelancers/~010c369f358457a4b2?mp_source=share" target="_blank" rel="noopener" class="social-link reveal">
                    <div class="social-icon">Up</div>
                    <div class="social-details">
                        <div class="social-name">Upwork</div>
                        <div class="social-handle">Freelance Profile</div>
                    </div>
                </a>
                
                <a href="https://www.instagram.com/irving_lopez14/profilecard/?igsh=MWt1eHBueTJzZmNwdQ==" target="_blank" rel="noopener" class="social-link reveal">
                    <div class="social-icon">IG</div>
                    <div class="social-details">
                        <div class="social-name">Instagram</div>
                        <div class="social-handle">@irving_lopez14</div>
                    </div>
                </a>
                
                <a href="https://www.facebook.com/share/18WpqXZXTE/?mibextid=LQQJ4d" target="_blank" rel="noopener" class="social-link reveal">
                    <div class="social-icon">FB</div>
                    <div class="social-details">
                        <div class="social-name">Facebook</div>
                        <div class="social-handle">Profile</div>
                    </div>
                </a>
                
                <a href="https://www.fastexpert.com/pros-technology/irving-lopez-102263/" target="_blank" rel="noopener" class="social-link reveal">
                    <div class="social-icon">FE</div>
                    <div class="social-details">
                        <div class="social-name">FastExpert</div>
                        <div class="social-handle">Professional Profile</div>
                    </div>
                </a>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="footer-content">
                <p>© 2025 Irving Lopez. Based in Nashville, TN.</p>
                <p style="margin-top: 0.5rem;">Systems Consultant • Product Manager • monday.com Expert</p>
            </div>
        </div>
    </footer>

    <script>
        // Smooth scroll reveal animations
        const observerOptions = {
            threshold: 0.15,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach((entry, index) => {
                if (entry.isIntersecting) {
                    setTimeout(() => {
                        entry.target.classList.add('active');
                    }, index * 100);
                }
            });
        }, observerOptions);

        document.querySelectorAll('.reveal').forEach((element) => {
            observer.observe(element);
        });
    </script>
</body>
</html>
