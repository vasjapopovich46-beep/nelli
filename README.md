<!DOCTYPE html>
<html lang="uk">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>NELLI — Photographer Prague</title>

<style>

@import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@300;400;500&family=Playfair+Display:ital,wght@0,400;0,500;1,400&display=swap');


/* =========================================================
   RESET
========================================================= */

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    background:#11110f;
    color:#f3f0ea;
    font-family:"DM Sans",sans-serif;
    font-weight:300;
    overflow-x:hidden;
}

body::before{
    content:"";
    position:fixed;
    inset:0;
    pointer-events:none;
    z-index:999;

    opacity:.035;

    background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 180 180' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.8' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.8'/%3E%3C/svg%3E");
}

a{
    color:inherit;
    text-decoration:none;
}

button{
    font-family:inherit;
}


/* =========================================================
   CURSOR
========================================================= */

.cursor{
    position:fixed;

    width:14px;
    height:14px;

    border:1px solid rgba(255,255,255,.7);
    border-radius:50%;

    pointer-events:none;

    transform:translate(-50%,-50%);

    z-index:9999;

    transition:
        width .3s ease,
        height .3s ease,
        background .3s ease;
}

.cursor.big{
    width:55px;
    height:55px;

    background:rgba(255,255,255,.08);
}


/* =========================================================
   NAV
========================================================= */

.nav{
    position:fixed;

    top:0;
    left:0;

    width:100%;
    height:85px;

    display:flex;
    align-items:center;
    justify-content:space-between;

    padding:0 5vw;

    z-index:100;

    background:linear-gradient(
        to bottom,
        rgba(17,17,15,.8),
        transparent
    );

    backdrop-filter:blur(5px);
}

.logo{
    font-family:"Playfair Display",serif;

    font-size:25px;

    letter-spacing:-.04em;
}

.logo em{
    font-style:italic;
}

.nav-links{
    display:flex;
    gap:35px;

    font-size:10px;

    text-transform:uppercase;

    letter-spacing:.16em;
}

.nav-links a{
    opacity:.65;

    transition:.3s;
}

.nav-links a:hover{
    opacity:1;
}

.nav-contact{
    padding:11px 17px;

    border:1px solid rgba(255,255,255,.25);

    border-radius:100px;

    font-size:10px;

    text-transform:uppercase;

    letter-spacing:.12em;

    transition:.35s;
}

.nav-contact:hover{
    background:white;
    color:#111;
}


/* =========================================================
   HERO
========================================================= */

.hero{
    min-height:100vh;

    position:relative;

    display:flex;
    align-items:center;
    justify-content:center;

    text-align:center;

    padding:130px 5vw 80px;

    overflow:hidden;

    background:
        radial-gradient(
            circle at 50% 35%,
            #403d36 0%,
            #1e1e1b 35%,
            #11110f 70%
        );
}

.hero-orb{
    position:absolute;

    width:55vw;
    height:55vw;

    max-width:800px;
    max-height:800px;

    border-radius:50%;

    background:
        radial-gradient(
            circle,
            rgba(213,190,157,.18),
            transparent 65%
        );

    filter:blur(40px);

    animation:orb 8s ease-in-out infinite alternate;
}

@keyframes orb{

    from{
        transform:scale(.9) translate(-2%, -1%);
    }

    to{
        transform:scale(1.08) translate(2%, 2%);
    }

}

.hero-content{
    position:relative;

    z-index:2;

    max-width:1000px;
}

.hero-small{
    font-size:10px;

    text-transform:uppercase;

    letter-spacing:.28em;

    color:#aaa49a;

    margin-bottom:30px;

    opacity:0;

    animation:fadeUp 1s .2s forwards;
}

.hero h1{
    font-family:"Playfair Display",serif;

    font-size:clamp(65px,11vw,155px);

    line-height:.78;

    font-weight:400;

    letter-spacing:-.075em;

    opacity:0;

    animation:heroIn 1.2s .35s cubic-bezier(.2,.8,.2,1) forwards;
}

.hero h1 span{
    display:block;

    font-style:italic;

    margin-left:12vw;
}

.hero-text{
    max-width:510px;

    margin:45px auto 0;

    color:#aaa69e;

    font-size:16px;

    line-height:1.7;

    opacity:0;

    animation:fadeUp 1s .8s forwards;
}

.hero-cta{
    display:inline-flex;

    align-items:center;
    gap:14px;

    margin-top:35px;

    padding:15px 20px;

    border:1px solid rgba(255,255,255,.2);

    border-radius:100px;

    text-transform:uppercase;

    letter-spacing:.13em;

    font-size:10px;

    opacity:0;

    animation:fadeUp 1s 1s forwards;

    transition:.4s;
}

.hero-cta:hover{
    background:#f4f0e8;
    color:#111;
    padding-left:27px;
    padding-right:27px;
}

.hero-cta span{
    font-size:16px;
}

.scroll{
    position:absolute;

    bottom:30px;

    left:50%;

    transform:translateX(-50%);

    display:flex;
    flex-direction:column;
    align-items:center;

    gap:10px;

    color:#77736c;

    font-size:9px;

    text-transform:uppercase;

    letter-spacing:.2em;
}

.scroll-line{
    width:1px;
    height:45px;

    background:linear-gradient(
        to bottom,
        #777,
        transparent
    );

    animation:scrollLine 2s infinite;
}

@keyframes scrollLine{

    0%{
        opacity:0;
        transform:scaleY(0);
        transform-origin:top;
    }

    50%{
        opacity:1;
        transform:scaleY(1);
    }

    100%{
        opacity:0;
        transform:scaleY(1);
        transform-origin:bottom;
    }

}


/* =========================================================
   INTRO
========================================================= */

.intro{
    min-height:75vh;

    display:grid;

    grid-template-columns:.7fr 1.3fr;

    gap:10vw;

    align-items:center;

    padding:130px 7vw;

    background:#f0ece5;

    color:#1a1917;
}

.label{
    font-size:10px;

    text-transform:uppercase;

    letter-spacing:.2em;

    color:#827c73;
}

.intro h2{
    margin-top:20px;

    font-family:"Playfair Display",serif;

    font-size:clamp(42px,6vw,80px);

    line-height:.95;

    font-weight:400;

    letter-spacing:-.055em;
}

.intro h2 em{
    font-style:italic;
}

.intro-text{
    max-width:650px;

    font-size:20px;

    line-height:1.7;

    color:#65615a;
}

.intro-text strong{
    color:#1a1917;

    font-weight:400;
}


/* =========================================================
   CHOICE SECTION
========================================================= */

.choose{
    padding:140px 5vw;

    background:#151513;
}

.choose-header{
    max-width:900px;

    margin-bottom:70px;
}

.choose-title{
    margin-top:20px;

    font-family:"Playfair Display",serif;

    font-size:clamp(50px,7vw,100px);

    line-height:.88;

    font-weight:400;

    letter-spacing:-.065em;
}

.choose-title em{
    font-style:italic;
}

.choose-description{
    max-width:500px;

    margin-top:30px;

    color:#858078;

    line-height:1.7;
}


/* =========================================================
   SERVICE CARDS
========================================================= */

.services{
    display:grid;

    grid-template-columns:repeat(4,1fr);

    gap:12px;
}

.service-card{
    min-height:330px;

    position:relative;

    padding:25px;

    overflow:hidden;

    background:#24231f;

    border:1px solid #34322d;

    cursor:pointer;

    transition:
        transform .6s cubic-bezier(.2,.8,.2,1),
        border-color .4s,
        background .5s;
}

.service-card::before{
    content:"";

    position:absolute;

    width:220px;
    height:220px;

    right:-80px;
    bottom:-100px;

    border-radius:50%;

    background:#c8a984;

    filter:blur(70px);

    opacity:0;

    transition:1s;
}

.service-card:hover{
    transform:translateY(-12px);

    border-color:#777267;

    background:#2a2925;
}

.service-card:hover::before{
    opacity:.25;
}

.service-number{
    font-size:10px;

    color:#77736c;
}

.service-icon{
    margin-top:50px;

    font-family:"Playfair Display",serif;

    font-size:45px;

    color:#aaa399;

    transition:.5s;
}

.service-card:hover .service-icon{
    transform:translateX(8px);
    color:#ded8cc;
}

.service-card h3{
    position:absolute;

    left:25px;
    bottom:48px;

    font-family:"Playfair Display",serif;

    font-size:28px;

    font-weight:400;
}

.service-card p{
    position:absolute;

    left:25px;
    bottom:20px;

    font-size:10px;

    color:#77736c;

    text-transform:uppercase;

    letter-spacing:.1em;
}


/* =========================================================
   SELECTED SERVICE
========================================================= */

.selection{
    margin-top:60px;

    padding:25px 0;

    border-top:1px solid #34322d;

    border-bottom:1px solid #34322d;

    display:flex;

    justify-content:space-between;

    align-items:center;
}

.selection-text{
    color:#817d75;

    font-size:11px;

    text-transform:uppercase;

    letter-spacing:.14em;
}

.selection-name{
    color:white;

    font-family:"Playfair Display",serif;

    font-size:25px;

    font-style:italic;
}

.selection-button{
    border:0;

    background:white;

    color:#151513;

    border-radius:100px;

    padding:13px 20px;

    cursor:pointer;

    font-size:10px;

    text-transform:uppercase;

    letter-spacing:.12em;

    transition:.3s;
}

.selection-button:hover{
    transform:translateX(5px);
}


/* =========================================================
   PORTFOLIO
========================================================= */

.portfolio{
    padding:140px 5vw;

    background:#f0ece5;

    color:#191816;
}

.portfolio-header{
    display:flex;

    justify-content:space-between;

    align-items:end;

    margin-bottom:60px;
}

.portfolio h2{
    margin-top:20px;

    font-family:"Playfair Display",serif;

    font-size:clamp(50px,7vw,100px);

    line-height:.85;

    font-weight:400;

    letter-spacing:-.06em;
}

.portfolio h2 em{
    font-style:italic;
}

.portfolio-note{
    max-width:260px;

    color:#777168;

    line-height:1.6;

    font-size:13px;
}

.portfolio-grid{
    display:grid;

    grid-template-columns:repeat(12,1fr);

    grid-auto-rows:90px;

    gap:14px;
}

.photo-placeholder{
    position:relative;

    overflow:hidden;

    background:
        linear-gradient(
            135deg,
            #cbc3b7,
            #9c958a
        );

    display:flex;

    align-items:center;

    justify-content:center;

    color:rgba(255,255,255,.65);

    font-family:"Playfair Display",serif;

    font-style:italic;

    font-size:35px;

    transition:.7s cubic-bezier(.2,.8,.2,1);
}

.photo-placeholder::after{
    content:"";

    position:absolute;

    inset:0;

    background:linear-gradient(
        120deg,
        transparent 20%,
        rgba(255,255,255,.3),
        transparent 80%
    );

    transform:translateX(-100%);

    transition:.8s;
}

.photo-placeholder:hover{
    transform:scale(.985);
}

.photo-placeholder:hover::after{
    transform:translateX(100%);
}

.photo-placeholder:nth-child(1){
    grid-column:span 7;
    grid-row:span 5;
}

.photo-placeholder:nth-child(2){
    grid-column:span 5;
    grid-row:span 3;

    background:
        linear-gradient(
            135deg,
            #b8aa9b,
            #766e65
        );
}

.photo-placeholder:nth-child(3){
    grid-column:span 5;
    grid-row:span 4;

    background:
        linear-gradient(
            135deg,
            #d3ccc0,
            #a39b90
        );
}

.photo-placeholder:nth-child(4){
    grid-column:span 4;
    grid-row:span 3;

    background:
        linear-gradient(
            135deg,
            #8f887d,
            #57534c
        );
}

.photo-placeholder:nth-child(5){
    grid-column:span 3;
    grid-row:span 3;

    background:
        linear-gradient(
            135deg,
            #c6b6a4,
            #8f7964
        );
}

.photo-tag{
    position:absolute;

    left:15px;
    bottom:15px;

    padding:8px 10px;

    background:rgba(15,15,14,.75);

    color:white;

    font-family:"DM Sans",sans-serif;

    font-size:9px;

    text-transform:uppercase;

    letter-spacing:.13em;
}


/* =========================================================
   ABOUT
========================================================= */

.about{
    min-height:90vh;

    padding:140px 7vw;

    display:grid;

    grid-template-columns:.8fr 1.2fr;

    gap:10vw;

    align-items:center;

    background:#191917;
}

.about-visual{
    aspect-ratio:4/5;

    position:relative;

    overflow:hidden;

    background:
        radial-gradient(
            circle at 40% 35%,
            #b9a68f,
            #5b554c 45%,
            #282722 80%
        );

    display:flex;

    align-items:center;
    justify-content:center;
}

.about-visual span{
    font-family:"Playfair Display",serif;

    font-size:50px;

    font-style:italic;

    color:rgba(255,255,255,.45);
}

.about h2{
    margin-top:20px;

    font-family:"Playfair Display",serif;

    font-size:clamp(55px,7vw,100px);

    line-height:.85;

    font-weight:400;

    letter-spacing:-.065em;
}

.about h2 em{
    font-style:italic;
}

.about-text{
    max-width:600px;

    margin-top:35px;

    color:#969189;

    font-size:17px;

    line-height:1.8;
}

.quote{
    max-width:600px;

    margin-top:55px;

    padding-top:25px;

    border-top:1px solid #36342f;

    font-family:"Playfair Display",serif;

    font-size:25px;

    line-height:1.4;
}


/* =========================================================
   CONTACT
========================================================= */

.contact{
    min-height:80vh;

    padding:140px 7vw;

    background:#d5c1aa;

    color:#191816;

    display:grid;

    grid-template-columns:1fr 1fr;

    gap:10vw;

    align-items:center;
}

.contact h2{
    margin-top:20px;

    font-family:"Playfair Display",serif;

    font-size:clamp(55px,8vw,115px);

    line-height:.82;

    font-weight:400;

    letter-spacing:-.07em;
}

.contact h2 em{
    font-style:italic;
}

.contact-info{
    align-self:end;
}

.contact-info p{
    max-width:450px;

    font-size:18px;

    line-height:1.7;

    color:#554d44;
}

.contact-buttons{
    display:flex;

    gap:10px;

    flex-wrap:wrap;

    margin-top:35px;
}

.contact-btn{
    padding:14px 18px;

    border:1px solid rgba(25,24,22,.35);

    border-radius:100px;

    font-size:10px;

    text-transform:uppercase;

    letter-spacing:.12em;

    transition:.3s;
}

.contact-btn:hover{
    background:#191816;
    color:white;
}


/* =========================================================
   FOOTER
========================================================= */

footer{
    padding:25px 5vw;

    display:flex;

    justify-content:space-between;

    background:#11110f;

    color:#77736c;

    font-size:9px;

    text-transform:uppercase;

    letter-spacing:.15em;
}


/* =========================================================
   SCROLL REVEAL
========================================================= */

.reveal{
    opacity:0;

    transform:translateY(50px);

    transition:
        opacity 1s ease,
        transform 1s cubic-bezier(.2,.8,.2,1);
}

.reveal.show{
    opacity:1;

    transform:translateY(0);
}


/* =========================================================
   MOBILE
========================================================= */

@media(max-width:900px){

    .nav-links{
        display:none;
    }

    .nav-contact{
        display:none;
    }

    .hero h1{
        font-size:72px;
    }

    .intro,
    .about,
    .contact{
        grid-template-columns:1fr;

        gap:60px;

        padding-top:100px;
        padding-bottom:100px;
    }

    .services{
        grid-template-columns:repeat(2,1fr);
    }

    .portfolio-header{
        display:block;
    }

    .portfolio-note{
        margin-top:25px;
    }

}


@media(max-width:600px){

    .nav{
        height:70px;
    }

    .hero{
        padding-top:120px;
    }

    .hero h1{
        font-size:58px;
    }

    .hero h1 span{
        margin-left:0;
    }

    .services{
        grid-template-columns:1fr;
    }

    .service-card{
        min-height:270px;
    }

    .selection{
        display:block;
    }

    .selection-button{
        margin-top:20px;
    }

    .portfolio-grid{
        grid-template-columns:1fr;

        grid-auto-rows:280px;
    }

    .photo-placeholder:nth-child(n){
        grid-column:span 1;
        grid-row:span 1;
    }

    footer{
        flex-direction:column;
        gap:10px;
    }

}

</style>
</head>


<body>


<div class="cursor"></div>


<!-- ========================================================
     NAVIGATION
========================================================= -->

<header class="nav">

    <a href="#" class="logo">
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

    <a href="#contact" class="nav-contact">
        Забронювати
    </a>

</header>



<!-- ========================================================
     HERO
========================================================= -->

<section class="hero">

    <div class="hero-orb"></div>

    <div class="hero-content">

        <div class="hero-small">
            Photographer · Prague · Czech Republic
        </div>

        <h1>
            Your story.
            <span>My vision.</span>
        </h1>

        <p class="hero-text">
            Фотографую моменти, які хочеться
            не просто зберегти, а прожити ще раз.
        </p>

        <a href="#choose" class="hero-cta">
            Обрати свою зйомку
            <span>↓</span>
        </a>

    </div>


    <div class="scroll">

        Scroll

        <div class="scroll-line"></div>

    </div>

</section>



<!-- ========================================================
     INTRO
========================================================= -->

<section class="intro reveal">

    <div>

        <div class="label">
            01 — Philosophy
        </div>

    </div>


    <div>

        <h2>
            Не потрібно<br>
            вміти <em>позувати.</em>
        </h2>

        <p class="intro-text">

            Вам не потрібно знати, куди ставити руки
            або як правильно дивитися в камеру.

            <br><br>

            Я підкажу, допоможу розслабитися
            і просто <strong>зловлю ваш момент.</strong>

        </p>

    </div>

</section>



<!-- ========================================================
     CHOOSE SESSION
========================================================= -->

<section class="choose" id="choose">

    <div class="choose-header reveal">

        <div class="label">
            02 — Find your story
        </div>

        <h2 class="choose-title">
            Яку історію<br>
            ми створимо <em>разом?</em>
        </h2>

        <p class="choose-description">
            Оберіть формат зйомки, який вам близький.
            А далі я допоможу перетворити вашу ідею
            на красиву фотосесію.
        </p>

    </div>


    <div class="services">


        <!-- WEDDING -->

        <article class="service-card reveal" data-name="Wedding">

            <div class="service-number">
                01
            </div>

            <div class="service-icon">
                W
            </div>

            <h3>
                Wedding
            </h3>

            <p>
                Весілля
            </p>

        </article>


        <!-- BAPTISM -->

        <article class="service-card reveal" data-name="Хрестини">

            <div class="service-number">
                02
            </div>

            <div class="service-icon">
                B
            </div>

            <h3>
                Хрестини
            </h3>

            <p>
                Baptism
            </p>

        </article>


        <!-- CEREMONY -->

        <article class="service-card reveal" data-name="Обрядова фотосесія">

            <div class="service-number">
                03
            </div>

            <div class="service-icon">
                C
            </div>

            <h3>
                Обряди
            </h3>

            <p>
                Особливі моменти
            </p>

        </article>


        <!-- STUDIO -->

        <article class="service-card reveal" data-name="Studio">

            <div class="service-number">
                04
            </div>

            <div class="service-icon">
                S
            </div>

            <h3>
                Studio
            </h3>

            <p>
                Студійна зйомка
            </p>

        </article>


        <!-- PORTRAIT -->

        <article class="service-card reveal" data-name="Portrait">

            <div class="service-number">
                05
            </div>

            <div class="service-icon">
                P
            </div>

            <h3>
                Portrait
            </h3>

            <p>
                Індивідуальна
            </p>

        </article>


        <!-- FAMILY -->

        <article class="service-card reveal" data-name="Family">

            <div class="service-number">
                06
            </div>

            <div class="service-icon">
                F
            </div>

            <h3>
                Family
            </h3>

            <p>
                Сімейна
            </p>

        </article>


        <!-- LOVE -->

        <article class="service-card reveal" data-name="Love Story">

            <div class="service-number">
                07
            </div>

            <div class="service-icon">
                L
            </div>

            <h3>
                Love Story
            </h3>

            <p>
                Для двох
            </p>

        </article>


        <!-- OTHER -->

        <article class="service-card reveal" data-name="Інше">

            <div class="service-number">
                08
            </div>

            <div class="service-icon">
                +
            </div>

            <h3>
                Інше
            </h3>

            <p>
                Ваша ідея
            </p>

        </article>


    </div>


    <!-- SELECTED -->

    <div class="selection">

        <div>

            <div class="selection-text">
                Ви обрали
            </div>

            <div class="selection-name" id="selectedName">
                Оберіть формат вище
            </div>

        </div>

        <a href="#contact" class="selection-button">
            Продовжити →
        </a>

    </div>

</section>



<!-- ========================================================
     PORTFOLIO
========================================================= -->

<section class="portfolio" id="portfolio">

    <div class="portfolio-header reveal">

        <div>

            <div class="label">
                03 — Selected work
            </div>

            <h2>
                Кадри, які<br>
                говорять <em>самі.</em>
            </h2>

        </div>

        <p class="portfolio-note">
            Тут згодом з'являться справжні
            фотографії Неллі — великі,
            атмосферні та без зайвого тексту.
        </p>

    </div>


    <div class="portfolio-grid reveal">

        <div class="photo-placeholder">
            PHOTO

            <span class="photo-tag">
                Wedding
            </span>
        </div>

        <div class="photo-placeholder">
            PHOTO

            <span class="photo-tag">
                Studio
            </span>
        </div>

        <div class="photo-placeholder">
            PHOTO

            <span class="photo-tag">
                Baptism
            </span>
        </div>

        <div class="photo-placeholder">
            PHOTO

            <span class="photo-tag">
                Portrait
            </span>
        </div>

        <div class="photo-placeholder">
            PHOTO

            <span class="photo-tag">
                Love story
            </span>
        </div>

    </div>

</section>



<!-- ========================================================
     ABOUT
========================================================= -->

<section class="about" id="about">

    <div class="about-visual reveal">

        <span>
            N.
        </span>

    </div>


    <div class="reveal">

        <div class="label">
            04 — About
        </div>

        <h2>
            Привіт,<br>
            я <em>Неллі.</em>
        </h2>

        <p class="about-text">

            Фотограф у Празі.
            Люблю красиве світло, живі емоції
            та моменти, які не потрібно вигадувати.

            <br><br>

            Весілля, хрестини, обрядові події,
            студійні та індивідуальні фотосесії —
            кожна історія для мене особлива.

        </p>

        <div class="quote">

            «Найкращі фотографії —
            це ті, де ви бачите не позу,
            а себе.»

        </div>

    </div>

</section>



<!-- ========================================================
     CONTACT
========================================================= -->

<section class="contact" id="contact">

    <div class="reveal">

        <div class="label">
            05 — Let's create
        </div>

        <h2>
            Давайте<br>
            створимо<br>
            <em>вашу історію.</em>
        </h2>

    </div>


    <div class="contact-info reveal">

        <p>

            Розкажіть мені, що ви задумали.
            Весілля, хрестини, студійна зйомка
            або щось зовсім інше.

            <br><br>

            Напишіть кілька слів —
            і разом придумаємо формат.

        </p>


        <div class="contact-buttons">

            <a href="#" class="contact-btn">
                Instagram ↗
            </a>

            <a href="mailto:hello@example.com" class="contact-btn">
                Написати email ↗
            </a>

        </div>

    </div>

</section>



<!-- ========================================================
     FOOTER
========================================================= -->

<footer>

    <span>
        NELLI PHOTO · PRAGUE
    </span>

    <span>
        © 2026
    </span>

</footer>



<script>

/* =========================================================
   CURSOR
========================================================= */

const cursor = document.querySelector(".cursor");

document.addEventListener("mousemove", e => {

    cursor.style.left = e.clientX + "px";
    cursor.style.top = e.clientY + "px";

});


document.querySelectorAll("a, button, .service-card").forEach(el => {

    el.addEventListener("mouseenter", () => {
        cursor.classList.add("big");
    });

    el.addEventListener("mouseleave", () => {
        cursor.classList.remove("big");
    });

});


/* =========================================================
   SERVICE SELECTION
========================================================= */

const cards = document.querySelectorAll(".service-card");

const selectedName =
    document.getElementById("selectedName");


cards.forEach(card => {

    card.addEventListener("click", () => {

        cards.forEach(item => {
            item.style.borderColor = "#34322d";
        });

        card.style.borderColor = "#c8a984";

        const name = card.dataset.name;

        selectedName.textContent = name;

        selectedName.style.opacity = "0";

        setTimeout(() => {

            selectedName.style.transition = ".5s";

            selectedName.style.opacity = "1";

        }, 50);

    });

});


/* =========================================================
   SCROLL REVEAL
========================================================= */

const observer = new IntersectionObserver(

    entries => {

        entries.forEach(entry => {

            if(entry.isIntersecting){

                entry.target.classList.add("show");

                observer.unobserve(entry.target);

            }

        });

    },

    {
        threshold:.12
    }

);


document.querySelectorAll(".reveal").forEach(el => {

    observer.observe(el);

});


/* =========================================================
   PARALLAX HERO
========================================================= */

const orb = document.querySelector(".hero-orb");

window.addEventListener("mousemove", e => {

    const x =
        (e.clientX / window.innerWidth - .5) * 20;

    const y =
        (e.clientY / window.innerHeight - .5) * 20;

    orb.style.transform =
        `translate(${x}px, ${y}px)`;

});

</script>


</body>
</html>
