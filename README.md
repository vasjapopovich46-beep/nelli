<!DOCTYPE html>
<html lang="uk">

<head>

<meta charset="UTF-8">

<meta
    name="viewport"
    content="width=device-width, initial-scale=1.0"
>

<meta
    name="description"
    content="Nelli Photography — фотограф у Празі. Весілля, хрещення, дні народження, сімейні, портретні та студійні фотосесії."
>

<title>NELLI — Photography</title>


<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

<link
    href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap"
    rel="stylesheet"
>


<style>

/* =====================================================
   RESET
===================================================== */

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    background: #10100f;
    color: #eee9e1;
    font-family: "DM Sans", sans-serif;
    font-weight: 300;
    overflow-x: hidden;
}

body.no-scroll {
    overflow: hidden;
}

img {
    display: block;
    width: 100%;
}

a {
    color: inherit;
    text-decoration: none;
}

button,
input,
textarea,
select {
    font: inherit;
}


/* =====================================================
   VARIABLES
===================================================== */

:root {

    --black: #10100f;
    --dark: #171715;
    --dark2: #1d1c19;

    --cream: #eee9e1;
    --muted: #9b958b;

    --line: rgba(238,233,225,.13);

    --accent: #c6b29a;

    --serif: "Cormorant Garamond", serif;
    --sans: "DM Sans", sans-serif;
}


/* =====================================================
   CURSOR
===================================================== */

.cursor-dot {

    position: fixed;

    width: 7px;
    height: 7px;

    border-radius: 50%;

    background: #fff;

    pointer-events: none;

    z-index: 9999;

    transform: translate(-50%,-50%);

    mix-blend-mode: difference;

    transition:
        width .25s,
        height .25s;
}

.cursor-ring {

    position: fixed;

    width: 35px;
    height: 35px;

    border: 1px solid rgba(255,255,255,.55);

    border-radius: 50%;

    pointer-events: none;

    z-index: 9998;

    transform: translate(-50%,-50%);

    transition:
        width .35s,
        height .35s,
        background .35s;
}


/* =====================================================
   PRELOADER
===================================================== */

.loader {

    position: fixed;

    inset: 0;

    background: #10100f;

    z-index: 10000;

    display: flex;

    align-items: center;

    justify-content: center;

    flex-direction: column;

    transition:
        opacity .8s,
        visibility .8s;
}

.loader.hidden {

    opacity: 0;

    visibility: hidden;
}

.loader-logo {

    font-family: var(--serif);

    font-size: 60px;

    font-weight: 300;

    letter-spacing: -.06em;
}

.loader-line {

    width: 120px;

    height: 1px;

    background: rgba(255,255,255,.2);

    margin-top: 25px;

    position: relative;

    overflow: hidden;
}

.loader-line::after {

    content: "";

    position: absolute;

    inset: 0;

    background: #eee9e1;

    transform: translateX(-100%);

    animation: loading 1.4s forwards;
}

@keyframes loading {

    to {
        transform: translateX(0);
    }

}


/* =====================================================
   NAV
===================================================== */

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
            rgba(16,16,15,.92),
            rgba(16,16,15,0)
        );

    backdrop-filter: blur(8px);

    transition:
        background .4s,
        height .4s;
}

.nav.scrolled {

    height: 68px;

    background:
        rgba(16,16,15,.88);

    backdrop-filter: blur(18px);
}

.brand {

    font-family: var(--serif);

    font-size: 30px;

    letter-spacing: -.06em;

    white-space: nowrap;
}

.brand span {

    font-style: italic;

    color: #b9ab9a;
}

.nav-links {

    display: flex;

    align-items: center;

    gap: 30px;

    font-size: 9px;

    letter-spacing: .18em;

    text-transform: uppercase;
}

.nav-links a {

    color: #a7a097;

    transition: color .3s;
}

.nav-links a:hover {

    color: #fff;
}


/* =====================================================
   LANGUAGE
===================================================== */

.language {

    position: relative;
}

.language-button {

    height: 36px;

    min-width: 55px;

    padding: 0 12px;

    border: 1px solid var(--line);

    border-radius: 50px;

    background: rgba(255,255,255,.03);

    color: #eee9e1;

    cursor: pointer;

    display: flex;

    align-items: center;

    justify-content: center;

    gap: 6px;

    font-size: 13px;

    transition: .3s;
}

.language-button:hover {

    background: rgba(255,255,255,.08);
}

.language-menu {

    position: absolute;

    top: 48px;

    right: 0;

    width: 180px;

    padding: 8px;

    background: #1d1c19;

    border: 1px solid var(--line);

    border-radius: 16px;

    box-shadow:
        0 20px 60px rgba(0,0,0,.4);

    opacity: 0;

    visibility: hidden;

    transform:
        translateY(-8px);

    transition: .3s;
}

.language.open .language-menu {

    opacity: 1;

    visibility: visible;

    transform: none;
}

.language-option {

    width: 100%;

    padding: 10px 12px;

    border: 0;

    background: transparent;

    color: #c7c1b8;

    border-radius: 10px;

    display: flex;

    align-items: center;

    gap: 10px;

    cursor: pointer;

    text-align: left;

    transition: .25s;
}

.language-option:hover {

    background: rgba(255,255,255,.08);

    color: white;
}


/* =====================================================
   MENU BUTTON
===================================================== */

.menu-button {

    display: none;

    width: 42px;
    height: 42px;

    border: 1px solid var(--line);

    border-radius: 50%;

    background: transparent;

    color: white;

    cursor: pointer;
}


/* =====================================================
   HERO
===================================================== */

.hero {

    min-height: 100vh;

    position: relative;

    display: flex;

    align-items: center;

    justify-content: center;

    overflow: hidden;

    background:

        radial-gradient(
            circle at 50% 45%,
            rgba(180,155,125,.17),
            transparent 30%
        ),

        #10100f;
}

.hero-image {

    position: absolute;

    inset: 5% 5% 0 5%;

    opacity: .35;

    overflow: hidden;

    border-radius: 0 0 50% 50%;
}

.hero-image img {

    width: 100%;
    height: 100%;

    object-fit: cover;

    filter:
        grayscale(.45)
        contrast(1.05)
        brightness(.65);

    transform: scale(1.05);

    animation: heroZoom 8s ease-out forwards;
}

@keyframes heroZoom {

    from {
        transform: scale(1.1);
    }

    to {
        transform: scale(1);
    }
}

.hero-overlay {

    position: absolute;

    inset: 0;

    background:
        linear-gradient(
            to bottom,
            rgba(16,16,15,.35),
            rgba(16,16,15,.72) 70%,
            #10100f
        );
}

.hero-circle {

    position: absolute;

    width: min(70vw,850px);

    aspect-ratio: 1;

    border: 1px solid rgba(255,255,255,.06);

    border-radius: 50%;

    animation:
        circleRotate 35s linear infinite;
}

@keyframes circleRotate {

    from {
        transform: rotate(0);
    }

    to {
        transform: rotate(360deg);
    }
}

.hero-content {

    position: relative;

    z-index: 2;

    text-align: center;

    max-width: 900px;

    padding:
        130px 20px 100px;
}

.hero-logo {

    width: min(310px,70vw);

    margin:
        0 auto 35px;

    background: transparent;

    border: 0;

    box-shadow: none;
}

.hero-logo img {

    background: transparent;

    border: 0;

    box-shadow: none;

    mix-blend-mode: screen;

    filter:
        drop-shadow(
            0 20px 50px rgba(0,0,0,.4)
        );
}

.eyebrow {

    color: var(--accent);

    font-size: 9px;

    letter-spacing: .32em;

    text-transform: uppercase;

    margin-bottom: 22px;
}

.hero h1 {

    font-family: var(--serif);

    font-size:
        clamp(55px,8vw,105px);

    line-height: .82;

    font-weight: 300;

    letter-spacing: -.07em;
}

.hero h1 em {

    font-style: italic;

    color: #c4b6a4;
}

.hero-text {

    max-width: 600px;

    margin:
        35px auto 0;

    color: #aaa49b;

    font-size: 14px;

    line-height: 1.8;
}

.hero-actions {

    display: flex;

    justify-content: center;

    gap: 10px;

    margin-top: 35px;

    flex-wrap: wrap;
}

.button {

    padding: 15px 23px;

    border-radius: 100px;

    border: 1px solid rgba(255,255,255,.22);

    font-size: 9px;

    letter-spacing: .15em;

    text-transform: uppercase;

    transition: .4s;
}

.button.primary {

    background: #eee9e1;

    color: #111;

    border-color: #eee9e1;
}

.button:hover {

    transform: translateY(-4px);
}

.button.secondary:hover {

    background: rgba(255,255,255,.08);
}

.scroll {

    position: absolute;

    bottom: 25px;

    left: 50%;

    transform:
        translateX(-50%);

    color: #77716a;

    font-size: 8px;

    letter-spacing: .25em;

    text-transform: uppercase;
}


/* =====================================================
   SECTION COMMON
===================================================== */

.section {

    padding: 150px 6vw;
}

.section-label {

    color: #756e65;

    font-size: 9px;

    letter-spacing: .25em;

    text-transform: uppercase;
}

.section-title {

    margin-top: 20px;

    font-family: var(--serif);

    font-size:
        clamp(55px,7vw,100px);

    font-weight: 300;

    line-height: .84;

    letter-spacing: -.07em;
}

.section-title em {

    font-style: italic;

    color: #bba994;
}


/* =====================================================
   INTRO
===================================================== */

.intro {

    background: #eee9e1;

    color: #171613;

    display: grid;

    grid-template-columns:
        .5fr 1.5fr;

    gap: 10vw;

    align-items: center;
}

.intro .section-label {

    color: #777168;
}

.intro-copy {

    max-width: 750px;
}

.intro-copy p {

    max-width: 650px;

    margin-top: 40px;

    color: #6e675e;

    font-size: 17px;

    line-height: 1.9;
}

.intro-note {

    margin-top: 35px;

    font-family: var(--serif);

    font-size: 27px;

    font-style: italic;

    color: #38342f;
}


/* =====================================================
   SERVICES
===================================================== */

.services {

    background: #171715;
}

.services-intro {

    display: flex;

    justify-content: space-between;

    align-items: end;

    gap: 40px;

    margin-bottom: 75px;
}

.services-description {

    max-width: 430px;

    color: #858078;

    font-size: 13px;

    line-height: 1.9;
}

.services-grid {

    display: grid;

    grid-template-columns:
        repeat(2,1fr);

    gap: 12px;
}

.service-card {

    position: relative;

    min-height: 390px;

    padding: 27px;

    overflow: hidden;

    background:
        linear-gradient(
            145deg,
            #25231f,
            #151514
        );

    border: 1px solid rgba(255,255,255,.09);

    transition:
        transform .7s cubic-bezier(.2,.8,.2,1),
        border-color .5s;
}

.service-card::before {

    content: "";

    position: absolute;

    width: 300px;
    height: 300px;

    right: -150px;
    bottom: -150px;

    border-radius: 50%;

    border: 1px solid rgba(255,255,255,.07);

    transition:
        transform .8s;
}

.service-card:hover {

    transform:
        translateY(-10px);

    border-color:
        rgba(198,178,154,.5);
}

.service-card:hover::before {

    transform: scale(1.6);
}

.service-number {

    color: #666159;

    font-size: 9px;

    letter-spacing: .2em;
}

.service-symbol {

    margin-top: 45px;

    font-family: var(--serif);

    font-size: 95px;

    font-style: italic;

    line-height: .8;

    color: #a79b8d;

    transition: .6s;
}

.service-card:hover .service-symbol {

    transform:
        translateX(10px)
        rotate(-5deg);

    color: #e2d7c7;
}

.service-info {

    position: absolute;

    left: 27px;

    bottom: 28px;
}

.service-info h3 {

    font-family: var(--serif);

    font-size: 39px;

    font-weight: 300;
}

.service-info p {

    margin-top: 8px;

    max-width: 320px;

    color: #777168;

    font-size: 11px;

    line-height: 1.6;
}

.service-arrow {

    position: absolute;

    right: 27px;

    bottom: 27px;

    width: 43px;
    height: 43px;

    border: 1px solid #403d37;

    border-radius: 50%;

    display: flex;

    align-items: center;

    justify-content: center;

    transition: .4s;
}

.service-card:hover .service-arrow {

    background: #eee9e1;

    color: #111;

    transform: rotate(45deg);
}


/* =====================================================
   MARQUEE
===================================================== */

.marquee {

    overflow: hidden;

    white-space: nowrap;

    padding: 26px 0;

    background: #c8b49d;

    color: #171613;
}

.marquee-track {

    display: inline-flex;

    align-items: center;

    gap: 35px;

    animation:
        marquee 30s linear infinite;
}

.marquee span {

    font-family: var(--serif);

    font-size: 32px;

    font-style: italic;
}

.marquee i {

    font-style: normal;

    opacity: .5;
}

@keyframes marquee {

    to {
        transform:
            translateX(-50%);
    }
}


/* =====================================================
   PORTFOLIO
===================================================== */

.portfolio {

    background: #eee9e1;

    color: #171613;
}

.portfolio-head {

    display: flex;

    justify-content: space-between;

    align-items: end;

    gap: 40px;

    margin-bottom: 70px;
}

.portfolio-description {

    max-width: 360px;

    color: #777067;

    font-size: 12px;

    line-height: 1.8;
}

.gallery {

    display: grid;

    grid-template-columns:
        repeat(12,1fr);

    grid-auto-rows: 75px;

    gap: 12px;
}

.gallery-item {

    position: relative;

    overflow: hidden;

    background: #b9b0a4;
}

.gallery-item img {

    width: 100%;
    height: 100%;

    object-fit: cover;

    transition:
        transform 1s,
        filter 1s;
}

.gallery-item:hover img {

    transform: scale(1.07);

    filter: brightness(.8);
}

.gallery-item::after {

    content: "";

    position: absolute;

    inset: 0;

    background:
        linear-gradient(
            to top,
            rgba(0,0,0,.5),
            transparent 45%
        );

    pointer-events: none;
}

.gallery-caption {

    position: absolute;

    left: 18px;
    bottom: 17px;

    z-index: 2;

    color: white;

    font-size: 8px;

    letter-spacing: .18em;

    text-transform: uppercase;
}

.g1 {

    grid-column:
        span 7;

    grid-row:
        span 7;
}

.g2 {

    grid-column:
        span 5;

    grid-row:
        span 5;
}

.g3 {

    grid-column:
        span 5;

    grid-row:
        span 6;
}

.g4 {

    grid-column:
        span 4;

    grid-row:
        span 4;
}

.g5 {

    grid-column:
        span 3;

    grid-row:
        span 4;
}


/* =====================================================
   ABOUT
===================================================== */

.about {

    background: #171715;

    display: grid;

    grid-template-columns:
        .8fr 1.2fr;

    gap: 10vw;

    align-items: center;
}

.about-photo {

    aspect-ratio: 4/5;

    overflow: hidden;

    background: #34312b;
}

.about-photo img {

    width: 100%;
    height: 100%;

    object-fit: cover;
}

.about-copy {

    max-width: 620px;
}

.about-text {

    margin-top: 38px;

    color: #928b82;

    font-size: 15px;

    line-height: 1.9;
}

.quote {

    margin-top: 45px;

    padding-top: 25px;

    border-top:
        1px solid var(--line);

    font-family: var(--serif);

    font-size: 28px;

    line-height: 1.35;

    color: #d5ccbf;
}


/* =====================================================
   CONTACT
===================================================== */

.contact {

    background: #c8b49d;

    color: #171613;

    display: grid;

    grid-template-columns:
        1fr 1fr;

    gap: 10vw;

    align-items: center;
}

.contact .section-label {

    color: #6e6256;
}

.contact-description {

    margin-top: 30px;

    max-width: 550px;

    color: #514a42;

    font-size: 15px;

    line-height: 1.9;
}

.contact-buttons {

    display: flex;

    flex-wrap: wrap;

    gap: 10px;

    margin-top: 35px;
}

.contact-button {

    padding: 14px 20px;

    border:
        1px solid rgba(23,22,19,.3);

    border-radius: 100px;

    font-size: 9px;

    letter-spacing: .15em;

    text-transform: uppercase;

    transition: .35s;
}

.contact-button:hover {

    background: #171613;

    color: #fff;

    border-color: #171613;
}


/* =====================================================
   BOOKING
===================================================== */

.booking {

    margin-top: 45px;

    padding: 30px;

    background:
        rgba(255,255,255,.22);

    border:
        1px solid rgba(23,22,19,.15);

    border-radius: 20px;
}

.booking h3 {

    font-family: var(--serif);

    font-size: 32px;

    font-weight: 300;
}

.form-grid {

    display: grid;

    grid-template-columns:
        1fr 1fr;

    gap: 12px;

    margin-top: 25px;
}

.form-field {

    display: flex;

    flex-direction: column;

    gap: 7px;
}

.form-field.full {

    grid-column:
        span 2;
}

.form-field label {

    font-size: 8px;

    letter-spacing: .16em;

    text-transform: uppercase;

    color: #645a50;
}

.form-field input,
.form-field textarea,
.form-field select {

    width: 100%;

    border: 0;

    border-bottom:
        1px solid rgba(23,22,19,.25);

    background: transparent;

    padding: 10px 0;

    outline: none;

    color: #171613;

    font-size: 13px;
}

.form-field textarea {

    min-height: 80px;

    resize: vertical;
}

.form-submit {

    margin-top: 22px;

    border: 0;

    background: #171613;

    color: white;

    border-radius: 100px;

    padding: 15px 25px;

    font-size: 9px;

    letter-spacing: .15em;

    text-transform: uppercase;

    cursor: pointer;

    transition: .35s;
}

.form-submit:hover {

    transform: translateY(-3px);

    background: #2a2824;
}


/* =====================================================
   FOOTER
===================================================== */

footer {

    background: #10100f;

    padding: 30px 5vw;

    display: flex;

    justify-content: space-between;

    color: #68625b;

    font-size: 8px;

    letter-spacing: .16em;

    text-transform: uppercase;
}


/* =====================================================
   REVEAL
===================================================== */

.reveal {

    opacity: 0;

    transform:
        translateY(35px);

    transition:
        opacity .9s ease,
        transform .9s
        cubic-bezier(.2,.8,.2,1);
}

.reveal.visible {

    opacity: 1;

    transform: none;
}


/* =====================================================
   MOBILE MENU
===================================================== */

.mobile-menu {

    position: fixed;

    inset: 0;

    background: #11110f;

    z-index: 999;

    padding: 120px 30px 40px;

    transform:
        translateX(100%);

    transition:
        transform .5s
        cubic-bezier(.2,.8,.2,1);
}

.mobile-menu.open {

    transform:
        translateX(0);
}

.mobile-menu a {

    display: block;

    font-family: var(--serif);

    font-size: 48px;

    padding: 12px 0;

    border-bottom:
        1px solid var(--line);
}


/* =====================================================
   RESPONSIVE
===================================================== */

@media(max-width:900px) {

    .nav-links {

        display: none;
    }

    .menu-button {

        display: block;
    }

    .nav {

        gap: 10px;
    }

    .services-intro {

        display: block;
    }

    .services-description {

        margin-top: 25px;
    }

    .intro,
    .about,
    .contact {

        grid-template-columns: 1fr;

        gap: 60px;
    }

    .contact {

        padding-bottom: 100px;
    }

}


@media(max-width:650px) {

    .section {

        padding: 100px 6vw;
    }

    .hero {

        min-height: 100svh;
    }

    .hero-image {

        inset: 0;
    }

    .hero-content {

        padding:
            120px 20px 80px;
    }

    .hero-logo {

        width: 75vw;
    }

    .hero h1 {

        font-size: 49px;
    }

    .hero-text {

        font-size: 13px;
    }

    .services-grid {

        grid-template-columns: 1fr;
    }

    .service-card {

        min-height: 330px;
    }

    .service-symbol {

        font-size: 80px;
    }

    .gallery {

        grid-template-columns: 1fr;

        grid-auto-rows: 300px;
    }

    .gallery-item {

        grid-column: span 1 !important;

        grid-row: span 1 !important;
    }

    .portfolio-head {

        display: block;
    }

    .portfolio-description {

        margin-top: 25px;
    }

    .form-grid {

        grid-template-columns: 1fr;
    }

    .form-field.full {

        grid-column:
            span 1;
    }

    .booking {

        padding: 22px;
    }

    footer {

        flex-direction: column;

        gap: 12px;
    }

    .cursor-dot,
    .cursor-ring {

        display: none;
    }

}


/* =====================================================
   LANGUAGE MOBILE
===================================================== */

@media(max-width:500px) {

    .brand {

        font-size: 26px;
    }

    .language-menu {

        right: -45px;
    }

}


/* =====================================================
   REDUCED MOTION
===================================================== */

@media(prefers-reduced-motion: reduce) {

    *,
    *::before,
    *::after {

        animation-duration: .01ms !important;

        animation-iteration-count: 1 !important;

        scroll-behavior: auto !important;

        transition-duration: .01ms !important;
    }

}

</style>

</head>


<body>


<!-- =====================================================
     LOADER
===================================================== -->

<div class="loader" id="loader">

    <div class="loader-logo">
        NELLI
    </div>

    <div class="loader-line"></div>

</div>


<!-- =====================================================
     CURSOR
===================================================== -->

<div class="cursor-dot" id="cursorDot"></div>

<div class="cursor-ring" id="cursorRing"></div>


<!-- =====================================================
     NAVIGATION
===================================================== -->

<header class="nav" id="nav">

    <a
        href="#home"
        class="brand"
    >
        NELLI <span>photo</span>
    </a>


    <nav class="nav-links">

        <a href="#services"
           data-i18n="navServices">
            Зйомки
        </a>

        <a href="#portfolio"
           data-i18n="navPortfolio">
            Портфоліо
        </a>

        <a href="#about"
           data-i18n="navAbout">
            Про мене
        </a>

        <a href="#contact"
           data-i18n="navContact">
            Контакти
        </a>

    </nav>


    <div style="
        display:flex;
        align-items:center;
        gap:10px;
    ">


        <!-- LANGUAGE -->

        <div
            class="language"
            id="language"
        >

            <button
                class="language-button"
                id="languageButton"
            >

                <span id="currentFlag">
                    🇺🇦
                </span>

                <span id="currentLang">
                    UA
                </span>

                ▾

            </button>


            <div class="language-menu">


                <button
                    class="language-option"
                    data-lang="uk"
                >
                    🇺🇦
                    Українська
                </button>


                <button
                    class="language-option"
                    data-lang="cs"
                >
                    🇨🇿
                    Čeština
                </button>


                <button
                    class="language-option"
                    data-lang="en"
                >
                    🇬🇧
                    English
                </button>


                <button
                    class="language-option"
                    data-lang="ru"
                >
                    🇷🇺
                    Русский
                </button>


                <button
                    class="language-option"
                    data-lang="hy"
                >
                    🇦🇲
                    Հայերեն
                </button>


                <button
                    class="language-option"
                    data-lang="vi"
                >
                    🇻🇳
                    Tiếng Việt
                </button>


                <button
                    class="language-option"
                    data-lang="zh"
                >
                    🇨🇳
                    中文
                </button>


                <button
                    class="language-option"
                    data-lang="ja"
                >
                    🇯🇵
                    日本語
                </button>

            </div>

        </div>


        <button
            class="menu-button"
            id="menuButton"
        >
            ☰
        </button>

    </div>

</header>


<!-- =====================================================
     MOBILE MENU
===================================================== -->

<div
    class="mobile-menu"
    id="mobileMenu"
>

    <a
        href="#services"
        data-mobile-link
        data-i18n="navServices"
    >
        Зйомки
    </a>

    <a
        href="#portfolio"
        data-mobile-link
        data-i18n="navPortfolio"
    >
        Портфоліо
    </a>

    <a
        href="#about"
        data-mobile-link
        data-i18n="navAbout"
    >
        Про мене
    </a>

    <a
        href="#contact"
        data-mobile-link
        data-i18n="navContact"
    >
        Контакти
    </a>

</div>


<!-- =====================================================
     HERO
===================================================== -->

<section
    class="hero"
    id="home"
>


    <div class="hero-image">

        <!--
            ЗАМІНИ НА СВОЄ ФОТО

            hero.jpg
        -->

        <img
            src="hero.jpg"
            alt="Nelli Photography"
        >

    </div>


    <div class="hero-overlay"></div>


    <div class="hero-circle"></div>


    <div class="hero-content">


        <!--
            ЛОГОТИП

            Залиш назву файлу,
            якщо твій логотип має
            саме таку назву.
        -->

        <div class="hero-logo">

            <img
                src="e6e5c1df-9682-4b22-adb4-764d0fd31df0.png"
                alt="Nelli"
            >

        </div>


        <div
            class="eyebrow"
            data-i18n="heroEyebrow"
        >
            Фотограф у Празі
        </div>


        <h1>

            <span data-i18n="heroTitle1">
                Ваші моменти.
            </span>

            <br>

            <em data-i18n="heroTitle2">
                Моя історія в кадрі.
            </em>

        </h1>


        <p
            class="hero-text"
            data-i18n="heroText"
        >
            Весілля · Хрещення · Дні народження ·
            Сімейні та портретні зйомки · Студія ·
            Особливі події
        </p>


        <div class="hero-actions">

            <a
                href="#services"
                class="button primary"
                data-i18n="heroButton"
            >
                Обрати зйомку
            </a>

            <a
                href="#portfolio"
                class="button secondary"
                data-i18n="heroPortfolio"
            >
                Дивитися роботи
            </a>

        </div>

    </div>


    <div class="scroll">
        Scroll
    </div>

</section>


<!-- =====================================================
     INTRO
===================================================== -->

<section class="section intro reveal">


    <div>

        <div
            class="section-label"
            data-i18n="introLabel"
        >
            01 — Фотографія
        </div>

    </div>


    <div class="intro-copy">

        <h2 class="section-title">

            <span data-i18n="introTitle1">
                Не просто
            </span>

            <br>

            <em data-i18n="introTitle2">
                фотографії.
            </em>

        </h2>


        <p data-i18n="introText">

            Фотографія для мене — це спосіб
            залишити емоцію. Не постановка
            заради красивого кадру, а справжні
            моменти, до яких хочеться повертатися
            через роки.

        </p>


        <div
            class="intro-note"
            data-i18n="introQuote"
        >
            «Найцінніше — те, що неможливо
            повторити вдруге.»

        </div>

    </div>

</section>


<!-- =====================================================
     SERVICES
===================================================== -->

<section
    class="section services"
    id="services"
>


    <div class="services-intro reveal">

        <div>

            <div
                class="section-label"
                data-i18n="servicesLabel"
            >
                02 — Зйомки
            </div>


            <h2 class="section-title">

                <span data-i18n="servicesTitle1">
                    Ваша
                </span>

                <br>

                <em data-i18n="servicesTitle2">
                    історія.
                </em>

            </h2>

        </div>


        <p
            class="services-description"
            data-i18n="servicesDescription"
        >

            Оберіть подію або формат.
            Якщо вашого варіанту немає —
            просто напишіть мені.
            Ми придумаємо зйомку саме під вас.

        </p>

    </div>


    <div class="services-grid">


        <!-- 01 -->

        <a
            href="#contact"
            class="service-card reveal"
        >

            <span class="service-number">
                01
            </span>

            <div class="service-symbol">
                W
            </div>

            <div class="service-info">

                <h3 data-i18n="wedding">
                    Весілля
                </h3>

                <p data-i18n="weddingDesc">
                    Ваш день від першого
                    погляду до останнього танцю.
                </p>

            </div>

            <span class="service-arrow">
                ↗
            </span>

        </a>


        <!-- 02 -->

        <a
            href="#contact"
            class="service-card reveal"
        >

            <span class="service-number">
                02
            </span>

            <div class="service-symbol">
                C
            </div>

            <div class="service-info">

                <h3 data-i18n="christening">
                    Хрещення
                </h3>

                <p data-i18n="christeningDesc">
                    Один із найважливіших
                    днів вашої дитини.
                </p>

            </div>

            <span class="service-arrow">
                ↗
            </span>

        </a>


        <!-- 03 -->

        <a
            href="#contact"
            class="service-card reveal"
        >

            <span class="service-number">
                03
            </span>

            <div class="service-symbol">
                B
            </div>

            <div class="service-info">

                <h3 data-i18n="birthday">
                    День народження
                </h3>

                <p data-i18n="birthdayDesc">
                    Свято, емоції, люди
                    та моменти, які залишаться.
                </p>

            </div>

            <span class="service-arrow">
                ↗
            </span>

        </a>


        <!-- 04 -->

        <a
            href="#contact"
            class="service-card reveal"
        >

            <span class="service-number">
                04
            </span>

            <div class="service-symbol">
                F
            </div>

            <div class="service-info">

                <h3 data-i18n="family">
                    Сімейна
                </h3>

                <p data-i18n="familyDesc">
                    Теплі фотографії
                    вашої сім'ї.
                </p>

            </div>

            <span class="service-arrow">
                ↗
            </span>

        </a>


        <!-- 05 -->

        <a
            href="#contact"
            class="service-card reveal"
        >

            <span class="service-number">
                05
            </span>

            <div class="service-symbol">
                P
            </div>

            <div class="service-info">

                <h3 data-i18n="portrait">
                    Портрет
                </h3>

                <p data-i18n="portraitDesc">
                    Характер, стиль
                    і ваша особистість.
                </p>

            </div>

            <span class="service-arrow">
                ↗
            </span>

        </a>


        <!-- 06 -->

        <a
            href="#contact"
            class="service-card reveal"
        >

            <span class="service-number">
                06
            </span>

            <div class="service-symbol">
                S
            </div>

            <div class="service-info">

                <h3 data-i18n="studio">
                    Студія
                </h3>

                <p data-i18n="studioDesc">
                    Світло, стиль
                    і контроль кожної деталі.
                </p>

            </div>

            <span class="service-arrow">
                ↗
            </span>

        </a>


        <!-- 07 -->

        <a
            href="#contact"
            class="service-card reveal"
        >

            <span class="service-number">
                07
            </span>

            <div class="service-symbol">
                M
            </div>

            <div class="service-info">

                <h3 data-i18n="maternity">
                    Вагітність
                </h3>

                <p data-i18n="maternityDesc">
                    Ніжна історія
                    нового життя.
                </p>

            </div>

            <span class="service-arrow">
                ↗
            </span>

        </a>


        <!-- 08 -->

        <a
            href="#contact"
            class="service-card reveal"
        >

            <span class="service-number">
                08
            </span>

            <div class="service-symbol">
                K
            </div>

            <div class="service-info">

                <h3 data-i18n="children">
                    Дитяча
                </h3>

                <p data-i18n="childrenDesc">
                    Справжні емоції
                    та безтурботне дитинство.
                </p>

            </div>

            <span class="service-arrow">
                ↗
            </span>

        </a>


        <!-- 09 -->

        <a
            href="#contact"
            class="service-card reveal"
        >

            <span class="service-number">
                09
            </span>

            <div class="service-symbol">
                L
            </div>

            <div class="service-info">

                <h3>
                    Love Story
                </h3>

                <p data-i18n="loveDesc">
                    Ваша історія
                    про двох.
                </p>

            </div>

            <span class="service-arrow">
                ↗
            </span>

        </a>


        <!-- 10 -->

        <a
            href="#contact"
            class="service-card reveal"
        >

            <span class="service-number">
                10
            </span>

            <div class="service-symbol">
                +
            </div>

            <div class="service-info">

                <h3 data-i18n="other">
                    Інша подія
                </h3>

                <p data-i18n="otherDesc">
                    Маєте іншу ідею?
                    Розкажіть мені.
                </p>

            </div>

            <span class="service-arrow">
                ↗
            </span>

        </a>


    </div>

</section>


<!-- =====================================================
     MARQUEE
===================================================== -->

<div class="marquee">

    <div class="marquee-track">

        <span>
            your story in frames
        </span>

        <i>✦</i>

        <span>
            moments worth keeping
        </span>

        <i>✦</i>

        <span>
            your story in frames
        </span>

        <i>✦</i>

        <span>
            moments worth keeping
        </span>

        <i>✦</i>

        <span>
            your story in frames
        </span>

        <i>✦</i>

        <span>
            moments worth keeping
        </span>

    </div>

</div>


<!-- =====================================================
     PORTFOLIO
===================================================== -->

<section
    class="section portfolio"
    id="portfolio"
>


    <div class="portfolio-head reveal">

        <div>

            <div
                class="section-label"
                data-i18n="portfolioLabel"
            >
                03 — Портфоліо
            </div>


            <h2 class="section-title">

                <span data-i18n="portfolioTitle1">
                    Кадри,
                </span>

                <br>

                <em data-i18n="portfolioTitle2">
                    які залишаються.
                </em>

            </h2>

        </div>


        <p
            class="portfolio-description"
            data-i18n="portfolioDescription"
        >

            Тут будуть ваші найкращі
            фотографії. Просто замініть
            файли photo-1.jpg, photo-2.jpg
            та інші на власні.

        </p>

    </div>


    <div class="gallery">


        <div class="gallery-item g1">

            <img
                src="photo-1.jpg"
                alt="Wedding photography"
            >

            <span
                class="gallery-caption"
                data-i18n="galleryWedding"
            >
                Wedding
            </span>

        </div>


        <div class="gallery-item g2">

            <img
                src="photo-2.jpg"
                alt="Portrait photography"
            >

            <span
                class="gallery-caption"
                data-i18n="galleryPortrait"
            >
                Portrait
            </span>

        </div>


        <div class="gallery-item g3">

            <img
                src="photo-3.jpg"
                alt="Family photography"
            >

            <span
                class="gallery-caption"
                data-i18n="galleryFamily"
            >
                Family
            </span>

        </div>


        <div class="gallery-item g4">

            <img
                src="photo-4.jpg"
                alt="Studio photography"
            >

            <span
                class="gallery-caption"
                data-i18n="galleryStudio"
            >
                Studio
            </span>

        </div>


        <div class="gallery-item g5">

            <img
                src="photo-5.jpg"
                alt="Event photography"
            >

            <span
                class="gallery-caption"
                data-i18n="galleryEvent"
            >
                Event
            </span>

        </div>


    </div>

</section>


<!-- =====================================================
     ABOUT
===================================================== -->

<section
    class="section about"
    id="about"
>


    <div class="about-photo reveal">

        <img
            src="about.jpg"
            alt="Nelli photographer"
        >

    </div>


    <div class="about-copy reveal">

        <div
            class="section-label"
            data-i18n="aboutLabel"
        >
            04 — Про мене
        </div>


        <h2 class="section-title">

            <span data-i18n="aboutTitle1">
                Неллі
            </span>

            <br>

            <em data-i18n="aboutTitle2">
                за кадром.
            </em>

        </h2>


        <p
            class="about-text"
            data-i18n="aboutText"
        >

            Тут буде особиста історія
            Неллі — як вона прийшла
            у фотографію, що любить
            знімати та чому обрала
            саме цей стиль.

        </p>


        <div
            class="quote"
            data-i18n="quote"
        >

            «Найкращі фотографії —
            це ті, де ви впізнаєте себе.»

        </div>

    </div>

</section>


<!-- =====================================================
     CONTACT
===================================================== -->

<section
    class="section contact"
    id="contact"
>


    <div class="reveal">

        <div
            class="section-label"
            data-i18n="contactLabel"
        >
            05 — Запис
        </div>


        <h2 class="section-title">

            <span data-i18n="contactTitle1">
                Давайте
            </span>

            <br>

            <em data-i18n="contactTitle2">
                створимо.
            </em>

        </h2>


        <p
            class="contact-description"
            data-i18n="contactDescription"
        >

            Розкажіть про вашу подію,
            дату та бажаний формат.
            Неллі зв'яжеться з вами
            та допоможе все організувати.

        </p>


        <div class="contact-buttons">

            <a
                href="https://www.instagram.com/viii.hairstylist/"
                target="_blank"
                rel="noopener"
                class="contact-button"
            >
                Instagram
            </a>

            <a
                href="mailto:YOUR_EMAIL@example.com"
                class="contact-button"
            >
                Email
            </a>

            <a
                href="tel:+420000000000"
                class="contact-button"
            >
                Phone
            </a>

        </div>

    </div>


    <div class="reveal">


        <div class="booking">

            <h3 data-i18n="formTitle">
                Розкажіть про зйомку
            </h3>


            <form
                action="https://formspree.io/f/xnpavyge"
                method="POST"
            >


                <div class="form-grid">


                    <div class="form-field">

                        <label data-i18n="name">
                            Ваше ім'я
                        </label>

                        <input
                            type="text"
                            name="name"
                            required
                            placeholder="Ваше ім'я"
                        >

                    </div>


                    <div class="form-field">

                        <label data-i18n="email">
                            Email
                        </label>

                        <input
                            type="email"
                            name="email"
                            required
                            placeholder="email@example.com"
                        >

                    </div>


                    <div class="form-field">

                        <label data-i18n="phone">
                            Телефон
                        </label>

                        <input
                            type="tel"
                            name="phone"
                            placeholder="+420..."
                        >

                    </div>


                    <div class="form-field">

                        <label data-i18n="date">
                            Дата
                        </label>

                        <input
                            type="date"
                            name="date"
                        >

                    </div>


                    <div class="form-field full">

                        <label data-i18n="type">
                            Тип зйомки
                        </label>


                        <select
                            name="session"
                            required
                        >

                            <option
                                value=""
                                data-i18n="choose"
                            >
                                Оберіть тип
                            </option>

                            <option
                                value="Wedding"
                                data-i18n="wedding"
                            >
                                Весілля
                            </option>

                            <option
                                value="Christening"
                                data-i18n="christening"
                            >
                                Хрещення
                            </option>

                            <option
                                value="Birthday"
                                data-i18n="birthday"
                            >
                                День народження
                            </option>

                            <option
                                value="Family"
                                data-i18n="family"
                            >
                                Сімейна
                            </option>

                            <option
                                value="Portrait"
                                data-i18n="portrait"
                            >
                                Портрет
                            </option>

                            <option
                                value="Studio"
                                data-i18n="studio"
                            >
                                Студія
                            </option>

                            <option
                                value="Maternity"
                                data-i18n="maternity"
                            >
                                Вагітність
                            </option>

                            <option
                                value="Children"
                                data-i18n="children"
                            >
                                Дитяча
                            </option>

                            <option
                                value="Love Story"
                            >
                                Love Story
                            </option>

                            <option
                                value="Other"
                                data-i18n="other"
                            >
                                Інша подія
                            </option>

                        </select>

                    </div>


                    <div class="form-field full">

                        <label data-i18n="message">
                            Розкажіть про вашу подію
                        </label>

                        <textarea
                            name="message"
                            placeholder="Дата, місце, кількість людей, побажання..."
                        ></textarea>

                    </div>

                </div>


                <input
                    type="hidden"
                    name="_subject"
                    value="Нова заявка з сайту NELLI"
                >


                <input
                    type="hidden"
                    name="language"
                    id="formLanguage"
                    value="uk"
                >


                <button
                    type="submit"
                    class="form-submit"
                    data-i18n="send"
                >
                    Надіслати заявку →
                </button>


            </form>

        </div>

    </div>

</section>


<!-- =====================================================
     FOOTER
===================================================== -->

<footer>

    <span>
        © 2026 NELLI PHOTOGRAPHY
    </span>

    <span data-i18n="footer">
        Фотограф у Празі
    </span>

</footer>


<script>

/* =====================================================
   LOADER
===================================================== */

window.addEventListener(
    "load",
    () => {

        setTimeout(
            () => {

                document
                    .getElementById("loader")
                    .classList
                    .add("hidden");

            },
            900
        );

    }
);


/* =====================================================
   NAV SCROLL
===================================================== */

const nav =
    document.getElementById("nav");

window.addEventListener(
    "scroll",
    () => {

        if(window.scrollY > 50) {

            nav.classList.add("scrolled");

        } else {

            nav.classList.remove("scrolled");

        }

    }
);


/* =====================================================
   REVEAL ANIMATION
===================================================== */

const revealObserver =
    new IntersectionObserver(
        entries => {

            entries.forEach(
                entry => {

                    if(
                        entry.isIntersecting
                    ) {

                        entry.target
                            .classList
                            .add("visible");

                        revealObserver
                            .unobserve(entry.target);

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
    .forEach(
        element => {

            revealObserver.observe(element);

        }
    );


/* =====================================================
   CURSOR
===================================================== */

const cursorDot =
    document.getElementById("cursorDot");

const cursorRing =
    document.getElementById("cursorRing");

if(
    window.matchMedia(
        "(pointer:fine)"
    ).matches
) {

    let mouseX = 0;
    let mouseY = 0;

    let ringX = 0;
    let ringY = 0;


    window.addEventListener(
        "mousemove",
        event => {

            mouseX = event.clientX;
            mouseY = event.clientY;

            cursorDot.style.left =
                mouseX + "px";

            cursorDot.style.top =
                mouseY + "px";

        }
    );


    function animateCursor() {

        ringX +=
            (mouseX - ringX) * .15;

        ringY +=
            (mouseY - ringY) * .15;

        cursorRing.style.left =
            ringX + "px";

        cursorRing.style.top =
            ringY + "px";

        requestAnimationFrame(
            animateCursor
        );

    }

    animateCursor();


    document
        .querySelectorAll("a,button")
        .forEach(
            element => {

                element.addEventListener(
                    "mouseenter",
                    () => {

                        cursorRing.style.width =
                            "55px";

                        cursorRing.style.height =
                            "55px";

                    }
                );


                element.addEventListener(
                    "mouseleave",
                    () => {

                        cursorRing.style.width =
                            "35px";

                        cursorRing.style.height =
                            "35px";

                    }
                );

            }
        );

}


/* =====================================================
   LANGUAGE SYSTEM
===================================================== */

const translations = {


    uk: {

        flag: "🇺🇦",
        short: "UA",

        navServices: "Зйомки",
        navPortfolio: "Портфоліо",
        navAbout: "Про мене",
        navContact: "Контакти",

        heroEyebrow: "Фотограф у Празі",

        heroTitle1: "Ваші моменти.",
        heroTitle2: "Моя історія в кадрі.",

        heroText:
            "Весілля · Хрещення · Дні народження · Сімейні та портретні зйомки · Студія · Особливі події",

        heroButton:
            "Обрати зйомку",

        heroPortfolio:
            "Дивитися роботи",

        introLabel:
            "01 — Фотографія",

        introTitle1:
            "Не просто",

        introTitle2:
            "фотографії.",

        introText:
            "Фотографія для мене — це спосіб залишити емоцію. Не постановка заради красивого кадру, а справжні моменти, до яких хочеться повертатися через роки.",

        introQuote:
            "«Найцінніше — те, що неможливо повторити вдруге.»",

        servicesLabel:
            "02 — Зйомки",

        servicesTitle1:
            "Ваша",

        servicesTitle2:
            "історія.",

        servicesDescription:
            "Оберіть подію або формат. Якщо вашого варіанту немає — просто напишіть мені. Ми придумаємо зйомку саме під вас.",

        wedding:
            "Весілля",

        weddingDesc:
            "Ваш день від першого погляду до останнього танцю.",

        christening:
            "Хрещення",

        christeningDesc:
            "Один із найважливіших днів вашої дитини.",

        birthday:
            "День народження",

        birthdayDesc:
            "Свято, емоції, люди та моменти, які залишаться.",

        family:
            "Сімейна",

        familyDesc:
            "Теплі фотографії вашої сім'ї.",

        portrait:
            "Портрет",

        portraitDesc:
            "Характер, стиль і ваша особистість.",

        studio:
            "Студія",

        studioDesc:
            "Світло, стиль і контроль кожної деталі.",

        maternity:
            "Вагітність",

        maternityDesc:
            "Ніжна історія нового життя.",

        children:
            "Дитяча",

        childrenDesc:
            "Справжні емоції та безтурботне дитинство.",

        other:
            "Інша подія",

        otherDesc:
            "Маєте іншу ідею? Розкажіть мені.",

        loveDesc:
            "Ваша історія про двох.",

        portfolioLabel:
            "03 — Портфоліо",

        portfolioTitle1:
            "Кадри,",

        portfolioTitle2:
            "які залишаються.",

        portfolioDescription:
            "Тут будуть ваші найкращі фотографії. Просто замініть файли photo-1.jpg, photo-2.jpg та інші на власні.",

        galleryWedding:
            "Wedding",

        galleryPortrait:
            "Portrait",

        galleryFamily:
            "Family",

        galleryStudio:
            "Studio",

        galleryEvent:
            "Event",

        aboutLabel:
            "04 — Про мене",

        aboutTitle1:
            "Неллі",

        aboutTitle2:
            "за кадром.",

        aboutText:
            "Тут буде особиста історія Неллі — як вона прийшла у фотографію, що любить знімати та чому обрала саме цей стиль.",

        quote:
            "«Найкращі фотографії — це ті, де ви впізнаєте себе.»",

        contactLabel:
            "05 — Запис",

        contactTitle1:
            "Давайте",

        contactTitle2:
            "створимо.",

        contactDescription:
            "Розкажіть про вашу подію, дату та бажаний формат. Неллі зв'яжеться з вами та допоможе все організувати.",

        formTitle:
            "Розкажіть про зйомку",

        name:
            "Ваше ім'я",

        email:
            "Email",

        phone:
            "Телефон",

        date:
            "Дата",

        type:
            "Тип зйомки",

        choose:
            "Оберіть тип",

        message:
            "Розкажіть про вашу подію",

        send:
            "Надіслати заявку →",

        footer:
            "Фотограф у Празі"

    },


    cs: {

        flag: "🇨🇿",
        short: "CZ",

        navServices: "Focení",
        navPortfolio: "Portfolio",
        navAbout: "O mně",
        navContact: "Kontakt",

        heroEyebrow:
            "Fotografka v Praze",

        heroTitle1:
            "Vaše okamžiky.",

        heroTitle2:
            "Můj příběh v obraze.",

        heroText:
            "Svatby · Křtiny · Narozeniny · Rodinné a portrétní focení · Studio · Speciální události",

        heroButton:
            "Vybrat focení",

        heroPortfolio:
            "Prohlédnout portfolio",

        introLabel:
            "01 — Fotografie",

        introTitle1:
            "Nejen",

        introTitle2:
            "fotografie.",

        introText:
            "Fotografie je pro mě způsob, jak zachytit emoci. Ne dokonalá póza, ale skutečné okamžiky, ke kterým se budete chtít vracet.",

        introQuote:
            "„To nejcennější nelze zopakovat.“",

        servicesLabel:
            "02 — Focení",

        servicesTitle1:
            "Váš",

        servicesTitle2:
            "příběh.",

        servicesDescription:
            "Vyberte si událost nebo typ focení. Pokud zde svou představu nevidíte, napište mi.",

        wedding:
            "Svatba",

        weddingDesc:
            "Váš den od prvního pohledu až po poslední tanec.",

        christening:
            "Křtiny",

        christeningDesc:
            "Jeden z nejdůležitějších dnů vašeho dítěte.",

        birthday:
            "Narozeniny",

        birthdayDesc:
            "Oslava, emoce, lidé a okamžiky, které zůstanou.",

        family:
            "Rodinné",

        familyDesc:
            "Přirozené a teplé fotografie vaší rodiny.",

        portrait:
            "Portrét",

        portraitDesc:
            "Charakter, styl a vaše osobnost.",

        studio:
            "Studio",

        studioDesc:
            "Světlo, styl a kontrola každého detailu.",

        maternity:
            "Těhotenské",

        maternityDesc:
            "Jemný příběh nového života.",

        children:
            "Dětské",

        childrenDesc:
            "Skutečné emoce a bezstarostné dětství.",

        other:
            "Jiná událost",

        otherDesc:
            "Máte jiný nápad? Napište mi.",

        loveDesc:
            "Váš příběh ve dvou.",

        portfolioLabel:
            "03 — Portfolio",

        portfolioTitle1:
            "Okamžiky,",

        portfolioTitle2:
            "které zůstávají.",

        portfolioDescription:
            "Zde budou vaše nejlepší fotografie. Jednoduše nahraďte soubory vlastními fotografiemi.",

        galleryWedding:
            "Wedding",

        galleryPortrait:
            "Portrait",

        galleryFamily:
            "Family",

        galleryStudio:
            "Studio",

        galleryEvent:
            "Event",

        aboutLabel:
            "04 — O mně",

        aboutTitle1:
            "Nelli",

        aboutTitle2:
            "za objektivem.",

        aboutText:
            "Zde bude osobní příběh Nelli — jak se dostala k fotografii a co ji na focení baví.",

        quote:
            "„Nejlepší fotografie jsou ty, ve kterých poznáte sami sebe.“",

        contactLabel:
            "05 — Rezervace",

        contactTitle1:
            "Pojďme",

        contactTitle2:
            "tvořit.",

        contactDescription:
            "Napište mi o vaší události, datu a představě. Ozvu se vám a pomůžu vše naplánovat.",

        formTitle:
            "Řekněte mi o focení",

        name:
            "Vaše jméno",

        email:
            "Email",

        phone:
            "Telefon",

        date:
            "Datum",

        type:
            "Typ focení",

        choose:
            "Vyberte typ",

        message:
            "Řekněte mi více",

        send:
            "Odeslat poptávku →",

        footer:
            "Fotografka v Praze"

    },


    en: {

        flag: "🇬🇧",
        short: "EN",

        navServices: "Sessions",
        navPortfolio: "Portfolio",
        navAbout: "About",
        navContact: "Contact",

        heroEyebrow:
            "Photographer in Prague",

        heroTitle1:
            "Your moments.",

        heroTitle2:
            "My story in frames.",

        heroText:
            "Weddings · Christenings · Birthdays · Family & Portraits · Studio · Special Events",

        heroButton:
            "Choose a session",

        heroPortfolio:
            "View portfolio",

        introLabel:
            "01 — Photography",

        introTitle1:
            "More than",

        introTitle2:
            "photographs.",

        introText:
            "Photography is a way of preserving emotion. Not perfect poses, but real moments you will want to return to years from now.",

        introQuote:
            "\"The most precious moments cannot be repeated.\"",

        servicesLabel:
            "02 — Sessions",

        servicesTitle1:
            "Your",

        servicesTitle2:
            "story.",

        servicesDescription:
            "Choose an event or photography style. If you don't see what you need, simply contact me.",

        wedding:
            "Wedding",

        weddingDesc:
            "Your day from the first look to the last dance.",

        christening:
            "Christening",

        christeningDesc:
            "One of the most important days for your child.",

        birthday:
            "Birthday",

        birthdayDesc:
            "Celebration, emotions, people and memories.",

        family:
            "Family",

        familyDesc:
            "Warm and natural family photography.",

        portrait:
            "Portrait",

        portraitDesc:
            "Character, style and personality.",

        studio:
            "Studio",

        studioDesc:
            "Light, style and control of every detail.",

        maternity:
            "Maternity",

        maternityDesc:
            "A gentle story of new life.",

        children:
            "Children",

        childrenDesc:
            "Real emotions and childhood.",

        other:
            "Other event",

        otherDesc:
            "Have another idea? Tell me about it.",

        loveDesc:
            "Your story of two.",

        portfolioLabel:
            "03 — Portfolio",

        portfolioTitle1:
            "Frames",

        portfolioTitle2:
            "that remain.",

        portfolioDescription:
            "This is where your best photographs will appear. Simply replace the image files with your own.",

        galleryWedding:
            "Wedding",

        galleryPortrait:
            "Portrait",

        galleryFamily:
            "Family",

        galleryStudio:
            "Studio",

        galleryEvent:
            "Event",

        aboutLabel:
            "04 — About",

        aboutTitle1:
            "Nelli",

        aboutTitle2:
            "behind the camera.",

        aboutText:
            "This section will tell Nelli's personal story — how she discovered photography and what she loves about creating images.",

        quote:
            "\"The best photographs are the ones where you recognize yourself.\"",

        contactLabel:
            "05 — Booking",

        contactTitle1:
            "Let's",

        contactTitle2:
            "create.",

        contactDescription:
            "Tell me about your event, date and idea. I will get back to you and help organize everything.",

        formTitle:
            "Tell me about your session",

        name:
            "Your name",

        email:
            "Email",

        phone:
            "Phone",

        date:
            "Date",

        type:
            "Session type",

        choose:
            "Choose a type",

        message:
            "Tell me about your event",

        send:
            "Send request →",

        footer:
            "Photographer in Prague"

    },


    ru: {

        flag: "🇷🇺",
        short: "RU",

        navServices: "Съёмки",
        navPortfolio: "Портфолио",
        navAbout: "Обо мне",
        navContact: "Контакты",

        heroEyebrow:
            "Фотограф в Праге",

        heroTitle1:
            "Ваши моменты.",

        heroTitle2:
            "Моя история в кадре.",

        heroText:
            "Свадьбы · Крещения · Дни рождения · Семейные и портретные съёмки · Студия · События",

        heroButton:
            "Выбрать съёмку",

        heroPortfolio:
            "Смотреть работы",

        introLabel:
            "01 — Фотография",

        introTitle1:
            "Не просто",

        introTitle2:
            "фотографии.",

        introText:
            "Фотография для меня — способ сохранить эмоцию. Не идеальная поза, а настоящие моменты, к которым хочется возвращаться.",

        introQuote:
            "«Самое ценное невозможно повторить.»",

        servicesLabel:
            "02 — Съёмки",

        servicesTitle1:
            "Ваша",

        servicesTitle2:
            "история.",

        servicesDescription:
            "Выберите событие или формат. Если вашего варианта нет — просто напишите мне.",

        wedding:
            "Свадьба",

        weddingDesc:
            "Ваш день от первого взгляда до последнего танца.",

        christening:
            "Крещение",

        christeningDesc:
            "Один из самых важных дней вашего ребёнка.",

        birthday:
            "День рождения",

        birthdayDesc:
            "Праздник, эмоции, люди и воспоминания.",

        family:
            "Семейная",

        familyDesc:
            "Тёплые и настоящие фотографии вашей семьи.",

        portrait:
            "Портрет",

        portraitDesc:
            "Характер, стиль и индивидуальность.",

        studio:
            "Студия",

        studioDesc:
            "Свет, стиль и контроль каждой детали.",

        maternity:
            "Беременность",

        maternityDesc:
            "Нежная история новой жизни.",

        children:
            "Детская",

        childrenDesc:
            "Настоящие эмоции и детство.",

        other:
            "Другое событие",

        otherDesc:
            "Есть другая идея? Расскажите мне.",

        loveDesc:
            "Ваша история вдвоём.",

        portfolioLabel:
            "03 — Портфолио",

        portfolioTitle1:
            "Кадры,",

        portfolioTitle2:
            "которые остаются.",

        portfolioDescription:
            "Здесь будут ваши лучшие фотографии. Просто замените файлы своими фотографиями.",

        galleryWedding:
            "Wedding",

        galleryPortrait:
            "Portrait",

        galleryFamily:
            "Family",

        galleryStudio:
            "Studio",

        galleryEvent:
            "Event",

        aboutLabel:
            "04 — Обо мне",

        aboutTitle1:
            "Нелли",

        aboutTitle2:
            "за кадром.",

        aboutText:
            "Здесь будет личная история Нелли — как она пришла в фотографию и что любит снимать.",

        quote:
            "«Лучшие фотографии — те, где вы узнаёте себя.»",

        contactLabel:
            "05 — Запись",

        contactTitle1:
            "Давайте",

        contactTitle2:
            "создадим.",

        contactDescription:
            "Расскажите о вашем событии, дате и желаемом формате. Нелли свяжется с вами.",

        formTitle:
            "Расскажите о съёмке",

        name:
            "Ваше имя",

        email:
            "Email",

        phone:
            "Телефон",

        date:
            "Дата",

        type:
            "Тип съёмки",

        choose:
            "Выберите тип",

        message:
            "Расскажите о событии",

        send:
            "Отправить заявку →",

        footer:
            "Фотограф в Праге"

    },


    hy: {

        flag: "🇦🇲",
        short: "HY",

        navServices: "Նկարահանումներ",
        navPortfolio: "Պորտֆոլիո",
        navAbout: "Իմ մասին",
        navContact: "Կապ",

        heroEyebrow:
            "Լուսանկարիչ Պրահայում",

        heroTitle1:
            "Ձեր պահերը։",

        heroTitle2:
            "Իմ պատմությունը կադրում։",

        heroText:
            "Հարսանիքներ · Մկրտություններ · Ծննդյան օրեր · Ընտանեկան և ստուդիական նկարահանումներ",

        heroButton:
            "Ընտրել նկարահանում",

        heroPortfolio:
            "Դիտել աշխատանքները",

        introLabel:
            "01 — Լուսանկարչություն",

        introTitle1:
            "Ոչ միայն",

        introTitle2:
            "լուսանկարներ։",

        introText:
            "Լուսանկարչությունն ինձ համար զգացմունք պահելու միջոց է։",

        introQuote:
            "«Ամենաթանկ պահերը հնարավոր չէ կրկնել»",

        servicesLabel:
            "02 — Նկարահանումներ",

        servicesTitle1:
            "Ձեր",

        servicesTitle2:
            "պատմությունը։",

        servicesDescription:
            "Ընտրեք միջոցառումը կամ նկարահանման տեսակը։",

        wedding:
            "Հարսանիք",

        weddingDesc:
            "Ձեր օրը առաջին հայացքից մինչև վերջին պարը։",

        christening:
            "Մկրտություն",

        christeningDesc:
            "Ձեր երեխայի կարևոր օրը։",

        birthday:
            "Ծննդյան օր",

        birthdayDesc:
            "Տոն, զգացմունքներ և հիշողություններ։",

        family:
            "Ընտանեկան",

        familyDesc:
            "Ջերմ ընտանեկան լուսանկարներ։",

        portrait:
            "Պորտրետ",

        portraitDesc:
            "Ձեր ոճը և անհատականությունը։",

        studio:
            "Ստուդիա",

        studioDesc:
            "Լույս, ոճ և մանրուքների վերահսկում։",

        maternity:
            "Հղիություն",

        maternityDesc:
            "Նոր կյանքի նուրբ պատմություն։",

        children:
            "Երեխաներ",

        childrenDesc:
            "Իրական զգացմունքներ և մանկություն։",

        other:
            "Այլ միջոցառում",

        otherDesc:
            "Ունե՞ք այլ գաղափար։ Գրեք ինձ։",

        loveDesc:
            "Ձեր երկուսի պատմությունը։",

        portfolioLabel:
            "03 — Պորտֆոլիո",

        portfolioTitle1:
            "Կադրեր,",

        portfolioTitle2:
            "որոնք մնում են։",

        portfolioDescription:
            "Այստեղ կլինեն ձեր լավագույն լուսանկարները։",

        galleryWedding:
            "Wedding",

        galleryPortrait:
            "Portrait",

        galleryFamily:
            "Family",

        galleryStudio:
            "Studio",

        galleryEvent:
            "Event",

        aboutLabel:
            "04 — Իմ մասին",

        aboutTitle1:
            "Նելլի",

        aboutTitle2:
            "տեսախցիկի հետևում։",

        aboutText:
            "Այստեղ կլինի Նելլիի անձնական պատմությունը։",

        quote:
            "«Լավագույն լուսանկարներն այն են, որտեղ դուք ճանաչում եք ինքներդ ձեզ»։",

        contactLabel:
            "05 — Ամրագրում",

        contactTitle1:
            "Եկեք",

        contactTitle2:
            "ստեղծենք։",

        contactDescription:
            "Պատմեք ձեր միջոցառման և ցանկությունների մասին։",

        formTitle:
            "Պատմեք նկարահանման մասին",

        name:
            "Ձեր անունը",

        email:
            "Email",

        phone:
            "Հեռախոս",

        date:
            "Ամսաթիվ",

        type:
            "Նկարահանման տեսակ",

        choose:
            "Ընտրեք տեսակը",

        message:
            "Պատմեք միջոցառման մասին",

        send:
            "Ուղարկել →",

        footer:
            "Լուսանկարիչ Պրահայում"

    },


    vi: {

        flag: "🇻🇳",
        short: "VI",

        navServices: "Dịch vụ",
        navPortfolio: "Portfolio",
        navAbout: "Giới thiệu",
        navContact: "Liên hệ",

        heroEyebrow:
            "Nhiếp ảnh gia tại Prague",

        heroTitle1:
            "Khoảnh khắc của bạn.",

        heroTitle2:
            "Câu chuyện trong từng khung hình.",

        heroText:
            "Đám cưới · Lễ rửa tội · Sinh nhật · Gia đình · Chân dung · Studio",

        heroButton:
            "Chọn buổi chụp",

        heroPortfolio:
            "Xem portfolio",

        introLabel:
            "01 — Nhiếp ảnh",

        introTitle1:
            "Không chỉ là",

        introTitle2:
            "những bức ảnh.",

        introText:
            "Nhiếp ảnh là cách lưu giữ cảm xúc và những khoảnh khắc thật.",

        introQuote:
            "“Những khoảnh khắc quý giá nhất không thể lặp lại.”",

        servicesLabel:
            "02 — Buổi chụp",

        servicesTitle1:
            "Câu",

        servicesTitle2:
            "chuyện của bạn.",

        servicesDescription:
            "Chọn loại sự kiện hoặc phong cách chụp phù hợp với bạn.",

        wedding:
            "Đám cưới",

        weddingDesc:
            "Ngày đặc biệt của bạn từ đầu đến cuối.",

        christening:
            "Lễ rửa tội",

        christeningDesc:
            "Một ngày quan trọng của gia đình.",

        birthday:
            "Sinh nhật",

        birthdayDesc:
            "Niềm vui, cảm xúc và kỷ niệm.",

        family:
            "Gia đình",

        familyDesc:
            "Những khoảnh khắc ấm áp bên gia đình.",

        portrait:
            "Chân dung",

        portraitDesc:
            "Phong cách và cá tính của bạn.",

        studio:
            "Studio",

        studioDesc:
            "Ánh sáng, phong cách và từng chi tiết.",

        maternity:
            "Thai kỳ",

        maternityDesc:
            "Câu chuyện nhẹ nhàng về một sự sống mới.",

        children:
            "Trẻ em",

        childrenDesc:
            "Cảm xúc thật và tuổi thơ.",

        other:
            "Sự kiện khác",

        otherDesc:
            "Có ý tưởng khác? Hãy nói với tôi.",

        loveDesc:
            "Câu chuyện của hai người.",

        portfolioLabel:
            "03 — Portfolio",

        portfolioTitle1:
            "Những khung hình",

        portfolioTitle2:
            "còn mãi.",

        portfolioDescription:
            "Đây là nơi hiển thị những bức ảnh đẹp nhất của bạn.",

        galleryWedding:
            "Wedding",

        galleryPortrait:
            "Portrait",

        galleryFamily:
            "Family",

        galleryStudio:
            "Studio",

        galleryEvent:
            "Event",

        aboutLabel:
            "04 — Giới thiệu",

        aboutTitle1:
            "Nelli",

        aboutTitle2:
            "phía sau máy ảnh.",

        aboutText:
            "Câu chuyện cá nhân của Nelli và hành trình đến với nhiếp ảnh.",

        quote:
            "“Những bức ảnh đẹp nhất là nơi bạn nhận ra chính mình.”",

        contactLabel:
            "05 — Đặt lịch",

        contactTitle1:
            "Hãy",

        contactTitle2:
            "cùng tạo nên.",

        contactDescription:
            "Hãy kể cho tôi về sự kiện và mong muốn của bạn.",

        formTitle:
            "Thông tin buổi chụp",

        name:
            "Tên của bạn",

        email:
            "Email",

        phone:
            "Điện thoại",

        date:
            "Ngày",

        type:
            "Loại chụp",

        choose:
            "Chọn loại",

        message:
            "Thông tin sự kiện",

        send:
            "Gửi yêu cầu →",

        footer:
            "Nhiếp ảnh gia tại Prague"

    },


    zh: {

        flag: "🇨🇳",
        short: "中文",

        navServices: "摄影服务",
        navPortfolio: "作品集",
        navAbout: "关于我",
        navContact: "联系",

        heroEyebrow:
            "布拉格摄影师",

        heroTitle1:
            "记录你的瞬间。",

        heroTitle2:
            "用镜头讲述故事。",

        heroText:
            "婚礼 · 洗礼 · 生日 · 家庭 · 人像 · 摄影棚 · 特别活动",

        heroButton:
            "选择摄影",

        heroPortfolio:
            "查看作品",

        introLabel:
            "01 — 摄影",

        introTitle1:
            "不只是",

        introTitle2:
            "照片。",

        introText:
            "摄影是保存情感的方式，让真实的瞬间成为可以再次回忆的记忆。",

        introQuote:
            "“最珍贵的瞬间无法重来。”",

        servicesLabel:
            "02 — 摄影服务",

        servicesTitle1:
            "你的",

        servicesTitle2:
            "故事。",

        servicesDescription:
            "选择适合你的活动或摄影类型。",

        wedding:
            "婚礼",

        weddingDesc:
            "记录婚礼当天每一个重要瞬间。",

        christening:
            "洗礼",

        christeningDesc:
            "记录孩子的重要时刻。",

        birthday:
            "生日",

        birthdayDesc:
            "欢乐、情感和珍贵回忆。",

        family:
            "家庭",

        familyDesc:
            "温暖自然的家庭摄影。",

        portrait:
            "人像",

        portraitDesc:
            "展现你的风格和个性。",

        studio:
            "摄影棚",

        studioDesc:
            "灯光、风格和每一个细节。",

        maternity:
            "孕妇",

        maternityDesc:
            "记录新生命的温柔故事。",

        children:
            "儿童",

        childrenDesc:
            "真实的情感和童年。",

        other:
            "其他活动",

        otherDesc:
            "有其他想法？告诉我。",

        loveDesc:
            "属于两个人的故事。",

        portfolioLabel:
            "03 — 作品集",

        portfolioTitle1:
            "留下的",

        portfolioTitle2:
            "每一帧。",

        portfolioDescription:
            "这里将展示你最喜欢的摄影作品。",

        galleryWedding:
            "Wedding",

        galleryPortrait:
            "Portrait",

        galleryFamily:
            "Family",

        galleryStudio:
            "Studio",

        galleryEvent:
            "Event",

        aboutLabel:
            "04 — 关于我",

        aboutTitle1:
            "Nelli",

        aboutTitle2:
            "镜头之后。",

        aboutText:
            "这里将介绍Nelli的摄影故事和她对摄影的热爱。",

        quote:
            "“最好的照片，是你能在其中看到自己的照片。”",

        contactLabel:
            "05 — 预约",

        contactTitle1:
            "让我们",

        contactTitle2:
            "一起创造。",

        contactDescription:
            "告诉我你的活动、日期和想法。",

        formTitle:
            "告诉我你的摄影需求",

        name:
            "你的名字",

        email:
            "Email",

        phone:
            "电话",

        date:
            "日期",

        type:
            "摄影类型",

        choose:
            "选择类型",

        message:
            "告诉我更多",

        send:
            "发送申请 →",

        footer:
            "布拉格摄影师"

    },


    ja: {

        flag: "🇯🇵",
        short: "JP",

        navServices: "撮影",
        navPortfolio: "ポートフォリオ",
        navAbout: "私について",
        navContact: "お問い合わせ",

        heroEyebrow:
            "プラハのフォトグラファー",

        heroTitle1:
            "あなたの瞬間を。",

        heroTitle2:
            "一枚の写真に物語を。",

        heroText:
            "ウェディング · 洗礼 · 誕生日 · 家族 · ポートレート · スタジオ",

        heroButton:
            "撮影を選ぶ",

        heroPortfolio:
            "作品を見る",

        introLabel:
            "01 — Photography",

        introTitle1:
            "ただの",

        introTitle2:
            "写真ではなく。",

        introText:
            "写真は感情を残すためのもの。本当の瞬間を、何年後にも思い出せる形で残します。",

        introQuote:
            "「大切な瞬間は二度と同じようには訪れない。」",

        servicesLabel:
            "02 — 撮影",

        servicesTitle1:
            "あなたの",

        servicesTitle2:
            "物語。",

        servicesDescription:
            "イベントや撮影スタイルをお選びください。",

        wedding:
            "ウェディング",

        weddingDesc:
            "最初の瞬間から最後のダンスまで。",

        christening:
            "洗礼",

        christeningDesc:
            "お子様の大切な一日を記録します。",

        birthday:
            "誕生日",

        birthdayDesc:
            "笑顔、感情、思い出を残します。",

        family:
            "ファミリー",

        familyDesc:
            "自然で温かい家族写真。",

        portrait:
            "ポートレート",

        portraitDesc:
            "あなたの個性とスタイルを。",

        studio:
            "スタジオ",

        studioDesc:
            "光、スタイル、細部までこだわります。",

        maternity:
            "マタニティ",

        maternityDesc:
            "新しい命の優しい物語。",

        children:
            "キッズ",

        childrenDesc:
            "本当の笑顔と子どもの時間。",

        other:
            "その他",

        otherDesc:
            "別のアイデアもお気軽にどうぞ。",

        loveDesc:
            "二人だけのストーリー。",

        portfolioLabel:
            "03 — Portfolio",

        portfolioTitle1:
            "残る",

        portfolioTitle2:
            "一枚一枚。",

        portfolioDescription:
            "ここにはあなたの最高の写真が表示されます。",

        galleryWedding:
            "Wedding",

        galleryPortrait:
            "Portrait",

        galleryFamily:
            "Family",

        galleryStudio:
            "Studio",

        galleryEvent:
            "Event",

        aboutLabel:
            "04 — About",

        aboutTitle1:
            "Nelli",

        aboutTitle2:
            "カメラの後ろで。",

        aboutText:
            "Nelliの写真への想いやストーリーをここに掲載します。",

        quote:
            "「最高の写真は、自分自身を見つけられる写真。」",

        contactLabel:
            "05 — Booking",

        contactTitle1:
            "一緒に",

        contactTitle2:
            "作りましょう。",

        contactDescription:
            "イベントの日付やご希望を教えてください。",

        formTitle:
            "撮影について",

        name:
            "お名前",

        email:
            "Email",

        phone:
            "電話番号",

        date:
            "日付",

        type:
            "撮影タイプ",

        choose:
            "タイプを選択",

        message:
            "イベントについて",

        send:
            "送信する →",

        footer:
            "プラハのフォトグラファー"

    }

};


/* =====================================================
   LANGUAGE LOGIC
===================================================== */

const language =
    document.getElementById(
        "language"
    );

const languageButton =
    document.getElementById(
        "languageButton"
    );

const currentFlag =
    document.getElementById(
        "currentFlag"
    );

const currentLang =
    document.getElementById(
        "currentLang"
    );

const formLanguage =
    document.getElementById(
        "formLanguage"
    );


languageButton.addEventListener(
    "click",
    () => {

        language.classList.toggle(
            "open"
        );

    }
);


document
    .querySelectorAll(".language-option")
    .forEach(
        option => {

            option.addEventListener(
                "click",
                () => {

                    const lang =
                        option.dataset.lang;

                    setLanguage(lang);

                    language.classList.remove(
                        "open"
                    );

                }
            );

        }
    );


function setLanguage(lang) {

    const data =
        translations[lang];

    if(!data) return;


    document
        .querySelectorAll("[data-i18n]")
        .forEach(
            element => {

                const key =
                    element.dataset.i18n;

                if(
                    data[key] !== undefined
                ) {

                    element.textContent =
                        data[key];

                }

            }
        );


    currentFlag.textContent =
        data.flag;

    currentLang.textContent =
        data.short;

    formLanguage.value =
        lang;


    document.documentElement.lang =
        lang;


    localStorage.setItem(
        "nelli-language",
        lang
    );

}


const savedLanguage =
    localStorage.getItem(
        "nelli-language"
    );


setLanguage(
    savedLanguage || "uk"
);


/* close language menu */

document.addEventListener(
    "click",
    event => {

        if(
            !language.contains(event.target)
        ) {

            language.classList.remove(
                "open"
            );

        }

    }
);


/* =====================================================
   MOBILE MENU
===================================================== */

const menuButton =
    document.getElementById(
        "menuButton"
    );

const mobileMenu =
    document.getElementById(
        "mobileMenu"
    );


menuButton.addEventListener(
    "click",
    () => {

        mobileMenu.classList.toggle(
            "open"
        );

        document.body.classList.toggle(
            "no-scroll"
        );

    }
);


document
    .querySelectorAll("[data-mobile-link]")
    .forEach(
        link => {

            link.addEventListener(
                "click",
                () => {

                    mobileMenu.classList.remove(
                        "open"
                    );

                    document.body.classList.remove(
                        "no-scroll"
                    );

                }
            );

        }
    );


/* =====================================================
   FORM
===================================================== */

const form =
    document.querySelector(
        ".booking form"
    );


form.addEventListener(
    "submit",
    () => {

        const languageValue =
            localStorage.getItem(
                "nelli-language"
            ) || "uk";

        formLanguage.value =
            languageValue;

    }
);

</script>


</body>

</html>
