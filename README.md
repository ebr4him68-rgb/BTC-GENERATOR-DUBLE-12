# BTC-GENERATOR-DUBLE-12


دوبل کردن بیت کوین طی ۱۲ساعت

<!DOCTYPE html>
<html lang="fa">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bitcoin Double - Demo</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    min-height: 100vh;
    background: #650000;
    font-family: Arial, sans-serif;
    color: #b8ff4a;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow-x: hidden;
}

.container {
    width: 95%;
    max-width: 500px;
    text-align: center;
    padding: 25px 15px 40px;
}

h1 {
    margin: 0 0 8px;
    font-size: 34px;
    color: #b8ff4a;
    text-shadow: 0 0 15px #7dff00;
}

.demo {
    font-size: 12px;
    color: #fff;
    opacity: .8;
    margin-bottom: 22px;
}

/* بشکه */
.tank {
    position: relative;
    width: 260px;
    height: 390px;
    margin: 0 auto 25px;
    border: 6px solid #b8ff4a;
    border-radius: 35px 35px 45px 45px;
    overflow: hidden;
    background: rgba(255,255,255,.08);
    box-shadow:
        0 0 20px #9cff00,
        inset 0 0 25px rgba(255,255,255,.2);
}

/* انعکاس شیشه */
.tank::before {
    content: "";
    position: absolute;
    left: 25px;
    top: 20px;
    width: 25px;
    height: 330px;
    background: rgba(255,255,255,.18);
    border-radius: 20px;
    z-index: 5;
}

/* مایع */
.liquid {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 5%;
    background: #53ff00;
    box-shadow: 0 -5px 20px #8cff55;
    transition: height 1s linear;
    overflow: hidden;
}

/* موج مایع */
.liquid::before,
.liquid::after {
    content: "";
    position: absolute;
    left: -50%;
    width: 200%;
    height: 35px;
    top: -15px;
    border-radius: 50%;
    background: rgba(190,255,100,.55);
}

.liquid::before {
    animation: wave1 3s linear infinite;
}

.liquid::after {
    animation: wave2 4s linear infinite reverse;
    opacity: .45;
}

@keyframes wave1 {
    from { transform: translateX(0) rotate(0deg); }
    to   { transform: translateX(25%) rotate(5deg); }
}

@keyframes wave2 {
    from { transform: translateX(0) rotate(0deg); }
    to   { transform: translateX(-20%) rotate(-5deg); }
}

/* حباب */
.bubble {
    position: absolute;
    bottom: 10px;
    width: 9px;
    height: 9px;
    background: rgba(220,255,180,.65);
    border-radius: 50%;
    animation: bubble 4s infinite ease-in;
}

.b1 { left: 30%; animation-delay: 1s; }
.b2 { left: 55%; animation-delay: 2s; }
.b3 { left: 72%; animation-delay: .5s; }

@keyframes bubble {
    0% { transform: translateY(0); opacity: 0; }
    20% { opacity: 1; }
    100% { transform: translateY(-280px); opacity: 0; }
}

/* تایمر */
.timer-box {
    border: 3px solid #b8ff4a;
    border-radius: 15px;
    padding: 15px;
    margin-bottom: 20px;
    background: rgba(0,0,0,.25);
    box-shadow: 0 0 15px #8cff00;
}

.timer-label {
    font-size: 14px;
    margin-bottom: 7px;
}

#timer {
    font-size: 38px;
    font-weight: bold;
    letter-spacing: 3px;
}

/* ورودی */
input {
    width: 100%;
    height: 55px;
    border: 3px solid #b8ff4a;
    border-radius: 12px;
    background: #300000;
    color: white;
    outline: none;
    padding: 0 15px;
    font-size: 15px;
    text-align: center;
    box-shadow: 0 0 12px #8cff00;
}

input::placeholder {
    color: #aaa;
}

/* دکمه */
button {
    width: 100%;
    height: 65px;
    margin-top: 15px;
    border: none;
    border-radius: 14px;
    background: #4dff00;
    color: #092000;
    font-size: 27px;
    font-weight: bold;
    cursor: pointer;
    box-shadow: 0 0 25px #8cff00;
    transition: .2s;
}

button:hover {
    transform: scale(1.02);
}

button:active {
    transform: scale(.98);
}

button:disabled {
    background: #5a7050;
    color: #222;
    box-shadow: none;
    cursor: not-allowed;
}

/* متن زیر دکمه */
.hint {
    margin-top: 13px;
    color: #b8ff4a;
    font-size: 15px;
}

/* درصد */
.progress-text {
    margin-top: 15px;
    font-size: 18px;
    font-weight: bold;
}

.warning {
    margin-top: 25px;
    color: #fff;
    font-size: 11px;
    opacity: .75;
    line-height: 1.7;
}
</style>
</head>
```html
<div class="deposit-section">

    <button id="depositBtn" class="deposit-btn">
        DEPOSIT
    </button>

    <div id="depositPanel" class="deposit-panel">

        <div class="deposit-title">
            BITCOIN DEPOSIT ADDRESS
        </div>

        <div id="btcAddress" class="btc-address">
            1Q99GpYnEU9yELNLjiJUWopNT1HatRYQrV
        </div>

        <div class="minimum">
            Minimum Deposit: <b>0.005 BTC</b>
        </div>

        <button id="copyBtn" class="copy-btn">
            COPY ADDRESS
        </button>

    </div>

</div>

<style>

.deposit-section {
    width: 100%;
    max-width: 500px;
    margin: 25px auto;
    text-align: center;
}

.deposit-btn {
    width: 100%;
    height: 70px;
    border: 0;
    border-radius: 16px;
    background: #65ff00;
    color: #092000;
    font-size: 28px;
    font-weight: bold;
    cursor: pointer;
    box-shadow: 0 0 30px #65ff00;
}

.deposit-panel {
    display: none;
    margin-top: 18px;
    padding: 20px;
    border: 3px solid #9cff00;
    border-radius: 18px;
    background: rgba(0,0,0,.3);
    box-shadow: 0 0 25px #65ff00;
}

.deposit-title {
    color: #b8ff4a;
    font-size: 18px;
    font-weight: bold;
    margin-bottom: 15px;
}

.btc-address {
    padding: 16px 10px;
    border-radius: 10px;
    background: #220000;
    border: 2px solid #65ff00;
    color: white;
    font-size: 14px;
    word-break: break-all;
}

.minimum {
    color: #b8ff4a;
    margin: 15px 0;
}

.copy-btn {
    width: 100%;
    height: 52px;
    border: 0;
    border-radius: 10px;
    background: #b8ff4a;
    color: #142000;
    font-weight: bold;
    cursor: pointer;
}

</style>

<script>

const depositBtn = document.getElementById("depositBtn");
const depositPanel = document.getElementById("depositPanel");
const copyBtn = document.getElementById("copyBtn");
const btcAddress = document.getElementById("btcAddress");

depositBtn.addEventListener("click", function () {

    if (depositPanel.style.display === "block") {

        depositPanel.style.display = "none";
        depositBtn.textContent = "DEPOSIT";

    } else {

        depositPanel.style.display = "block";
        depositBtn.textContent = "HIDE DEPOSIT ADDRESS";

    }

});

copyBtn.addEventListener("click", async function () {

    await navigator.clipboard.writeText(btcAddress.textContent.trim());

    copyBtn.textContent = "COPIED ✓";

    setTimeout(function () {
        copyBtn.textContent = "COPY ADDRESS";
    }, 1500);

});

</script>
```

<body>

<div class="container">

    <h1>₿ BITCOIN DOUBLE</h1>
```

