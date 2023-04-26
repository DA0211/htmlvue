<template>
  <div>
    <h1>This is Child C Component</h1>
    <h1>{{ name }}</h1>
    <h1>{{ fname1 }}</h1>
    <h1>{{firstName}} {{lastName}}</h1>
    <h1>{{count}}</h1>
    <button @click="incrementCount(true)">Increment Count in Child</button>
    <button @click="incrementCount(false)">Decrement Count in Child</button>
  </div>
</template>

<script>
import { inject, toRefs } from "vue";
export default {
  name: "childC",
  setup() {
    const fname1 = inject('fname', "Default name");
    const state = inject('state', {});
    const count = inject("count")
    const incrementCount = inject("incrementCount")
    return {
      fname1,
      ...toRefs(state),
      count,
      incrementCount
    };
  },
  inject: ["name"],
};
</script>