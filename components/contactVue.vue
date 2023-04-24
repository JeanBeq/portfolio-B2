<template>
    <div class="mainContact">
        <div class="topContact">
            <h1>Me contacter</h1>
            <h2>Mon profil vous intéresse ?</h2>
            <a href="mailto:jean.bequilleux@gmail.com" class="mainBtn">Envoyer un email</a>
        </div>
        <div class="midContact">
            <div class="bandeContact"></div> 
            <div class="iconesRs">
                <a href="" data-aos="zoom-in"><img src="/img/tel.svg" alt=""></a>
                <a href="https://github.com/JeanBeq" data-aos="zoom-in"><img src="/img/github.svg" alt=""></a>
                <a href="https://www.linkedin.com/in/jean-bequilleux/" data-aos="zoom-in"><img src="/img/linkedin.svg" alt=""></a>
            </div>
            <div class="bandeContact"></div>
        </div>
        
    </div>
    
</template>

<style>
.mainContact .topContact h1{
    text-transform: uppercase;
    color: black;
    margin-left: 30.8%;
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
  background-size: 100% 100%; 
  color: #fff; 
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
@media screen and (max-width: 991px){
  .mainContact .topContact h1{
    font-size: 12vw;
}
}
</style>