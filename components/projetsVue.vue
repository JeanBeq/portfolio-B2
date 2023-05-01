<template>
    <div class="allPj">
        <div class="projets">
            <div class="bande-pj"></div>
            <h2>MES - <strong>PROJETS /</strong></h2>
            <p>Réalisés lors de stages ou lors de projets scolaires</p>
            <div class="bande-pj-2"></div>
        </div>
    <div class="projetsPart">
        <div class="sliderProjets" data-aos="zoom-in">
            <div class="navSliderPj">
                <a v-for="pj in pjs" @click="selectPj(pj)" :class="{ active: pj.id === selectedPjId}">
                    {{ pj.name }}
                </a>
            </div>
            <div class="contentSliderPj">
                <h3 class="pjTitle">{{pjs[selectedPjId].name}}</h3>
                <div class="contentPjDetails">
                    <img :src="selectedPjImg" alt="" class="pjImg">    
                    <p class="pjText">{{pjs[selectedPjId].txt}}</p>
                </div>
                <a class="buttonPjLink" :href="selectedPjLink">Site internet</a>
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
.projets h2{
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
.sliderProjets{
    width: 100%;
    position: relative;
    margin-top: 2rem;
    width: 80rem;
    height: 30em;
    background-color: #484848;
    border-radius:20px;
    display: flex;
    flex-direction: row;
    margin: 0 auto;
}
.navSliderPj{
    display: flex;
    flex-direction: column;
    height: 100%;
    justify-content: space-between ;
    width: 20vw;
}
.contentSliderPj img{
    width: 450px;
    height: 250px;
    object-fit: cover;
}
.sliderProjets .navSliderPj a{
    height: 100%;
    text-align: center;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 10px;
    color: white;
}
.sliderProjets .navSliderPj a.active{
    background-color: rgb(103, 103, 103);
}
.sliderProjets .navSliderPj a.active:first-child{
    border-radius: 20px 0px 0px 0px;
}
.sliderProjets .navSliderPj a.active:last-child{
    border-radius: 0px 0px 0px 20px;
}
.projetsPart{
    width: 100%;
    display: flex;
    justify-content: center;
    margin-top:5rem;
}
.pjTitle{
    color: white;
    font-size: 3rem;
    font-weight: bold;
    margin-top: 1em;
    margin-left: 1em;
}
.pjText{
    color: white;
    margin-left: 1em;
    width: 50vw;
}
.pjImg{
    margin-left: 1em;
}
.contentPjDetails{
    display: flex;
    margin-top: 1rem;
}
.buttonPjLink{
    margin-top: 1rem;
    color: #f6bd60;
    margin-left: 1rem;
    padding: 10px;
    border-radius: 60px;
    border: 1px solid #f6bd60;
    display: inline-block;
    width: fit-content;
    margin-bottom: 20px;
    background-image: linear-gradient(#f6bd60, #f6bd60); 
    background-repeat: no-repeat; 
    background-size: 100% 0; 
    background-position: bottom; 
    transition: background-size 0.2s ease-out; 
}
.buttonPjLink:hover{
  background-size: 100% 100%; 
  color: #fff; 
}
@media screen and (max-width: 991px) {
    .sliderProjets{ 
        display: flex;
        flex-direction: column;
        height: 100%;
    }
    .sliderProjets .navSliderPj{
        width: 100%;
    }
    .sliderProjets .navSliderPj a.active:first-child{
    border-radius: 20px 20px 0px 0px;
    }
    .sliderProjets .navSliderPj a.active:last-child{
        border-radius: 0px 0px 20px 20px;
    }
    .contentPjDetails{
        display: flex;
        flex-direction: column;
    }
    .contentPjDetails img{
        width: 90%;
        margin: 0 auto;
    }
    .pjText{
        margin-left: 5%;
        width: 90vw;
    }
    .bande-pj{
        display: none;
    }
    .bande-pj-2{
        display: none;
    }
}
</style>

<script>
import { gsap } from "gsap";

export default{
    data() {
    return{
        selectedPjLink: 'https://www.refugeshautesbauges.fr/',
        selectedPjId: 0,
        selectedPjImg: "/img/rhb.png",
        selectedPjName: 'Refuges Hautes Bauges',
        selectedCompTxt: "J'ai découvert l'Html au lycée grâce à la spécialité NSI, j'ai tout de suite eu un fort intérêt pour ce langage et pour le développement orienté WEB",
        pjs : [
            {
                id: 0,
                name: 'Refuges Hautes Bauges',
                description: 'html 1',
                src: "/img/rhb.png",
                txt: "Le site web de l'association Refuges Hautes Bauges a été créé à la suite d'un projet inter-écoles d'une semaine. Notre objectif était d'aider cette association à améliorer sa présence digitale en créant un site internet et en améliorant sa communication digitale, notamment en créant un nouveau logo adapté à ses besoins. Pour répondre à leurs besoins, nous avons créé leur nouveau site internet en utilisant WordPress, ainsi qu'une charte graphique complète grâce à la suite Adobe. Malgré les limites en termes de ressources, nous avons réussi à fournir un site web moderne et fonctionnel pour l'association.",
                lien: 'https://www.refugeshautesbauges.fr/',
            },
            {
                id: 1,
                name: 'ADB Services',
                description: 'CSS 1',
                src: "/img/adb.png",
                txt: "Lors de mon stage chez Alpha Agency, j'ai réalisé le site web pour ADB Services en utilisant Wix. J'ai travaillé sur la maquette et la personnalisation du design pour répondre aux besoins spécifiques de l'entreprise. Le choix de Wix m'a permis de travailler rapidement et efficacement, pour créer un site fonctionnel et esthétique qui répondait aux attentes du client. Cette expérience a été très enrichissante pour moi sur le plan professionnel et personnel.",
                lien: 'https://www.adbservices.fr/',
            },
            {
                id: 2,
                name: 'Gear Rallye',
                description: 'Gear rallye',
                src: "/img/gear.png",
                txt: "Il s'agit d'un site internet que j'ai créé lors d'une semaine d'examens en première année de bachelor. Le sujet étant libre, j'ai choisi de créer un rallye de supercars. Le site présente les éléments de la charte graphique ainsi que les informations clés de l'événement. Bien que le site ne soit pas entièrement finalisé en raison de contraintes de temps, il reste à finaliser le responsive design et à améliorer certains détails",
                lien: 'https://github.com/JeanBeq/Projet-partiel-site-Gear-Rallye',
            },
        ]
    }
  },
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
    },
    methods:{
    selectPj(pj) {
        this.selectedPjId = pj.id
        const selectedPj = this.pjs.find(element => element.id === this.selectedPjId);

        this.selectedPjImg = selectedPj.src
        this.selectedPjLink = selectedPj.lien
    }
  }
}
</script>