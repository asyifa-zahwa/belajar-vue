<script setup>
import Counter from './Counter.vue';
import CounterStateless from './CounterStateless.vue';
import { ref } from 'vue';

const counter = ref(0);

const title1 = 'asyifa';
const title2 = 'zahwa';

const increment = (value) => {
    counter.value+= value;
};

</script>
<template>
    <h1 id="count">Counter baru</h1>

    <Counter title="asyifa" initial-count="10" />
    <Counter title="zahwa" initial-count="20" />
    <!-- <Counter :title="title1" />
    <Counter v-bind:title="title2" /> -->
    <CounterStateless :counter="counter" name="Stateless Counter" :increment="2" @click="increment" />
    <!-- <button @click="counter++">Add Counter</button> -->
</template>
<style scoped>
</style>