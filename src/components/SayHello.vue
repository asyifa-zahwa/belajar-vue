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
    function changeFirstName() {
        person.firstName = document.getElementById('firstName2').value;
    }
    function changeLastName(event) {
        person.lastName = event.target.value;
    }
</script>
<template>
    <div>
        <form action="">

            <button @click="increment">Increment Counter</button>
            <button v-on:click="counter++">increment inline</button>
            <p>Counter: {{ counter }}</p>
            <h1 class="hello">Hello {{ fullName }}</h1>
            <input type="text" id="firstName" placeholder="First Name" >
            <input type="text" id="lastName" placeholder="Last Name">
            <input type="text" placeholder="First Name" @input="changeFirstName" id="firstName2">
            <input type="text" placeholder="Last Name" @input="changeLastName">
            <input type="text" v-model="person.firstName" placeholder="First Name">
            <input type="text" v-model="person.lastName" placeholder="Last Name">
            <button @click.prevent="sayHello">Say Hello</button>
        </form>

    </div>
</template>
<style scoped>
    .hello {
        color:rgb(25, 219, 132);
        font-size: 2em;
        text-align: center;
    }
</style>