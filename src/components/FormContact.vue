<script setup>
import { ref } from 'vue';

//varaibles liées aux entrée du formulaire
const email = ref('esdasilva@hotmail.fr')
const name = ref('')
const subject = ref('')
const message = ref('')

//Object contiens l'ensembe des données validé dans le formulaire
const demandContact = ref({
    email: email.value,
    name: '',
    subject: '',
    message: ''
})
//array contain all demand
const listDemandContact = ref([])

//booléan active la classe pour le message d'erreur
const isActive = ref(false)

/**
 * validation du formulaire de comtact
 * @param {event} e 
 */
function onSubmit(e) {
    e.preventDefault()
    if (name.value === '' || subject.value === '' || message.value === '') {
        isActive.value = true
    } else {
        demandContact.value.name = name.value
        demandContact.value.subject = subject.value
        demandContact.value.message = message.value
        listDemandContact.value.push(demandContact)
        isActive.value = false
        name.value = ''
        subject.value = ''
        message.value = ''
    }
}

</script>
<template>
    <div class="error__message" :class="{ active: isActive }">tous les champs doivent être remplit</div>
    <form class="form" @submit="onSubmit">
        <label for="name"> Prénom/Nom</label>
        <input type="text" name="name" id="name" v-model.trim="name">
        <label for="subject">Sujet</label>
        <input type="text" name="subject" id="subject" v-model.trim="subject">
        <label for="message">Message</label>
        <textarea name="message" id="message" cols="30" rows="10" v-model.trim="message"></textarea>
        <button type="submit" class="form__button">Envoyer</button>
    </form>
</template>
<style scoped>
.error__message {
    display: none;
}

.active {
    display: block;
    text-align: center;
    border: 1px solid red;
    margin: 0 auto;
    padding: 0.6em;
    width: fit-content;
    background: var(--primary-bg-color-tr);
    color: red;
    font-style: italic;
}

.form {
    display: flex;
    flex-direction: column;
    margin: 0 auto;
    align-items: center;
    width: 350px;
    padding: 10px;
}

.form input,
textarea {
    width: 100%;
    border-radius: 5px;
}

.form__button {
    margin-top: 10px;
    padding: 0.4em;
    background: var(--secondary-bg-color);
    border: 1px solid var(--primary-bg-color);
    border-radius: 5px;
    box-shadow: 3px 3px 3px var(--primary-text-color);
}
</style>