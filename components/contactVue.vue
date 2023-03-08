<template>
    <div class="mainContact">
        <div class="topContact">
            <h1>me contacter</h1>
            <h2>Mon profil vous intéresse</h2>
            <a href="mailto:jean.bequilleux@gmail.com" class="mainBtn">Envoyer un email</a>
        </div>
        <div class="midContact">
            <div class="bandeContact"></div> 
            <div class="iconesRs">
                <a href=""><img src="/img/tel.svg" alt=""></a>
                <a href="https://github.com/JeanBeq"><img src="/img/github.svg" alt=""></a>
                <a href="https://www.linkedin.com/in/jean-bequilleux/"><svg width="64" height="64" viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M11.9999 25.3334H10.6666C8.15243 25.3334 6.89536 25.3334 6.11429 26.1144C5.33325 26.8955 5.33325 28.1526 5.33325 30.6667V53.3334C5.33325 55.8475 5.33325 57.1046 6.11429 57.8856C6.89536 58.6667 8.15243 58.6667 10.6666 58.6667H11.9999C14.5141 58.6667 15.7711 58.6667 16.5522 57.8856C17.3333 57.1046 17.3333 55.8475 17.3333 53.3334V30.6667C17.3333 28.1526 17.3333 26.8955 16.5522 26.1144C15.7711 25.3334 14.5141 25.3334 11.9999 25.3334Z" fill="black" stroke="black" stroke-width="1.5"/>
                        <path d="M17.3333 11.3334C17.3333 14.6471 14.647 17.3334 11.3333 17.3334C8.01955 17.3334 5.33325 14.6471 5.33325 11.3334C5.33325 8.01967 8.01955 5.33337 11.3333 5.33337C14.647 5.33337 17.3333 8.01967 17.3333 11.3334Z" fill="black" stroke="black" stroke-width="1.5"/>
                        <path d="M32.8693 25.3334H30.6666C28.1525 25.3334 26.8954 25.3334 26.1143 26.1144C25.3333 26.8955 25.3333 28.1526 25.3333 30.6667V53.3334C25.3333 55.8475 25.3333 57.1046 26.1143 57.8856C26.8954 58.6667 28.1525 58.6667 30.6666 58.6667H31.9999C34.5141 58.6667 35.7711 58.6667 36.5522 57.8856C37.3333 57.1046 37.3333 55.8475 37.3333 53.3334L37.3335 44.0003C37.3335 39.5822 38.7415 36.0003 42.901 36.0003C44.9805 36.0003 46.6666 37.7912 46.6666 40.0003V52.0003C46.6666 54.5144 46.6666 55.7715 47.4477 56.5526C48.2285 57.3336 49.4858 57.3336 51.9999 57.3336H53.3298C55.8434 57.3336 57.1002 57.3336 57.8813 56.5528C58.6623 55.772 58.6626 54.5152 58.6631 52.0016L58.6669 37.3339C58.6669 30.7067 52.3637 25.334 46.1247 25.334C42.573 25.334 39.4045 27.075 37.3335 29.7974C37.3333 28.1171 37.3333 27.2771 36.9685 26.6534C36.7373 26.2583 36.4082 25.9295 36.0133 25.6984C35.3895 25.3334 34.5495 25.3334 32.8693 25.3334Z" fill="black" stroke="black" stroke-width="1.5" stroke-linejoin="round"/>
                    </svg>
</a>
            </div>
            <div class="bandeContact"></div>
        </div>
        
    </div>
    
</template>

<style>
.mainContact .topContact h1{
    text-transform: uppercase;
    color: black;
    text-align: center;
    font-size: 80px;
    font-weight: bold;
    margin-top: 80px;
}
.mainContact .topContact h2{
    color: black;
    text-align: left;
    margin-left: 30.8%;
    margin-top: -15px;
    margin-bottom: 20px;
}
.mainContact .topContact a{
    margin-left: 30.8%;
    padding: 10px;
    border-radius: 60px;
    border: 1px solid black;
    display: inline-block;
    width: fit-content;
    margin-bottom: 20px;
    background-image: linear-gradient(#f6bd60, #f6bd60); 
    background-repeat: no-repeat; 
    background-size: 100% 0; 
    background-position: bottom; 
    transition: background-size 0.2s ease-out; 
}
.mainContact .topContact a:hover {
  background-size: 100% 100%; /* on augmente la hauteur du dégradé pour remplir le background du lien */
  color: #fff; /* on change la couleur de texte du lien lorsque le background est rempli */
}
.mainContact .topContact a:hover{
    box-shadow: rgba(255, 255, 255, 0.1) 0px 1px 1px 0px inset, rgba(50, 50, 93, 0.25) 0px 50px 100px -20px, rgba(0, 0, 0, 0.3) 0px 30px 60px -30px;
}
.bandeContact{
    height: 0.5px;
    width: 80%;
    background-color: black;
    margin: 0 auto;
}
.bandeContact:last-child{
    margin-bottom: 40px
}
.iconesRs{
    display: flex;
    justify-content: space-around;
    margin-top: 20px;
    margin-bottom: 20px;
}
.iconesRs path{
  fill: black;
}
.iconesRs svg:hover{
    animation: fill 1s forwards;
    fill: #DADADA;
}

@keyframes fill-up {
  from {
    fill: transparent;
  }
  to {
    fill: #f6bd60;
  }
  0% {
    fill: transparent;
    transform: translate(0, 100%);
  }
  100% {
    fill: #f6bd60;
    transform: translate(0, 0);
  }
}
</style>

<script>
import { gsap } from "gsap";
    export default{
      Mounted() {
        gsap.fromTo(".mainBtn",
            {
                opacity: 0,
                y: "100%",
            },
            {
                duration: 1.5,
                opacity: 1,
                y: 0,
                delay: 1.3,
                ease: "power3.inOut",
                stagger: 0.1,
            }
  );
}
    }
</script>