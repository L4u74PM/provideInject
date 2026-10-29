
<template>
    <div class="category-list">
        <h2>
            Productes
        </h2>
        <div class="products">
            <Productitem v-for="p in products":key="p.name" :product="p"></Productitem>
        </div>
    </div>
</template>
<script setup>
import Productitem from './Productitem.vue';
import { inject } from 'vue';
const products = inject('products')
</script>