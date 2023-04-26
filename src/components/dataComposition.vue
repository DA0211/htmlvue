<template>
    <div>
        <h1>This is Composition API</h1>
        <h1> {{name}} </h1>
        <h1>{{fullName.fname}} {{fullName.lname}} </h1>
    </div>
</template>

<script>
import {reactive} from "vue";
export default {
    name:"dataComposition",
    // setup(){
    //     let fullName = ref("JohnDoe")
    //     console.log(fullName)
    //     setTimeout(() => {
    //         fullName.value = "Abc"
    //         console.log(fullName)
    //     }, 2000);
    //     return{
    //         fullName
    //     }
    // },
    setup(){
        const fullName = reactive({
            fname :"John",
            lname :"Doe"
        })
        return{
            fullName
        }
    },
    data(){
        return{
            name:"Dhruv Agarwal"
        }
    },
}
</script>