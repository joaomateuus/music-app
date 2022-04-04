<template>
    <div class="md:flex flex-col">
        <h1 class="text-white text-xl">Vue MusicApp</h1>
        <div class="md: flex flex-row justify-evenly mt-2 mb-2" v-for="music in list" :key="music.id"> 
           <div class="md: flex flex-col text-white">
                <span class="text-green-500">{{ music.name }}</span>
                <span >
                    {{ music.artistName }}
                    <span> {{ music.albumName }} - {{ music.year }}</span>
                </span>
           </div>
            <div class="">
                <img :src="music.src" alt="">
            </div>
        </div>
    
        <div>
            <MusicPlayer />
        </div>
    
    </div>
</template>

<script>
import MusicPlayer from './MusicPlayer.vue'

export default {
    name: 'MusicList',
    components: {MusicPlayer},
    data() {
        return{
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

