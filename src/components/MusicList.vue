<template>
    <div v-show="!isPlaying" class="md:flex flex-col p-4 pt-4">
        <h1 class="text-white text-4xl m-4">Vue MusicApp</h1>
        <div class="md: flex flex-row justify-evenly mb-2 border-2 border-white rounded-md pt-2 hover:bg-gray-800"
        v-for="(music, musicIndex) in list" :key="music.id" @click="playMusic(musicIndex)"> 
           <div class="md: flex flex-col text-white">
                <span class="text-green-500 text-2xl font-bold">{{ music.name }}</span>
                <span>
                    {{ music.artistName }}
                    <span> {{ music.albumName }} - {{ music.year }}</span>
                </span>
           </div>
            <div class="">
                <img :src="music.src" class="ml" alt="">
            </div>
        </div>
    </div>
    <div v-show="isPlaying">
        <MusicPlayer :music="list[currentMusic]"
        @goback="isPlaying = !isPlaying"  />
    </div>
    
</template>

<script>
import MusicPlayer from './MusicPlayer.vue'

export default {
    name: 'MusicList',
    components: {MusicPlayer},
    data() {
        return{
            isPlaying: false,
            currentMusic: 0,
            list: [
                 {
                    id: 1,
                    name: 'Cheap Thrills',
                    artistName: 'Adam Lambert',
                    albumName: 'Everything',
                    year: 2021,
                    src: `https://source.unsplash.com/random/400x400?date=1`,
                    songSrc: `https://file-examples-com.github.io/uploads/2017/11/file_example_MP3_700KB.mp3`
                },
                {
                    id: 2,
                    name: 'Lean on',
                    artistName: 'Adam Levine',
                    albumName: 'Goind Down',
                    year: 2001,
                    src: `https://source.unsplash.com/random/400x400?date=2`,
                    songSrc: `https://filesamples.com/samples/audio/mp3/sample3.mp3`
                },
                {
                    id: 3,
                    name: 'Counting Stars',
                    artistName: 'Adam Hart',
                    albumName: 'Spice It Up',
                    year: 2013,
                    src: `https://source.unsplash.com/random/400x400?date=3`,
                    songSrc: `https://filesamples.com/samples/audio/mp3/sample1.mp3`
                }

            ]
        }
    },
    methods: {
        playMusic(index) {
            this.currentMusic = index;
            this.isPlaying = true;
        }
    }
}
</script>

<style>

img{
    height:15vh ;
    width: 10vw;
    border-radius: 3px;
}
</style>

