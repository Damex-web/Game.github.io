
# Game.github.io


<!DOCTYPE html>
<html lang="en">
<head>
    <title>Rock Paper Scissors Game</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Pixelify+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            text-align: center;
            padding: 10% 0px;
            margin: 0;
            background: #580012ea;
            height: 100vh;
            color: white;
        }
        
        .container {
            position: fixed;
        }
        h1 {
            padding: 20px 10px;
            background: #0e0003ea;
            
            font-family: 'Pixelify Sans', san_serif;
        }

        h3 {
            margin-top: 20px;
            color: #000165
        }

        .padBtn {
            font-size: 30px;
            padding: 20px 20px;
            margin: 10px;
            cursor: pointer;
            border-radius: 50%;
            border: 2px solid #ff001f;
            outline: none;
        }
        
        .padBtn:active:focus {
            border: 2px solid #ff001f;
        }

        .buttons {
            display: flex;
            justify-content: center;
        }
        
    </style>
</head>
<body>
    
    <div class="container">
        <h1> Rock🪨 Paper📜 Scissors✂️ Game 🎮</h1>
        <h2 id="me">Me: </h2>
        <h2 id="computer">Computer: </h2>
        <h3 id="result">Result</h3>
        <h3 id="score">Score: Me 0 - 0 Computer</h3>

        <div class="buttons">
            <button class="padBtn" id="rock">🪨</button>
            <button class="padBtn" id="paper">📜</button>
            <button class="padBtn" id="scissors">✂️</button>
        </div>
    </div>



    <script>
        
        var playerT = document.querySelector("#me");
        var computerT = document.querySelector("#computer");
        var resultT = document.querySelector("#result");
        var scoreT = document.querySelector("#score"); 
        var padT = document.querySelectorAll(".padBtn");

        var player;
        var computer;
        var result;
        var playerScore = 0;
        var computerScore = 0;

        padT.forEach(padT => {
            padT.addEventListener("click", function () {
                player = padT.textContent;
                computerTurn();
                playerT.textContent = "Me: " + player;
                computerT.textContent = "Computer: " + computer;
                result = checkWinner();
        
        
        
                if (result === "You Win 👻🦾!") {
                   playerScore++;
                } else if (result === "You Loss 😂🥵!") {
                    computerScore++;
                }
                 resultT.textContent = result;
                 scoreT.textContent = "Score: " + "Me " + playerScore + " - " + computerScore + " Computer";
            });
        });
        
        function computerTurn() {
            var choices = ["🪨", "📜", "✂️"];
            var randomIndex = Math.floor(Math.random() * choices.length);
            computer = choices[randomIndex];
        }

        function checkWinner() {
            if (player === computer) {
                return "It's a draw 🤝👐!";
            } else if (
                (player === "🪨" && computer === "✂️") ||
                (player === "📜" && computer === "🪨") ||
                (player === "✂️" && computer === "📜")
            ) {
                return "You Win 👻🦾!";
            } else {
                return "You Loss 😂🥵!";
            }
        }
    </script>
</body>
</html>
