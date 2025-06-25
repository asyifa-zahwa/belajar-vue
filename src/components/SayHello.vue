<script setup>
import { reactive } from 'vue';
import { ref } from 'vue';
import { computed } from 'vue';
   
    const person = reactive({
        firstName: '',
        lastName: '',
    });
    const fullName = computed((oldValue) => {
        //bisa dikasih oldValue
        console.info('Old Value:', oldValue);
        console.info('Manggil fungsi fullName');
        return `${person.firstName} ${person.lastName}`;
    })
    function sayHello() {
        
        person.firstName = document.getElementById('firstName').value;
        person.lastName = document.getElementById('lastName').value;
    }
    const counter = ref(0);
    function increment() {
        counter.value++;
        console.info('Counter:', counter.value);
    }
</script>
<template>
    <div>
        <button @click="increment">Increment Counter</button>
        <p>Counter: {{ counter }}</p>
        <h1 class="hello">Hello {{ fullName }}</h1>
        <input type="text" id="firstName" placeholder="First Name" >
        <input type="text" id="lastName" placeholder="Last Name">
        <button @click="sayHello">Say Hello</button>

    </div>
</template>
<style scoped>
    .hello {
        color:rgb(25, 219, 132);
        font-size: 2em;
        text-align: center;
    }
</style>