<template>
  <div id="app">
    <Header @performSearch="performSearch"/>
    <Main :movies="movies" :series="series" :searchTerm="searchTerm"/>
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
      series:[],
    }
  },
  
  methods:{
    //intercetto evento e eseguo ricerca 
    performSearch(userSearch){
      this.searchTerm = userSearch;
      axios.get(`${this.baseUri}/search/movie/${this.apiKey}&language=it_IT&query=${this.searchTerm}`)
      .then((res)=>{this.movies=(res.data.results);});
      axios.get(`${this.baseUri}/search/tv/${this.apiKey}&language=it_IT&query=${this.searchTerm}`)
      .then((res)=>{this.series=(res.data.results);});
    }
  }
}
</script>

<style lang="scss">
@import '~@fortawesome/fontawesome-free/css/all.min.css';

html{
  background-color:gray;
}
  
// html::-webkit-scrollbar {
//   display: none;
// }


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color:gray;
  overflow-y: hidden;
}

.container{
  max-width: 1300px;
  margin: 0 auto;
}


</style>
