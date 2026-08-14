<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Nelli — Photographer Prague</title>

    <style>
        @import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@300;400;500&family=Playfair+Display:ital,wght@0,400;0,500;1,400&display=swap');

        :root {
            --bg: #f4f1eb;
            --text: #191817;
            --muted: #77736d;
            --line: #d9d4cc;
            --dark: #20201e;
            --white: #faf9f6;
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
            background: var(--bg);
            color: var(--text);
            font-family: "DM Sans", sans-serif;
            font-weight: 300;
        }

        a {
            color: inherit;
            text-decoration: none;
        }

        button {
            font-family: inherit;
        }

        /* =========================
           NAVIGATION
        ========================= */

        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 82px;

            display: flex;
            align-items: center;
            justify-content: space-between;

            padding: 0 5vw;

            z-index: 100;

            background: rgba(244, 241, 235, 0.82);
            backdrop-filter: blur(15px);

            border-bottom: 1px solid rgba(217, 212, 204, .7);
        }

        .logo {
            font-family: "Playfair Display", serif;
            font-size: 25px;
            letter-spacing: -0.03em;
        }

        .logo span {
            font-style: italic;
        }

        nav {
            display: flex;
            gap: 35px;

            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: .15em;
        }

        nav a {
            position: relative;
            opacity: .7;
            transition: .3s;
        }

        nav a:hover {
            opacity: 1;
        }

        nav a::after {
            content: "";

            position: absolute;
            left: 0;
            bottom: -7px;

            width: 0;
            height: 1px;

            background: var(--text);

            transition: .3s;
        }

        nav a:hover::after {
            width: 100%;
        }

        .menu {
            display: none;

            border: 0;
            background: none;

            font-size: 24px;
            cursor: pointer;
        }


        /* =========================
           HERO
        ========================= */

        .hero {
            min-height: 100vh;

            padding: 150px 5vw 80px;

            display: grid;
            grid-template-columns: 1fr 1fr;

            gap: 8vw;

            align-items: center;
        }

        .hero-label {
            margin-bottom: 28px;

            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: .22em;

            color: var(--muted);
        }

        .hero h1 {
            font-family: "Playfair Display", serif;

            font-weight: 400;

            font-size: clamp(60px, 8vw, 120px);

            line-height: .88;

            letter-spacing: -.065em;
        }

        .hero h1 em {
            font-style: italic;
        }

        .hero-description {
            margin-top: 40px;

            max-width: 480px;

            font-size: 17px;
            line-height: 1.7;

            color: #5d5953;
        }

        .hero-button {
            display: inline-flex;
            align-items: center;
            gap: 18px;

            margin-top: 35px;

            padding: 15px 20px;

            border-radius: 100px;

            background: var(--dark);
            color: white;

            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: .12em;

            transition: .3s;
        }

        .hero-button:hover {
            transform: translateY(-3px);
            padding-right: 25px;
        }

        .arrow {
            width: 28px;
            height: 28px;

            border: 1px solid #777;

            border-radius: 50%;

            display: grid;
            place-items: center;
        }


        /* =========================
           HERO VISUAL PLACEHOLDER
        ========================= */

        .hero-visual {
            height: 650px;

            position: relative;

            background:
                linear-gradient(
                    135deg,
                    #d7d0c5,
                    #bcb4a8
                );

            overflow: hidden;
        }

        .hero-visual::before {
            content: "PHOTO";

            position: absolute;

            inset: 0;

            display: grid;
            place-items: center;

            font-family: "Playfair Display", serif;

            font-size: 55px;
            font-style: italic;

            color: rgba(255,255,255,.6);

            letter-spacing: .1em;
        }

        .visual-caption {
            position: absolute;

            left: 20px;
            bottom: 20px;

            padding: 12px 15px;

            background: rgba(250,249,246,.9);

            font-size: 10px;

            text-transform: uppercase;
            letter-spacing: .14em;
        }


        /* =========================
           INTRO
        ========================= */

        .intro {
            padding: 130px 5vw;

            background: var(--white);

            display: grid;
            grid-template-columns: .7fr 1.3fr;

            gap: 8vw;
        }

        .section-number {
            font-size: 11px;

            text-transform: uppercase;
            letter-spacing: .18em;

            color: var(--muted);
        }

        .intro h2 {
            font-family: "Playfair Display", serif;

            font-size: clamp(40px, 5vw, 70px);

            font-weight: 400;

            line-height: .98;

            letter-spacing: -.045em;
        }

        .intro h2 em {
            font-style: italic;
        }

        .intro p {
            margin-top: 30px;

            max-width: 650px;

            font-size: 18px;

            line-height: 1.75;

            color: #65615b;
        }


        /* =========================
           SERVICES
        ========================= */

        .services {
            padding: 120px 5vw;
        }

        .services-title {
            font-family: "Playfair Display", serif;

            font-size: clamp(45px, 6vw, 80px);

            font-weight: 400;

            letter-spacing: -.05em;

            margin-top: 15px;
        }

        .service-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);

            margin-top: 65px;

            border-top: 1px solid var(--line);
        }

        .service {
            padding: 30px 30px 40px 0;

            border-bottom: 1px solid var(--line);
        }

        .service + .service {
            padding-left: 30px;

            border-left: 1px solid var(--line);
        }

        .service-number {
            font-size: 11px;

            color: var(--muted);
        }

        .service h3 {
            margin-top: 60px;

            font-family: "Playfair Display", serif;

            font-size: 32px;

            font-weight: 400;
        }

        .service p {
            margin-top: 17px;

            max-width: 300px;

            color: var(--muted);

            line-height: 1.6;
        }


        /* =========================
           PORTFOLIO
        ========================= */

        .portfolio {
            padding: 120px 5vw;

            background: var(--dark);

            color: white;
        }

        .portfolio-top {
            display: flex;

            justify-content: space-between;
            align-items: end;

            gap: 30px;
        }

        .portfolio-title {
            font-family: "Playfair Display", serif;

            font-size: clamp(50px, 7vw, 90px);

            font-weight: 400;

            line-height: .9;

            letter-spacing: -.06em;
        }

        .portfolio-title em {
            font-style: italic;
        }

        .filters {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
        }

        .filter {
            padding: 10px 15px;

            border: 1px solid #4b4a46;

            border-radius: 100px;

            background: transparent;

            color: #d8d4cd;

            cursor: pointer;

            font-size: 10px;

            text-transform: uppercase;

            letter-spacing: .12em;

            transition: .25s;
        }

        .filter:hover,
        .filter.active {
            background: white;
            color: var(--dark);
        }

        .gallery {
            margin-top: 55px;

            display: grid;

            grid-template-columns: repeat(12, 1fr);

            grid-auto-rows: 110px;

            gap: 15px;
        }

        .gallery-item {
            position: relative;

            background: #363532;

            overflow: hidden;

            display: grid;
            place-items: center;

            color: #77746e;

            font-family: "Playfair Display", serif;

            font-size: 25px;

            font-style: italic;

            transition: .5s;
        }

        .gallery-item:hover {
            transform: scale(.985);
        }

        .gallery-item:nth-child(1) {
            grid-column: span 7;
            grid-row: span 5;
        }

        .gallery-item:nth-child(2) {
            grid-column: span 5;
            grid-row: span 3;
        }

        .gallery-item:nth-child(3) {
            grid-column: span 5;
            grid-row: span 4;
        }

        .gallery-item:nth-child(4) {
            grid-column: span 4;
            grid-row: span 3;
        }

        .gallery-item:nth-child(5) {
            grid-column: span 3;
            grid-row: span 3;
        }

        .gallery-label {
            position: absolute;

            left: 15px;
            bottom: 15px;

            padding: 8px 10px;

            background: rgba(20,20,19,.7);

            color: white;

            font-family: "DM Sans", sans-serif;

            font-size: 9px;

            text-transform: uppercase;
            letter-spacing: .13em;
        }


        /* =========================
           ABOUT
        ========================= */

        .about {
            padding: 130px 5vw;

            display: grid;

            grid-template-columns: .8fr 1.2fr;

            gap: 9vw;

            align-items: center;
        }

        .about-visual {
            aspect-ratio: 4 / 5;

            background: #d2ccc2;

            display: grid;

            place-items: center;

            color: rgba(255,255,255,.65);

            font-family: "Playfair Display", serif;

            font-size: 40px;

            font-style: italic;
        }

        .about h2 {
            font-family: "Playfair Display", serif;

            font-size: clamp(45px, 6vw, 80px);

            font-weight: 400;

            line-height: .92;

            letter-spacing: -.055em;

            margin-top: 15px;
        }

        .about p {
            max-width: 620px;

            margin-top: 30px;

            font-size: 18px;

            line-height: 1.7;

            color: #625e58;
        }

        .quote {
            margin-top: 55px;

            padding-top: 25px;

            border-top: 1px solid var(--line);

            font-family: "Playfair Display", serif;

            font-size: 25px;

            line-height: 1.4;
        }


        /* =========================
           CONTACT
        ========================= */

        .contact {
            padding: 130px 5vw;

            background: #d8c5b1;

            display: grid;

            grid-template-columns: 1fr 1fr;

            gap: 8vw;
        }

        .contact h2 {
            font-family: "Playfair Display", serif;

            font-size: clamp(55px, 8vw, 105px);

            font-weight: 400;

            line-height: .86;

            letter-spacing: -.06em;
        }

        .contact h2 em {
            font-style: italic;
        }

        .contact-text {
            align-self: end;
        }

        .contact-text p {
            max-width: 480px;

            font-size: 18px;

            line-height: 1.7;

            color: #514a43;
        }

        .contact-links {
            margin-top: 35px;

            display: flex;

            gap: 10px;

            flex-wrap: wrap;
        }

        .contact-link {
            padding: 13px 17px;

            border: 1px solid rgba(25,24,23,.3);

            border-radius: 100px;

            font-size: 11px;

            text-transform: uppercase;

            letter-spacing: .1em;

            transition: .3s;
        }

        .contact-link:hover {
            background: var(--dark);
            color: white;
        }


        /* =========================
           FOOTER
        ========================= */

        footer {
            padding: 25px 5vw;

            display: flex;

            justify-content: space-between;

            font-size: 10px;

            text-transform: uppercase;

            letter-spacing: .12em;

            color: var(--muted);
        }


        /* =========================
           MOBILE
        ========================= */

        @media (max-width: 800px) {

            header {
                height: 70px;
            }

            nav {
                display: none;

                position: absolute;

                top: 70px;
                left: 0;

                width: 100%;

                padding: 25px 5vw;

                background: var(--bg);

                flex-direction: column;

                gap: 22px;
            }

            nav.open {
                display: flex;
            }

            .menu {
                display: block;
            }

            .hero {
                padding-top: 120px;

                grid-template-columns: 1fr;

                gap: 50px;
            }

            .hero-visual {
                height: 550px;
            }

            .intro,
            .about,
            .contact {
                grid-template-columns: 1fr;

                gap: 50px;

                padding-top: 90px;
                padding-bottom: 90px;
            }

            .service-grid {
                grid-template-columns: 1fr;
            }

            .service + .service {
                padding-left: 0;

                border-left: 0;
            }

            .portfolio-top {
                display: block;
            }

            .filters {
                margin-top: 30px;
            }

            .gallery {
                grid-template-columns: 1fr 1fr;

                grid-auto-rows: 150px;
            }

            .gallery-item:nth-child(1) {
                grid-column: span 2;
                grid-row: span 3;
            }

            .gallery-item:nth-child(2),
            .gallery-item:nth-child(3) {
                grid-column: span 1;
                grid-row: span 2;
            }

            .gallery-item:nth-child(4),
            .gallery-item:nth-child(5) {
                grid-column: span 1;
                grid-row: span 2;
            }

            footer {
                flex-direction: column;

                gap: 10px;
            }
        }

        @media (max-width: 480px) {

            .hero h1 {
                font-size: 58px;
            }

            .hero-visual {
                height: 480px;
            }

            .gallery {
                grid-template-columns: 1fr;

                grid-auto-rows: 250px;
            }

            .gallery-item:nth-child(n) {
                grid-column: span 1;
                grid-row: span 1;
            }
        }
    </style>
</head>


<body>


<!-- =========================
     HEADER
========================= -->

<header>

    <a href="#" class="logo">
        nelli <span>photo</span>
    </a>

    <nav id="nav">

        <a href="#portfolio">
            Портфоліо
        </a>

        <a href="#services">
            Зйомки
        </a>

        <a href="#about">
            Про мене
        </a>

        <a href="#contact">
            Контакти
        </a>

    </nav>

    <button class="menu" id="menu">
        ☰
    </button>

</header>



<!-- =========================
     HERO
========================= -->

<section class="hero">

    <div>

        <div class="hero-label">
            Photographer · Prague · CZ
        </div>

        <h1>
            Історії,<br>
            які хочеться<br>
            <em>переглядати.</em>
        </h1>

        <p class="hero-description">
            Весільний та lifestyle-фотограф у Празі.
            Живі емоції, красиве світло і фотографії,
            в яких ви впізнаєте себе.
        </p>

        <a href="#contact" class="hero-button">

            Запитати про зйомку

            <span class="arrow">
                ↗
            </span>

        </a>

    </div>


    <!-- ПОТІМ ТУТ БУДЕ ФОТО -->

    <div class="hero-visual">

        <div class="visual-caption">
            Prague · Love stories
        </div>

    </div>

</section>



<!-- =========================
     INTRO
========================= -->

<section class="intro">

    <div class="section-number">
        01 — Підхід
    </div>

    <div>

        <h2>
            Не просто позувати.<br>
            А прожити <em>момент.</em>
        </h2>

        <p>
            Моя задача — не перетворити вашу зйомку
            на набір однакових поз.
            Я допомагаю розслабитися, підказую,
            коли це потрібно, і ловлю те,
            що відбувається між кадрами.
        </p>

    </div>

</section>



<!-- =========================
     SERVICES
========================= -->

<section class="services" id="services">

    <div class="section-number">
        02 — Зйомки
    </div>

    <h2 class="services-title">
        Що ми можемо<br>
        <em>створити разом.</em>
    </h2>


    <div class="service-grid">


        <article class="service">

            <div class="service-number">
                01
            </div>

            <h3>
                Wedding
            </h3>

            <p>
                День, який минає швидко.
                Фотографії, які залишаються
                назавжди.
            </p>

        </article>


        <article class="service">

            <div class="service-number">
                02
            </div>

            <h3>
                Love story
            </h3>

            <p>
                Прогулянка, побачення або
                просто ви двоє.
                Без зайвої постановки.
            </p>

        </article>


        <article class="service">

            <div class="service-number">
                03
            </div>

            <h3>
                Individual
            </h3>

            <p>
                Портрети, lifestyle та
                персональні зйомки
                у Празі й за її межами.
            </p>

        </article>


    </div>

</section>



<!-- =========================
     PORTFOLIO
========================= -->

<section class="portfolio" id="portfolio">

    <div class="portfolio-top">

        <div>

            <div class="section-number">
                03 — Selected work
            </div>

            <h2 class="portfolio-title">
                Обрані<br>
                <em>історії.</em>
            </h2>

        </div>


        <div class="filters">

            <button class="filter active">
                Усі
            </button>

            <button class="filter">
                Wedding
            </button>

            <button class="filter">
                Love story
            </button>

            <button class="filter">
                Family
            </button>

        </div>

    </div>


    <!-- ЗАРАЗ ЦЕ ПРОСТО ПЛЕЙСХОЛДЕРИ -->

    <div class="gallery">

        <div class="gallery-item">
            PHOTO
            <span class="gallery-label">
                Wedding
            </span>
        </div>

        <div class="gallery-item">
            PHOTO
            <span class="gallery-label">
                Love story
            </span>
        </div>

        <div class="gallery-item">
            PHOTO
            <span class="gallery-label">
                Wedding
            </span>
        </div>

        <div class="gallery-item">
            PHOTO
            <span class="gallery-label">
                Family
            </span>
        </div>

        <div class="gallery-item">
            PHOTO
            <span class="gallery-label">
                Portrait
            </span>
        </div>

    </div>

</section>



<!-- =========================
     ABOUT
========================= -->

<section class="about" id="about">

    <!-- ПОТІМ ТУТ БУДЕ ФОТО НЕЛЛІ -->

    <div class="about-visual">
        PHOTO
    </div>


    <div>

        <div class="section-number">
            04 — Про мене
        </div>

        <h2>
            Привіт,<br>
            я <em>Неллі.</em>
        </h2>

        <p>
            Фотограф у Празі, яка любить красиві
            історії, справжні емоції та моменти,
            які не потрібно вигадувати.
        </p>

        <p>
            Я знімаю весілля, love story,
            індивідуальні та сімейні історії.
            Мені важливо, щоб під час зйомки
            вам було комфортно — навіть якщо
            ви ніколи раніше не фотографувалися.
        </p>


        <div class="quote">

            «Вам не потрібно вміти позувати.
            Просто приходьте собою.»

        </div>

    </div>

</section>



<!-- =========================
     CONTACT
========================= -->

<section class="contact" id="contact">

    <div>

        <div class="section-number">
            05 — Let's create
        </div>

        <h2>
            Розкажіть<br>
            про свою<br>
            <em>історію.</em>
        </h2>

    </div>


    <div class="contact-text">

        <p>
            Напишіть мені дату, формат зйомки
            та кілька слів про вашу ідею.
            Я відповім і допоможу з наступними
            кроками.
        </p>


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
                Email ↗
            </a>

        </div>

    </div>

</section>



<!-- =========================
     FOOTER
========================= -->

<footer>

    <span>
        © Nelli Photo Prague
    </span>

    <span>
        Prague · Czech Republic
    </span>

</footer>



<script>

    const menu = document.getElementById("menu");
    const nav = document.getElementById("nav");

    menu.addEventListener("click", () => {

        nav.classList.toggle("open");

    });


    // Закриваємо меню після натискання

    document.querySelectorAll("nav a").forEach(link => {

        link.addEventListener("click", () => {

            nav.classList.remove("open");

        });

    });


    // Фільтри портфоліо — поки просто візуальна взаємодія

    const filters = document.querySelectorAll(".filter");

    filters.forEach(button => {

        button.addEventListener("click", () => {

            filters.forEach(item => {
                item.classList.remove("active");
            });

            button.classList.add("active");

        });

    });

</script>


</body>
</html>
