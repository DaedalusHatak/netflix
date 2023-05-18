<script setup lang="ts">
import HeroNetflix from '@/components/HeroNetflix.vue'
import BaseCard from '@/components/BaseCard.vue'
import AskedQuestions from '@/components/AskedQuestions.vue'
import { ref, type Component } from 'vue'
import EnjoyTv from '@/components/comp-img/EnjoyTv.vue'
import KidsImg from '@/components/comp-img/KidsImg.vue'
import EverywhereImg from '@/components/comp-img/EverywhereImg.vue'
import DownloadImg from '@/components/comp-img/DownloadImg.vue'


type Movie =  {
adult: boolean,
backdrop_path: string,
genre_ids: number[],
id:number,
original_language:string,
original_title: string,
overview: string,
popularity:number,
poster_path:string,
release_date:string,
title:string,
video: boolean,
vote_average: number,
vote_count:number
}

type Results = {
  results: Movie[]
}
const movies = ref<Results>();

interface Section{
  header: string,
  desc: string,
  comp: Component,
  reverse?: boolean
}
const sections: Section[] =[
  {
    header: 'Enjoy on your TV',
    desc: 'Watch on Smart TVs, Playstation, Xbox, Chromecast, Apple TV, Blu-ray players, and more.',
    comp: EnjoyTv
  },
  {
    header: 'Download your shows to watch offline',
    desc: 'Save your favorites easily and always have something to watch.',
    comp: DownloadImg,
    reverse: true
  },
  {
    header: 'Watch everywhere',
    desc: 'Stream unlimited movies and TV shows on your phone, tablet, laptop, and TV.',
    comp: EverywhereImg
  },
  {
    header: 'Create profiles for kids',
    desc: 'Send kids on adventures with their favorite characters in a space made just for them—free with your membership.',
    comp: KidsImg,
    reverse: true
  }
]
async function getMovies() {
  let key: String
  await fetch(`${import.meta.env.VITE_APP_SERVER_NAME}/get-token`)
    .then((res) => {
      return res.json()
    })
    .then((resp) => {
      key = resp.access_token
    })
    .then(() => {
      fetch(`${import.meta.env.VITE_APP_SERVER_NAME}/hello`, {
        headers: { 'content-type': 'application/json', authorization: `Bearer ${key}` }
      })
        .then((resp) => {
          return resp.json()
        })
        .then((response) => {
          movies.value = response
        })
    })
}

getMovies()
</script>

<template>
    <section class="hero-image">
      <HeroNetflix/>
    </section>
    <section v-for="section in sections" :key="section.header">
      <BaseCard
        class="content-section"
        :reverse="section.reverse"
        :header="section.header"
        :desc="section.desc"
        ><component :is="section?.comp"></component
      ></BaseCard>
    </section>

    <section>
      <AskedQuestions class="content-section"/>
    </section>
    <div v-if="movies">
      <div class="movies" v-for="movie in movies.results" :key="movie.id">
        {{ movie.original_title }}
      </div>
    </div>
</template>


<style scoped>
.movies {
  padding: 2rem;
}

section {
  position: relative;
  padding: 0 1.5rem;
}
section::after {
  content: '';

  width: 200%;
  height: 0.2rem;
  bottom: -0.2rem;
  background-color: rgb(51, 26, 187, 0.8);

  z-index: 10;
  position: absolute;
  display: flex;
left:-1.5rem;
  justify-content: center;
  color: rgb(255, 255, 255);
  text-align: center;
}
@media screen and (min-width: 600px) {
  .content-section {
    max-width: calc(100% - 4rem);
    margin: auto;
  }
}
@media screen and (min-width: 1280px) {
  .content-section {
    max-width: calc(83.33333333333334% - 6rem);
    margin: auto;
  }
  section{
    padding: 0 3rem;
  }
}
@media screen and (min-width: 1920px) {
  .content-section {
    max-width: calc(66.66666666666666% - 6rem);
    margin: auto;
  }
}
</style>