<script setup>
import {ref} from 'vue'
import {computed} from 'vue'

const product = ref('Socks')
const count = ref(0)
const description = ref('Product description')
const stock = ref(10)

const remainingStock = computed(() => stock.value - count.value)

</script>

<template>
  <div class="product-display">
    <div class="product-container">
      <div class="product-info">
        <h1>{{count}} {{product}}</h1>
        <button @click="count++" :disabled="remainingStock === 0">Increase</button>
        <button @click="count--" :disabled="count === 0">Decrease</button>
      
        <p>Stock: {{ remainingStock }}</p>
      </div>
    </div>
  </div>
</template>