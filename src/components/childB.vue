<template>
    <div>
        <h1>This is Child B Component</h1>
        <childC />
    </div>
</template>

<script>
import childC from "./childC.vue"
export default {
    name:"childB",
    components :{
        childC,
    }
}
</script>