project/
│── index.html
│── style.css
│── script.js


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>JavaScript Assignment</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>JavaScript Assignment Demo</h1>

  <div id="message"></div>

  <button id="greetBtn">Click for Greeting</button>
  <button id="listBtn">Show Number List</button>
  <button id="colorBtn">Change Background</button>

  <ul id="numberList"></ul>

  <script src="script.js"></script>
</body>


body {
  font-family: Arial, sans-serif;
  text-align: center;
  margin: 40px;
  background-color: #f0f0f0;
}

h1 {
  color: #333;
}

button {
  margin: 10px;
  padding: 10px 15px;
  font-size: 16px;
  cursor: pointer;
  border-radius: 8px;
  border: none;
  background-color: #4CAF50;
  color: white;
}

button:hover {
  background-color: #45a049;
}

#message {
  margin: 20px;
  font-size: 18px;
  font-weight: bold;
  color: #444;
}

#numberList {
  margin-top: 20px;
  list-style: none;
  padding: 0;
}

// =============================
// Part 1: Variable Declarations and Conditionals
// =============================
let userName = "Alex";
let userAge = 20;

if (userAge >= 18) {
  console.log(userName + " is an adult.");
} else {
  console.log(userName + " is a minor.");
}

// =============================
// Part 2: Custom Functions
// =============================

// Function 1: Greeting Message
function greetUser(name) {
  return "Hello, " + name + "! Welcome to the site.";
}

// Function 2: Generate Number List
function generateNumbers(limit) {
  let numbers = [];
  for (let i = 1; i <= limit; i++) {
    numbers.push(i);
  }
  return numbers;
}

// =============================
// Part 3: Loop Examples
// =============================

// Example 1: For loop
for (let i = 1; i <= 3; i++) {
  console.log("For loop count: " + i);
}

// Example 2: While loop
let count = 0;
while (count < 3) {
  console.log("While loop count: " + count);
  count++;
}

// =============================
// Part 4: DOM Interactions
// =============================

// Interaction 1: Display greeting message on button click
document.getElementById("greetBtn").addEventListener("click", function() {
  document.getElementById("message").innerText = greetUser(userName);
});

// Interaction 2: Show a list of numbers in the DOM
document.getElementById("listBtn").addEventListener("click", function() {
  let numbers = generateNumbers(5);
  let listElement = document.getElementById("numberList");
  listElement.innerHTML = ""; // clear old list

  numbers.forEach(function(num) {
    let li = document.createElement("li");
    li.textContent = "Number: " + num;
    listElement.appendChild(li);
  });
});

// Interaction 3: Change background color of the page
document.getElementById("colorBtn").addEventListener("click", function() {
  document.body.style.backgroundColor =
    document.body.style.backgroundColor === "lightblue" ? "#f0f0f0" : "lightblue";
});
