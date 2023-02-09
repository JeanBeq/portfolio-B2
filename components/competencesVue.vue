<template>
    <div class="bandeCompetences">
        <h2>MES - <strong>compétences</strong></h2>
        <div class="competencesShow">
            <div class="nav-comp-menu">
                <a v-for="comp in comps" :key="comp.id" @click="selectComp(comp)" :class="{ active: comp.id === selectedCompId }">
                    {{ comp.name }}
                </a>
            </div>
            <div class="cardComp">
                <div class="left-comp-card">
                    <img :src="selectedCompImg" alt="">
                </div>
                <div class="right-comp-card">
                    <p>{{ selectedCompName }}</p>
                </div>
            </div>
            
    </div>
    </div>
</template>

<style>
    .bandeCompetences{
        background-color: #323232;
        border-top: dashed #f6bd60;
    }
    .bandeCompetences h2{
        color: white;
        font-size: 55px;
    }
    .bandeCompetences h2 strong{
        font-weight: bold;
        text-transform: uppercase;
    }
    .active{
        background-color: red;
    }
    .cardComp img{
        height: 100px;
    }
</style>

<!-- <template>
    <div class="container">
        <div class="nav">
            <a v-for="item in artists" @click="selectArtist(item)" :class="{ active: item.id === selectedArtistId }">
                {{ item.name }}
            </a>
        </div>
        <div class="main">
            <img id="imgartiste" :src="selectedArtistImg" alt="">
            <div class="degrade"></div>
            <a href="">réserver</a>
            <p id="dateArtist">{{artists[selectedArtistId].date}}</p>
            <p id="locaArtist">{{artists[selectedArtistId].loca}}</p>
        </div>
    </div>
</template> -->

<script lang="ts">

export default {
  name: 'ListComp',
  data() {
    return{
        selectedCompId: 0,
        FirstComp: 0,
        selectedCompImg: "/img/htmllogo.png",
        selectedCompName: 'HTML',
        comps : [
            {
                id: 0,
                name: 'HTML',
                description: 'html 1',
                src: "/img/htmllogo.png"
            },
            {
                id: 1,
                name: 'CSS',
                description: 'CSS 1',
                src: "/img/csslogo.png"
            },
            {
                id: 2,
                name: 'JS',
                description: 'JS 1',
                src: "/img/jslogo.png"
            },
            {
                id: 3,
                name: 'PHP',
                description: 'PHP 1',
                src: "/img/phplogo.png"
            },
            {
                id: 4,
                name: 'SQL',
                description: 'sql 1',
                src: "/img/sqllogo.png"
            },
        ]
    }
  },
  methods:{
    selectComp(comp) {
        this.selectedCompId = comp.id
        this.selectedCompName = comp.name
        const selectedComp = this.comps.find(element => element.id === this.selectedCompId);
        this.selectedCompImg = selectedComp.src
    }
  }
}
</script>