<template class="app-con">
    <Home :picture="picture" class="home"/>
    <div class="side">
        <MainSide />
        <Story @story="story"/>
        <Map @map="map"/>
        <Questions @ques="ques"/>
        <Travel @travel="travel"/>
        <Pictures :current="current" @selected="selected" class="watch"/>
        <Transition>
         <Modal @minimize="open=false" v-if="open" />
        </Transition>
    </div>
</template>
<script>

const default_layout = "default";
import Home from '../components/Home';
import Story from '../components/Story';
import MainSide from '../components/MainSide';
import Questions from "../components/Questions";
import Map from "../components/Map";
import Travel from "../components/Travel";
import Pictures from "../components/Pictures";
import Modal from "../components/Modal";



export default {
    name: 'App',
    components: {MainSide, Home, Story, Questions, Map, Travel, Pictures, Modal},
  computed: {},
  data() {
      return {
          message:'Welcome to our wedding',
          open: false,
          picture:'',
          people: [],
          current:[]
      }
  },
  methods: {
        selected(data) {
            this.open = true;
            // this.current = ""
            console.log(data)
        },
        story(){
            this.picture = 'story'
        },
        map(){
            this.picture = 'map'
        },
        ques(){
            this.picture = 'ques'
        },
        travel(){
            this.picture = 'travel'
        }
  },
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
  .v-enter-active,
  .v-leave-active {
      transition: opacity 0.5s ease;
  }

  .v-enter-from,
  .v-leave-to {
      opacity: 0;
  }
</style>
