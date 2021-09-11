<template>
    <div class="header">
        <input v-model="userSearch" type="text"  v-on:keyup.enter="$emit('performSearch', userSearch)">    
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

</style>