<template>
    <nav id="navBar">
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
        z-index: 10;
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
        transform:translate(-50%, -50%);
        transition: top 0.3s;
    }
    nav a{
        color: white;
        text-decoration: none;
        font-size: 18px;
        margin-right: 25px;
    }
    nav p{
        color: white;
        margin-left: 20px;
        font-size: 18px;
    }
</style>

<script>
    export default{
        mounted() {
            var prevScrollpos = window.pageYOffset;
            window.onscroll = function() {
            var currentScrollPos = window.pageYOffset;
            if (prevScrollpos < currentScrollPos) {
                document.getElementById("navBar").style.top = "-10%";
            } else {
                document.getElementById("navBar").style.top = "10%";
            }
            prevScrollpos = currentScrollPos;
        }
        }
    }
</script>