ResultSlider2 = 
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
    text-align: center;
    transition: top 0.8s cubic-bezier(.3,-0.91,.6,1.52);
  }
  .result-card svg {
    margin: 10px 0;
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
    <label for='tab1'>Revenue</label>
    <label for='tab2'>Customer</label>
    <label for='tab3'>Conversion</label>
  </div>

  <div class='results-preview'>
    <div class='result-card card1'>
      <h3>Revenue Report</h3>
      <p style='margin: 5px 0;'>Q1 Revenue: £250,000</p>
      <svg width='50' height='50' viewBox='0 0 24 24' xmlns='http://www.w3.org/2000/svg'>
        <circle cx='12' cy='12' r='10' stroke='#29323F' stroke-width='2' fill='none'/>
        <path d='M8 12h8' stroke='#29323F' stroke-width='2'/>
        <path d='M12 8v8' stroke='#29323F' stroke-width='2'/>
      </svg>
      <div class='line'></div>
      <div class='line'></div>
    </div>

    <div class='result-card card2'>
      <h3>Customer Profile</h3>
      <p style='margin: 5px 0;'>Active Users: 1,200</p>
      <svg width='50' height='50' viewBox='0 0 24 24' xmlns='http://www.w3.org/2000/svg'>
        <circle cx='12' cy='8' r='4' stroke='#29323F' stroke-width='2' fill='none'/>
        <path d='M4 20c0-4 4-7 8-7s8 3 8 7' stroke='#29323F' stroke-width='2' fill='none'/>
      </svg>
      <div class='line'></div>
      <div class='line'></div>
    </div>

    <div class='result-card card3'>
      <h3>Conversion Rate</h3>
      <p style='margin: 5px 0;'>Current Rate: 8.5%</p>
      <svg width='50' height='50' viewBox='0 0 24 24' xmlns='http://www.w3.org/2000/svg'>
        <path d='M3 17l6-6 4 4 8-8' stroke='#29323F' stroke-width='2' fill='none'/>
        <path d='M14 7h7v7' stroke='#29323F' stroke-width='2' fill='none'/>
      </svg>
      <div class='line'></div>
      <div class='line'></div>
    </div>
  </div>
</div>
"
