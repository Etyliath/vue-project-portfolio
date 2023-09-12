<script setup>
import { ref } from 'vue';
import CreationDetail from '@/components/CreationDetail.vue'

defineProps(['creation'])

const revele=ref(false)

function toggleModale() {
    revele.value = !revele.value
}

</script>
<template>
    <div class="creation-item">
        <h3> {{ creation.title }}</h3>
        <img :src="`/images/${creation.image}`" alt="image d'une page web" @click="toggleModale">
    </div>
    <CreationDetail :revele="revele" :toggleModale="toggleModale" :creation="creation"/>
</template>
<style>

.creation-item {
    display: flex;
    flex-direction: column;
    align-items: center;
}
.creation-item h3{
    padding: 0.8em;
}
</style>