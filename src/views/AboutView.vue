<script setup lang="ts"></script>

<template>
  <div class="about">

    <img src="/assets/imgs/jurassic-world-rebirth-zora-loomis.jpg" alt="two people who are looking att a dinosaure egg in a nest"/>
  
    <article>
      <header>
        <h1>Jurassic World: Rebirth (2025)</h1>
        <p>Genres: Action, Adventure, Sci-Fi, Thriller</p>
      </header>
  
      <section>
        <p>
          Five years after the events of Jurassic World Dominion, the planet's ecology has 
          proven largely inhospitable to dinosaurs. Those remaining exist in isolated equatorial 
          environments with climates resembling the one in which they once thrived. The three most 
          colossal creatures across land, sea, and air within that tropical biosphere hold, in their DNA, 
          the key to a drug that will bring miraculous life-saving benefits to humankind.
        </p>
      </section>
  
      <section>
        <p>
          Academy Award® nominee Johansson plays skilled covert operations expert 
          Zora Bennett, contracted to lead a skilled team on a top-secret mission to 
          secure the genetic material. When Zora's operation intersects with a civilian 
          family whose boating expedition was capsized by marauding aquatic dinos, 
          they all find themselves stranded on a forbidden island that had once housed 
          an undisclosed research facility for Jurassic Park. There, in a terrain 
          populated by dinosaurs of vastly different species, they come face-to-face 
          with a sinister, shocking discovery that has been hidden from the world for decades.
        </p>
      </section>
    </article>
  </div>
</template>

<style lang="scss" scoped>
  .about {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    img {
      object-fit: cover;
      max-width: 85vw;
    }

    h1 {
      @include h2;
      color: $yellow;
    }
    p {
      @include h2;
      font-size: rem(15);
      color: $yellow;
      max-width: 40ch;
    }
  }
</style>
