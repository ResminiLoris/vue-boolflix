<template>
<!-- v-for="(movie,index) in movies" :key="index" -->
    <ul class="col-4">
        <li>
            <!-- poster -->
            <div class="cover">
                <div v-if="item.poster_path"><img class="poster" :src="`${posterUri}${posterWidth}${item.poster_path}`" alt=""></div>
                <div v-else><img class="img-placeholder" :src="posterPlaceholder" alt=""></div>
                <div class="hover-effect">
                    <!-- titolo -->
                    <div><strong class="text-danger">titolo:</strong>{{item.title || item.name}}</div>
                    <!-- titolo originale -->
                    <div><strong class="text-danger">titolo originale:</strong>:{{item.original_title || item.original_name}}</div>
                    <div><strong class="text-danger">overview:</strong>:{{item.overview}}</div>
                    <!-- lingua -->
                    <div v-if="item.original_language=== 'en'"><strong class="text-danger">lingua originale:</strong><img class="leng-icon" src="../assets/img/gb.svg" alt="eng"></div>
                    <div v-else-if="item.original_language=== 'it'"><strong class="text-danger">lingua originale:</strong><img class="leng-icon" src="../assets/img/it.svg" alt="ita"></div>
                    <div v-else ><strong class="text-danger">lingua originale:</strong>{{item.original_language}}</div>
                    <!-- voto -->
                    <span v-for="index in 5" :key="index">
                        <i v-if="index <= score(item.vote_average)" class="fas fa-star"></i>
                        <i v-else class="far fa-star"></i>
                    </span>
                </div>
            </div>
          </li>
      </ul>
</template>

<script>
export default {
    name: 'Card',
    props:['item',],
    data(){
        return{
            posterUri: 'https://image.tmdb.org/t/p',
            posterWidth: '/w342',
            posterPlaceholder: 'https://www.altavod.com/assets/images/poster-placeholder.png',
        }
    },
    
    methods:{
        score(vote){
            return Math.round(vote / 2)
        }
    }
}
</script>

<style>
   .img-placeholder{
       width: 342px;
   }
   .cover{
       position: relative;
   }
    .hover-effect{
        opacity: 0;
        padding: 20px;
        position: absolute;
        top: 0;
        display: block;
        width: 342px;
        height: 100%;
        background-color: rgba(0, 0, 0, 0.8);
        color: white;
        cursor: pointer;
        overflow: auto;
    }

    
    
    .hover-effect:hover{
        opacity: 100;
    } 

    .fas,
    .far
    {
        color: yellow;
    }
    
</style>
