# 📱 Lesson 4: Progressive Web Apps (PWAs) & Accessibility ♿  

## 💡 Mission: Make Web Apps Work Offline & Stay Accessible!  
**Objective:** Learn how to build **Progressive Web Apps (PWAs)** that are **accessible, fast, and work even without an internet connection**.  

### 🔹 Topics Covered:  
✅ **What is a PWA?** (Core Features & Benefits)  
✅ **Making a PWA Keyboard & Screen Reader-Friendly**  
✅ **Using Service Workers for Offline Support**  
✅ **Adding a Web App Manifest for Installation**  
✅ **Testing & Deploying an Accessible PWA**  

---

## 📖 Part 1: What is a Progressive Web App (PWA)?  

🎯 **A PWA is a web app that behaves like a native app**.  
- Can be **installed** on a phone like an app 📱  
- Works **offline** and loads **instantly** ⚡  
- Supports **push notifications** 🔔  
- Designed to be **accessible & user-friendly** ♿  

📌 **Key Features of a PWA:**  
✅ **Responsive Design** – Works on all screen sizes 📏  
✅ **Offline Support** – Loads even with no internet 🌍  
✅ **Fast Loading** – Uses caching for speed 🚀  
✅ **Installable** – Can be added to the home screen 📲  

---

## 🛠️ Lab Challenges: Building an Accessible PWA  

### 🚀 Challenge 1: Set Up a Simple PWA  

📌 **Task:** Create a basic web app that works as a PWA.  

#### 🔹 Folder Structure:  
```
📂 myPWA/
 ├── 📄 index.html
 ├── 📄 styles.css
 ├── 📄 app.js
 ├── 📄 service-worker.js
 ├── 📄 manifest.json
 ├── 📂 images/
 └── 📂 icons/
```

---

### 🚀 Challenge 2: Make the Web App Installable  

📌 **Task:** Add a **Web App Manifest** so users can install the app.  

#### 🔹 Create `manifest.json`:  
```json
{
  "name": "Accessible PWA",
  "short_name": "PWA",
  "description": "A Progressive Web App with accessibility features.",
  "start_url": "/index.html",
  "display": "standalone",
  "background_color": "#ffffff",
  "theme_color": "#000000",
  "icons": [
    {
      "src": "icons/icon-192x192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "icons/icon-512x512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ]
}
```

#### 🔹 Link the Manifest in `index.html`:  
```html
<link rel="manifest" href="manifest.json">
```

🎯 **Bonus:** Test the **"Add to Home Screen"** prompt in Chrome!  

---

### 🚀 Challenge 3: Enable Offline Support with a Service Worker  

📌 **Task:** Use a **Service Worker** to cache assets for offline access.  

#### 🔹 Create `service-worker.js`:  
```js
const CACHE_NAME = "pwa-cache-v1";
const urlsToCache = [
  "/",
  "/index.html",
  "/styles.css",
  "/app.js",
  "/icons/icon-192x192.png",
  "/icons/icon-512x512.png"
];

self.addEventListener("install", (event) => {
  event.waitUntil(
    caches.open(CACHE_NAME).then((cache) => {
      return cache.addAll(urlsToCache);
    })
  );
});

self.addEventListener("fetch", (event) => {
  event.respondWith(
    caches.match(event.request).then((response) => {
      return response || fetch(event.request);
    })
  );
});
```

#### 🔹 Register the Service Worker in `app.js`:  
```js
if ("serviceWorker" in navigator) {
  navigator.serviceWorker.register("/service-worker.js")
    .then(() => console.log("Service Worker Registered"));
}
```

🎯 **Bonus:** Show an **"Offline Mode" message** when the user is offline.  

---

### 🚀 Challenge 4: Improve Keyboard & Screen Reader Accessibility  

📌 **Task:** Ensure users can **navigate the PWA easily** with a keyboard & screen reader.  

#### 🔹 Add Skip Links for Fast Navigation:  
```html
<a href="#mainContent" class="skip-link">Skip to Main Content</a>
<main id="mainContent">...</main>
```

#### 🔹 Improve Focus Styles in `styles.css`:  
```css
button:focus, a:focus {
  outline: 3px solid yellow;
}
```

#### 🔹 Enable Screen Reader-Friendly Alerts in `app.js`:  
```js
function showLiveAlert(message) {
  let alert = document.createElement("div");
  alert.setAttribute("role", "alert");
  alert.innerText = message;
  document.body.appendChild(alert);
  
  setTimeout(() => {
    alert.remove();
  }, 3000);
}
```

🎯 **Bonus:** Add **dark mode & font size adjustments** for better readability.  

---

### 🚀 Challenge 5: Test Your PWA & Accessibility  

📌 **Task:** Test your PWA on mobile and with **accessibility tools**.  

#### ✅ Test Checklist:  
✅ **Install the PWA on a phone or desktop**  
✅ **Turn off the internet & see if it loads**  
✅ **Test with screen readers (VoiceOver, NVDA, ChromeVox)**  
✅ **Run a Lighthouse audit in Chrome DevTools**  

🎯 **Bonus:** Add a **"Reduce Motion" option** using `prefers-reduced-motion`.  

---

## 🎒 Homework & Next Steps  
✅ **Complete your first PWA & test accessibility features**.  
✅ **Make sure it works offline & installs on a phone**.  
✅ **Run Lighthouse accessibility tests & improve your score.**  

📢 **Next Lesson:** **Voice-Controlled Websites – Implementing Speech-Based Interactions!** 🎤🚀  

---

## 🛠️ Additional Resources  

📌 **Google’s Guide to PWAs**  
🔗 [https://web.dev/progressive-web-apps/](https://web.dev/progressive-web-apps/)  

📌 **MDN Docs: Service Workers & Caching**  
🔗 [https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API)  

📌 **Google Lighthouse (PWA Testing)**  
🔗 [https://developers.google.com/web/tools/lighthouse](https://developers.google.com/web/tools/lighthouse)  

📌 **Using prefers-reduced-motion for PWAs**  
🔗 [https://web.dev/prefers-reduced-motion/](https://web.dev/prefers-reduced-motion/)  

---

# 🎉 Lesson Wrap-Up  
✅ We built a **PWA that installs & works offline**.  
✅ We added **Service Workers for caching**.  
✅ We improved **keyboard & screen reader navigation**.  
✅ We tested **PWA performance & accessibility**.  
