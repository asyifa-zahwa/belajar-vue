<script setup>
    console.info('Hello Vue!');
    const message = '<b> Hello Vue! </b>';
    const className = 'hello';
    const id = 'hello';
    const data = {
        class: 'hello',
        id: 'hello',
    };
    const isDisabled = false;
    function showMessage() {
        console.info('showMessage');
    }
    //kalau nama variable dan nama property sama, bisa ditulis seperti ini => :id="id"=> :id
</script>
<template>
    <h1 class="hello">hello vue {{ message.toUpperCase() }}</h1>
    <h2>{{ 100 * 20 }}</h2>
    <h2>{{ showMessage() }}</h2>
    <p v-bind:class="className"  v-html="message"></p>
    <p :class="className" :id v-text="message"></p>
    <button :disabled="isDisabled">iya</button>
    <p v-bind="data">coba objek</p>
    <p :class="data.class" :id="data.id">coba objek pisah</p>
</template>
<style scoped>
    .hello {
        color:rgb(25, 219, 132);
        font-size: 2em;
        text-align: center;
    }
</style>