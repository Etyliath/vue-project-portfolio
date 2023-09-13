<script setup>
import { RouterLink } from 'vue-router'
</script>
<template>
    <div class="container">
        <h1>Not found</h1>
        <img src="/images/erreur-404.png" alt="">
        <p>Oops, this page didn't exists</p>
        <div class="back-home">
            <RouterLink to="/">Accueil</RouterLink>
        </div>
    </div>
</template>
<style scoped>
.container {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.back-home {
    padding: 5px 20px;
    border: 1px solid;
    border-radius: 5px;
    background: var(--primary-bg-color);
}

.back-home a {
    text-decoration: none;
}
</style>