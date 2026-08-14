<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Неллі — фотограф у Празі</title>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">


<style>

/* =========================================================
   ОСНОВА
========================================================= */

:root {
    --темний: #0d0d0c;
    --темний2: #151513;
    --світлий: #f1ede6;
    --світлий2: #e4ddd2;
    --золотий: #b79b7a;
    --сірий: #888178;

    --шрифт-заголовків: "Cormorant Garamond", serif;
    --шрифт-тексту: "DM Sans", sans-serif;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    background: var(--темний);
    color: var(--світлий);
    font-family: var(--шрифт-тексту);
    font-weight: 300;
    overflow-x: hidden;
}

a {
    color: inherit;
    text-decoration: none;
}

button {
    font-family: inherit;
}


/* =========================================================
   ЗЕРНИСТІСТЬ
========================================================= */

body::after {
    content: "";

    position: fixed;
    inset: 0;

    pointer-events: none;

    z-index: 9999;

    opacity: .035;

    background-image:
        url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.8' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='.8'/%3E%3C/svg%3E");
}


/* =========================================================
   КУРСОР
========================================================= */

.cursor {
    position: fixed;

    width: 9px;
    height: 9px;

    border: 1px solid rgba(255,255,255,.8);

    border-radius: 50%;

    pointer-events: none;

    z-index: 99999;

    transform: translate(-50%, -50%);

    transition:
        width .35s ease,
        height .35s ease,
        background .35s ease;
}

.cursor.active {
    width: 55px;
    height: 55px;

    background: rgba(255,255,255,.08);
}


/* =========================================================
   НАВІГАЦІЯ
========================================================= */

.nav {
    position: fixed;

    top: 0;
    left: 0;

    width: 100%;
    height: 82px;

    padding: 0 5vw;

    display: flex;
    align-items: center;
    justify-content: space-between;

    z-index: 1000;

    background:
        linear-gradient(
            to bottom,
            rgba(13,13,12,.9),
            transparent
        );

    backdrop-filter: blur(8px);
}

.nav-logo {
    font-family: var(--шрифт-заголовків);

    font-size: 26px;

    letter-spacing: -.04em;
}

.nav-logo span {
    font-style: italic;
}

.nav-links {
    display: flex;

    gap: 34px;

    font-size: 10px;

    text-transform: uppercase;

    letter-spacing: .14em;
}

.nav-links a {
    color: #aaa49b;

    transition: .3s;
}

.nav-links a:hover {
    color: white;
}

.nav-button {
    padding: 11px 18px;

    border: 1px solid rgba(255,255,255,.25);

    border-radius: 100px;

    font-size: 9px;

    text-transform: uppercase;

    letter-spacing: .12em;

    transition: .35s;
}

.nav-button:hover {
    background: white;
    color: #111;
}


/* =========================================================
   ПЕРШИЙ ЕКРАН
========================================================= */

.hero {
    min-height: 100vh;

    position: relative;

    display: flex;

    align-items: center;
    justify-content: center;

    overflow: hidden;

    text-align: center;

    background:
        radial-gradient(
            ellipse at center,
            #403a32 0%,
            #211f1b 32%,
            #0d0d0c 75%
        );
}

.hero-light {
    position: absolute;

    width: 70vw;
    height: 70vw;

    max-width: 900px;
    max-height: 900px;

    border-radius: 50%;

    background:
        radial-gradient(
            circle,
            rgba(190,160,125,.18),
            transparent 65%
        );

    filter: blur(35px);

    transition: transform 1s ease;
}

.hero-ring {
    position: absolute;

    width: 55vw;
    height: 55vw;

    max-width: 750px;
    max-height: 750px;

    border: 1px solid rgba(255,255,255,.06);

    border-radius: 50%;

    animation:
        obrut-kola 35s linear infinite;
}

.hero-ring::before {
    content: "";

    position: absolute;

    inset: 12%;

    border: 1px solid rgba(255,255,255,.035);

    border-radius: 50%;
}

@keyframes obrut-kola {
    from {
        transform: rotate(0deg);
    }

    to {
        transform: rotate(360deg);
    }
}

.hero-content {
    position: relative;

    z-index: 5;

    width: 100%;

    padding: 120px 20px 100px;
}


/* =========================================================
   ЛОГОТИП
========================================================= */

.hero-logo {
    width: min(520px, 80vw);

    margin: 0 auto 38px;

    opacity: 0;

    transform:
        translateY(35px)
        scale(.93);

    animation:
        поява-логотипу 1.5s
        .1s
        cubic-bezier(.2,.8,.2,1)
        forwards;
}

.hero-logo img {
    display: block;

    width: 100%;
    height: auto;

    mix-blend-mode: screen;

    filter:
        drop-shadow(
            0 25px 55px
            rgba(0,0,0,.45)
        );

    transition:
        transform 1s ease,
        filter 1s ease;
}

.hero-logo:hover img {
    transform: scale(1.025);

    filter:
        drop-shadow(
            0 30px 65px
            rgba(190,155,115,.22)
        );
}

@keyframes поява-логотипу {

    0% {
        opacity: 0;

        transform:
            translateY(45px)
            scale(.9);

        filter: blur(12px);
    }

    65% {
        opacity: 1;

        filter: blur(0);
    }

    100% {
        opacity: 1;

        transform:
            translateY(0)
            scale(1);
    }
}


/* =========================================================
   ТЕКСТ ПЕРШОГО ЕКРАНУ
========================================================= */

.hero-caption {
    opacity: 0;

    animation:
        поява 1s
        .9s
        forwards;
}

@keyframes поява {
    to {
        opacity: 1;
    }
}

.hero-small {
    color: var(--золотий);

    font-size: 9px;

    text-transform: uppercase;

    letter-spacing: .28em;

    margin-bottom: 18px;
}

.hero-title {
    font-family: var(--шрифт-заголовків);

    font-weight: 300;

    font-size: clamp(42px, 6vw, 75px);

    line-height: .9;

    letter-spacing: -.05em;
}

.hero-title em {
    font-style: italic;
}

.hero-description {
    max-width: 550px;

    margin: 25px auto 0;

    color: #aaa49b;

    font-size: 14px;

    line-height: 1.7;
}

.hero-button {
    display: inline-flex;

    align-items: center;

    gap: 14px;

    margin-top: 30px;

    padding: 14px 21px;

    border: 1px solid rgba(255,255,255,.25);

    border-radius: 100px;

    font-size: 9px;

    text-transform: uppercase;

    letter-spacing: .15em;

    transition: .4s;
}

.hero-button:hover {
    background: white;

    color: #111;

    padding-left: 27px;
    padding-right: 27px;
}

.hero-button span {
    font-size: 16px;
}


/* =========================================================
   ПРОКРУТКА
========================================================= */

.hero-scroll {
    position: absolute;

    bottom: 25px;
    left: 50%;

    transform: translateX(-50%);

    display: flex;

    flex-direction: column;

    align-items: center;

    gap: 9px;

    color: #66615a;

    font-size: 8px;

    text-transform: uppercase;

    letter-spacing: .25em;
}

.scroll-line {
    width: 1px;
    height: 45px;

    background:
        linear-gradient(
            to bottom,
            #777,
            transparent
        );

    animation:
        рух-скролу 2s infinite;
}

@keyframes рух-скролу {

    0% {
        opacity: 0;

        transform:
            scaleY(0);

        transform-origin: top;
    }

    50% {
        opacity: 1;

        transform:
            scaleY(1);
    }

    100% {
        opacity: 0;

        transform:
            scaleY(1);

        transform-origin: bottom;
    }
}


/* =========================================================
   ВСТУП
========================================================= */

.intro {
    min-height: 75vh;

    padding: 130px 7vw;

    display: grid;

    grid-template-columns: .6fr 1.4fr;

    gap: 10vw;

    align-items: center;

    background: var(--світлий);

    color: #171614;
}

.номер-секції {
    font-size: 9px;

    text-transform: uppercase;

    letter-spacing: .22em;

    color: #817a70;
}

.intro-title {
    font-family: var(--шрифт-заголовків);

    font-weight: 300;

    font-size: clamp(50px, 6vw, 85px);

    line-height: .88;

    letter-spacing: -.055em;
}

.intro-title em {
    font-style: italic;
}

.intro-text {
    max-width: 650px;

    margin-top: 35px;

    font-size: 17px;

    line-height: 1.85;

    color: #676159;
}


/* =========================================================
   ВИБІР ФОТОСЕСІЇ
========================================================= */

.choose {
    padding: 145px 5vw;

    background: var(--темний2);
}

.choose-header {
    max-width: 900px;

    margin-bottom: 75px;
}

.choose-title {
    margin-top: 18px;

    font-family: var(--шрифт-заголовків);

    font-weight: 300;

    font-size: clamp(55px, 8vw, 105px);

    line-height: .82;

    letter-spacing: -.065em;
}

.choose-title em {
    font-style: italic;
}

.choose-subtitle {
    max-width: 570px;

    margin-top: 35px;

    color: #858077;

    font-size: 14px;

    line-height: 1.8;
}


/* =========================================================
   КАРТКИ
========================================================= */

.session-grid {
    display: grid;

    grid-template-columns:
        repeat(4, 1fr);

    gap: 10px;
}

.session {
    min-height: 330px;

    position: relative;

    padding: 24px;

    overflow: hidden;

    border: 1px solid #33312d;

    background:
        linear-gradient(
            145deg,
            #25241f,
            #1a1917
        );

    cursor: pointer;

    transition:
        transform .7s
        cubic-bezier(.2,.8,.2,1),
        border-color .5s,
        background .7s;
}

.session:hover {
    transform: translateY(-12px);

    border-color: #817665;

    background:
        linear-gradient(
            145deg,
            #302c25,
            #1b1a18
        );
}

.session.selected {
    border-color: var(--золотий);

    box-shadow:
        0 20px 50px
        rgba(0,0,0,.25);
}

.session::after {
    content: "";

    position: absolute;

    width: 220px;
    height: 220px;

    right: -90px;
    bottom: -100px;

    border-radius: 50%;

    background:
        radial-gradient(
            circle,
            rgba(190,155,115,.28),
            transparent 65%
        );

    filter: blur(20px);

    opacity: 0;

    transition: .7s;
}

.session:hover::after {
    opacity: 1;
}

.session-number {
    font-size: 9px;

    color: #66615a;

    letter-spacing: .15em;
}

.session-symbol {
    margin-top: 45px;

    font-family: var(--шрифт-заголовків);

    font-size: 50px;

    color: #aaa399;

    transition: .5s;
}

.session:hover .session-symbol {
    color: #ded4c7;

    transform:
        translateX(7px)
        rotate(-3deg);
}

.session h3 {
    position: absolute;

    left: 24px;
    right: 20px;
    bottom: 52px;

    font-family: var(--шрифт-заголовків);

    font-size: 29px;

    font-weight: 300;

    line-height: 1;
}

.session small {
    position: absolute;

    left: 24px;
    bottom: 23px;

    color: #69645c;

    font-size: 8px;

    text-transform: uppercase;

    letter-spacing: .12em;
}


/* =========================================================
   ОБРАНА ЗЙОМКА
========================================================= */

.selected-box {
    margin-top: 60px;

    padding: 25px 0;

    border-top: 1px solid #33312d;

    border-bottom: 1px solid #33312d;

    display: flex;

    justify-content: space-between;

    align-items: center;
}

.selected-label {
    color: #6e6961;

    font-size: 8px;

    text-transform: uppercase;

    letter-spacing: .18em;
}

.selected-name {
    margin-top: 5px;

    font-family: var(--шрифт-заголовків);

    font-size: 27px;

    font-style: italic;

    color: #eee9e1;

    transition: opacity .2s;
}

.selected-button {
    padding: 13px 20px;

    background: var(--світлий);

    color: #111;

    border-radius: 100px;

    font-size: 9px;

    text-transform: uppercase;

    letter-spacing: .13em;

    transition: .3s;
}

.selected-button:hover {
    transform: translateX(7px);
}


/* =========================================================
   РУХОМИЙ РЯДОК
========================================================= */

.marquee {
    overflow: hidden;

    padding: 25px 0;

    background: #b69b7d;

    color: #171614;

    white-space: nowrap;
}

.marquee-track {
    display: inline-flex;

    gap: 35px;

    animation:
        біг-рядка 27s
        linear
        infinite;
}

.marquee span {
    font-family: var(--шрифт-заголовків);

    font-size: 29px;

    font-style: italic;
}

.marquee-dot {
    font-family: var(--шрифт-тексту);

    font-style: normal;

    opacity: .5;
}

@keyframes біг-рядка {

    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(-50%);
    }
}


/* =========================================================
   ПОРТФОЛІО
========================================================= */

.portfolio {
    padding: 145px 5vw;

    background: var(--світлий);

    color: #171614;
}

.portfolio-head {
    display: flex;

    justify-content: space-between;

    align-items: end;

    gap: 40px;

    margin-bottom: 65px;
}

.portfolio-title {
    margin-top: 18px;

    font-family: var(--шрифт-заголовків);

    font-size: clamp(55px, 7vw, 100px);

    line-height: .82;

    font-weight: 300;

    letter-spacing: -.065em;
}

.portfolio-title em {
    font-style: italic;
}

.portfolio-description {
    max-width: 310px;

    color: #777169;

    font-size: 12px;

    line-height: 1.7;
}


/* =========================================================
   МІСЦЯ ДЛЯ ФОТО
========================================================= */

.gallery {
    display: grid;

    grid-template-columns:
        repeat(12, 1fr);

    grid-auto-rows: 90px;

    gap: 12px;
}

.gallery-item {
    position: relative;

    overflow: hidden;

    display: flex;

    align-items: center;
    justify-content: center;

    font-family: var(--шрифт-заголовків);

    font-size: 36px;

    font-style: italic;

    color: rgba(255,255,255,.65);

    background:
        linear-gradient(
            135deg,
            #c8c0b4,
            #928a7e
        );

    transition:
        transform .8s
        cubic-bezier(.2,.8,.2,1);
}

.gallery-item:hover {
    transform: scale(.985);
}

.gallery-item::before {
    content: "";

    position: absolute;

    inset: 0;

    background:
        linear-gradient(
            115deg,
            transparent 25%,
            rgba(255,255,255,.3),
            transparent 75%
        );

    transform: translateX(-120%);

    transition: .9s;
}

.gallery-item:hover::before {
    transform: translateX(120%);
}

.gallery-item:nth-child(1) {
    grid-column: span 7;
    grid-row: span 5;
}

.gallery-item:nth-child(2) {
    grid-column: span 5;
    grid-row: span 3;

    background:
        linear-gradient(
            135deg,
            #afa297,
            #756d64
        );
}

.gallery-item:nth-child(3) {
    grid-column: span 5;
    grid-row: span 4;

    background:
        linear-gradient(
            135deg,
            #d0c8bc,
            #9d9488
        );
}

.gallery-item:nth-child(4) {
    grid-column: span 4;
    grid-row: span 3;

    background:
        linear-gradient(
            135deg,
            #898279,
            #514d47
        );
}

.gallery-item:nth-child(5) {
    grid-column: span 3;
    grid-row: span 3;

    background:
        linear-gradient(
            135deg,
            #c4b19c,
            #856f59
        );
}

.gallery-tag {
    position: absolute;

    left: 14px;
    bottom: 14px;

    padding: 7px 10px;

    background: rgba(15,15,14,.75);

    color: white;

    font-family: var(--шрифт-тексту);

    font-size: 8px;

    font-style: normal;

    text-transform: uppercase;

    letter-spacing: .14em;
}


/* =========================================================
   ПРО НЕЛЛІ
========================================================= */

.about {
    padding: 145px 7vw;

    min-height: 90vh;

    display: grid;

    grid-template-columns: .8fr 1.2fr;

    gap: 10vw;

    align-items: center;

    background: #151513;
}

.about-photo {
    aspect-ratio: 4 / 5;

    position: relative;

    overflow: hidden;

    display: flex;

    align-items: center;
    justify-content: center;

    background:
        radial-gradient(
            circle at 40% 35%,
            #bca991,
            #61594e 45%,
            #282621 85%
        );
}

.about-photo::before {
    content: "";

    position: absolute;

    inset: 20px;

    border: 1px solid rgba(255,255,255,.25);
}

.about-photo span {
    font-family: var(--шрифт-заголовків);

    font-size: 90px;

    font-style: italic;

    color: rgba(255,255,255,.35);
}

.about-title {
    margin-top: 20px;

    font-family: var(--шрифт-заголовків);

    font-size: clamp(55px, 7vw, 105px);

    font-weight: 300;

    line-height: .82;

    letter-spacing: -.07em;
}

.about-title em {
    font-style: italic;
}

.about-text {
    max-width: 600px;

    margin-top: 35px;

    color: #918b82;

    font-size: 16px;

    line-height: 1.85;
}

.quote {
    max-width: 600px;

    margin-top: 55px;

    padding-top: 25px;

    border-top: 1px solid #35332e;

    font-family: var(--шрифт-заголовків);

    font-size: 27px;

    line-height: 1.35;
}


/* =========================================================
   КОНТАКТ
========================================================= */

.contact {
    min-height: 80vh;

    padding: 140px 7vw;

    display: grid;

    grid-template-columns: 1fr 1fr;

    gap: 10vw;

    align-items: center;

    background: #d4bda5;

    color: #181715;
}

.contact-title {
    margin-top: 20px;

    font-family: var(--шрифт-заголовків);

    font-size: clamp(60px, 8vw, 115px);

    font-weight: 300;

    line-height: .8;

    letter-spacing: -.07em;
}

.contact-title em {
    font-style: italic;
}

.contact-text {
    max-width: 500px;

    color: #514a42;

    font-size: 17px;

    line-height: 1.8;
}

.contact-links {
    display: flex;

    flex-wrap: wrap;

    gap: 10px;

    margin-top: 35px;
}

.contact-link {
    padding: 14px 19px;

    border: 1px solid rgba(24,23,21,.3);

    border-radius: 100px;

    font-size: 9px;

    text-transform: uppercase;

    letter-spacing: .13em;

    transition: .35s;
}

.contact-link:hover {
    background: #181715;

    color: white;
}


/* =========================================================
   НИЗ САЙТУ
========================================================= */

.footer {
    padding: 25px 5vw;

    display: flex;

    justify-content: space-between;

    background: #0d0d0c;

    color: #66625c;

    font-size: 8px;

    text-transform: uppercase;

    letter-spacing: .17em;
}


/* =========================================================
   АНІМАЦІЯ ПОЯВИ
========================================================= */

.reveal {
    opacity: 0;

    transform: translateY(45px);

    transition:
        opacity 1s ease,
        transform 1s cubic-bezier(.2,.8,.2,1);
}

.reveal.visible {
    opacity: 1;

    transform: translateY(0);
}


/* =========================================================
   ТЕЛЕФОН
========================================================= */

@media(max-width: 900px) {

    .nav-links {
        display: none;
    }

    .nav-button {
        display: none;
    }

    .hero-logo {
        width: min(450px, 85vw);
    }

    .intro,
    .about,
    .contact {
        grid-template-columns: 1fr;

        gap: 60px;

        padding-top: 100px;
        padding-bottom: 100px;
    }

    .session-grid {
        grid-template-columns:
            repeat(2, 1fr);
    }

    .portfolio-head {
        display: block;
    }

    .portfolio-description {
        margin-top: 25px;
    }
}


@media(max-width: 600px) {

    .nav {
        height: 70px;
    }

    .hero-content {
        padding-top: 115px;
    }

    .hero-logo {
        width: 88vw;

        margin-bottom: 28px;
    }

    .hero-title {
        font-size: 39px;
    }

    .session-grid {
        grid-template-columns: 1fr;
    }

    .session {
        min-height: 275px;
    }

    .selected-box {
        display: block;
    }

    .selected-button {
        display: inline-block;

        margin-top: 20px;
    }

    .gallery {
        grid-template-columns: 1fr;

        grid-auto-rows: 280px;
    }

    .gallery-item:nth-child(n) {
        grid-column: span 1;
        grid-row: span 1;
    }

    .contact {
        min-height: auto;
    }

    .footer {
        flex-direction: column;

        gap: 10px;
    }

    .cursor {
        display: none;
    }
}

</style>
</head>


<body>


<!-- =========================================================
     КУРСОР
========================================================= -->

<div class="cursor"></div>


<!-- =========================================================
     МЕНЮ
========================================================= -->

<header class="nav">

    <a href="#" class="nav-logo">
        Неллі <span>фото</span>
    </a>

    <nav class="nav-links">

        <a href="#choose">
            Види зйомок
        </a>

        <a href="#portfolio">
            Портфоліо
        </a>

        <a href="#about">
            Про мене
        </a>

    </nav>

    <a href="#contact" class="nav-button">
        Замовити зйомку
    </a>

</header>


<!-- =========================================================
     ПЕРШИЙ ЕКРАН
========================================================= -->

<section class="hero">

    <div class="hero-light"></div>

    <div class="hero-ring"></div>


    <div class="hero-content">


        <!-- ЛОГОТИП -->

        <div class="hero-logo">

            <img
                src="logo.png"
                alt="Логотип Неллі"
            >

        </div>


        <div class="hero-caption">

            <div class="hero-small">
                Фотограф у Празі
            </div>


            <h1 class="hero-title">

                Ваші моменти.
                <br>

                <em>Моя історія в кадрі.</em>

            </h1>


            <p class="hero-description">

                Весілля · Хрестини · Обрядові події ·
                Студійні фотосесії · Портрети · Сімейні зйомки

            </p>


            <a
                href="#choose"
                class="hero-button"
            >

                Обрати зйомку

                <span>↓</span>

            </a>

        </div>

    </div>


    <div class="hero-scroll">

        Гортайте

        <div class="scroll-line"></div>

    </div>

</section>


<!-- =========================================================
     ВСТУП
========================================================= -->

<section class="intro reveal">

    <div>

        <div class="номер-секції">
            01 — Про фотографію
        </div>

    </div>


    <div>

        <h2 class="intro-title">

            Фотографії,
            <br>

            які хочеться
            <em>відчути.</em>

        </h2>


        <p class="intro-text">

            Не потрібно вміти позувати.
            Не потрібно знати, куди дивитися.

            <br><br>

            Просто будьте собою —
            я подбаю про те, щоб ваші емоції,
            людей поруч і важливі моменти
            залишити у кадрі.

        </p>

    </div>

</section>


<!-- =========================================================
     ВИБІР ЗЙОМКИ
========================================================= -->

<section
    class="choose"
    id="choose"
>

    <div class="choose-header reveal">

        <div class="номер-секції">
            02 — Оберіть зйомку
        </div>


        <h2 class="choose-title">

            Яку зйомку
            <br>

            ви
            <em>шукаєте?</em>

        </h2>


        <p class="choose-subtitle">

            Оберіть варіант, який вам підходить.
            Якщо ви ще не визначилися —
            нічого страшного, я допоможу підібрати
            формат саме для вас.

        </p>

    </div>


    <div class="session-grid">


        <!-- 01 -->

        <article
            class="session reveal"
            data-name="Весільна фотосесія"
        >

            <div class="session-number">
                01
            </div>

            <div class="session-symbol">
                В
            </div>

            <h3>
                Весільна фотосесія
            </h3>

            <small>
                Ваш особливий день
            </small>

        </article>


        <!-- 02 -->

        <article
            class="session reveal"
            data-name="Фотосесія хрестин"
        >

            <div class="session-number">
                02
            </div>

            <div class="session-symbol">
                Х
            </div>

            <h3>
                Хрестини
            </h3>

            <small>
                Важливий день для родини
            </small>

        </article>


        <!-- 03 -->

        <article
            class="session reveal"
            data-name="Обрядова фотосесія"
        >

            <div class="session-number">
                03
            </div>

            <div class="session-symbol">
                О
            </div>

            <h3>
                Обрядова фотосесія
            </h3>

            <small>
                Традиції та особливі моменти
            </small>

        </article>


        <!-- 04 -->

        <article
            class="session reveal"
            data-name="Студійна фотосесія"
        >

            <div class="session-number">
                04
            </div>

            <div class="session-symbol">
                С
            </div>

            <h3>
                Студійна фотосесія
            </h3>

            <small>
                Зйомка у студії
            </small>

        </article>


        <!-- 05 -->

        <article
            class="session reveal"
            data-name="Індивідуальна фотосесія"
        >

            <div class="session-number">
                05
            </div>

            <div class="session-symbol">
                І
            </div>

            <h3>
                Індивідуальна фотосесія
            </h3>

            <small>
                Фотосесія саме для вас
            </small>

        </article>


        <!-- 06 -->

        <article
            class="session reveal"
            data-name="Сімейна фотосесія"
        >

            <div class="session-number">
                06
            </div>

            <div class="session-symbol">
                С
            </div>

            <h3>
                Сімейна фотосесія
            </h3>

            <small>
                Теплі моменти родини
            </small>

        </article>


        <!-- 07 -->

        <article
            class="session reveal"
            data-name="Фотосесія для двох"
        >

            <div class="session-number">
                07
            </div>

            <div class="session-symbol">
                ♥
            </div>

            <h3>
                Фотосесія для двох
            </h3>

            <small>
                Для закоханих
            </small>

        </article>


        <!-- 08 -->

        <article
            class="session reveal"
            data-name="Інша фотосесія"
        >

            <div class="session-number">
                08
            </div>

            <div class="session-symbol">
                +
            </div>

            <h3>
                Інша фотосесія
            </h3>

            <small>
                Розкажіть про свою ідею
            </small>

        </article>

    </div>


    <!-- ОБРАНИЙ ВАРІАНТ -->

    <div class="selected-box">

        <div>

            <div class="selected-label">
                Ви обрали
            </div>

            <div
                class="selected-name"
                id="selectedName"
            >
                Оберіть вид зйомки
            </div>

        </div>


        <a
            href="#contact"
            class="selected-button"
        >
            Розповісти про зйомку →
        </a>

    </div>

</section>


<!-- =========================================================
     РУХОМИЙ РЯДОК
========================================================= -->

<div class="marquee">

    <div class="marquee-track">

        <span>Весілля</span>
        <span class="marquee-dot">✦</span>

        <span>Хрестини</span>
        <span class="marquee-dot">✦</span>

        <span>Студійні фотосесії</span>
        <span class="marquee-dot">✦</span>

        <span>Сімейні фотосесії</span>
        <span class="marquee-dot">✦</span>

        <span>Портрети</span>
        <span class="marquee-dot">✦</span>

        <span>Фотосесії для двох</span>
        <span class="marquee-dot">✦</span>

        <span>Весілля</span>
        <span class="marquee-dot">✦</span>

        <span>Хрестини</span>
        <span class="marquee-dot">✦</span>

    </div>

</div>


<!-- =========================================================
     ПОРТФОЛІО
========================================================= -->

<section
    class="portfolio"
    id="portfolio"
>

    <div class="portfolio-head reveal">

        <div>

            <div class="номер-секції">
                03 — Портфоліо
            </div>


            <h2 class="portfolio-title">

                Моменти,
                <br>

                які хочеться
                <em>зберегти.</em>

            </h2>

        </div>


        <p class="portfolio-description">

            Тут згодом з'являться справжні
            фотографії Неллі.

            <br><br>

            Весілля, хрестини, студійні,
            сімейні та індивідуальні зйомки.

        </p>

    </div>


    <div class="gallery reveal">


        <div class="gallery-item">

            ФОТО

            <span class="gallery-tag">
                Весілля
            </span>

        </div>


        <div class="gallery-item">

            ФОТО

            <span class="gallery-tag">
                Студія
            </span>

        </div>


        <div class="gallery-item">

            ФОТО

            <span class="gallery-tag">
                Хрестини
            </span>

        </div>


        <div class="gallery-item">

            ФОТО

            <span class="gallery-tag">
                Портрет
            </span>

        </div>


        <div class="gallery-item">

            ФОТО

            <span class="gallery-tag">
                Для двох
            </span>

        </div>


    </div>

</section>


<!-- =========================================================
     ПРО НЕЛЛІ
========================================================= -->

<section
    class="about"
    id="about"
>


    <div class="about-photo reveal">

        <span>
            Н.
        </span>

    </div>


    <div class="reveal">

        <div class="номер-секції">
            04 — Про фотографа
        </div>


        <h2 class="about-title">

            Привіт,
            <br>

            я
            <em>Неллі.</em>

        </h2>


        <p class="about-text">

            Я фотограф у Празі.

            <br><br>

            Знімаю весілля, хрестини,
            обрядові події, студійні,
            сімейні та індивідуальні
            фотосесії.

            <br><br>

            Для мене важливо не просто
            зробити красиву фотографію,
            а зберегти справжні емоції,
            атмосферу та людей,
            які були поруч.

        </p>


        <div class="quote">

            «Найкращі фотографії —
            це ті, де ви бачите
            себе справжніх.»

        </div>

    </div>

</section>


<!-- =========================================================
     КОНТАКТ
========================================================= -->

<section
    class="contact"
    id="contact"
>


    <div class="reveal">

        <div class="номер-секції">
            05 — Замовити зйомку
        </div>


        <h2 class="contact-title">

            Розкажіть
            <br>

            про свою
            <br>

            <em>зйомку.</em>

        </h2>

    </div>


    <div class="contact-text reveal">

        Розкажіть, яку фотосесію ви хочете,
        бажану дату та кілька слів
        про вашу ідею.

        <br><br>

        Якщо ви ще не знаєте, як саме
        має виглядати зйомка —
        нічого страшного.

        Разом підберемо найкращий варіант.

        <div class="contact-links">


            <a
                href="#"
                class="contact-link"
            >
                Перейти в Instagram ↗
            </a>


            <a
                href="mailto:hello@example.com"
                class="contact-link"
            >
                Написати Неллі ↗
            </a>


        </div>

    </div>
 
</section>


<!-- =========================================================
     НИЗ
========================================================= -->

<footer class="footer">

    <span>
        НЕЛЛІ · ФОТОГРАФ · ПРАГА
    </span>

    <span>
        © 2026
    </span>

</footer>


<script>

/* =========================================================
   КУРСОР
========================================================= */

const cursor =
    document.querySelector(".cursor");


document.addEventListener(
    "mousemove",
    function(event) {

        cursor.style.left =
            event.clientX + "px";

        cursor.style.top =
            event.clientY + "px";

    }
);


document
    .querySelectorAll(
        "a, .session, .gallery-item"
    )
    .forEach(function(element) {

        element.addEventListener(
            "mouseenter",
            function() {

                cursor.classList.add("active");

            }
        );

        element.addEventListener(
            "mouseleave",
            function() {

                cursor.classList.remove("active");

            }
        );

    });


/* =========================================================
   РУХ СВІТЛА ЗА МИШКОЮ
========================================================= */

const light =
    document.querySelector(".hero-light");


document.addEventListener(
    "mousemove",
    function(event) {

        const x =
            (
                event.clientX /
                window.innerWidth -
                .5
            ) * 35;

        const y =
            (
                event.clientY /
                window.innerHeight -
                .5
            ) * 35;


        light.style.transform =
            `translate(${x}px, ${y}px)`;

    }
);


/* =========================================================
   ВИБІР ФОТОСЕСІЇ
========================================================= */

const sessions =
    document.querySelectorAll(".session");

const selectedName =
    document.getElementById("selectedName");


sessions.forEach(function(session) {

    session.addEventListener(
        "click",
        function() {


            sessions.forEach(function(item) {

                item.classList.remove("selected");

            });


            session.classList.add("selected");


            const name =
                session.dataset.name;


            selectedName.style.opacity = "0";


            setTimeout(function() {

                selectedName.textContent =
                    name;

                selectedName.style.opacity =
                    "1";

            }, 180);

        }
    );

});


/* =========================================================
   ПОЯВА БЛОКІВ ПРИ ПРОКРУТЦІ
========================================================= */

const observer =
    new IntersectionObserver(
        function(entries) {

            entries.forEach(
                function(entry) {

                    if (
                        entry.isIntersecting
                    ) {

                        entry.target
                            .classList
                            .add("visible");

                        observer
                            .unobserve(
                                entry.target
                            );

                    }

                }
            );

        },
        {
            threshold: .12
        }
    );


document
    .querySelectorAll(".reveal")
    .forEach(function(element) {

        observer.observe(element);

    });


/* =========================================================
   ПЛАВИЙ ПЕРЕХІД ДО РОЗДІЛІВ
========================================================= */

document
    .querySelectorAll('a[href^="#"]')
    .forEach(function(link) {

        link.addEventListener(
            "click",
            function(event) {

                const target =
                    document.querySelector(
                        this.getAttribute("href")
                    );


                if (target) {

                    event.preventDefault();


                    target.scrollIntoView({
                        behavior: "smooth"
                    });

                }

            }
        );

    });

</script>

</body>
</html>
