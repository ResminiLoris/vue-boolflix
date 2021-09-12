<template>
  <div v-if="searchTerm" class="main container">
      <!-- film -->
      <h1>Movies</h1>
      <ul>
          <li v-for="(movie,index) in movies" :key="index" >
              <div>
                  <!-- poster -->
                  <div><img class="poster" :src="`${posterUri}${posterWidth}${movie.poster_path}`" alt=""></div>
                  <!-- titolo -->
                  <div><strong>titolo:</strong>{{movie.title}}</div>
                  <!-- titolo originale -->
                  <div><strong>titolo originale:</strong>:{{movie.original_title}}</div>
                  <!-- lingua -->
                  <div v-if="movie.original_language=== 'en'"><strong>lingua originale:</strong><img class="leng-icon" src="../assets/img/gb.svg" alt="eng"></div>
                  <div v-else-if="movie.original_language=== 'it'"><strong>lingua originale:</strong><img class="leng-icon" src="../assets/img/it.svg" alt="ita"></div>
                  <div v-else ><strong>lingua originale:</strong>{{movie.original_language}}</div>
                  <!-- voto -->
                  <div><strong>voto:</strong>{{movie.vote_average}}</div>
                </div>
          </li>
      </ul>
      <!-- serie TV -->
      <h1>Series</h1>
      <ul>
          <li v-for="(serie,index) in series" :key="index" >
              <div>
                  <!-- poster -->
                  <div><img class="poster" :src="`${posterUri}${posterWidth}${serie.poster_path}`" alt=""></div>
                  <!-- titolo -->
                  <div><strong>titolo:</strong>{{serie.name}}</div>
                  <!-- titolo originale -->
                  <div><strong>titolo originale:</strong>:{{serie.original_name}}</div>
                  <!-- lingua -->
                  <div v-if="serie.original_language=== 'en'"><strong>lingua originale:</strong><img class="leng-icon" src="../assets/img/gb.svg" alt="eng"></div>
                  <div v-else-if="serie.original_language=== 'it'"><strong>lingua originale:</strong><img class="leng-icon" src="../assets/img/it.svg" alt="ita"></div>
                  <div v-else ><strong>lingua originale:</strong>{{serie.original_language}}</div>
                  <!-- voto -->
                  <div><strong>voto:</strong>{{serie.vote_average}}</div>
                </div>
          </li>
      </ul>
  </div>
</template>

<script>
export default {
    name: "Main",
    props:['movies', 'series', 'searchTerm'],
    data(){
        return{
            posterUri: 'https://image.tmdb.org/t/p',
            posterWidth: '/w342',
        }
    },
}
</script>

<style  lang="scss">
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
