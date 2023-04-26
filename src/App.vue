<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <!-- <getposts /> -->
  <!-- <dataComposition /> -->
  <!-- <methodComposition /> -->
  <!-- <vmodelComposition /> -->
  <!-- <computedComposition /> -->
  <!-- <watchComposition /> -->
  <!-- <provideInjectComposition /> -->
  <div>
    <button @click="show = true">Show ME</button>
    <componentEmitEvent v-show="show" @close="closeEvent" :name='name' />
    <h1>App : {{name}}, Age : {{age}}</h1>
    <h1> {{count}} </h1>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import getposts from "./components/getPosts.vue"
// import dataComposition from "./components/dataComposition.vue"
// import methodComposition from "./components/methodComposition.vue"
// import vmodelComposition from "./components/vmodelComposition.vue"
// import computedComposition from "./components/computedComposition.vue";
// import watchComposition from "./components/watchComposition.vue";
// import provideInjectComposition from "./components/provideInjectComposition.vue"
import componentEmitEvent from "./components/componentEmitEvent.vue";
export default {
  name: "App",
  components: {
    // HelloWorld,
    // getposts,
    // dataComposition,
    // methodComposition,
    // vmodelComposition,
    // computedComposition,
    // watchComposition,
    // provideInjectComposition,
    componentEmitEvent,
  },
  data() {
    return {
      show: false,
      name: "",
      age:null,
      count :0
    };
  },
  methods: {
    closeEvent(name,age) {
      this.show = false;
      this.name = name;
      this.age = age;
    },
    mouse(event){
      console.log(event)
      this.count = this.count + 1
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
