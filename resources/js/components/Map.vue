<template>
    <div class="map-con">
        <h1 class="watch">Location</h1>
        <div class="desc">
            <p>EKO HOTEL, LAGOS.</p>
            <p>SATURDAY, JUNE 11TH 2022</p>
        </div>
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d179373.19670210892!2d3.1205295379310227!3d6.568909183523651!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x103bf53aec4dd92d%3A0x5e34fe6a84cddd53!2sEko%20Hotels%20%26%20Suites!5e0!3m2!1sen!2suk!4v1652534711929!5m2!1sen!2suk" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
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
