# Animated Card Slider for Power BI

This repository contains my test files for recreating an animated card slider inspired by [Pavan Yuvan's CodePen](https://codepen.io/Pavan_Yuvan/pen/vXepGe).

---

## 🗂️ Project Structure

1️⃣ **Step 1 — HTML + JS Test**  
- `slider-test.html`  
  ✅ This file uses the original HTML, CSS, and JavaScript to test the slider effect in the browser.  
  ✅ Helps me understand how the slider works and what animations are handled by JS.

2️⃣ **Step 2 — Power BI DAX Version**  
- `slider-powerbi-dax.txt` (or `.pbix` if you save inside Power BI)  
  ✅ In this step, I removed the JavaScript parts to adapt the design to work inside Power BI.  
  ✅ Rebuilt the slider’s structure and styling using only HTML and CSS, rendered through a DAX measure or a custom column with HTML Viewer visual.

---

## 💡 Purpose

The goal of this project is to:
- Explore how far a dynamic slider effect can be replicated in Power BI without JavaScript.
- Learn how to convert web components into Power BI-friendly HTML/CSS for better user experience.
- Improve my skills with DAX-generated HTML.

---

## 📌 Notes

- The CodePen inspiration uses Swiper.js for functionality.  
  This is not available inside Power BI visuals, so I tested a static version instead.
- I may update this repo with different slider versions or improvements.

---

## 📄 Credits

- Original idea by [Pavan Yuvan on CodePen](https://codepen.io/Pavan_Yuvan/pen/vXepGe).

---

## ⚡ Try It Yourself!

1. Clone this repo  
2. Open the `slider-test.html` in your browser to see the original effect.
3. Use the `slider-powerbi-dax.txt` as a template to build your own DAX measure in Power BI.

---

## 🔗 License

This is a test project for learning purposes only.
