<script setup lang="ts">
import BookingCard from '@/components/molecules/BookingCard.vue';
import IncrementBtn from '@/components/atoms/IncrementButton.vue';
import DecrementButton from '@/components/atoms/DecrementButton.vue';
</script>

<template>
  <div class="ticket">
    <BookingCard />
    <h1>This is the Tickets page</h1>
    <IncrementBtn button-text="+"/>
    <DecrementButton button-text="-" />
  </div>
</template>

<style lang="scss" scoped>
  h1 {
    color:$red;
  }
  .ticket {
  background-color: black;
  height: 98vh;
}
</style>
