<script setup>
import { ref, useSlots } from 'vue';
import About from './About.vue';
import Blog from './Blog.vue';
import Contact from './Contact.vue';

const currentPage = ref('About');
const pages = {
    About,
    Blog,
    Contact
}
</script>
<template>
    <div>
        <h1>Welcome to My Vue App</h1>
        <nav>
            <button @click="currentPage = 'About'">About</button>
            <button @click="currentPage = 'Blog'">Blog</button>
            <button @click="currentPage = 'Contact'">Contact</button>
        </nav>
        <component :is="pages[currentPage]"></component>
    </div>

</template>
<style scoped>
    
</style>