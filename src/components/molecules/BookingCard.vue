<script setup lang="ts">
import BookBtn from '../atoms/BookBtn.vue';
</script>

<template>
  <div class="bookingCard">
    <h2>Thursday, March 6</h2>
    <p>6:00 PM</p>
    <p>Salon 8, Dolby Theatre</p>
    <BookBtn />
  </div>
</template>

<style lang="scss" scoped>
  .bookingCard {
    font-family: $primary-font;
    display: flex;
    flex-direction: column;
    margin: 1.5625rem;
    padding: 1.5625rem;
    background-color: $lightgreen;
    align-items: center;
    justify-content: center;
    text-align: center;
    position: relative;
    width: 180px;
    height: 300px;
    border-radius: 8px;
    color: $white;

    button {
      margin-top: 2rem;
    }
  }

</style>
