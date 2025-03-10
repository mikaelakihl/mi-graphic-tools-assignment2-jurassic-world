<script setup lang="ts">
import BookBtn from '../atoms/BookBtn.vue'
import { ref } from 'vue'

interface Day {
  date: string
  display: string
}

const days = ref<Day[]>([])

const generateDates = (): void => {
  const today = new Date()
  for (let i = 1; i < 6; i++) {
    // Everytime i is less than 5, we generate a new bookingCard, IE we generate 5 days worth of bookings.
    const date = new Date()
    date.setDate(today.getDate() + i)

    days.value.push({
      date: date.toISOString().split('T')[0], // This separates the date from time, so the variable date is only date.
      display: date.toLocaleDateString('en-GB', {
        weekday: 'short',
        day: 'numeric',
        month: 'short',
      }),
      // This formats the date according to region (in this case EN-GB) for display.
    })
  }
}

generateDates()
</script>

<template>
  <div class="bookingCard-wrapper">
    <div v-for="day in days" :key="day.date" class="bookingCard">
      <h2 class="bookingDate">{{ day.display }}</h2>
      <p class="bookingTime">6:00 PM</p>
      <p class="bookingLocation">Salon 8, Dolby Theatre</p>
      <BookBtn />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.bookingCard-wrapper {
  display: flex;
  max-width: 100vw;
  overflow-x: auto;
  white-space: nowrap;
  .bookingCard {
    font-family: $primary-font;
    display: flex;
    flex-direction: column;
    margin: 1rem;
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

  .bookingDate{
    @include h2;
  }

  .bookingTime{
    @include quote;
  }

  .bookingLocation{
    @include h3;
  }
}

@media (min-width: 1440px) {
  .bookingCard-wrapper {
    flex-direction: column;
    overflow-y: auto;
    max-height: 40vh;

    .bookingCard {
      width: 86.25rem;
      height: 7.5rem;
      justify-content: space-around;
      flex-direction: row;
      margin: 0.5625rem auto;

      button {
        margin-top: 0;
      }
    }
  }
}
</style>
