# digital-bhem
# index.html
 <!DOCTYPE html>
<html lang="en">

<head>


    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EASY-Calculator</title>
    <link rel="stylesheet" href="styles.css">

</head>
<body>

    <div class="calci">
        <h1>Calculator</h1>
    </div>


    <div class="container">
        <div class="calculator">
            <form >


                <div class="display">
                    <input type="text" name="display">
                </div>



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

            </form>
        </div>
    </div>
    
</body>
</html>
