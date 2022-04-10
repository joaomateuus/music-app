<template>
  <div class="md: flex flex-col content-center text-white">
      <div class="md: flex flex-row justify-between">
        <button  class="w-20 border-2 border-white rounded-md hover:bg-white hover:text-green-800 text-xl font-bold"
        @click="goback">
          Back 
        </button>
        <h1 class="font-bold">Vue MusicApp</h1>
      </div>
      <div class="md:flex flex-col content-center justify-center mt-4 pr-2">
        <img class="h-64 w-64 ml-64 rounded-md" :src="music.src" alt=""> 
        <h1 class="pt-4 font-bold text-xl">{{ music.name }}</h1>
        <h2>{{ music.artistName }}- {{ music.albumName }}</h2>
        <h3>{{ music.year }}</h3>
      </div>

      <div class="md:flex flex-row content-center justify-center space-x-12 pt-8 mr-8">
        <button class="border-2 border-white rounded-full h-14 w-14 bg-white pt-4"></button>
        <button class="border-2 border-white rounded-full h-14 w-14 pl-4 hover:bg-green-800 hover:border-green-800 bg-white"><img src="https://cdn4.iconfinder.com/data/icons/ionicons/512/icon-pause-512.png" class="h-6 w-6" alt=""></button>
        <button class="border-2 border-white rounded-full h-14 w-14 pl-4 bg-white hover:bg-black"><img src="https://findicons.com/files/icons/770/token_dark/256/media_player.png" class="h-6 w-6" alt=""></button>
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
      songSrc: String,
    },

  },
  emits: ['goback'],
  methods: {
      goback(){
        this.$emit('goback');
      }
  }
}
</script>

<style>

</style>