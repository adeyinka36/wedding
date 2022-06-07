<template>
    <div class="main-container">
        <div :class="['main', picture]">
            <div class="nav">
                <svg v-if="!showDrop" @click="toggleDrop" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" class="bars"><path d="M0 96C0 78.33 14.33 64 32 64H416C433.7 64 448 78.33 448 96C448 113.7 433.7 128 416 128H32C14.33 128 0 113.7 0 96zM0 256C0 238.3 14.33 224 32 224H416C433.7 224 448 238.3 448 256C448 273.7 433.7 288 416 288H32C14.33 288 0 273.7 0 256zM416 448H32C14.33 448 0 433.7 0 416C0 398.3 14.33 384 32 384H416C433.7 384 448 398.3 448 416C448 433.7 433.7 448 416 448z"/></svg>
                <svg v-else @click="toggleDrop" class="bars" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512"><path d="M310.6 361.4c12.5 12.5 12.5 32.75 0 45.25C304.4 412.9 296.2 416 288 416s-16.38-3.125-22.62-9.375L160 301.3L54.63 406.6C48.38 412.9 40.19 416 32 416S15.63 412.9 9.375 406.6c-12.5-12.5-12.5-32.75 0-45.25l105.4-105.4L9.375 150.6c-12.5-12.5-12.5-32.75 0-45.25s32.75-12.5 45.25 0L160 210.8l105.4-105.4c12.5-12.5 32.75-12.5 45.25 0s12.5 32.75 0 45.25l-105.4 105.4L310.6 361.4z"/></svg>
                <p @click="toggleDrop" >MENU</p>
                <ul :class="['drop-down', showDrop && 'activate-drop']">
                    <li @click="$emit('scroll', 'home');showDrop=false" class="couple"><h2>ADEYEMI & EFE</h2></li>
                    <li @click="$emit('scroll', 'home');showDrop=false">Home</li>
                    <li @click="$emit('scroll', 'story');showDrop=false">Story</li>
                    <li @click="$emit('scroll', 'location');showDrop=false">Location</li>
                    <li @click="$emit('scroll', 'ques');showDrop=false">Q & A</li>
                    <li @click="$emit('scroll', 'travel');showDrop=false">Travel</li>
<!--                    <li @click="$emit('scroll', 'pictures');showDrop=false">Reception</li>-->
                    <li @click="$emit('showGallery')">Gallery</li>
                </ul>
            </div>
            <div @click="showDrop=false" class="description">
                <h1 class="first">ADEYEMI</h1>
                <h1>& EFE</h1>
                <p>We can't wait to share our special day with you. Help us capture our wedding with love.</p>
            </div>
        </div>
    </div>

</template>

<script>
export default{
    name: 'Home',
    data(){
        return{
            showDrop: false,
        }
    },
    props: {
        picture:{
            type: String,
            required: false
        }
    },
    methods: {
        toggleDrop(){
            this.showDrop = !this.showDrop;
        }
    }
}
</script>

<style lang="scss" scoped>
.main-container{
    position: relative;
}
.main-container .main {
    width: 100%;
    height: 100vh;
    max-width: 100%;
    position: relative;
    transition: background 750ms ease-out;
    background-image: url("../../../public/images/picture-1.jpg");
    background-position: 0 .05rem;
    background-size: cover;
    background-repeat: no-repeat;
    .description {
        position: absolute;
        width: 100%;
        height: 100%;
        background: radial-gradient(rgba(0,0,0,0), #000);
        padding: 2rem 5rem 5rem 2rem;
        display: flex;
        flex-direction: column;
        justify-content: flex-end;
        align-items: flex-start;
    }
    .nav {
        width: 120px;
        padding: 1rem;
        z-index: 1000;
        border-radius: 30px;
        ul.drop-down{
            position: absolute;
            transition: height ease-out 1s, opacity linear;
            height: 0;
            visibility: hidden;
            top: 2.5rem;
            left: 1rem;
            background-color: pink;
            width: 70vw;
            max-width: 500px;
            padding: 1rem;
            border-radius: 8px;
            li{
                font-size: 1.3rem;
                margin-top: 1rem;
                font-weight: bold;
                &:hover{
                    cursor: pointer;
                    color:  rgb(178, 124, 106);
                }
            }
            .couple{
                margin-bottom: 2rem;
            }
        }
        ul.activate-drop{
            height: auto;
            visibility: visible;
        }
    }
}
.main-container .map{
    background-image: url("../../../public/images/picture-6.jpg");
}
.main-container .story{
    background-image: url("../../../public/images/picture-8.jpg");
}
.main-container .travel{
    background-image: url("../../../public/images/picture-1.jpg");
}
.main-container  .ques{
    background-image: url("../../../public/images/picture-8.jpg");
}
@media(min-width: 768px){
    .main-container{
        .main{
            position: fixed;
            width: 70vw;
            z-index: 1;
        }
        .description{
            h1{
             font-size: 3.5rem;
            }
            p{
             font-size: 2rem;
            }
        }
    }
}
@media(max-width: 767px) {
    .main-container .main {
     background-position: center;
    }
}

</style>
