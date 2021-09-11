<template>
  <div class="main container">
      <ul>
          <li v-for="(movie,index) in movies" :key="index" >
              <div>
                  <div><strong>titolo:</strong>{{movie.title}}</div>
                  <div><strong>titolo originale:</strong>:{{movie.original_title}}</div>
                  <div><strong>lingua originale:</strong>{{movie.original_language}}</div>
                  <div><strong>voto:</strong>{{movie.vote_average}}</div>
                </div>
          </li>
      </ul>
  </div>
</template>

<script>
export default {
    name: "Main",
    props:['movies'],
}
</script>

<style  lang="scss">
ul{
    list-style-type: none;
    li{
        margin-bottom: 20px;
        border: 1px solid black;
        padding: 10px;
    }
}

</style>