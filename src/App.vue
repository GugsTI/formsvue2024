<script setup>
import { ref } from 'vue';
import UserProfileForm from './components/UserProfileForm.vue';
import UserProfileDisplay from './components/UserProfileDisplay.vue';

const currentView = ref('form');
const userData = ref({});

function handleFormSubmit(data) {
  userData.value = data;
  currentView.value = 'display';
}
</script>

<template>
  <div id="app">
    <button @click="currentView = 'form'">Exibir Formulário</button>
    <button @click="currentView = 'display'">Exibir Informações</button>

    <UserProfileForm v-if="currentView === 'form'" @submit="handleFormSubmit" />
    <UserProfileDisplay v-if="currentView === 'display'" :userData="userData" />
  </div>
</template>

<style>
/* Adicione os estilos CSS para o componente principal aqui */
</style>