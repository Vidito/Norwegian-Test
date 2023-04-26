<script setup>
import {defineProps, defineEmits} from 'vue'
import { RouterLink } from "vue-router";


const emit= defineEmits(['selectOption'])
const {question} = defineProps(['question'])
const emitSelectedOption = (isCorrect)=>{
    emit("selectOption", isCorrect)
}

</script>

<template>
    <div class="question-container">
        <h1 class="question">
           {{ question.text }}
        </h1>
        <div class="options-container">
            <div 
            v-for="option in question.options" 
            :key="option.id" 
            class="option" 
            @click="emitSelectedOption(option.isCorrect)"
            >
                <p class="option-label">{{ option.label }}</p>
                <div class="option-value">
                    <p>{{option.text}}</p>
                </div>
            </div>
            <RouterLink to="/">Home</RouterLink>
        </div>
    </div>
</template>
<style scoped>
.question-container{
        margin-top: 20px;
    }

    .question{
        font-size: 1.5rem;
        margin-bottom: 20px;
    }
    .option{
        display: flex;
        margin-bottom: 20px;
        cursor: pointer;
    }
    .option-label{
        background-color: #ef2e2f;
        width: 50px;
        height: 50px;
        font-size: 30px;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .option-value{
        background-color: #c5c8df;
        width: 100%;
        font-size: 30px;
        padding: 0 20px;  
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