<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy New Year Muskan</title>
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-pink: #ff758c;
            --dark-red: #e63946;
            --soft-white: rgba(255, 255, 255, 0.92);
        }

        body {
            margin: 0;
            height: 100vh;
            background: #000; /* Black background makes colors pop */
            background: radial-gradient(circle, #2d0b1d 0%, #000000 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: 'Poppins', sans-serif;
            overflow: hidden;
            cursor: pointer;
        }

        .card {
            background: var(--soft-white);
            padding: 50px 30px;
            border-radius: 30px;
            text-align: center;
            max-width: 450px;
            box-shadow: 0 0 50px rgba(230, 57, 70, 0.3);
            z-index: 10;
            position: relative;
            animation: cardEntrance 1.5s ease-out;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        h1 {
            font-family: 'Great Vibes', cursive;
            font-size: 56px;
            color: var(--dark-red);
            margin: 0;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }

        h2 {
            color: #333;
            font-weight: 600;
            letter-spacing: 2px;
            text-transform: uppercase;
            margin-bottom: 25px;
            font-size: 1.2rem;
        }

        p {
            font-size: 17px;
            color: #444;
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .heart-icon {
            font-size: 45px;
            color: var(--dark-red);
            display: inline-block;
            animation: pulse 1.2s infinite;
        }

        footer {
            margin-top: 30px;
            font-size: 15px;
            color: #666;
            font-style: italic;
        }

        /* Animations */
        @keyframes cardEntrance {
            from { opacity: 0; transform: scale(0.8) translateY(50px); }
            to { opacity: 1; transform: scale(1) translateY(0); }
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.25); }
            100% { transform: scale(1); }
        }

        /* Particle/Confetti Styles */
        .particle {
            position: absolute;
            border-radius: 50%;
            pointer-events: none;
            z-index: 5;
        }
    </style>
</head>
<body>

<div class="card">
    <h1>Happy New Year</h1>
    <h2>Muskan</h2>

    <p>
        Every moment with you is a gift.<br>
        As we step into 2026, I want you to know that my favorite place in the world is right by your side.
    </p>

    <div class="heart-icon">❤️</div>

    <p>
        Thank you for being my peace and my joy.<br>
        Let's make this year our best one yet!
    </p>

    <footer>
        Forever yours,<br>
        <strong>With all my love</strong>
    </footer>
</div>

<script>
    // Create floating particles
    function createParticle(x, y) {
        const particle = document.createElement('div');
        particle.className = 'particle';
        document.body.appendChild(particle);

        const size = Math.floor(Math.random() * 10 + 5);
        particle.style.width = `${size}px`;
        particle.style.height = `${size}px`;
        
        const colors = ['#ff758c', '#ffbe0b', '#fb5607', '#ff006e', '#8338ec'];
        particle.style.background = colors[Math.floor(Math.random() * colors.length)];
        
        const destinationX = x + (Math.random() - 0.5) * 300;
        const destinationY = y + (Math.random() - 0.5) * 300;

        particle.style.left = `${x}px`;
        particle.style.top = `${y}px`;

        const animation = particle.animate([
            { transform: 'translate(0, 0)', opacity: 1 },
            { transform: `translate(${destinationX - x}px, ${destinationY - y}px)`, opacity: 0 }
        ], {
            duration: 1000 + Math.random() * 1000,
            easing: 'cubic-bezier(0, .9, .57, 1)',
            fill: 'forwards'
        });

        animation.onfinish = () => particle.remove();
    }

    // Burst on click
    document.addEventListener('mousedown', (e) => {
        for (let i = 0; i < 20; i++) {
            createParticle(e.clientX, e.clientY);
        }
    });

    // Auto-generate some background magic
    setInterval(() => {
        const x = Math.random() * window.innerWidth;
        const y = Math.random() * window.innerHeight;
        for (let i = 0; i < 5; i++) {
            createParticle(x, y);
        }
    }, 800);
</script>

</body>
</html>
