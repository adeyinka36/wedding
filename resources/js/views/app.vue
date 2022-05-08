<template class="app-con">
    <Home class="home"/>
    <div class="side">
        <MainSide/>
        <Story/>
    </div>
</template>
<script>

const default_layout = "default";
import Home from '../components/Home';
import Story from '../components/Story';
import MainSide from '../components/MainSide';



export default {
    name: 'App',
    components: {MainSide, Home,Story},
  computed: {},
  data() {
      return {
          message:'Welcome to our wedding'
      }
  }
};
</script>
<style lang="scss" scoped>
  .app-con{
      background-color: lightyellow;
      min-width: 100vw;
      display: flex;
      .side {
          width: 100vw;
          display: flex;
          flex-direction: column;
      }
  }
  @media(min-width: 768px) {
      .home{
          /*position: fixed;*/
          width: 70%;
          top: 0;
          left: 0;
      }
      .side{
          overflow: auto;
          float: right;
          width: 28.8vw;
          right: 0;
      }
  }
</style>
