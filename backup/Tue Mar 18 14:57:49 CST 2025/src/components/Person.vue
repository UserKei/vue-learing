<template>
    <div class="person">
       <h2>name: {{ name }}</h2>
       <h2>age: {{ age }}</h2>
       <button @click="changeAge">change age</button>
       <button @click="changeName">change name</button>
    </div>
</template>

<script setup lang="ts" name="Person">
    import {reactive, toRefs} from 'vue'
    let person = reactive({
        name: 'Kei',
        age: 20
    })
    let {name, age} = toRefs(person)

    function changeName() {
        name.value += '_'
    }

    function changeAge() {
        age.value += 1
    }

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
</style>