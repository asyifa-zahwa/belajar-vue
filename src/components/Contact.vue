<script setup>
import { reactive } from 'vue';
import ContactForm from './ContactForm.vue';
import ContactList from './ContactList.vue';
   
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

        <ContactForm v-model="person" />
        <ContactList v-model:name.uppercase="person.name" :email="person.email" :message="person.message" :age="person.age" :type="person.type" :complain="person.complain" />
    </div>
</template>
<style scoped>
    .hello {
        color:rgb(25, 219, 132);
        font-size: 2em;
        text-align: center;
    }
</style>