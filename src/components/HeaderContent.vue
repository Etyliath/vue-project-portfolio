<script setup>
import { ref } from 'vue';

const isPresentationActive = ref(false)
const isCreationsActive = ref(false)
const isContactActive = ref(false)
/**
 * valide la class active sur le lien d'ancrage choisi
 * @param {String} link 
 */
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
        <a href="#top" class="topbar__logo" @click="activeClass"><img src="/images/MonProfil_logo.jpg" alt=""
                class="topbar__logo"></a>
        <nav class="topbar__nav">
            <a href="#presentation" :class="{ active: isPresentationActive }"
                @click="activeClass('presentation')">Présentation</a>
            <a href="#creations" :class="{ active: isCreationsActive }" @click="activeClass('creations')">Création</a>
            <a href="#contact" :class="{ active: isContactActive }" @click="activeClass('contact')">Contact</a>
        </nav>
    </header>
</template>
<style scoped>
.topbar {
    position: fixed;
    max-width: 1280px;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    color: var(--primary-text-color);
    margin: 0;
    padding: 10px 20px 10px 10px;
    border-bottom: 2px solid var(--secondary-bg-color);
    background: linear-gradient(var(--secondary-bg-color), 40%, var(--primary-bg-color));
    z-index: 4;
}

.topbar__logo {
    border-radius: 10px;
    text-decoration: none;
    border: none;
}

.topbar__nav {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 10px;
}

a {
    color: inherit;
}

.topbar__nav a {
    text-decoration: none;
    font-size: 18px;
    color: inherit;
}
.topbar__nav a:hover{
    font-weight: bold;
}
.active {
    font-weight: bold;
    border-bottom: 2px solid var(--primary-text-color);
}

.topbar__nav .portfolio-active-link {
    font-weight: bold;
    border-bottom: 2px solid var(--primary-text-color);
}


</style>