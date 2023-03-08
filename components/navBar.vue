<template>
    <div class="cursor"></div>
    <div class="cursor2"></div>
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
    @media screen and (min-width: 991px) {
        .cursor {
            z-index: 100;
            width: 40px;
            height: 40px;
            border-radius: 100%;
            border: 1px solid white;
            transition: all 200ms ease-out;
            position: fixed;
            pointer-events: none;
            left: 0;
            top: 0;
            transform: translate(calc(-50% + 15px), -50%);
        }
        .cursor2 {
            z-index: 99;
            width: 15px;
            height: 15px;
            border-radius: 100%;
            background-color: grey;
            opacity: .3;
            position: fixed;
            transform: translate(-50%, -50%);
            pointer-events: none;
            transition: width .3s, height .3s, opacity .3s;
        }
        .hover {
            width: 70px;
            height: 70px;
            background-color: #f6bd60 ;
            opacity: 0.5;
            z-index: 100;
        }
        .cursorinnerhover {
            width: 50px;
            height: 50px;
            opacity: .5;
            z-index: 100;
        }
    }
    @media screen and (max-width: 991px) {
        nav{
            width: 100vw;
            margin: 0 auto;
            padding: 15px;
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

            
            var cursor = document.querySelector('.cursor');
            var cursorinner = document.querySelector('.cursor2');
            var a = document.querySelectorAll('a');

            document.addEventListener('mousemove', function(e){
                var x = e.clientX;
                var y = e.clientY;
                cursor.style.transform = `translate3d(calc(${e.clientX}px - 50%), calc(${e.clientY}px - 50%), 0)`
            });

            document.addEventListener('mousemove', function(e){
                var x = e.clientX;
                var y = e.clientY;
                cursorinner.style.left = x + 'px';
                cursorinner.style.top = y + 'px';
            });

            document.addEventListener('mousedown', function(){
                cursor.classList.add('click');
                cursorinner.classList.add('cursorinnerhover')
            });

            document.addEventListener('mouseup', function(){
                cursor.classList.remove('click')
                cursorinner.classList.remove('cursorinnerhover')
            });

            a.forEach(item => {
            item.addEventListener('mouseover', () => {
                cursor.classList.add('hover');
            });
            item.addEventListener('mouseleave', () => {
                cursor.classList.remove('hover');
            });
            })
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
