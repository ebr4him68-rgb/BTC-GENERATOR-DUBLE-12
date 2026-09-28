

برای شروع دوبل کردن بیت کوین مقدار BTCخودرا به ادرس زیر ارسال کنید ودادرس خودتون رو ثبت کنید و ۱۲ساعت منتظر باشید
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Bitcoin Double</title>

<style>
*{
    box-sizing:border-box;
}

html,body{
    margin:0;
    padding:0;
    min-height:100%;
}

body{
    background:#650000;
    font-family:Arial,Tahoma,sans-serif;
    color:#baff4a;
}

.container{
    width:94%;
    max-width:520px;
    margin:0 auto;
    padding:25px 10px 45px;
    text-align:center;
}

.title{
    font-size:30px;
    font-weight:bold;
    margin-bottom:25px;
    color:#baff4a;
    text-shadow:0 0 15px #72ff00;
}

/* =========================
   TANK
========================= */

.tank{
    position:relative;
    width:300px;
    height:430px;
    margin:0 auto;
    overflow:hidden;

    border:7px solid #baff4a;
    border-radius:42px 42px 55px 55px;

    background:rgba(255,255,255,0.08);

    box-shadow:
        0 0 25px #72ff00,
        inset 0 0 35px rgba(255,255,255,0.25);
}

/* شیشه */
.tank::after{
    content:"";
    position:absolute;
    z-index:20;

    top:18px;
    left:25px;

    width:22px;
    height:375px;

    border-radius:20px;

    background:rgba(255,255,255,0.18);

    pointer-events:none;
}

/* =========================
   LIQUID
========================= */

.liquid{
    position:absolute;

    left:0;
    bottom:0;

    width:100%;
    height:5%;

    background:
        linear-gradient(
            to bottom,
            #baff70 0%,
            #5dff00 25%,
            #27b000 100%
        );

    box-shadow:
        0 -5px 25px #72ff00;

    transition:height 1s linear;
}

/* موج اول */
.wave{
    position:absolute;

    left:-60%;
    top:-18px;

    width:220%;
    height:45px;

    border-radius:50%;

    background:#c5ff80;

    opacity:0.75;

    animation:waveOne 3s linear infinite;
}

/* موج دوم */
.wave.second{
    top:-10px;

    opacity:0.35;

    animation:waveTwo 4s linear infinite reverse;
}

@keyframes waveOne{

    0%{
        transform:translateX(0) rotate(0deg);
    }

    50%{
        transform:translateX(12%) rotate(3deg);
    }

    100%{
        transform:translateX(25%) rotate(5deg);
    }
}

@keyframes waveTwo{

    0%{
        transform:translateX(0) rotate(0deg);
    }

    50%{
        transform:translateX(-10%) rotate(-3deg);
    }

    100%{
        transform:translateX(-20%) rotate(-5deg);
    }
}

/* =========================
   BUBBLES
========================= */

.bubble{
    position:absolute;

    bottom:5px;

    width:10px;
    height:10px;

    border-radius:50%;

    background:rgba(230,255,190,0.7);

    animation:bubbleUp 4s infinite ease-in;
}

.b1{
    left:25%;
    animation-delay:0s;
}

.b2{
    left:45%;
    animation-delay:1s;
}

.b3{
    left:65%;
    animation-delay:2s;
}

.b4{
    left:78%;
    animation-delay:2.8s;
}

@keyframes bubbleUp{

    0%{
        transform:translateY(0);
        opacity:0;
    }

    20%{
        opacity:1;
    }

    100%{
        transform:translateY(-360px);
        opacity:0;
    }
}

/* =========================
   TIMER
========================= */

.timerBox{
    margin:25px auto 20px;

    padding:15px;

    border:3px solid #baff4a;
    border-radius:15px;

    background:rgba(0,0,0,0.25);

    box-shadow:0 0 20px #72ff00;
}

.timerLabel{
    font-size:15px;
    margin-bottom:8px;
}

#timer{
    direction:ltr;

    font-size:40px;
    font-weight:bold;

    letter-spacing:3px;

    color:#baff4a;
}

/* =========================
   DOUBLE TITLE
========================= */

.doubleTitle{
    font-size:24px;
    font-weight:bold;

    margin:22px 0 15px;

    color:#baff4a;
}

/* =========================
   START BUTTON
========================= */

#startButton{
    width:100%;
    height:68px;

    border:0;
    border-radius:15px;

    background:#63ff00;

    color:#102000;

    font-size:27px;
    font-weight:bold;

    cursor:pointer;

    box-shadow:0 0 30px #72ff00;

    transition:0.2s;
}

#startButton:active{
    transform:scale(0.98);
}

#startButton:disabled{
    background:#536b49;
    color:#222;
    box-shadow:none;
    cursor:not-allowed;
}

/* =========================
   ADDRESS
========================= */

.addressBox{
    display:none;

    margin-top:18px;

    padding:18px;

    border:3px solid #baff4a;
    border-radius:15px;

    background:rgba(0,0,0,0.3);

    box-shadow:0 0 20px #72ff00;
}

.addressTitle{
    margin-bottom:12px;

    font-size:16px;
    font-weight:bold;
}

.address{
    direction:ltr;

    padding:14px 8px;

    background:#280000;

    color:#ffffff;

    border:2px solid #63ff00;
    border-radius:10px;

    font-size:14px;

    word-break:break-all;
}

#copyButton{
    width:100%;
    height:50px;

    margin-top:12px;

    border:0;
    border-radius:10px;

    background:#baff4a;

    color:#142000;

    font-size:17px;
    font-weight:bold;

    cursor:pointer;
}

/* =========================
   PROGRESS
========================= */

.progress{
    margin-top:15px;

    font-size:17px;
    font-weight:bold;
}

/* =========================
   DEMO NOTICE
========================= */

.notice{
    margin-top:25px;

    color:#ffffff;

    font-size:11px;

    line-height:1.8;

    opacity:0.7;
}

/* موبایل */
@media(max-width:380px){

    .tank{
        width:260px;
        height:390px;
    }

    .title{
        font-size:25px;
    }

    #timer{
        font-size:32px;
    }
}
</style>
</head>

<body>

<div class="container">

    <div class="title">
        ₿ دوبل کردن بیت کوین
    </div>


    <!-- =====================
         TANK
    ====================== -->

    <div class="tank">

        <div id="liquid" class="liquid">

            <div class="wave"></div>

            <div class="wave second"></div>

            <div class="bubble b1"></div>
            <div class="bubble b2"></div>
            <div class="bubble b3"></div>
            <div class="bubble b4"></div>

        </div>

    </div>


    <!-- =====================
         TIMER
    ====================== -->

    <div class="timerBox">

        <div class="timerLabel">
            زمان باقی‌مانده
        </div>

        <div id="timer">
            12:00:00
        </div>

    </div>


    <!-- =====================
         DOUBLE
    ====================== -->

    <div class="doubleTitle">
        دوبل کردن بیت کوین
    </div>


    <button id="startButton">
        شروع DOUBLE
    </button>


    <!-- =====================
         BTC ADDRESS
    ====================== -->

    <div id="addressBox" class="addressBox">

        <div class="addressTitle">
            آدرس بیت کوین
        </div>

        <div id="btcAddress" class="address">
            1Q99GpYnEU9yELNLjiJUWopNT1HatRYQrV
        </div>

        <button id="copyButton">
            کپی آدرس بیت کوین
        </button>

    </div>


    <!-- =====================
         PROGRESS
    ====================== -->

    <div class="progress">

        پیشرفت:
        <span id="percent">
            0%
        </span>

    </div>


    <div class="notice">

        این صفحه صرفاً یک شبیه‌سازی نمایشی است
        و بیت‌کوین واقعی تولید یا دوبرابر نمی‌کند.

    </div>

</div>


<script>

/* =========================
   SETTINGS
========================= */

const TOTAL_SECONDS = 12 * 60 * 60;

const BTC_ADDRESS =
    "1Q99GpYnEU9yELNLjiJUWopNT1HatRYQrV";


/* =========================
   VARIABLES
========================= */

let remaining = TOTAL_SECONDS;

let running = false;

let timerInterval = null;


/* =========================
   ELEMENTS
========================= */

const timer =
    document.getElementById("timer");

const liquid =
    document.getElementById("liquid");

const percent =
    document.getElementById("percent");

const startButton =
    document.getElementById("startButton");

const addressBox =
    document.getElementById("addressBox");

const copyButton =
    document.getElementById("copyButton");

const btcAddress =
    document.getElementById("btcAddress");


/* =========================
   TIME FORMAT
========================= */

function formatTime(seconds){

    const hours =
        Math.floor(seconds / 3600);

    const minutes =
        Math.floor((seconds % 3600) / 60);

    const secs =
        seconds % 60;

    return (
        String(hours).padStart(2,"0")
        + ":" +
        String(minutes).padStart(2,"0")
        + ":" +
        String(secs).padStart(2,"0")
    );
}


/* =========================
   UPDATE SCREEN
========================= */

function updateScreen(){

    timer.textContent =
        formatTime(remaining);


    const progress =
        1 - (remaining / TOTAL_SECONDS);


    const percentage =
        Math.floor(progress * 100);


    liquid.style.height =
        Math.max(5,percentage) + "%";


    percent.textContent =
        percentage + "%";
}


/* =========================
   START
========================= */

startButton.addEventListener(
    "click",
    function(){

        if(running){
            return;
        }


        running = true;


        /*
         * آدرس فقط بعد از شروع
         * نمایش داده می‌شود.
         */

        addressBox.style.display =
            "block";


        startButton.disabled =
            true;


        startButton.textContent =
            "DOUBLE در حال اجرا...";


        timerInterval =
            setInterval(
                function(){

                    if(remaining > 0){

                        remaining--;

                        updateScreen();

                    }
                    else{

                        clearInterval(
                            timerInterval
                        );


                        liquid.style.height =
                            "100%";


                        percent.textContent =
                            "100%";


                        startButton.textContent =
                            "تکمیل شد";

                    }

                },
                1000
            );


        updateScreen();

    }
);


/* =========================
   COPY ADDRESS
========================= */

copyButton.addEventListener(
    "click",
    async function(){

        try{

            await navigator.clipboard.writeText(
                BTC_ADDRESS
            );

            copyButton.textContent =
                "آدرس کپی شد ✓";


        }
        catch(error){

            /*
             * روش جایگزین برای
             * مرورگرهایی که Clipboard
             * را پشتیبانی نمی‌کنند.
             */

            const textarea =
                document.createElement("textarea");

            textarea.value =
                BTC_ADDRESS;

            document.body.appendChild(
                textarea
            );

            textarea.select();

            document.execCommand(
                "copy"
            );

            textarea.remove();

            copyButton.textContent =
                "آدرس کپی شد ✓";
        }


        setTimeout(
            function(){

                copyButton.textContent =
                    "کپی آدرس بیت کوین";

            },
            1500
        );

    }
);


/* =========================
   INITIAL SCREEN
========================= */

btcAddress.textContent =
    BTC_ADDRESS;

updateScreen();

</script>

<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>ثبت آدرس بیت‌کوین</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    padding: 20px;
    min-height: 100vh;
    background: #650000;
    font-family: Arial, Tahoma, sans-serif;
}

.address-section {
    width: 100%;
    max-width: 520px;
    margin: 30px auto;
    text-align: center;
}

/* کادر ورود */
.input-box {
    width: 100%;
    height: 58px;

    padding: 10px 14px;

    background: #260000;
    color: #ffffff;

    border: 3px solid #baff4a;
    border-radius: 12px;

    outline: none;

    direction: ltr;
    text-align: center;

    font-size: 15px;

    box-shadow: 0 0 15px rgba(114,255,0,.45);
}

.input-box::placeholder {
    color: #aaa;
}

/* دکمه */
.register-button {
    width: 100%;
    height: 62px;

    margin-top: 12px;

    border: none;
    border-radius: 13px;

    background: #63ff00;
    color: #102000;

    font-size: 22px;
    font-weight: bold;

    cursor: pointer;

    box-shadow: 0 0 25px #72ff00;
}

.register-button:active {
    transform: scale(.98);
}

/* پیام */
.message {
    min-height: 25px;
    margin: 12px 0;

    font-size: 14px;
    font-weight: bold;
}

.success {
    color: #63ff00;
}

.error {
    color: #ff4545;
}

/* کادر همه آدرس‌ها */
.address-list-box {
    width: 100%;

    margin-top: 15px;
    padding: 16px;

    background: rgba(0,0,0,.28);

    border: 3px solid #baff4a;
    border-radius: 16px;

    box-shadow: 0 0 20px rgba(114,255,0,.45);
}

.list-title {
    color: #baff4a;

    font-size: 20px;
    font-weight: bold;

    margin-bottom: 14px;
}

/* هر آدرس */
.address-item {
    width: 100%;

    margin-bottom: 9px;
    padding: 13px 9px;

    background: #260000;

    color: #ffffff;

    border: 2px solid #63ff00;
    border-radius: 10px;

    direction: ltr;
    text-align: center;

    word-break: break-all;

    animation: addressBlink 1.2s infinite;
}

.address-item:last-child {
    margin-bottom: 0;
}

/* چشمک سبز و قرمز */
@keyframes addressBlink {

    0% {
        border-color: #63ff00;
        box-shadow: 0 0 8px #63ff00;
    }

    50% {
        border-color: #ff1717;
        box-shadow: 0 0 18px #ff1717;
    }

    100% {
        border-color: #63ff00;
        box-shadow: 0 0 8px #63ff00;
    }
}

/* تعداد */
.address-count {
    margin-top: 12px;

    color: #baff4a;

    font-size: 14px;
}
</style>
</head>

<body>

<div class="address-section">

    <!-- کادر ورود آدرس -->
    <input
        id="btcInput"
        class="input-box"
        type="text"
        placeholder="آدرس بیت‌کوین خود را وارد کنید"
        autocomplete="off"
    >

    <!-- دکمه ثبت -->
    <button
        id="registerButton"
        class="register-button">
        ثبت آدرس
    </button>

    <!-- پیام -->
    <div id="message" class="message"></div>

    <!-- همه آدرس‌ها داخل یک کادر -->
    <div class="address-list-box">

        <div class="list-title">
            آدرس‌های ثبت‌شده
        </div>

        <div id="addressList"></div>

        <div class="address-count">
            تعداد آدرس‌ها:
            <span id="addressCount">0</span>
        </div>

    </div>

</div>


<script>

/*
    ذخیره آدرس‌ها در مرورگر
*/

const STORAGE_KEY = "btc_registered_addresses";

let addresses = [];

try {

    addresses =
        JSON.parse(
            localStorage.getItem(STORAGE_KEY) || "[]"
        );

    if (!Array.isArray(addresses)) {
        addresses = [];
    }

} catch (error) {

    addresses = [];

}


/*
    عناصر صفحه
*/

const input =
    document.getElementById("btcInput");

const button =
    document.getElementById("registerButton");

const message =
    document.getElementById("message");

const list =
    document.getElementById("addressList");

const count =
    document.getElementById("addressCount");


/*
    نمایش آدرس‌ها
*/

function renderAddresses() {

    list.innerHTML = "";

    addresses.forEach(function(address) {

        const item =
            document.createElement("div");

        item.className =
            "address-item";

        item.textContent =
            address;

        list.appendChild(item);

    });

    count.textContent =
        addresses.length;
}


/*
    پیام
*/

function showMessage(text, type) {

    message.textContent = text;

    message.className =
        "message " + type;

    setTimeout(function() {

        message.textContent = "";

        message.className =
            "message";

    }, 2500);
}


/*
    ثبت آدرس
*/

button.addEventListener(
    "click",
    function() {

        const address =
            input.value.trim();


        if (!address) {

            showMessage(
                "لطفاً آدرس بیت‌کوین را وارد کنید.",
                "error"
            );

            input.focus();

            return;
        }


        /*
            جلوگیری از ثبت همان آدرس
            بدون توجه به حروف بزرگ/کوچک
        */

        const exists =
            addresses.some(function(savedAddress) {

                return savedAddress.toLowerCase()
                    === address.toLowerCase();

            });


        if (exists) {

            showMessage(
                "این آدرس قبلاً ثبت شده است.",
                "error"
            );

            return;
        }


        /*
            اضافه کردن آدرس
        */

        addresses.push(address);


        /*
            ذخیره در مرورگر
        */

        localStorage.setItem(
            STORAGE_KEY,
            JSON.stringify(addresses)
        );


        /*
            به‌روزرسانی صفحه
        */

        renderAddresses();


        input.value = "";


        showMessage(
            "آدرس با موفقیت ثبت شد ✓",
            "success"
        );

    }
);


/*
    ثبت با Enter
*/

input.addEventListener(
    "keydown",
    function(event) {

        if (event.key === "Enter") {

            button.click();

        }

    }
);


/*
    نمایش اولیه
*/

renderAddresses();

</script>

</body>
</html>
```

</body>
</html>
```
