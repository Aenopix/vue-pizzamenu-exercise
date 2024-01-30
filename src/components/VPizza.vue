<script setup>
import { ref } from 'vue';

const props = defineProps({
  pizza: {
    name: String,
    ingredients: String,
    price: Number,
    photoName: String,
    soldOut: Boolean
  }
})

const _pizza = ref(JSON.parse(JSON.stringify(props.pizza)))
</script>

<template>
  <li class="pizza">
    <img :src="_pizza.photoName" :alt="_pizza.name" />
    <div>
      <h3>{{ _pizza.name }}</h3>
      <p>{{ _pizza.ingredients }}</p>
      <span>{{ _pizza.soldOut ? "SOLD OUT" : `\$${_pizza.price}` }}</span>
    </div>
  </li>
</template>