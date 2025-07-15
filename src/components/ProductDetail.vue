<script setup>
import { ref, computed } from 'vue';

const props = defineProps({
    id: {
        type: String,
        required: true
    },
    name: {
        type: String,
        required: true,
        validator: (value, props) => {
            return value.trim().length > 0;
        }
    },
    price: {
        type: Number,
        required: true,
        validator: (value, props) => {
            return value >= 0;
        }
    },
});
   
</script>
<template>
    <div>
        <h1 id="title">Product</h1>
        <p>Id: {{ props.id }}</p>
        <p>Name: {{ props.name }}</p>
        <p>Price: {{ props.price | currency }}</p>
    </div>
  
</template>
<style scoped>
    
</style>