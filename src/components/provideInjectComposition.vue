<template>
  <div>
    <h1>This is Provide-Inject Composition Component</h1>
    <h1>{{ name }}</h1>
    <h1>{{ fname }}</h1>
    <h1>{{ firstName }} {{ lastName }}</h1>
    <h1>{{ count }}</h1>
    <button @click="incrementCount(true)">Increment Count</button>
    <button @click="incrementCount(false)">Decrement Count</button>
    <childA class="ABC" />
  </div>
</template>

<script>
// import {provide} from "vue"
import childA from "./childA.vue";
import { provide, reactive, ref, toRefs } from "vue";
export default {
  name: "provideInjectComposition",
  components: {
    childA,
  },
  setup() {
    const fname = ref("Dhruv");
    const count = ref(0);
    const state = reactive({
      firstName: "John",
      lastName: "Doe",
    });
    function incrementCount(val) {
        if(val){
            count.value++;
        }
        else{
            count.value--
        }
    }
    provide("fname", fname);
    provide("state", state);
    provide("count", count);
    provide("incrementCount", incrementCount);
    return {
      fname,
      ...toRefs(state),
      incrementCount,
      count
    };
  },
  data() {
    return {
      name: "Dhruv Agarwal",
    };
  },
  provide() {
    return { name: this.name };
  },
};
</script>