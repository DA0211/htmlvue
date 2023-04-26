<template>
  <div>
    <h1>This is Method Composition</h1>
    <h1>{{ count }}</h1>
    <button @click="addCount">Increment Count</button>

    <h1>{{ count1 }}</h1>
    <h1>{{ fname + " " + lname }}</h1>
    <button @click="addCountReactive">Increment Count</button>
  </div>
</template>

<script>
import { ref, reactive, toRefs } from "vue";
export default {
  name: "methodComposition",
  setup() {
    const count = ref(0);
    const state = reactive({
      count1: 0,
      fname :"Dhruv",
      lname:"Agarwal"
    });

    function addCount() {
      count.value++;
    }
    function addCountReactive(){
        state.count1++
        state.fname= "John"
        state.lname = "Doe"
    }
    return {
      count,
      addCount,
      addCountReactive,
      ...toRefs(state)
    };
  },
};
</script>