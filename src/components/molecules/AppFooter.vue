<script lang="ts" setup></script>

<template>
  <div class="wrapper">
    <div class="icon-wrapper">
      <img src="/assets/icons/facebook-icon.jpg" />
      <img src="/assets/icons/InstagramIcon.jpg" />
      <img src="/assets/icons/youtube-icon.jpg" />
    </div>
    <div class="p-wrapper">
      <p class="upper">Movie platform © 2025 Powster</p>
      <p>© 2025 Universal Pictures. <span class="upper">All rights reserved.</span></p>
      <p>In Theaters July 2, 2025.</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.wrapper {
  width: 100%;
  min-height: rem(40);
  background-color: $lightgreen;
}

.icon-wrapper {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  padding-top: 0.5rem;
  padding-left: 1rem;
  padding-bottom: 0.5rem;
  gap: 0.5rem;
}

.p-wrapper {
  display: flex;
  justify-content: space-between;
  padding-left: 0.5rem;
  padding-right: 0.5rem;

  p {
    color: $white;
    @include h2;
    font-size: rem(6);
  }
}

.upper {
  text-transform: uppercase;
}

img {
  max-width: rem(20);
  max-height: rem(20);
}

@media (min-width: 600px) {
  .p-wrapper {
    justify-content: flex-end;
  }

  img {
    max-width: rem(30);
    max-height: rem(30);
  }
}

@media (min-width: 1024px) {
  .wrapper {
    display: flex;
    justify-content: space-between;
}

.p-wrapper {
  align-items: end;
}
}
</style>
