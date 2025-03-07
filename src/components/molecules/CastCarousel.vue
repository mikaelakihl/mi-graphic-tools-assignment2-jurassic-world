<script lang="ts" setup>
const actors = [
  {
    image: "assets/actors/scarlet-johansson.jpg",
    name: "Scarlett Johansson",
    character: "Zora Bennett"
  },
  {
    image: "assets/actors/jonathan-bailey.jpg",
    name: "Jonathan Bailey",
    character: "Dr. Henry Loomis"
  },
  {
    image: "assets/actors/rupert-friend.jpg",
    name: "Rupert Friend",
    character: "Martin Krebs"
  },
  {
    image: "assets/actors/mahershala-ali.jpg",
    name: "Mahershala Ali",
    character: "Duncan Kincaid"
  },
  {
    image: "assets/actors/manuel-garcia-rulfo.jpg",
    name: "Manuel Garcia-Rulfo",
    character: "Reuben Delgado"
  },
  {
    image: "assets/actors/audrina-miranda.jpg",
    name: "Audrina Miranda",
    character: "Isabella Delgado"
  },
  {
    image: "assets/actors/bechir-sylvain.jpg",
    name: "Bechir Sylvain",
    character: "LeClerc"
  },
  {
    image: "assets/actors/luna-blaise.jpg",
    name: "Luna Blaise",
    character: "Delgado"
  },
  {
    image: "assets/actors/ed-skrein.jpg",
    name: "Ed Skrein",
    character: "(To Be Announced)"
  },
  {
    image: "assets/actors/ed-skrein.jpg",
    name: "See more from",
    character: "cast & crew"
  }
];

</script>

<template>
  <div class="card-container">
      <div class="card" v-for="(card, index) in actors" :key="index">
          <img class="cast-image" :src="card.image" :alt="card.name" />
          <div class="actor-info">
              <p class="actor-name">{{ card.name }}</p>
              <p class="character-name">{{ card.character }}</p>
          </div>
      </div>
  </div>
</template>

<style lang="scss" scoped>
  .card-container {
    display: flex;
    background-color: $black;
    padding-bottom: 10px;
    gap: 10px;
    max-width: 100vw;
    overflow-x: auto;
    // scroll-behavior: smooth;

    .card {
      min-width: 124px;
      min-height: 172px;
      background-color: $black;
    }

    p {
      color: $white;
      font-size: 12px;
      margin: 0;
    }
    .actor-name {
      font-weight: 700;
    }
  }

  .actor-info {
      display: flex;
      flex-direction: column;
      align-items: center;
  }
  .cast-image {
      border-radius: 50%;
      object-fit: cover;
      width: 124px;
      height: 124px;
  }
</style>