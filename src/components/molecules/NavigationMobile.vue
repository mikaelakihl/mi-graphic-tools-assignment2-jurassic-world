<script lang="ts" setup>
import { ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router'

const isActive = ref(false)

function toggleHamburgerMenu() {
  isActive.value = !isActive.value
}
</script>

<template>
  <div class="menu-container">
    <div class="hamburger-container">
      <button :class="['hamburger', { active: isActive }]" @click="toggleHamburgerMenu">
        <span class="hamburger-line"></span>
        <span class="hamburger-line"></span>
        <span class="hamburger-line"></span>
      </button>
    </div>

    <div :class="['menu-open-wrapper', { active: isActive }]">
      <h2 class="menu-open-heading">Menu</h2>

      <nav class="nav-links">
        <div class="router-link-wrapper">
          <RouterLink class="router-link" to="/">Home</RouterLink>
        </div>
        <div class="router-link-wrapper">
          <RouterLink class="router-link" to="/about">About</RouterLink>
        </div>
        <div class="router-link-wrapper">
          <RouterLink class="router-link" to="/tickets">Tickets</RouterLink>
        </div>
        <div class="router-link-wrapper">
          <RouterLink class="router-link" to="/cast">Cast</RouterLink>
        </div>
      </nav>
    </div>
  </div>
  <RouterView />
</template>

<style lang="scss" scoped>
.menu-open-wrapper {
  background-color: $black;
  width: 80%;
  height: 100vh;
  color: $white;
  display: none;
  position: fixed;
  top: 0;
  border-right: solid 0.0625rem $white;
}

.menu-open-wrapper.active {
  display: block;
  z-index: 1;
}

.menu-open-heading {
  margin-top: 7rem;
  text-align: center;
}

.nav-links {
  display: flex;
  flex-direction: column;
  padding-bottom: 0.625rem;
}

.router-link-wrapper {
  border-bottom: solid $white 1px;
  height: 3.75rem;
  display: flex;
  align-items: center;
}

.router-link {
  color: $white;
  text-decoration: none;
  padding-left: 1rem;
}

.menu-container {
  position: relative;
  width: 80%;
}

.hamburger-container {
  position: relative;
}

.hamburger {
  width: 3.125rem;
  height: 3.125rem;
  background: transparent;
  border: 0;
  left: 2.25rem;
  top: 1.125rem;
  z-index: 2;
  position: absolute;
}

.hamburger-line {
  display: block;
  width: 2.3125rem;
  height: 0.125rem;
  background-color: $white;
  border-radius: 0.375rem;
  margin-bottom: 0.625rem;
  transition: all 0.3s ease-in-out;
}

.hamburger.active {
  right: 1.25rem;
  left: unset;
}

.hamburger.active .hamburger-line:nth-child(1) {
  transform: rotate(45deg);
  position: absolute;
  height: 0.25rem;
}

.hamburger.active .hamburger-line:nth-child(2) {
  opacity: 0;
}

.hamburger.active .hamburger-line:nth-child(3) {
  transform: rotate(-45deg);
  position: absolute;
  top: 1.25rem;
  height: 0.25rem;
}
</style>
