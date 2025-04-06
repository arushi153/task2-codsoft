<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f0f0f0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .calculator {
            border-radius: 12px;
            background-color: #333;
            padding: 20px;
            width: 280px;
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.2);
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        #display {
            grid-column: span 4;
            height: 60px;
            background-color: #000;
            color: #fff;
            font-size: 24px;
            border: none;
            text-align: right;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 10px;
            outline: none;
        }

        button {
            width: 100%;
            height: 60px;
            font-size: 22px;
            border: none;
            border-radius: 8px;
            background-color: #f4f4f4;
            color: #333;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #ddd;
        }

        button:active {
            background-color: #bbb;
        }

        .operator {
            background-color: #f39c12;
            color: white;
        }

        .operator:hover {
            background-color: #e67e22;
        }

        .equals {
            background-color: #27ae60;
            color: white;
            grid-column: span 2;
        }

        .equals:hover {
            background-color: #2ecc71;
        }

        .clear {
            background-color: #e74c3c;
            color: white;
        }

        .clear:hover {
            background-color: #c0392b;
        }
    </style>
</head>

<body>

    <div class="calculator">
        <input type="text" id="display" disabled>
        <button class="clear" onclick="clearDisplay()">C</button>
        <button onclick="appendToDisplay('1')">1</button>
        <button onclick="appendToDisplay('2')">2</button>
        <button class="operator" onclick="appendToDisplay('+')">+</button>
        <button onclick="appendToDisplay('3')">3</button>
        <button onclick="appendToDisplay('4')">4</button>
        <button onclick="appendToDisplay('5')">5</button>
        <button class="operator" onclick="appendToDisplay('-')">-</button>
        <button onclick="appendToDisplay('6')">6</button>
        <button onclick="appendToDisplay('7')">7</button>
        <button onclick="appendToDisplay('8')">8</button>
        <button class="operator" onclick="appendToDisplay('*')">*</button>
        <button onclick="appendToDisplay('9')">9</button>
        <button onclick="appendToDisplay('0')">0</button>
        <button class="equals" onclick="calculate()">=</button>
        <button class="operator" onclick="appendToDisplay('/')">/</button>
    </div>

    <script>
        function appendToDisplay(value) {
            document.getElementById('display').value += value;
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        function calculate() {
            try {
                document.getElementById('display').value = eval(document.getElementById('display').value);
            } catch (e) {
                document.getElementById('display').value = 'Error';
            }
        }
    </script>

</body>

</html>
