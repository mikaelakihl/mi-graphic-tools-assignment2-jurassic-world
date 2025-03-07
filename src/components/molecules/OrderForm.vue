<script setup lang="ts">

</script>

<template>
  <section class="order-form">
    <form>
      <div class="form-container">
        <label>
          <span>Full Name</span>
          <input id="nameInput" type="text" name="name" placeholder="Enter your full name" required>
        </label>
      </div>
      <div class="form-container">
        <label class="ticket-amount-container">
          <span>Tickets</span>
          <div>
            <button>-</button>
            <span>0</span>
            <button>+</button>
          </div>
        </label>
      </div>
      <div class="form-container">
        <label>
          <span>Email</span>
          <input id="emailInput" type="email" name="email" placeholder="Enter your email address" required>
        </label>
      </div>
      <div class="form-container">
        <label>
          <span>Phone (Optional)</span>
          <input id="phoneInput" type="tel" name="phone" placeholder="Enter your phone number (optional)">
        </label>
      </div>
      <div class="form-container">
        <label class="terms-container">
          <input id="termsCheckbox" type="checkbox" name="terms" required>
          <span>I agree to the terms and conditions</span>
        </label>
      </div>
      <div class="form-container">
        <button>Proceed</button>
        <button>Cancel</button>
      </div>
    </form>
  </section>
</template>

<style lang="scss" scoped>
  section {
    width: 100vw;
    display: flex;
    form {
      background-color: rgb(219, 131, 131);
      width: 100%;
      height: 100%;
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      .form-container {
        grid-column: span 4; // Most span 4, below are exeptions
        width: 100%;
        padding: 1rem;
        gap: 1rem;
        background-color: rgb(0, 0, 0);
        label {
          width: 100%;
          display: flex;
          flex-direction: column;
          span {
            color: rgb(255, 255, 255);
            // padding-bottom: .3rem;
          }
        }
        .terms-container {
          flex-direction: row;
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
            justify-content: space-between;
            align-items: center;
          }
        }
      }
      .form-container:nth-child(1),
      .form-container:nth-child(2) {
        grid-column: span 2;
      }
      .form-container:nth-child(6) {
        display: flex;
        justify-content: space-between;
      }
    }
  }
</style>