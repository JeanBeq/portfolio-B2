<template>
    <nav id="navBar">
        <div class="nav-left" >
            <img src="/img/logo.png" alt="">
        </div>
        <div class="menu-icon" @click="toggleMenu">
            <Menu 
            color="white"
            :size="32"
            />
        </div>
        <div class="nav-right" :class="{ active: menuOpen }">
            <a href="/" class="uppercase">Accueil</a>
            <a href="/about" class="uppercase">A propos</a>
            <a href="/contact" class="uppercase">Contact</a>
        </div>
    </nav>
</template>

<style>
    nav{
        z-index: 10;
        background-color: #484848;
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
    .nav-left{
        width: 30px;
    }
    .menu-icon{
        display: none;
    }
    .nav-right {
        transition:2s all ease-in-out;
    }
    @media screen and (max-width: 991px) {
        nav{
            width: 100%;
            margin: 0 auto;
            padding: 0 20px;
            border-radius: 10px;
            display: flex;
            justify-content: space-between;
            position: fixed;
            top: 5%;
            left: 50%;
            transform:translate(-50%, -50%);
        }
        .nav-right {
            display: none;
        }
        .nav-right.active {
            display: flex;
            flex-direction: column;
            align-items: center;
            position: absolute;
            top: 90%;
            left: 0;
            width: 100%;
            background-color: #333;
            z-index: 999;
            transition:2s all ease-in-out;
            border-radius: 0px 0px 15px 15px;
        }
        .nav-right.active a {
            font-size: 22px;
            margin: 0;
            padding: 5px;
        }
        .menu-icon {
            display: block;
            padding: 15px;
        }
        nav {
            padding: 0 20px;
        }
        .nav-left{
            width: 30px;
            display: flex;
            align-items: center;
        }
}
</style>

<script setup>
import { Menu } from 'lucide-vue-next';
</script>

<script>
    export default{
        data() {
            return{
                menuOpen: false
            }
        },
        methods: {
            toggleMenu: function() {
            this.menuOpen = !this.menuOpen;
            }
        },
        mounted() {

            window.addEventListener('DOMContentLoaded', function() {
            var menuIcon = document.querySelector('.menu-icon');
            var menu = document.querySelector('.menu');

            menuIcon.addEventListener('click', function() {
                menu.classList.toggle('active');
            });
            });

            var prevScrollpos = window.pageYOffset;
            window.onscroll = function() {
            var currentScrollPos = window.pageYOffset;
            if (prevScrollpos < currentScrollPos) {
                document.getElementById("navBar").style.top = "-10%";
            } else {
                if (window.innerWidth < 960) {
                    var navHeightValue = '5%'
                } else {
                    var navHeightValue = '10%'
                }
                document.getElementById("navBar").style.top = navHeightValue;
            }
            prevScrollpos = currentScrollPos;
            }
            }
        }
</script>
