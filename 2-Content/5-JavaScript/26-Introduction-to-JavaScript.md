# Day 26 — Introduction to JavaScript

🔬 **Type:** Theory + Practical
🕐 **Duration:** 2 Hours
📚 **Unit:** 5 — JavaScript
🧪 **Lab Experiment:** 17

---

## Learning Objectives

By the end of this session, students will be able to:
- Explain what JavaScript is and where it runs
- Write JavaScript using internal and external methods
- Use variables, data types, operators, and conditional statements
- Display output using alert, console.log, and document.write

---

## 1. What is JavaScript?

> **Analogy:** If HTML is the **skeleton** and CSS is the **clothing**, then JavaScript is the **muscles and brain** — it makes the body move, react, and think.

JavaScript is a **programming language** that runs in the browser. It adds:
- **Interactivity** — button clicks, form validation, animations
- **Dynamic content** — update page without reloading
- **API interaction** — fetch data from servers

### HTML vs CSS vs JavaScript

| Technology | Role | Example |
|-----------|------|---------|
| HTML | Content/Structure | "Here's a button" |
| CSS | Appearance | "The button is blue and rounded" |
| JavaScript | Behavior | "When clicked, show a message" |

---

## 2. Adding JavaScript to HTML

### Internal (in `<script>` tag)

```html
<body>
    <h1>Hello World</h1>
    <script>
        alert('Welcome to JavaScript!');
    </script>
</body>
```

### External (separate .js file) ✅ Best Practice

**script.js:**
```javascript
alert('Welcome to JavaScript!');
```

**index.html:**
```html
<body>
    <h1>Hello World</h1>
    <script src="script.js"></script>
</body>
```

> Place `<script>` at the **end of `<body>`** so HTML loads before JavaScript runs.

---

## 3. Variables & Data Types

### Declaring Variables

```javascript
let name = "Rahul";          // Can be changed
const PI = 3.14159;          // Cannot be changed (constant)
var age = 20;                // Old way (avoid — use let instead)
```

| Keyword | Reassignable | Scope | Use When |
|---------|-------------|-------|----------|
| `let` | ✅ Yes | Block | Value changes |
| `const` | ❌ No | Block | Value stays same |
| `var` | ✅ Yes | Function | Avoid (legacy) |

### Data Types

```javascript
let text = "Hello";           // String
let count = 42;               // Number
let price = 99.99;            // Number (no separate float)
let isStudent = true;         // Boolean
let grade = null;             // Null (intentionally empty)
let address;                  // Undefined (not assigned)
let fruits = ["Apple", "Mango", "Banana"];  // Array
let student = { name: "Rahul", age: 20 };  // Object
```

### Type Checking

```javascript
console.log(typeof "Hello");     // "string"
console.log(typeof 42);          // "number"
console.log(typeof true);        // "boolean"
console.log(typeof undefined);   // "undefined"
```

---

## 4. Operators

### Arithmetic

```javascript
let a = 10, b = 3;
console.log(a + b);    // 13 (Addition)
console.log(a - b);    // 7  (Subtraction)
console.log(a * b);    // 30 (Multiplication)
console.log(a / b);    // 3.333... (Division)
console.log(a % b);    // 1  (Modulus/Remainder)
console.log(a ** b);   // 1000 (Exponent: 10³)
```

### Comparison

```javascript
console.log(5 == "5");     // true  (loose equality — compares value only)
console.log(5 === "5");    // false (strict equality — value AND type)
console.log(5 != "5");     // false
console.log(5 !== "5");    // true
console.log(5 > 3);        // true
console.log(5 <= 5);       // true
```

> **Always use `===`** (strict) instead of `==` (loose) to avoid unexpected type coercion bugs.

### Logical

```javascript
console.log(true && false);   // false (AND — both must be true)
console.log(true || false);   // true  (OR — at least one true)
console.log(!true);           // false (NOT — flip the value)
```

---

## 5. Output Methods

```javascript
// Pop-up dialog
alert("Hello World!");

// Browser console (F12 → Console tab)
console.log("Debug message");

// Write into HTML
document.write("<h2>Written by JS</h2>");

// Change element content
document.getElementById("output").textContent = "Hello!";
document.getElementById("output").innerHTML = "<strong>Hello!</strong>";
```

---

## 6. Conditional Statements

```javascript
let marks = 75;

if (marks >= 90) {
    console.log("Grade: A+");
} else if (marks >= 75) {
    console.log("Grade: A");
} else if (marks >= 60) {
    console.log("Grade: B");
} else if (marks >= 40) {
    console.log("Grade: C");
} else {
    console.log("Grade: F (Fail)");
}
```

### Ternary Operator (Shorthand)

```javascript
let age = 20;
let status = (age >= 18) ? "Adult" : "Minor";
console.log(status);  // "Adult"
```

---

## Practical Session

### 🧪 Lab Experiment 17: JavaScript Basics

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Basics</title>
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body { font-family: 'Segoe UI', sans-serif; background: #f4f4f4; padding: 30px; }
        .container { max-width: 600px; margin: 0 auto; }
        h1 { color: #1565C0; text-align: center; margin-bottom: 20px; }
        
        .card {
            background: white;
            border-radius: 10px;
            padding: 25px;
            margin-bottom: 20px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }
        .card h3 { color: #333; margin-bottom: 10px; }
        
        input, select {
            width: 100%;
            padding: 10px;
            margin: 5px 0 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 15px;
        }
        
        button {
            padding: 10px 25px;
            background: #1565C0;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 15px;
        }
        button:hover { background: #0D47A1; }
        
        .result {
            margin-top: 10px;
            padding: 15px;
            background: #E8F5E9;
            border-radius: 5px;
            font-weight: bold;
            display: none;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>JavaScript Basics Lab</h1>

        <!-- 1. Greeting -->
        <div class="card">
            <h3>1. Personalized Greeting</h3>
            <input type="text" id="nameInput" placeholder="Enter your name">
            <button onclick="greet()">Greet Me!</button>
            <div class="result" id="greetResult"></div>
        </div>

        <!-- 2. Calculator -->
        <div class="card">
            <h3>2. Simple Calculator</h3>
            <input type="number" id="num1" placeholder="First number">
            <input type="number" id="num2" placeholder="Second number">
            <select id="operator">
                <option value="+">+ Add</option>
                <option value="-">− Subtract</option>
                <option value="*">× Multiply</option>
                <option value="/">÷ Divide</option>
            </select>
            <button onclick="calculate()">Calculate</button>
            <div class="result" id="calcResult"></div>
        </div>

        <!-- 3. Grade Checker -->
        <div class="card">
            <h3>3. Grade Checker</h3>
            <input type="number" id="marks" placeholder="Enter marks (0-100)" min="0" max="100">
            <button onclick="checkGrade()">Check Grade</button>
            <div class="result" id="gradeResult"></div>
        </div>

        <!-- 4. Age Calculator -->
        <div class="card">
            <h3>4. Age Calculator</h3>
            <input type="number" id="birthYear" placeholder="Enter birth year (e.g., 2005)">
            <button onclick="calcAge()">Calculate Age</button>
            <div class="result" id="ageResult"></div>
        </div>
    </div>

    <script>
        function showResult(id, message) {
            const el = document.getElementById(id);
            el.textContent = message;
            el.style.display = 'block';
        }

        // 1. Greeting
        function greet() {
            const name = document.getElementById('nameInput').value.trim();
            if (name === '') {
                showResult('greetResult', 'Please enter your name!');
                return;
            }
            const hour = new Date().getHours();
            let greeting;
            if (hour < 12) greeting = 'Good Morning';
            else if (hour < 17) greeting = 'Good Afternoon';
            else greeting = 'Good Evening';
            showResult('greetResult', `${greeting}, ${name}! Welcome to Web Technology.`);
        }

        // 2. Calculator
        function calculate() {
            const a = parseFloat(document.getElementById('num1').value);
            const b = parseFloat(document.getElementById('num2').value);
            const op = document.getElementById('operator').value;
            
            if (isNaN(a) || isNaN(b)) {
                showResult('calcResult', 'Please enter valid numbers!');
                return;
            }
            
            let result;
            switch (op) {
                case '+': result = a + b; break;
                case '-': result = a - b; break;
                case '*': result = a * b; break;
                case '/': 
                    if (b === 0) { showResult('calcResult', 'Cannot divide by zero!'); return; }
                    result = a / b; 
                    break;
            }
            showResult('calcResult', `${a} ${op} ${b} = ${result}`);
        }

        // 3. Grade Checker
        function checkGrade() {
            const marks = parseInt(document.getElementById('marks').value);
            if (isNaN(marks) || marks < 0 || marks > 100) {
                showResult('gradeResult', 'Please enter marks between 0 and 100!');
                return;
            }
            
            let grade, emoji;
            if (marks >= 90) { grade = 'A+ (Outstanding)'; emoji = '🏆'; }
            else if (marks >= 75) { grade = 'A (Excellent)'; emoji = '⭐'; }
            else if (marks >= 60) { grade = 'B (Good)'; emoji = '👍'; }
            else if (marks >= 40) { grade = 'C (Average)'; emoji = '📝'; }
            else { grade = 'F (Fail)'; emoji = '❌'; }
            
            showResult('gradeResult', `${emoji} Marks: ${marks} → Grade: ${grade}`);
        }

        // 4. Age Calculator
        function calcAge() {
            const birthYear = parseInt(document.getElementById('birthYear').value);
            const currentYear = new Date().getFullYear();
            
            if (isNaN(birthYear) || birthYear < 1900 || birthYear > currentYear) {
                showResult('ageResult', 'Please enter a valid birth year!');
                return;
            }
            
            const age = currentYear - birthYear;
            const canVote = age >= 18 ? 'Yes ✅' : 'No ❌';
            showResult('ageResult', `Age: ${age} years | Can vote: ${canVote}`);
        }
    </script>

</body>
</html>
```

---

## Summary

| Concept | Key Takeaway |
|---------|-------------|
| JavaScript | Adds interactivity to web pages |
| `let` / `const` | Modern variable declarations |
| Data types | String, Number, Boolean, null, undefined, Array, Object |
| `===` | Always use strict equality |
| `if/else` | Conditional logic |
| Output | `alert()`, `console.log()`, `document.getElementById()` |

---

*Day 26 of 55 | Unit 5 — JavaScript | Web Technology (25BCA060)*
