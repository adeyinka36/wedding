<template>
    <div class="main-con">
    <h1>Q & A</h1>
    <p class="note">For all our friends and family who have lots of questions, please check out out Q & A first!</p>
    <div class="questions">
        <div v-for="ques in questions" class="con">
            <h4>Q</h4>
            <div>
                <p class="note">{{ ques[0] }}</p>
                <p>{{ ques[1] }}</p>
            </div>
        </div>
    </div>
    </div>
</template>

<script>
export default{
    name: 'Questions',
    data(){
     return {
         questions:[
             ['Can I bring a date?', 'We have a reserved a seat for you due to limited capacity, the wedding is  strictly by invitation'],
             ['Can I bring a date?', 'We have a reserved a seat for you due to limited capacity, the wedding is  strictly by invitation'],
             ['Can I bring a date?', 'We have a reserved a seat for you due to limited capacity, the wedding is  strictly by invitation'],
             ['Can I bring a date?', 'We have a reserved a seat for you due to limited capacity, the wedding is  strictly by invitation'],
             ['Can I bring a date?', 'We have a reserved a seat for you due to limited capacity, the wedding is  strictly by invitation'],
             ['Can I bring a date?', 'We have a reserved a seat for you due to limited capacity, the wedding is  strictly by invitation'],
             ['Can I bring a date?', 'We have a reserved a seat for you due to limited capacity, the wedding is  strictly by invitation'],
         ]
     }
    },
}
</script>

<style lang="scss" scoped>
   .main-con{
       padding: 1rem;
       h1{
           margin-top: 2.2rem;
       }
       h1,p{
           margin-bottom: 1rem;
           text-align: center;
       }
       .note{
           font-weight: 600;
       }
   }
    .questions{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        .con{
            margin-bottom: 1.25rem;
            display: flex;
            h4{
                margin-right: .5rem;
            }
            div{
                p{
                    margin-bottom: .5rem;
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
