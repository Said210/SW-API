<template>
  <h2 class="text-xl"> SW API </h2> <br>
  <div class=" movies bg-gray-200 grid grid-cols-3 gap-4 justify-center items-center overflow-x-auto">
    <FilterArea v-bind:movies="movies"/>
    
  </div>
</template>

<script>
import FilterArea from './components/FilterArea.vue'

import axios from "axios";

export default {
  name: 'App',
  components: {
    FilterArea
  }, 
  data () {
    return{
      movies: [],
//      characters: [],
      currently: null
    }
  },
  mounted() {
    axios.get("https://swapi.dev/api/films/")
    .then((response) => {
      this.movies = response.data.results
    })
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
.movies{
  min-height: 10rem;
}
</style>
