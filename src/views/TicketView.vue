<script setup lang="ts">
import BookingCard from '@/components/molecules/BookingCard.vue'
</script>

<template>
  <div class="ticket">
    <BookingCard />
    <h1>This is the Tickets page</h1>
  </div>
</template>

<style lang="scss" scoped>
h1 {
  color: $red;
}
.ticket {
  background-color: black;
  height: 98vh;
}
</style>
