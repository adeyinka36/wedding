<template>
    <div class="main-container">
        <div class="main">
            <div class="nav">
                <svg v-if="!showDrop" @click="toggleDrop" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" class="bars"><path d="M0 96C0 78.33 14.33 64 32 64H416C433.7 64 448 78.33 448 96C448 113.7 433.7 128 416 128H32C14.33 128 0 113.7 0 96zM0 256C0 238.3 14.33 224 32 224H416C433.7 224 448 238.3 448 256C448 273.7 433.7 288 416 288H32C14.33 288 0 273.7 0 256zM416 448H32C14.33 448 0 433.7 0 416C0 398.3 14.33 384 32 384H416C433.7 384 448 398.3 448 416C448 433.7 433.7 448 416 448z"/></svg>
                <svg v-else @click="toggleDrop" class="bars" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512"><path d="M310.6 361.4c12.5 12.5 12.5 32.75 0 45.25C304.4 412.9 296.2 416 288 416s-16.38-3.125-22.62-9.375L160 301.3L54.63 406.6C48.38 412.9 40.19 416 32 416S15.63 412.9 9.375 406.6c-12.5-12.5-12.5-32.75 0-45.25l105.4-105.4L9.375 150.6c-12.5-12.5-12.5-32.75 0-45.25s32.75-12.5 45.25 0L160 210.8l105.4-105.4c12.5-12.5 32.75-12.5 45.25 0s12.5 32.75 0 45.25l-105.4 105.4L310.6 361.4z"/></svg>
                <p @click="toggleDrop" >MENU</p>
                <ul :class="['drop-down', showDrop && 'activate-drop']">
                    <li class="couple"><h2>ADEYEMI & EFE</h2></li>
                    <li>Home</li>
                    <li>Story</li>
                    <li>Schedule</li>
                    <li>Q & A</li>
                    <li>Travel</li>
                    <li>Wedding Party</li>
                    <li>Registry</li>
                    <li>Moments</li>
                </ul>
            </div>
            <div class="description">
                <h1>ADEYEMI</h1>
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
    methods: {
        toggleDrop(){
            this.showDrop = !this.showDrop;
        }
    }
}
</script>

<style lang="scss" scoped>
.main-container .main {
    width: 100%;
    height: 100vh;
    max-width: 100%;
    position: relative;
    background-image: url("../../../public/images/wedding-placeholder.jpg");
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    .description {
        padding: 2rem 5rem 2rem 2rem;
    }
    .nav {
        ul.drop-down{
            position: absolute;
            transition: height ease-out 1s, opacity linear;
            height: 0;
            visibility: hidden;
            top: 2rem;
            left: 1rem;
            background-color: pink;
            width: 70vw;
            max-width: 500px;
            padding: 1rem;
            border-radius: 8px;
            li{
                font-size: 1.2rem;
                margin-top: 1rem;
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
@media(min-width: 768px){
    .main-container{
        .main{
            position: fixed;
            width: 70vw;
        }
    }
}
</style>
