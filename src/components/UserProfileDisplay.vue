<script setup>
import { defineProps } from 'vue';

// eslint-disable-next-line no-unused-vars
const props = defineProps({
  userData: Object,
});

const estados = [
  { code: 'AC', name: 'Acre' },
  { code: 'AL', name: 'Alagoas' },
  { code: 'AP', name: 'Amapá' },
  { code: 'AM', name: 'Amazonas' },
  { code: 'BA', name: 'Bahia' },
  { code: 'CE', name: 'Ceará' },
  { code: 'DF', name: 'Distrito Federal' },
  { code: 'ES', name: 'Espírito Santo' },
  { code: 'GO', name: 'Goiás' },
  { code: 'MA', name: 'Maranhão' },
  { code: 'MT', name: 'Mato Grosso' },
  { code: 'MS', name: 'Mato Grosso do Sul' },
  { code: 'MG', name: 'Minas Gerais' },
  { code: 'PA', name: 'Pará' },
  { code: 'PB', name: 'Paraíba' },
  { code: 'PR', name: 'Paraná' },
  { code: 'PE', name: 'Pernambuco' },
  { code: 'PI', name: 'Piauí' },
  { code: 'RJ', name: 'Rio de Janeiro' },
  { code: 'RN', name: 'Rio Grande do Norte' },
  { code: 'RS', name: 'Rio Grande do Sul' },
  { code: 'RO', name: 'Rondônia' },
  { code: 'RR', name: 'Roraima' },
  { code: 'SC', name: 'Santa Catarina' },
  { code: 'SP', name: 'São Paulo' },
  { code: 'SE', name: 'Sergipe' },
  { code: 'TO', name: 'Tocantins' },
];
</script>

<template>
  <div class="display-container">
    <h2>Informações do Usuário</h2>
    <p><strong>Nome:</strong> {{ userData.nome }}</p>
    <p><strong>E-mail:</strong> {{ userData.email }}</p>
    <p><strong>Data de Nascimento:</strong> {{ userData.dataNasc }}</p>
    <p><strong>Endereço:</strong> {{ userData.endereco }}</p>
    <p><strong>Cidade:</strong> {{ userData.cidade }}</p>
    <p><strong>Estado:</strong> {{ estados.find(estado => estado.code === userData.estado)?.name }}</p>
    <p><strong>Hobbies:</strong> {{ userData.hobbies }}</p>
    <p><strong>Linguagens de Programação:</strong> {{ userData.linguagens }}</p>
    <p><strong>Biografia:</strong> {{ userData.biografia }}</p>
  </div>
</template>

<style scoped>
/* Adicione os estilos CSS para a exibição aqui */
.display-container {
  padding: 20px;
}
</style>