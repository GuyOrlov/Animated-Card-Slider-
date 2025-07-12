# Result Slider — HTML/CSS Card Slider for Power BI

This project shows how I recreated an animated card slider inspired by [Pavan Yuvan’s CodePen](https://codepen.io/Pavan_Yuvan/pen/vXepGe) to test in Power BI using HTML and CSS only — no JavaScript!

---

## 🎯 What’s Inside

✅ `slider-test.html`  
A simple file to test the original slider effect using HTML, CSS, and JavaScript in the browser.

✅ `ResultSlider` (DAX measure example)  
A fully static version of the slider, adapted to run in Power BI by removing all JavaScript.  
This uses a **DAX variable** containing HTML and CSS, rendered with an HTML Viewer custom visual.

---

## ⚙️ How to Use in Power BI

1️⃣ Add a new **DAX measure** to your Power BI data model, for example:
```DAX

ResultSlider = 
"
<style>
  :root {
    --deepBlue: #29323F;
    --yellow: #FCEE6D;
    --white: #fff;
  }
  * {
    box-sizing: border-box;
    margin: 0; 
    padding: 0;
    outline: none;
    border: none;
  }
  .wrapper {
    display: flex;
    width: 750px;
    height: 450px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    overflow: hidden;
    font-family: Arial, sans-serif;
  }
  .results-list {
    width: 40%;
    background: var(--deepBlue);
    display: flex;
    flex-direction: column;
  }
  .results-list label {
    padding: 20px 25px;
    color: var(--white);
    cursor: pointer;
    transition: 0.3s;
  }
  input[type='radio'] { display: none; }
  input#tab1:checked ~ .results-list label[for='tab1'],
  input#tab2:checked ~ .results-list label[for='tab2'],
  input#tab3:checked ~ .results-list label[for='tab3'] {
    background: var(--yellow);
    color: var(--deepBlue);
  }
  .results-preview {
    position: relative;
    width: 60%;
    background: var(--yellow);
    overflow: hidden;
  }
  .result-card {
    position: absolute;
    top: 100%;
    left: 7.5%;
    width: 85%;
    height: 50%;
    background: var(--white);
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    transition: top 0.8s cubic-bezier(.3,-0.91,.6,1.52);
  }
  input#tab1:checked ~ .results-preview .card1,
  input#tab2:checked ~ .results-preview .card2,
  input#tab3:checked ~ .results-preview .card3 {
    top: 25%;
  }
  .result-card .line {
    width: 3px;
    height: 60px;
    background: var(--deepBlue);
    margin: 4px 0;
    opacity: 0;
    animation: none;
  }
  input#tab1:checked ~ .results-preview .card1 .line,
  input#tab2:checked ~ .results-preview .card2 .line,
  input#tab3:checked ~ .results-preview .card3 .line {
    animation: lineAnim 1s forwards;
  }
  @keyframes lineAnim {
    0% { opacity: 0; transform: scaleY(0); }
    50% { opacity: 1; transform: scaleY(1.2); }
    100% { opacity: 0; transform: scaleY(0); }
  }
</style>

<div class='wrapper'>
  <input type='radio' name='tab' id='tab1' checked>
  <input type='radio' name='tab' id='tab2'>
  <input type='radio' name='tab' id='tab3'>

  <div class='results-list'>
    <label for='tab1'>Result One</label>
    <label for='tab2'>Result Two</label>
    <label for='tab3'>Result Three</label>
  </div>

  <div class='results-preview'>
    <div class='result-card card1'>
      <h3>Result One</h3>
      <div class='line'></div>
      <div class='line'></div>
    </div>
    <div class='result-card card2'>
      <h3>Result Two</h3>
      <div class='line'></div>
      <div class='line'></div>
    </div>
    <div class='result-card card3'>
      <h3>Result Three</h3>
      <div class='line'></div>
      <div class='line'></div>
    </div>
  </div>
</div>
"
