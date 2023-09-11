<script setup>
defineProps(['title','image'])
</script>
<template>
    <div class="creation-item">
        <h3> {{ title }}</h3>
        <a href="#"><img :src="`/images/${image}`" alt="image d'une page web"></a>
    </div>
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