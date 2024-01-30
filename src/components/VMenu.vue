<script setup>
import { computed } from 'vue'
import VPizza from '@/components/VPizza.vue'

const props = defineProps({
  pizzas: Array
})

const numPizzas = computed(() => props.pizzas.length)
</script>

<template>
  <main class="menu">
    <h2>Our menu</h2>
    <template v-if="numPizzas > 0">
      <p>
        Authentic Italian cuisine. 6 creative dishes to choose from. All
        from our stone oven, all organic, all delicious.
      </p>
      <ul class="pizzas">
        <VPizza v-for="pizza in pizzas" :key="pizza.name" :pizza="pizza" />
      </ul>
    </template>
    <p v-else>We're still working on our menu. Please come back later :)</p>
  </main>
</template>