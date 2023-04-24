<template>
  <div class="error_container">
    <p>{{error}}</p>    
  </div>
</template>

<script>
export default{
  props:{
    error: String
  }
}
</script>

<style scoped>
  .error_container{
    color: #850000;
    background-color: #ffcccc;
    border: 2px solid #ffb8b8;
    border-radius: 5px;
    padding:10px;
    max-width: 400px;
    margin: 30px auto;
    text-align: center;
  }
</style>