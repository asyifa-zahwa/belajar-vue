<script setup>
import { reactive } from 'vue';
import { ref } from 'vue';
import { computed } from 'vue';

const score = ref(100);

   
</script>
<template>
     <!-- contoh v-if (menghapus elemen dari DOM) -->
    <div v-if="score > 90">
        <h1>Yey Cool Socer</h1>
        <h1 class="red">Score: {{ score }}</h1>
    </div>
    <div v-else-if="score > 80">
        <h1>Yey Good Score</h1>
        <h1 class="bold">Score: {{ score }}</h1>
    </div>
    <div v-else>
        <h1>You have to learn more</h1>
        <h1>Score: {{ score }}</h1> 
    </div>
    <!-- //contoh v-show (tidak menghapus elemen dari DOM) -->
    <div v-show="score > 90">
        <h1>Yey Cool Socer</h1>
        <h1 class="red">Score: {{ score }}</h1>
    </div>
</template>
<style scoped>
    .red {
        color: red;
    }
    .bold {
        text-transform: uppercase;
        font-weight: bold;
    }
</style>