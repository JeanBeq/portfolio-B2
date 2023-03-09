<template>
    <div class="cursor"></div>
    <div class="cursor2"></div>
</template>

<style>
    @media screen and (min-width: 991px) {
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
        .cursorinnerhover {
            width: 50px;
            height: 50px;
            opacity: .5;
            z-index: 100;
        }
        .hover{
            width: 50px;
            height: 50px;
        }
    }
</style>

<script>
    export default{
        mounted() {
            var cursor = document.querySelector('.cursor');
            var cursorinner = document.querySelector('.cursor2');
            var a = document.querySelectorAll('a');
            var button = document.querySelectorAll('button');


            document.addEventListener('mousemove', function(e){
                var x = e.clientX;
                var y = e.clientY;
                cursorinner.style.left = x + 'px';
                cursorinner.style.top = y + 'px';
            });

            document.addEventListener('mousedown', function(){
                cursorinner.classList.add('cursorinnerhover')
            });

            document.addEventListener('mouseup', function(){
                cursorinner.classList.remove('cursorinnerhover')
            });

            a.forEach (item => {
            item.addEventListener('mouseover', () => {
                cursorinner.classList.add('hover');
            });
            item.addEventListener('mouseleave', () => {
                cursorinner.classList.remove('hover');
            });
            })
            
            button.forEach (item => {
            item.addEventListener('mouseover', () => {
                cursorinner.classList.add('hover');
            });
            item.addEventListener('mouseleave', () => {
                cursorinner.classList.remove('hover');
            });
            })
        }
    }
</script>