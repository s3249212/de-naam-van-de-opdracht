<script setup>
import {ref, reactive} from 'vue';

// Ref voor de score
const clicks = ref(0);

const person = reactive({
    firstName: '[onbekend]',
    country: '[onbekend]',
});

const incrementClicks = () => {
    clicks.value++;
};

// Functie om team te wijzigen
const changeCountry = newCountry => {
    person.country = newCountry;
};
</script>

<template>
    <input v-model="person.firstName" placeholder="Voornaam" />
    Hallo, jouw naam is {{ person.firstName }} en je komt uit {{ person.country }}.

    <button @click="incrementClicks">{{ clicks }} clicks</button>

    <button @click="changeCountry('Nederland')">Nederland</button>
    <button @click="changeCountry('België')">België</button>
</template>
