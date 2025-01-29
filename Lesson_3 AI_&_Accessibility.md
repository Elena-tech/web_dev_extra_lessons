# 🧠 Lesson 3: AI & Accessibility – Speech Recognition, Text-to-Speech, and More! 🎤  

## 💡 Mission: Use AI to Make the Web More Accessible!  
**Objective:** Learn how to **integrate AI-driven accessibility features** into web applications using **Speech Recognition, Text-to-Speech (TTS), and other AI-powered tools** to improve accessibility.  

### 🔹 Topics Covered:  
✅ **What is AI-powered accessibility?**  
✅ **Implementing Text-to-Speech (TTS) with JavaScript**  
✅ **Using Speech Recognition for Voice Commands**  
✅ **AI-Powered Image Descriptions & OCR (Optical Character Recognition)**  
✅ **Testing & Deploying an AI-Powered Accessible Web App**  

---

## 📖 Part 1: How AI Improves Accessibility  

🎯 **AI-powered accessibility helps users with:**  
- **Visual impairments** (screen readers, OCR for image recognition)  
- **Speech & motor disabilities** (voice commands, speech-to-text)  
- **Cognitive impairments** (simplified text, AI-generated summaries)  

📌 **Common AI Tools for Web Accessibility:**  
- **Screen readers with AI-powered voice synthesis**  
- **AI-generated alt text for images**  
- **Speech-to-text for voice-controlled navigation**  

---

## 🛠️ Lab Challenges: Hands-on AI Accessibility Enhancements!  

### 🚀 Challenge 1: Implement Text-to-Speech (TTS)  

📌 **Task:** Allow users to **click a button** to have text read aloud using the **Web Speech API**.  

#### 🔹 HTML:  
```html
<p id="text">Web accessibility makes the internet more inclusive for everyone.</p>
<button id="speakButton">🔊 Read Aloud</button>
```

#### 🔹 JavaScript (TTS using Web Speech API):  
```js
document.getElementById("speakButton").addEventListener("click", function() {
  let msg = new SpeechSynthesisUtterance(document.getElementById("text").innerText);
  window.speechSynthesis.speak(msg);
});
```

🎯 **Bonus:** Let users **pause & resume** speech!  

---

### 🚀 Challenge 2: Add Speech Recognition (Voice Commands)  

📌 **Task:** Enable **voice input** so users can **dictate text** instead of typing.  

#### 🔹 HTML:  
```html
<input type="text" id="voiceInput" placeholder="Speak to enter text">
<button id="startVoice">🎙️ Start Dictation</button>
```

#### 🔹 JavaScript (Speech Recognition API):  
```js
window.SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
let recognition = new SpeechRecognition();
recognition.interimResults = true;

document.getElementById("startVoice").addEventListener("click", function() {
  recognition.start();
});

recognition.addEventListener("result", function(event) {
  document.getElementById("voiceInput").value = event.results[0][0].transcript;
});
```

🎯 **Bonus:** Add **commands like "open settings" or "submit form"** using voice!  

---

### 🚀 Challenge 3: AI-Powered Image Descriptions  

📌 **Task:** Use **AI-based Optical Character Recognition (OCR)** to **extract text from images** for screen readers.  

#### 🔹 HTML:  
```html
<input type="file" id="imageUpload">
<button id="processImage">📷 Extract Text</button>
<p id="imageText"></p>
```

#### 🔹 JavaScript (OCR Using Tesseract.js):  
```js
document.getElementById("processImage").addEventListener("click", function() {
  let file = document.getElementById("imageUpload").files[0];
  if (file) {
    let reader = new FileReader();
    reader.onload = function() {
      Tesseract.recognize(reader.result, 'eng').then(({ data }) => {
        document.getElementById("imageText").innerText = data.text;
      });
    };
    reader.readAsDataURL(file);
  }
});
```

🎯 **Bonus:** Use AI APIs like **Google Vision** for **automatic alt text generation**!  

---

### 🚀 Challenge 4: Voice-Controlled Navigation  

📌 **Task:** Let users **navigate a webpage using voice commands** (e.g., "Go to Contact Page").  

#### 🔹 JavaScript (Voice Navigation):  
```js
recognition.addEventListener("result", function(event) {
  let command = event.results[0][0].transcript.toLowerCase();
  
  if (command.includes("home")) {
    window.location.href = "index.html";
  } else if (command.includes("contact")) {
    window.location.href = "contact.html";
  }
});
```

🎯 **Bonus:** Add a **voice confirmation response** using Speech Synthesis!  

---

## 🎒 Homework & Next Steps  
✅ **Implement at least one AI-powered accessibility feature** in a personal project.  
✅ **Test the speech recognition and text-to-speech features with different browsers**.  
✅ **Try an AI-powered accessibility tool like Google Vision API for image descriptions**.  

📢 **Next Lesson:** **Progressive Web Apps (PWAs) & Accessibility – Creating Offline-Friendly Experiences!** 🚀  

---

## 🛠️ Additional Resources  

📌 **Web Speech API – Mozilla MDN Docs:**  
🔗 [https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API)  

📌 **Tesseract.js (OCR for Image Text Extraction)**  
🔗 [https://tesseract.projectnaptha.com/](https://tesseract.projectnaptha.com/)  

📌 **Google Cloud Vision API (AI-Based Image Recognition)**  
🔗 [https://cloud.google.com/vision](https://cloud.google.com/vision)  

📌 **Accessible Voice UI Design Best Practices**  
🔗 [https://www.nngroup.com/articles/voice-user-interface-design/](https://www.nngroup.com/articles/voice-user-interface-design/)  

---

# 🎉 Lesson Wrap-Up  
✅ We implemented **Text-to-Speech (TTS) for reading content aloud**.  
✅ We enabled **Speech Recognition for voice-controlled input**.  
✅ We extracted **image text using AI-powered OCR**.  
✅ We built **Voice Navigation to improve usability**.  
