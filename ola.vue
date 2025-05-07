// Esse código retorna o nome escrito no input com uma mensagem "Olá (nome), seja bem vindo!"


<template>
    <input type="text" v-model="nome" placeholder="Digite seu nome" />
    <p v-if="nome">Bem-vindo, {{ nome }}!</p>
</template>

<script>
export default {
  data() {
    return {
      nome: ''
    }
  }
}
</script>

<style>
input{
  border-radius: 5px;
}
</style>
