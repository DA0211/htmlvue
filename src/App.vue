<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <!-- <getposts /> -->
  <!-- <dataComposition /> -->
  <!-- <methodComposition /> -->
  <!-- <vmodelComposition /> -->
  <!-- <computedComposition /> -->
  <!-- <watchComposition /> -->
  <provideInjectComposition />
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import getposts from "./components/getPosts.vue"
// import dataComposition from "./components/dataComposition.vue"
// import methodComposition from "./components/methodComposition.vue"
// import vmodelComposition from "./components/vmodelComposition.vue"
// import computedComposition from "./components/computedComposition.vue";
// import watchComposition from "./components/watchComposition.vue";
import provideInjectComposition from "./components/provideInjectComposition.vue"
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
    provideInjectComposition,
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
