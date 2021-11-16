<template>
   <!-- Start of component -->
   <div class="bg-white border-2 p-6 rounded-md width-1/3 shadow-lg" v-for="character in charactersprop" v-bind:key="character.name">
      {{JSON.stringify(character)}}
   </div>
   <!-- End of component -->
</template>

<script>
export default {
  name: 'CharactersArea',
  props: {
    charactersprop: Array
  }, 
  data(){
    return{
      characters: []
    }
    // 
  },
  mount(){
  }
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
