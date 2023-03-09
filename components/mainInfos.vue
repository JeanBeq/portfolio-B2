<template>
    <div class="main-infos">
        <div class="main-infos-mid">
            <h1>A propos de moi</h1>
            <h2>Développeur web</h2>
            <div class="mainInfosMidBottom">
                <div class="main-infos-mid-left">
                    <p id="desc">Bonjour à tous ! Je m'appelle Jean j'ai 19 ans et je viens d'Haute Savoie. J'étudie à My Digital School à Annecy, ou j'apprends le développement web ainsi que le design et le marketing digital à travers un bachelor web & multimédias. Je me suis orienté dans le développement web au cours de ma deuxième année de bachelor. J'ai eu l'occasion de mettre en avant mes compétences en réalisant plusieurs stages. <br><br> Lors de ma formation, j'ai eu l'occasion d'apprendre plusieurs langages de programmation. Je maîtrise l'HTML, le CSS, le JS avec les frameworks Vue et Nuxt, le PHP avec le framework symfony, la conception UML et le SQL. Je m'aitrise aussi les CMS WordPress et Wix que j'ai pu découvrir lors de projets scolaires ou de stages. <br><br>
                    En plus de cela grâce à ma formation pluridisciplinaire je maîtrise aussi la suite Adobe, Figma et la suite Office.
                    </p> 
                </div>
                <div class="main-infos-mid-right">
                    <img src="/img/jean.png" alt="" class="mainImg">
                </div>
            </div>
        </div>
        <div class="main-infos-img">
            <img src="/img/pic_about.jpg" alt="" id="pic-about">
            <h2 id="text-anim">MES PASSIONS</h2>
        </div>
        <div class="main-infos-txt">
            <p>Depuis petit, je suis passionné par l'automobile et les sports motorisés en général. J'ai eu l'occasion de pouvoir assister à de nombreux événements dans de nombreux pays. En plus de cela, je suis passionné par la photographie et la vidéo depuis des années et je combine ces deux passions en allant à des événements liés au sport automobile pour prendre des photos. Je pratique aussi plusieurs sports. Je pratique la musculation depuis plus d'un an, je fais du ski alpin depuis tout jeune et de la boxe française depuis un an.</p>
        </div>
    </div>
</template>

<style>
.main-infos{
    display: flex;
    flex-direction: column;
}
.main-infos .main-infos-mid{
    width: 100%;
    padding-left: 80px;
    padding-right: 80px;
    color: white;
}
.main-infos .main-infos-mid h2{
    text-align: center;
    font-size: 8vw;
    font-weight: bold;
    margin-top: -20PX;
}.main-infos .main-infos-mid h1{
    text-align: center;
    font-weight: bold;
    margin-top: 50px;
    color: #f6bd60;
}
.main-infos .main-infos-mid p{
    text-align: center;
    margin-top: 20px;
    margin-bottom: 80px;
}
.main-infos .main-infos-img img{
    object-fit: cover;
    width: 100%;
    margin: 0;
    height: 400px;
}
.main-infos-img{
    position: relative;
}
.main-infos-img h2{
    position: absolute;
    transform: translate(-50%, -50%);
    top: 50%;
    left: 50%;
    color: white;
    font-size: 80px;
    font-weight: bold;
}
.main-infos-txt p{
    text-align: center;
    margin-top: 20px;
    margin-bottom: 80px;
}
.main-infos-txt{
    padding-left: 80px;
    padding-right: 80px;
    color: white;
}
.mainInfosMidBottom{
    display: flex;
    margin: 40px;
}
.main-infos-mid-right, .main-infos-mid-left{
    width: 50%;
}
.main-infos-mid-right img{
    -webkit-box-shadow: -15px -15px 0px 0px #F6BD60; 
    box-shadow: -15px -15px 0px 0px #F6BD60;
    display: inline-block;
}
.main-infos-mid-right img:hover{
    transform: translate(-15px -15px 0px 0px);
}
.main-infos-mid-left{
    display: flex;
    justify-content: center;
    align-items: center;
}
.main-infos-mid-right{
    display: flex;
    justify-content: center;
    align-items: center;
}
@media screen and (max-width: 991px) {
    .main-infos-mid h1{
        font-size: 5vw;
    }
    .main-infos-mid h2{
        font-size: 15vw;
        margin-top: 15px;
    }
    .main-infos-mid-left p{
        font-size: 3vw;
    }
    .mainInfosMidBottom{
        flex-direction:column-reverse;
        margin: 10px;
    }
    .main-infos .main-infos-mid{
        padding-left: 0;
        padding-right: 0;
    }
    .mainInfosMidBottom{
        align-items: center;
    }
    .main-infos-mid-left{
        width: 90%;
    }
    .main-infos-mid-right img{
        margin-top: 20px;
    }
    .main-infos-txt p{
        font-size: 3vw;
        width: 90%;
        text-align: center;
        margin: 0 auto;
        margin-top: 20px; 
        margin-bottom: 20px;
    }
    .main-infos-txt{
        padding-left: 0;
        padding-right: 0;
        
    }
    .main-infos-img h2{
        font-size: 12vw;
    }
}
</style>

<script>
import { gsap } from "gsap";
import { onMounted } from "vue";
    export default{
        data(){
            return{
                images : ['/img/pic_about.jpg', '/img/pic_about2.jpg', '/img/pic_about3.jpg'],
                index : 0,
                imgElement : null,
            }
        },
        methods:{
            change () {
                // gsap.set('#pic-about', { attr: { src: this.images[this.index] } });
                this.imgElement = document.querySelector('#pic-about');
                this.imgElement.src=this.images[this.index]
                this.index > 1 ? this.index = 0 : this.index++;
            }
        },
        mounted(){
            setInterval(this.change, 3000);

            gsap.fromTo("#desc",
            {
                opacity: 0,
                x: "-100%",
            },
            {
            duration: 1.5,
            opacity: 1,
            x: 0,
            }
            );

            gsap.fromTo(
                ".mainImg",
                {
                opacity: 0,
                y: 100,
                rotation: 10,
                },
                {
                duration: 0.5,
                opacity: 1,
                y: 0,
                rotation: 0,
                ease: "power2.inOut",
                }
            );
        },
        // created() {
        //     setInterval(this.change, 3000);
        // }
    }
</script>