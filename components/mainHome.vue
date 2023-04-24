<template>
    <div class="container-main">
        <video src="/video/video_background2.mp4" autoplay loop muted playsinline></video>
        <h1 class="line-1 anim-typewriter">Developpeur web</h1>
        <h2>Jean Béquilleux - Etudiant Web Developpeur situé à Annecy</h2>
    </div>
</template>

<style>
    video{
        position: absolute;
        height: 100vh;
        width: 100%;
        object-fit: cover;
        z-index: -1;
        overflow-x: hidden;
    }
    .container-main h1{
        font-size: 100px;
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
    .container-main{
        height: 100vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
    .container-main .line-1{
        width: 20.18em;
        border-right: 4px solid rgba(255,255,255,.75);
        white-space: nowrap;
        overflow: hidden;
        -webkit-box-sizing:content-box;
        box-sizing:content-box;
        text-align: center;
    }
    .anim-typewriter{
        width:0;
    }
    @media screen and (max-width: 991px) {
        .container-main h1{
            font-size:12vw
        }
        .container-main h2{
            font-size: 5vw;
        }
    }
</style>