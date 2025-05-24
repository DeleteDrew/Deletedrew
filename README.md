<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Membership - Simple Membership</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', serif;
            line-height: 1.7;
            color: #2d3436;
            background: #2d5016;
            min-height: 100vh;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Simple Header */
        header {
            padding: 2rem 0;
            text-align: center;
        }

        .logo {
            font-size: 2.5rem;
            font-weight: normal;
            color: white;
            text-shadow: 0 2px 4px rgba(0,0,0,0.1);
            margin-bottom: 0.5rem;
        }

        .tagline {
            color: rgba(255,255,255,0.9);
            font-size: 1.1rem;
            font-style: italic;
        }

        /* Main Content */
        .main-content {
            background: rgba(74, 124, 89, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 3rem;
            margin: 2rem 0;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .intro {
            text-align: center;
            margin-bottom: 3rem;
        }

        .intro h1 {
            font-size: 2rem;
            color: #f5f5dc;
            margin-bottom: 1rem;
            font-weight: normal;
        }

        .intro p {
            font-size: 1.2rem;
            color: #f5f5dc;
            max-width: 600px;
            margin: 0 auto 2rem;
        }

        /* Simple Features */
        .features {
            margin: 3rem 0;
        }

        .features h2 {
            text-align: center;
            font-size: 1.8rem;
            color: #f5f5dc;
            margin-bottom: 2rem;
            font-weight: normal;
        }

        .feature-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            list-style: none;
        }

        .feature-list li {
            background: #4a7c59;
            padding: 1.5rem;
            border-radius: 15px;
            border-left: 4px solid #f5f5dc;
            font-size: 1.1rem;
            color: #f5f5dc;
        }

        .feature-emoji {
            font-size: 1.5rem;
            margin-right: 0.5rem;
        }

        /* Simple Pricing */
        .pricing {
            text-align: center;
            margin: 3rem 0;
            padding: 2rem;
            background: #4a7c59;
            border-radius: 20px;
            color: white;
        }

        .pricing h2 {
            font-size: 1.8rem;
            margin-bottom: 1rem;
            font-weight: normal;
        }

        .price-display {
            font-size: 4rem;
            font-weight: bold;
            margin: 1rem 0;
            text-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .price-period {
            font-size: 1.2rem;
            opacity: 0.9;
            margin-bottom: 1rem;
        }

        .service-fee {
            background: rgba(255,255,255,0.2);
            padding: 1rem;
            border-radius: 10px;
            margin: 2rem 0;
            border: 2px dashed rgba(255,255,255,0.4);
        }

        .cta-button {
            background: #4a7c59;
            color: #f5f5dc;
            padding: 1rem 3rem;
            border: none;
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            margin-top: 1rem;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.2);
        }

        /* Simple Footer */
        footer {
            text-align: center;
            padding: 2rem;
            color: rgba(255,255,255,0.8);
            font-size: 0.9rem;
        }

        footer a {
            color: rgba(255,255,255,0.9);
            text-decoration: none;
            margin: 0 1rem;
        }

        footer a:hover {
            color: white;
        }

        /* Logo above price */
        .price-logo {
            font-size: 3rem;
            margin-bottom: 1rem;
            display: block;
            filter: drop-shadow(0 2px 4px rgba(0,0,0,0.2));
        }
        .bunny {
            position: fixed;
            bottom: 20px;
            left: -60px;
            font-size: 2.5rem;
            z-index: 1000;
            opacity: 0;
            animation: bunnyHop 8s ease-in-out 2s 1 forwards;
        }

        @keyframes bunnyHop {
            0% {
                left: -60px;
                bottom: 20px;
                opacity: 1;
                transform: rotate(0deg);
            }
            10% {
                bottom: 60px;
                transform: rotate(-5deg);
            }
            15% {
                bottom: 20px;
                transform: rotate(0deg);
            }
            25% {
                bottom: 70px;
                transform: rotate(5deg);
            }
            30% {
                bottom: 20px;
                transform: rotate(0deg);
            }
            40% {
                bottom: 50px;
                transform: rotate(-3deg);
            }
            45% {
                bottom: 20px;
                transform: rotate(0deg);
            }
            55% {
                bottom: 80px;
                transform: rotate(8deg);
            }
            60% {
                bottom: 20px;
                transform: rotate(0deg);
            }
            70% {
                bottom: 45px;
                transform: rotate(-2deg);
            }
            75% {
                bottom: 20px;
                transform: rotate(0deg);
            }
            85% {
                bottom: 65px;
                transform: rotate(4deg);
            }
            90% {
                bottom: 20px;
                transform: rotate(0deg);
            }
            100% {
                left: calc(100vw + 60px);
                bottom: 20px;
                opacity: 0;
                transform: rotate(0deg);
            }
        }
        .leaf {
            position: absolute;
            opacity: 0.1;
            font-size: 2rem;
            animation: float 6s ease-in-out infinite;
            pointer-events: none;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(10deg); }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .main-content {
                padding: 2rem;
                margin: 1rem 0;
            }
            
            .intro h1 {
                font-size: 1.8rem;
            }
            
            .price-display {
                font-size: 3rem;
            }
            
            .feature-list {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Hopping Bunny -->
    <div class="bunny">🐰</div>

    <!-- Floating Nature Elements -->
    <div class="leaf" style="top: 10%; left: 10%;">🍃</div>
    <div class="leaf" style="top: 20%; right: 15%; animation-delay: -2s;">🌿</div>
    <div class="leaf" style="top: 60%; left: 5%; animation-delay: -4s;">🍃</div>
    <div class="leaf" style="bottom: 20%; right: 10%; animation-delay: -1s;">🌿</div>

    <!-- Header -->
    <header>
        <div class="container">
            <h1 class="logo">Membership</h1>
            <p class="tagline">Simple subscription, just $0.99</p>
        </div>
    </header>

    <!-- Main Content -->
    <main class="container">
        <div class="main-content">
            
            <!-- Introduction -->
            <section class="intro">
                <h1>Simple subscription service</h1>
                <p>Join our community with a straightforward monthly subscription.</p>
            </section>

            <!-- Simple Pricing -->
            <section class="pricing">
                <h2>One simple price</h2>
                <div class="price-display">$0.99</div>
                <div class="price-period">per month</div>
                
                <div class="service-fee">
                    <strong>Just a service fee</strong><br>
                    <small>What you see is what you pay</small>
                </div>

                <p style="margin: 1rem 0; opacity: 0.9;">
                    Cancel anytime • No contracts
                </p>

                <button class="cta-button" onclick="goToPayment()">
                    Start your journey
                </button>
            </section>

        </div>
    </main>

    <!-- Simple Footer -->
    <footer>
        <div class="container">
            <p>
                <a href="#">Help</a>
                <a href="#">Privacy</a>
                <a href="#">Terms</a>
                <a href="#">Contact</a>
            </p>
            <p style="margin-top: 1rem;">
                Membership • Made with care for simple living
            </p>
        </div>
    </footer>

    <script>
        function goToPayment() {
            // Redirect to payment page
            window.location.href = 'payment.html';
        }

        // Add gentle scroll behavior
        document.documentElement.style.scrollBehavior = 'smooth';

        // Simple entrance animation
        window.addEventListener('load', function() {
            const mainContent = document.querySelector('.main-content');
            mainContent.style.opacity = '0';
            mainContent.style.transform = 'translateY(30px)';
            mainContent.style.transition = 'opacity 1s ease, transform 1s ease';
            
            setTimeout(() => {
                mainContent.style.opacity = '1';
                mainContent.style.transform = 'translateY(0)';
            }, 300);
        });
    </script>
</body>
</html>
