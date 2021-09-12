<template>
  <div class="main container">
      <!-- film -->
      <h1>Movies</h1>
      <ul>
          <li v-for="(movie,index) in movies" :key="index" >
              <div>
                  <div><strong>titolo:</strong>{{movie.title}}</div>
                  <div><strong>titolo originale:</strong>:{{movie.original_title}}</div>
                  <div v-if="movie.original_language=== 'en'"><strong>lingua originale:</strong><img src="../assets/img/gb.svg" alt="eng"></div>
                  <div v-else-if="movie.original_language=== 'it'"><strong>lingua originale:</strong><img src="../assets/img/it.svg" alt="ita"></div>
                  <div v-else ><strong>lingua originale:</strong>{{movie.original_language}}</div>
                  <div><strong>voto:</strong>{{movie.vote_average}}</div>
                </div>
          </li>
      </ul>
      <!-- serie TV -->
      <h1>Series</h1>
      <ul>
          <li v-for="(serie,index) in series" :key="index" >
              <div>
                  <div><strong>titolo:</strong>{{serie.name}}</div>
                  <div><strong>titolo originale:</strong>:{{serie.original_name}}</div>
                  <div v-if="serie.original_language=== 'en'"><strong>lingua originale:</strong><img src="../assets/img/gb.svg" alt="eng"></div>
                  <div v-else-if="serie.original_language=== 'it'"><strong>lingua originale:</strong><img src="../assets/img/it.svg" alt="ita"></div>
                  <div v-else ><strong>lingua originale:</strong>{{serie.original_language}}</div>
                  <div><strong>voto:</strong>{{serie.vote_average}}</div>
                </div>
          </li>
      </ul>
  </div>
</template>

<script>
export default {
    name: "Main",
    props:['movies', 'series'],
}
</script>

<style  lang="scss">
ul{
    list-style-type: none;
    li{
        margin-bottom: 20px;
        border: 1px solid black;
        padding: 10px;
        
        img{
            width: 20px;
        }
    }
}

</style>