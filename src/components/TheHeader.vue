<script setup>
import { RouterLink } from 'vue-router';
</script>
<template>
    <div class="header">
        <h1>Portfolio</h1>
        <nav class="nav">
            <a href="#"><img src="../assets/images/MonProfil_mini.jpg" alt="photo de edouard"></a>
            <RouterLink to="/">Accueil</RouterLink>
            <a href="#presentation">Présentation</a>
            <a href="#creations">Création</a>
            <a href="#contact">Contact</a>
        </nav>
    </div>
</template>
<style>
.header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    display: flex;
    justify-content: end;
    align-items: center;
    background: rgb(94, 148, 202, 0.7);
    margin: 0;
    border-bottom: 2px solid rgb(94, 148, 202, 0.8);
    background: linear-gradient(rgba(76, 135, 106, 0.6), 15%, rgb(94, 148, 202, 0.6));

}

.header h1 {
    flex-grow: 1;
    padding: 0.5rem 0.8rem;
    font-style: italic;
    color: white;
    font-size: 2.5rem;
}

.nav {
    display: flex;
    align-items: center;
    margin-right: 20px;
}

.nav a {
    text-decoration: none;
    color: white;
    padding: 0.6rem 0.8rem;
    font-size: 18px;
}
.nav .portfolio-active-link{
    border-bottom: 2px solid white;
}

img {
    width: 60px;
    height: auto;
    border-radius: 10px;
    border: none;
}</style>