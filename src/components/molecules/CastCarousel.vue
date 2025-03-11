<script lang="ts" setup>
import scarlettImage from '/assets/actors/scarlet-johansson.jpg';
import jonathanImage from '/assets/actors/jonathan-bailey.jpg';
import rupertImage from '/assets/actors/rupert-friend.jpg';
import mahershalaImage from '/assets/actors/mahershala-ali.jpg';
import manuelImage from '/assets/actors/manuel-garcia-rulfo.jpg';  
import audrinaImage from '/assets/actors/audrina-miranda.jpg';  
import bechirImage from '/assets/actors/bechir-sylvain.jpg';  
import lunaImage from '/assets/actors/luna-blaise.jpg';  
import edImage from '/assets/actors/ed-skrein.jpg';  
import profileImage from '/assets/actors/profile.jpg';  
  
  
const actors = [
  {
    name: "Scarlett Johansson",
    character: "Zora Bennett",
    img: {
        src: scarlettImage,
        width: 120,
        height: 120,
        alt: 'Scarlett Johansson, actress in Jurassic World Rebirth'
      },
    url: "https://www.imdb.com/name/nm0424060/"
  },
  {
    name: "Jonathan Bailey",
    character: "Dr. Henry Loomis",
    img: {
        src: jonathanImage,
        width: 120,
        height: 120,
        alt: 'Jonathan Bailey, actor in Jurassic World Rebirth'
      },
    url: "https://www.imdb.com/name/nm0047332/?ref_=tt_cst_t_2"
  },
  {
    name: "Rupert Friend",
    character: "Martin Krebs",
    img: {
        src: rupertImage,
        width: 120,
        height: 120,
        alt: 'Rupert Friend, actor in Jurassic World Rebirth'
      },
    url: "https://www.imdb.com/name/nm1670029/?ref_=tt_cst_t_3"
  },
  {
    name: "Mahershala Ali",
    character: "Duncan Kincaid",
    img: {
        src: mahershalaImage,
        width: 120,
        height: 120,
        alt: 'Mahershala Ali, actor in Jurassic World Rebirth'
      },
    url: "https://www.imdb.com/name/nm0991810/?ref_=tt_cst_t_5"
  },
  {
    name: "Manuel Garcia-Rulfo",
    character: "Reuben Delgado",
    img: {
        src: manuelImage,
        width: 120,
        height: 120,
        alt: 'Manuel Garcia-Rulfo, actor in Jurassic World Rebirth'
      },
    url: "https://www.imdb.com/name/nm2636310/?ref_=tt_cst_t_4"
  },
  {
    name: "Audrina Miranda",
    character: "Isabella Delgado",
    img: {
        src: audrinaImage,
        width: 120,
        height: 120,
        alt: 'Audrina Miranda, actress in Jurassic World Rebirth'
      },
    url: "https://www.imdb.com/name/nm12778418/?ref_=tt_cst_t_11"
  },
  {
    name: "Bechir Sylvain",
    character: "LeClerc",
    img: {
        src: bechirImage,
        width: 120,
        height: 120,
        alt: 'Bechir Sylvain, actor in Jurassic World Rebirth'
      },
    url: "https://www.imdb.com/name/nm2718355/?ref_=tt_cst_t_10"
  },
  {
    name: 'Luna Blaise',
    character: 'Delgado',
    img: {
        src: lunaImage,
        width: 120,
        height: 120,
        alt: 'Luna Blaise, actress in Jurassic World Rebirth'
      },
    url: 'https://www.imdb.com/name/nm2399046/?ref_=tt_cst_t_7',
  },
  {
    name: "Ed Skrein",
    character: "(To Be Announced)",
    img: {
        src: edImage,
        width: 120,
        height: 120,
        alt: 'Ed Skrein, actor in Jurassic World Rebirth'
      },
    url: "https://www.imdb.com/name/nm4534098/?ref_=tt_cst_i_6"
  },
  {
    name: "See more from",
    character: "cast & crew",
    img: {
        src: profileImage,
        width: 120,
        height: 120,
        alt: 'profile icon'
      },
    url: "https://www.imdb.com/title/tt31036941/"
  }
];
</script>

<template>
  <div class="card-container">
    <a :href="card.url" target="_blank" class="card" v-for="(card, index) in actors" :key="index">
      <img class="cast-image" :src="card.img.src" :alt="card.img.alt" loading="lazy" width="120px" height="120px" />
      <div class="actor-info">
        <p class="actor-name">{{ card.name }}</p>
        <p class="character-name">{{ card.character }}</p>
      </div>
    </a>
  </div>
</template>
<style lang="scss" scoped>

h2 {
  @include h2;
  background-color: $black;
  color: $white;
  text-decoration: underline;
}
  .card-container {
    display: grid;
    grid-template-columns: repeat(10, 1fr);
    background-color: $black;
    padding-bottom: 10px;
    gap: 20px;
    max-width: 100vw;
    overflow-x: auto;
    padding: rem(40);

    .card {
      max-width: 144px;
      max-height: 192px;
      background-color: $black;
      cursor: pointer;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
    }

    .card:hover {
      transform: scale(1.05);
      transition: transform 0.2s ease-in-out;
    }

    p {
      color: $white;
      font-size: rem(12);
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
    justify-content: center; 
    width: 100%;
  }

  .cast-image {
    border-radius: 50%;
    object-fit: cover;
  }

  /* Media query för tablet-läge */
  @media (min-width: 720px) and (max-width: 1240px) {
    .card-container {
      overflow-x: unset;
      grid-template-columns: repeat(5, 1fr); /* 5 kort per rad */
      grid-template-rows: repeat(2, auto); /* 2 rader */
    }

    .card {
      max-width: 100%;
      max-height: auto;
    }
  }
</style>
