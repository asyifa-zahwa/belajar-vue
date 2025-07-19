<script setup>
import { ref } from 'vue';
import { nextTick } from 'vue';

const {counter, name} = defineProps(
    {
        counter: {
            type: Number,
            default: 0
        },
        name: {
            type: String,
            default: 'Stateless Counter'
        },
        increment:{
            type: Number,
            default: 1
        }
    }
);
const emit = defineEmits(['click']);


</script>
<template>
    <div>

        <h1 >Counter {{ name }} : {{ counter }}</h1>
        <button @click="emit('click', increment)">Increment</button>
    </div>
   
   
</template>
<style scoped>
</style>