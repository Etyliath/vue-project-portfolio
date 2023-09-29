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
const toastMessage=ref('')
const toastStyle=ref({})

/**
 * validation du formulaire de comtact
 * @param {event} e 
 */
function onSubmit(e) {
    e.preventDefault()
    if (name.value === '' || subject.value === '' || message.value === '') {
        isActive.value = true
        toastStyle.value={
            border: '1px solid red',
            color: 'red'
        }
        toastMessage.value='tous les champs doivent être remplit'
        setTimeout(()=>isActive.value = false,3000)
    } else {
        demandContact.value.name = name.value
        demandContact.value.subject = subject.value
        demandContact.value.message = message.value
        listDemandContact.value.push(demandContact)
        name.value = ''
        subject.value = ''
        message.value = ''
        isActive.value = true
        toastStyle.value={
            border: '1px solid green',
            color: 'green'
        }
        toastMessage.value='Message envoyé'
        setTimeout(()=>isActive.value = false,3000)
    }
}

</script>
<template>
    <div class="toast__message" :class="{ active: isActive }" :style="toastStyle" > {{ toastMessage }} </div>
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
.toast__message {
    display: none;
}

.active {
    display: block;
    text-align: center;
    margin: 0 auto;
    padding: 0.6em;
    width: fit-content;
    background: white;
    font-style: italic;
    box-shadow: 8px 8px 8px var(--primary-text-color);
    border-radius: 10px;
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