<template>
    <div class="main-story">
        <h1 class="story">OUR STORY</h1>
        <p><strong>ADE</strong></p>
        <p>It all started in the DM – On the fateful day, I was casually browsing through my feed then I came across this beautiful and interesting looking lady – the picture was for her celebrating the completion of her masters. Naturally, I was intrigued and decided to slide right into the DM to strike up a conversation with the line: “You have such a beautiful smile and brains to match by the looks… how are you doing?”  - cheesy I know haha. She replied to me, and the rest was history.</p>
        <p>During our long conversations which became a constant for us, I found out that I shared a lot of things with this wonderful lady – ‘Ife mi’. She also complemented me on my not so strong areas. Being in a long-distance relationship, it was always challenging wanting to see the love of your life but not being able to as often. We saw each other a couple of times and at some point, I knew that it was only natural to take the next step. </p>
        <p>I proposed to Efe in October 2021 as I couldn’t see myself embarking on this journey of life with anyone else. All the wonderful and challenging times we have had has just further strengthened my resolve that you are the one I want to do all of life with.</p>
        <p>I love to the moon and back Efe.</p>
        <br/>
        <br/>
        <p><strong>EFE</strong></p>
        <p>We found each other online on a social media app – Instagram. We grew a strong liking to each other and found ourselves talking/calling every day, with our interests and views on life being very similar we could talk for hours. I saw Adeyemi as a very pleasant guy who was very easy to talk to and conversations with him was always very interesting and inspiring, this made it so easy and natural to accept when Adeyemi asked me to be his girlfriend in 2019. Even though this was scary to me being that we were in two distant countries, I truly fancied and cared about him. Our relationship blossomed daily, we agreed to send loving text messages to each other every morning, which kept our bond strong despite the distance.</p>
        <p>In October 2021, we decided to take a trip to Ghana for my birthday. This was such an amazing experience for me because I got to spend it with the most amazing man, someone I love with my whole heart. After my birthday, before we got ready to head back, Adeyemi took me to dinner, went on one knee and asked me to be his wife, and of course I said yes. It was a really happy day for us. </p>
        <p>I love you Ade mi, my perfect gentleman and person for life.</p>
    </div>
</template>

<script>
export default {
    name: 'Story',
    mounted() {
        const observer  =  new IntersectionObserver(entries=>{
            entries.forEach(entry=> {
                if(entry.isIntersecting){
                    this.$emit('story')
                }
            })
        });

        setTimeout(()=>{
            let watch = document.getElementsByClassName('story')[0]
            observer.observe(watch);
        },500)
    }

}
</script>
<style lang="scss" scoped>
.main-story{
    font-size: 1.2rem;
    width: 100%;
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    height: auto;
    p{
        text-align: center;
        margin-top: 1rem;
    }
}
</style>
