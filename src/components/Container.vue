<script setup>
import { ref, useSlots } from 'vue';

const slot = useSlots();

const counter = ref(0);

</script>
<template>
    <h1>{{ title }}</h1>
    <div v-if="slot.header">
        <h2>Container Component</h2>
        <p>This is a container component that can hold other components or content.</p>
        <slot name="header"  :counter="counter">
            <!-- This is where the content of the slot will be rendered -->
            <p>Default content if no slot is provided.</p>
        </slot>
    </div>
    <div v-if="slot.default">
        <!-- <slot /> 
         This is where the content of the slot will be rendered -->
         <slot name="default" :counter="counter">
            <!-- This is where the content of the slot will be rendered -->
            <p>Default content if no slot is provided.</p>
         </slot>

    </div>
    <div v-if="slot.footer">
        <slot name="footer" :counter="counter">
            <!-- This is where the content of the footer slot will be rendered -->
            <p>Default footer content if no footer slot is provided.</p>
        </slot>
    </div>
    <div>
        <h2>Counter: {{ counter }}</h2>
        <button @click="counter++">Increment Counter</button>
        <button @click="counter--">Decrement Counter</button>
    </div>


</template>
<style scoped>
</style>