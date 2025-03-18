<template>
    <div class="app">
        <h1>Fuck You</h1>
        <Person/>
    </div>
</template>

<script lang="ts">
    import Person from './components/Person.vue';
    export default {
        name:'App',
        components:{Person}
    }
</script>
    
<style>
    .app {
        background-color: aquamarine;
    }
</style> 