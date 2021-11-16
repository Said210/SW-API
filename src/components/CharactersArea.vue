<template>
   <!-- Start of component -->
   <div class="bg-white border-2 p-6 rounded-md w-full shadow-lg" >
      <strong>{{name}}</strong> <br>
      {{birth_year}}
   </div>
   <!-- End of component -->
</template>

<script>
import axios from "axios";
export default {
  name: 'CharactersArea',
  props: {
    characterurl: String
  }, 
  data(){
    return{
      name: "",
      birth_year: ""
    }
    // 
  },
  mounted(){
    console.log(this.characterurl);
    axios.get(this.characterurl)
    .then((response) => {      
      let r = response.data;
      console.log(r);
      this.name = r.name;
      this.birth_year = r.birth_year;

    }).catch(function (error) {
    // handle error
    console.log(error);
  })
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
