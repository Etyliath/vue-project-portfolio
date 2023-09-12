<script setup>
defineProps(['revele', 'toggleModale', 'creation'])
</script>
  
<template>
    <div class="bloc-modale" v-if="revele">
        <div class="overlay" @click="toggleModale"></div>
        <div class="modale">
            <div class="btn-modale" @click="toggleModale">X</div>
            <h3> {{ creation.title }}</h3>
            <p>date de creation: {{ creation.date }}</p>
            <p>technologie utilisées: {{ creation.techno }}</p>
            <a :href="`${creation.link}`" target="_blank">lien vers la création</a>
            <div class="modale-images">
                <img :src="`/images/${creation.image}`" alt="image d'une page web">
                <img :src="`/images/${creation.image2}`" alt="image d'une page web">
                <img :src="`/images/${creation.image3}`" alt="image d'une page web">
            </div>
        </div>
    </div>
</template>
  
<style scoped>
.bloc-modale {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    justify-content: center;
    align-items: center;
}

.overlay {
    background: rgba(0, 0, 0, 0.5);
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
}

.modale {
    background: #f1f1f1;
    color: #333;
    padding: 1.5em;
    position: fixed;
    top: 20%;
    border-radius: 10px;
}

.modale-images {
    display: flex;
    align-items: start;
    gap: 10px;
    padding: 0.6em 0;

}

.modale h3 {
    font-size: 1.9em;
    text-align: center;
}

.modale P {
    padding: 0.5em 0;

}

.modale a {
    text-decoration: none;
    color: #333;
}

.btn-modale {
    position: absolute;
    top: 10px;
    right: 10px;
    background: red;
    color: white;
    padding: 0.2em 0.4em;
    border: 1px solid white;
    border-radius: 5px;
    cursor: pointer;
}
</style>