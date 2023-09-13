<script setup>
defineProps(['revele', 'toggleModale', 'creation'])
</script>
  
<template>
    <div class="modale" v-if="revele">
        <div class="modale__overlay" @click="toggleModale"></div>
        <div class="modale__bloc">
            <div class="modale__button" @click="toggleModale">X</div>
            <h3 class="modale__title"> {{ creation.title }}</h3>
            <p class="modale__text">Date de creation: <span class="modale__style"> {{ creation.date }} </span> </p>
            <p class="modale__text">Technologie utilisées: <span class="modale__style"> {{ creation.techno }}</span></p>
            <a :href="`${creation.link}`" target="_blank" class="modale__link">Voir la création</a>
            <div class="modale__images">
                <img :src="`/images/${creation.image}`" :alt="`${creation.alt}`">
                <img :src="`/images/${creation.image2}`" :alt="`${creation.alt2}`">
                <img :src="`/images/${creation.image3}`" :alt="`${creation.alt3}`">
            </div>
        </div>
    </div>
</template>
  
<style scoped>
.modale {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    justify-content: center;
    align-items: center;
}

.modale__overlay {
    background: rgba(0, 0, 0, 0.6);
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
}

.modale__bloc {
    background: var(--primary-bg-color);
    color: var(--primary-text-color);
    padding: 1.5em;
    position: fixed;
    top: 15%;
    border-radius: 10px;
}



.modale__title {
    font-size: 1.5em;
    text-align: center;
    padding: 0.5em 0;
}
.modale__title::after {
    content: '';
    display: block;
    height: 1px;
    width: 100px;
    margin: 10px auto 0;
    background: var(--primary-text-color);
}
.modale__text{
font-size: 1.1em;
margin: 10px 0;
}
.modale__style{
    font-style: italic;
}
.modale__link {
    font-size: 1.1em;
    text-decoration: none;
    color: var(--primary-text-color-tr);
}
.modale__link:hover {
    color: var(--primary-text-color);
    border-bottom: 2px solid var(--primary-text-color);
    transition: 0.3s;
}
.modale__link::after {
    content: '';
    display: block;
    height: 1px;
    width: 100px;
    margin: 10px auto;
    background: var(--primary-border-color);
}
.modale__images {
    display: flex;
    align-items: start;
    gap: 10px;
    flex-wrap: wrap;
    padding: 0.6em 0;

}
.modale__button {
    position: absolute;
    top: 10px;
    right: 10px;
    background: var(--secondary-bg-color);
    color: var(--primary-text-color);
    padding: 0.2em 0.4em;
    /* border: 1px solid white; */
    border-radius: 5px;
    cursor: pointer;
}
</style>