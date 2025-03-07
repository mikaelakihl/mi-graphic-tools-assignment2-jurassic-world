<script lang="ts" setup>
import { ref } from 'vue';
import { RouterLink, RouterView } from 'vue-router'

const isActive = ref(false);

function toggleHamburgerMenu(){


 isActive.value = !isActive.value;
}


</script>

<template>
<div class="menu-container">
<div class="hamburger-container">
  <button :class="['hamburger', { 'active': isActive}]" @click="toggleHamburgerMenu">
    <span class="hamburger-line"></span>
    <span class="hamburger-line"></span>
    <span class="hamburger-line"></span>
  </button>
</div>

<div :class="['menu-open-wrapper', { 'active': isActive}]">

<h2 class="menu-open-heading">Menu</h2>

<nav class="nav-links">
  <RouterLink class="router-link" to="/">Home</RouterLink>
  <RouterLink class="router-link" to="/about">About</RouterLink>
  <RouterLink class="router-link" to="/tickets">Tickets</RouterLink>
  <RouterLink class="router-link" to="/cast">Cast</RouterLink>
</nav>
</div>
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
  position: fixed;
  margin-top: 0;
}

.menu-open-wrapper.active{
  display: block;
  z-index: 1;
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

.menu-container{
  position: relative;
  width: 80%;
}

.hamburger-container{
  position: relative;

}

.hamburger{
  width: 50px;
    height: 50px;
    background: transparent;
    border: 0;
    left: 20px;
    top: 20px;
    z-index: 2;
    position: absolute;

}

.hamburger-line{
  display: block;
    width: 37px;
    height: 2px;
    background-color: $white;
    border-radius: 6px;
    margin-bottom: 10px;
    transition: all 0.3s ease-in-out

}

.hamburger.active{
  right:20px;
  left:unset;


}


.hamburger.active .hamburger-line:nth-child(1) {
  transform: rotate(45deg);
  position: absolute;

}

.hamburger.active .hamburger-line:nth-child(2) {
  opacity: 0; /* Den mellersta linjen försvinner */
}

.hamburger.active .hamburger-line:nth-child(3) {
  transform: rotate(-45deg);
  position: absolute;
  top: 20px;

}


</style>

