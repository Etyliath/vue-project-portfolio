<script setup>
import CreationContent from '@/components/CreationContent.vue'
import FormContact from '@/components/FormContact.vue';
import { ref } from 'vue';
import sourceData from '@/data.json'

/**
 * sources dess données pour afficher la modale
 */
const creations = ref(sourceData.creations)

</script>
<template>
    <main class="main">
        <div class="main__banner">
            <h2>Portfolio Edouard DA SILVA</h2>
        </div>
        <section id="presentation" class="main__presentation">
            <h2>Presentation</h2>
            <p>
                Bonjour, je m’appelle Edouard et je suis un web développeur junior passionné par la création de sites web
                dynamiques et interactifs. J’ai appris les langages et des frameworks les plus utilisés dans le domaine du
                web, tels que HTML, CSS, JavaScript, Vue.js. Je maîtrise également les outils de développement collaboratif,
                comme Git, GitHub et Visual Studio Code.
            </p>
            <p>
                J’ai réalisé plusieurs projets personnels qui démontrent mes compétences et ma créativité. Par exemple, j’ai
                créé un site web de mon CV et un cahier charges pour la refonte d'un site web et j'ai dynamiser un site communautaire en javascript.
            </p>
            <p> Je suis toujours à la recherche de nouveaux défis et de nouvelles opportunités d’apprentissage. Je suis
                motivé, curieux et autonome. Je sais m’adapter aux besoins des clients et travailler en équipe. Je suis
                disponible pour travailler à temps plein ou à temps partiel, en présentiel ou à distance.
            </p>

        </section>
        <section id="creations" class="main__creations">
            <h2>Mes créations</h2>
            <p>Vous trouverez ci-dessous certaines de mes creations vous pouvez cliquez sur l'image pour la consulter</p>
            <div class="creations__items">
                <CreationContent v-for="creation in creations" :key="creation.id" :creation="creation" />
            </div>
            <div class="creations__line-end"></div>
        </section>
        <section id="contact" class="contact">
            <h2>Me Contacter</h2>
            <p>
                Si vous êtes intéressé par mon profil, n’hésitez pas à me contacter par e-mail via le formulaire ci-dessous.
                <br>
                Vous pouvez également consulter mon CV en ligne.
            </p>
            <FormContact />
        </section>
    </main>
</template>
<style scoped>
.main {
    margin-top: 95px;
    flex-grow: 1;
    z-index: 2;
    background: var(--primary-bg-color);
}

.main h2 {
    padding: 0.8em 0;
}

.main p {
    line-height: 1.5em;
}

.main__banner {

    background-image: linear-gradient(to bottom,
            var(--primary-bg-color-tr),
            var(--secondary-bg-color-tr)), url("/images/image-code-web.jpg");
    height: 200px;
    padding: 0 0.8em 0;
}

.main__presentation {
    scroll-margin-top: 95px;
    padding: 0 0.8em 0.6em;
}

.main__presentation p {
    padding: 0.2em 0;
}

.main__creations {
    scroll-margin-top: 105px;
    padding: 0 0.8em 0.6em;
}

.main__presentation::after {
    content: '';
    display: block;
    height: 2px;
    width: 200px;
    margin: 10px auto;
    background: var(--secondary-bg-color);
}

.creations__line-end {
    content: '';
    display: block;
    height: 2px;
    width: 200px;
    margin: 10px auto;
    background: var(--secondary-bg-color);
}

.creations__items {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    align-items: start;
    padding: 0 0.8em 0.6em;
    gap: 0.8em;
}

.contact {
    padding: 0 0.8em 0.6em;
}
</style>