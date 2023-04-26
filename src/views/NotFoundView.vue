<script setup>

import { RouterLink } from "vue-router";
</script>

<template>
    <h1>404: Page Not found</h1>
    <RouterLink to="/">Go Back</RouterLink>
</template>
<style scoped>
h1{
    margin: 3rem auto;
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