<template>
  <div v-if="searchTerm" class="main container">
        <!-- film -->
        <div v-if="this.movies.length > 0">
            <h1 class="mb-3 mt-3 text-danger text-uppercase fw-bold">Movies</h1>
            <div class="row">
                <Card v-for="(movie,index) in movies" :key="index" :item="movie" class="p-0"/>
            </div>
        </div>
        <!-- serie TV -->
        <div v-if="this.series.length > 0">
            <h1 class="mb-3 mt-3 text-danger text-uppercase fw-bold">Series</h1>
            <div class="row">
                <Card v-for="(serie,index) in series" :key="index" :item="serie" class="p-0"/>
            </div>
        </div>
  </div>
</template>

<script>
import Card from '../components/Card.vue';

export default {
    name: "Main",
    components: {
        Card,
    },
    data(){
        return{
            posterUri: 'https://image.tmdb.org/t/p',
            posterWidth: '/w342',
        }
    },
    props:['movies', 'series', 'searchTerm'],
}
</script>

<style  lang="scss">

.main{
    width: 100vw;
}

ul{
    list-style-type: none;
    li{
        margin-bottom: 20px;
        padding: 10px;
    }
}

.leng-icon{
    width: 20px;
}
</style>
