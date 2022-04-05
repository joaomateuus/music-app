<template>
  <div class="md: flex flex-col content-center text-white">
      <div class="md: flex flex-row justify-between">
        <button class="w-16 border-2 border-white rounded-md">Back</button>
        <h1 class="font-bold">Vue MusicApp</h1>
      </div>
      <div class="md:flex flex-col content-center justify-center mt-4">
        <img class="h-64 w-64 ml-16 rounded-md" :src="music.src" alt=""> 
        <h1 class="pt-2">{{ music.name }}</h1>
        <h2>{{ music.artistName }}- {{ music.albumName }}</h2>
        <h3>{{ music.year }}</h3>
      </div>
  </div>
</template>

<script>
export default {
  name:'MusicPlayer',
  props: {
    music: {
      id: Number,
      name: String,
      artistName: String,
      albumName: String,
      year: Number,
      src: String,
      songSrc: String
    }
  }
}
</script>

<style>

</style>