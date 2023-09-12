<script setup>
import { ref } from 'vue';

const email =ref('esdasilva@hotmail.fr')
const postContact =ref({
    email: email.value,
    name:'',
    subject:'',
    message:''
})

function onSubmit(e) {
    //définir la methode d'envoi du mail
    e.target.reset()
}

</script>
<template>
    <div class="container">
        <form action="http://192.168.11.45" method="post" class="form" @submit.prevent="onSubmit">
            <label for="name"> Prénom/Nom</label>
            <input type="text" name="name" id="name" v-model="postContact.name">
            <label for="subject">Sujet</label>
            <input type="text" name="subject" id="subject" v-model="postContact.subject">
            <label for="message">Message</label>
            <textarea name="message" id="message" cols="30" rows="10" v-model="postContact.message"></textarea>
            <button type="submit" class="form-btn">Envoyer</button>
        </form>
    </div>
</template>
<style>
.container{
    width: 350px;
}
.form {
    display: flex;
    flex-direction: column;
    padding: 10px;
}
.form-btn{
    margin-top: 10px;
    padding: 0.2em;
}
</style>