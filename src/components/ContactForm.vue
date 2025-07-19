<script setup>
import { reactive } from 'vue';

const model = defineModel({
    required: true,
    type: Object,
    default: () => ({
        name: '',
        email: '',
        age: 0,
        type: 'regular',
        complain: false,
        message: ''
    }),
    get: (value) => {
        value.email = value.email.toUpperCase();
        return value;
    },
    
});

   
</script>
<template>
    <div>
        <h1 >Contact Us</h1>
        <form action="">
            <div>
                <label for="name">Name :
                    <input type="text" v-model="model.name" placeholder="Name">
                </label>
            </div>
            <div>
                <label for="email">Email :
                    <input type="email" v-model="model.email" placeholder="Email">
                </label>
            </div>
            <div>
                <label for="age">Age :
                    <input type="number" v-model.number="model.age" placeholder="Age">
                </label>
            </div>
            <div>
                <label for="type">Type :
                    <select v-model="model.type">
                        <option value="regular">Regular</option>
                        <option value="vip">VIP</option>
                    </select>
                </label>
            </div>
            <div>
                <label for="complain">
                    <input type="checkbox" v-model="model.complain"> Complain
                </label>
            </div>
            <div>
                <label for="message">Message :
                    <textarea v-model="model.message" placeholder="Message"></textarea>
                </label>
            </div>
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