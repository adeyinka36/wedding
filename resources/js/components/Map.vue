<template>
    <div class="map-con">
        <h1 class="watch">Location</h1>
        <div class="desc">
            <p>The Palm Centre.</p>
            <p>No. 7 Ogala Street, off Owo-Eke Road</p>
            <p>Boji Boji Owa-Agbor</p>
            <p>SATURDAY, JUNE 11TH 2022</p>
            <p>Time: 12noon.</p>
        </div>
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d31728.935579149846!2d6.164735448961567!3d6.248316921289028!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x10414e56ba75d509%3A0xfb109346984ce351!2sAgbor%2C%20Nigeria!5e0!3m2!1sen!2suk!4v1654616591162!5m2!1sen!2suk" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
    </div>
</template>

<script>
  export default{
      name: 'Map',
      mounted() {
          const observer  =  new IntersectionObserver(entries=>{
              entries.forEach(entry=> {
                if(entry.isIntersecting){
                    this.$emit('map')
                }
              })
          });

          setTimeout(()=>{
              let watch = document.getElementsByClassName('watch')[0]
              observer.observe(watch);
          },500)
      }
  }
</script>

<style lang="scss" scoped>
 h1{
     margin-top:2.2rem;
 }
 p{
     font-weight: 600;
 }
 h1,p{
     text-align: center;
     margin-bottom: 1rem;
 }
 .map-con{
     padding: 1rem;
 }
</style>
