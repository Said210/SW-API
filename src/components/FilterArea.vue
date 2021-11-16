<template>
   <!-- Start of component -->
   <div class="bg-white rounded-xl p-3" v-for="(movie,i) in movies" v-bind:key="movie.episode_id">
      <div id="header" class="items-center mb-4"> 
         <div id="header-text" class="leading-5 sm">
            <h4 class="text-xl font-semibold">{{movie.title}}</h4>
            <h5 class="font-semibold text-blue-600">{{movie.release_date}}</h5>
         </div>
      </div>
      <div id="quote">
         <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" v-on:click="select_movie(movie.episode_id, i)">Ver mas</button>
      </div>
   </div>
   <!-- End of component -->


   <CharactersArea v-bind:characterurl="character" v-for="character in characters" :key="character"/>
</template>

<script>
import CharactersArea from './CharactersArea.vue'
// import axios from "axios";

export default {
  name: 'FilterArea',
  components: {
    CharactersArea
  },
  props: {
    movies: Array
  },
  data(){
    return{
      characters: []
    }
  },
  methods: {
    select_movie: function(movie_id, movie_index){
      console.log(this.movies[movie_index].characters)
      this.characters = this.movies[movie_index].characters;
    } 
  },
  mounted() {
    this.characters = this.movies.characters;
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
