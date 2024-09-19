<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Girasol y Frases Lindas</title>
    <style>
        body {
            background-color: #f0f8ff;
            font-family: 'Arial', sans-serif;
            text-align: center;
            color: #333;
            margin: 0;
            padding: 0;
        }

        h1 {
            margin-top: 20px;
            color: #ffa500;
            font-size: 2em; /* Ajustado para ser más pequeño en móviles */
            font-weight: bold;
        }

        canvas {
            margin-top: 20px;
            border: 2px solid #333;
            background-color: #e0f7fa;
            max-width: 100%; /* Asegura que el canvas se ajuste al ancho de la pantalla */
            height: auto; /* Mantiene la proporción del canvas */
        }

        #fraseLindas, #mensaje {
            font-size: 1.2em; /* Ajustado para ser más pequeño en móviles */
            color: #ffa500;
            margin-top: 30px;
            font-weight: bold;
        }

        #mensaje {
            margin-top: 50px;
        }

        #reiniciarBtn {
            margin-top: 20px;
            padding: 10px 20px;
            font-size: 1em;
            color: #fff;
            background-color: #ffa500;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        #reiniciarBtn:hover {
            background-color: #e89f00;
        }

        /* Media Queries para pantallas pequeñas */
        @media (max-width: 600px) {
            h1 {
                font-size: 1.5em;
            }

            #fraseLindas, #mensaje {
                font-size: 1em;
            }

            #reiniciarBtn {
                padding: 8px 16px;
                font-size: 0.9em;
            }
        }
    </style>
</head>
<body>
    <h1>flor amarilla</h1>
    <canvas id="girasolCanvas" width="800" height="800"></canvas>
    <p id="fraseLindas"></p>
    <p id="mensaje"></p>
    <button id="reiniciarBtn">Volver a Dibujar</button>

    <script>
        window.onload = function() {
            const canvas = document.getElementById('girasolCanvas');
            const ctx = canvas.getContext('2d');

            // Definición de frases lindas
            const frases = [
                "Eres una persona increíble.",
                "vamos a aprobar lo juro .",
                "Todo lo que sueñas está por llegar.",
                "bañate porfi.",
                "Brillas con luz propia.",
                "Hoy es un día perfecto para ser feliz.",
                "layaut.",
                "Sigue adelante, lo mejor está por venir.",
                "aaaaaaaaa pero.",
                "Tu sonrisa es contagiosa.",
                "Eres una persona increíble.",
                "Cada día es una nueva oportunidad.",
                "Lo que te hace diferente, te hace especial."
            ];

            // Nombres y mensaje especial
            const mensaje = "Ezequiel, Agustina, Abigail, joaco, Nai y Micaela les deseo un lindo 21 de septiembre.";

            // Mostrar frase al azar
            function mostrarFrase() {
                const frase = frases[Math.floor(Math.random() * frases.length)];
                document.getElementById("fraseLindas").innerText = frase;
            }

            // Mostrar mensaje final
            function mostrarMensajeFinal() {
                document.getElementById("mensaje").innerText = mensaje;
            }

            // Dibujar el centro del girasol
            function dibujarCentro() {
                ctx.beginPath();
                ctx.arc(400, 400, 50, 0, 2 * Math.PI); // Círculo central
                ctx.fillStyle = '#8B4513'; // Marrón para el centro del girasol
                ctx.fill();
            }

            // Dibujar pétalos del girasol
            function dibujarPetalos() {
                ctx.fillStyle = '#FFD700'; // Amarillo para los pétalos
                const numPetalos = 20;
                const angulo = (2 * Math.PI) / numPetalos;
                const petaloBaseWidth = 30;
                const petaloBaseHeight = 120;
                const petaloBordesWidth = 10;
                const petaloBordesHeight = 20;
                
                for (let i = 0; i < numPetalos; i++) {
                    ctx.save();
                    ctx.translate(400, 400);
                    ctx.rotate(angulo * i);
                    ctx.translate(0, -150);

                    // Pétalo interior
                    ctx.beginPath();
                    ctx.ellipse(0, 0, petaloBaseWidth, petaloBaseHeight, 0, 0, 2 * Math.PI);
                    ctx.fillStyle = '#FFD700';
                    ctx.fill();

                    // Borde del pétalo
                    ctx.beginPath();
                    ctx.ellipse(0, 0, petaloBaseWidth + petaloBordesWidth, petaloBaseHeight + petaloBordesHeight, 0, 0, 2 * Math.PI);
                    ctx.strokeStyle = '#FFA500';
                    ctx.lineWidth = 4;
                    ctx.stroke();

                    ctx.restore();
                }
            }

            // Dibujar el girasol paso a paso
            function dibujarGirasol() {
                let petalosDibujados = 0;
                const numPetalos = 20; // Ajustado para 20 pétalos
                const angulo = (2 * Math.PI) / numPetalos;

                const intervalo = setInterval(() => {
                    if (petalosDibujados < numPetalos) {
                        // Dibujar pétalos uno por uno
                        ctx.save();
                        ctx.translate(400, 400);
                        ctx.rotate(angulo * petalosDibujados);
                        ctx.translate(0, -150);

                        ctx.beginPath();
                        ctx.ellipse(0, 0, 30, 120, 0, 0, 2 * Math.PI);
                        ctx.fillStyle = '#FFD700';
                        ctx.fill();

                        ctx.beginPath();
                        ctx.ellipse(0, 0, 40, 130, 0, 0, 2 * Math.PI);
                        ctx.strokeStyle = '#FFA500';
                        ctx.lineWidth = 4;
                        ctx.stroke();

                        ctx.restore();

                        // Mostrar frase al azar cada 2 pétalos
                        if (petalosDibujados % 2 === 0) {
                            mostrarFrase();
                        }

                        petalosDibujados++;
                    } else {
                        clearInterval(intervalo); // Detener cuando termine
                        dibujarCentro(); // Dibujar el centro del girasol al final
                        mostrarMensajeFinal(); // Mostrar el mensaje final
                    }
                }, 500); // Dibujar un pétalo cada 0.5 segundos
            }

            dibujarGirasol(); // Iniciar dibujo del girasol

            // Añadir evento al botón de reinicio
            document.getElementById('reiniciarBtn').addEventListener('click', function() {
                ctx.clearRect(0, 0, canvas.width, canvas.height); // Limpiar el canvas
                dibujarGirasol(); // Volver a dibujar el girasol
            });
        };
    </script>
</body>
</html>
