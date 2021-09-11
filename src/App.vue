<template>
  <div id="app">
    <Header @performSearch="performSearch"/>
    <Main :movies="movies"/>
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data(){
    return{
      //dati stringa API
      baseUri:'https://api.themoviedb.org/3',
      apiKey:'?api_key=0181c88e325259dc3871fdd26428b628',
      //termine per la ricerca
      searchTerm:'',
      //risultati ricerca
      movies:[],
    }
  },
  methods:{
    //intercetto evento e eseguo ricerca 
    performSearch(userSearch){
      console.log(this.searchTerm);
      this.searchTerm = userSearch;
      axios.get(`${this.baseUri}/search/movie/${this.apiKey}&query=${this.searchTerm}`).then((res)=>{
      this.movies=(res.data.results);
     })
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container{
  max-width: 1300px;
  margin: 0 auto;
}
</style>
