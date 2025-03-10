<script setup lang="ts">
import TheButton from '@/components/atoms/TheButton.vue';
</script>

<template>
  <div class="home">
    <div class="image-container">
      <img src="\assets\JurassicLogo.jpg" alt="" width="390px" height="425px">
    </div>
    <h2 class="premier-text">Premiere 2 July</h2>
    <div class="button-container">
      <TheButton button-text="Watch Trailer" class="homepage-buttons"/>
      <TheButton button-text="Book Tickets" class="homepage-buttons"/>
    </div>
    <div class="quote-container">
      <blockquote>
        <p class="quote-p">"I came for dinosaurs. I stayed because I was too shocked to move. 10/10, would get eaten again."</p>
        <p class="quote-giver">-Dino Saar</p>
      </blockquote>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.home {
  background-color: black;
  height: 86.7vh;
  display: flex;
  flex-direction: column;
  align-items: center;

  .image-container {
    margin-top: 5rem;
  }
  
  h2 {
    text-align: center;
    margin-top: 2rem;
    color: $lightyellow;
  }

  .button-container {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 1.5rem;
    gap: 2rem;

    .homepage-buttons {
      width: 8.25rem;
      height: 2.75rem;
      white-space: nowrap;
    }
  }
  
  .quote-container {
    width: 85%;
    margin: auto;
    margin-top: 0.5rem;
    display: flex;
    align-items: center;
    justify-content: center;
    color: rgba(255, 255, 255, 0.35);;
    font-size: 20px;
    font-style: italic;
      
    .quote-giver {
      margin: 1rem;
      position: relative;
      left: 16.5rem;
    }

    .quote-p {
      margin: 0;
    }
  }
}
</style>
