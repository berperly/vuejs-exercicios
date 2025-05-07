// Esse código impõe um minimo de 6 caracteres para uma senha


<template>
    <input type="password" v-model="senha" placeholder="Digite sua senha" />
<p v-if="senha.length < 6">Sua senha deve conter no mínimo 6 caracteres</p>
</template>

<script>
export default {
  data() {
    return {
      senha: '',
    }
  }
}
</script>

<style>
input{
  border-radius: 5px;
}
</style>
