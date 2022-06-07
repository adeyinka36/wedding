<template>
    <div class="main-side">
        <div class="flowers f1"></div>
        <div class="event">
            <p>Saturday, June 11th 2022</p>
            <h2>Delta, Nigeria</h2>
            <p v-if="this.future">In {{ days }}Days and {{hours}}Hrs.</p>
            <p v-else>{{ days }}Days  and {{hours}}Hrs Ago.</p>
        </div>
        <div class="flowers f2"></div>
    </div>
</template>
<script>
export default{
    data (){
        return{
            future: new Date() < new Date('06-11-2022'),
            days: 20,
            hours: 20
        }
    },
    created() {
        let remainder = 0;
        let today = new Date()
        let wedding =  new Date('06-11-2022');
        if(today < wedding){
           this.days = Math.floor(( wedding.getTime() - today.getTime() )/(1000*60*60*24))
            remainder = ( wedding.getTime() - today.getTime() )%(1000*60*60*24)
            this.hours = Math.floor(remainder/ (1000*60*60))
        } else {
            this.days = Math.floor(( today.getTime() -  wedding.getTime() )/(1000*60*60*24))
            remainder = ( today.getTime() -  wedding.getTime() )%(1000*60*60*24)
            this.hours = Math.floor(remainder/ (1000*60*60))
        }
    }
}

</script>
<style lang="scss" scoped>
    .main-side{
        width: 100%;
        height: 100vh;
        background-color: #fffff8;
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        .event{
            font-size: 1.5rem;
            padding: .75rem;
           h2{
               margin-top: .75rem;
               margin-bottom: .75rem;
           }
           *{
               text-align: center;
           }
        }
        .flowers{
            width: 50vw;
            height: 50vw;
            max-width: 500px;
            max-height: 500px;
            position: absolute;
            background-position: center;
            background-size: contain;
            background-repeat: no-repeat;
        }
        .f1{
            top: 0;
            left: 0;
            margin-left: -.6rem;
            background-image: url('https://withjoy.dexecure.net/assets/public/styles/prod/fionas_flowers/8bfe1ae2be6878d41b7a542012db292c25b59d496ee74083e0b58604ea6742c1@1x');
        }
        .f2{
            background-image: url('https://withjoy.dexecure.net/assets/public/styles/prod/fionas_flowers/c7802621bdb574c650445e0d71dc4d8e747a682c68dc5b9549c1df2a99ba6fa8@1x');
            bottom: 0;
            right: 0;
        }
    }
    @media(min-width: 768px){
        .main-side{
            .flowers{
                max-width: 250px;
                max-height: 250px;
            }
        }
    }
</style>
