<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Our Love Story ❤️</title>

<style>

/* =========================
   GENERAL
========================= */

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    overflow: hidden;
    font-family: Arial, sans-serif;
    background: #16051f;
}

.screen {
    position: fixed;
    inset: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

/* =========================
   START SCREEN
========================= */

#startScreen {
    background:
        radial-gradient(circle, #5a174e, #16051f 70%);
    color: white;
    transition: 1s;
}

.start-title {
    font-size: 30px;
    text-align: center;
    margin-bottom: 40px;
    text-shadow: 0 0 20px #ff416c;
}

.broken-heart {
    font-size: 120px;
    cursor: pointer;
    user-select: none;
    animation: heartbeat 1.2s infinite;
    filter: drop-shadow(0 0 25px #ff416c);
}

.click-text {
    margin-top: 30px;
    color: #ffc7d7;
    animation: blink 1.5s infinite;
}

/* =========================
   LOVE SCENE
========================= */

#loveScene {
    display: none;

    background:
        linear-gradient(
            to bottom,
            #24104a 0%,
            #74315e 40%,
            #ed765f 70%,
            #ffb45d 100%
        );

    overflow: hidden;
}

/* Sun */

.sun {
    position: absolute;
    width: 150px;
    height: 150px;
    border-radius: 50%;

    left: 50%;
    top: 32%;

    transform: translate(-50%, -50%);

    background: #ffe99b;

    box-shadow:
        0 0 40px #ffd86b,
        0 0 100px #ff8555;
}

/* Mountains */

.mountain {
    position: absolute;

    bottom: 25%;

    width: 0;
    height: 0;

    border-left: 240px solid transparent;
    border-right: 240px solid transparent;
    border-bottom: 300px solid #25152e;
}

.mountain.left {
    left: -160px;
}

.mountain.right {
    right: -160px;
}

/* Ground */

.ground {
    position: absolute;

    bottom: 21%;

    width: 100%;
    height: 50px;

    background: #15101d;

    border-radius: 50% 50% 0 0;
}

/* =========================
   COUPLE
========================= */

.couple {

    position: absolute;

    width: 300px;
    height: 300px;

    bottom: 21%;
    left: 50%;

    transform: translateX(-50%);
}

.head {
    position: absolute;

    width: 48px;
    height: 48px;

    border-radius: 50%;

    background: #17121c;

    top: 30px;
}

.boy-head {
    left: 70px;
}

.girl-head {
    right: 70px;
}

/* Girl hair */

.girl-head::before {

    content: "";

    position: absolute;

    width: 70px;
    height: 90px;

    background: #0c0910;

    border-radius: 50%;

    left: -11px;
    top: -10px;

    z-index: -1;
}

/* Bodies */

.body {
    position: absolute;

    width: 75px;
    height: 125px;

    top: 75px;

    background: #17121c;

    border-radius: 40px 40px 10px 10px;
}

.boy-body {
    left: 55px;
}

.girl-body {
    right: 55px;
    height: 135px;
}

/* Arms */

.arm {

    position: absolute;

    width: 18px;
    height: 90px;

    top: 85px;

    background: #17121c;

    border-radius: 20px;

    transform-origin: top;
}

.boy-arm {

    left: 105px;

    transform: rotate(-30deg);
}

.girl-arm {

    right: 105px;

    transform: rotate(30deg);
}

/* Legs */

.leg {

    position: absolute;

    width: 22px;
    height: 85px;

    top: 190px;

    background: #17121c;

    border-radius: 20px;
}

.boy-leg1 {
    left: 70px;
    transform: rotate(7deg);
}

.boy-leg2 {
    left: 105px;
    transform: rotate(-7deg);
}

.girl-leg1 {
    right: 70px;
    transform: rotate(-7deg);
}

.girl-leg2 {
    right: 105px;
    transform: rotate(7deg);
}

/* Couple animation */

.fun {

    animation:
        coupleDance 2s ease-in-out infinite;
}

@keyframes coupleDance {

    0%,100% {
        transform:
            translateX(-50%)
            rotate(0deg);
    }

    50% {
        transform:
            translateX(-50%)
            translateY(-10px)
            rotate(3deg);
    }
}

/* =========================
   HEARTS
========================= */

.heart {

    position: absolute;

    color: #ff416c;

    pointer-events: none;

    animation:
        floatHeart 5s linear forwards;
}

@keyframes floatHeart {

    0% {
        opacity: 0;
        transform:
            translateY(0)
            scale(.5);
    }

    20% {
        opacity: 1;
    }

    100% {
        opacity: 0;

        transform:
            translateY(-500px)
            scale(1.5);
    }
}

/* =========================
   QUESTION LAYERS
========================= */

.questionLayer {

    position: absolute;

    inset: 0;

    display: none;

    justify-content: center;
    align-items: center;

    flex-direction: column;

    background:
        rgba(30,5,30,.25);

    z-index: 50;

    text-align: center;

    color: white;
}

.questionLayer.active {
    display: flex;
}

.questionNumber {

    font-size: 16px;

    color: #ffc0d0;

    margin-bottom: 15px;

    letter-spacing: 2px;
}

.question {

    font-size: 30px;

    max-width: 700px;

    padding: 20px;

    text-shadow:
        0 0 15px #ff416c;

    animation:
        questionAppear .8s ease;
}

@keyframes questionAppear {

    from {
        opacity: 0;
        transform: scale(.7);
    }

    to {
        opacity: 1;
        transform: scale(1);
    }
}

/* Buttons */

.buttons {

    display: flex;

    gap: 25px;

    margin-top: 30px;
}

button {

    border: none;

    padding: 15px 35px;

    border-radius: 30px;

    font-size: 20px;

    cursor: pointer;

    transition: .25s;
}

.yes {

    background: #ff416c;

    color: white;

    box-shadow:
        0 0 20px #ff416c;
}

.yes:hover {

    transform: scale(1.15);
}

.no {

    background: white;

    color: #ff416c;

    position: relative;

    transition: none;
}

/* =========================
   FINAL
========================= */

#finalScreen {

    display: none;

    background:
        radial-gradient(
            circle,
            #a93663,
            #21071f
        );

    color: white;

    text-align: center;

    z-index: 200;
}

.finalHeart {

    font-size: 110px;

    animation:
        heartbeat 1s infinite;
}

#finalScreen h1 {

    font-size: 50px;

    color: #ffb7cb;

    text-shadow:
        0 0 30px #ff416c;
}

#finalScreen p {

    margin-top: 20px;

    font-size: 21px;
}

/* =========================
   ANIMATIONS
========================= */

@keyframes heartbeat {

    0%,100% {
        transform: scale(1);
    }

    50% {
        transform: scale(1.15);
    }
}

@keyframes blink {

    50% {
        opacity: .4;
    }
}

</style>
</head>


<body>


<!-- =================================
     START
================================= -->

<div id="startScreen" class="screen">

    <div class="start-title">
        Something special is waiting for you... ❤️
    </div>

    <div
        id="brokenHeart"
        class="broken-heart"
    >
        💔
    </div>

    <div class="click-text">
        Click the broken heart...
    </div>

</div>


<!-- =================================
     LOVE SCENE
================================= -->

<div id="loveScene" class="screen">

    <div class="sun"></div>

    <div class="mountain left"></div>
    <div class="mountain right"></div>

    <div class="ground"></div>


    <!-- Couple -->

    <div id="couple" class="couple">

        <!-- Boy -->

        <div class="head boy-head"></div>

        <div class="body boy-body"></div>

        <div class="arm boy-arm"></div>

        <div class="leg boy-leg1"></div>
        <div class="leg boy-leg2"></div>


        <!-- Girl -->

        <div class="head girl-head"></div>

        <div class="body girl-body"></div>

        <div class="arm girl-arm"></div>

        <div class="leg girl-leg1"></div>
        <div class="leg girl-leg2"></div>

    </div>


    <!-- =================================
         QUESTION 1
    ================================= -->

    <div
        id="q1"
        class="questionLayer"
    >

        <div class="questionNumber">
            QUESTION 1 / 5 ❤️
        </div>

        <div class="question">
            Do you believe two people can meet by destiny? ✨
        </div>

        <div class="buttons">

            <button
                class="yes"
                onclick="nextQuestion(1)"
            >
                YES ❤️
            </button>

            <button
                class="no"
                onmouseenter="escapeNo(this)"
                ontouchstart="escapeNo(this)"
            >
                NO
            </button>

        </div>

    </div>


    <!-- =================================
         QUESTION 2
    ================================= -->

    <div
        id="q2"
        class="questionLayer"
    >

        <div class="questionNumber">
            QUESTION 2 / 5 💕
        </div>

        <div class="question">
            Would you like to turn ordinary days into extraordinary chapters, creating a world of memories that belongs only to us? 🌅
        </div>

        <div class="buttons">

            <button
                class="yes"
                onclick="nextQuestion(2)"
            >
                YES ❤️
            </button>

            <button
                class="no"
                onmouseenter="escapeNo(this)"
                ontouchstart="escapeNo(this)"
            >
                NO
            </button>

        </div>

    </div>


    <!-- =================================
         QUESTION 3
    ================================= -->

    <div
        id="q3"
        class="questionLayer"
    >

        <div class="questionNumber">
            QUESTION 3 / 5 💖
        </div>

        <div class="question">
            When the shadows fall and the world grows cold, will you stay right here and hold my hand through the storm? 🌇
        </div>

        <div class="buttons">

            <button
                class="yes"
                onclick="nextQuestion(3)"
            >
                YES ❤️
            </button>

            <button
                class="no"
                onmouseenter="escapeNo(this)"
                ontouchstart="escapeNo(this)"
            >
                NO
            </button>

        </div>

    </div>


    <!-- =================================
         QUESTION 4
    ================================= -->

    <div
        id="q4"
        class="questionLayer"
    >

        <div class="questionNumber">
            QUESTION 4 / 5 💗
        </div>

        <div class="question">
            will you let me be the reason behind your daily smile? 😊
        </div>

        <div class="buttons">

            <button
                class="yes"
                onclick="nextQuestion(4)"
            >
                YES ❤️
            </button>

            <button
                class="no"
                onmouseenter="escapeNo(this)"
                ontouchstart="escapeNo(this)"
            >
                NO
            </button>

        </div>

    </div>


    <!-- =================================
         QUESTION 5
    ================================= -->

    <div
        id="q5"
        class="questionLayer"
    >

        <div class="questionNumber">
            FINAL QUESTION / 5 💍
        </div>

        <div class="question">
            Will you be mine and start this beautiful journey with me? ❤️
        </div>

        <div class="buttons">

            <button
                class="yes"
                onclick="finalAnswer()"
            >
                YES 💍
            </button>

            <button
                class="no"
                onmouseenter="escapeNo(this)"
                ontouchstart="escapeNo(this)"
            >
                NO
            </button>

        </div>

    </div>

</div>


<!-- =================================
     FINAL SCREEN
================================= -->

<div id="finalScreen" class="screen">

    <div class="finalHeart">
        ❤️
    </div>

    <h1>
        THIS IS WHERE OUR STORI BEGINS ! 💍🥰
    </h1>

    <p>
        From this moment... it's you and me. Forever. ♾️❤️🥹🥰
    </p>

    <p>
        Forever & Always ❤️
    </p>

</div>


<script>

/* =================================
   START → HEART
================================= */

const brokenHeart =
    document.getElementById("brokenHeart");

const startScreen =
    document.getElementById("startScreen");

const loveScene =
    document.getElementById("loveScene");

const couple =
    document.getElementById("couple");


brokenHeart.onclick = function() {

    brokenHeart.innerHTML = "❤️";

    brokenHeart.style.transform =
        "scale(1.5)";

    setTimeout(() => {

        startScreen.style.opacity = "0";

        setTimeout(() => {

            startScreen.style.display =
                "none";

            loveScene.style.display =
                "flex";

            couple.classList.add("fun");

            createHearts();

            // Start Question 1
            setTimeout(() => {

                document
                    .getElementById("q1")
                    .classList.add("active");

            }, 4000);

        }, 800);

    }, 500);

};


/* =================================
   NEXT QUESTION
================================= */

function nextQuestion(current) {

    // Hide current question

    document
        .getElementById("q" + current)
        .classList.remove("active");


    // Next question

    const next = current + 1;

    setTimeout(() => {

        document
            .getElementById("q" + next)
            .classList.add("active");

    }, 600);

}


/* =================================
   NO BUTTON ESCAPE
================================= */

function escapeNo(button) {

    const parent =
        button.parentElement;

    const parentRect =
        parent.getBoundingClientRect();


    // Random movement

    const maxX = 120;
    const maxY = 80;

    const x =
        (Math.random() * maxX * 2)
        - maxX;

    const y =
        (Math.random() * maxY * 2)
        - maxY;


    button.style.transform =
        `translate(${x}px, ${y}px)`;

}


/* Also stop clicks */

document.addEventListener(
    "click",
    function(event) {

        if (
            event.target.classList
                .contains("no")
        ) {

            event.preventDefault();

            escapeNo(event.target);

        }

    },
    true
);


/* =================================
   FLOATING HEARTS
================================= */

function createHearts() {

    setInterval(() => {

        if (
            loveScene.style.display ===
            "flex"
        ) {

            const heart =
                document.createElement("div");

            heart.className =
                "heart";

            heart.innerHTML =
                "❤️";

            heart.style.left =
                (35 + Math.random() * 30)
                + "%";

            heart.style.bottom =
                (20 + Math.random() * 10)
                + "%";

            heart.style.fontSize =
                (15 + Math.random() * 25)
                + "px";

            heart.style.animationDuration =
                (3 + Math.random() * 3)
                + "s";


            loveScene.appendChild(heart);


            setTimeout(() => {

                heart.remove();

            }, 6000);

        }

    }, 700);

}


/* =================================
   FINAL ANSWER
================================= */

function finalAnswer() {

    loveScene.style.display =
        "none";

    document
        .getElementById("finalScreen")
        .style.display =
        "flex";


    // Celebration hearts

    for (
        let i = 0;
        i < 50;
        i++
    ) {

        setTimeout(() => {

            const heart =
                document.createElement("div");

            heart.innerHTML =
                "❤️";

            heart.style.position =
                "fixed";

            heart.style.left =
                Math.random() * 100 + "%";

            heart.style.top =
                Math.random() * 100 + "%";

            heart.style.fontSize =
                (20 + Math.random() * 40)
                + "px";

            heart.style.zIndex =
                "300";

            heart.style.animation =
                "heartbeat .8s infinite";


            document
                .getElementById("finalScreen")
                .appendChild(heart);

        }, i * 70);

    }

}

</script>

</body>
</html>
