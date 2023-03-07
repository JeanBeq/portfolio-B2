<template>
    <div class="mainContact">
        <div class="topContact">
            <h1>me contacter</h1>
            <h2>Mon profil vous intéresse</h2>
            <a href="#" class="cta">
                <span>Envoyer un email</span>
                <svg width="13px" height="10px" viewBox="0 0 13 10">
                    <path d="M1,5 L11,5"></path>
                    <polyline points="8 1 12 5 8 9"></polyline>
                </svg>
            </a>
            <!-- <a href="mailto:jean.bequilleux@gmail.com">Envoyer un email</a> -->
        </div>
        <div class="midContact">
            <div class="bandeContact"></div> 
            <div class="iconesRs">
                <a href=""><img src="/img/tel.svg" alt=""></a>
                <a href=""><img src="/img/github.svg" alt=""></a>
                <a href=""><img src="/img/linkedin.svg" alt=""></a>
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
    /* transform: translate(-50%); */
    /* margin-left: 52rem; */
    margin-left: -400px;
    margin-top: -15px;
    margin-bottom: 20px;
}
.mainContact .topContact a{
    margin-left: 470px;
}
.bandeContact{
    height: 0.5px;
    width: 80%;
    background-color: black;
    margin: 0 auto;
}
.iconesRs{
    display: flex;
    justify-content: space-around;
    margin-top: 20px;
    margin-bottom: 20px;
}
.cta {
  position: relative;
  margin: auto;
  padding: 19px 22px;
  transition: all .2s ease; }
  .cta:before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    display: block;
    border-radius: 28px;
    background: #f6bd60;
    width: 56px;
    height: 56px;
    transition: all .3s ease; }
  .cta span {
    position: relative;
    font-size: 16px;
    line-height: 18px;
    font-weight: 900;
    letter-spacing: .25em;
    text-transform: uppercase;
    vertical-align: middle; }
  .cta svg {
    position: relative;
    top: 0;
    margin-left: 10px;
    fill: none;
    stroke-linecap: round;
    stroke-linejoin: round;
    stroke: #111;
    stroke-width: 2;
    transform: translateX(-5px);
    transition: all .3s ease; }
  .cta:hover:before {
    width: 100%;
    background: #f6bd60; }
  .cta:hover svg {
    transform: translateX(0); }
  .cta:active {
    transform: scale(0.96); }
</style>