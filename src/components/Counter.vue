<script setup>
import { ref } from 'vue';
let count = 0;
function increment() {
    count++;
    document.getElementById('count').innerText = `Counter :   ${count}`;
    //harus pake document.getElementById karena tidak bisa pakai v-model
}
let count2 = ref(0);
function increment2() {
    count2.value++;
    //harus pake .value karena count2 adalah reactive variable
}   
</script>
<template>
    <h1 id="count">Counter : {{ count }}</h1>
    <button @click="increment">Increment</button>
    <button @click="decrement">Decrement</button>
    <h1>Counter 2 : {{ count2 }}</h1>
    <button @click="increment2">Increment 2</button>
</template>
<style scoped>
</style>