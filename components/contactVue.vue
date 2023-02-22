<template>
    <div class="contact-main">
        <div class="left-contact">
            <div class="infos-cnt">
                <div class="contact-mail">
                <Mail fill="black" :size="64" :stroke-width="0.4" class="icons"/>
                <h3>jean.bequilleux@gmail.com</h3>
            </div>
            <div class="contact-ink">
                <Linkedin fill="black" :size="64" :stroke-width="0.4" class="icons"/>
                <h3><a href="https://www.linkedin.com/in/jean-bequilleux/">Jean Béquilleux</a></h3>
            </div>
            </div>           
        </div>
        <div class="right-contact">
            <h3>CONTACT</h3>
        </div>
    </div>
</template>

<style>
.contact-main{
    display: flex;
}
.left-contact, .right-contact{
    width: 50%;
}
.icons{
    color: white;
}
.left-contact{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
.contact-mail, .contact-ink{
    display: flex;
    align-items: center;
}
.contact-mail h3, .contact-ink h3{
    color: black;
    margin-left: 20px;
}
.infos-cnt{
    border-radius: 20px;
    width: 80%;
    margin: 40px;
    background-color: white;
    padding: 15px;
    display: flex;
    flex-direction: column;
    align-items: center;
}
.right-contact h3{
    color: white;
    text-align: center;
    font-weight: bold;
    margin: 0 auto;
    font-size: 70px;
}
.right-contact{
    display: flex;
    align-items: center;
}
</style>

<script setup>
import {  Mail, Linkedin } from 'lucide-vue-next';
</script>