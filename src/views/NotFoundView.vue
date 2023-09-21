<script setup>
import { RouterLink } from 'vue-router'

</script>
<template>
    <div class="container">
        <h2>Not found</h2>
        <img src="/images/erreur-404.png" alt="">
        <p>Oops, this page didn't exists
        </p>
        <div class="back-homepage">
            <RouterLink to="/">Retour à l'accueil</RouterLink>
        </div>
    </div>
</template>
<style scoped>
.container {
    width: 1280px;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
    justify-content: stretch;
    justify-content: center;
    align-items: center;
    background-image: linear-gradient(to bottom,
            var(--primary-bg-color-tr),
            var(--secondary-bg-color-tr)), url("/images/image-code-web.jpg");

}
.back-homepage {
    margin-top: 10px;
    padding: 5px 20px;
    border: 1px solid var(--secondary-bg-color);
    ;
    border-radius: 5px;
    color: var(--primary-text-color);
    background: var(--primary-bg-color);
}

.back-homepage a {
    text-decoration: none;
    color: var(--primary-text-color);
}
</style>