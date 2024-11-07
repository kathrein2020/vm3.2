<script setup>

import {ref ,onMounted, defineAsyncComponent} from "vue"
import Banner from "./components/Banner.vue";

const movies =ref([])
const bannerMovie = ref(null)

const AsyncBanner = defineAsyncComponent(() => {
  return ("./components/Banner.vue")
})




const getMovies = async () => {
  movies.value = await fetch("https://api.themoviedb.org/3/movie/popular?api_key=4e44d9029b1270a757cddc766a1bcb63&language=en-US")
  .then(res => res.json())
  .then(res => res.results)
}

const getRandomInt = (min, max) => {
  return Math.floor(Math.random() * (max-min))
}

onMounted(async()=> {
  await getMovies()
  
  bannerMovie.value=movies.value[getRandomInt(0, movies.value.length-1)]

})
console.log(bannerMovie.value)
</script>

<template>
<!-- <h1 class="bg-red-600" style="background-color: beige;">HelloWorld</h1> -->
<!-- {{ bannerMovie }} -->


<!-- из Banner.vue -->
 <Banner 
:banner="bannerMovie"
/>

</template>

<style>

</style>
