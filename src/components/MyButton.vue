<script setup>
import { reactive, useAttrs } from 'vue';
const props = defineProps(["umur"]);
console.info(props);

defineOptions({
    name: 'MyButton',
    inheritAttrs: true // jika tidak ditambahkan maka atribut yang ada di template tidak akan diturunkan ke element yang ada di template
});
const attribut = useAttrs();
console.info(attribut)
</script>
<template>
   <button> tombol : {{ attribut.name }}</button>
   <!-- <button> dua</button> -->
   <!-- kalau dua element inheriAttrs otmatis tidak diturunkan -->
</template>
<style scoped>
   
</style>