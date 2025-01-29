# 🚀 Lesson 0: JavaScript Basics for Accessibility  

## 💡 Mission: Master JavaScript Fundamentals Before Building Accessible Web Apps!  
**Objective:** Learn the **core JavaScript concepts** needed for web accessibility, including **variables, functions, loops, events, and DOM manipulation**.  

### 🔹 Topics Covered:  
✅ **What is JavaScript?**  
✅ **Variables & Data Types**  
✅ **Operators & Conditional Statements**  
✅ **Loops & Arrays**  
✅ **Functions & Events**  
✅ **DOM Manipulation (Updating Web Pages Dynamically)**  

---

## 📖 Part 1: What is JavaScript?  

🎯 **JavaScript is the language that makes web pages interactive!**  
- Allows **buttons, forms, animations, and accessibility features**.  
- Runs **in the browser** (no installation needed).  
- Used in **web apps, games, and AI-powered accessibility tools**.  

📌 **How JavaScript Works:**  
✅ **HTML** (Structure) → Defines the page layout.  
✅ **CSS** (Styling) → Makes the page look nice.  
✅ **JavaScript** (Behavior) → Adds interactivity and accessibility!  

---

## 🛠️ Lab Challenges: JavaScript Basics  

### 🚀 Challenge 1: Declare Variables & Display Values  

📌 **Task:** Store your name and favorite number in variables and log them.  

#### 🔹 JavaScript:  
```js
let name = "Alex";
let favoriteNumber = 7;

console.log("My name is " + name);
console.log("My favorite number is " + favoriteNumber);
```

🎯 **Bonus:** Use **template literals** instead of `+`:  
```js
console.log(`My name is ${name} and my favorite number is ${favoriteNumber}`);
```

---

### 🚀 Challenge 2: Simple Math Operations  

📌 **Task:** Add, subtract, multiply, and divide numbers using JavaScript.  

#### 🔹 JavaScript:  
```js
let a = 10;
let b = 5;

console.log("Addition: " + (a + b));
console.log("Subtraction: " + (a - b));
console.log("Multiplication: " + (a * b));
console.log("Division: " + (a / b));
```

🎯 **Bonus:** Ask the user for numbers using `prompt()`.  
```js
let userNumber = prompt("Enter a number:");
console.log(`You entered: ${userNumber}`);
```

---

### 🚀 Challenge 3: Conditional Statements (If/Else)  

📌 **Task:** Check if a number is **even or odd** using JavaScript.  

#### 🔹 JavaScript:  
```js
let number = 7;

if (number % 2 === 0) {
  console.log("Even number");
} else {
  console.log("Odd number");
}
```

🎯 **Bonus:** Let the user input a number using `prompt()`.  

---

### 🚀 Challenge 4: Loops & Arrays  

📌 **Task:** Create an **array of colors** and print each color using a loop.  

#### 🔹 JavaScript:  
```js
let colors = ["Red", "Blue", "Green", "Yellow"];

for (let i = 0; i < colors.length; i++) {
  console.log(colors[i]);
}
```

🎯 **Bonus:** Use a **`forEach` loop** instead.  
```js
colors.forEach(color => console.log(color));
```

---

### 🚀 Challenge 5: Functions & Button Click Events  

📌 **Task:** Create a **function that logs a message** when a button is clicked.  

#### 🔹 HTML:  
```html
<button id="clickMe">Click Me</button>
```

#### 🔹 JavaScript:  
```js
document.getElementById("clickMe").addEventListener("click", function() {
  console.log("Button clicked!");
});
```

🎯 **Bonus:** Change the button text when clicked!  
```js
document.getElementById("clickMe").addEventListener("click", function() {
  this.innerText = "Clicked!";
});
```

---

### 🚀 Challenge 6: Change Web Page Content (DOM Manipulation)  

📌 **Task:** Change a webpage’s content dynamically with JavaScript.  

#### 🔹 HTML:  
```html
<p id="message">Hello, world!</p>
<button id="changeText">Change Text</button>
```

#### 🔹 JavaScript:  
```js
document.getElementById("changeText").addEventListener("click", function() {
  document.getElementById("message").innerText = "Text changed!";
});
```

🎯 **Bonus:** Change **text color** dynamically!  
```js
document.getElementById("changeText").addEventListener("click", function() {
  let message = document.getElementById("message");
  message.innerText = "Text changed!";
  message.style.color = "blue";
});
```

---

### 🚀 Challenge 7: Create an Interactive Input Field  

📌 **Task:** Let users type text, and **display it on the page** when they press a button.  

#### 🔹 HTML:  
```html
<input type="text" id="userInput" placeholder="Type something">
<button id="displayText">Display</button>
<p id="output"></p>
```

#### 🔹 JavaScript:  
```js
document.getElementById("displayText").addEventListener("click", function() {
  let input = document.getElementById("userInput").value;
  document.getElementById("output").innerText = input;
});
```

🎯 **Bonus:** Clear the input field after clicking!  
```js
document.getElementById("displayText").addEventListener("click", function() {
  let input = document.getElementById("userInput");
  document.getElementById("output").innerText = input.value;
  input.value = ""; // Clear input field
});
```

---

## 🎒 Homework & Next Steps  
✅ **Complete at least three JavaScript challenges**.  
✅ **Use `console.log()` to debug your code**.  
✅ **Modify the examples and experiment!**  

📢 **Next Lesson:** **Web Animation & Accessibility – Creating Smooth, Inclusive Interactions!** 🚀  

---

## 🛠️ Additional Resources  

📌 **JavaScript Basics (MDN Docs)**  
🔗 [https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics)  

📌 **JavaScript Loops & Arrays (W3Schools)**  
🔗 [https://www.w3schools.com/js/js_loop_for.asp](https://www.w3schools.com/js/js_loop_for.asp)  

📌 **Interactive JavaScript Exercises**  
🔗 [https://javascript.info/](https://javascript.info/)  

---

# 🎉 Lesson Wrap-Up  
✅ We covered **variables, math, conditionals, loops, functions, and events**.  
✅ We practiced **DOM manipulation** to change webpage content dynamically.  
✅ We prepared for **adding accessibility features in future lessons**.  

