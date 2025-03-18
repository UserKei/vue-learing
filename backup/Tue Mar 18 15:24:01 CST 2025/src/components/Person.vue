<template>
    <div class="person">
        firstName <input type="text" v-model="firstName"> <br>
        lastName <input type="text" v-model="lastName"> <br>
        fullName <span>{{ fullName }}</span> <br>
        <button @click="changeFullName">changeFullName</button>
    </div>
</template>

<script setup lang="ts" name="Person">
    import {ref, computed} from 'vue'

    let firstName = ref('Yuki')
    let lastName = ref('Noa')

    // 只读写法
    // let fullName = computed(()=> {
    //     return firstName.value.slice(0,1).toUpperCase() 
    //     + firstName.value.slice(1) 
    //     + lastName.value;
    // })

    let fullName = computed({
        get() {
            return firstName.value.slice(0,1).toUpperCase() 
            + firstName.value.slice(1) 
            + '-' + lastName.value;
        },
        set(val) {
            const [s1, s2] = val.split('-')
            firstName.value = s1
            lastName.value = s2 
        }
    })

    function changeFullName() {
        fullName.value = "User-Kei"
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
    input {
        margin: 5px;
    }
</style>