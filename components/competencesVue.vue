<template>
    <div class="bandeCompetences">
        <h2 data-aos="fade-up">MES - <strong>compétences</strong></h2>
        <div class="competencesShow">
            <div v-for="(comp, index) in comps" :key="index" class="slide">
            </div>
            <div class="cardComp">
                <div class="left-comp-card">
                    <img :src="selectedCompImg" alt="">
                </div>
                <div class="right-comp-card">
                    <p data-aos="fade-left">{{ selectedCompTxt }}</p>
                </div>
                <div class="buttonSlider">
                    <button @click="prevPage" :disabled="currentPage === 0">
                        <img src="/img/Arrow2.svg" alt=""  id="arrowPrev">
                    </button>
                    <h3>Défiler</h3>
                    <button @click="nextPage" :disabled="currentPage === totalPages-1"><img src="/img/Arrow1.svg" alt=""></button>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
    .bandeCompetences{
        background-color: #323232;
        border-top: dashed #f6bd60 0.5px;
        padding-bottom: 30px;
    }
    .bandeCompetences h2{
        color: white;
        padding-top: 30px;
        font-size: 55px;
        text-align: center;
    }
    .bandeCompetences h2 strong{
        font-weight: bold;
        text-transform: uppercase;
    }
    .cardComp .left-comp-card img{
        height: 300px;
        width: 300px;
        margin-left: 40px;
        transition: all ease-in-out 0.2s;
    }
    .cardComp{
        position: relative;
        width: 1000px;
        height: 400px;
        background-color: #D9D9D9;
        border-radius:20px;
        display: flex;
        flex-direction: row;
    }
    .competencesShow{
        width: 95%;
        margin: 0 auto;
        padding-top: 30px;
        display: flex;
        justify-content: center;
        flex-direction: row;
        margin-bottom: 30px;
    }
    .right-comp-card{
        position: relative;
        width: 80%;
    }
    .right-comp-card p{
        margin-left: 50px;
        margin-right: 50px;
        margin-top: 50px;
        width: 90%;
        color: black;
    }
    .cardComp a{
        border-radius: 30px;
        background-color: #f6bd60;
        padding: 10px;
        position: absolute;
        right: 40px;
        bottom: 40px;
    }
    .left-comp-card{
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .cardComp .buttonSlider{
        position: absolute;
        transform: translate(-50%, -50%);
        left: 88%;
        top: 100%;
        display: flex;
        align-items: center;
        background-color: #f6bd60;
        width: 400px;
        border-radius: 10px;
        justify-content: space-around;
    }
    .cardComp .buttonSlider button{
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 10px;
        border: none;
        background: transparent;
    }
    .cardComp .buttonSlider button img{
        height: 24px;
    }
    @media screen and (max-width: 991px) {
        .cardComp{
            width: 90%;
            height: 470px;
            display: flex;
            flex-direction: column;
        }
        .cardComp .buttonSlider{
            left: 50%;
            top: 100%;
            width: 200px;
        }
        .cardComp .left-comp-card img{
            height: 200px;
            width: 200px;
            margin-left: 0px;
            margin-top: 40px;
        }
        .right-comp-card p{
            margin-bottom: 50px;
            text-align: center;
        }
        .bandeCompetences h2{
            font-size: 12vw;
        }
    }
</style>

<script lang="ts">

export default {
  name: 'ListComp',
  data() {
    return{
        currentPage: 0,
        selectedCompId: 0,
        selectedCompImg: "/img/htmllogo.png",
        selectedCompName: 'HTML',
        selectedCompTxt: "J'ai découvert l'Html au lycée grâce à la spécialité NSI, j'ai tout de suite eu un fort intérêt pour ce langage et pour le développement orienté WEB",
        comps : [
            {
                id: 0,
                name: 'HTML',
                description: 'html 1',
                src: "/img/htmllogo.png",
                txt: "J'ai découvert l'Html au lycée grâce à la spécialité NSI, j'ai tout de suite eu un fort intérêt pour ce langage et pour le développement orienté WEB"
            },
            {
                id: 1,
                name: 'CSS',
                description: 'CSS 1',
                src: "/img/csslogo.png",
                txt: "De même que l'Html, j'ai découvert le CSS au lycée grâce à la spécialité NSI, j'ai bien aimé directement le coté Front"
            },
            {
                id: 2,
                name: 'JS',
                description: 'JS 1',
                src: "/img/jslogo.png",
                txt: "J'ai découvert le Javascript en première année d'études à My Digital School et de même que tous les autres langages dit Front, j'ai accroché directement."
                
            },
            {
                id: 3,
                name: 'PHP',
                description: 'PHP 1',
                src: "/img/phplogo.png",
                txt: "J'ai découvert le PHP lors de ma première année d'étude à My Digital School. J'ai pu faire de nombreux projets en PHP."
            },
            {
                id: 4,
                name: 'SQL',
                description: 'sql 1',
                src: "/img/sqllogo.png",
                txt: "J'ai appris le SQL en même temps que le PHP lors de ma formation."
            },
            {
                id: 5,
                name: 'Python',
                description: 'Py 1',
                src: "/img/pylogo.png",
                txt: "J'ai appris le Python grâce à la spécialité NSI au lycée ou j'ai pu faire de nombreux petits projets et j'ai continué en parallèle pour des petits projets personnels."
            },
            {
                id: 6,
                name: 'WordPress',
                description: 'Wp',
                src: "/img/wplogo.png",
                txt: "J'ai appris à utiliser le CMS WordPress au sein de ma formation à My Digital School, j'ai pu approfondir ses connaissances en réalisant des projets scolaires via ces outils."
            },
            {
                id: 7,
                name: 'Vue js',
                description: 'Wp',
                src: "/img/vuelogo.png",
                txt: "J'ai découvert le framework Vue.js en deuxième année de bachelor web & multimédia, j'ai pu réaliser plusieurs projets dessus et ce portfolio est réalisé avec Vue.js et Nuxt js"
            },
            {
                id: 7,
                name: 'Symfony',
                description: 'Symfony',
                src: "/img/symflogo.png",
                txt: "J'ai eu l'occasion de découvrir le Framework Symfony en deuxième année de bachelor où nous avons pu réaliser une multitude de projets pour maîtriser cet outil."
            },
        ]
    }
  },
  methods: {
    prevPage() {
      if (this.currentPage >= 0) {
        this.currentPage--;
        this.selectedCompImg = this.comps[this.currentPage].src;
        this.selectedCompTxt = this.comps[this.currentPage].txt;
      }
    },
    nextPage() {
      if (this.currentPage < this.totalPages -1) {
        this.currentPage++;
        this.selectedCompImg = this.comps[this.currentPage].src;
        this.selectedCompTxt = this.comps[this.currentPage].txt;
      }
    },
  },
  computed: {
    totalPages() {
      return Math.ceil(this.comps.length);
    },
  },
}
</script>