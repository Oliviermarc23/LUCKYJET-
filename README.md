<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lucky Jet Bot</title>
    <style>
        body {
            background-color: #0c0c0c;
            color: white;
            font-family: Arial, sans-serif;
            text-align: center;
        }
        .container {
            width: 90%;
            max-width: 400px;
            margin: auto;
            padding: 20px;
            background: #1a1a1a;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(255, 255, 255, 0.1);
        }
        .logo {
            font-size: 24px;
            font-weight: bold;
            color: #1e90ff;
        }
        .multiplier {
            font-size: 28px;
            font-weight: bold;
            margin: 20px 0;
        }
        .countdown {
            font-size: 18px;
            margin: 10px 0;
        }
        .btn {
            display: block;
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: none;
            cursor: pointer;
            font-size: 16px;
            font-weight: bold;
            border-radius: 5px;
        }
        .btn-primary {
            background: linear-gradient(to right, #6a11cb, #2575fc);
            color: white;
        }
        .btn-secondary {
            background: linear-gradient(to right, #ff416c, #ff4b2b);
            color: white;
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="logo">1Win <span style="color: #b41cf0;">Lucky Jet</span></div>
        <div class="multiplier" id="multiplier">--X - --X</div>
        <div class="countdown">Chance: <span id="chance">--%</span></div>
        <div class="countdown">Before the signal: <span id="timer">60</span> sec</div>
        <button class="btn btn-primary" onclick="generatePrediction()">GET SIGNAL</button>
        <button class="btn btn-secondary">GO TO GAME</button>
    </div>

    <script>
        function randomInRange(min, max) {
            return (Math.random() * (max - min) + min).toFixed(2);
        }

        function generatePrediction() {
            let leftMultiplier = randomInRange(2, 3.5);
            let rightMultiplier = randomInRange(8, 25);
            let chance = randomInRange(92, 98);
            document.getElementById("multiplier").innerText = `${leftMultiplier}X - ${rightMultiplier}X`;
            document.getElementById("chance").innerText = `${chance}%`;
            
            let countdown = 60;
            document.getElementById("timer").innerText = countdown;
            let interval = setInterval(() => {
                countdown--;
                document.getElementById("timer").innerText = countdown;
                if (countdown <= 0) {
                    clearInterval(interval);
                }
            }, 1000);
        }
    </script>

</body>
</html>
