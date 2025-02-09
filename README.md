# digital-bhem
# index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" class="display" disabled>
        <div class="buttons">
            <button class="btn" onclick="appendNumber(7)">7</button>
            <button class="btn" onclick="appendNumber(8)">8</button>
            <button class="btn" onclick="appendNumber(9)">9</button>
            <button class="btn" onclick="setOperation('/')">/</button>

            <button class="btn" onclick="appendNumber(4)">4</button>
            <button class="btn" onclick="appendNumber(5)">5</button>
            <button class="btn" onclick="appendNumber(6)">6</button>
            <button class="btn" onclick="setOperation('*')">*</button>

            <button class="btn" onclick="appendNumber(1)">1</button>
            <button class="btn" onclick="appendNumber(2)">2</button>
            <button class="btn" onclick="appendNumber(3)">3</button>
            <button class="btn" onclick="setOperation('-')">-</button>

            <button class="btn" onclick="appendNumber(0)">0</button>
            <button class="btn" onclick="clearDisplay()">C</button>
            <button class="btn" onclick="calculateResult()">=</button>
            <button class="btn" onclick="setOperation('+')">+</button>
        </div>
    </div>
#style.css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f4f4f4;
}

.calculator {
    width: 260px;
    background-color: white;
    border-radius: 10px;
    padding: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.display {
    width: 100%;
    height: 50px;
    font-size: 24px;
    text-align: right;
    margin-bottom: 10px;
    padding: 10px;
    border: none;
    background-color: #f0f0f0;
    border-radius: 5px;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}

button {
    font-size: 18px;
    padding: 20px;
    background-color: #f0f0f0;
    border: 1px solid #ddd;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
}

button:hover {
    background-color: #ddd;
}

button:active {
    background-color: #bbb;
}


#scrpit.js
let currentInput = '';
let previousInput = '';
let operator = null;

function appendNumber(number) {
    currentInput += number;
    updateDisplay(currentInput);
}

function setOperation(op) {
    if (currentInput === '') return;
    if (previousInput !== '') {
        calculateResult();
    }
    operator = op;
    previousInput = currentInput;
    currentInput = '';
}

function clearDisplay() {
    currentInput = '';
    previousInput = '';
    operator = null;
    updateDisplay('0');
}

function calculateResult() {
    if (previousInput === '' || currentInput === '') return;
    
    let result;
    const prev = parseFloat(previousInput);
    const current = parseFloat(currentInput);
    
    switch (operator) {
        case '+':
            result = prev + current;
            break;
        case '-':
            result = prev - current;
            break;
        case '*':
            result = prev * current;
            break;
        case '/':
            if (current === 0) {
                alert('Cannot divide by zero');
                return;
            }
            result = prev / current;
            break;
        default:
            return;
    }
    
    currentInput = result.toString();
    operator = null;
    previousInput = '';
    updateDisplay(currentInput);
}

function updateDisplay(value) {
    document.getElementById('display').value = value;
}
    <script src="script.js"></script>
</body>
</html>

   

