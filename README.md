<!DOCTYPE html>
<html lang="uk">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <meta name="description" content="Неллі — професійний фотограф у Празі. Весільні, сімейні, портретні та студійні фотосесії.">

  <title>Неллі — фотограф у Празі</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">

  <style>

    :root {
      --black: #11110f;
      --dark: #191816;
      --cream: #f2eee7;
      --beige: #d4bda5;
      --gold: #b69a79;
      --gray: #898279;

      --serif: "Cormorant Garamond", serif;
      --sans: "DM Sans", sans-serif;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
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

    img {
      display: block;
      max-width: 100%;
    }


    /* =========================
       NAVIGATION
    ========================= */

    .nav {
      position: fixed;
      top: 0;
      left: 0;

      width: 100%;
      height: 78px;

      padding: 0 5vw;

      display: flex;
      align-items: center;
      justify-content: space-between;

      z-index: 1000;

      background:
        linear-gradient(
          to bottom,
          rgba(17,17,15,.95),
          rgba(17,17,15,0)
        );

      backdrop-filter: blur(8px);
    }

    .logo-text {
      font-family: var(--serif);
      font-size: 30px;
      letter-spacing: -0.04em;
    }

    .logo-text em {
      font-style: italic;
    }

    .nav-links {
      display: flex;
      gap: 32px;

      font-size: 10px;
      letter-spacing: .16em;
      text-transform: uppercase;
    }

    .nav-links a {
      color: #aaa39a;
      transition: .3s;
    }

    .nav-links a:hover {
      color: white;
    }

    .nav-button {
      border: 1px solid rgba(255,255,255,.3);
      border-radius: 100px;

      padding: 11px 18px;

      font-size: 9px;
      letter-spacing: .15em;
      text-transform: uppercase;

      transition: .35s;
    }

    .nav-button:hover {
      background: white;
      color: #111;
    }


    /* =========================
       HERO
    ========================= */

    .hero {
      min-height: 100vh;

      position: relative;

      display: flex;
      align-items: center;
      justify-content: center;

      text-align: center;

      overflow: hidden;

      background:
        radial-gradient(
          circle at 50% 45%,
          rgba(182,154,121,.25),
          transparent 30%
        ),
        radial-gradient(
          circle at center,
          #38332c 0%,
          #211f1b 35%,
          #11110f 75%
        );
    }

    .hero-circle {
      position: absolute;

      width: min(70vw, 850px);
      aspect-ratio: 1;

      border: 1px solid rgba(255,255,255,.06);

      border-radius: 50%;

      animation: rotateCircle 35s linear infinite;
    }

    .hero-circle::after {
      content: "";

      position: absolute;

      inset: 12%;

      border: 1px solid rgba(255,255,255,.04);

      border-radius: 50%;
    }

    @keyframes rotateCircle {
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

      padding: 120px 20px 80px;

      max-width: 1000px;
    }

    .hero-logo {
      width: min(380px, 75vw);

      margin: 0 auto 40px;

      animation: heroAppear 1.2s ease both;
    }

    .hero-logo img {
      width: 100%;

      filter:
        drop-shadow(
          0 25px 50px rgba(0,0,0,.5)
        );
    }

    @keyframes heroAppear {

      from {
        opacity: 0;
        transform: translateY(30px) scale(.95);
        filter: blur(10px);
      }

      to {
        opacity: 1;
        transform: none;
        filter: blur(0);
      }
    }

    .eyebrow {
      color: var(--gold);

      font-size: 9px;

      letter-spacing: .3em;

      text-transform: uppercase;

      margin-bottom: 20px;
    }

    .hero h1 {
      font-family: var(--serif);

      font-size: clamp(48px, 7vw, 90px);

      font-weight: 300;

      line-height: .9;

      letter-spacing: -.06em;
    }

    .hero h1 em {
      font-style: italic;
    }

    .hero-description {
      max-width: 600px;

      margin: 30px auto 0;

      color: #aaa39a;

      font-size: 14px;

      line-height: 1.8;
    }

    .hero-button {
      display: inline-flex;

      margin-top: 32px;

      padding: 15px 24px;

      border: 1px solid rgba(255,255,255,.25);

      border-radius: 100px;

      font-size: 9px;

      letter-spacing: .15em;

      text-transform: uppercase;

      transition: .35s;
    }

    .hero-button:hover {
      background: white;
      color: #111;

      transform: translateY(-3px);
    }

    .scroll-down {
      position: absolute;

      bottom: 25px;
      left: 50%;

      transform: translateX(-50%);

      color: #777168;

      font-size: 8px;

      letter-spacing: .25em;

      text-transform: uppercase;
    }

    .scroll-down::after {
      content: "";

      display: block;

      width: 1px;
      height: 45px;

      margin: 10px auto 0;

      background: linear-gradient(
        #777,
        transparent
      );
    }


    /* =========================
       GENERAL
    ========================= */

    .section-number {
      color: #81796f;

      font-size: 9px;

      letter-spacing: .25em;

      text-transform: uppercase;
    }

    .big-title {
      font-family: var(--serif);

      font-size: clamp(55px, 7vw, 100px);

      line-height: .84;

      font-weight: 300;

      letter-spacing: -.065em;
    }

    .big-title em {
      font-style: italic;
    }


    /* =========================
       INTRO
    ========================= */

    .intro {
      padding: 140px 7vw;

      display: grid;

      grid-template-columns: .5fr 1.5fr;

      gap: 10vw;

      align-items: center;

      background: var(--cream);

      color: #181714;
    }

    .intro-text {
      max-width: 650px;
    }

    .intro-text p {
      margin-top: 35px;

      color: #69635b;

      font-size: 17px;

      line-height: 1.85;
    }


    /* =========================
       SERVICES
    ========================= */

    .services {
      padding: 140px 5vw;

      background: var(--dark);
    }

    .services-heading {
      margin-bottom: 70px;
    }

    .services-heading h2 {
      margin-top: 20px;
    }

    .services-description {
      max-width: 600px;

      margin-top: 30px;

      color: #858077;

      font-size: 14px;

      line-height: 1.8;
    }

    .services-grid {
      display: grid;

      grid-template-columns:
        repeat(4, 1fr);

      gap: 10px;
    }

    .service-card {
      min-height: 330px;

      position: relative;

      padding: 24px;

      overflow: hidden;

      border: 1px solid #33312d;

      background:
        linear-gradient(
          145deg,
          #292720,
          #191816
        );

      transition:
        .6s cubic-bezier(.2,.8,.2,1);
    }

    .service-card:hover {
      transform: translateY(-10px);

      border-color: #82715d;
    }

    .service-number {
      color: #68625a;

      font-size: 9px;

      letter-spacing: .15em;
    }

    .service-letter {
      margin-top: 45px;

      font-family: var(--serif);

      font-size: 60px;

      color: #aaa39a;

      transition: .5s;
    }

    .service-card:hover .service-letter {
      transform:
        translateX(8px)
        rotate(-4deg);

      color: #e1d7c8;
    }

    .service-card h3 {
      position: absolute;

      left: 24px;
      bottom: 50px;

      font-family: var(--serif);

      font-size: 31px;

      font-weight: 300;
    }

    .service-card small {
      position: absolute;

      left: 24px;
      bottom: 23px;

      color: #69645c;

      font-size: 8px;

      letter-spacing: .13em;

      text-transform: uppercase;
    }


    /* =========================
       MARQUEE
    ========================= */

    .marquee {
      overflow: hidden;

      white-space: nowrap;

      padding: 25px 0;

      background: var(--beige);

      color: #181714;
    }

    .marquee-track {
      display: inline-flex;

      gap: 35px;

      animation:
        marquee 25s linear infinite;
    }

    .marquee span {
      font-family: var(--serif);

      font-size: 30px;

      font-style: italic;
    }

    .marquee i {
      font-style: normal;

      opacity: .45;
    }

    @keyframes marquee {

      to {
        transform: translateX(-50%);
      }

    }


    /* =========================
       PORTFOLIO
    ========================= */

    .portfolio {
      padding: 140px 5vw;

      background: var(--cream);

      color: #171613;
    }

    .portfolio-header {
      display: flex;

      justify-content: space-between;

      align-items: end;

      gap: 40px;

      margin-bottom: 65px;
    }

    .portfolio-description {
      max-width: 330px;

      color: #777168;

      font-size: 12px;

      line-height: 1.8;
    }

    .gallery {
      display: grid;

      grid-template-columns:
        repeat(12, 1fr);

      grid-auto-rows: 80px;

      gap: 12px;
    }

    .gallery-item {
      position: relative;

      overflow: hidden;

      background: #bdb4a7;
    }

    .gallery-item img {
      width: 100%;
      height: 100%;

      object-fit: cover;

      transition:
        transform .8s,
        filter .8s;
    }

    .gallery-item:hover img {
      transform: scale(1.06);

      filter: brightness(.85);
    }

    .gallery-label {
      position: absolute;

      left: 15px;
      bottom: 15px;

      padding: 7px 10px;

      background: rgba(10,10,10,.7);

      color: white;

      font-size: 8px;

      letter-spacing: .14em;

      text-transform: uppercase;
    }

    .gallery-one {
      grid-column: span 7;
      grid-row: span 6;
    }

    .gallery-two {
      grid-column: span 5;
      grid-row: span 4;
    }

    .gallery-three {
      grid-column: span 5;
      grid-row: span 5;
    }

    .gallery-four {
      grid-column: span 4;
      grid-row: span 3;
    }

    .gallery-five {
      grid-column: span 3;
      grid-row: span 3;
    }


    /* =========================
       ABOUT
    ========================= */

    .about {
      padding: 140px 7vw;

      display: grid;

      grid-template-columns:
        .8fr 1.2fr;

      gap: 10vw;

      align-items: center;

      background: var(--dark);
    }

    .about-image {
      aspect-ratio: 4 / 5;

      overflow: hidden;

      background:
        linear-gradient(
          145deg,
          #b7aa99,
          #4d473f
        );
    }

    .about-image img {
      width: 100%;
      height: 100%;

      object-fit: cover;
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

      margin-top: 50px;

      padding-top: 25px;

      border-top: 1px solid #35332e;

      font-family: var(--serif);

      font-size: 28px;

      line-height: 1.35;
    }


    /* =========================
       CONTACT
    ========================= */

    .contact {
      padding: 140px 7vw;

      display: grid;

      grid-template-columns:
        1fr 1fr;

      gap: 10vw;

      align-items: center;

      background: var(--beige);

      color: #181714;
    }

    .contact-description {
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

      letter-spacing: .13em;

      text-transform: uppercase;

      transition: .35s;
    }

    .contact-link:hover {
      background: #181714;

      color: white;
    }


    /* =========================
       FOOTER
    ========================= */

    footer {
      padding: 25px 5vw;

      display: flex;

      justify-content: space-between;

      background: var(--black);

      color: #66615a;

      font-size: 8px;

      letter-spacing: .16em;

      text-transform: uppercase;
    }


    /* =========================
       ANIMATIONS
    ========================= */

    .reveal {
      opacity: 0;

      transform: translateY(35px);

      transition:
        opacity .9s,
        transform .9s cubic-bezier(.2,.8,.2,1);
    }

    .reveal.visible {
      opacity: 1;

      transform: none;
    }


    /* =========================
       MOBILE
    ========================= */

    @media(max-width: 900px) {

      .nav-links {
        display: none;
      }

      .nav-button {
        display: none;
      }

      .intro,
      .about,
      .contact {
        grid-template-columns: 1fr;

        gap: 60px;
      }

      .services-grid {
        grid-template-columns:
          repeat(2,1fr);
      }

      .portfolio-header {
        display: block;
      }

      .portfolio-description {
        margin-top: 25px;
      }

    }


    @media(max-width: 600px) {

      .nav {
        height: 68px;
      }

      .hero-content {
        padding-top: 105px;
      }

      .hero-logo {
        width: 85vw;
      }

      .hero h1 {
        font-size: 43px;
      }

      .services-grid {
        grid-template-columns: 1fr;
      }

      .service-card {
        min-height: 270px;
      }

      .gallery {
        grid-template-columns: 1fr;

        grid-auto-rows: 280px;
      }

      .gallery-item {
        grid-column: span 1 !important;

        grid-row: span 1 !important;
      }

      .intro,
      .about,
      .contact {
        padding-top: 100px;
        padding-bottom: 100px;
      }

      footer {
        flex-direction: column;

        gap: 10px;
      }

    }

  </style>
</head>


<body>


  <!-- =========================
       NAVIGATION
  ========================= -->

  <header class="nav">

    <a href="#" class="logo-text">
      Неллі <em>фото</em>
    </a>

    <nav class="nav-links">

      <a href="#services">
        Зйомки
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


  <!-- =========================
       HERO
  ========================= -->

  <section class="hero">

    <div class="hero-circle"></div>

    <div class="hero-content">

      <!-- ТВОЄ ФОТО ЛОГОТИПУ -->
      <div class="hero-logo">

        <img
          src="e6e5c1df-9682-4b22-adb4-764d0fd31df0.png"
          alt="Логотип Неллі"
        >

      </div>


      <div class="eyebrow">
        Фотограф у Празі
      </div>


      <h1>

        Ваші моменти.

        <br>

        <em>Моя історія в кадрі.</em>

      </h1>


      <p class="hero-description">

        Весілля · Хрестини · Обрядові події ·
        Студійні фотосесії · Портрети · Сімейні зйомки

      </p>


      <a href="#services" class="hero-button">

        Обрати зйомку ↓

      </a>

    </div>


    <div class="scroll-down">
      Гортайте
    </div>

  </section>



  <!-- =========================
       INTRO
  ========================= -->

  <section class="intro reveal">

    <div class="section-number">
      01 — Про фотографію
    </div>


    <div class="intro-text">

      <h2 class="big-title">

        Фотографії,

        <br>

        які хочеться <em>відчути.</em>

      </h2>


      <p>

        Не потрібно вміти позувати.
        Не потрібно знати, куди дивитися.
        Просто будьте собою — я подбаю про те,
        щоб ваші емоції та важливі моменти
        залишилися у кадрі.

      </p>

    </div>

  </section>



  <!-- =========================
       SERVICES
  ========================= -->

  <section class="services" id="services">

    <div class="services-heading reveal">

      <div class="section-number">
        02 — Оберіть зйомку
      </div>


      <h2 class="big-title">

        Яку зйомку

        <br>

        <em>створимо?</em>

      </h2>


      <p class="services-description">

        Оберіть формат, який вам підходить.
        Якщо не знаєте, що саме хочете —
        просто напишіть мені.

      </p>

    </div>



    <div class="services-grid">


      <a href="#contact" class="service-card reveal">

        <div class="service-number">
          01
        </div>

        <div class="service-letter">
          W
        </div>

        <h3>
          Весілля
        </h3>

        <small>
          Ваш день · ваша історія
        </small>

      </a>



      <a href="#contact" class="service-card reveal">

        <div class="service-number">
          02
        </div>

        <div class="service-letter">
          F
        </div>

        <h3>
          Сімейна
        </h3>

        <small>
          Теплі моменти разом
        </small>

      </a>



      <a href="#contact" class="service-card reveal">

        <div class="service-number">
          03
        </div>

        <div class="service-letter">
          P
        </div>

        <h3>
          Портрет
        </h3>

        <small>
          Ти справжній / справжня
        </small>

      </a>



      <a href="#contact" class="service-card reveal">

        <div class="service-number">
          04
        </div>

        <div class="service-letter">
          S
        </div>

        <h3>
          Студія
        </h3>

        <small>
          Світло · стиль · характер
        </small>

      </a>


    </div>

  </section>



  <!-- =========================
       MARQUEE
  ========================= -->

  <div class="marquee">

    <div class="marquee-track">

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

      <i>✦</i>

      <span>
        your story in frames
      </span>

    </div>

  </div>



  <!-- =========================
       PORTFOLIO
  ========================= -->

  <section class="portfolio" id="portfolio">

    <div class="portfolio-header reveal">

      <div>

        <div class="section-number">
          03 — Портфоліо
        </div>

        <h2 class="big-title">

          Мої

          <br>

          <em>історії.</em>

        </h2>

      </div>


      <p class="portfolio-description">

        Тут будуть справжні фотографії
        робіт Неллі.

        Просто завантаж свої фото
        у GitHub під назвами:

        photo-1.jpg,
        photo-2.jpg,
        photo-3.jpg,
        photo-4.jpg,
        photo-5.jpg

      </p>

    </div>



    <div class="gallery">


      <div class="gallery-item gallery-one">

        <img
          src="photo-1.jpg"
          alt="Весільна фотосесія"
        >

        <span class="gallery-label">
          Wedding
        </span>

      </div>



      <div class="gallery-item gallery-two">

        <img
          src="photo-2.jpg"
          alt="Портретна фотосесія"
        >

        <span class="gallery-label">
          Portrait
        </span>

      </div>



      <div class="gallery-item gallery-three">

        <img
          src="photo-3.jpg"
          alt="Сімейна фотосесія"
        >

        <span class="gallery-label">
          Family
        </span>

      </div>



      <div class="gallery-item gallery-four">

        <img
          src="photo-4.jpg"
          alt="Студійна фотосесія"
        >

        <span class="gallery-label">
          Studio
        </span>

      </div>



      <div class="gallery-item gallery-five">

        <img
          src="photo-5.jpg"
          alt="Фотосесія"
        >

        <span class="gallery-label">
          Story
        </span>

      </div>


    </div>

  </section>



  <!-- =========================
       ABOUT
  ========================= -->

  <section class="about" id="about">


    <div class="about-image reveal">

      <!--
        Додай фото Неллі
        під назвою about.jpg
      -->

      <img
        src="about.jpg"
        alt="Неллі — фотограф"
      >

    </div>



    <div class="reveal">

      <div class="section-number">
        04 — Про мене
      </div>


      <h2
        class="big-title"
        style="margin-top:20px;"
      >

        Неллі

        <br>

        <em>за кадром.</em>

      </h2>


      <p class="about-text">

        Тут можна написати коротку
        особисту історію Неллі:

        як вона прийшла у фотографію,
        що любить знімати та чому
        клієнтам комфортно працювати
        саме з нею.

      </p>


      <div class="quote">

        «Найкращі фотографії —
        це не ті, де всі ідеально
        позують, а ті, де ви
        впізнаєте себе.»

      </div>

    </div>

  </section>



  <!-- =========================
       CONTACT
  ========================= -->

  <section class="contact" id="contact">


    <div class="reveal">

      <div class="section-number">
        05 — Контакти
      </div>


      <h2
        class="big-title"
        style="margin-top:20px;"
      >

        Давайте

        <br>

        <em>створимо.</em>

      </h2>

    </div>



    <div class="reveal">

      <p class="contact-description">

        Розкажіть, яку подію або зйомку
        ви плануєте.

        Напишіть у зручний месенджер —
        відповім і допоможу підібрати
        формат.

      </p>


      <div class="contact-links">

        <!-- ЗАМІНИ ПОСИЛАННЯ НА СПРАВЖНІ -->

        <a
          class="contact-link"
          href="https://www.instagram.com/"
          target="_blank"
        >
          Instagram
        </a>


        <a
          class="contact-link"
          href="mailto:YOUR_EMAIL@example.com"
        >
          Email
        </a>


        <a
          class="contact-link"
          href="tel:+420000000000"
        >
          Телефон
        </a>

      </div>

    </div>

  </section>


</main>



<!-- =========================
     FOOTER
========================= -->

<footer>

  <span>
    © 2026 Неллі · фотограф у Празі
  </span>

  <span>
    NELLI PHOTOGRAPHY
  </span>

</footer>



<script>

  /*
    Поява елементів
    при прокрутці
  */

  const observer =
    new IntersectionObserver(
      entries => {

        entries.forEach(entry => {

          if (entry.isIntersecting) {

            entry.target.classList.add(
              "visible"
            );

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



  /*
    Легкий parallax
    головного кола
  */

  const circle =
    document.querySelector(".hero-circle");


  window.addEventListener(
    "scroll",
    () => {

      const y =
        window.scrollY * .08;

      circle.style.transform =
        `translateY(${y}px)`;

    }
  );

</script>


</body>
</html>
