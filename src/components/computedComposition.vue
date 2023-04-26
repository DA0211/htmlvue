<template>
  <div>
    <h1>This is Computed Composition Component.</h1>
    <input type="text" placeholder="Enter First Name" v-model="fname" />
    <input type="text" placeholder="Enter First Name" v-model="lname" />
    <h1>{{ fullname }}</h1>

    <input type="text" placeholder="Enter First Name" v-model="fname1" />
    <input type="text" placeholder="Enter First Name" v-model="lname1" />
    <h1>{{ fullName1 }}</h1>

    <input type="text" placeholder="Enter First Name" v-model="fname2" />
    <input type="text" placeholder="Enter First Name" v-model="lname2" />
    <h1>{{ fullName2 }}</h1>
  </div>
</template>

<script>
import { ref, computed, reactive, toRefs } from "vue";
export default {
  name: "computedComposition",
  setup() {
    const fname1 = ref("");
    const lname1 = ref("");

    const state = reactive({
      fname2: "",
      lname2: "",
    });

    const fullName1 = computed(function () {
      return `Name is : ${fname1.value + lname1.value}`;
    });

    const fullName2 = computed(function () {
      return `name is : ${state.fname2 + state.lname2}`;
    });
    return {
      fname1,
      lname1,
      fullName1,
      ...toRefs(state),
      fullName2
    };
  },
  data() {
    return {
      fname: "",
      lname: "",
    };
  },
  computed: {
    fullname() {
      return `Name is : ${this.fname + " " + this.lname}`;
    },
  },
};
</script>