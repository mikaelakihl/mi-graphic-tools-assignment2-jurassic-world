<script setup lang="ts">
import { ref, computed, defineProps, defineEmits } from 'vue'
import DecrementButton from '../atoms/DecrementButton.vue'
import IncrementButton from '../atoms/IncrementButton.vue'
import TheButton from '../atoms/TheButton.vue'

const props = defineProps<{
  ticketAmount: number
  formEnabled: boolean
}>()

const emit = defineEmits(['update-ticket-amount'])

// VARIABLES
// const ticketAmount = ref(0)
const nameInput = ref('')
const emailInput = ref('')
const phoneInput = ref('')
const termsChecked = ref(false)

// ADD AND REMOVE TICKETS
// ADD AND REMOVE TICKETS
const decrement = () => {
  if (props.ticketAmount > 0) {
    emit('update-ticket-amount', props.ticketAmount - 1)
  }
}

const increment = () => {
  emit('update-ticket-amount', props.ticketAmount + 1)
}

const isProceedDisabled = computed(() => {
  return (
    nameInput.value.trim() === '' ||
    emailInput.value.trim() === '' ||
    props.ticketAmount < 1 || // Use props.ticketAmount
    !termsChecked.value
  )
})

// SUBMIT EVENT
const submitForm = (event: Event) => {
  event.preventDefault()
  if (!isProceedDisabled.value) {
    console.log('Form Sent', {
      name: nameInput.value,
      email: emailInput.value,
      phone: phoneInput.value,
      tickets: props.ticketAmount, // Use props.ticketAmount
      termsAccepted: termsChecked.value,
    })
    resetForm()
  }
}

// CANCEL EVENT
const resetForm = () => {
  nameInput.value = ''
  emailInput.value = ''
  phoneInput.value = ''
  emit('update-ticket-amount', 0)
  termsChecked.value = false
}
</script>

<template>
  <section class="order-form">
    <form @submit="submitForm" :class="{ disabled: !props.formEnabled }">
      <div class="form-container">
        <label>
          <span>Full Name</span>
          <input
            v-model="nameInput"
            type="text"
            name="name"
            placeholder="Enter your full name"
            required
            :disabled="!props.formEnabled"
          />
        </label>
      </div>
      <div class="form-container">
        <div class="ticket-amount-container">
          <span>Tickets</span>
          <div class="amount-buttons">
            <DecrementButton
              button-text="-"
              @click="decrement"
              type="button"
              :disabled="!props.formEnabled"
            />
            <span id="ticketAmount">{{ ticketAmount }}</span>
            <IncrementButton
              button-text="+"
              @click="increment"
              type="button"
              :disabled="!props.formEnabled"
            />
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
            :disabled="!props.formEnabled"
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
            :disabled="!props.formEnabled"
          />
        </label>
      </div>
      <div class="form-container">
        <label class="terms-container">
          <input
            v-model="termsChecked"
            type="checkbox"
            name="terms"
            required
            :disabled="!props.formEnabled"
          />
          <span>I agree to the terms and conditions</span>
        </label>
      </div>
      <div class="form-container">
        <TheButton
          type="submit"
          class="proceed-btn"
          buttonText="Proceed"
          :disabled="isProceedDisabled"
        />
        <TheButton type="button" class="cancel-btn" buttonText="Cancel" @click="resetForm" />
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
