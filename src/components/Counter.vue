<script setup>
import { ref } from 'vue';
import { nextTick } from 'vue';
let count = 0;
function increment() {
    count++;
    document.getElementById('count').innerText = `Counter :   ${count}`;
    //harus pake document.getElementById karena tidak bisa pakai v-model
}
let count2 = ref(0);
let count3 = ref({
    no: 0,
    name: 'Counter 3',
})
function increment2() {
    count2.value++;
    //harus pake .value karena count2 adalah reactive variable
}   
function increment3() {
    count3.value.no++;
    console.log(count3.value);
    //harus pake .value karena count3 adalah reactive variable
}
//coba next tick
async function incrementNextTick() {
    count2.value++;
    await nextTick();
    console.log('Counter 2 updated:', count2.value);
}

</script>
<template>
    <h1 id="count">Counter : {{ count }}</h1>
    <button @click="increment">Increment</button>
    <button @click="decrement">Decrement</button>
    <h1>Counter 2 : {{ count2 }}</h1>
    <h1>Counter 3 : {{ count3.no }} </h1>
    <button @click="increment3">Increment 3</button>
    <button @click="increment2">Increment 2</button>
    <button @click="incrementNextTick">Increment 2 with nextTick</button>
    <p>Counter 2 with ref: {{ count2 }}</p>
</template>
<style scoped>
</style>