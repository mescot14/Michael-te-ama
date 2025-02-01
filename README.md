<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¿Quieres ser mi Valentín, mi muñequita?</title>
    <style>
        /* Estilos generales */
        body {
            text-align: center;
            background-color: #ffebf0;
            font-family: Arial, sans-serif;
            color: #d63384;
            overflow: hidden;
        }
        
        /* Contenedor principal */
        .container {
            margin-top: 100px;
            position: relative;
            z-index: 10;
        }

        /* Animación de escritura */
        .typing-text {
            font-size: 36px;
            font-weight: bold;
            display: inline-block;
            border-right: 3px solid #d63384;
            white-space: nowrap;
            overflow: hidden;
            width: 0;
            animation: typing 3s steps(30, end) forwards, blink-caret 0.75s infinite;
        }

        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }

        @keyframes blink-caret {
            50% { border-color: transparent; }
        }

        /* Botones con animación */
        .buttons {
            margin-top: 20px;
        }
        .btn {
            font-size: 20px;
            padding: 12px 24px;
            margin: 10px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: 0.3s;
        }
        .yes {
            background-color: #ff4081;
            color: white;
            animation: heartbeat 1.5s infinite;
        }
        .no {
            background-color: #ccc;
            color: black;
        }
        .yes:hover {
            background-color: #d81b60;
        }
        .no:hover {
            background-color: #999;
        }

        @keyframes heartbeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        /* Animación de corazones flotando */
        .heart {
            position: absolute;
            color: #ff4081;
            font-size: 20px;
            opacity: 0.7;
            animation: float 5s linear infinite;
        }

        @keyframes float {
            0% { transform: translateY(0); opacity: 0.7; }
            50% { opacity: 1; }
            100% { transform: translateY(-100vh); opacity: 0; }
        }

    </style>
</head>
<body>

    <div class="container">
        <h1 class="typing-text">💖 ¿Quieres ser mi Valentín, mi muñequita? 💖</h1>
        <p>Hoy quiero preguntarte algo muy especial...</p>
        <div class="buttons">
            <button class="btn yes" onclick="aceptar()">✔️ Sí, me encantaría</button>
            <button class="btn no" onclick="rechazar()">💭 Déjame pensarlo...</button>
        </div>
        <p id="respuesta"></p>
    </div>

    <script>
        function aceptar() {
            document.getElementById("respuesta").innerHTML = "😍 ¡Sabía que dirías sí! Será un día increíble ❤️";
        }
        function rechazar() {
            document.getElementById("respuesta").innerHTML = "😢 Bueno... pero yo sé que en el fondo quieres decir sí 💕";
        }

        // Generar corazones flotantes
        function crearCorazon() {
            const heart = document.createElement("div");
            heart.innerHTML = "❤️";
            heart.classList.add("heart");
            document.body.appendChild(heart);

            const tamaño = Math.random() * 20 + 10 + "px";
            heart.style.left = Math.random() * window.innerWidth + "px";
            heart.style.fontSize = tamaño;

            const duracion = Math.random() * 5 + 3 + "s";
            heart.style.animationDuration = duracion;

            setTimeout(() => {
                heart.remove();
            }, 5000);
        }

        setInterval(crearCorazon, 500);
    </script>

</body>
</html>
