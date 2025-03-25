<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para ti 💖</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 50px;
        }
        h1 {
            color: #ff4081;
        }
        .btn {
            font-size: 20px;
            padding: 10px 20px;
            margin: 10px;
            border: none;
            cursor: pointer;
            border-radius: 10px;
            position: relative;
        }
        .yes-btn {
            background-color: #4CAF50;
            color: white;
        }
        .no-btn {
            background-color: #f44336;
            color: white;
        }
        .hidden {
            display: none;
        }
        .button-container {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div id="step1">
        <h1>¿Sigues enojado conmigo? 🥺</h1>
        <div class="button-container">
            <button class="btn yes-btn" onclick="showStep(2)">Sí 😢</button>
            <button class="btn no-btn" onclick="showFinalMessage('¡Sabía que no podías resistirte! Eres el mejor del mundo y te amo con todo y chocheras de abuelito. 💖')">No 😊</button>
        </div>
    </div>
    
    <div id="step2" class="hidden">
        <h1>¿Sabías que los hombres que perdonan rápido son más guapos? 🤩</h1>
        <div class="button-container">
            <button class="btn yes-btn" onclick="showStep(3)">Sí 😏</button>
            <button class="btn no-btn" onclick="showMessageThenStep('Pues ahora lo sabes, y tú eres el más guapo de todos. 😘', 3)">No 🤔</button>
        </div>
    </div>
    
    <div id="step3" class="hidden">
        <h1>Si te hago ojitos bonitos... ¿me perdonas? 🥺👉👈</h1>
        <div class="button-container">
            <button class="btn yes-btn" onclick="showFinalMessage('¡Sabía que dirías que sí! Así me gusta, paz y amor ✌️💖')">Sí 😍</button>
            <button class="btn no-btn" onclick="showMessageThenStep('Okay... pero al menos sonríe un poquito. 😏', 4)">No 🙄</button>
        </div>
    </div>
    
    <div id="step4" class="hidden">
        <h1>¿Ya no estás enojado conmigo? 🥰</h1>
        <div class="button-container">
            <button id="movingYes" class="btn yes-btn" onmouseover="moveButton()" onclick="showMessageThenStep('Piénsalo mejor... 😏', 4)">Sí 😆</button>
            <button class="btn no-btn" onclick="showFinalMessage('Ves que no es tan difícil? 😏💕')">No 😊</button>
        </div>
    </div>
    
    <p id="message" class="hidden"></p>
    
    <script>
        function showStep(step) {
            document.querySelectorAll("div").forEach(div => div.classList.add("hidden"));
            document.getElementById(`step${step}`).classList.remove("hidden");
        }
        
        function showMessageThenStep(msg, step) {
            document.getElementById("message").textContent = msg;
            document.getElementById("message").classList.remove("hidden");
            setTimeout(() => {
                document.getElementById("message").classList.add("hidden");
                showStep(step);
            }, 2000);
        }
        
        function showFinalMessage(msg) {
            document.querySelectorAll("div").forEach(div => div.classList.add("hidden"));
            document.getElementById("message").textContent = msg;
            document.getElementById("message").classList.remove("hidden");
        }
        
        function moveButton() {
            let button = document.getElementById("movingYes");
            let x = Math.random() * (window.innerWidth - 150);
            let y = Math.random() * (window.innerHeight - 150);
            button.style.position = "absolute";
            button.style.left = `${x}px`;
            button.style.top = `${y}px`;
        }
    </script>
</body>
</html>
