<template>
    <div class="person">
        <h2>A {{ car.brand }} car, price {{ car.price }}</h2>
        <button @click="modifyPrice">modifyPrice</button>
        <button @click="changeCar">changeCar</button>
    </div>
</template>

<script setup lang="ts" name="Person">
    import {reactive, ref} from 'vue'
    let car = ref({brand: 'Benz', price: 10000})

    let games = ref([
        {id:'1213112',name:'MHWI'},
        {id:'12141325',name:'MHWs'},
        {id:'141341515',name:'MHRS'}
    ])

    // reactive 深层次修改
    // ref 处理对象的响应式数据,底层是用的reactive封装 

    function modifyPrice() {
        car.value.price += 10
    }

    function changeCar() {
        // Object.assign(car.value,{brand:'BMW',price:10041})
        car.value = {brand: 'BMW', price: 12431}
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