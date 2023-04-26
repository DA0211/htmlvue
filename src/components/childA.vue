<template>
    <div>
        <h1 :="$attrs">This is Child A Component</h1>
        <childB />
    </div>
</template>

<script>
import childB from "./childB.vue"
export default {
    name:"childA",
    components :{
        childB
    },
    inheritAttrs :false
}
</script>