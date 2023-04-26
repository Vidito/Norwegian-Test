<script setup>
    // const props = defineProps(['quiz'])
    import { useRouter } from "vue-router";
    const router = useRouter()

    const {quiz} = defineProps(['quiz'])
    const navigateToQuiz = () => {
      router.push(`/quiz/${quiz.id}`)
    }

</script>

<template>
    <div class="card" @click="navigateToQuiz">
        <img :src="quiz.img" alt="">
        <div class="card-text">
            <h2>{{quiz.name}}</h2>
            <p>{{ quiz.questions.length }} Questions</p>
        </div>
    </div>

</template>

<style scoped>
.card{
  width:300px;
  overflow: hidden;
  background-color: #233067;
  border: 1px solid #233067;
  border-radius: 5px;
  margin-bottom: 35px;
  margin-right: 20px;
  cursor: pointer;
  transition: .3s all;
  
}
.card:hover{
  transform: translateY(-4px);
  box-shadow: 1px 1px 10px rgba(233, 227, 227, 0.1) ;

}
.card img{
  width:100%;
  height: 190px;
  border: 3px solid #fefefe;
}

.card .card-text{
  padding:5px;
}

.card-text h2{
  font-weight: bold;
}
h2, p{
  color: #fefefe;
}

</style>