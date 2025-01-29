# 🎭 Lesson 1: Web Animation & Accessibility 🎭  

## 💡 Mission: Make Animations That Enhance, Not Distract!  
**Objective:** Learn how to **create animations** using **CSS & JavaScript** while ensuring they **don’t harm users with motion sensitivity** or **cause accessibility issues**.  

### 🔹 Topics Covered:  
✅ When to Use & Avoid Animations  
✅ CSS Transitions & Animations (Best Practices for Accessibility)  
✅ JavaScript Animations & Reduced Motion Preferences  
✅ Testing Motion Preferences & Alternative Solutions  

---

## 📖 Part 1: Why Accessibility Matters for Animation?  

🎯 **Problem:** Some users have motion sensitivity disorders like **Vestibular Disorders** or **Photosensitive Epilepsy**, making certain animations uncomfortable or even harmful.  

💡 **Solution:** Web animations should:  
✅ **Enhance usability** (not be purely decorative).  
✅ **Respect user preferences** (e.g., reduced motion settings).  
✅ **Avoid triggering disorders** (flashes, rapid motion, excessive movement).  

📌 **WCAG Guidelines for Motion Sensitivity:**  
- **Avoid flashing animations** faster than **3 times per second**.  
- **Provide an option to disable animations** (if they are not essential).  
- **Use the `prefers-reduced-motion` media query** to check user preferences.  

---

## 🛠️ Lab Challenges: Accessible Animation in Action!  

### 🚀 Challenge 1: Basic CSS Animation (With a Safe Approach)  

📌 **Task:** Create a simple **fade-in effect** that respects accessibility guidelines.  

#### 🔹 HTML:  
```html
<div class="box">Accessible Animation</div>
```

#### 🔹 CSS:  
```css
.box {
  width: 200px;
  height: 100px;
  background-color: darkblue;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 18px;
  border-radius: 10px;
  opacity: 0;
  animation: fadeIn 2s ease-in-out forwards;
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}
```

🎯 **Bonus:** Add a **hover effect** that changes the background color smoothly.  

---

### 🚀 Challenge 2: Add a "Reduced Motion" Alternative  

📌 **Task:** Use the `prefers-reduced-motion` media query to disable animations for users who prefer minimal movement.  

#### 🔹 CSS Update:  
```css
@media (prefers-reduced-motion: reduce) {
  .box {
    animation: none;
  }
}
```

🔹 **Why?** If a user has **motion sensitivity settings enabled**, animations will **automatically be disabled**.  

🎯 **Bonus:** Add a **toggle switch** for users to turn animations **on/off**.  

---

### 🚀 Challenge 3: JavaScript Animation with Reduced Motion Preference  

📌 **Task:** Create a **bouncing animation** using JavaScript that **respects user motion preferences**.  

#### 🔹 HTML:  
```html
<button id="animateBtn">Bounce the Box!</button>
<div id="animatedBox"></div>
```

#### 🔹 CSS:  
```css
#animatedBox {
  width: 100px;
  height: 100px;
  background-color: red;
  position: relative;
}
```

#### 🔹 JavaScript:  
```js
document.getElementById("animateBtn").addEventListener("click", function() {
  let prefersReducedMotion = window.matchMedia("(prefers-reduced-motion: reduce)").matches;
  if (prefersReducedMotion) {
    alert("Motion is disabled for accessibility.");
    return;
  }
  
  let box = document.getElementById("animatedBox");
  box.style.transition = "transform 0.5s ease-in-out";
  box.style.transform = "translateY(-50px)";
  
  setTimeout(() => {
    box.style.transform = "translateY(0)";
  }, 500);
});
```

🎯 **Bonus:** Instead of disabling animation completely, make a **gentler effect** for users who prefer reduced motion.  

---

### 🚀 Challenge 4: Creating a Scroll Animation (That Respects Accessibility!)  

📌 **Task:** Make a section **fade in when scrolled into view**, but disable it for users with motion sensitivity.  

#### 🔹 HTML:  
```html
<section id="animatedSection">
  <h2>Scroll down to see me!</h2>
</section>
```

#### 🔹 CSS:  
```css
#animatedSection {
  opacity: 0;
  transform: translateY(50px);
  transition: opacity 1s ease-out, transform 1s ease-out;
}

#animatedSection.visible {
  opacity: 1;
  transform: translateY(0);
}
```

#### 🔹 JavaScript:  
```js
const section = document.getElementById("animatedSection");
const observer = new IntersectionObserver(entries => {
  if (entries[0].isIntersecting) {
    let prefersReducedMotion = window.matchMedia("(prefers-reduced-motion: reduce)").matches;
    if (!prefersReducedMotion) {
      section.classList.add("visible");
    }
  }
});

observer.observe(section);
```

🎯 **Bonus:** Instead of a fade effect, make it a **color transition** for reduced-motion users.  

---

## 🎒 Homework & Next Steps  
✅ **Finish at least two animation challenges.**  
✅ **Test animations with accessibility tools like `prefers-reduced-motion`.**  
✅ **Run your animations through a screen reader (NVDA, VoiceOver) to see how they interact.**  

📢 **Next Lesson:** **Building an Accessible Web App** – Taking all our knowledge so far and applying it to a **real-world project**! 🚀  

---

## 🛠️ Additional Resources  

📌 **CSS Animations & Accessibility Best Practices:**  
🔗 [CSS Tricks - Introduction to Reduced Motion Media Query](https://css-tricks.com/introduction-reduced-motion-media-query/)  

📌 **Google Developers Guide on Motion Accessibility:**  
🔗 [Google Web Dev - prefers-reduced-motion](https://web.dev/prefers-reduced-motion/)  

📌 **Mozilla MDN Web Docs – prefers-reduced-motion:**  
🔗 [MDN prefers-reduced-motion](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion)  

📌 **FreeCodeCamp – Accessible Animations:**  
🔗 [FreeCodeCamp - Accessible Web Animations](https://www.freecodecamp.org/news/accessible-web-animation/)  

---

# 🎉 Lesson Wrap-Up  
✅ Animations should **enhance** the user experience, not distract.  
✅ **Use `prefers-reduced-motion`** to respect user settings.  
✅ **Test animations** with accessibility tools and screen readers.  
✅ **Provide alternative motion effects** (like color changes instead of movement).  
