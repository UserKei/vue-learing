<template>
    <div class="person">
        <h2>name: {{ name }}</h2>
        <h2>age: {{ age }}</h2>
        <button @click="showTel">check the phone number</button>
        <button @click="modifyName">modifyName</button>
        <button @click="modifyAge">modifyAge</button>
        
    </div>
</template>

<script lang="ts">
    export default {
        name:'Person',
        data() {
            return {
                name:'Kei',
                age:20,
                tel:1111111111
            }
        },
        methods: {
            showTel() {
                alert(this.tel)
            },
            modifyName() {
                this.name = "Yuki"
            },
            modifyAge() {
                this.age += 1
            }
        }
    }
</script>

<style scoped>
    .person{
        background-color: darkgray;
        box-shadow: 0 0 10px;
    }
    button {
        margin: 5px;
    }
</style>