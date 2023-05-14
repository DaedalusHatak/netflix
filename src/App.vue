<script setup lang="ts">
import { computed, ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router'
import HeroNetflix from './components/HeroNetflix.vue'
import EnjoyTV from './components/EnjoyTV.vue'

const movies = ref<any>()

async function getMovies() {
  await fetch(import.meta.env.VITE_APP_SERVER_NAME)
    .then((resp) => {
      return resp.json()
    })
    .then((response) => {
      movies.value = response
    })
}
getMovies()
</script>

<template>
  <main>
    <section class="hero-image">
      <hero-netflix></hero-netflix>
  </section>
  <section>
      <EnjoyTV class="content-section"></EnjoyTV>
  </section>
  <section>
      <EnjoyTV class="content-section"></EnjoyTV>
  </section>
  <div class="movies"  v-for="movie in movies.movies.results" :key="movie">{{ movie.original_title}}</div>
</main>
 

  <RouterView />
</template>

<style scoped lang="scss">
.movies{
  padding:2rem;
}
main{
  overflow: hidden;
}
section{

  position: relative;
}
section::after{
  content:'';
  
  width: 100%;
    height: 0.5rem;
    bottom: -0.5rem;
    background-color: rgb(35,35,35);
z-index: 10;
  position: absolute;
    display: flex;

    justify-content: center;
    color: rgb(255,255,255);
    text-align: center;


}
@media screen and (min-width: 600px) {
  .content-section {
    max-width: calc(100% - 4rem);
  }
}
@media screen and (min-width: 1280px) {
  .content-section {
    max-width: calc(83.33333333333334% - 6rem);
  }
}
@media screen and (min-width: 1920px) {
  .content-section {
    max-width: calc(66.66666666666666% - 6rem);
  }
}
</style>
