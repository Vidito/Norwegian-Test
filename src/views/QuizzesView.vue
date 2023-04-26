<script setup>
import data from '../data/data.json'
import {ref, watch} from 'vue'
import Card from '../components/Card.vue'

const quizzes = ref(data)
const search = ref("")

watch(search, ()=>{
  quizzes.value = data.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()))
})

</script> 

<template>
  <div>
    <header>
      <h1>Language Quizzes</h1>
      <input v-model.trim="search" type="text" placeholder="Search...">
    </header>
    <div class="options-container">
      <Card v-for="quiz in quizzes" :key="quiz.id" :quiz="quiz"/>
    </div>
  </div>
</template>

<style scoped>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}



header{
  margin-bottom: 10px;
  margin-top: 30px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  gap: 1rem;
}
header h1{
  font-weight: bold;
  margin-right: 30px;
}
input{
  border: none;
  background-color: rgba(255, 255, 255, 0.1);
  padding: 10px;
  border-radius: 5px;
  color:aliceblue;
}
input:focus{
    outline: none;
}

.options-container  {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  margin-top: 40px;
}


</style>