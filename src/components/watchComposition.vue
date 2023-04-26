<template>
  <div>
    <h1>This is watch Composition Component</h1>
    <input type="text" placeholder="First Name" v-model="fname" />

    <input type="text" placeholder="First Name" v-model="fname1" />
    <input type="text" placeholder="First Name" v-model="fname2" />
    <input type="text" placeholder="First Name" v-model="options.age" />
    <h1> {{options.age}} </h1>
  </div>
</template>

<script>
import { reactive, ref, toRefs, watch } from "vue";
export default {
  name: "watchComposition",
  setup() {
    const fname1 = ref("");

    const state = reactive({
      fname2: "",
      options:{
        age:null
      }
    });

    watch(
      () => state.options,
      function (nval, oval) {
        console.log(oval);
        console.log(nval);
      },
      { deep: true }
    );
    watch(
      fname1,
      (oval, nval) => {
        console.log(oval, nval);
      },
      { immediate: true }
    );
    return { fname1, ...toRefs(state) };
  },
  data() {
    return {
      fname: "",
      lname: "",
    };
  },
  watch: {
    fname: {
      handler(nval, oval) {
        console.log("Old Value :", oval);
        console.log("new Value :", nval);
      },
      immediate: true,
    },
  },
};
</script>