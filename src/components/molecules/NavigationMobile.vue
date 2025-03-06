<script lang="ts" setup>
import { ref } from 'vue';
import { RouterLink, RouterView } from 'vue-router'

const hamburgerBtn = ref (document.querySelector('hamburgerBtn'));
const isActive = ref(false);

function toggleHamburgerMenu(){


 isActive.value = !isActive.value;
}


</script>

<template>

<div class="hamburger-container">
  <button id="hamburgerbBtn" class="hamburger" @click="toggleHamburgerMenu">
    <span class="hamburger-line"></span>
    <span class="hamburger-line"></span>
    <span class="hamburger-line"></span>
  </button>
</div>

<div :class="['menu-open-wrapper', { 'active': isActive }]">

<h2 class="menu-open-heading">Menu</h2>

<nav class="nav-links">
  <RouterLink class="router-link" to="/">Home</RouterLink>
  <RouterLink class="router-link" to="/about">About</RouterLink>
  <RouterLink class="router-link" to="/tickets">Tickets</RouterLink>
  <RouterLink class="router-link" to="/cast">Cast</RouterLink>
</nav>
</div>
<RouterView />
</template>

<style lang="scss" scoped>

.menu-open-wrapper{
  background-color: $black;
  width: 80%;
  height: 100vh;
  color: $white;
  display: none;
}

.menu-open-heading{
  text-align: center;
}

.nav-links{
  display: flex;
  flex-direction: column;
  padding-bottom: 10px;

}

.router-link{
  color: $white;
  text-decoration: none;
  border-bottom: solid $white 1px;
  margin-bottom: 50px;
  padding-bottom: 10px;
  padding-left: 1rem;
}

.hamburger{
  width: 50px;
    height: 50px;
    background: transparent;
    border: 0;
    position: fixed;
    left: 20px;
    top: 20px;
    z-index: 3;
}

.hamburger-line{
  display: block;
    width: 37px;
    height: 2px;
    background-color: $white;
    border-radius: 6px;
    margin-bottom: 10px;
    transition: all 0.3s ease-in-out;
}

.active{
  display: block;
  position: fixed;

}


</style>

