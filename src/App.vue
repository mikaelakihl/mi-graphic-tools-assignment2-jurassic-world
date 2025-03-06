<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import AppFooter from './components/molecules/AppFooter.vue'
</script>

<template>
  <header>
    <div class="header-wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/tickets">Tickets</RouterLink>
        <RouterLink to="/cast">Cast</RouterLink>
      </nav>

    </div>
  </header>
  <RouterView />
  <AppFooter />
</template>

<style lang="scss" scoped></style>
