<template>
    <div class="main-con">
        <h1>RECEPTION</h1>
        <div class="gallery">
            <span class="pic" v-for="(pic, index) in images">
              <img @click="$emit('selected', index)" :src="pic[0]">
              <p>{{pic[1]}}</p>
            </span>
        </div>
    </div>
</template>
<script>

export default {
    name: 'Picture',
    data(){
        return{
            images:[
                ['../../images/people.jpg', 'Person1'],
                ['../../images/people2.jpg', 'Person2'],
                ['../../images/people.jpg', 'Person1'],
                ['../../images/people2.jpg', 'Person2'],
                ['../../images/people.jpg', 'Person1'],
                ['../../images/people2.jpg', 'Person2'],
                ['../../images/people.jpg', 'Person2'],
                ['../../images/people2.jpg', 'Person1'],
                ['../../images/people.jpg', 'Person2'],
                ['../../images/people2.jpg', 'Person1'],
            ]
        }
    },
}
</script>
<style lang="scss" scoped>
    .main-con {
        display: none;
        padding: 1.5rem;
        h1{
            text-align: center;
            margin-bottom: 1rem;
        }
        .gallery {
            justify-content: center;
            align-items: center;
            display: flex;
            flex-wrap: wrap;
            p{
                font-weight: 600;
            }

            .pic {
                max-width: 40%;
                min-width: 11rem;
                margin: 0 .5rem 1.25rem;

                img{
                    max-width: 100%;
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
        }
    }

</style>
