<script lang="ts" setup>
const actors = [
  {
    image: "assets/actors/scarlet-johansson.jpg",
    name: "Scarlett Johansson",
    character: "Zora Bennett",
    url: "https://www.imdb.com/name/nm0424060/"
  },
  {
    image: "assets/actors/jonathan-bailey.jpg",
    name: "Jonathan Bailey",
    character: "Dr. Henry Loomis",
    url: "https://www.imdb.com/name/nm0047332/?ref_=tt_cst_t_2"
  },
  {
    image: "assets/actors/rupert-friend.jpg",
    name: "Rupert Friend",
    character: "Martin Krebs",
    url: "https://www.imdb.com/name/nm1670029/?ref_=tt_cst_t_3"
  },
  {
    image: "assets/actors/mahershala-ali.jpg",
    name: "Mahershala Ali",
    character: "Duncan Kincaid",
    url: "https://www.imdb.com/name/nm0991810/?ref_=tt_cst_t_5"
  },
  {
    image: "assets/actors/manuel-garcia-rulfo.jpg",
    name: "Manuel Garcia-Rulfo",
    character: "Reuben Delgado",
    url: "https://www.imdb.com/name/nm2636310/?ref_=tt_cst_t_4"
  },
  {
    image: "assets/actors/audrina-miranda.jpg",
    name: "Audrina Miranda",
    character: "Isabella Delgado",
    url: "https://www.imdb.com/name/nm12778418/?ref_=tt_cst_t_11"
  },
  {
    image: "assets/actors/bechir-sylvain.jpg",
    name: "Bechir Sylvain",
    character: "LeClerc",
    url: "https://www.imdb.com/name/nm2718355/?ref_=tt_cst_t_10"
  },
  {
    image: "assets/actors/luna-blaise.jpg",
    name: "Luna Blaise",
    character: "Delgado",
    url: "https://www.imdb.com/name/nm2399046/?ref_=tt_cst_t_7"
  },
  {
    image: "assets/actors/ed-skrein.jpg",
    name: "Ed Skrein",
    character: "(To Be Announced)",
    url: "https://www.imdb.com/name/nm4534098/?ref_=tt_cst_i_6"
  },
  {
    image: "assets/actors/ed-skrein.jpg",
    name: "See more from",
    character: "cast & crew",
    url: "https://www.imdb.com/title/tt31036941/"
  }
];

const openActorPage = (url: string) => {
  if (url) {
    window.open(url, "_blank"); // Öppnar länken i en ny flik
  }
};

</script>

<template>
  <div class="card-container">
      <div class="card" v-for="(card, index) in actors" :key="index" @click="openActorPage(card.url)">
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
      cursor: pointer;
    }
    .card:hover {
      transform: scale(1.05);
      transition: transform 0.2s ease-in-out;
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
      width: 120px;
      height: 120px;
  }
</style>