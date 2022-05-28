<template>
    <div class="main-con">
        <div class="close">
            <p  @click="$emit('minimize')" class="minimize">CLOSE</p>
            <svg @click="$emit('minimize')" class="arrow minimize" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M502.6 278.6l-128 128c-12.51 12.51-32.76 12.49-45.25 0c-12.5-12.5-12.5-32.75 0-45.25L402.8 288H32C14.31 288 0 273.7 0 255.1S14.31 224 32 224h370.8l-73.38-73.38c-12.5-12.5-12.5-32.75 0-45.25s32.75-12.5 45.25 0l128 128C515.1 245.9 515.1 266.1 502.6 278.6z"/></svg>
        </div>
        <div class="pics">
              <img class="pic" v-for="(pic, index ) in images" @mouseover="(e)=>changeData(index, e)" @click="(e)=>changeData(index, e)" :src="pic[0]">
        </div>
        <div class="desc">
            <img :src="currentImage">
            <p class="main">{{currentName }}</p>
            <p>{{ currentDescription }}</p>
        </div>

    </div>
</template>
<script>
export default{
    name: 'Modal',
    props:{
        current:{
            type: Number,
            required: false,
            default: 0
        },
    },
    data(){
        return{
            currentName: null,
            currentDescription: null,
            currentImage: null,
            images:[
                ['../../images/people.jpg', 'Person1', 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit'],
                ['../../images/people2.jpg', 'Person2', 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit'],
                ['../../images/people.jpg', 'Person1', 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit'],
                ['../../images/people2.jpg', 'Person2', 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit'],
                ['../../images/people.jpg', 'Person1', 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit'],
                ['../../images/people2.jpg', 'Person2', 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit'],
                ['../../images/people.jpg', 'Person1', 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit'],
                ['../../images/people2.jpg', 'Person2', 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit'],
                ['../../images/people.jpg', 'Person1', 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit'],
                ['../../images/people2.jpg', 'Person2', 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit'],
            ]
        }
    },
    mounted(){
        this.currentImage = (this.images[this.current])[0]
        this.currentName = (this.images[this.current])[1]
        this.currentDescription = (this.images[this.current])[2]
    },
    methods: {
        changeData(index){
            console.log('changing')
            this.currentImage = this.images[index][0]
            this.currentName = this.images[index][1]
            this.currentDescription = this.images[index][2]
        }
    }
}
</script>


<style lang="scss" scoped>
.main-con {
    .minimize{
        cursor: pointer;
    }
    .close{
        display: flex;
        justify-content: center;
        align-items: center;
        position: fixed;
        right: 0;
        top: 0;
        padding: 1rem;
        p{
            font-weight: bold;
            font-size: 1.5rem;
            margin-right: .5rem;
        }
        svg{
            height: 2.3rem
        }
    }
    background-color: white;
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    display: flex;
    .pics {
        width: 65%;
        justify-content: center;
        align-items: center;
        display: flex;
        flex-wrap: wrap;
        overflow-y: auto;
            img {
                max-width: 100%;
                min-width: 15rem;
                width: 25%;
                margin: 0 .5rem 1.25rem;
                transition: transform 500ms ease-out;
                &:hover{
                    transform: scale(1.5);
                }
            }
    }
    .desc{
        width: 35%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
        background-color: #fffff8;
        padding: 1rem;
        img{
            display: none;
        }
        p{
            font-size: 1.2rem;
            font-weight: 350;
            width: 100%;
            text-align: center;
        }
        .main{
            margin-bottom: 1rem;
            font-weight: 600;
            font-size: 1.5rem;
        }
    }
    @media (min-width: 401px) {
        .pics{
            padding: 5rem;
        }
    }
    @media (max-width: 400px) {
        .pics{
            display: none;
        }
        .desc{
            width: 100%;
            img{
                display: inline-flex;
                width: 90%;
                margin-bottom: 9rem;
                margin-left: 1rem;
            }

        }
    }
}
</style>
