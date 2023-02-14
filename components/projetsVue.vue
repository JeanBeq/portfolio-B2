<template>
    <div class="projets">
        <h2>MES - <strong>PROJETS /</strong></h2>
        <p>Réalisés lors de stages ou lors de projets scolaires</p>
    </div>
    <div class="sliderProjets">
        <button id="but-left">
            <p>-></p>
        </button>
        <button id="but-right">
            <p>-/</p>
        </button>
        <div class="left-slider-pr">
            <img src="/img/rhb.png" alt="">
            <h2>Association Refuges Hautes Bauges</h2>
        </div>
        <div class="right-slider-pr">
            <img src="/img/adb.png" alt="">
            <h2>Société de nettoyage ADB service</h2>
        </div>
    </div>
</template>

<style>
.projets h2{
    color: white;
    padding-top: 30px;
    font-size: 55px;
}
.projets p{
    color: white;
    margin-top: -30px;
    text-align: center;
    margin-bottom: 20px;
}
.projets h2 strong{
    font-weight: bold;
    text-transform: uppercase;
}
.sliderProjets{
    display: flex;
    position: relative;
}
.sliderProjets img{
    height: 500px;
    object-fit: cover;
    filter: blur(3px);
    transition: all ease-in-out 0.2s;
}
.sliderProjets img:hover{
    filter: blur(0px);
}
.sliderProjets h2{
    position: absolute;
    text-align: center;
    bottom: 2%;
    left: 50%;
    transform: translate(-50%, -50%);
    text-transform: uppercase;
    color: #f6bd60;
    font-weight: bold;
    font-size: 30px;
}
.left-slider-pr{
    position: relative;
    width: 50%;
}
.right-slider-pr{
    width: 50%;
    position: relative;
}
#but-right{
    position: absolute;
    top: 50%;
    right: 10%;
    z-index: 1;
}
#but-left{
    position: absolute;
    top: 50%;
    left: 10%;
    z-index: 1;
}
</style>