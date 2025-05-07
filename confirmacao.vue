<template>
  <div>
    <input type="email" v-model="mail" placeholder="Digite seu email" />
    <br />
    <input type="password" v-model="senha" placeholder="Digite sua senha" />
    <br />
    <button @click="enviarMensagem" :disabled="!dadosValidos">Realizar cadastro</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mail: '',
      senha: '',
    }
  },
  computed: {
    dadosValidos() {
      return this.mail && this.senha
    }
  },
  methods:{
     enviarMensagem() {
    alert("Seu cadastro foi realizado com sucesso!");
    },
    },
}
</script>

<style>
input, button {
  border-radius: 5px;
  background-color: white;
}
</style>
