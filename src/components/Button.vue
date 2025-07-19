<script setup>
import { reactive, useSlots } from 'vue';
import MyButton from './MyButton.vue';
import Container from './Container.vue';



const functionAllert = () => {
    alert('Hello Vue');
};


   
</script>
<template>
    Container
    <Container title="Belajar Vue.js Dasar">
        <template #header="attribut">
            <h1>Header Slot {{ attribut.counter }}</h1>
        </template>
        <template #default="attribut">
           
            <p>Ini adalah contoh penggunaan slot di Vue.js</p>
            <p>Slot memungkinkan kita untuk menyisipkan konten ke dalam komponen</p>
            <MyButton class="button" @click="functionAllert" :name="attribut.counter" umur="80" />
        </template>
        <!-- <template #footer>
            <h1>Footer Slot</h1>
        </template> -->
    </Container>

</template>
<style scoped>
    .button {
        background-color: #4CAF50; /* Green */
        border: none;
        color: white;
        padding: 15px 32px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 16px;
        margin: 4px 2px;
        cursor: pointer;
    }
   
</style>