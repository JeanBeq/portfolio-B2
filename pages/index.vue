<template>
    <div class="cursor">
        <div class="cursor__ball cursor__ball--big ">
            <svg height="30" width="30">
            <circle cx="15" cy="15" r="12" stroke-width="0"></circle>
            </svg>
        </div>
        <div class="cursor__ball cursor__ball--small">
            <svg height="10" width="10">
            <circle cx="5" cy="5" r="4" stroke-width="0"></circle>
            </svg>
        </div>
        </div>
    <div>
        <NavBar />
        <MainHome />
        <BandeDefil />
        <CompetencesVue />
        <ProjetsVue />
        <footerVue />
    </div>
</template>

<style>
    @import url('https://fonts.googleapis.com/css2?family=DM+Sans&display=swap');
    body{
        background-color: black;
        cursor: none;
    }
    p, h1, h2, h3, a{
        font-family: 'DM Sans', sans-serif;
    }
    .cursor {
        pointer-events: none;
    }
    .cursor__ball {
        position: fixed;
        top: 0;
        left: 0;
        mix-blend-mode: difference;
        z-index: 1000;
    }
    .cursor__ball circle {
        fill: #f7f8fa;
    }

</style>

<script>
"use strict";

const $bigBall = document.querySelector('.cursor__ball--big');
const $smallBall = document.querySelector('.cursor__ball--small');
const $hoverables = document.querySelectorAll('.hoverable');

// Listeners
document.body.addEventListener('mousemove', onMouseMove);
for (let i = 0; i < $hoverables.length; i++) {
  $hoverables[i].addEventListener('mouseenter', onMouseHover);
  $hoverables[i].addEventListener('mouseleave', onMouseHoverOut);
}

// Move the cursor
function onMouseMove(e) {
  TweenMax.to($bigBall, .4, {
    x: e.pageX - 15,
    y: e.pageY - 15
  });
  TweenMax.to($smallBall, .1, {
    x: e.pageX - 5,
    y: e.pageY - 7
  });
}

// Hover an element
function onMouseHover() {
  TweenMax.to($bigBall, .3, {
    scale: 4
  });
}
function onMouseHoverOut() {
  TweenMax.to($bigBall, .3, {
    scale: 1
  });
}
</script>
