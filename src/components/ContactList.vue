<script setup>
import { reactive } from 'vue';

const [name, nameModifier] = defineModel('name', {
    type: String,
    default: '',
    get: (value) => {
        if (nameModifier.uppercase) {
            // If a modifier is provided, apply it
            console.log('nameModifier', nameModifier);
            return value.trim().toUpperCase();
            
        }else {
            //console.log('nameModifier', nameModifier);
            return value.trim();
        }
        // Custom getter to modify the value before returning
        
    },
});
const email = defineModel('email', {
    type: String,
    default: ''
});
const message = defineModel('message', {
    type: String,
    default: ''
});
const age = defineModel('age', {
    type: Number,
    default: 0
});
const type = defineModel('type', {
    type: String,
    default: 'regular'
});
const complain = defineModel('complain', {
    type: Boolean,
    default: false
});

   

   
</script>
<template>
    <h1>Preview</h1>
    <div>
        <p>Name : {{ name }}</p>
        <p>Email : {{ email }}</p>
        <p>Message : {{ message }}</p>
        <p>Age : {{ age }}</p>
        <p>Type : {{ type }}</p>
        <p>Complain : {{ complain }}</p>
       
    </div>
</template>
<style scoped>
    .hello {
        color:rgb(25, 219, 132);
        font-size: 2em;
        text-align: center;
    }
</style>