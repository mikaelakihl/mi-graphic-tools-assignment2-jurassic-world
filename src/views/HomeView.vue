<script setup lang="ts">
import TheButton from '@/components/atoms/TheButton.vue'
import CookiesBanner from '@/components/molecules/CookiesBanner.vue'
</script>

<template>
  <div class="home">
    <div class="image-container">
      <img src="\assets\icons\jurassic-logo.jpg" alt="" width="390px" height="425px" />
    </div>
    <h2 class="premier-text">Premiere 2 July</h2>
    <div class="button-container">
      <TheButton button-text="Watch Trailer" class="homepage-buttons" />
      <TheButton button-text="Book Tickets" class="homepage-buttons" />
    </div>
    <div class="quote-container">
      <blockquote>
        <p class="quote-p">
          "I came for dinosaurs. I stayed because I was too shocked to move. 10/10, would get eaten
          again."
        </p>
        <p class="quote-giver">-Dino Saar</p>
      </blockquote>
    </div>
    <CookiesBanner />
  </div>
</template>

<style lang="scss" scoped>
.home {
  background-color: black;
  min-height: 84.1vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  // text-align: center;

  .image-container {
    margin-top: 3rem;
  }
  h2 {
    text-align: center;
    margin: 0;
    margin-top: -0.5rem;
    @include h1;
    color: $lightyellow;
  }

  .button-container {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 3.5rem;
    gap: 3rem;

    .homepage-buttons {
      width: 8.25rem;
      height: 2.75rem;
      white-space: nowrap;
    }
  }

  .quote-container {
    width: 100%;
    margin: 0;
    margin-top: 1rem;
    color: rgba(255, 255, 255, 0.5);
    font-size: rem(20);
    font-style: italic;
    @include h3;

    .quote-giver {
      text-align: right;
    }

    .quote-p {
      width: 80%;
      margin: auto;
    }
  }
}

@media (min-width: 768px) and (max-width: 1024px) {
  .home {
    height: 83vh;
    max-height: 83vh;
    overflow-y: auto;
    .image-container {
      width: 100%;
      height: auto;
      text-align: center;
      margin-top: 0;
      img {
        width: 70%;
        height: auto;
      }
    }

    h2 {
      margin-top: -175px;
    }

    .button-container {
      margin-top: 2rem;
      gap: 6rem;

      .homepage-buttons {
        width: 11.5625rem;
        height: 2.9375rem;
      }
    }

    .quote-container {
      .quote-giver {
        margin-right: 7rem;
      }

      .quote-p {
        text-align: right;
        width: 60%;
      }
    }
  }
}

@media (min-width: 1025px) {
  .home {
    height: 85vh;
    .image-container {
      height: 90%;
      text-align: center;
      img {
        position: relative;
        bottom: 5rem;
        width: 100%;
        height: 100%;
        z-index: 0;
      }
    }

    h2 {
      z-index: 1;
      margin-top: -240px;
    }

    .button-container {
      .homepage-buttons {
        z-index: 1;
      }
    }

    .quote-container {
      width: 47%;
      .quote-giver {
        text-align: right;
      }

      .quote-p {
        width: 100%;
      }
    }
  }
}
</style>
