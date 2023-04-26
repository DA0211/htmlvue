<template>
  <div>
    <h1>This is V-Model Composition Component.</h1>
    <input type="text" placeholder="First Name" v-model.trim="fname" />
    <input type="text" placeholder="Last Name" v-model.trim="lname" />
    <h1>{{ `First name : ${fname} Last name : ${lname}` }}</h1>

    <input type="text" placeholder="First Name" v-model.trim="fname1" />
    <input type="text" placeholder="Last Name" v-model.trim="lname1" />
    <h1>{{ `First name : ${fname1} Last name : ${lname1}` }}</h1>

    <input type="text" placeholder="First Name" v-model.trim="name" />
    <h1>{{ `Name : ${name}` }}</h1>
  </div>
</template>

<script>
import { ref, reactive, toRefs } from "vue";
export default {
  name: "vmodelComposition",
  setup() {
    const name = ref("");
    const state = reactive({
      fname1: "",
      lname1: "",
    });
    return {
      name,
      ...toRefs(state),
    };
  },
  data() {
    return {
      fname: "",
      lname: "",
    };
  },
};
</script>