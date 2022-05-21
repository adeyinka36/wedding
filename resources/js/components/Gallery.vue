<template>
    <div class="main">
        <svg v-if="!showModal" :class="['cancel', showModal ? 'modal-cancel' : '']" @click="$emit('closeGallery')" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512"><!--! Font Awesome Pro 6.1.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2022 Fonticons, Inc. --><path d="M310.6 361.4c12.5 12.5 12.5 32.75 0 45.25C304.4 412.9 296.2 416 288 416s-16.38-3.125-22.62-9.375L160 301.3L54.63 406.6C48.38 412.9 40.19 416 32 416S15.63 412.9 9.375 406.6c-12.5-12.5-12.5-32.75 0-45.25l105.4-105.4L9.375 150.6c-12.5-12.5-12.5-32.75 0-45.25s32.75-12.5 45.25 0L160 210.8l105.4-105.4c12.5-12.5 32.75-12.5 45.25 0s12.5 32.75 0 45.25l-105.4 105.4L310.6 361.4z"/></svg>
        <h1>ENJOY OUR GALLLERY</h1>
        <div class="gallery">
            <img @click="(e)=>triggerModal(index, e)" v-for="(pic,index) in images" :src="pic">
        </div>
        <Transition>
            <div v-if="showModal" class="modal">
                <svg :class="['cancel', showModal ? 'modal-cancel' : '']" @click="showModal=false" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512"><!--! Font Awesome Pro 6.1.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2022 Fonticons, Inc. --><path d="M310.6 361.4c12.5 12.5 12.5 32.75 0 45.25C304.4 412.9 296.2 416 288 416s-16.38-3.125-22.62-9.375L160 301.3L54.63 406.6C48.38 412.9 40.19 416 32 416S15.63 412.9 9.375 406.6c-12.5-12.5-12.5-32.75 0-45.25l105.4-105.4L9.375 150.6c-12.5-12.5-12.5-32.75 0-45.25s32.75-12.5 45.25 0L160 210.8l105.4-105.4c12.5-12.5 32.75-12.5 45.25 0s12.5 32.75 0 45.25l-105.4 105.4L310.6 361.4z"/></svg>
                <div class="inner">
                    <span><svg @click="back" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512"><path d="M224 480c-8.188 0-16.38-3.125-22.62-9.375l-192-192c-12.5-12.5-12.5-32.75 0-45.25l192-192c12.5-12.5 32.75-12.5 45.25 0s12.5 32.75 0 45.25L77.25 256l169.4 169.4c12.5 12.5 12.5 32.75 0 45.25C240.4 476.9 232.2 480 224 480z"/></svg></span>
                    <img :src="images[currentImage]">
                    <span>
                        <svg @click= "forward" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512"><path d="M96 480c-8.188 0-16.38-3.125-22.62-9.375c-12.5-12.5-12.5-32.75 0-45.25L242.8 256L73.38 86.63c-12.5-12.5-12.5-32.75 0-45.25s32.75-12.5 45.25 0l192 192c12.5 12.5 12.5 32.75 0 45.25l-192 192C112.4 476.9 104.2 480 96 480z"/></svg>
                    </span>
                </div>
            </div>
        </Transition>
    </div>
</template>
<script>
export default{
    name: 'Gallery',
    data(){
        return{
            currentImage: null,
            showModal: false,
            images:[
                '../../images/people.jpg',
                '../../images/people.jpg',
                '../../images/people.jpg',
                '../../images/people.jpg',
                '../../images/people.jpg',
                '../../images/people.jpg',
                '../../images/people.jpg',
                '../../images/people.jpg',
                '../../images/people.jpg',
                '../../images/people.jpg',
            ]
        }
    },
    methods:{
        triggerModal(index){
            this.currentImage = index;
            this.showModal = true;
        },
        back(){
            if(this.currentImage-1 >= 0){
                this.currentImage--
            } else {
                this.currentImage = this.images.length-1
            }

        },
        forward(){
            if(this.currentImage <= this.images.length-2){
                this.currentImage++
            } else{
                this.currentImage = 0
            }
        }
    }
}
</script>
<style lang="scss" scoped>
.v-enter-active,
.v-leave-active {
    transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
    opacity: 0;
}
.main{
    min-height: 80vh;
    display: flex;
    justify-content: space-around;
    align-items: center;
    flex-direction: column;
}
.gallery {
    width: 75%;
    min-height: auto;
    justify-content: center;
    align-items: center;
    display: flex;
    flex-wrap: wrap;
        img{
            max-width: 15rem;
            min-width: 11rem;
            transition: transform 250ms ease-out;
            border: 5px solid rgba(255, 165, 0, 0);
            &:hover{
                cursor: pointer;
                border: 5px solid rgba(255, 165, 0, 1);
                transform: scale(1.25);
            }
    }
}

.modal{
    position: fixed;
    top:0;
    height: 100vh;
    width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgba(0,0,0,.7);
    .inner{
        display: flex;
        height: 100%;
        img{
            width:80%;
            object-fit: contain;
        }
        span{
            width: 10%;
            display: flex;
            justify-content: center;
            align-items: center;
            svg{
                color: white;
                height: 1.8rem;
                path{
                    fill: white;
                }
                &:hover{
                    cursor: pointer;
                    color: lightyellow;
                }
            }
        }
    }
}
.cancel{
    z-index: 1000;
    position: fixed;
    right: 1rem;
    top: 2.5rem;
    height: 3rem;
    path{
        fill: black;
        &:hover{
            cursor: pointer;
            fill: red;
        }
    }
}
.modal-cancel{
    path{
        fill: white;
    }
}
.inner{
    svg{
        z-index: 100000;
    }
}

</style>
