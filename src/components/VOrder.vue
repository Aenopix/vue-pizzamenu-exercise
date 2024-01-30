<script setup>
defineProps({
  openHour: Number,
  closeHour: Number
})
</script>

<template>
  <div class="order">
    <p>We're open from {{ openHour }}:00 to {{ closeHour }}:00. Come visit us or order online.</p>
    <button class="btn">Order</button>
  </div>
</template>