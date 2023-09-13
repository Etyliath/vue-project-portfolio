<script setup>
import CreationContent from '@/components/CreationContent.vue'
import FormContact from './FormContact.vue';
import { ref } from 'vue';
import sourceData from '@/data.json'
const creations = ref(sourceData.creations)
</script>
<template>
    <main class="main" id="main">
        <h2>Edouard DA SILVA</h2>
        <section id="presentation">
            <h2>Presentation</h2>
            <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Officiis nisi eveniet aut quis fuga exercitationem
                asperiores modi, ullam beatae qui sequi ipsum sed voluptate debitis eligendi cum. Quibusdam, temporibus
                cumque?
            </p>
        </section>
        <section id="creations">
            <h2>Créations</h2>
            <div class="creations">
                <CreationContent
                    v-for="creation in creations"
                    :key="creation.id"
                    :creation="creation"
                />
            </div>
        </section>
        <section id="contact">
            <h2>Contact</h2>
            <FormContact />
        </section>
    </main>
</template>
<style>
#main {
    /* margin-top: 95px; */
    flex-grow: 1;
    padding: 0 0.8em 0;
    z-index: 2;
}

.main h2 {
    padding: 0.8em 0;
}

.main img {
    width: 350px;
    height: auto;
}

#presentation {
    padding-bottom: 0.6em;
    border-bottom: 2px solid var(--primary-text-color);
}

.creations {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    align-items: start;
    padding: 0 0.8em 0.6em;
    border-bottom: 2px solid var(--primary-text-color);
}

</style>