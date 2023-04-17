<template>
    <footer>
        <div class="footer-left">
            <p>Fait par <a href="https://www.linkedin.com/in/jean-bequilleux/">Jean Béquilleux</a> </p>
        </div>
        <div class="footer-right">
            <a href="/contact">Contact</a>
        </div>
    </footer>
</template>

<style>
    footer p, footer a{
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
    .footer-left, .footer-right{
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .footer-left{
        margin-left: 5vw;
    }
    .footer-left a{
        text-decoration: underline;
    }
    .footer-right{
        margin-right: 5vw;
    }
</style>