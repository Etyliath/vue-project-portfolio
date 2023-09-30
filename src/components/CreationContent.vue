<script setup>
import { ref } from 'vue';
import CreationDetail from '@/components/CreationDetail.vue'

defineProps(['creation'])

const revele = ref(false)

function toggleModale() {
    revele.value = !revele.value
}

</script>
<template>
    <div class="creation-item">
        <h3> {{ creation.title }}</h3>
        <img :src="`/images/${creation.images[0].image}`" :alt="`${creation.images[0].alt}`" @click="toggleModale">
    </div>
    <CreationDetail :revele="revele" :toggleModale="toggleModale" :creation="creation" />
</template>
<style scoped>
.creation-item {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.creation-item h3 {
    padding: 0.8em;
}

.creation-item img {
    width: 350px;
    height: auto;
}
.creation-item:hover{
    box-shadow: 8px 8px 8px var(--primary-text-color);
    cursor: pointer;
}

</style>