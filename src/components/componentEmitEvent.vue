<template>
    <div>
        <h1>This is Component Emit Event Compoonent</h1>
        <button @click="$emit('close','Dhruv',20)">Close ME</button>
        <h1>Component : {{name}}</h1>
    </div>
</template>

<script>
export default {
    name:"componentEmitEvent",
    emit:['close'],
    props:['name']
}
</script>