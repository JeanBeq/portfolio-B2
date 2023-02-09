<template>
    <nav class="">
        <div class="nav-left">
            <p>PORTFOLIO</p>
        </div>
        <div class="nav-right">
            <a href="/" class="uppercase">Accueil</a>
            <a href="/projets" class="uppercase">Projets</a>
            <a href="/about" class="uppercase">A propos</a>
            <a href="/contact" class="uppercase">Contact</a>
        </div>
    </nav>
</template>

<style>
    nav{
        background-color: #323232;
        width: 90%;
        margin: 0 auto;
        padding: 15px;
        border-radius: 10px;
        display: flex;
        justify-content: space-between;
        position: fixed;
        top: 10%;
        left: 50%;
        transform:translate(-50%, -50%)
    }
    a{
        color: white;
        text-decoration: none;
        font-size: 18px;
        margin-right: 25px;
    }
    p{
        color: white;
        margin-left: 20px;
        font-size: 18px;
    }
</style>