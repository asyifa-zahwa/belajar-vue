<script setup>
import { reactive } from 'vue';
import { ref } from 'vue';
import { computed } from 'vue';

const className = [ 'red', 'bold' ];
   const red = ref(false);
   const bold = ref(false);
function toggleRed() {
    red.value = !red.value;
}
function toggleBold() {
    bold.value = !bold.value;
}
//inline style
const inlineStyle = computed(() => {
    return {
        color: red.value ? 'red' : 'black',
        fontWeight: bold.value ? 'bold' : 'normal',
    };
});

   
</script>
<template>
    <h1 :class="{red:red, bold:bold}">Style</h1>
    <h1 :class="[className]">Style</h1>
    <h1 :style="inlineStyle">Inline Style</h1>
    <button @click="toggleRed">RedButton</button>
    <button @click="toggleBold">Bold</button>
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