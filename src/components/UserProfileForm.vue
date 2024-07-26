<script setup>
import { ref, defineEmits } from 'vue';

const emit = defineEmits(['submit']);

const nome = ref('');
const email = ref('');
const senha = ref('');
const confirmaSenha = ref('');
const dataNasc = ref('');
const endereco = ref('');
const cidade = ref('');
const estado = ref('');
const hobbies = ref('');
const linguagens = ref('');
const biografia = ref('');

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

function handleSubmit() {
  if (senha.value !== confirmaSenha.value) {
    alert('As senhas não coincidem.');
    return;
  }

  const userData = {
    nome: nome.value,
    email: email.value,
    senha: senha.value,
    dataNasc: dataNasc.value,
    endereco: endereco.value,
    cidade: cidade.value,
    estado: estado.value,
    hobbies: hobbies.value,
    linguagens: linguagens.value,
    biografia: biografia.value,
  };

  emit('submit', userData);
}
</script>

<template>
  <div class="form-container">
    <form @submit.prevent="handleSubmit">
      <div class="form-group">
        <label for="nome">Nome</label>
        <input type="text" id="nome" v-model="nome" placeholder="Insira seu nome" required />
      </div>
      
      <div class="form-group">
        <label for="email">E-mail</label>
        <input type="email" id="email" v-model="email" placeholder="Insira seu e-mail" required />
      </div>

      <div class="form-group">
        <label for="senha">Senha</label>
        <input type="password" id="senha" v-model="senha" placeholder="Insira sua senha" required />
      </div>

      <div class="form-group">
        <label for="confirmaSenha">Confirmação de Senha</label>
        <input type="password" id="confirmaSenha" v-model="confirmaSenha" placeholder="Confirme sua senha" required />
      </div>

      <div class="form-group">
        <label for="dataNasc">Data de Nascimento</label>
        <input type="date" id="dataNasc" v-model="dataNasc" required />
      </div>

      <div class="form-group">
        <label for="endereco">Endereço</label>
        <input type="text" id="endereco" v-model="endereco" placeholder="Insira seu endereço" required />
      </div>

      <div class="form-group">
        <label for="cidade">Cidade</label>
        <input type="text" id="cidade" v-model="cidade" placeholder="Insira sua cidade" required />
      </div>

      <div class="form-group">
        <label for="estado">Estado</label>
        <select id="estado" v-model="estado" required>
          <option disabled value="">Selecione um estado</option>
          <option v-for="uf in estados" :key="uf.code" :value="uf.code">
            {{ uf.name }}
          </option>
        </select>
      </div>

      <div class="form-group">
        <label for="hobbies">Hobbies</label>
        <input type="text" id="hobbies" v-model="hobbies" placeholder="Insira seus hobbies" />
      </div>

      <div class="form-group">
        <label for="linguagens">Linguagens de Programação</label>
        <input type="text" id="linguagens" v-model="linguagens" placeholder="Insira suas linguagens de programação" />
      </div>

      <div class="form-group">
        <label for="biografia">Biografia</label>
        <textarea id="biografia" v-model="biografia" placeholder="Escreva sua biografia"></textarea>
      </div>

      <button type="submit">Salvar</button>
    </form>
  </div>
</template>

<style scoped>
/* Adicione os estilos CSS para o formulário aqui */
.form-container {
  padding: 20px;
}
.form-group {
  margin-bottom: 15px;
}
</style>