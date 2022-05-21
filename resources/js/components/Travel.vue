<template>
    <div class="main-con">
        <h1 class="travel">TRAVEL</h1>
        <p class="note">For all our friends and family who have lots of questions, please check out out Q & A first!</p>
        <div class="questions">
            <div v-for="ques in questions" class="con">
                <h4>
                    <svg class="car" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M39.61 196.8L74.8 96.29C88.27 57.78 124.6 32 165.4 32H346.6C387.4 32 423.7 57.78 437.2 96.29L472.4 196.8C495.6 206.4 512 229.3 512 256V448C512 465.7 497.7 480 480 480H448C430.3 480 416 465.7 416 448V400H96V448C96 465.7 81.67 480 64 480H32C14.33 480 0 465.7 0 448V256C0 229.3 16.36 206.4 39.61 196.8V196.8zM109.1 192H402.9L376.8 117.4C372.3 104.6 360.2 96 346.6 96H165.4C151.8 96 139.7 104.6 135.2 117.4L109.1 192zM96 256C78.33 256 64 270.3 64 288C64 305.7 78.33 320 96 320C113.7 320 128 305.7 128 288C128 270.3 113.7 256 96 256zM416 320C433.7 320 448 305.7 448 288C448 270.3 433.7 256 416 256C398.3 256 384 270.3 384 288C384 305.7 398.3 320 416 320z"/></svg>
                </h4>
                <div>
                    <p class="note">{{ ques[0] }}</p>
                    <p class="orange">{{ ques[1] }}</p>
                    <p>{{ ques[2] }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default{
    name: 'Travel',
    data(){
        return {
            questions:[
                ['Eko Hotel Station', '12 max road, MK4R RFS','This is 4 miles from the location'],
                ['Eko Hotel Station', '12 max road, MK4R RFS','This is 4 miles from the location'],
                ['Eko Hotel Station', '12 max road, MK4R RFS','This is 4 miles from the location'],
                ['Eko Hotel Station', '12 max road, MK4R RFS','This is 4 miles from the location'],
                ['Eko Hotel Station', '12 max road, MK4R RFS','This is 4 miles from the location'],
                ['Eko Hotel Station', '12 max road, MK4R RFS','This is 4 miles from the location'],
            ]
        }
    },
    mounted() {
        const observer  =  new IntersectionObserver(entries=>{
            entries.forEach(entry=> {
                if(entry.isIntersecting){
                    this.$emit('travel')
                }
            })
        });

        setTimeout(()=>{
            let watch = document.getElementsByClassName('travel')[0]
            observer.observe(watch);
        },500)
    }
}
</script>

<style lang="scss" scoped>
.main-con{
    padding: 1.5rem;
    h1{
        margin-top: 2.2rem;
    }
    h1,p{
        margin-bottom: 1rem;
        text-align: center;
    }
    .note{
        font-weight: 600;
        text-align: left;
        margin-bottom: 2rem;
    }
}
.questions{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
    .orange,.car{
        color: orangered !important;
    }
    .car{
        height: 2rem;
    }
    .con{
        margin-bottom: 1.25rem;
        display: flex;
        h4{
            margin-right: .5rem;
        }
        div{
            p{
                margin-bottom: 1rem;
                text-align: left;
            }
        }
        span{
            display: flex;
            height: 100%;
            margin-bottom: auto;
            div{
                display: flex;
                flex-direction: column;
                justify-content: space-between;
            }
        };
    }
}
</style>
