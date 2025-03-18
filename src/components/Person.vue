<template>
    <div class="person">
        <h2>{{ sum }}</h2>
        <button @click="sumAdd">sum+1</button>
    </div>
</template>

<script setup lang="ts" name="Person">
    import {ref, watch} from 'vue'

    let sum = ref(0)
    
    function sumAdd() {
        sum.value += 1
    }

    // watch 
    const stopwatch = watch(sum,(newValue,oldValue)=>{
        console.log('sum has been changed','new ', newValue, 'old ', oldValue)
        if(newValue >= 10) {
            stopwatch() 
        }
    })
</script>

<style scoped>
    .person{
        background-color: rgb(231, 134, 134);
        box-shadow: 0 0 10px;
        padding: 10px;
        border-radius: 10px;
    }
    button {
        margin: 5px;
    }
    li {
        font-size: 20px;
    }
    input {
        margin: 5px;
    }
</style>