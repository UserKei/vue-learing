<template>
    <div class="person">
        <h2>name: {{ name }}</h2>
        <h2>age: {{ age }}</h2>
        <button @click="showTel">check the phone number</button>
        <button @click="modifyName">modifyName</button>
        <button @click="modifyAge">modifyAge</button>
    </div>
</template>

<script setup lang="ts" name="Person">
    import {ref} from 'vue'

    let name = ref("Kei")
    let age = ref(20)
    let tel = "11212123"
    
    function modifyName() {
        name.value = "Yuki"
    }
    
    function modifyAge() {
        age.value += 1
    }
    
    function showTel() {
        alert(tel)
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
</style>