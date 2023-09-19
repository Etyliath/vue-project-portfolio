<script setup>
import { ref } from 'vue';

const email = ref('esdasilva@hotmail.fr')
const postContact = ref({
    email: email.value,
    name: '',
    subject: '',
    message: ''
})

function onSubmit(e) {
    //définir la methode d'envoi du mail
    e.target.reset()
}

</script>
<template>
    <form action="http://192.168.11.45" method="post" class="form" @submit.prevent="onSubmit">
        <label for="name"> Prénom/Nom</label>
        <input type="text" name="name" id="name" v-model="postContact.name">
        <label for="subject">Sujet</label>
        <input type="text" name="subject" id="subject" v-model="postContact.subject">
        <label for="message">Message</label>
        <textarea name="message" id="message" cols="30" rows="10" v-model="postContact.message"></textarea>
        <button type="submit" class="form__button">Envoyer</button>
    </form>
</template>
<style scoped>
.form {
    display: flex;
    flex-direction: column;
    width: 350px;
    padding: 10px;
}
.form input,textarea{
    border-radius: 5px;
}
.form__button {
    margin-top: 10px;
    padding: 0.2em;
    background: var(--secondary-bg-color);
    border: 1px solid var(--primary-bg-color);
    border-radius: 5px;
}
</style>