<script setup>
    import { defineProps } from "vue";
    const {questionStatus, barPercentage} = defineProps(["questionStatus", "barPercentage"])
</script>

<template>
    <header>
        <h4>Question {{questionStatus}}</h4>
        <div class="bar">
            <div class="completion" :style="{width: barPercentage}" ></div>
        </div>
    </header>
</template>
<style scoped>
    header{
        margin: 1rem auto;
    }
    header h4{
        font-size: 30px;
    }
    .bar{
        margin: 0 auto;
        width: 280px;
        height: 30px;
        /* border: 3px  #ef2e2f; */
        border: 3px solid red;
    }
    .completion{
        height: 100%;
        background-color: #c5c8df;
    }

</style>