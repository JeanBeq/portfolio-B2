<template>
    <div class="allPj">
        <div class="projets">
        <div class="bande-pj"></div>
        <h1>MES - <strong>PROJETS /</strong></h1>
        <p>Réalisés lors de stages ou lors de projets scolaires</p>
        <div class="bande-pj-2"></div>
    </div>
    <div class="sliderProjets" data-aos="zoom-in">
        <div class="left-slider-pr">
            <img src="/img/rhb.png" alt="">
            <div class="textPopUp">
                <h2>Association Refuges Hautes Bauges</h2>
            </div>
        </div>
        <div class="right-slider-pr">
            <img src="/img/adb.png" alt="">
            <div class="textPopUp">
                <h2>Société de nettoyage ADB service</h2>
            </div>
        </div>
    </div>
    </div>
    
</template>

<style>
.allPj{
    background-color: #323232;
}
.projets{
    position: relative;
}
.projets h1{
    color: white;
    padding-top: 30px;
    font-size: 55px;
    text-align: center;
}
.projets p{
    color: white;
    margin-top: -10px;
    text-align: center;
    margin-bottom: 20px;
}
.projets h1 strong{
    font-weight: bold;
    text-transform: uppercase;
}
.sliderProjets{
    display: flex;
    position: relative;
    margin-top: 60px;
    width: 90%;
    margin: 0 auto;
}
.sliderProjets img{
    height: 500px;
    object-fit: cover;
    filter: blur(0px);
    transition: all ease-in-out 0.2s;
}
.sliderProjets img:hover{
    filter: blur(5px);
}
.sliderProjets .textPopUp ::before {
    content: "";
    position: absolute;
    transform: translate(-50%, -50%);
    bottom: 10%;
    left: 50%;
    color: pink;
    display: none;
}
.sliderProjets .textPopUp::after, .sliderProjets .textPopUp :hover {
    content: "";
    position: absolute;
    transform: translate(-50%, -50%);
    bottom: 40%;
    left: 50%;
    color: pink;
    display: block;
}
.left-slider-pr{
    position: relative;
    width: 50%;
    margin-top: 50px;
    margin-bottom: 50px;
}
.right-slider-pr{
    width: 50%;
    position: relative;
    margin-top: 50px;
    margin-bottom: 50px;
}
.bande-pj{
    background-color: #f6bd60;
    position: absolute;
    transform: translate(-50%, -50%);
    top: 20%;
    left: 50%;
    width: 600px;
    height: 4px;
}
.bande-pj-2{
    background-color: #f6bd60;
    height: 4px;
    width: 500px;
    position: absolute;
    transform: translate(-50%, -50%);
    top: 110%;
    left: 50%;
    margin-bottom: 100px;
}
@media screen and (max-width: 991px) {
    .bande-pj{
        width: 100vw;
    }
    .bande-pj-2{
        width: 100vw;
    }
    .allPj h1{
        font-size: 12vw;
    }
}
</style>

<script>
import { gsap } from "gsap";
// import { SplitText } from "gsap/SplitText";
// gsap.registerPlugin(SplitText);  

export default{
    mounted() {
        const line = document.querySelector(".bande-pj");
        const line2 = document.querySelector(".bande-pj-2");

        let previewTimeline = gsap.timeline({ delay: 0.5 , repeat: -1});

        previewTimeline.fromTo(line, 
        {
            scaleX: 0,
        }, 
        {
            transformOrigin: "right center",
            scaleX: 1,
            duration: 0.8,
            ease: "none"
        })
        .to(line, {
            transformOrigin: "left center",
            scaleX: 0,
            duration: 0.8,
            ease: "none"
        })

      previewTimeline.fromTo(line2, {
        scaleX: 0,
      }, {
        transformOrigin: "right center",
        scaleX: 1,
        duration: 0.8,
        ease: "none",
      }).to(line2, {
        transformOrigin: "left center",
        scaleX: 0,
        duration: 0.8,
        ease: "none"
      })
    }
}
</script>