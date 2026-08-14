<!DOCTYPE html>
<html lang="uk">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NELLI — Photography</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600;700&family=Inter:wght@300;400;500;600&display=swap');

:root{
    --bg:#0c0c0c;
    --bg2:#131313;
    --text:#f4f1ec;
    --muted:#aaa49d;
    --line:rgba(255,255,255,.12);
    --accent:#d7c5a4;
}

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    background:var(--bg);
    color:var(--text);
    font-family:Inter,sans-serif;
    overflow-x:hidden;
}

body:before{
    content:"";
    position:fixed;
    inset:0;
    pointer-events:none;
    background:
      radial-gradient(circle at 20% 20%,rgba(215,197,164,.06),transparent 30%),
      radial-gradient(circle at 80% 70%,rgba(255,255,255,.035),transparent 30%);
    z-index:-1;
}

a{
    color:inherit;
    text-decoration:none;
}

button{
    font:inherit;
}

/* ================= HEADER ================= */

header{
    position:fixed;
    top:0;
    left:0;
    width:100%;
    height:82px;
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding:0 6%;
    z-index:1000;
    transition:.4s;
}

header.scrolled{
    background:rgba(10,10,10,.88);
    backdrop-filter:blur(18px);
    border-bottom:1px solid var(--line);
}

.logo{
    display:flex;
    align-items:center;
    gap:12px;
}

.logo img{
    width:45px;
    height:45px;
    object-fit:contain;
    border-radius:50%;
    mix-blend-mode:screen;
}

.logo-text{
    font-family:"Cormorant Garamond",serif;
    font-size:28px;
    letter-spacing:5px;
}

nav{
    display:flex;
    gap:30px;
}

nav a{
    font-size:12px;
    text-transform:uppercase;
    letter-spacing:2px;
    color:#d4d0ca;
    transition:.3s;
}

nav a:hover{
    color:white;
}

.lang-wrap{
    position:relative;
}

.lang-btn{
    border:1px solid var(--line);
    background:rgba(255,255,255,.04);
    color:white;
    padding:10px 15px;
    border-radius:30px;
    cursor:pointer;
    display:flex;
    align-items:center;
    gap:8px;
}

.lang-menu{
    position:absolute;
    right:0;
    top:50px;
    width:170px;
    padding:8px;
    background:#171717;
    border:1px solid var(--line);
    border-radius:15px;
    opacity:0;
    visibility:hidden;
    transform:translateY(-10px);
    transition:.3s;
}

.lang-menu.open{
    opacity:1;
    visibility:visible;
    transform:translateY(0);
}

.lang-option{
    width:100%;
    padding:11px;
    border:0;
    background:none;
    color:white;
    cursor:pointer;
    text-align:left;
    border-radius:9px;
}

.lang-option:hover{
    background:rgba(255,255,255,.08);
}

.menu-btn{
    display:none;
    border:0;
    background:none;
    color:white;
    font-size:25px;
    cursor:pointer;
}

/* ================= HERO ================= */

.hero{
    min-height:100vh;
    display:grid;
    grid-template-columns:1.05fr .95fr;
    align-items:center;
    padding:120px 7% 70px;
    gap:70px;
}

.hero-left{
    animation:fadeUp 1.2s ease both;
}

.kicker{
    color:var(--accent);
    text-transform:uppercase;
    letter-spacing:5px;
    font-size:11px;
    margin-bottom:25px;
}

.hero h1{
    font-family:"Cormorant Garamond",serif;
    font-size:clamp(70px,10vw,150px);
    line-height:.75;
    font-weight:500;
    letter-spacing:-5px;
}

.hero h1 span{
    display:block;
    margin-left:70px;
    font-style:italic;
    color:#cfc8bd;
}

.hero-description{
    max-width:480px;
    color:var(--muted);
    line-height:1.8;
    margin:45px 0 30px;
}

.hero-buttons{
    display:flex;
    gap:15px;
    flex-wrap:wrap;
}

.btn{
    padding:15px 24px;
    border-radius:100px;
    border:1px solid var(--line);
    transition:.35s;
    display:inline-flex;
    align-items:center;
    justify-content:center;
}

.btn.primary{
    background:#eee9e1;
    color:#111;
}

.btn:hover{
    transform:translateY(-4px);
}

.btn.primary:hover{
    background:white;
}

.hero-right{
    position:relative;
    height:650px;
}

.hero-photo{
    position:absolute;
    width:75%;
    height:90%;
    right:0;
    top:5%;
    overflow:hidden;
    border-radius:2px;
}

.hero-photo img{
    width:100%;
    height:100%;
    object-fit:cover;
    transition:transform 1.2s;
}

.hero-photo:hover img{
    transform:scale(1.05);
}

.hero-frame{
    position:absolute;
    width:70%;
    height:80%;
    left:0;
    bottom:0;
    border:1px solid rgba(215,197,164,.4);
}

/* ================= MARQUEE ================= */

.marquee{
    border-top:1px solid var(--line);
    border-bottom:1px solid var(--line);
    overflow:hidden;
    white-space:nowrap;
    padding:20px 0;
}

.marquee-inner{
    display:inline-block;
    animation:marquee 25s linear infinite;
}

.marquee span{
    margin:0 35px;
    font-family:"Cormorant Garamond",serif;
    font-size:25px;
    font-style:italic;
    color:#c8c0b5;
}

/* ================= GENERAL ================= */

section{
    padding:120px 7%;
}

.section-top{
    display:flex;
    justify-content:space-between;
    align-items:end;
    margin-bottom:55px;
    gap:30px;
}

.section-number{
    font-size:11px;
    letter-spacing:3px;
    color:var(--accent);
}

.section-title{
    font-family:"Cormorant Garamond",serif;
    font-size:clamp(50px,7vw,90px);
    font-weight:500;
    line-height:.85;
}

.section-description{
    max-width:370px;
    color:var(--muted);
    line-height:1.7;
}

/* ================= SERVICES ================= */

.services{
    background:#101010;
}

.service-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:2px;
}

.service{
    min-height:300px;
    padding:35px;
    background:#151515;
    border:1px solid rgba(255,255,255,.05);
    position:relative;
    overflow:hidden;
    transition:.5s;
}

.service:before{
    content:"";
    position:absolute;
    inset:0;
    background:linear-gradient(135deg,rgba(215,197,164,.08),transparent 50%);
    opacity:0;
    transition:.5s;
}

.service:hover{
    transform:translateY(-8px);
}

.service:hover:before{
    opacity:1;
}

.service-num{
    color:#777;
    font-size:12px;
}

.service-icon{
    font-size:35px;
    margin:40px 0 25px;
    filter:grayscale(1);
}

.service h3{
    font-family:"Cormorant Garamond",serif;
    font-size:32px;
    font-weight:500;
}

.service p{
    color:var(--muted);
    margin-top:12px;
    line-height:1.6;
    font-size:14px;
}

/* ================= PORTFOLIO ================= */

.portfolio-grid{
    display:grid;
    grid-template-columns:repeat(12,1fr);
    grid-auto-rows:250px;
    gap:12px;
}

.photo{
    position:relative;
    overflow:hidden;
    background:#1b1b1b;
}

.photo:nth-child(1){grid-column:span 5;grid-row:span 2}
.photo:nth-child(2){grid-column:span 7}
.photo:nth-child(3){grid-column:span 4}
.photo:nth-child(4){grid-column:span 3}
.photo:nth-child(5){grid-column:span 5}
.photo:nth-child(6){grid-column:span 4}
.photo:nth-child(7){grid-column:span 8}
.photo:nth-child(8){grid-column:span 4}

.photo img{
    width:100%;
    height:100%;
    object-fit:cover;
    transition:1s;
    filter:saturate(.8);
}

.photo:hover img{
    transform:scale(1.08);
    filter:saturate(1);
}

.photo-label{
    position:absolute;
    left:20px;
    bottom:20px;
    background:rgba(0,0,0,.55);
    backdrop-filter:blur(10px);
    padding:8px 14px;
    border-radius:30px;
    font-size:11px;
}

/* ================= PACKAGES ================= */

.packages{
    background:#101010;
}

.package-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:15px;
}

.package{
    padding:40px 32px;
    border:1px solid var(--line);
    background:#141414;
    transition:.4s;
}

.package:hover{
    transform:translateY(-10px);
    border-color:rgba(215,197,164,.5);
}

.package.featured{
    background:#e8e2d8;
    color:#151515;
}

.package-name{
    font-size:11px;
    text-transform:uppercase;
    letter-spacing:3px;
}

.package-price{
    font-family:"Cormorant Garamond",serif;
    font-size:55px;
    margin:25px 0;
}

.package ul{
    list-style:none;
}

.package li{
    padding:12px 0;
    border-bottom:1px solid rgba(255,255,255,.1);
    font-size:14px;
}

/* ================= ABOUT ================= */

.about{
    display:grid;
    grid-template-columns:.8fr 1.2fr;
    gap:100px;
    align-items:center;
}

.about-photo{
    height:650px;
    overflow:hidden;
}

.about-photo img{
    width:100%;
    height:100%;
    object-fit:cover;
}

.about-text h2{
    font-family:"Cormorant Garamond",serif;
    font-size:75px;
    font-weight:500;
    line-height:.9;
    margin-bottom:35px;
}

.about-text p{
    color:var(--muted);
    line-height:1.9;
    max-width:600px;
}

/* ================= CONTACT ================= */

.contact{
    text-align:center;
    min-height:70vh;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    background:
      radial-gradient(circle at center,rgba(215,197,164,.07),transparent 45%);
}

.contact h2{
    font-family:"Cormorant Garamond",serif;
    font-size:clamp(70px,11vw,150px);
    font-weight:500;
    line-height:.8;
}

.contact p{
    color:var(--muted);
    margin:35px auto;
    max-width:450px;
    line-height:1.7;
}

.contact-links{
    display:flex;
    gap:12px;
    flex-wrap:wrap;
    justify-content:center;
}

.contact-link{
    padding:14px 22px;
    border:1px solid var(--line);
    border-radius:100px;
    transition:.3s;
}

.contact-link:hover{
    background:#eee9e1;
    color:#111;
}

/* ================= FOOTER ================= */

footer{
    padding:35px 7%;
    border-top:1px solid var(--line);
    display:flex;
    justify-content:space-between;
    color:#777;
    font-size:12px;
}

/* ================= ANIMATION ================= */

.reveal{
    opacity:0;
    transform:translateY(50px);
    transition:1s ease;
}

.reveal.visible{
    opacity:1;
    transform:none;
}

@keyframes fadeUp{
    from{
        opacity:0;
        transform:translateY(40px);
    }
    to{
        opacity:1;
        transform:none;
    }
}

@keyframes marquee{
    from{transform:translateX(0)}
    to{transform:translateX(-50%)}
}

/* ================= MOBILE ================= */

@media(max-width:900px){

    header{
        padding:0 5%;
    }

    nav{
        position:absolute;
        top:82px;
        left:0;
        width:100%;
        background:#101010;
        flex-direction:column;
        padding:25px;
        display:none;
    }

    nav.open{
        display:flex;
    }

    .menu-btn{
        display:block;
    }

    .hero{
        grid-template-columns:1fr;
        padding-top:140px;
    }

    .hero-right{
        height:500px;
    }

    .hero h1{
        font-size:85px;
    }

    .hero h1 span{
        margin-left:35px;
    }

    .service-grid,
    .package-grid{
        grid-template-columns:1fr;
    }

    .portfolio-grid{
        display:grid;
        grid-template-columns:1fr 1fr;
        grid-auto-rows:220px;
    }

    .photo:nth-child(n){
        grid-column:span 1;
        grid-row:span 1;
    }

    .photo:first-child{
        grid-column:span 2;
        grid-row:span 2;
    }

    .about{
        grid-template-columns:1fr;
        gap:50px;
    }

    .about-photo{
        height:500px;
    }

    .about-text h2{
        font-size:60px;
    }

    footer{
        flex-direction:column;
        gap:15px;
    }
}

@media(max-width:550px){

    section{
        padding:90px 5%;
    }

    .logo-text{
        font-size:22px;
        letter-spacing:3px;
    }

    .hero h1{
        font-size:67px;
    }

    .hero-right{
        height:420px;
    }

    .portfolio-grid{
        grid-template-columns:1fr;
    }

    .photo:first-child{
        grid-column:span 1;
    }

    .section-top{
        flex-direction:column;
        align-items:flex-start;
    }
}
</style>
</head>

<body>

<header id="header">

    <a href="#home" class="logo">

        <!-- ЗАМІНИ ЦЕ ПОСИЛАННЯ НА ЛОГОТИП -->
        <img src="logo.png" alt="Nelli Photography">

        <span class="logo-text">NELLI</span>
    </a>

    <nav id="nav">
        <a href="#services" data-i18n="nav_services">Послуги</a>
        <a href="#portfolio" data-i18n="nav_portfolio">Портфоліо</a>
        <a href="#packages" data-i18n="nav_packages">Пакети</a>
        <a href="#about" data-i18n="nav_about">Про мене</a>
        <a href="#contact" data-i18n="nav_contact">Контакти</a>
    </nav>

    <div style="display:flex;align-items:center;gap:15px">

        <div class="lang-wrap">

            <button class="lang-btn" id="langBtn">
                <span id="currentFlag">🇺🇦</span>
                <span id="currentLang">UA</span>
                <span>⌄</span>
            </button>

            <div class="lang-menu" id="langMenu">

                <button class="lang-option" data-lang="uk">
                    🇺🇦 Українська
                </button>

                <button class="lang-option" data-lang="ru">
                    🇷🇺 Русский
                </button>

                <button class="lang-option" data-lang="en">
                    🇬🇧 English
                </button>

                <button class="lang-option" data-lang="cs">
                    🇨🇿 Čeština
                </button>

            </div>

        </div>

        <button class="menu-btn" id="menuBtn">☰</button>

    </div>

</header>


<main>

<!-- HERO -->

<section class="hero" id="home">

    <div class="hero-left">

        <div class="kicker" data-i18n="hero_kicker">
            Photography · Prague
        </div>

        <h1>
            Nelli
            <span>stories.</span>
        </h1>

        <p class="hero-description" data-i18n="hero_text">
            Фотографую справжні моменти, емоції та людей такими,
            якими вони є. Весілля, сімейні історії, хрестини,
            дні народження та красиві портрети.
        </p>

        <div class="hero-buttons">
            <a href="#portfolio" class="btn primary" data-i18n="hero_btn1">
                Дивитися роботи
            </a>

            <a href="#contact" class="btn" data-i18n="hero_btn2">
                Забронювати дату
            </a>
        </div>

    </div>


    <div class="hero-right">

        <div class="hero-frame"></div>

        <div class="hero-photo">

            <!-- ГОЛОВНЕ ФОТО -->
            <img src="hero.jpg" alt="Nelli Photography">

        </div>

    </div>

</section>


<!-- MARQUEE -->

<div class="marquee">
    <div class="marquee-inner">
        <span>Weddings</span>
        <span>Family</span>
        <span>Christenings</span>
        <span>Portraits</span>
        <span>Birthday</span>
        <span>Studio</span>
        <span>Love Story</span>

        <span>Weddings</span>
        <span>Family</span>
        <span>Christenings</span>
        <span>Portraits</span>
        <span>Birthday</span>
        <span>Studio</span>
        <span>Love Story</span>
    </div>
</div>


<!-- SERVICES -->

<section class="services reveal" id="services">

    <div class="section-top">

        <div>
            <div class="section-number">01 / SERVICES</div>
            <h2 class="section-title" data-i18n="services_title">
                Що я<br>знімаю
            </h2>
        </div>

        <p class="section-description" data-i18n="services_desc">
            Кожна подія має свою атмосферу. Моє завдання —
            зберегти її так, щоб через роки ви могли знову
            відчути цей момент.
        </p>

    </div>


    <div class="service-grid">

        <div class="service">
            <span class="service-num">01</span>
            <div class="service-icon">♡</div>
            <h3 data-i18n="wedding">Весілля</h3>
            <p data-i18n="wedding_desc">
                Від ранкових зборів до останнього танцю.
            </p>
        </div>

        <div class="service">
            <span class="service-num">02</span>
            <div class="service-icon">✦</div>
            <h3 data-i18n="christening">Хрестини</h3>
            <p data-i18n="christening_desc">
                Ніжні та щирі фотографії особливого дня.
            </p>
        </div>

        <div class="service">
            <span class="service-num">03</span>
            <div class="service-icon">○</div>
            <h3 data-i18n="birthday">День народження</h3>
            <p data-i18n="birthday_desc">
                Емоції, гості, деталі та атмосфера свята.
            </p>
        </div>

        <div class="service">
            <span class="service-num">04</span>
            <div class="service-icon">⌁</div>
            <h3 data-i18n="studio">Студія</h3>
            <p data-i18n="studio_desc">
                Стильні портрети та творчі фотосесії.
            </p>
        </div>

        <div class="service">
            <span class="service-num">05</span>
            <div class="service-icon">∞</div>
            <h3 data-i18n="family">Сімейні</h3>
            <p data-i18n="family_desc">
                Живі кадри без штучних поз.
            </p>
        </div>

        <div class="service">
            <span class="service-num">06</span>
            <div class="service-icon">♡</div>
            <h3 data-i18n="lovestory">Love Story</h3>
            <p data-i18n="lovestory_desc">
                Історія двох людей у красивих кадрах.
            </p>
        </div>

    </div>

</section>


<!-- PORTFOLIO -->

<section class="reveal" id="portfolio">

    <div class="section-top">

        <div>
            <div class="section-number">02 / PORTFOLIO</div>
            <h2 class="section-title" data-i18n="portfolio_title">
                Обрані<br>історії
            </h2>
        </div>

        <p class="section-description" data-i18n="portfolio_desc">
            Тут з'являтимуться найкращі моменти з ваших
            фотосесій.
        </p>

    </div>


    <div class="portfolio-grid">

        <div class="photo">
            <img src="photo1.jpg" alt="Wedding">
            <div class="photo-label" data-i18n="wedding">Весілля</div>
        </div>

        <div class="photo">
            <img src="photo2.jpg" alt="Portrait">
            <div class="photo-label" data-i18n="portrait">Портрет</div>
        </div>

        <div class="photo">
            <img src="photo3.jpg" alt="Family">
            <div class="photo-label" data-i18n="family">Сімейна</div>
        </div>

        <div class="photo">
            <img src="photo4.jpg" alt="Studio">
            <div class="photo-label" data-i18n="studio">Студія</div>
        </div>

        <div class="photo">
            <img src="photo5.jpg" alt="Christening">
            <div class="photo-label" data-i18n="christening">Хрестини</div>
        </div>

        <div class="photo">
            <img src="photo6.jpg" alt="Birthday">
            <div class="photo-label" data-i18n="birthday">День народження</div>
        </div>

        <div class="photo">
            <img src="photo7.jpg" alt="Love Story">
            <div class="photo-label">Love Story</div>
        </div>

        <div class="photo">
            <img src="photo8.jpg" alt="Family">
            <div class="photo-label" data-i18n="family">Сімейна</div>
        </div>

    </div>

</section>


<!-- PACKAGES -->

<section class="packages reveal" id="packages">

    <div class="section-top">

        <div>
            <div class="section-number">03 / PACKAGES</div>

            <h2 class="section-title" data-i18n="packages_title">
                Формати<br>зйомки
            </h2>

        </div>

        <p class="section-description" data-i18n="packages_desc">
            Пакети можна легко змінити під ваші реальні
            ціни та умови.
        </p>

    </div>


    <div class="package-grid">

        <div class="package">

            <div class="package-name" data-i18n="package1">
                MINI
            </div>

            <div class="package-price">
                €120
            </div>

            <ul>
                <li data-i18n="p1_1">1 година зйомки</li>
                <li data-i18n="p1_2">20 оброблених фото</li>
                <li data-i18n="p1_3">Онлайн-галерея</li>
                <li data-i18n="p1_4">Термін 7–10 днів</li>
            </ul>

        </div>


        <div class="package featured">

            <div class="package-name" data-i18n="package2">
                STORY
            </div>

            <div class="package-price">
                €250
            </div>

            <ul>
                <li data-i18n="p2_1">2–3 години зйомки</li>
                <li data-i18n="p2_2">50+ оброблених фото</li>
                <li data-i18n="p2_3">Онлайн-галерея</li>
                <li data-i18n="p2_4">Допомога з локацією</li>
            </ul>

        </div>


        <div class="package">

            <div class="package-name" data-i18n="package3">
                EVENT
            </div>

            <div class="package-price">
                €450+
            </div>

            <ul>
                <li data-i18n="p3_1">Події та свята</li>
                <li data-i18n="p3_2">Велика кількість фото</li>
                <li data-i18n="p3_3">Авторська обробка</li>
                <li data-i18n="p3_4">Індивідуальний пакет</li>
            </ul>

        </div>

    </div>

</section>


<!-- ABOUT -->

<section class="about reveal" id="about">

    <div class="about-photo">
        <img src="about.jpg" alt="Nelli">
    </div>

    <div class="about-text">

        <div class="section-number">04 / ABOUT</div>

        <h2 data-i18n="about_title">
            Люди.<br>
            Емоції.<br>
            Історії.
        </h2>

        <p data-i18n="about_text">
            Я Nelli — фотограф, яка любить справжні моменти.
            Без зайвої постановки та награних емоцій.
            Мені важливо, щоб після фотосесії ви отримали
            не просто красиві фотографії, а спогади,
            до яких захочеться повертатися.
        </p>

    </div>

</section>


<!-- CONTACT -->

<section class="contact reveal" id="contact">

    <div class="section-number">05 / CONTACT</div>

    <h2 data-i18n="contact_title">
        Створимо<br>
        щось справжнє.
    </h2>

    <p data-i18n="contact_text">
        Розкажіть мені про вашу подію або ідею —
        і ми разом придумаємо найкращий формат зйомки.
    </p>

    <div class="contact-links">

        <a class="contact-link" href="https://instagram.com/" target="_blank">
            Instagram
        </a>

        <a class="contact-link" href="mailto:example@email.com">
            Email
        </a>

        <a class="contact-link" href="tel:+420000000000">
            Phone
        </a>

    </div>

</section>

</main>


<footer>

    <span>© 2026 NELLI PHOTOGRAPHY</span>

    <span data-i18n="footer">
        Prague · Czech Republic
    </span>

</footer>


<script>

/* ================= LANGUAGES ================= */

const translations = {

uk:{
nav_services:"Послуги",
nav_portfolio:"Портфоліо",
nav_packages:"Пакети",
nav_about:"Про мене",
nav_contact:"Контакти",

hero_kicker:"Photography · Prague",
hero_text:"Фотографую справжні моменти, емоції та людей такими, якими вони є. Весілля, сімейні історії, хрестини, дні народження та красиві портрети.",
hero_btn1:"Дивитися роботи",
hero_btn2:"Забронювати дату",

services_title:"Що я<br>знімаю",
services_desc:"Кожна подія має свою атмосферу. Моє завдання — зберегти її так, щоб через роки ви могли знову відчути цей момент.",

wedding:"Весілля",
wedding_desc:"Від ранкових зборів до останнього танцю.",
christening:"Хрестини",
christening_desc:"Ніжні та щирі фотографії особливого дня.",
birthday:"День народження",
birthday_desc:"Емоції, гості, деталі та атмосфера свята.",
studio:"Студія",
studio_desc:"Стильні портрети та творчі фотосесії.",
family:"Сімейні",
family_desc:"Живі кадри без штучних поз.",
lovestory:"Love Story",
lovestory_desc:"Історія двох людей у красивих кадрах.",

portfolio_title:"Обрані<br>історії",
portfolio_desc:"Тут з'являтимуться найкращі моменти з ваших фотосесій.",
portrait:"Портрет",

packages_title:"Формати<br>зйомки",
packages_desc:"Пакети можна легко змінити під ваші реальні ціни та умови.",

package1:"MINI",
package2:"STORY",
package3:"EVENT",

p1_1:"1 година зйомки",
p1_2:"20 оброблених фото",
p1_3:"Онлайн-галерея",
p1_4:"Термін 7–10 днів",

p2_1:"2–3 години зйомки",
p2_2:"50+ оброблених фото",
p2_3:"Онлайн-галерея",
p2_4:"Допомога з локацією",

p3_1:"Події та свята",
p3_2:"Велика кількість фото",
p3_3:"Авторська обробка",
p3_4:"Індивідуальний пакет",

about_title:"Люди.<br>Емоції.<br>Історії.",
about_text:"Я Nelli — фотограф, яка любить справжні моменти. Без зайвої постановки та награних емоцій. Мені важливо, щоб після фотосесії ви отримали не просто красиві фотографії, а спогади, до яких захочеться повертатися.",

contact_title:"Створимо<br>щось справжнє.",
contact_text:"Розкажіть мені про вашу подію або ідею — і ми разом придумаємо найкращий формат зйомки.",

footer:"Prague · Czech Republic"
},

ru:{
nav_services:"Услуги",
nav_portfolio:"Портфолио",
nav_packages:"Пакеты",
nav_about:"Обо мне",
nav_contact:"Контакты",

hero_kicker:"Photography · Prague",
hero_text:"Фотографирую настоящие моменты, эмоции и людей такими, какие они есть. Свадьбы, семейные истории, крестины, дни рождения и красивые портреты.",
hero_btn1:"Смотреть работы",
hero_btn2:"Забронировать дату",

services_title:"Что я<br>снимаю",
services_desc:"Каждое событие имеет свою атмосферу. Моя задача — сохранить её так, чтобы спустя годы вы снова могли почувствовать этот момент.",

wedding:"Свадьбы",
wedding_desc:"От утренних сборов до последнего танца.",
christening:"Крестины",
christening_desc:"Нежные и искренние фотографии особенного дня.",
birthday:"День рождения",
birthday_desc:"Эмоции, гости, детали и атмосфера праздника.",
studio:"Студия",
studio_desc:"Стильные портреты и творческие фотосессии.",
family:"Семейные",
family_desc:"Живые кадры без искусственных поз.",
lovestory:"Love Story",
lovestory_desc:"История двух людей в красивых кадрах.",

portfolio_title:"Избранные<br>истории",
portfolio_desc:"Здесь будут лучшие моменты ваших фотосессий.",
portrait:"Портрет",

packages_title:"Форматы<br>съёмки",
packages_desc:"Пакеты можно легко изменить под ваши реальные цены и условия.",

package1:"MINI",
package2:"STORY",
package3:"EVENT",

p1_1:"1 час съёмки",
p1_2:"20 обработанных фото",
p1_3:"Онлайн-галерея",
p1_4:"Срок 7–10 дней",

p2_1:"2–3 часа съёмки",
p2_2:"50+ обработанных фото",
p2_3:"Онлайн-галерея",
p2_4:"Помощь с локацией",

p3_1:"События и праздники",
p3_2:"Большое количество фото",
p3_3:"Авторская обработка",
p3_4:"Индивидуальный пакет",

about_title:"Люди.<br>Эмоции.<br>Истории.",
about_text:"Я Nelli — фотограф, которая любит настоящие моменты. Без лишней постановки и наигранных эмоций. Мне важно, чтобы после фотосессии вы получили не просто красивые фотографии, а воспоминания, к которым захочется возвращаться.",

contact_title:"Создадим<br>что-то настоящее.",
contact_text:"Расскажите мне о вашем событии или идее — и мы вместе придумаем лучший формат съёмки.",

footer:"Prague · Czech Republic"
},

en:{
nav_services:"Services",
nav_portfolio:"Portfolio",
nav_packages:"Packages",
nav_about:"About",
nav_contact:"Contact",

hero_kicker:"Photography · Prague",
hero_text:"I capture real moments, emotions and people exactly as they are. Weddings, family stories, christenings, birthdays and beautiful portraits.",
hero_btn1:"View portfolio",
hero_btn2:"Book a date",

services_title:"What I<br>shoot",
services_desc:"Every event has its own atmosphere. My job is to preserve it so you can feel that moment again years later.",

wedding:"Weddings",
wedding_desc:"From getting ready to the last dance.",
christening:"Christenings",
christening_desc:"Tender and honest photographs of a special day.",
birthday:"Birthdays",
birthday_desc:"Emotions, guests, details and the atmosphere of the celebration.",
studio:"Studio",
studio_desc:"Stylish portraits and creative photoshoots.",
family:"Family",
family_desc:"Natural photographs without forced poses.",
lovestory:"Love Story",
lovestory_desc:"The story of two people in beautiful frames.",

portfolio_title:"Selected<br>stories",
portfolio_desc:"The best moments from your photoshoots will appear here.",
portrait:"Portrait",

packages_title:"Photography<br>packages",
packages_desc:"Packages can easily be changed according to your real prices and conditions.",

package1:"MINI",
package2:"STORY",
package3:"EVENT",

p1_1:"1 hour shoot",
p1_2:"20 edited photos",
p1_3:"Online gallery",
p1_4:"7–10 day delivery",

p2_1:"2–3 hour shoot",
p2_2:"50+ edited photos",
p2_3:"Online gallery",
p2_4:"Location assistance",

p3_1:"Events & celebrations",
p3_2:"Large number of photos",
p3_3:"Professional editing",
p3_4:"Custom package",

about_title:"People.<br>Emotions.<br>Stories.",
about_text:"I’m Nelli — a photographer who loves real moments. No unnecessary posing or fake emotions. I want you to leave every photoshoot with more than beautiful images — I want you to have memories you will want to return to.",

contact_title:"Let's create<br>something real.",
contact_text:"Tell me about your event or idea and together we will create the perfect photography experience.",

footer:"Prague · Czech Republic"
},

cs:{
nav_services:"Služby",
nav_portfolio:"Portfolio",
nav_packages:"Balíčky",
nav_about:"O mně",
nav_contact:"Kontakt",

hero_kicker:"Photography · Prague",
hero_text:"Fotografuji skutečné okamžiky, emoce a lidi takové, jací opravdu jsou. Svatby, rodinné příběhy, křtiny, narozeniny a krásné portréty.",
hero_btn1:"Prohlédnout portfolio",
hero_btn2:"Rezervovat termín",

services_title:"Co<br>fotím",
services_desc:"Každá událost má svou atmosféru. Mým úkolem je zachytit ji tak, abyste tento okamžik mohli znovu prožít i za několik let.",

wedding:"Svatby",
wedding_desc:"Od ranních příprav až po poslední tanec.",
christening:"Křtiny",
christening_desc:"Jemné a upřímné fotografie výjimečného dne.",
birthday:"Narozeniny",
birthday_desc:"Emoce, hosté, detaily a atmosféra oslavy.",
studio:"Studio",
studio_desc:"Stylové portréty a kreativní focení.",
family:"Rodinné",
family_desc:"Přirozené fotografie bez nucených póz.",
lovestory:"Love Story",
lovestory_desc:"Příběh dvou lidí v krásných fotografiích.",

portfolio_title:"Vybrané<br>příběhy",
portfolio_desc:"Zde se objeví nejlepší okamžiky z vašich focení.",
portrait:"Portrét",

packages_title:"Formáty<br>focení",
packages_desc:"Balíčky lze snadno upravit podle vašich skutečných cen a podmínek.",

package1:"MINI",
package2:"STORY",
package3:"EVENT",

p1_1:"1 hodina focení",
p1_2:"20 upravených fotografií",
p1_3:"Online galerie",
p1_4:"Dodání 7–10 dní",

p2_1:"2–3 hodiny focení",
p2_2:"50+ upravených fotografií",
p2_3:"Online galerie",
p2_4:"Pomoc s výběrem lokace",

p3_1:"Akce a oslavy",
p3_2:"Velké množství fotografií",
p3_3:"Profesionální úprava",
p3_4:"Individuální balíček",

about_title:"Lidé.<br>Emoce.<br>Příběhy.",
about_text:"Jsem Nelli — fotografka, která miluje opravdové okamžiky. Bez zbytečného aranžování a hraných emocí. Chci, abyste si z focení odnesli nejen krásné fotografie, ale také vzpomínky, ke kterým se budete chtít vracet.",

contact_title:"Vytvořme<br>něco opravdového.",
contact_text:"Napište mi o vaší události nebo nápadu a společně vytvoříme ideální formát focení.",

footer:"Praha · Česká republika"
}

};


/* LANGUAGE SWITCH */

const langBtn = document.getElementById("langBtn");
const langMenu = document.getElementById("langMenu");

langBtn.addEventListener("click",()=>{
    langMenu.classList.toggle("open");
});

document.querySelectorAll(".lang-option").forEach(option=>{

    option.addEventListener("click",()=>{

        const lang = option.dataset.lang;

        changeLanguage(lang);

        langMenu.classList.remove("open");

    });

});


function changeLanguage(lang){

    const data = translations[lang];

    document.documentElement.lang = lang;

    document.querySelectorAll("[data-i18n]").forEach(element=>{

        const key = element.dataset.i18n;

        if(data[key]){
            element.innerHTML = data[key];
        }

    });


    const info = {

        uk:["🇺🇦","UA"],
        ru:["🇷🇺","RU"],
        en:["🇬🇧","EN"],
        cs:["🇨🇿","CZ"]

    };

    document.getElementById("currentFlag").textContent = info[lang][0];

    document.getElementById("currentLang").textContent = info[lang][1];

    localStorage.setItem("nelliLanguage",lang);
}


/* LOAD SAVED LANGUAGE */

const savedLanguage = localStorage.getItem("nelliLanguage") || "uk";

changeLanguage(savedLanguage);


/* ================= MOBILE MENU ================= */

const menuBtn = document.getElementById("menuBtn");
const nav = document.getElementById("nav");

menuBtn.addEventListener("click",()=>{
    nav.classList.toggle("open");
});

document.querySelectorAll("nav a").forEach(link=>{
    link.addEventListener("click",()=>{
        nav.classList.remove("open");
    });
});


/* ================= HEADER ================= */

window.addEventListener("scroll",()=>{

    const header = document.getElementById("header");

    if(window.scrollY > 50){
        header.classList.add("scrolled");
    }else{
        header.classList.remove("scrolled");
    }

});


/* ================= REVEAL ANIMATION ================= */

const observer = new IntersectionObserver(
    entries=>{
        entries.forEach(entry=>{
            if(entry.isIntersecting){
                entry.target.classList.add("visible");
            }
        });
    },
    {threshold:.12}
);

document.querySelectorAll(".reveal").forEach(el=>{
    observer.observe(el);
});


/* CLOSE LANGUAGE MENU */

document.addEventListener("click",(e)=>{

    if(!e.target.closest(".lang-wrap")){
        langMenu.classList.remove("open");
    }

});

</script>

</body>
</html>
