# calculator-html
## Program
### html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <div class="calculator">
            <div class="header">
                <p>J BARATH KUMAR</p>
                <p>212221230012</p>
            </div>
            <div class="display" id="display">0</div>
            <div class="buttons">
                <button onclick="clearDisplay()">AC</button>
                <button onclick="deleteLast()">DEL</button>
                <button onclick="appendOperator('+')">+</button>
                <button onclick="appendOperator('-')">-</button>
                <button onclick="appendNumber(9)">9</button>
                <button onclick="appendNumber(8)">8</button>
                <button onclick="appendNumber(7)">7</button>
                <button onclick="appendOperator('/')">/</button>
                <button onclick="appendNumber(6)">6</button>
                <button onclick="appendNumber(5)">5</button>
                <button onclick="appendNumber(4)">4</button>
                <button onclick="appendOperator('*')">*</button>
                <button onclick="appendNumber(3)">3</button>
                <button onclick="appendNumber(2)">2</button>
                <button onclick="appendNumber(1)">1</button>
                <button onclick="appendOperator('%')">%</button>
                <button onclick="appendNumber(0)">0</button>
                <button onclick="appendNumber('00')">00</button>
                <button onclick="appendDot()">.</button>
                <button onclick="calculateResult()">=</button>
            </div>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
```
### css
```css
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background: linear-gradient(to right, #0f0c29, #302b63, #24243e);
    font-family: 'Arial', sans-serif;
    color: white;
}

.container {
    text-align: center;
}

.calculator {
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(10px);
    border-radius: 20px;
    padding: 20px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
    border: 1px solid rgba(255, 255, 255, 0.3);
}

.header p {
    margin: 5px 0;
    font-size: 1em;
    color: #fff;
    text-shadow: 0 0 5px #ff00ff, 0 0 10px #ff00ff;
}

.display {
    background: rgba(0, 0, 0, 0.7);
    padding: 20px;
    font-size: 2em;
    text-align: right;
    border-radius: 10px;
    margin-bottom: 10px;
    color: #fff;
    text-shadow: 0 0 5px #00ffff, 0 0 10px #00ffff;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}

button {
    background: rgba(255, 255, 255, 0.2);
    border: none;
    padding: 20px;
    font-size: 1.5em;
    border-radius: 10px;
    color: #fff;
    cursor: pointer;
    transition: background 0.3s, box-shadow 0.3s;
    text-shadow: 0 0 5px #00ffff, 0 0 10px #00ffff;
}

button:hover {
    background: rgba(255, 255, 255, 0.3);
    box-shadow: 0 0 10px #00ffff, 0 0 20px #00ffff;
}

button:active {
    background: rgba(255, 255, 255, 0.4);
    box-shadow: 0 0 20px #00ffff, 0 0 40px #00ffff;
}
```
### javascript
```js
let display = document.getElementById('display');
let currentInput = '';

function appendNumber(number) {
    if (currentInput === '0' && number === 0) return;
    currentInput += number;
    display.innerText = currentInput;
}

function appendOperator(operator) {
    if (currentInput === '') return;
    currentInput += operator;
    display.innerText = currentInput;
}

function appendDot() {
    if (currentInput.includes('.')) return;
    currentInput += '.';
    display.innerText = currentInput;
}

function clearDisplay() {
    currentInput = '';
    display.innerText = '0';
}

function deleteLast() {
    currentInput = currentInput.slice(0, -1);
    display.innerText = currentInput || '0';
}

function calculateResult() {
    try {
        currentInput = eval(currentInput).toString();
        display.innerText = currentInput;
    } catch (error) {
        display.innerText = 'Error';
        currentInput = '';
    }
}
```
## output
![image](https://github.com/Karthikeyan21001828/calculator-html/assets/93427303/893d90c3-0bc9-45fb-9547-d908f396cf88)
