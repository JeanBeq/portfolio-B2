<template>
    <footer>
        <div class="footer-left">
            <p>Fait par Jean Béquilleux</p>
        </div>
        <div class="footer-right">
            <p>partie droite du footer</p>
        </div>
    </footer>
</template>

<style>
    p{
        color: white;
    }
    footer{
        display: flex;
        justify-content: space-between;
    }
    footer{
        background-color: black;
        height: 100px;
    }
    .footer-left{
        display: flex;
        align-items: center;
        justify-content: center;
    }
</style>