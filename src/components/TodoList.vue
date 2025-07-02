<script setup>
import { reactive } from 'vue';
import { ref } from 'vue';
import { computed } from 'vue';
   
    const title = [
        {
            id: 1,
            name: 'Belajar Vue.js Dasar',
            done: true,
        },
        {
            id: 2,
            name: 'Belajar Vue.js Lanjutan',
            done: false,
        },
        {
            id: 3,
            name: 'Belajar Vue.js untuk Pemula',
            done: false,
        },
    ]
</script>
<template>
    <!-- v-for dan v if bisa digunakan dalam satu element tapi v-if akan diprioritaskan karena itu menjadi tidak efisien, jadi tetap gunakan beda element-->
    <div>
        <h1 class="hello">Todo List</h1>
        <ul>
            <template v-for="item in title" :key="item.id">
                <!-- perulangan peritem pakai arraynya-->
                <li  v-if="item.done === true">
                    {{ item.name }}
                </li>

            </template>
        </ul>
        <!-- perulangan peritem pakai objectnya -->
         <ul v-for="item in title" :key="item.id">
            <li v-for="(id, name) in item">
                {{id}} : {{name}}
            </li>

         </ul>
        <p>Belajar Vue.js Dasar</p>

    </div>
    <div v-for="n in 10" :key="n">
        <h1>
            hello {{ n }}
        </h1>
    </div>
</template>
<style scoped>
    .hello {
        color:rgb(25, 219, 132);
        font-size: 2em;
        text-align: center;
    }
</style>