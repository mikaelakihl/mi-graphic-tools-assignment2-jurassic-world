<script setup lang="ts">
import CastCarousel from '@/components/molecules/CastCarousel.vue';
</script>

<template>
  <div class="cast">
    <CastCarousel />

    <div class="crew">
      <h2>Crew</h2>
      <div class="crew-info">
        <h3>Director</h3>
        <p>Gareth Edwards</p>
      </div>

      <div class="crew-info">
        <h3>Producers</h3>
        <p>Frank Marshall</p>
        <p>Patrick Crowley</p>
      </div>

      <div class="crew-info">
        <h3>Executive Producers</h3>
        <p>Steven Spielberg</p>
        <p>Denis L. Stewart</p>
        <p>Jim Spencer</p>
      </div>

      <div class="crew-info">
        <h3>Screenplay by</h3>
        <p>David Koepp</p>
        <p>based om characters created by Michael Crichton</p>
      </div>
    </div>
    
    <a href="https://www.imdb.com/title/tt31036941/" target="_blank">Read more about production</a>

    <img src="/assets/imgs/jurassic-world-rebirth-ocean.jpg" />
  </div>
</template>

<style lang="scss" scoped>

.cast {
  display: flex;
  flex-direction: column;
  background-color: $black;
  color: white;

  h2 {
    text-decoration: underline;
    font-size: rem(24);
    font-weight: 400;
    margin-left: rem(30);

  }
  a {
      @include link;
      color: $yellow;
      align-self: center;
      padding-top: rem(20);
      text-decoration: none;
    }

  img {
    padding: rem(10);
  }
}

.crew {
  .crew-info {
    font-size: rem(16);
    margin-left: rem(30);


    h3 {
      font-weight: 700;
      margin-bottom: 0;
    }

    p {
      margin-top: 0;
      margin-bottom: 0;
      font-weight: 300;
      font-style: italic;
    }
  }
}

@media (min-width: 720px) {
.cast {
  a {
  margin: rem(40);
}
}
  .crew {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  text-align: center;
  h2 {
    margin-left: 0;
    grid-column: 1/5 span;
  }

  :nth-child(2), :nth-child(4) {
    grid-column: 2 / 3;
  }
  
  :nth-child(3), :nth-child(5) {
    grid-column: 4 / 5;
  }
  .crew-info {
    text-align: left;
  }

}

}

</style>
