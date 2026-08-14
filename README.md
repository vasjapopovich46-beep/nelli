<!DOCTYPE html>
<html lang="uk">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>NELLI — Photography</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600;700&family=Inter:wght@300;400;500;600&display=swap');

:root{
    --bg:#0b0b0b;
    --bg2:#111111;
    --card:#151515;
    --text:#f2eee8;
    --muted:#99948d;
    --line:rgba(255,255,255,.11);
    --accent:#d6c4a3;
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
    z-index:-1;
    background:
        radial-gradient(circle at 15% 20%,rgba(214,196,163,.055),transparent 30%),
        radial-gradient(circle at 85% 75%,rgba(255,255,255,.035),transparent 30%);
}

a{
    text-decoration:none;
    color:inherit;
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
    padding:0 6%;
    display:flex;
    align-items:center;
    justify-content:space-between;
    z-index:1000;
    transition:.4s ease;
}

header.scrolled{
    background:rgba(10,10,10,.88);
    backdrop-filter:blur(20px);
    border-bottom:1px solid var(--line);
}

.logo{
    display:flex;
    align-items:center;
    gap:13px;
}

.logo-mark{
    width:43px;
    height:43px;
    border:1px solid rgba(255,255,255,.3);
    border-radius:50%;
    display:flex;
    align-items:center;
    justify-content:center;
    font-family:"Cormorant Garamond",serif;
    font-size:20px;
    letter-spacing:-1px;
}

.logo-text{
    font-family:"Cormorant Garamond",serif;
    font-size:27px;
    letter-spacing:5px;
}

nav{
    display:flex;
    gap:30px;
}

nav a{
    font-size:11px;
    text-transform:uppercase;
    letter-spacing:2px;
    color:#c8c3bc;
    transition:.3s;
}

nav a:hover{
    color:white;
}

.header-right{
    display:flex;
    align-items:center;
    gap:15px;
}

/* LANGUAGE */

.lang-wrap{
    position:relative;
}

.lang-btn{
    border:1px solid var(--line);
    background:rgba(255,255,255,.035);
    color:white;
    padding:9px 14px;
    border-radius:50px;
    cursor:pointer;
    display:flex;
    align-items:center;
    gap:7px;
}

.lang-menu{
    position:absolute;
    right:0;
    top:50px;
    width:175px;
    background:#161616;
    border:1px solid var(--line);
    border-radius:15px;
    padding:8px;
    opacity:0;
    visibility:hidden;
    transform:translateY(-8px);
    transition:.3s;
}

.lang-menu.open{
    opacity:1;
    visibility:visible;
    transform:translateY(0);
}

.lang-option{
    display:block;
    width:100%;
    border:0;
    background:transparent;
    color:#eee;
    text-align:left;
    padding:11px;
    border-radius:9px;
    cursor:pointer;
}

.lang-option:hover{
    background:rgba(255,255,255,.08);
}

.menu-btn{
    display:none;
    border:0;
    background:none;
    color:white;
    font-size:24px;
    cursor:pointer;
}

/* ================= HERO ================= */

.hero{
    min-height:100vh;
    padding:130px 7% 80px;
    display:grid;
    grid-template-columns:1fr 1fr;
    align-items:center;
    gap:70px;
}

.hero-content{
    animation:fadeUp 1.1s ease both;
}

.eyebrow{
    color:var(--accent);
    text-transform:uppercase;
    letter-spacing:5px;
    font-size:10px;
    margin-bottom:25px;
}

.hero h1{
    font-family:"Cormorant Garamond",serif;
    font-weight:500;
    font-size:clamp(75px,10vw,145px);
    line-height:.72;
    letter-spacing:-6px;
}

.hero h1 span{
    display:block;
    margin-left:70px;
    font-style:italic;
    color:#c9c2b8;
}

.hero-description{
    color:var(--muted);
    line-height:1.8;
    max-width:500px;
    margin:45px 0 30px;
}

.buttons{
    display:flex;
    flex-wrap:wrap;
    gap:12px;
}

.btn{
    padding:15px 23px;
    border-radius:50px;
    border:1px solid var(--line);
    transition:.35s;
}

.btn:hover{
    transform:translateY(-4px);
}

.btn.primary{
    background:#eee9e1;
    color:#111;
}

.hero-visual{
    height:650px;
    position:relative;
}

.hero-frame{
    position:absolute;
    width:70%;
    height:80%;
    left:0;
    bottom:0;
    border:1px solid rgba(214,196,163,.4);
}

.hero-placeholder{
    position:absolute;
    right:0;
    top:4%;
    width:76%;
    height:91%;
    overflow:hidden;
    background:
        linear-gradient(145deg,#24221f,#111);
    display:flex;
    align-items:center;
    justify-content:center;
    text-align:center;
}

.placeholder-content{
    position:relative;
    z-index:2;
    padding:30px;
}

.placeholder-icon{
    font-size:50px;
    opacity:.65;
    margin-bottom:20px;
}

.placeholder-title{
    font-family:"Cormorant Garamond",serif;
    font-size:36px;
}

.placeholder-small{
    color:#888;
    font-size:11px;
    letter-spacing:2px;
    text-transform:uppercase;
    margin-top:10px;
}

/* ================= MARQUEE ================= */

.marquee{
    overflow:hidden;
    white-space:nowrap;
    border-top:1px solid var(--line);
    border-bottom:1px solid var(--line);
    padding:20px 0;
}

.marquee-track{
    display:inline-block;
    animation:marquee 30s linear infinite;
}

.marquee span{
    margin:0 35px;
    font-family:"Cormorant Garamond",serif;
    font-style:italic;
    font-size:25px;
    color:#c8c0b6;
}

/* ================= SECTIONS ================= */

section{
    padding:120px 7%;
}

.section-header{
    display:flex;
    justify-content:space-between;
    align-items:end;
    gap:40px;
    margin-bottom:55px;
}

.section-number{
    color:var(--accent);
    font-size:10px;
    letter-spacing:3px;
    margin-bottom:20px;
}

.section-title{
    font-family:"Cormorant Garamond",serif;
    font-weight:500;
    font-size:clamp(55px,7vw,95px);
    line-height:.82;
}

.section-description{
    max-width:390px;
    color:var(--muted);
    line-height:1.8;
}

/* ================= SERVICES ================= */

.services{
    background:#101010;
}

.services-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:2px;
}

.service{
    min-height:310px;
    padding:35px;
    background:#151515;
    border:1px solid rgba(255,255,255,.04);
    position:relative;
    overflow:hidden;
    transition:.5s;
}

.service:hover{
    transform:translateY(-8px);
    background:#191919;
}

.service-number{
    color:#666;
    font-size:11px;
}

.service-symbol{
    font-size:38px;
    margin:45px 0 25px;
    color:#cfc6b9;
}

.service h3{
    font-family:"Cormorant Garamond",serif;
    font-size:34px;
    font-weight:500;
}

.service p{
    color:var(--muted);
    font-size:13px;
    line-height:1.7;
    margin-top:10px;
}

/* ================= PORTFOLIO ================= */

.portfolio-grid{
    display:grid;
    grid-template-columns:repeat(12,1fr);
    grid-auto-rows:240px;
    gap:12px;
}

.portfolio-card{
    position:relative;
    overflow:hidden;
    background:#181818;
    border:1px solid rgba(255,255,255,.05);
}

.portfolio-card:nth-child(1){
    grid-column:span 5;
    grid-row:span 2;
}

.portfolio-card:nth-child(2){
    grid-column:span 7;
}

.portfolio-card:nth-child(3){
    grid-column:span 4;
}

.portfolio-card:nth-child(4){
    grid-column:span 3;
}

.portfolio-card:nth-child(5){
    grid-column:span 5;
}

.portfolio-card:nth-child(6){
    grid-column:span 4;
}

.portfolio-card:nth-child(7){
    grid-column:span 8;
}

.portfolio-card:nth-child(8){
    grid-column:span 4;
}

.photo-placeholder{
    width:100%;
    height:100%;
    display:flex;
    align-items:center;
    justify-content:center;
    text-align:center;
    padding:20px;
    position:relative;
    transition:.6s;
}

.photo-placeholder:before{
    content:"";
    position:absolute;
    inset:0;
    background:
        radial-gradient(circle at 30% 30%,rgba(214,196,163,.12),transparent 35%),
        linear-gradient(135deg,#1d1d1d,#101010);
}

.portfolio-card:hover .photo-placeholder{
    transform:scale(1.04);
}

.photo-placeholder-content{
    position:relative;
    z-index:2;
}

.photo-number{
    font-size:10px;
    letter-spacing:4px;
    color:#777;
    margin-bottom:13px;
}

.photo-title{
    font-family:"Cormorant Garamond",serif;
    font-size:32px;
}

.photo-note{
    font-size:9px;
    color:#777;
    letter-spacing:2px;
    text-transform:uppercase;
    margin-top:8px;
}

/* ================= ABOUT ================= */

.about{
    display:grid;
    grid-template-columns:.8fr 1.2fr;
    gap:100px;
    align-items:center;
    background:#101010;
}

.about-placeholder{
    height:620px;
    background:
        radial-gradient(circle at 60% 30%,rgba(214,196,163,.12),transparent 35%),
        linear-gradient(150deg,#202020,#101010);
    display:flex;
    align-items:center;
    justify-content:center;
    text-align:center;
}

.about-placeholder-inner{
    padding:30px;
}

.about-placeholder-icon{
    font-size:55px;
    margin-bottom:20px;
}

.about-placeholder-title{
    font-family:"Cormorant Garamond",serif;
    font-size:36px;
}

.about-placeholder-small{
    color:#777;
    font-size:10px;
    letter-spacing:2px;
    margin-top:10px;
}

.about-text h2{
    font-family:"Cormorant Garamond",serif;
    font-weight:500;
    font-size:80px;
    line-height:.82;
    margin-bottom:35px;
}

.about-text p{
    max-width:600px;
    color:var(--muted);
    line-height:1.9;
}

/* ================= CONTACT ================= */

.contact{
    min-height:75vh;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    text-align:center;
    background:
        radial-gradient(circle at center,rgba(214,196,163,.065),transparent 45%);
}

.contact h2{
    font-family:"Cormorant Garamond",serif;
    font-size:clamp(70px,11vw,150px);
    line-height:.78;
    font-weight:500;
}

.contact p{
    max-width:480px;
    color:var(--muted);
    line-height:1.8;
    margin:35px 0;
}

.contact-buttons{
    display:flex;
    flex-wrap:wrap;
    justify-content:center;
    gap:12px;
}

.contact-button{
    padding:14px 22px;
    border:1px solid var(--line);
    border-radius:50px;
    transition:.3s;
}

.contact-button:hover{
    background:#eee9e1;
    color:#111;
}

/* ================= FOOTER ================= */

footer{
    border-top:1px solid var(--line);
    padding:35px 7%;
    display:flex;
    justify-content:space-between;
    color:#666;
    font-size:11px;
}

/* ================= REVEAL ================= */

.reveal{
    opacity:0;
    transform:translateY(45px);
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
    from{
        transform:translateX(0);
    }
    to{
        transform:translateX(-50%);
    }
}

/* ================= MOBILE ================= */

@media(max-width:900px){

    header{
        padding:0 5%;
    }

    nav{
        display:none;
        position:absolute;
        top:82px;
        left:0;
        width:100%;
        background:#101010;
        padding:25px;
        flex-direction:column;
        gap:22px;
        border-bottom:1px solid var(--line);
    }

    nav.open{
        display:flex;
    }

    .menu-btn{
        display:block;
    }

    .hero{
        grid-template-columns:1fr;
        padding-top:135px;
    }

    .hero h1{
        font-size:85px;
    }

    .hero-visual{
        height:500px;
    }

    .services-grid{
        grid-template-columns:1fr;
    }

    .portfolio-grid{
        grid-template-columns:1fr 1fr;
        grid-auto-rows:220px;
    }

    .portfolio-card:nth-child(n){
        grid-column:span 1;
        grid-row:span 1;
    }

    .portfolio-card:first-child{
        grid-column:span 2;
        grid-row:span 2;
    }

    .about{
        grid-template-columns:1fr;
        gap:50px;
    }

    .about-placeholder{
        height:500px;
    }

    .about-text h2{
        font-size:65px;
    }
}

@media(max-width:550px){

    section{
        padding:90px 5%;
    }

    .logo-text{
        font-size:21px;
        letter-spacing:3px;
    }

    .logo-mark{
        width:38px;
        height:38px;
    }

    .hero h1{
        font-size:68px;
    }

    .hero h1 span{
        margin-left:35px;
    }

    .hero-visual{
        height:420px;
    }

    .portfolio-grid{
        grid-template-columns:1fr;
    }

    .portfolio-card:first-child{
        grid-column:span 1;
    }

    .section-header{
        flex-direction:column;
        align-items:flex-start;
    }

    footer{
        flex-direction:column;
        gap:12px;
    }
}
</style>
</head>

<body>

<!-- ================= HEADER ================= -->

<header id="header">

    <a href="#home" class="logo">

        <div class="logo-mark">
            N
        </div>

        <div class="logo-text">
            NELLI
        </div>

    </a>

    <nav id="nav">

        <a href="#services" data-i18n="nav_services">
            Послуги
        </a>

        <a href="#portfolio" data-i18n="nav_portfolio">
            Портфоліо
        </a>

        <a href="#about" data-i18n="nav_about">
            Про мене
        </a>

        <a href="#contact" data-i18n="nav_contact">
            Контакти
        </a>

    </nav>

    <div class="header-right">

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

        <button class="menu-btn" id="menuBtn">
            ☰
        </button>

    </div>

</header>


<!-- ================= MAIN ================= -->

<main>

<!-- HERO -->

<section class="hero" id="home">

    <div class="hero-content">

        <div class="eyebrow" data-i18n="hero_eyebrow">
            Photography · Prague
        </div>

        <h1>
            Nelli
            <span>stories.</span>
        </h1>

        <p class="hero-description" data-i18n="hero_description">
            Фотографую справжні моменти, емоції та історії,
            які хочеться пам'ятати.
        </p>

        <div class="buttons">

            <a href="#portfolio" class="btn primary" data-i18n="hero_portfolio">
                Переглянути портфоліо
            </a>

            <a href="#contact" class="btn" data-i18n="hero_contact">
                Зв'язатися
            </a>

        </div>

    </div>


    <div class="hero-visual">

        <div class="hero-frame"></div>

        <div class="hero-placeholder">

            <div class="placeholder-content">

                <div class="placeholder-icon">
                    ◇
                </div>

                <div class="placeholder-title" data-i18n="hero_photo">
                    Головне фото
                </div>

                <div class="placeholder-small" data-i18n="photo_replace">
                    тут буде фотографія Nelli
                </div>

            </div>

        </div>

    </div>

</section>


<!-- MARQUEE -->

<div class="marquee">

    <div class="marquee-track">

        <span>Weddings</span>
        <span>Family</span>
        <span>Christenings</span>
        <span>Birthday</span>
        <span>Studio</span>
        <span>Portraits</span>
        <span>Love Story</span>

        <span>Weddings</span>
        <span>Family</span>
        <span>Christenings</span>
        <span>Birthday</span>
        <span>Studio</span>
        <span>Portraits</span>
        <span>Love Story</span>

    </div>

</div>


<!-- SERVICES -->

<section class="services reveal" id="services">

    <div class="section-header">

        <div>

            <div class="section-number">
                01 / SERVICES
            </div>

            <h2 class="section-title" data-i18n="services_title">
                Що я<br>знімаю
            </h2>

        </div>

        <p class="section-description" data-i18n="services_description">
            Від великих свят до маленьких сімейних моментів.
            Кожна зйомка має свою атмосферу.
        </p>

    </div>


    <div class="services-grid">

        <div class="service">

            <div class="service-number">01</div>

            <div class="service-symbol">♡</div>

            <h3 data-i18n="wedding">
                Весілля
            </h3>

            <p data-i18n="wedding_desc">
                День, який хочеться пам'ятати назавжди.
            </p>

        </div>


        <div class="service">

            <div class="service-number">02</div>

            <div class="service-symbol">✦</div>

            <h3 data-i18n="christening">
                Хрестини
            </h3>

            <p data-i18n="christening_desc">
                Ніжні моменти особливого дня.
            </p>

        </div>


        <div class="service">

            <div class="service-number">03</div>

            <div class="service-symbol">○</div>

            <h3 data-i18n="birthday">
                День народження
            </h3>

            <p data-i18n="birthday_desc">
                Емоції, люди та атмосфера свята.
            </p>

        </div>


        <div class="service">

            <div class="service-number">04</div>

            <div class="service-symbol">⌁</div>

            <h3 data-i18n="studio">
                Студія
            </h3>

            <p data-i18n="studio_desc">
                Стильні портрети та творчі фотосесії.
            </p>

        </div>


        <div class="service">

            <div class="service-number">05</div>

            <div class="service-symbol">∞</div>

            <h3 data-i18n="family">
                Сімейні
            </h3>

            <p data-i18n="family_desc">
                Живі кадри без зайвої постановки.
            </p>

        </div>


        <div class="service">

            <div class="service-number">06</div>

            <div class="service-symbol">♡</div>

            <h3 data-i18n="lovestory">
                Love Story
            </h3>

            <p data-i18n="lovestory_desc">
                Історія двох людей.
            </p>

        </div>

    </div>

</section>


<!-- PORTFOLIO -->

<section class="reveal" id="portfolio">

    <div class="section-header">

        <div>

            <div class="section-number">
                02 / PORTFOLIO
            </div>

            <h2 class="section-title" data-i18n="portfolio_title">
                Обрані<br>історії
            </h2>

        </div>

        <p class="section-description" data-i18n="portfolio_description">
            Тут будуть справжні фотографії Nelli.
            Поки що це стильні демонстраційні блоки.
        </p>

    </div>


    <div class="portfolio-grid">


        <div class="portfolio-card">

            <div class="photo-placeholder">

                <div class="photo-placeholder-content">

                    <div class="photo-number">
                        01
                    </div>

                    <div class="photo-title" data-i18n="photo_wedding">
                        Фото весілля
                    </div>

                    <div class="photo-note" data-i18n="replace_later">
                        замінити на фото
                    </div>

                </div>

            </div>

        </div>


        <div class="portfolio-card">

            <div class="photo-placeholder">

                <div class="photo-placeholder-content">

                    <div class="photo-number">
                        02
                    </div>

                    <div class="photo-title" data-i18n="photo_christening">
                        Фото хрестин
                    </div>

                    <div class="photo-note" data-i18n="replace_later">
                        замінити на фото
                    </div>

                </div>

            </div>

        </div>


        <div class="portfolio-card">

            <div class="photo-placeholder">

                <div class="photo-placeholder-content">

                    <div class="photo-number">
                        03
                    </div>

                    <div class="photo-title" data-i18n="photo_birthday">
                        Фото дня народження
                    </div>

                    <div class="photo-note" data-i18n="replace_later">
                        замінити на фото
                    </div>

                </div>

            </div>

        </div>


        <div class="portfolio-card">

            <div class="photo-placeholder">

                <div class="photo-placeholder-content">

                    <div class="photo-number">
                        04
                    </div>

                    <div class="photo-title" data-i18n="photo_studio">
                        Фото студії
                    </div>

                    <div class="photo-note" data-i18n="replace_later">
                        замінити на фото
                    </div>

                </div>

            </div>

        </div>


        <div class="portfolio-card">

            <div class="photo-placeholder">

                <div class="photo-placeholder-content">

                    <div class="photo-number">
                        05
                    </div>

                    <div class="photo-title" data-i18n="photo_family">
                        Фото сімейної зйомки
                    </div>

                    <div class="photo-note" data-i18n="replace_later">
                        замінити на фото
                    </div>

                </div>

            </div>

        </div>


        <div class="portfolio-card">

            <div class="photo-placeholder">

                <div class="photo-placeholder-content">

                    <div class="photo-number">
                        06
                    </div>

                    <div class="photo-title" data-i18n="photo_portrait">
                        Фото портретів
                    </div>

                    <div class="photo-note" data-i18n="replace_later">
                        замінити на фото
                    </div>

                </div>

            </div>

        </div>


        <div class="portfolio-card">

            <div class="photo-placeholder">

                <div class="photo-placeholder-content">

                    <div class="photo-number">
                        07
                    </div>

                    <div class="photo-title">
                        Love Story
                    </div>

                    <div class="photo-note" data-i18n="replace_later">
                        замінити на фото
                    </div>

                </div>

            </div>

        </div>


        <div class="portfolio-card">

            <div class="photo-placeholder">

                <div class="photo-placeholder-content">

                    <div class="photo-number">
                        08
                    </div>

                    <div class="photo-title" data-i18n="photo_event">
                        Фото події
                    </div>

                    <div class="photo-note" data-i18n="replace_later">
                        замінити на фото
                    </div>

                </div>

            </div>

        </div>


    </div>

</section>


<!-- ABOUT -->

<section class="about reveal" id="about">

    <div class="about-placeholder">

        <div class="about-placeholder-inner">

            <div class="about-placeholder-icon">
                ◇
            </div>

            <div class="about-placeholder-title" data-i18n="about_photo">
                Фото Nelli
            </div>

            <div class="about-placeholder-small" data-i18n="replace_later">
                замінити на фото
            </div>

        </div>

    </div>


    <div class="about-text">

        <div class="section-number">
            03 / ABOUT
        </div>

        <h2 data-i18n="about_title">
            Люди.<br>
            Емоції.<br>
            Історії.
        </h2>

        <p data-i18n="about_text">
            Я Nelli — фотограф, яка любить справжні моменти.
            Без зайвої постановки та награних емоцій.
            Мені важливо зберігати не просто красиві кадри,
            а спогади, до яких хочеться повертатися.
        </p>

    </div>

</section>


<!-- CONTACT -->

<section class="contact reveal" id="contact">

    <div class="section-number">
        04 / CONTACT
    </div>

    <h2 data-i18n="contact_title">
        Створимо<br>
        щось справжнє.
    </h2>

    <p data-i18n="contact_text">
        Розкажіть про вашу подію або ідею —
        і разом створимо красиву історію.
    </p>

    <div class="contact-buttons">

        <a href="#" class="contact-button">
            Instagram
        </a>

        <a href="#" class="contact-button">
            Email
        </a>

        <a href="#" class="contact-button">
            Telegram
        </a>

    </div>

</section>

</main>


<!-- FOOTER -->

<footer>

    <span>
        © 2026 NELLI PHOTOGRAPHY
    </span>

    <span data-i18n="footer">
        Prague · Czech Republic
    </span>

</footer>


<script>

/* ================= TRANSLATIONS ================= */

const translations = {

uk:{

nav_services:"Послуги",
nav_portfolio:"Портфоліо",
nav_about:"Про мене",
nav_contact:"Контакти",

hero_eyebrow:"Photography · Prague",

hero_description:
"Фотографую справжні моменти, емоції та історії, які хочеться пам'ятати.",

hero_portfolio:"Переглянути портфоліо",
hero_contact:"Зв'язатися",

hero_photo:"Головне фото",
photo_replace:"тут буде фотографія Nelli",

services_title:"Що я<br>знімаю",

services_description:
"Від великих свят до маленьких сімейних моментів. Кожна зйомка має свою атмосферу.",

wedding:"Весілля",
wedding_desc:"День, який хочеться пам'ятати назавжди.",

christening:"Хрестини",
christening_desc:"Ніжні моменти особливого дня.",

birthday:"День народження",
birthday_desc:"Емоції, люди та атмосфера свята.",

studio:"Студія",
studio_desc:"Стильні портрети та творчі фотосесії.",

family:"Сімейні",
family_desc:"Живі кадри без зайвої постановки.",

lovestory:"Love Story",
lovestory_desc:"Історія двох людей.",

portfolio_title:"Обрані<br>історії",

portfolio_description:
"Тут будуть справжні фотографії Nelli. Поки що це стильні демонстраційні блоки.",

photo_wedding:"Фото весілля",
photo_christening:"Фото хрестин",
photo_birthday:"Фото дня народження",
photo_studio:"Фото студії",
photo_family:"Фото сімейної зйомки",
photo_portrait:"Фото портретів",
photo_event:"Фото події",

replace_later:"замінити на фото",

about_photo:"Фото Nelli",

about_title:"Люди.<br>Емоції.<br>Історії.",

about_text:
"Я Nelli — фотограф, яка любить справжні моменти. Без зайвої постановки та награних емоцій. Мені важливо зберігати не просто красиві кадри, а спогади, до яких хочеться повертатися.",

contact_title:"Створимо<br>щось справжнє.",

contact_text:
"Розкажіть про вашу подію або ідею — і разом створимо красиву історію.",

footer:"Prague · Czech Republic"

},


ru:{

nav_services:"Услуги",
nav_portfolio:"Портфолио",
nav_about:"Обо мне",
nav_contact:"Контакты",

hero_eyebrow:"Photography · Prague",

hero_description:
"Фотографирую настоящие моменты, эмоции и истории, которые хочется помнить.",

hero_portfolio:"Посмотреть портфолио",
hero_contact:"Связаться",

hero_photo:"Главное фото",
photo_replace:"здесь будет фотография Nelli",

services_title:"Что я<br>снимаю",

services_description:
"От больших праздников до маленьких семейных моментов. Каждая съёмка имеет свою атмосферу.",

wedding:"Свадьбы",
wedding_desc:"День, который хочется помнить всегда.",

christening:"Крестины",
christening_desc:"Нежные моменты особенного дня.",

birthday:"День рождения",
birthday_desc:"Эмоции, люди и атмосфера праздника.",

studio:"Студия",
studio_desc:"Стильные портреты и творческие фотосессии.",

family:"Семейные",
family_desc:"Живые кадры без лишней постановки.",

lovestory:"Love Story",
lovestory_desc:"История двух людей.",

portfolio_title:"Избранные<br>истории",

portfolio_description:
"Здесь будут настоящие фотографии Nelli. Пока это стильные демонстрационные блоки.",

photo_wedding:"Фото свадьбы",
photo_christening:"Фото крестин",
photo_birthday:"Фото дня рождения",
photo_studio:"Фото студии",
photo_family:"Фото семейной съёмки",
photo_portrait:"Фото портретов",
photo_event:"Фото события",

replace_later:"заменить на фото",

about_photo:"Фото Nelli",

about_title:"Люди.<br>Эмоции.<br>Истории.",

about_text:
"Я Nelli — фотограф, которая любит настоящие моменты. Без лишней постановки и наигранных эмоций. Мне важно сохранять не просто красивые кадры, а воспоминания, к которым хочется возвращаться.",

contact_title:"Создадим<br>что-то настоящее.",

contact_text:
"Расскажите о вашем событии или идее — и вместе создадим красивую историю.",

footer:"Prague · Czech Republic"

},


en:{

nav_services:"Services",
nav_portfolio:"Portfolio",
nav_about:"About",
nav_contact:"Contact",

hero_eyebrow:"Photography · Prague",

hero_description:
"I capture real moments, emotions and stories worth remembering.",

hero_portfolio:"View portfolio",
hero_contact:"Get in touch",

hero_photo:"Main photo",
photo_replace:"Nelli's photograph will be here",

services_title:"What I<br>shoot",

services_description:
"From big celebrations to small family moments. Every photoshoot has its own atmosphere.",

wedding:"Weddings",
wedding_desc:"A day worth remembering forever.",

christening:"Christenings",
christening_desc:"Tender moments from a special day.",

birthday:"Birthdays",
birthday_desc:"Emotions, people and celebration.",

studio:"Studio",
studio_desc:"Stylish portraits and creative photoshoots.",

family:"Family",
family_desc:"Natural photographs without unnecessary posing.",

lovestory:"Love Story",
lovestory_desc:"The story of two people.",

portfolio_title:"Selected<br>stories",

portfolio_description:
"Real Nelli photographs will appear here. For now these are stylish demonstration blocks.",

photo_wedding:"Wedding photos",
photo_christening:"Christening photos",
photo_birthday:"Birthday photos",
photo_studio:"Studio photos",
photo_family:"Family photos",
photo_portrait:"Portrait photos",
photo_event:"Event photos",

replace_later:"replace with photo",

about_photo:"Nelli's photo",

about_title:"People.<br>Emotions.<br>Stories.",

about_text:
"I'm Nelli — a photographer who loves real moments. No unnecessary posing or fake emotions. I want to preserve not just beautiful images, but memories you will want to return to.",

contact_title:"Let's create<br>something real.",

contact_text:
"Tell me about your event or idea — and together we'll create a beautiful story.",

footer:"Prague · Czech Republic"

},


cs:{

nav_services:"Služby",
nav_portfolio:"Portfolio",
nav_about:"O mně",
nav_contact:"Kontakt",

hero_eyebrow:"Photography · Prague",

hero_description:
"Fotografuji skutečné okamžiky, emoce a příběhy, na které chcete vzpomínat.",

hero_portfolio:"Prohlédnout portfolio",
hero_contact:"Kontaktovat",

hero_photo:"Hlavní fotografie",
photo_replace:"zde bude fotografie Nelli",

services_title:"Co<br>fotím",

services_description:
"Od velkých oslav až po malé rodinné okamžiky. Každé focení má svou vlastní atmosféru.",

wedding:"Svatby",
wedding_desc:"Den, na který chcete vzpomínat navždy.",

christening:"Křtiny",
christening_desc:"Jemné okamžiky výjimečného dne.",

birthday:"Narozeniny",
birthday_desc:"Emoce, lidé a atmosféra oslavy.",

studio:"Studio",
studio_desc:"Stylové portréty a kreativní focení.",

family:"Rodinné",
family_desc:"Přirozené fotografie bez zbytečného aranžování.",

lovestory:"Love Story",
lovestory_desc:"Příběh dvou lidí.",

portfolio_title:"Vybrané<br>příběhy",

portfolio_description:
"Zde budou skutečné fotografie Nelli. Zatím jsou zde stylové demonstrační bloky.",

photo_wedding:"Fotografie svatby",
photo_christening:"Fotografie křtin",
photo_birthday:"Fotografie narozenin",
photo_studio:"Fotografie ze studia",
photo_family:"Rodinné fotografie",
photo_portrait:"Portrétní fotografie",
photo_event:"Fotografie události",

replace_later:"nahradit fotografií",

about_photo:"Fotografie Nelli",

about_title:"Lidé.<br>Emoce.<br>Příběhy.",

about_text:
"Jsem Nelli — fotografka, která miluje skutečné okamžiky. Bez zbytečného aranžování a hraných emocí. Chci zachovat nejen krásné fotografie, ale také vzpomínky, ke kterým se budete chtít vracet.",

contact_title:"Vytvořme<br>něco skutečného.",

contact_text:
"Napište mi o vaší události nebo nápadu — společně vytvoříme krásný příběh.",

footer:"Praha · Česká republika"

}

};


/* ================= LANGUAGE SYSTEM ================= */

const langBtn =
document.getElementById("langBtn");

const langMenu =
document.getElementById("langMenu");

const currentFlag =
document.getElementById("currentFlag");

const currentLang =
document.getElementById("currentLang");


langBtn.addEventListener("click",function(){

    langMenu.classList.toggle("open");

});


document.querySelectorAll(".lang-option").forEach(function(option){

    option.addEventListener("click",function(){

        const lang = this.dataset.lang;

        changeLanguage(lang);

        langMenu.classList.remove("open");

    });

});


function changeLanguage(lang){

    const data = translations[lang];

    if(!data) return;

    document.documentElement.lang = lang;

    document.querySelectorAll("[data-i18n]").forEach(function(element){

        const key = element.dataset.i18n;

        if(data[key]){
            element.innerHTML = data[key];
        }

    });


    const languageInfo = {

        uk:["🇺🇦","UA"],
        ru:["🇷🇺","RU"],
        en:["🇬🇧","EN"],
        cs:["🇨🇿","CZ"]

    };


    currentFlag.textContent =
        languageInfo[lang][0];

    currentLang.textContent =
        languageInfo[lang][1];


    localStorage.setItem(
        "nelli-language",
        lang
    );

}


/* ================= LOAD LANGUAGE ================= */

const savedLanguage =
localStorage.getItem("nelli-language") || "uk";

changeLanguage(savedLanguage);


/* ================= MOBILE MENU ================= */

const menuBtn =
document.getElementById("menuBtn");

const nav =
document.getElementById("nav");


menuBtn.addEventListener("click",function(){

    nav.classList.toggle("open");

});


document.querySelectorAll("nav a").forEach(function(link){

    link.addEventListener("click",function(){

        nav.classList.remove("open");

    });

});


/* ================= HEADER ================= */

window.addEventListener("scroll",function(){

    const header =
    document.getElementById("header");

    if(window.scrollY > 40){

        header.classList.add("scrolled");

    }else{

        header.classList.remove("scrolled");

    }

});


/* ================= SCROLL ANIMATION ================= */

const observer =
new IntersectionObserver(

    function(entries){

        entries.forEach(function(entry){

            if(entry.isIntersecting){

                entry.target.classList.add("visible");

            }

        });

    },

    {
        threshold:.12
    }

);


document
.querySelectorAll(".reveal")
.forEach(function(element){

    observer.observe(element);

});


/* ================= CLOSE LANGUAGE ================= */

document.addEventListener("click",function(event){

    if(!event.target.closest(".lang-wrap")){

        langMenu.classList.remove("open");

    }

});

</script>

</body>
</html>
