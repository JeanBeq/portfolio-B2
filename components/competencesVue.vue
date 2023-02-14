<template>
    <div class="bandeCompetences">
        <h2>MES - <strong>compétences</strong></h2>
        <div class="competencesShow">
            <div class="nav-comp-menu">
                <a v-for="comp in comps" :key="comp.id" @click="selectComp(comp)" :class="{active: comp.id === selectedCompId }">
                    {{ comp.name }}
                </a>
            </div>
            <div class="cardComp">
                <div class="left-comp-card">
                    <img :src="selectedCompImg" alt="">
                </div>
                <div class="right-comp-card">
                    <p>{{ selectedCompTxt }}</p>
                </div>
                <a href="/about" class="shadow-2xl">En savoir plus</a>
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
    }
    .bandeCompetences h2 strong{
        font-weight: bold;
        text-transform: uppercase;
    }
    .nav-comp-menu .active{
        background-color: #403d39;
        box-shadow: rgb(38, 57, 77) 0px 20px 30px -10px;
    }
    .cardComp img{
        height: 200px;
        margin-left: 40px;
        transition: all ease-in-out 0.2s;
    }
    .cardComp{
        position: relative;
        width: 1000px;
        background-color: #403d39;
        border-radius: 0 15px 15px 0;
        display: flex;
        flex-direction: row;
    }
    .nav-comp-menu{
        width: 300px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
    }
    .nav-comp-menu a{
        background-color: #a5a5a5;
        color: white;
        width: 100%;
        height: 50px;
        text-align: center;
        display: flex;
        align-items: center;
        justify-content: center;
        transition: all ease-in-out 0.2s;
    }
    .nav-comp-menu a:first-child{
        border-radius: 15px 0 0 0;
    }
    .nav-comp-menu a:last-child{
        border-radius: 0 0 0 15px;
    }
    .competencesShow{
        width: 95%;
        margin: 0 auto;
        padding-top: 30px;
        display: flex;
        flex-direction: row;
        margin-bottom: 30px;
    }
    .right-comp-card{
        position: relative;
    }
    .right-comp-card p{
        margin-left: 30px;
        margin-top: 50px;
        width: 600px;
    }
    .cardComp a{
        border-radius: 30px;
        background-color: #f6bd60;
        padding: 10px;
        position: absolute;
        right: 40px;
        bottom: 40px;
        color: white;
    }
    .left-comp-card{
        display: flex;
        align-items: center;
        justify-content: center;
        width: 300px;
    }
</style>

<script lang="ts">

export default {
  name: 'ListComp',
  data() {
    return{
        selectedCompId: 0,
        FirstComp: 0,
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
                txt: "De même que l'Html j'ai découvert le CSS au lycée grâce à la spécialité NSI, j'ai bien aimé directement le coté Front"
            },
            {
                id: 2,
                name: 'JS',
                description: 'JS 1',
                src: "/img/jslogo.png",
                txt: "J'ai découvert le Javascript en première année d'études à MyDigitalSchool et de même que tous les autres langages dit Front j'ai accroché directement."
                
            },
            {
                id: 3,
                name: 'PHP',
                description: 'PHP 1',
                src: "/img/phplogo.png",
                txt: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed massa nisl, pretium sed orci vitae, commodo dictum arcu. Phasellus pulvinar augue et efficitur eleifend. In in malesuada ex. Aenean urna odio, porta quis ultrices nec, pulvinar quis velit. Nullam vitae nunc purus. Sed a gravida tortor."
            },
            {
                id: 4,
                name: 'SQL',
                description: 'sql 1',
                src: "/img/sqllogo.png",
                txt: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed massa nisl, pretium sed orci vitae, commodo dictum arcu. Phasellus pulvinar augue et efficitur eleifend. In in malesuada ex. Aenean urna odio, porta quis ultrices nec, pulvinar quis velit. Nullam vitae nunc purus. Sed a gravida tortor."
            },
            {
                id: 5,
                name: 'Python',
                description: 'Py 1',
                src: "/img/pylogo.png",
                txt: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed massa nisl, pretium sed orci vitae, commodo dictum arcu. Phasellus pulvinar augue et efficitur eleifend. In in malesuada ex. Aenean urna odio, porta quis ultrices nec, pulvinar quis velit. Nullam vitae nunc purus. Sed a gravida tortor."
            },
        ]
    }
  },
  methods:{
    selectComp(comp) {
        this.selectedCompId = comp.id
        this.selectedCompName = comp.name
        this.selectedCompTxt = comp.txt
        const selectedComp = this.comps.find(element => element.id === this.selectedCompId);
        this.selectedCompImg = selectedComp.src
    }
  }
}
</script>