# ODD23-24-WT-JavaScript
# a) Calculate Electricity Bill:
HTML Structure:

The HTML structure includes a form with an input field for entering the units of electricity consumed and a button to calculate the bill.
There's a div element to display the result.
JavaScript Logic:

The JavaScript function calculateBill is triggered when the button is clicked.
It retrieves the entered units, determines the rate based on different slabs, calculates the bill, and displays the result.
Styling:

The styling is done using CSS to enhance the visual appeal.
Background color, fonts, and button styles are applied
# code:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Electricity Bill Calculator</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f4f4;
            text-align: center;
            margin: 20px;
        }

        form {
            background-color: #ffffff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
        }

        h1 {
            color: #333333;
        }

        button {
            background-color: #4caf50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        #result {
            margin-top: 20px;
            font-size: 18px;
            color: #333333;
        }
    </style>
    <script>
        function calculateBill() {
            var units = document.getElementById("units").value;
            var rate = 0;

            if (units <= 50) {
                rate = 0.50;
            } else if (units <= 150) {
                rate = 0.75;
            } else if (units <= 250) {
                rate = 1.20;
            } else {
                rate = 1.50;
            }

            var billAmount = units * rate;
            document.getElementById("result").innerHTML = "Your electricity bill is $" + billAmount.toFixed(2);
        }
    </script>
</head>
<body>
    <h1>Electricity Bill Calculator</h1>
    <form>
        <label for="units">Enter Units Consumed:</label>
        <input type="number" id="units" required>
        <button type="button" onclick="calculateBill()">Calculate Bill</button>
    </form>
    <div id="result"></div>
</body>
</html>
```
# Output:
![image](https://github.com/Hariveeraprasad-2006/ODD23-24-WT-JavaScript/assets/145049988/b4e6b176-5951-43a4-a17a-35075b7b6c3a)

# b) Factorial Calculation:
HTML Structure:

Simple HTML structure with an input field to enter a number and a button to calculate the factorial.
A div element is used to display the result.
JavaScript Logic:

The JavaScript function calculateFactorial is triggered when the button is clicked.
It retrieves the entered number, calculates the factorial using a loop, and displays the result.
Styling:

Minimal styling is applied for readability.
Background color and button styles are used.
# code:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Factorial Calculator</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #ecf0f1;
            text-align: center;
            margin: 20px;
            color: #333333;
        }

        h1 {
            color: #3498db;
        }

        input {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            box-sizing: border-box;
        }

        button {
            background-color: #2ecc71;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        #result {
            margin-top: 20px;
            font-size: 18px;
        }
    </style>
    <script>
        function calculateFactorial() {
            var inputNumber = parseInt(document.getElementById("inputNumber").value);
            var factorial = 1;

            for (var i = 1; i <= inputNumber; i++) {
                factorial *= i;
            }

            document.getElementById("result").innerHTML = "Factorial of " + inputNumber + " is: " + factorial;
        }
    </script>
</head>
<body>
    <h1>Factorial Calculator</h1>
    <label for="inputNumber">Enter a Number:</label>
    <input type="number" id="inputNumber" required>
    <button type="button" onclick="calculateFactorial()">Calculate Factorial</button>
    <div id="result"></div>
</body>
</html>
```
# output:
![image](https://github.com/Hariveeraprasad-2006/ODD23-24-WT-JavaScript/assets/145049988/3663e373-e6f3-4235-8cf2-e67f9e7801d1)
# c) Generate 'N' Prime Numbers:
HTML Structure:

Basic HTML structure with an input field to enter the number of prime numbers to generate and a button to trigger the generation.
A div element is used to display the generated prime numbers.
JavaScript Logic:

The JavaScript function generatePrimes is triggered when the button is clicked.
It retrieves the entered number, generates prime numbers using a loop and a helper function isPrime, and displays the result.
Styling:

Simple styling is applied for visual appeal.
Background color and button styles are used.
# code:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prime Number Generator</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #d35400;
            text-align: center;
            margin: 20px;
            color: #ffffff;
        }

        h1 {
            color: #3498db;
        }

        input {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            box-sizing: border-box;
        }

        button {
            background-color: #27ae60;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        #result {
            margin-top: 20px;
            font-size: 18px;
        }
    </style>
    <script>
        function generatePrimes() {
            var numberOfPrimes = parseInt(document.getElementById("numberOfPrimes").value);
            var primes = [];

            for (var i = 2; primes.length < numberOfPrimes; i++) {
                if (isPrime(i)) {
                    primes.push(i);
                }
            }

            document.getElementById("result").innerHTML = "First " + numberOfPrimes + " prime numbers: " + primes.join(', ');
        }

        function isPrime(num) {
            for (var i = 2; i <= Math.sqrt(num); i++) {
                if (num % i === 0) {
                    return false;
                }
            }
            return num > 1;
        }
    </script>
</head>
<body>
    <h1>Prime Number Generator</h1>
    <label for="numberOfPrimes">Enter Number of Primes:</label>
    <input type="number" id="numberOfPrimes" required>
    <button type="button" onclick="generatePrimes()">Generate Primes</button>
    <div id="result"></div>
</body>
</html>
```
# d) Simple Calculator:
HTML Structure:

The HTML structure includes a form with input fields for two numbers and buttons for addition, subtraction, multiplication, and division.
A div element is used to display the result.
JavaScript Logic:

The JavaScript function calculate is triggered when any of the operation buttons is clicked.
It retrieves the entered numbers, performs the selected operation, and displays the result.
Styling:

Styling is applied to make the calculator visually appealing.
Background color, font, and button styles are used.
# code:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #3498db;
            text-align: center;
            margin: 20px;
            color: #ffffff;
        }

        form {
            background-color: #ffffff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
        }

        h1 {
            color: #333333;
        }

        label {
            display: block;
            margin-bottom: 10px;
        }

        input {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            box-sizing: border-box;
        }

        button {
            background-color: #2ecc71;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        #result {
            margin-top: 20px;
            font-size: 18px;
            color: #333333;
        }
    </style>
    <script>
        function calculate(operation) {
            var num1 = parseFloat(document.getElementById("num1").value);
            var num2 = parseFloat(document.getElementById("num2").value);

            if (!isNaN(num1) && !isNaN(num2)) {
                switch (operation) {
                    case 'add':
                        document.getElementById("result").innerHTML = "Result: " + (num1 + num2);
                        break;
                    case 'subtract':
                        document.getElementById("result").innerHTML = "Result: " + (num1 - num2);
                        break;
                    case 'multiply':
                        document.getElementById("result").innerHTML = "Result: " + (num1 * num2);
                        break;
                    case 'divide':
                        if (num2 !== 0) {
                            document.getElementById("result").innerHTML = "Result: " + (num1 / num2);
                        } else {
                            document.getElementById("result").innerHTML = "Cannot divide by zero!";
                        }
                        break;
                    default:
                        document.getElementById("result").innerHTML = "Invalid operation";
                }
            } else {
                document.getElementById("result").innerHTML = "Please enter valid numbers";
            }
        }
    </script>
</head>
<body>
    <h1>Simple Calculator</h1>
    <form>
        <label for="num1">Enter Number 1:</label>
        <input type="number" id="num1" required>
        <label for="num2">Enter Number 2:</label>
        <input type="number" id="num2" required>
        <button type="button" onclick="calculate('add')">Add</button>
        <button type="button" onclick="calculate('subtract')">Subtract</button>
        <button type="button" onclick="calculate('multiply')">Multiply</button>
        <button type="button" onclick="calculate('divide')">Divide</button>
    </form>
    <div id="result"></div>
</body>
</html>
```
# Output:
![image](https://github.com/Hariveeraprasad-2006/ODD23-24-WT-JavaScript/assets/145049988/5ba861d4-f243-4ad3-bed2-4bd6f5325ffa)
# e) Simple Text Editor Application:
HTML Structure:

HTML structure includes input field for text, a dropdown to choose operations, a button to perform the operation, and a div to display the result.
JavaScript Logic:

The JavaScript function manipulateText is triggered when the button is clicked.
It retrieves the entered text and the selected operation from the dropdown, performs the operation, and displays the result.
Styling:

Styling is applied for visual appeal.
Background color, font, input styles, and button styles are used.
# code:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Text Editor</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #2c3e50;
            text-align: center;
            margin: 20px;
            color: #ffffff;
        }

        label {
            display: block;
            margin-bottom: 10px;
            color: #ffffff;
        }

        input {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            box-sizing: border-box;
        }

        select {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            box-sizing: border-box;
            color: #000000; /* Corrected text color */
        }

        button {
            background-color: #3498db;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        #output {
            margin-top: 20px;
            font-size: 18px;
            color: #ffffff;
        }
    </style>
    <script>
        function manipulateText() {
            var userInput = document.getElementById("userInput").value;
            var operation = document.getElementById("operation").value;
            var result = "";

            switch (operation) {
                case 'capitalize':
                    result = userInput.toUpperCase();
                    break;
                case 'lowercase':
                    result = userInput.toLowerCase();
                    break;
                case 'reverse':
                    result = userInput.split('').reverse().join('');
                    break;
                case 'clear':
                    document.getElementById("userInput").value = "";
                    result = "Text cleared!";
                    break;
                default:
                    result = "Invalid operation";
            }

            document.getElementById("output").innerHTML = result;
        }
    </script>
</head>
<body>
    <h1>Text Editor</h1>
    <label for="userInput">Enter Text:</label>
    <input type="text" id="userInput" required>
    <label for="operation">Choose Operation:</label>
    <select id="operation">
        <option value="capitalize">Capitalize</option>
        <option value="lowercase">Lowercase</option>
        <option value="uppercase">Uppercase</option>
        <option value="reverse">Reverse</option>
        <option value="clear">Clear</option>
    </select>
    <button type="button" onclick="manipulateText()">Perform Operation</button>
    <div id="output"></div>
</body>
</html>
```
# Output:
![image](https://github.com/Hariveeraprasad-2006/ODD23-24-WT-JavaScript/assets/145049988/c8fd97ea-44df-43a7-99ad-4fd0c471ab23)

# Developed by: Arikatla Hari Veera Prasad
# Register Number: 212223240014
# result:
The JavaScript programs offer practical tools – from an intuitive electricity bill calculator to a versatile text editor. Designed with clear interfaces and dynamic functionality, they showcase the seamless integration of HTML, CSS, and JavaScript for efficient and visually appealing web solutions.
