<script lang="ts" setup></script>

<template>
  <div class="wrapper">
    <div class="icon-wrapper">
      <img src="/assets/facebookIcon.jpg" />
      <img src="/assets/InstagramIcon.jpg" />
      <img src="/assets/youtubeIcon.jpg" />
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
  min-height: 50px;
  background-color: $lightgreen;
}

.icon-wrapper {
  display: flex;
  justify-content: flex-start;
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
    font-size: 6px;
  }
}

.upper {
  text-transform: uppercase;
}

img {
  max-width: 20px;
  max-height: 20px;
}

@media (min-width: 600px) {
  .p-wrapper {
    justify-content: flex-end;
  }

  img {
    max-width: 30px;
    max-height: 30px;
  }
}

@media (min-width: 1024px) {
  img {
    max-width: 40px;
    max-height: 40px;
  }
}
</style>
