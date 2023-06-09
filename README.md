# Ex-06:
## Create a simple calculator built with React
### AIM:
The aim of this code is to create a simple calculator using React. The calculator allows users to perform basic arithmetic calculations.
### ALGORITHM:
1. Import the necessary dependencies from the React library and the CSS file.
2. Create a functional component called "App" to represent the calculator.
3. Initialize the state variable "result" using the useState hook to store the current calculation result.
4. Implement functions to handle different actions:
* "handleClick": Concatenates the clicked button's name to the current result.
* "handleClear": Clears the result, resetting it to an empty string.
* "handleCalculate": Evaluates the result expression using the eval() function, sets the result to the calculated value, or displays an error message if the expression is invalid.
5. Render the UI elements using JSX:
* Display a heading for the calculator.
* Create an input field to display the result, which is read-only.
* Create a keypad with buttons for digits, operators, and special functions.
* Attach the appropriate event handlers to each button.
* Apply CSS classes and styles to the UI elements to achieve the desired layout and appearance.
### PROGRAM:
### App.js:
```javascript
import React, { useState } from 'react';
import './App.css';

function App() {
  const [result, setResult] = useState('');

  const handleClick = (e) => {
    setResult(result.concat(e.target.name));
  };

  const handleClear = () => {
    setResult('');
  };

  const handleCalculate = () => {
    try {
      setResult(eval(result).toString());
    } catch (error) {
      setResult('Error');
    }
  };

  return (
    <body>
      <p>SIMPLE CALCULATOR</p>
      <div className="calculator">
        <input type="text" value={result} readOnly />
        <div className="keypad">
          <button name="7" onClick={handleClick}>7</button>
          <button name="8" onClick={handleClick}>8</button>
          <button name="9" onClick={handleClick}>9</button>
          <button className="operator" name="/" onClick={handleClick}>&divide;</button>
          <button name="4" onClick={handleClick}>4</button>
          <button name="5" onClick={handleClick}>5</button>
          <button name="6" onClick={handleClick}>6</button>
          <button className="operator" name="*" onClick={handleClick}>&times;</button>
          <button name="1" onClick={handleClick}>1</button>
          <button name="2" onClick={handleClick}>2</button>
          <button name="3" onClick={handleClick}>3</button>
          <button className="operator" name="-" onClick={handleClick}>&ndash;</button>
          <button name="0" onClick={handleClick}>0</button>
          <button name="." onClick={handleClick}>.</button>
          <button className="operator" id="equals" onClick={handleCalculate}>=</button>
          <button className="operator" name="%" onClick={handleClick}>%</button>
          <button className="operator clear" onClick={handleClear}>Clear</button>
        </div>
      </div>
    </body>
  );
}

export default App;
```
### App.css:
```
.calculator {
  width: 300px;
  margin: 50px auto;
  background-color: #3da9bc;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(172, 179, 255, 0.99);
}
body{
  background-color: rgb(154, 192, 225);
  margin:200px;
}
p{
  color:rgba(255, 255, 255, 0.848);
  text-align:center;
  font-size:40px;
  font-weight:700;
}

input[type="text"] {
  width: 100%;
  height: 40px;
  margin-bottom: 10px;
  font-size: 18px;
  padding: 5px;
}

.keypad {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 5px;
}

button {
  width: 100%;
  height: 40px;
  font-size: 18px;
  border: none;
  background-color: #fff;
  cursor: pointer;
}

.operator {
  background-color: #c55585;
  color: #000000;
}

#equals {
  background-color: #795278;
  color: #fff;
}
.operator.clear {
  grid-column: span 4;
}
```
### OUTPUT:

<img width="332" alt="1" src="https://github.com/KeerthikaNagarajan/React-Calculator/assets/93427089/2e3b18d1-f891-46fb-9aaf-97f36e0c44c6">

<img width="320" alt="2" src="https://github.com/KeerthikaNagarajan/React-Calculator/assets/93427089/e8d53ff2-4582-4022-b376-cd051afa019f">

### RESULT:
 The code will generate a simple calculator application with a user interface. 
