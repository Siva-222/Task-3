# Task-3
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f2f2f2;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .calculator {
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
        }
        .display {
            width: 100%;
            height: 60px;
            background-color: #e6e6e6;
            border: none;
            font-size: 24px;
            padding: 10px;
            margin-bottom: 10px;
            text-align: right;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 60px);
            gap: 10px;
        }
        button {
            padding: 20px;
            font-size: 18px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            background-color: #2e86de;
            color: white;
        }
        button.operator {
            background-color: #117a65;
        }
        button.equal {
            background-color: #c0392b;
            grid-column: span 2;
        }
        button.clear {
            background-color: #f39c12;
            grid-column: span 2;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" class="display" id="display" disabled>
        <div class="buttons">
            <button onclick="clearDisplay()" class="clear">C</button>
            <button onclick="appendToDisplay('/')" class="operator">/</button>
            <button onclick="appendToDisplay('*')" class="operator">*</button>
            <button onclick="appendToDisplay('7')">7</button>
            <button onclick="appendToDisplay('8')">8</button>
            <button onclick="appendToDisplay('9')">9</button>
            <button onclick="appendToDisplay('-')" class="operator">-</button>
            <button onclick="appendToDisplay('4')">4</button>
            <button onclick="appendToDisplay('5')">5</button>
            <button onclick="appendToDisplay('6')">6</button>
            <button onclick="appendToDisplay('+')" class="operator">+</button>
            <button onclick="appendToDisplay('1')">1</button>
            <button onclick="appendToDisplay('2')">2</button>
            <button onclick="appendToDisplay('3')">3</button>
            <button onclick="calculate()" class="equal">=</button>
            <button onclick="appendToDisplay('0')">0</button>
            <button onclick="appendToDisplay('.')">.</button>
        </div>
    </div>

    <script>
        const display = document.getElementById('display');

        function appendToDisplay(value) {
            display.value += value;
        }

        function clearDisplay() {
            display.value = '';
        }

        function calculate() {
            try {
                display.value = eval(display.value);
            } catch (e) {
                alert('Invalid Expression');
                clearDisplay();
            }
        }
    </script>
</body>
</html>
