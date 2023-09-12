<script setup>
import { ref } from 'vue';

// import { RouterLink } from 'vue-router';
const isPresentationActive = ref(false)
const isCreationsActive = ref(false)
const isContactActive = ref(false)

function activeClass(link) {
    if (link === 'presentation') {
        isPresentationActive.value = true
        isCreationsActive.value = false
        isContactActive.value = false
    } else if (link === 'creations') {
        isPresentationActive.value = false
        isCreationsActive.value = true
        isContactActive.value = false
    } else if (link === 'contact') {
        isPresentationActive.value = false
        isCreationsActive.value = false
        isContactActive.value = true
    } else {
        isPresentationActive.value = false
        isCreationsActive.value = false
        isContactActive.value = false
    }
}

</script>
<template>
    <header class="topbar" id="header">
        <a href="#top" class="topbar-logo" @click="activeClass"><img src="/images/MonProfil_logo.jpg" alt=""
                class="topbar-logo"></a>
        <nav class="topbar-nav">
            <!-- <RouterLink to="/">Accueil</RouterLink> -->
            <a href="#presentation" :class="{ active: isPresentationActive }"
                @click="activeClass('presentation')">Présentation</a>
            <a href="#creations" :class="{ active: isCreationsActive }" @click="activeClass('creations')">Création</a>
            <a href="#contact" :class="{ active: isContactActive }" @click="activeClass('contact')">Contact</a>
        </nav>
        <a href="#top" class="go-top"><img src="/images/chevrons-haut.svg" alt="2 chevrons vers le haut"></a>
    </header>
</template>
<style scoped>
.topbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    color: white;
    background: rgb(94, 148, 202, 0.7);
    margin: 0;
    padding: 10px 20px 10px 10px;
    border-bottom: 2px solid rgb(94, 148, 202, 0.8);
    background: linear-gradient(rgba(76, 135, 106, 0.6), 15%, rgb(94, 148, 202, 0.6));
    z-index: 4;
}

.topbar-logo {
    border-radius: 10px;
    text-decoration: none;
    border: none;
}

.topbar-nav {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 10px;
}

a {
    color: inherit;
}

.topbar-nav a {
    text-decoration: none;
    font-size: 18px;
    color: inherit;
}

.active {
    border-bottom: 2px solid white;
}

.topbar-nav .portfolio-active-link {
    border-bottom: 2px solid white;
}

.go-top {
    position: fixed;
    bottom: 90px;
    right: 30px;
    font-size: 15px;
    color: rgba(0, 0, 0, 0.5);
    text-decoration: none;
    text-align: center;
    border: 1px solid;
    border-radius: 5px;
    padding: 0.2em;
}

</style>