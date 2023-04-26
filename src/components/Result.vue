<script setup>
    import { defineProps } from "vue";
    import { RouterLink } from "vue-router";
    const {numberOfCorrectAnswers, quizQuestionLength} = defineProps(["numberOfCorrectAnswers","quizQuestionLength", ])

</script>

<template>
    <div class="results">
        <p>Your Results...</p>
        <h1>
            {{numberOfCorrectAnswers}}/{{ quizQuestionLength }}
        </h1>
        <RouterLink to="/">Go Back</RouterLink>
    </div>
</template>

<style scoped>
    .results{
        text-align: center;
        padding:100px 0;
    }
    p{
        font-size:1.5rem;

    }
    h1{
        font-size: 4rem;
        margin-bottom: 2rem;
    }
    a{
        padding: 1rem 2em;
        background-color: #c5c8df;
        color: #233067;
        text-decoration: none;
        transition: .3s all;
    }
    a:hover{
        transform: scale(10px, 10px);
        background-color: transparent;
        color: #c5c8df;
        border: 1px solid #c5c8df;
    }
</style>