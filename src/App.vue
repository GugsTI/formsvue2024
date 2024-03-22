<script setup>
import { ref } from 'vue';
const nome = ref('');
const idade = ref('');






const dados = function(){
  alert( `Seu Nome: ${nome.value}`)
   alert( `Sua idade: ${idade.value}`)
}



</script>
<template>
  <p>Nome:</p><input class="inp" v-model="nome" />
  <p>idade:</p><input class="inp" type="number" v-model="idade">

  <button @click="dados" >Resultado</button>
  

  
</template>

<style>
.inp {
  border-radius: 5px;
  color: white;
  background-color: blue;
}
</style>