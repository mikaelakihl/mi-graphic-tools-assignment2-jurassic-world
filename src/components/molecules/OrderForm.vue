<script setup lang="ts">
import { ref, computed } from 'vue'
import DecrementButton from '../atoms/DecrementButton.vue'
import IncrementButton from '../atoms/IncrementButton.vue'
import TheButton from '../atoms/TheButton.vue'

// VARIABLES
const ticketAmount = ref(0)

const nameInput = ref('')
const emailInput = ref('')
const phoneInput = ref('')
const termsChecked = ref(false)

// ADD AND REMOVE TICKETS
const decrement = () => {
  if (ticketAmount.value > 0) {
    ticketAmount.value--
  }
}

const increment = () => {
  ticketAmount.value++
}

const isProceedDisabled = computed(() => {
  return (
    nameInput.value.trim() === '' ||
    emailInput.value.trim() === '' ||
    ticketAmount.value < 1 ||
    !termsChecked.value
  )
})

// SUBMIT EVENT
const submitForm = (event: Event) => {
  event.preventDefault(); // Förhindra sidladdning
  if (!isProceedDisabled.value) {
    console.log('Form Sent', {
      name: nameInput.value,
      email: emailInput.value,
      phone: phoneInput.value,
      tickets: ticketAmount.value,
      termsAccepted: termsChecked.value
    });
    resetForm()
  }
};

// CANCEL EVENT
const resetForm = () => {
  nameInput.value = ''
  emailInput.value = ''
  phoneInput.value = ''
  ticketAmount.value = 0
  termsChecked.value = false
}

</script>

<template>
  <section class="order-form">
    <form @submit="submitForm">
      <div class="form-container">
        <label>
          <span>Full Name</span>
          <input
            v-model="nameInput"
            type="text"
            name="name"
            placeholder="Enter your full name"
            required
          />
        </label>
      </div>
      <div class="form-container">
        <div class="ticket-amount-container">
          <span>Tickets</span>
          <div class="amount-buttons">
            <DecrementButton button-text="-" @click="decrement" type="button" />
            <span id="ticketAmount">{{ ticketAmount }}</span>
            <IncrementButton button-text="+" @click="increment" type="button" />
          </div>
        </div>
      </div>
      <div class="form-container">
        <label>
          <span>Email</span>
          <input
            v-model="emailInput"
            type="email"
            name="email"
            placeholder="Enter your email address"
            required
          />
        </label>
      </div>
      <div class="form-container">
        <label>
          <span>Phone (Optional)</span>
          <input
            v-model="phoneInput"
            type="tel"
            name="phone"
            placeholder="Enter your phone number (optional)"
          />
        </label>
      </div>
      <div class="form-container">
        <label class="terms-container">
          <input v-model="termsChecked" type="checkbox" name="terms" required />
          <span>I agree to the terms and conditions</span>
        </label>
      </div>
      <div class="form-container">
        <TheButton type="submit" class="proceed-btn" buttonText="Proceed" :disabled="isProceedDisabled" />
        <TheButton type="button" class="cancel-btn" buttonText="Cancel" @click="resetForm"/>
      </div>
    </form>
  </section>
</template>

<style lang="scss" scoped>
section {
  width: 100vw;
  display: flex;
  background-color: $black;
  justify-content: center;
  form {
    width: clamp(300px, 95vw, 1100px);
    height: 100%;
    display: grid;
    gap: 1.5rem;
    margin: 1rem;
    grid-template-columns: repeat(4, 1fr);
    .form-container {
      grid-column: span 4; // Most span 4, below are exeptions
      width: 100%;
      gap: 1rem;
      background-color: rgb(0, 0, 0);
      label {
        width: 100%;
        display: flex;
        flex-direction: column;
        span {
          color: rgb(255, 255, 255);
        }
      }
      div {
        width: 100%;
        display: flex;
        flex-direction: column;
        span {
          color: rgb(255, 255, 255);
        }
      }
      .terms-container {
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: 1rem;
        font-size: 1.2rem;
      }
      .ticket-amount-container {
        align-items: center;
        height: 100%;
        div {
          display: flex;
          width: 100%;
          height: 100%;
          flex-direction: row;
          justify-content: space-between;
          align-items: center;
          margin-top: 0.5rem;
        }
      }
    }
    .form-container:nth-child(1),
    .form-container:nth-child(2) {
      grid-column: span 2;
      button {
        margin: 0;
        width: clamp(45px, 10vw, 80px);
      }
    }
    .form-container:nth-child(6) {
      display: flex;
      justify-content: space-between;
      button {
        margin: 0;
        width: clamp(140px, 30vw, 326px);
      }
    }
  }
}

.proceed-btn {
  background-color: $lightyellow;
  color: $black;
  transition: background-color 0.3s ease;

  &:hover {
    background-color: $yellow;
  }

  &:active {
    background-color: $lightyellow;
    transition: background-color 0s;
  }

  &:disabled {
    background-color: $grey;
    color: $black;
  }
}

.cancel-btn {
  background-color: $lightred;
  color: $black;
  transition: background-color 0.3s ease;

  &:hover {
    background-color: $red;
  }

  &:active {
    background-color: $lightred;
    transition: background-color 0s;
  }
}
</style>
