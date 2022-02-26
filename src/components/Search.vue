<template>
    <div id="search-container">
        <input type="text" v-model="query" v-on:input="$emit('query-change', query)" class="white-text" >
         <i class="material-icons input-icon">search</i>
    </div>
    
</template>

<script>
export default {
    name: 'Search',
    data(){
        return {
            query: ''
        }
    }
}
</script>

<style scoped>
    #search-container{
        width: 450px;
        margin: 0 auto;
        position: relative;
    }
    input{
        padding: 15px 35px 15px 15px;
    }

    .input-icon {
 color: white;
 position: absolute;
  width: 20px;
  height: 20px;
  left: 12px;
  top: 50%;
  transform: translateY(-50%);
  left: unset;
  right: 12px;
  
}
    
</style>