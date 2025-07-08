<script setup>
import { reactive } from 'vue';
   
    const person = reactive({
        name: '',
        email: '',
        message: '',
        age: 0,
        type: 'regular',
        complain: false,

    });
   
</script>
<template>
    <div>
        <h1 class="hello">Contact Us</h1>
        <form action="">
            <input type="text" v-model="person.name" placeholder="Name">
            <input type="email" v-model="person.email" placeholder="Email">
            <textarea v-model="person.message" placeholder="Message"></textarea>
            <input type="number" v-model.number="person.age" placeholder="Age"> 
            <!-- dikasih number agar bisa dioperasikan -->
            <select v-model="person.type">
                <option value="regular">Regular</option>
                <option value="vip">VIP</option>
            </select>
            <label>
                <input type="checkbox" v-model="person.complain"> Complain
            </label>
            <button @click.prevent>Submit</button>
        </form>
        <pre>{{ person }}</pre>
        <p>{{ typeof(person.age) }}</p>
        <p>{{ person.age > 17 ? 'You are an adult' : 'You are a minor' }}</p>
    </div>
</template>
<style scoped>
    .hello {
        color:rgb(25, 219, 132);
        font-size: 2em;
        text-align: center;
    }
</style>