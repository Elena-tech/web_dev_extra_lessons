
# 🏗️ Lesson 2: Building an Accessible Web App ♿  

## 💡 Mission: Apply Accessibility Best Practices to a Real Web App!  
**Objective:** Use **HTML, CSS, JavaScript, and ARIA attributes** to build a **fully accessible interactive web app** that is **keyboard-navigable, screen reader-friendly, and usable by all**.  

### 🔹 Topics Covered:  
✅ Structuring an App with **Semantic HTML**  
✅ Making Forms **Accessible & Validated**  
✅ Keyboard Navigation & **Focus Management**  
✅ Using **ARIA Roles & Live Regions**  
✅ Testing Accessibility with **DevTools & Screen Readers**  

---

## 📖 Part 1: Planning Your Accessible Web App  

### 🎯 **What We'll Build:**  
A **To-Do List Web App** where users can:  
✅ Add, complete, and remove tasks  
✅ Navigate via **keyboard & screen readers**  
✅ Receive **live feedback** on form actions  

---

## 🛠️ Lab Challenges: Hands-on Accessibility Fixes!  

### 🚀 Challenge 1: Structuring the Web App with Semantic HTML  

📌 **Task:** Replace `<div>` elements with meaningful **semantic HTML tags** for structure.  

#### 🔹 HTML Structure Before (❌ Bad Example):  
```html
<div>
  <div>My Tasks</div>
  <div>
    <input type="text" id="taskInput">
    <button>Add Task</button>
  </div>
  <div id="taskList"></div>
</div>
```

#### ✅ **Improved Version with Semantic HTML:**  
```html
<header>
  <h1>My Accessible To-Do List</h1>
</header>
<main>
  <form id="taskForm">
    <label for="taskInput">Enter a Task:</label>
    <input type="text" id="taskInput" aria-describedby="taskInstructions">
    <button type="submit">Add Task</button>
    <p id="taskInstructions">Press Enter to add a task.</p>
  </form>
  <section aria-live="polite">
    <ul id="taskList"></ul>
  </section>
</main>
```

🎯 **Bonus:** Add a `<footer>` with accessibility links!  

---

### 🚀 Challenge 2: Add Accessible Form Validation  

📌 **Task:** Ensure that error messages **are screen reader-friendly** and displayed **live** when input is invalid.  

#### 🔹 HTML:  
```html
<form id="taskForm">
  <label for="taskInput">New Task:</label>
  <input type="text" id="taskInput" aria-describedby="errorMsg">
  <button type="submit">Add Task</button>
  <p id="errorMsg" class="error" aria-live="assertive"></p>
</form>
```

#### 🔹 JavaScript:  
```js
document.getElementById("taskForm").addEventListener("submit", function(event) {
  event.preventDefault();
  let taskInput = document.getElementById("taskInput");
  let errorMsg = document.getElementById("errorMsg");

  if (!taskInput.value.trim()) {
    errorMsg.innerText = "Please enter a task!";
    taskInput.focus();
  } else {
    errorMsg.innerText = "";
    addTask(taskInput.value);
    taskInput.value = "";
  }
});
```

🎯 **Bonus:** Add a **clear button** that resets the form.  

---

### 🚀 Challenge 3: Implement Keyboard Navigation  

📌 **Task:** Make sure users can navigate and complete tasks using only the **keyboard**.  

#### 🔹 JavaScript (Keyboard Event Handling):  
```js
document.addEventListener("keydown", function(event) {
  let activeElement = document.activeElement;
  
  if (event.key === "Enter" && activeElement.tagName === "BUTTON") {
    activeElement.click();
  }
});
```

🎯 **Bonus:** Add a **skip-to-content link** for quick keyboard navigation.  

---

### 🚀 Challenge 4: Enhance Screen Reader Support with ARIA  

📌 **Task:** Use **ARIA attributes** to make **task updates live** for screen readers.  

#### 🔹 HTML:  
```html
<section aria-live="polite" id="taskListContainer">
  <ul id="taskList"></ul>
</section>
```

#### 🔹 JavaScript:  
```js
function addTask(taskText) {
  let taskList = document.getElementById("taskList");
  let taskItem = document.createElement("li");
  taskItem.innerText = taskText;
  
  let removeButton = document.createElement("button");
  removeButton.innerText = "Remove";
  removeButton.setAttribute("aria-label", `Remove task: ${taskText}`);
  removeButton.addEventListener("click", () => {
    taskItem.remove();
  });

  taskItem.appendChild(removeButton);
  taskList.appendChild(taskItem);
}
```

🎯 **Bonus:** Add **a success message live region** when a task is added.  

---

### 🚀 Challenge 5: Add Dark Mode for Customization  

📌 **Task:** Implement **a theme toggle** that remembers user preferences.  

#### 🔹 HTML:  
```html
<button id="themeToggle">Enable Dark Mode</button>
```

#### 🔹 CSS:  
```css
.dark-mode {
  background-color: #222;
  color: white;
}
```

#### 🔹 JavaScript:  
```js
document.getElementById("themeToggle").addEventListener("click", function() {
  document.body.classList.toggle("dark-mode");
  localStorage.setItem("theme", document.body.classList.contains("dark-mode") ? "dark" : "light");
});

window.onload = function() {
  if (localStorage.getItem("theme") === "dark") {
    document.body.classList.add("dark-mode");
  }
};
```

🎯 **Bonus:** Add **a slider for font size adjustments**.  

---

## 🎒 Homework & Next Steps  
✅ **Complete the Accessible To-Do List app** with at least **3 accessibility improvements.**  
✅ **Test your app with a screen reader (NVDA, VoiceOver, ChromeVox).**  
✅ **Run Lighthouse accessibility tests & improve your score.**  

📢 **Next Lesson:** **AI & Accessibility – Speech Recognition, Text-to-Speech, and More!** 🚀  

---

## 🛠️ Additional Resources  

📌 **ARIA (Accessible Rich Internet Applications) Guide:**  
🔗 [https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA)  

📌 **WebAIM – Keyboard Accessibility**  
🔗 [https://webaim.org/techniques/keyboard/](https://webaim.org/techniques/keyboard/)  

📌 **Google Lighthouse (Built-in DevTools Accessibility Audit)**  
🔗 [https://developers.google.com/web/tools/lighthouse/](https://developers.google.com/web/tools/lighthouse/)  

📌 **FreeCodeCamp – Web Accessibility Course**  
🔗 [https://www.freecodecamp.org/news/accessibility-web-design-a11y/](https://www.freecodecamp.org/news/accessibility-web-design-a11y/)  

---

# 🎉 Lesson Wrap-Up  
✅ We structured our app with **semantic HTML**.  
✅ We added **form validation & live error messages**.  
✅ We implemented **ARIA attributes & keyboard navigation**.  
✅ We added **Dark Mode for customization**.  
