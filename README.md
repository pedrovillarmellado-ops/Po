<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para Amanda 🌌</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background: radial-gradient(ellipse at bottom, #1B2735 0%, #090A0F 100%);
            height: 100vh;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Arial', sans-serif;
        }

        #nombre {
            color: white;
            font-size: 5rem;
            text-shadow: 0 0 20px #fff, 0 0 30px #74b9ff, 0 0 40px #74b9ff;
            z-index: 10;
            animation: flotar 3s ease-in-out infinite;
        }

        @keyframes flotar {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        /* Estrellas simples */
        .star {
            position: absolute;
            background: white;
            border-radius: 50%;
            opacity: 0.5;
            animation: parpadeo var(--d) infinite;
        }

        @keyframes parpadeo {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 1; }
        }
    </style>
</head>
<body onclick="tocarMusica()">

    <h1 id="nombre">Amanda</h1>

    <audio id="musica" loop>
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
    </audio>

    <script>
        // Crear estrellas aleatorias
        for (let i = 0; i < 150; i++) {
            let star = document.createElement('div');
            star.className = 'star';
            let size = Math.random() * 3 + 'px';
            star.style.width = size;
            star.style.height = size;
            star.style.top = Math.random() * 100 + 'vh';
            star.style.left = Math.random() * 100 + 'vw';
            star.style.setProperty('--d', Math.random() * 3 + 2 + 's');
            document.body.appendChild(star);
        }

        function tocarMusica() {
            document.getElementById('musica').play();
        }
    </script>
</body>
</html>

