<template>
    <div class="header row h-100 p-5 justify-content-between align-items-center">
        <div class="col-3">
            <h1 class="text-danger logotext fw-bold">Boolflix</h1>
        </div>
        <div class="col-2">
            <input id="searchbar" v-model="userSearch" type="text" placeholder="cerca..."  v-on:keyup.enter="$emit('performSearch', userSearch)">    
        </div>
    </div>  
</template>

<script>
export default {
    name: 'Header',
    data(){
        return{
            userSearch:'',
        }
    }
}
</script>

<style scoped>
    .header{
        height: 100px;
        background-color: black;
        max-width: 1932px;
    }
    .logotext{
        font-size: 50px;
    }
</style>