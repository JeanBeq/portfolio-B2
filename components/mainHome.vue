<template>
    <div class="container-main">
        <!-- <img src="/img/blob.svg" alt="" id="svg1">
        <img src="/img/blob2.svg" alt="" id="svg2"> -->
        <img src="/img/wave.svg" alt="" id="wave" data-aos="fade-up">
        <h1 class="">Developpeur web</h1>
        <h2>Jean Béquilleux - Etudiant Web Developpeur situé à Annecy</h2>
    </div>
</template>

<style>
    .container-main h1{
        font-size: 7vw;
        color: white;
        text-transform: uppercase;
        font-weight: bold;
        overflow: hidden;
    }
    .container-main h2{
        color: white;
        font-size: 25px;
        margin-bottom: 20px;
    }
    .container-main h1, .container-main h2{
        text-align: center;
    }
    .container-main #svg1{
        position: absolute;
        z-index: -1;
        left: -10%;
        top: 10%;
        size: 210%;
    }
    .container-main #wave{
        position: absolute;
        z-index: -1;
        bottom: 0;
        width: 100vw;
    }
    .container-main #svg2{
        position: absolute;
        z-index: -1;
        left: -5%;
        top: 15%;
    }
    .container-main{
        height: 100vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        background-repeat: no-repeat;
        background-size: cover;
        position: relative;
    }
    @media screen and (max-width: 991px) {
        .container-main h1{
            font-size:8vw
        }
        .container-main h2{
            font-size: 5vw;
        }
    }
</style>