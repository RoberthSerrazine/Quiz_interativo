<!DOCTYPE html>
<html>
<head>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }
        .quiz-container {
            max-width: 800px;
            background: #fff;
            margin: 50px auto;
            padding: 30px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.15);
        }
        .question {
            font-weight: bold;
            font-size: 1.2em;
            color: #2c3e50;
        }
        .options {
            margin: 20px 0;
        }
        .options label {
            display: block;
            margin-bottom: 10px;
            font-size: 1.1em;
        }
        .options input[type="radio"] {
            margin-right: 10px;
        }
        button {
            background: #3498db;
            color: #fff;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1.1em;
        }
        button:hover {
            background: #2980b9;
        }
    </style>
</head>
<body>
    <div class="quiz-container">
        <p class="question">1. Quem ganhou a Copa do Mundo da FIFA de 2002?</p>
        <div class="options">
            <label><input type="radio" name="option1"> Alemanha</label>
            <label><input type="radio" name="option1"> Brasil</label>
            <label><input type="radio" name="option1"> Argentina</label>
            <label><input type="radio" name="option1"> França</label>
        </div>
        <p class="question">2. Quem é o maior artilheiro da história da Copa do Mundo da FIFA?</p>
        <div class="options">
            <label><input type="radio" name="option2"> Pelé</label>
            <label><input type="radio" name="option2"> Diego Maradona</label>
            <label><input type="radio" name="option2"> Miroslav Klose</label>
            <label><input type="radio" name="option2"> Lionel Messi</label>
        </div>
        <p class="question">3. Quem ganhou a Bola de Ouro da FIFA em 2020?</p>
        <div class="options">
            <label><input type="radio" name="option3"> Lionel Messi</label>
            <label><input type="radio" name="option3"> Cristiano Ronaldo</label>
            <label><input type="radio" name="option3"> Neymar</label>
            <label><input type="radio" name="option3"> Robert Lewandowski</label>
        </div>
        <p class="question">4. Quem ganhou a Copa América de 2021?</p>
        <div class="options">
            <label><input type="radio" name="option4"> Brasil</label>
            <label><input type="radio" name="option4"> Argentina</label>
            <label><input type="radio" name="option4"> Chile</label>
            <label><input type="radio" name="option4"> Peru</label>
        </div>
        <p class="question">5. Quem é o atual campeão da UEFA Champions League?</p>
        <div class="options">
            <label><input type="radio" name="option5"> Real Madrid</label>
            <label><input type="radio" name="option5"> Barcelona</label>
            <label><input type="radio" name="option5"> Bayern Munich</label>
            <label><input type="radio" name="option5"> Paris Saint-Germain</label>
        </div>
        <button onclick="checkAnswers()">Verificar respostas</button>
        <p id="result"></p>
    </div>
    <script>
        function checkAnswers() {
            var answers = ["Brasil", "Miroslav Klose", "Robert Lewandowski", "Argentina", "Bayern Munich"];
            var questions = ["option1", "option2", "option3", "option4", "option5"];
            var result = document.getElementById('result');
            result.textContent = '';
            for (var i = 0; i < questions.length; i++) {
                var options = document.getElementsByName(questions[i]);
                for (var j = 0; j < options.length; j++) {
                    if (options[j].checked) {
                        result.textContent += "Pergunta " + (i+1) + ": " + (options[j].nextSibling.textContent.trim() === answers[i] ? "Correto!" : "Incorreto!") + "\n";
                        break;
                    }
                }
            }
        }
    </script>
</body>
</html>
