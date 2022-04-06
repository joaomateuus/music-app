<template>
  <div class="app-container p-3 bg-black m-auto" >
    <MusicList />
  </div>
</template>

<script>
import MusicList from './components/MusicList.vue'

export default {
  name: 'App',
  components: {
    MusicList,
  },
  data() {
    return{
       
    }
   
  },
}
</script>

<style>
.app-container{
  width: 60vw;
  height: 90vh;
  border-radius: 5px;
}


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
