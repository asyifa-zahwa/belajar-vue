<script setup>
import { onWatcherCleanup, reactive } from 'vue';
import { ref } from 'vue';
import { computed } from 'vue';
import { watch } from 'vue';
import { watchEffect } from 'vue';
import productDetail from './ProductDetail.vue';

const product = ref(null);
const productId = ref("product1");
const currency = (value) => {
    return new Intl.NumberFormat('id-ID', {
        style: 'currency',
        currency: 'IDR'
    }).format(value);
};
   
// watch(productId, async (newValue) => {
//     console.log("watch triggered for productId");
//     console.log("Product ID changed to:", newValue);
//     const response = await fetch(`/${newValue}.json`);
//     product.value = await response.json();
// }, {
//      immediate: true, deep: true,
//      //once : true // jika ingin hanya sekali saja
//      once: true // jika ingin hanya sekali perubahan saja

//      //kalau untuk yang tidak ada data awal, bisa gunakan dibawah ini
//     // if (newValue) {
//     //     const response = await fetch(`/${newValue}.json`);
//     //     product.value = await response.json();
//     // } else {
//     //     product.value = null;
        
//     // }
// });    
//untuk watcheffect digunakan seperti watch, tapi tidak perlu menuliskan parameter baruValue dan immediate : true
watchEffect(async () => {
    //onwatcherCleanup digunakan untuk membersihkan efek samping yang dibuat oleh watchEffect
    //seperti misalnya menghapus event listener atau membersihkan interval
    //dipanggil ketika watchEffect selesai dieksekusi
    //atau ketika ada perubahan pada reactive data yang digunakan dalam watchEffect
    onWatcherCleanup(() => {
        console.log("Cleanup function called");
    });
    console.log("watchEffect triggered");
    const response = await fetch(`/${productId.value}.json`);
    product.value = await response.json();
});

   
</script>
<template>
   <label for="product">
    product id :
    <select v-model="productId">
        <!-- <option value="">Select Product</option> -->
        <option value="product1">Laptop ASUS ROG</option>
        <option value="product2">Laptop Lenovo Legion 5</option>
        <option value="product3">Laptop Apple MacBook Pro</option>
    </select>
   </label>
    <div v-if="product">
        
        <productDetail :id="product.id" :name="product.name" :price="product.price"></productDetail>
          <!-- <h1 class="hello">{{ product.name }}</h1>
          <p>Price: {{ product.price | currency }}</p>
          <p>{{ product.description }}</p> -->
     </div>
     <div v-else>
          <p>Please select a product.</p>
     </div>

</template>
<style scoped>
    .hello {
        color:rgb(25, 219, 132);
        font-size: 2em;
        text-align: center;
    }
</style>