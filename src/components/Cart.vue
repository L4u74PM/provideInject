<template>
    <div class="cart">
        <h2>Carret</h2>
        <p>{{ cart.length }} articles</p>
        <ul>
            <CartItem
                v-for="(item, index) in cart"
                :key="index"
                :item="item"
            />
        </ul>
        <p class="total">{{ total }}</p>
        <button @click="clearCart" :disabled="cart.length === 0">🗑️ Buida carret</button>
    </div>
</template>

<script setup>
import { inject, computed } from 'vue'
import CartItem from './CartItem.vue'

const cart = inject('cart')
const total = computed(() => cart.reduce((sum, product) => sum + product.price, 0))
const clearCart = () => cart.splice(0)
</script>