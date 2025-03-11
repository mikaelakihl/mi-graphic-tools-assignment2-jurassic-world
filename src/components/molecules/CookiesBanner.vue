<script setup lang="ts">
import { ref } from 'vue'

// Prototype functionality for hiiding the cookies banner
const showCookies = ref(true)
const hideCookies = () => {
  showCookies.value = false
}
</script>

<template>
  <div class="cookies" :class="{ hidden: !showCookies }">
    <span>Want cookies? We'we got 'em!</span>
    <div class="button-wrapper">
      <button @click="hideCookies">Accept</button>
      <button @click="hideCookies">Decline</button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.cookies {
  background-color: $black;
  color: $lightgrey;
  position: fixed;
  width: 100%;
  height: 100px;
  bottom: 0;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
  gap: 0.5rem;
  font-size: rem(20);
  transition:
    transform 0.5s ease,
    visibility 0.5s ease;
  span {
    padding: 0.5rem;
    width: 100%;
    text-align: center;
  }
  .button-wrapper {
    display: flex;
    height: 100%;
    width: clamp(200px, 60%, 400px);
    gap: 1rem;
    justify-content: space-between;
    button {
      background-color: $lightgreen;
      color: $white;
      border: none;
      height: 44px;
      width: 100%;
      cursor: pointer;
      border-radius: 8px;
      &:hover {
        background-color: $grey;
      }
      &:active {
        background-color: $green;
      }
    }
  }
}

@media (min-width: 1440px) {
  .cookies {
    height: 120px;
    flex-direction: row;
    .button-wrapper {
      width: 388px;
      flex-direction: column;
      padding: 8px;
      justify-content: space-evenly;
      gap: 8px;
    }
  }
}

.hidden {
  visibility: hidden;
  transform: translateY(100%); //Moves Banner off screen
}
</style>
