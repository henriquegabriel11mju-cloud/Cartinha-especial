<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Henrique × Kathleen — 11 meses</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;500;600;700&family=DM+Sans:wght@300;400;500;600&family=Italianno&display=swap" rel="stylesheet">

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    background:#12090b;
    color:#f7eee9;
    font-family:"DM Sans",sans-serif;
    overflow-x:hidden;
}

#progress{
    position:fixed;
    top:0;
    left:0;
    width:0%;
    height:3px;
    background:#d99498;
    z-index:9999;
}

body::before{
    content:"";
    position:fixed;
    inset:0;
    pointer-events:none;
    opacity:.035;
    background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='180' height='180'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.8' numOctaves='3'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
    z-index:100;
}

section{
    position:relative;
    min-height:100vh;
    padding:110px 8vw;
    display:flex;
    flex-direction:column;
    justify-content:center;
    overflow:hidden;
}

.serif{
    font-family:"Cormorant Garamond",serif;
}

.script{
    font-family:"Italianno",cursive;
}

.label{
    font-size:10px;
    letter-spacing:4px;
    text-transform:uppercase;
    color:#b77d82;
}

.line{
    height:1px;
    width:100%;
    background:#3d2528;
    margin:35px 0;
}

.reveal{
    opacity:0;
    transform:translateY(30px);
    transition:1s ease;
}

.reveal.show{
    opacity:1;
    transform:translateY(0);
}

/* SENHA */

#lock{
    position:fixed;
    inset:0;
    background:#12090b;
    z-index:9998;
    display:flex;
    align-items:center;
    justify-content:center;
    padding:25px;
}

.lock-box{
    width:100%;
    max-width:420px;
    text-align:center;
    padding:50px 30px;
    border-top:1px solid #75484e;
    border-bottom:1px solid #75484e;
}

.lock-small{
    font-size:10px;
    letter-spacing:5px;
    text-transform:uppercase;
    color:#b77d82;
    margin-bottom:25px;
}

.lock-box h1{
    font-family:"Cormorant Garamond",serif;
    font-size:62px;
    line-height:.85;
    font-weight:400;
}

.lock-box p{
    margin:25px 0;
    color:#b8a1a2;
    font-size:13px;
}

input{
    width:100%;
    padding:16px;
    background:transparent;
    border:1px solid #634145;
    color:white;
    outline:none;
    text-align:center;
    letter-spacing:6px;
    font-size:16px;
}

.unlock{
    width:100%;
    margin-top:12px;
    padding:16px;
    border:none;
    background:#f2dfda;
    color:#261215;
    font-weight:bold;
    letter-spacing:2px;
    cursor:pointer;
}

/* HERO */

.hero{
    justify-content:flex-end;
    padding-bottom:85px;
    background:
        radial-gradient(circle at 75% 25%,rgba(132,47,61,.38),transparent 35%),
        #12090b;
}

.hero-number{
    position:absolute;
    right:-5vw;
    top:8vh;
    font-family:"Cormorant Garamond",serif;
    font-size:60vw;
    line-height:.7;
    color:transparent;
    -webkit-text-stroke:1px rgba(218,142,148,.16);
}

.hero-top{
    position:absolute;
    top:65px;
    left:8vw;
    right:8vw;
    display:flex;
    justify-content:space-between;
    font-size:9px;
    letter-spacing:3px;
    text-transform:uppercase;
    color:#907276;
}

.hero h1{
    position:relative;
    font-family:"Cormorant Garamond",serif;
    font-size:clamp(70px,15vw,180px);
    line-height:.7;
    font-weight:400;
    letter-spacing:-5px;
}

.hero h1 span{
    display:block;
    margin-left:12vw;
    color:#e0afb0;
    font-style:italic;
}

.hero-sub{
    position:relative;
    max-width:510px;
    margin-left:auto;
    margin-top:55px;
    color:#bda6a7;
    font-size:14px;
    line-height:1.9;
}

.hero-sub strong{
    color:#f3e2de;
    font-weight:500;
}

.scroll{
    position:absolute;
    bottom:30px;
    left:8vw;
    font-size:9px;
    letter-spacing:3px;
    text-transform:uppercase;
    color:#80676a;
}

/* CONTADOR */

.counter-section{
    background:#f2e8e3;
    color:#291719;
}

.counter-wrap{
    max-width:1000px;
}

.counter-title{
    font-family:"Cormorant Garamond",serif;
    font-size:clamp(55px,9vw,120px);
    line-height:.78;
    font-weight:400;
    margin-top:20px;
}

.counter-title em{
    color:#a05259;
}

.counter{
    margin-top:75px;
    display:grid;
    grid-template-columns:repeat(4,1fr);
    border-top:1px solid #cdb9b5;
    border-bottom:1px solid #cdb9b5;
}

.time{
    padding:35px 20px;
    text-align:center;
    border-right:1px solid #cdb9b5;
}

.time:last-child{
    border-right:0;
}

.time strong{
    display:block;
    font-family:"Cormorant Garamond",serif;
    font-size:60px;
    font-weight:400;
    color:#8f4e56;
}

.time span{
    font-size:9px;
    letter-spacing:3px;
    text-transform:uppercase;
    color:#836c6d;
}

.counter-note{
    margin-top:30px;
    font-family:"Italianno",cursive;
    font-size:36px;
    color:#a05259;
}

/* COMEÇO */

.begin{
    background:#12090b;
}

.begin-grid{
    display:grid;
    grid-template-columns:1fr 1.3fr;
    gap:9vw;
    align-items:end;
}

.begin h2{
    font-family:"Cormorant Garamond",serif;
    font-size:clamp(60px,10vw,130px);
    line-height:.75;
    font-weight:400;
}

.begin h2 em{
    color:#d08a8f;
    margin-left:50px;
}

.begin-text{
    color:#bca4a4;
    font-size:15px;
    line-height:2;
    max-width:550px;
}

/* GALERIA */

.gallery{
    background:#eadbd5;
    color:#281719;
}

.gallery-header{
    display:flex;
    justify-content:space-between;
    align-items:end;
    gap:40px;
}

.gallery h2{
    font-family:"Cormorant Garamond",serif;
    font-size:clamp(65px,10vw,135px);
    line-height:.75;
    font-weight:400;
}

.gallery h2 em{
    color:#9d5159;
}

.gallery-intro{
    max-width:300px;
    color:#735a5b;
    font-size:13px;
    line-height:1.8;
}

.photos{
    margin-top:65px;
    display:grid;
    grid-template-columns:1.15fr .85fr 1fr;
    gap:15px;
    align-items:center;
}

.photo{
    position:relative;
    overflow:hidden;
    background:#d1bbb6;
}

.photo:nth-child(1){
    height:470px;
}

.photo:nth-child(2){
    height:350px;
}

.photo:nth-child(3){
    height:420px;
}

.photo img{
    width:100%;
    height:100%;
    object-fit:cover;
    display:block;
    transition:transform .7s ease;
}

.photo:hover img{
    transform:scale(1.05);
}

.photo::after{
    content:"♡";
    position:absolute;
    right:18px;
    bottom:10px;
    font-family:"Cormorant Garamond",serif;
    font-size:35px;
    color:white;
    text-shadow:0 2px 10px rgba(0,0,0,.4);
}

.photo-caption{
    position:absolute;
    left:15px;
    bottom:15px;
    color:white;
    font-size:9px;
    letter-spacing:2px;
    text-transform:uppercase;
    text-shadow:0 2px 10px #000;
}

/* MÚSICA */

.music{
    background:#1b0d10;
    align-items:center;
    text-align:center;
}

.music-card{
    width:min(600px,100%);
    border:1px solid #4a2b30;
    padding:55px 35px;
    background:rgba(255,255,255,.025);
}

.music-icon{
    width:75px;
    height:75px;
    border:1px solid #a65b64;
    border-radius:50%;
    display:flex;
    align-items:center;
    justify-content:center;
    margin:0 auto 25px;
    color:#d9959a;
    font-size:30px;
}

.music-card h2{
    font-family:"Cormorant Garamond",serif;
    font-size:55px;
    font-weight:400;
}

.music-card p{
    color:#a99394;
    font-size:12px;
    margin:12px 0 30px;
}

.music-button{
    border:1px solid #a65b64;
    background:transparent;
    color:#edcfcc;
    padding:14px 35px;
    cursor:pointer;
    letter-spacing:2px;
}

audio{
    display:none;
}

.music-progress{
    width:100%;
    height:2px;
    background:#41272b;
    margin-top:30px;
    overflow:hidden;
}

.music-progress span{
    display:block;
    height:100%;
    width:0%;
    background:#d9959a;
}

/* 11 */

.number-section{
    background:#f3e8e3;
    color:#241416;
    align-items:center;
    text-align:center;
}

.big11{
    font-family:"Cormorant Garamond",serif;
    font-size:min(70vw,700px);
    line-height:.6;
    font-weight:300;
    color:#9f565e;
    letter-spacing:-20px;
}

.number-caption{
    max-width:500px;
    margin-top:65px;
    color:#765b5d;
    font-size:14px;
    line-height:1.9;
}

/* 11 MOTIVOS */

.reasons{
    background:#12090b;
}

.reasons h2{
    font-family:"Cormorant Garamond",serif;
    font-size:clamp(60px,10vw,135px);
    line-height:.75;
    font-weight:400;
    margin-top:20px;
}

.reasons h2 span{
    color:#d28b90;
    font-style:italic;
}

.reason-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    margin-top:70px;
    gap:1px;
    background:#382124;
}

.reason{
    padding:30px;
    min-height:180px;
    background:#12090b;
    border:1px solid #382124;
    transition:.4s;
}

.reason:hover{
    background:#251216;
    transform:translateY(-5px);
}

.reason b{
    display:block;
    font-family:"Cormorant Garamond",serif;
    font-size:42px;
    color:#c77e84;
    margin-bottom:25px;
    font-weight:400;
}

.reason p{
    color:#b49b9c;
    font-size:13px;
    line-height:1.7;
}

/* FUTURO */

.future{
    background:#f2e8e3;
    color:#281719;
}

.future h2{
    font-family:"Cormorant Garamond",serif;
    font-size:clamp(60px,10vw,135px);
    line-height:.75;
    font-weight:400;
}

.future h2 em{
    color:#a05259;
}

.future-text{
    max-width:570px;
    margin:70px 0 0 auto;
    color:#73595a;
    line-height:2;
}

/* CARTA */

.letter-section{
    background:#1b0d10;
    align-items:center;
}

.paper{
    width:min(850px,100%);
    background:#f5ece7;
    color:#2c1719;
    padding:clamp(40px,8vw,90px);
    box-shadow:0 30px 80px rgba(0,0,0,.35);
    position:relative;
}

.paper::before{
    content:"PARA KATHLEEN";
    position:absolute;
    right:30px;
    top:25px;
    font-size:8px;
    letter-spacing:3px;
    color:#a66b70;
}

.paper h2{
    font-family:"Italianno",cursive;
    font-size:65px;
    color:#9e555d;
    font-weight:400;
}

.paper p{
    margin-top:28px;
    font-family:"Cormorant Garamond",serif;
    font-size:21px;
    line-height:1.7;
    color:#523b3d;
}

.signature{
    margin-top:45px;
    font-family:"Italianno",cursive;
    font-size:45px;
    color:#9e555d;
}

/* FINAL */

.final{
    min-height:110vh;
    text-align:center;
    align-items:center;
    background:
        radial-gradient(circle at 50% 40%,rgba(135,45,61,.45),transparent 35%),
        #12090b;
}

.final-outline{
    position:absolute;
    font-family:"Cormorant Garamond",serif;
    font-size:70vw;
    line-height:.6;
    color:transparent;
    -webkit-text-stroke:1px rgba(220,145,150,.13);
}

.final-content{
    position:relative;
    z-index:2;
}

.final-small{
    font-size:10px;
    letter-spacing:5px;
    color:#b87d82;
    text-transform:uppercase;
}

.final h2{
    margin:30px 0;
    font-family:"Cormorant Garamond",serif;
    font-size:clamp(55px,10vw,130px);
    line-height:.78;
    font-weight:400;
}

.final h2 em{
    color:#d99599;
    font-style:italic;
}

.final p{
    max-width:550px;
    color:#bca4a4;
    line-height:1.9;
    font-size:14px;
}

.final-love{
    margin-top:55px;
    font-family:"Italianno",cursive;
    color:#e0a2a5;
    font-size:55px;
}

/* CORAÇÕES */

.heart{
    position:fixed;
    bottom:-30px;
    color:#df9297;
    font-size:22px;
    animation:up 4s linear forwards;
    z-index:10000;
    pointer-events:none;
}

@keyframes up{
    0%{
        transform:translateY(0);
        opacity:0;
    }
    15%{opacity:1;}
    100%{
        transform:translateY(-100vh) rotate(25deg);
        opacity:0;
    }
}

/* MOBILE */

@media(max-width:700px){

    section{
        padding:90px 7vw;
    }

    .hero h1{
        font-size:24vw;
    }

    .hero-number{
        font-size:90vw;
        top:18vh;
    }

    .counter{
        grid-template-columns:1fr 1fr;
    }

    .time:nth-child(2){
        border-right:0;
    }

    .time:nth-child(-n+2){
        border-bottom:1px solid #cdb9b5;
    }

    .time strong{
        font-size:48px;
    }

    .begin-grid{
        grid-template-columns:1fr;
        gap:50px;
    }

    .begin h2{
        font-size:23vw;
    }

    .gallery-header{
        display:block;
    }

    .gallery-intro{
        margin-top:35px;
    }

    .photos{
        grid-template-columns:1fr;
    }

    .photo:nth-child(1),
    .photo:nth-child(2),
    .photo:nth-child(3){
        height:400px;
    }

    .reason-grid{
        grid-template-columns:1fr 1fr;
    }

    .reason{
        padding:20px;
        min-height:150px;
    }

    .reason p{
        font-size:12px;
    }

    .future-text{
        margin-left:0;
    }

    .paper p{
        font-size:19px;
    }

    .final h2{
        font-size:20vw;
    }
}
</style>
</head>

<body>

<div id="progress"></div>


<!-- SENHA -->

<div id="lock">

    <div class="lock-box">

        <div class="lock-small">
            Uma coisa só nossa
        </div>

        <h1>
            Henrique<br>
            <span style="color:#d98b8f;font-style:italic;">×</span><br>
            Kathleen
        </h1>

        <p>
            Tem uma pequena surpresa esperando por você.
        </p>

        <input
            id="password"
            type="password"
            placeholder="SENHA"
        >

        <button class="unlock" onclick="unlock()">
            ENTRAR
        </button>

    </div>

</div>


<!-- HERO -->

<section class="hero">

    <div class="hero-number">11</div>

    <div class="hero-top">
        <span>05.11.2025</span>
        <span>Henrique × Kathleen</span>
    </div>

    <div class="label reveal">
        uma história que ainda está sendo escrita
    </div>

    <h1 class="reveal">
        11
        <span>meses.</span>
    </h1>

    <div class="hero-sub reveal">

        <strong>Kathleen, isso aqui não é só um site.</strong>

        <br><br>

        É um pedacinho do que eu sinto por você.
        Uma lembrança de tudo que a gente viveu
        e de tudo que ainda quero viver ao seu lado.

    </div>

    <div class="scroll">
        continue descendo ↓
    </div>

</section>


<!-- CONTADOR -->

<section class="counter-section">

    <div class="counter-wrap">

        <div class="label reveal">
            capítulo 01 — nosso tempo
        </div>

        <h2 class="counter-title reveal">
            E enquanto você<br>
            lê isso, o nosso tempo<br>
            <em>continua passando.</em>
        </h2>

        <div class="counter reveal">

            <div class="time">
                <strong id="months">00</strong>
                <span>meses</span>
            </div>

            <div class="time">
                <strong id="days">00</strong>
                <span>dias</span>
            </div>

            <div class="time">
                <strong id="hours">00</strong>
                <span>horas</span>
            </div>

            <div class="time">
                <strong id="minutes">00</strong>
                <span>minutos</span>
            </div>

        </div>

        <div class="counter-note reveal">
            ...e cada segundo é mais um segundo com você. ❤️
        </div>

    </div>

</section>


<!-- COMEÇO -->

<section class="begin">

    <div class="label reveal">
        capítulo 02 — o começo
    </div>

    <div class="line"></div>

    <div class="begin-grid">

        <h2 class="reveal">
            Tudo<br>
            começou<br>
            <em>com nós.</em>
        </h2>

        <div class="begin-text reveal">

            <p>
                11 meses podem ser só 11 meses para alguém.
                Para mim, são 11 meses tendo você como
                minha pessoa favorita.
            </p>

            <br>

            <p>
                E quando eu penso em tudo que ainda pode
                acontecer, parece que esses 11 meses foram
                só o primeiro capítulo.
            </p>

        </div>

    </div>

</section>


<!-- FOTOS -->

<section class="gallery">

    <div class="gallery-header reveal">

        <div>

            <div class="label">
                capítulo 03 — nossas memórias
            </div>

            <h2>
                Alguns<br>
                <em>momentos.</em>
            </h2>

        </div>

        <div class="gallery-intro">

            Porque algumas lembranças merecem
            ficar guardadas para sempre.

        </div>

    </div>


    <div class="photos">

        <!-- TROQUE OS NOMES DOS ARQUIVOS SE PRECISAR -->

        <div class="photo reveal">
            <img src="foto1.jpg" alt="Uma memória nossa">
            <div class="photo-caption">
                nós
            </div>
        </div>

        <div class="photo reveal">
            <img src="foto2.jpg" alt="Uma memória nossa">
            <div class="photo-caption">
                uma lembrança
            </div>
        </div>

        <div class="photo reveal">
            <img src="foto3.jpg" alt="Uma memória nossa">
            <div class="photo-caption">
                para guardar
            </div>
        </div>

    </div>

</section>


<!-- MÚSICA -->

<section class="music">

    <div class="music-card reveal">

        <div class="music-icon">
            ♪
        </div>

        <div class="label">
            capítulo 04 — nossa música
        </div>

        <h2>
            Os Anjos Cantam
        </h2>

        <p>
            Jorge & Mateus · uma música para nós
        </p>

        <!-- COLOQUE A SUA MÚSICA COMO "musica.mp3" -->

        <audio id="song" src="musica.mp3"></audio>

        <button
            id="musicButton"
            class="music-button"
            onclick="toggleMusic()"
        >
            ▶ TOCAR
        </button>

        <div class="music-progress">
            <span id="musicProgress"></span>
        </div>

    </div>

</section>


<!-- 11 -->

<section class="number-section">

    <div class="label reveal">
        capítulo 05 — nós
    </div>

    <div class="big11 reveal">
        11
    </div>

    <div class="number-caption reveal">

        <strong>11 meses.</strong>

        <br><br>

        11 meses de conversas, risadas,
        momentos aleatórios, carinho,
        brincadeiras e histórias que só
        fazem sentido porque são nossas.

    </div>

</section>


<!-- MOTIVOS -->

<section class="reasons">

    <div class="label reveal">
        capítulo 06 — motivos
    </div>

    <h2 class="reveal">
        11 coisas<br>
        que fazem<br>
        <span>você ser você.</span>
    </h2>

    <div class="reason-grid">

        <div class="reason reveal">
            <b>01</b>
            <p>Seu jeito de falar comigo.</p>
        </div>

        <div class="reason reveal">
            <b>02</b>
            <p>As nossas conversas que nunca parecem suficientes.</p>
        </div>

        <div class="reason reveal">
            <b>03</b>
            <p>As risadas que surgem do nada.</p>
        </div>

        <div class="reason reveal">
            <b>04</b>
            <p>O jeito que você consegue melhorar meus dias.</p>
        </div>

        <div class="reason reveal">
            <b>05</b>
            <p>Os pequenos detalhes que só você tem.</p>
        </div>

        <div class="reason reveal">
            <b>06</b>
            <p>Seu carinho.</p>
        </div>

        <div class="reason reveal">
            <b>07</b>
            <p>As nossas brincadeiras.</p>
        </div>

        <div class="reason reveal">
            <b>08</b>
            <p>O jeito que você faz eu me sentir importante.</p>
        </div>

        <div class="reason reveal">
            <b>09</b>
            <p>As memórias que estamos criando.</p>
            
