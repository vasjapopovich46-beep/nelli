<!DOCTYPE html>
<html lang="uk">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>NELLI — Photographer Prague</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">

<style>

/* =========================================================
   VARIABLES
========================================================= */

:root {
    --black: #0d0d0c;
    --dark: #141412;
    --cream: #eee9e1;
    --cream2: #f5f1ea;
    --gold: #b99b78;
    --muted: #817b72;
    --line: rgba(255,255,255,.12);

    --serif: "Cormorant Garamond", serif;
    --sans: "DM Sans", sans-serif;
}


/* =========================================================
   RESET
========================================================= */

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    background: var(--black);
    color: var(--cream);
    font-family: var(--sans);
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
   FILM GRAIN
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
   CUSTOM CURSOR
========================================================= */

.cursor {
    position: fixed;

    width: 10px;
    height: 10px;

    border: 1px solid rgba(255,255,255,.8);

    border-radius: 50%;

    pointer-events: none;

    z-index: 99999;

    transform: translate(-50%, -50%);

    transition:
        width .35s ease,
        height .35s ease,
        background .35s ease,
        border-color .35s ease;
}

.cursor.active {
    width: 60px;
    height: 60px;

    background: rgba(255,255,255,.08);

    border-color: rgba(255,255,255,.4);
}


/* =========================================================
   NAVIGATION
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

    background: linear-gradient(
        to bottom,
        rgba(13,13,12,.85),
        transparent
    );

    backdrop-filter: blur(8px);
}

.nav-logo {
    font-family: var(--serif);

    font-size: 25px;

    letter-spacing: -.04em;
}

.nav-logo em {
    font-style: italic;
}

.nav-links {
    display: flex;
    gap: 35px;

    font-size: 10px;

    text-transform: uppercase;

    letter-spacing: .16em;
}

.nav-links a {
    color: #aaa49b;

    transition: .3s;
}

.nav-links a:hover {
    color: white;
}

.nav-book {
    padding: 11px 17px;

    border: 1px solid rgba(255,255,255,.25);

    border-radius: 100px;

    font-size: 9px;

    text-transform: uppercase;

    letter-spacing: .14em;

    transition: .35s;
}

.nav-book:hover {
    background: white;
    color: var(--black);
}


/* =========================================================
   HERO
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
            #3d3932 0%,
            #201f1b 30%,
            #0d0d0c 72%
        );
}


/* glowing background */

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


/* subtle rings */

.hero-ring {
    position: absolute;

    width: 55vw;
    height: 55vw;

    max-width: 700px;
    max-height: 700px;

    border: 1px solid rgba(255,255,255,.06);

    border-radius: 50%;

    animation: rotateRing 30s linear infinite;
}

.hero-ring::before {
    content: "";

    position: absolute;

    inset: 12%;

    border: 1px solid rgba(255,255,255,.035);

    border-radius: 50%;
}

@keyframes rotateRing {

    from {
        transform: rotate(0deg);
    }

    to {
        transform: rotate(360deg);
    }

}


/* hero content */

.hero-content {
    position: relative;

    z-index: 3;

    width: 100%;

    padding: 130px 20px 100px;
}


/* logo */

.hero-logo {
    width: min(520px, 78vw);

    margin: 0 auto 42px;

    opacity: 0;

    transform:
        translateY(35px)
        scale(.94);

    animation:
        logoReveal 1.5s
        .15s
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
            0 30px 70px
            rgba(190,155,115,.22)
        );
}

@keyframes logoReveal {

    0% {
        opacity: 0;

        transform:
            translateY(50px)
            scale(.9);

        filter: blur(12px);
    }

    60% {
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


/* hero caption */

.hero-caption {
    opacity: 0;

    animation:
        fadeUp 1s
        1s
        forwards;
}

.hero-caption-top {
    color: var(--gold);

    font-size: 9px;

    text-transform: uppercase;

    letter-spacing: .28em;

    margin-bottom: 18px;
}

.hero-caption h1 {
    font-family: var(--serif);

    font-weight: 300;

    font-size: clamp(35px, 5vw, 65px);

    line-height: .9;

    letter-spacing: -.04em;
}

.hero-caption h1 em {
    font-style: italic;
}

.hero-description {
    max-width: 470px;

    margin: 25px auto 0;

    color: #aaa49b;

    font-size: 14px;

    line-height: 1.7;
}


/* CTA */

.hero-button {
    display: inline-flex;

    align-items: center;

    gap: 13px;

    margin-top: 30px;

    padding: 14px 19px;

    border: 1px solid rgba(255,255,255,.25);

    border-radius: 100px;

    font-size: 9px;

    text-transform: uppercase;

    letter-spacing: .15em;

    transition: .4s;
}

.hero-button:hover {
    background: white;

    color: var(--black);

    padding-left: 25px;

    padding-right: 25px;
}

.hero-button span {
    font-size: 16px;
}


/* scroll */

.hero-scroll {
    position: absolute;

    bottom: 25px;

    left: 50%;

    transform: translateX(-50%);

    display: flex;

    flex-direction: column;

    align-items: center;

    gap: 10px;

    color: #66615a;

    font-size: 8px;

    text-transform: uppercase;

    letter-spacing: .25em;
}

.scroll-line {
    width: 1px;

    height: 45px;

    background: linear-gradient(
        to bottom,
        #777,
        transparent
    );

    animation: scrollAnim 2s infinite;
}

@keyframes scrollAnim {

    0% {
        opacity: 0;
        transform: scaleY(0);
        transform-origin: top;
    }

    50% {
        opacity: 1;
        transform: scaleY(1);
    }

    100% {
        opacity: 0;
        transform: scaleY(1);
        transform-origin: bottom;
    }

}


/* =========================================================
   INTRO
========================================================= */

.intro {
    min-height: 75vh;

    padding: 130px 7vw;

    display: grid;

    grid-template-columns: .65fr 1.35fr;

    gap: 10vw;

    align-items: center;

    background: var(--cream2);

    color: #171614;
}

.eyebrow {
    font-size: 9px;

    text-transform: uppercase;

    letter-spacing: .22em;

    color: #817a70;
}

.intro-title {
    font-family: var(--serif);

    font-weight: 300;

    font-size: clamp(48px, 6vw, 85px);

    line-height: .9;

    letter-spacing: -.055em;
}

.intro-title em {
    font-style: italic;
}

.intro-text {
    max-width: 650px;

    margin-top: 35px;

    font-size: 18px;

    line-height: 1.8;

    color: #676159;
}


/* =========================================================
   CHOOSE
========================================================= */

.choose {
    padding: 145px 5vw;

    background: var(--dark);
}

.choose-header {
    max-width: 900px;

    margin-bottom: 75px;
}

.choose-title {
    margin-top: 18px;

    font-family: var(--serif);

    font-weight: 300;

    font-size: clamp(55px, 8vw, 105px);

    line-height: .82;

    letter-spacing: -.065em;
}

.choose-title em {
    font-style: italic;
}

.choose-subtitle {
    max-width: 500px;

    margin-top: 35px;

    color: #858077;

    font-size: 14px;

    line-height: 1.8;
}


/* cards */

.session-grid {
    display: grid;

    grid-template-columns:
        repeat(4, 1fr);

    gap: 10px;
}

.session {
    min-height: 340px;

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
    margin-top: 48px;

    font-family: var(--serif);

    font-size: 48px;

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
    bottom: 50px;

    font-family: var(--serif);

    font-size: 30px;

    font-weight: 300;
}

.session small {
    position: absolute;

    left: 24px;
    bottom: 23px;

    color: #69645c;

    font-size: 8px;

    text-transform: uppercase;

    letter-spacing: .16em;
}


/* selected */

.selected {
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

    font-family: var(--serif);

    font-size: 26px;

    font-style: italic;

    color: #eee9e1;
}

.selected-button {
    padding: 13px 19px;

    background: var(--cream);

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
   MARQUEE
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
        marquee 25s
        linear
        infinite;
}

.marquee span {
    font-family: var(--serif);

    font-size: 28px;

    font-style: italic;
}

.marquee-dot {
    font-family: var(--sans);

    font-style: normal;

    opacity: .5;
}

@keyframes marquee {

    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(-50%);
    }

}


/* =========================================================
   PORTFOLIO
========================================================= */

.portfolio {
    padding: 145px 5vw;

    background: var(--cream2);

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

    font-family: var(--serif);

    font-size: clamp(55px, 7vw, 100px);

    line-height: .82;

    font-weight: 300;

    letter-spacing: -.065em;
}

.portfolio-title em {
    font-style: italic;
}

.portfolio-description {
    max-width: 280px;

    color: #777169;

    font-size: 12px;

    line-height: 1.7;
}


/* portfolio placeholders */

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

    font-family: var(--serif);

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

    font-family: var(--sans);

    font-size: 8px;

    font-style: normal;

    text-transform: uppercase;

    letter-spacing: .14em;
}


/* =========================================================
   ABOUT
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

    background:
        radial-gradient(
            circle at 40% 35%,
            #bca991,
            #61594e 45%,
            #282621 85%
        );

    display: flex;

    align-items: center;

    justify-content: center;
}

.about-photo span {
    font-family: var(--serif);

    font-size: 80px;

    font-style: italic;

    color: rgba(255,255,255,.35);
}

.about-title {
    margin-top: 20px;

    font-family: var(--serif);

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

    font-family: var(--serif);

    font-size: 26px;

    line-height: 1.35;
}


/* =========================================================
   CONTACT
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

    font-family: var(--serif);

    font-size: clamp(60px, 8vw, 115px);

    font-weight: 300;

    line-height: .8;

    letter-spacing: -.07em;
}

.contact-title em {
    font-style: italic;
}

.contact-text {
    align-self: end;

    max-width: 470px;

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
    padding: 14px 18px;

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
   FOOTER
========================================================= */

.footer {
    padding: 24px 5vw;

    display: flex;

    justify-content: space-between;

    background: #0d0d0c;

    color: #66625c;

    font-size: 8px;

    text-transform: uppercase;

    letter-spacing: .17em;
}


/* =========================================================
   REVEAL
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
   MOBILE
========================================================= */

@media(max-width: 900px) {

    .nav-links {
        display: none;
    }

    .nav-book {
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
        grid-template-columns: repeat(2,1fr);
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
        padding-top: 120px;
    }

    .hero-logo {
        width: 88vw;

        margin-bottom: 30px;
    }

    .hero-caption h1 {
        font-size: 38px;
    }

    .session-grid {
        grid-template-columns: 1fr;
    }

    .session {
        min-height: 280px;
    }

    .selected {
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
     CURSOR
========================================================= -->

<div class="cursor"></div>



<!-- =========================================================
     NAVIGATION
========================================================= -->

<header class="nav">

    <a href="#" class="nav-logo">
        nelli <em>photo</em>
    </a>


    <nav class="nav-links">

        <a href="#choose">
            Зйомки
        </a>

        <a href="#portfolio">
            Портфоліо
        </a>

        <a href="#about">
            Про мене
        </a>

    </nav>


    <a href="#contact" class="nav-book">
        Забронювати
    </a>

</header>



<!-- =========================================================
     HERO
========================================================= -->

<section class="hero">

    <div class="hero-light"></div>

    <div class="hero-ring"></div>


    <div class="hero-content">


        <!-- ЛОГОТИП -->

        <div class="hero-logo">

            <img
                src="logo.png"
                alt="Nelli Photographer Prague"
            >

        </div>


        <div class="hero-caption">

            <div class="hero-caption-top">
                Photographer · Prague
            </div>


            <h1>
                Your story.
                <em>My vision.</em>
            </h1>


            <p class="hero-description">

                Весілля · Хрестини · Студія · Portrait ·
                Love Story · Family

            </p>


            <a href="#choose" class="hero-button">

                Обрати свою зйомку

                <span>
                    ↓
                </span>

            </a>

        </div>

    </div>


    <div class="hero-scroll">

        Scroll

        <div class="scroll-line"></div>

    </div>

</section>



<!-- =========================================================
     INTRO
========================================================= -->

<section class="intro reveal">

    <div>

        <div class="eyebrow">
            01 — Philosophy
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
            я подбаю про те, щоб ваша історія
            залишилася у кадрі.

        </p>

    </div>

</section>



<!-- =========================================================
     SESSION CHOICE
========================================================= -->

<section class="choose" id="choose">


    <div class="choose-header reveal">

        <div class="eyebrow">
            02 — Your story
        </div>


        <h2 class="choose-title">

            Яку історію
            <br>

            створимо
            <em>разом?</em>

        </h2>


        <p class="choose-subtitle">

            Оберіть те, що найближче саме вам.
            Якщо не знаєте, що підійде —
            просто оберіть «Інше».

        </p>

    </div>



    <div class="session-grid">


        <article
            class="session reveal"
            data-name="Wedding"
        >

            <div class="session-number">
                01
            </div>

            <div class="session-symbol">
                W
            </div>

            <h3>
                Wedding
            </h3>

            <small>
                Весільна зйомка
            </small>

        </article>



        <article
            class="session reveal"
            data-name="Хрестини"
        >

            <div class="session-number">
                02
            </div>

            <div class="session-symbol">
                B
            </div>

            <h3>
                Хрестини
            </h3>

            <small>
                Baptism
            </small>

        </article>



        <article
            class="session reveal"
            data-name="Обрядова фотосесія"
        >

            <div class="session-number">
                03
            </div>

            <div class="session-symbol">
                C
            </div>

            <h3>
                Обряди
            </h3>

            <small>
                Особливі моменти
            </small>

        </article>



        <article
            class="session reveal"
            data-name="Studio"
        >

            <div class="session-number">
                04
            </div>

            <div class="session-symbol">
                S
            </div>

            <h3>
                Studio
            </h3>

            <small>
                Студійна фотосесія
            </small>

        </article>



        <article
            class="session reveal"
            data-name="Portrait"
        >

            <div class="session-number">
                05
            </div>

            <div class="session-symbol">
                P
            </div>

            <h3>
                Portrait
            </h3>

            <small>
                Індивідуальна
            </small>

        </article>



        <article
            class="session reveal"
            data-name="Family"
        >

            <div class="session-number">
                06
            </div>

            <div class="session-symbol">
                F
            </div>

            <h3>
                Family
            </h3>

            <small>
                Сімейна
            </small>

        </article>



        <article
            class="session reveal"
            data-name="Love Story"
        >

            <div class="session-number">
                07
            </div>

            <div class="session-symbol">
                L
            </div>

            <h3>
                Love Story
            </h3>

            <small>
                Для двох
            </small>

        </article>



        <article
            class="session reveal"
            data-name="Інше"
        >

            <div class="session-number">
                08
            </div>

            <div class="session-symbol">
                +
            </div>

            <h3>
                Інше
            </h3>

            <small>
                Ваша ідея
            </small>

        </article>


    </div>



    <!-- SELECTED SESSION -->

    <div class="selected">

        <div>

            <div class="selected-label">
                Обраний формат
            </div>

            <div
                class="selected-name"
                id="selectedName"
            >
                Оберіть зйомку
            </div>

        </div>


        <a
            href="#contact"
            class="selected-button"
        >
            Продовжити →
        </a>

    </div>

</section>



<!-- =========================================================
     MARQUEE
========================================================= -->

<div class="marquee">

    <div class="marquee-track">

        <span>
            Wedding
        </span>

        <span class="marquee-dot">
            ✦
        </span>

        <span>
            Love Story
        </span>

        <span class="marquee-dot">
            ✦
        </span>

        <span>
            Studio
        </span>

        <span class="marquee-dot">
            ✦
        </span>

        <span>
            Family
        </span>

        <span class="marquee-dot">
            ✦
        </span>

        <span>
            Portrait
        </span>

        <span class="marquee-dot">
            ✦
        </span>

        <span>
            Wedding
        </span>

        <span class="marquee-dot">
            ✦
        </span>

        <span>
            Love Story
        </span>

        <span class="marquee-dot">
            ✦
        </span>

    </div>

</div>



<!-- =========================================================
     PORTFOLIO
========================================================= -->

<section class="portfolio" id="portfolio">


    <div class="portfolio-head reveal">

        <div>

            <div class="eyebrow">
                03 — Selected work
            </div>

            <h2 class="portfolio-title">

                Ваші моменти.
                <br>

                Наші
                <em>кадри.</em>

            </h2>

        </div>


        <p class="portfolio-description">

            Тут згодом з'являться справжні
            фотографії Неллі.

            <br><br>

            Великі кадри, мінімум тексту,
            максимум атмосфери.

        </p>

    </div>



    <div class="gallery reveal">


        <div class="gallery-item">

            PHOTO

            <span class="gallery-tag">
                Wedding
            </span>

        </div>


        <div class="gallery-item">

            PHOTO

            <span class="gallery-tag">
                Studio
            </span>

        </div>


        <div class="gallery-item">

            PHOTO

            <span class="gallery-tag">
                Baptism
            </span>

        </div>


        <div class="gallery-item">

            PHOTO

            <span class="gallery-tag">
                Portrait
            </span>

        </div>


        <div class="gallery-item">

            PHOTO

            <span class="gallery-tag">
                Love Story
            </span>

        </div>


    </div>

</section>



<!-- =========================================================
     ABOUT
========================================================= -->

<section class="about" id="about">


    <div class="about-photo reveal">

        <span>
            N.
        </span>

    </div>


    <div class="reveal">

        <div class="eyebrow">
            04 — About Nelli
        </div>


        <h2 class="about-title">

            Привіт,
            <br>

            я
            <em>Неллі.</em>

        </h2>


        <p class="about-text">

            Фотограф у Празі.

            <br><br>

            Весілля, хрестини, обрядові події,
            студійні, сімейні та індивідуальні
            фотосесії.

            <br><br>

            Мені подобається ловити не просто
            красивий кадр, а справжню емоцію
            всередині нього.

        </p>


        <div class="quote">

            «Найкращі фотографії —
            це ті, де ви бачите
            себе справжніх.»

        </div>

    </div>

</section>



<!-- =========================================================
     CONTACT
========================================================= -->

<section class="contact" id="contact">


    <div class="reveal">

        <div class="eyebrow">
            05 — Let's create
        </div>


        <h2 class="contact-title">

            Розкажіть
            <br>

            про свою
            <br>

            <em>історію.</em>

        </h2>

    </div>


    <div class="contact-text reveal">

        Напишіть, яку зйомку ви хочете,
        бажану дату та кілька слів
        про вашу ідею.

        <br><br>

        Навіть якщо ви ще не знаєте,
        як саме все має виглядати —
        це нормально.

        <div class="contact-links">

            <a
                href="#"
                class="contact-link"
            >
                Instagram ↗
            </a>


            <a
                href="mailto:hello@example.com"
                class="contact-link"
            >
                Написати ↗
            </a>

        </div>

    </div>

</section>



<!-- =========================================================
     FOOTER
========================================================= -->

<footer class="footer">

    <span>
        NELLI PHOTO · PRAGUE
    </span>

    <span>
        © 2026
    </span>

</footer>



<script>

/* =========================================================
   CUSTOM CURSOR
========================================================= */

const cursor =
    document.querySelector(".cursor");


document.addEventListener(
    "mousemove",
    (event) => {

        cursor.style.left =
            event.clientX + "px";

        cursor.style.top =
            event.clientY + "px";

    }
);


document
    .querySelectorAll(
        "a, button, .session, .gallery-item"
    )
    .forEach(element => {

        element.addEventListener(
            "mouseenter",
            () => {

                cursor.classList.add("active");

            }
        );

        element.addEventListener(
            "mouseleave",
            () => {

                cursor.classList.remove("active");

            }
        );

    });


/* =========================================================
   HERO PARALLAX
========================================================= */

const light =
    document.querySelector(".hero-light");


document.addEventListener(
    "mousemove",
    (event) => {

        const x =
            (event.clientX /
                window.innerWidth - .5) * 35;

        const y =
            (event.clientY /
                window.innerHeight - .5) * 35;


        light.style.transform =
            `translate(${x}px, ${y}px)`;

    }
);


/* =========================================================
   SESSION SELECT
========================================================= */

const sessions =
    document.querySelectorAll(".session");

const selectedName =
    document.getElementById("selectedName");


sessions.forEach(session => {

    session.addEventListener(
        "click",
        () => {

            sessions.forEach(item => {

                item.style.borderColor =
                    "#33312d";

            });


            session.style.borderColor =
                "#b99b78";


            const name =
                session.dataset.name;


            selectedName.style.opacity = "0";


            setTimeout(() => {

                selectedName.textContent =
                    name;

                selectedName.style.opacity =
                    "1";

            }, 180);

        }
    );

});


/* =========================================================
   SCROLL REVEAL
========================================================= */

const observer =
    new IntersectionObserver(
        (entries) => {

            entries.forEach(entry => {

                if(entry.isIntersecting) {

                    entry.target
                        .classList
                        .add("visible");

                    observer
                        .unobserve(entry.target);

                }

            });

        },
        {
            threshold: .12
        }
    );


document
    .querySelectorAll(".reveal")
    .forEach(element => {

        observer.observe(element);

    });


/* =========================================================
   SMOOTH CONTACT BUTTON
========================================================= */

document
    .querySelectorAll('a[href^="#"]')
    .forEach(link => {

        link.addEventListener(
            "click",
            function(event) {

                const target =
                    document.querySelector(
                        this.getAttribute("href")
                    );

                if(target) {

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
