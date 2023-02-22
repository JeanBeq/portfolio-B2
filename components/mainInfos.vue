<template>
    <div class="main-infos">
        <div class="main-infos-mid">
            <h1>A propos de moi</h1>
            <h2>Developpeur web - web design</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur lectus felis, venenatis nec est eget, rutrum finibus orci. Etiam facilisis, ipsum eget vulputate ornare, lorem libero vulputate purus, in convallis dolor nibh sit amet nisl. In lacus est, porttitor eget purus non, fermentum hendrerit lacus. Phasellus euismod nunc nulla, vel semper ante egestas id. Nullam a leo ligula. Vivamus urna lectus, rhoncus quis cursus id, laoreet sit amet ipsum. Maecenas elementum ligula ac fringilla facilisis.</p>
        </div>
        <div class="main-infos-img">
            <img src="/img/pic_about.jpg" alt="" id="pic-about">
            <h2>MES PASSIONS</h2>
        </div>
        <div class="main-infos-txt">
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur lectus felis, venenatis nec est eget, rutrum finibus orci. Etiam facilisis, ipsum eget vulputate ornare, lorem libero vulputate purus, in convallis dolor nibh sit amet nisl. In lacus est, porttitor eget purus non, fermentum hendrerit lacus. Phasellus euismod nunc nulla, vel semper ante egestas id. Nullam a leo ligula. Vivamus urna lectus, rhoncus quis cursus id, laoreet sit amet ipsum. Maecenas elementum ligula ac fringilla facilisis.</p>
        </div>
    </div>
</template>

<style>
.main-infos{
    display: flex;
    flex-direction: column;
}
.main-infos .main-infos-mid{
    width: 100%;
    padding-left: 80px;
    padding-right: 80px;
    color: white;
}
.main-infos .main-infos-mid h2{
    text-align: center;
    font-size: 60px;
    font-weight: bold;
    margin-top: -25PX;
}.main-infos .main-infos-mid h1{
    text-align: center;
    font-weight: bold;
    margin-top: 50px;
    color: #f6bd60;
}
.main-infos .main-infos-mid p{
    text-align: center;
    margin-top: 20px;
    margin-bottom: 80px;
}
.main-infos .main-infos-img img{
    object-fit: cover;
    width: 100%;
    margin: 0;
    height: 400px;
}
.main-infos-img{
    position: relative;
}
.main-infos-img h2{
    position: absolute;
    transform: translate(-50%, -50%);
    top: 50%;
    left: 50%;
    color: white;
    font-size: 80px;
    font-weight: bold;
}
.main-infos-txt p{
    text-align: center;
    margin-top: 20px;
    margin-bottom: 80px;
}
.main-infos-txt{
    padding-left: 80px;
    padding-right: 80px;
    color: white;
}
</style>

<script>
    export default{
        data(){
            return{
                images : ['/img/pic_about.jpg', '/img/pic_about2.jpg', '/img/pic_about3.jpg'],
                index : 0,
                imgElement : null,
            }
        },
        methods:{
            change () {
                // gsap.set('#pic-about', { attr: { src: this.images[this.index] } });
                this.imgElement = document.querySelector('#pic-about');
                this.imgElement.src=this.images[this.index]
                this.index > 1 ? this.index = 0 : this.index++;
            }
        },
        mounted(){
            setInterval(this.change, 3000);
        },
        // created() {
        //     setInterval(this.change, 3000);
        // }
    }
</script>