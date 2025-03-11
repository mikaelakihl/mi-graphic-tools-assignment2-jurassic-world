<script lang="ts" setup>
import { computed, ref } from 'vue';
import { RouterLink, RouterView, useRoute } from 'vue-router';

const isActive = ref(false);
const route = useRoute();
const ShouldShowSvg = computed(()=> {
  return route.path!== '/';
});

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
        <div class="router-link-wrapper router-link-wrapper-icon">
          <img
            v-if="ShouldShowSvg"
            class="router-link router-link-icon"
            src="/assets/svg/JurassicWorld.svg"
            height="115px"
          />
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
  <div class="router-link-icon-mobile-wrapper">
      <img
          v-if="ShouldShowSvg"
          class="router-link router-link-icon router-link-icon-mobile"
          src="/assets/svg/JurassicWorld.svg"
          height="115px"
          />
    </div>
  <RouterView />
</template>

<style lang="scss" scoped>

.menu-container {
  position: relative;
  width: 80%;
}
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
  z-index: 998;
}

.menu-open-heading {
  margin-top: 7rem;
  text-align: center;
  @include h1;
}

.nav-links {
  flex-direction: column;
  padding-bottom: 0.625rem;
}

.router-link-wrapper {
  border-bottom: solid $white 1px;
  height: 3.75rem;
  display: flex;
  align-items: center;

  .router-link {
    text-decoration: none;
    margin-left: 1rem;
    @include h4;
    color: $white;

    &:hover{
      border-bottom: 1px solid $white;


    }
  }
}
.menu-container {
  position: relative;
  background-color: $black;
  width: 100%;
  height: 10vh;
}

.hamburger-container {
  position: relative;

  height: 100%;
  display: flex;
  align-items: center;
  justify-content: left;
  margin-left: 1rem;
}

.hamburger {
  width: 3.125rem;
  height: 3.125rem;
  margin: 0.5rem 0 0 0.5rem;
  background: transparent;
  border: 0;
  z-index: 999;
}

.router-link-wrapper-icon {
  display: none;
}
.router-link-icon-mobile-wrapper{
  display: flex;
  justify-content: right;
  height: 100px;

.hamburger.active {
  position: relative;
  // right: 1.25rem;
  left: 19rem;
}

  .router-link-icon-mobile{
    height: 80px;
  }

}

// ------------Tablet/desktop navigation-----------

@media (min-width: 800px) {
  .menu-open-wrapper {
    display: block;
    height: 120px;
    width: 100%;
  }
  .menu-open-heading {
    display: none;
  }

  .hamburger {
    display: none;
  }

  .router-link-wrapper {
    border-bottom: none;
    justify-content: center;
    height: auto;

    .router-link{
      margin-left: 0;
    }
  }

  .nav-links {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    flex-direction: row;
    align-items: center;
    height: 120px;

    .router-link-wrapper:nth-child(4) {
      grid-column: 4;
    }
  }

  .router-link-wrapper-icon {
    display: block;
    align-items: center;
    justify-content: center;
    display: flex;

    .router-link {
      padding-left: 0;
    }

    .router-link-icon {
      max-width: 100%;
      &:hover{
        border-bottom: none;
      }
    }
  }
}
</style>
