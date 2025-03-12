<script setup lang="ts">
import { ref } from 'vue'
import BookingCard from '@/components/molecules/BookingCard.vue'
import OrderForm from '@/components/molecules/OrderForm.vue'

const ticketAmount = ref(0)
const formEnabled = ref(false)

const enableForm = () => {
  ticketAmount.value++ // Add 1 ticket when enabling
  formEnabled.value = true
}

const updateTicketAmount = (amount: number) => {
  ticketAmount.value = amount
}
</script>

<template>
  <div class="ticket">
    <BookingCard @enable-form="enableForm" class="ticket-card" />
    <OrderForm
      :ticketAmount="ticketAmount"
      :formEnabled="formEnabled"
      @update-ticket-amount="updateTicketAmount"
    />
  </div>
</template>

<style lang="scss" scoped>
h1 {
  color: $red;
}
.ticket {
  background-color: black;
  min-height: 85vh;
}

.ticket-card {
  margin-top: 1rem;
}
</style>
