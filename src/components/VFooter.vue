<script setup>
import { computed } from 'vue'
import VOrder from '@/components/VOrder.vue'

const hour = new Date().getHours();
const openHour = 12
const closeHour = 22
const isOpen = computed(() => {
  return hour >= openHour && hour <= closeHour
})
</script>

<template>
  <footer class="footer">
    <VOrder v-if="isOpen" :open-hour="openHour" :close-hour="closeHour" />
    <p v-else>We're happy to welcome you between {{ openHour }}:00 and {{ closeHour }}:00.</p>
  </footer>
</template>
