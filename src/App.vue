<script setup>
import { RouterView } from 'vue-router';

</script>

<template>
  <div class="wrapper">
    <div class="container">
      <RouterView />
    </div>
  </div>
</template>

<style scoped>
  .wrapper{
    background-color:#c5c8df;
    height: 100vh;
    width: 100vw;
    padding-top: 2rem;
  }
.container{
  
  background-color: #233067;
  max-width:1000px;
  min-height: 85vh;
  margin:0 auto;
  padding: 2rem;
  border-radius: 5px;
  text-align: center;
  color: #fefefe;
}

</style>