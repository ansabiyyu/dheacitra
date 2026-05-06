# dheacitra
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>terimakasih.</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #000000;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Times New Roman', Times, serif;
            overflow: hidden;
            position: relative;
        }

        .thank-you {
            font-size: 8rem;
            font-weight: 400;
            color: #ffffff;
            text-align: center;
            letter-spacing: 0.08em;
            text-transform: lowercase; /* SEMUA HURUF KECIL */
            text-shadow: 
                0 0 10px #ffffff,
                0 0 20px #ffffff,
                0 0 30px #ffffff,
                0 0 40px #ffff00,
                0 0 70px #ffff00;
            animation: glow 2s ease-in-out infinite alternate;
            cursor: pointer;
            user-select: none;
        }

        @keyframes glow {
            from {
                text-shadow: 
                    0 0 10px #ffffff,
                    0 0 20px #ffffff,
                    0 0 30px #ffffff,
                    0 0 40px #ffff00,
                    0 0 70px #ffff00;
            }
            to {
                text-shadow: 
                    0 0 20px #ffffff,
                    0 0 30px #ffffff,
                    0 0 50px #ffffff,
                    0 0 60px #ffff00,
                    0 0 100px #ffff00;
            }
        }

        /* Efek klik */
        .thank-you:active {
            transform: scale(0.95);
            transition: transform 0.1s;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .thank-you {
                font-size: 4rem;
                letter-spacing: 0.06em;
            }
        }

        @media (max-width: 480px) {
            .thank-you {
                font-size: 3rem;
                letter-spacing: 0.04em;
            }
        }

        /* Efek mouse move - kuning neon */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at var(--x, 50%) var(--y, 50%), rgba(255, 255, 0, 0.2) 0%, transparent 50%);
            pointer-events: none;
            z-index: 9999;
            opacity: 0;
            transition: opacity 0.3s;
        }

        body:hover::before {
            opacity: 1;
        }
    </style>
</head>
<body>
    <div class="thank-you" id="thankYouText">terimakasih.</div>

    <script>
        // Efek mouse follow kuning neon
        document.addEventListener('mousemove', (e) => {
            document.body.style.setProperty('--x', e.clientX + 'px');
            document.body.style.setProperty('--y', e.clientY + 'px');
        });

        // Efek klik
        document.getElementById('thankYouText').addEventListener('click', function() {
            this.style.transform = 'scale(1.1)';
            setTimeout(() => {
                this.style.transform = 'scale(1)';
            }, 150);
        });

        // Fullscreen on double click
        document.addEventListener('dblclick', () => {
            if (document.fullscreenElement) {
                document.exitFullscreen();
            } else {
                document.documentElement.requestFullscreen();
            }
        });
    </script>
</body>
</html>