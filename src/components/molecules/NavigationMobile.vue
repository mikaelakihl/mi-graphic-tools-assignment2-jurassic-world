<script lang="ts" setup>
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
  <div class="wrapper">

<h2>Menu</h2>

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
.wrapper{
  background-color: black;
  width: 80%;
  height: 100vh;
  color: white;
}

.nav-links{

  display: flex;
  flex-direction: column;
  padding-bottom: 10px;




}

.router-link{
  color: white;
  text-decoration: none;
  border-bottom: solid white 1px;
}
</style>

