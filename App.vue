// Esse projeto é baseado em uma interface de login utilizando 4 campos com input para designar o
nome, email e duas confirmações de senha (ambas precisam ser iguais) após a validação, caso as
senhas sejam idênticas, um alert é retornado exibindo a variavel "nome".

<script>
export default {
  data() {
    return {
      senha: '',
      confirmarSenha: '',
      confirmar: '',
      nome: '',
    }
  },
  computed: {
    senhaValida() {
      return this.senha && this.confirmarSenha && this.senha === this.confirmarSenha
    },
  },
  methods: {
    gerarMensagem() {
      this.confirmar = alert(`Olá ${this.nome}, seu cadastro foi realizado com sucesso!`)
    },
  },
}
</script>

<template>
  <div class="container mt-5" style="max-width: 400px">
    <h3 class="mb-4 text-center">Cadastro</h3>

    <div class="mb-3">
      <label for="formGroupExampleInput" class="form-label">Digite seu nome</label>
      <input
        v-model="nome"
        type="text"
        class="form-control"
        id="formGroupExampleInput"
        placeholder="Digite seu nome"
      />
    </div>

    <div class="mb-3">
      <label for="formGroupExampleInput2" class="form-label">Digite seu E-MAIL</label>
      <input
        type="text"
        class="form-control"
        id="formGroupExampleInput2"
        placeholder="Digite seu E-MAIL"
      />
    </div>

    <div class="mb-3">
      <label for="senha" class="form-label">Senha</label>
      <input
        type="password"
        class="form-control"
        id="senha"
        v-model="senha"
        placeholder="Digite a senha"
      />
    </div>

    <div class="mb-3">
      <label for="confirmarSenha" class="form-label">Confirmar Senha</label>
      <input
        type="password"
        class="form-control"
        id="confirmarSenha"
        v-model="confirmarSenha"
        placeholder="Confirme a senha"
      />
      <div v-if="confirmarSenha && !senhaValida" class="text-danger mt-1">
        As senhas não coincidem.
      </div>
    </div>

    <button @click="gerarMensagem" type="button" class="btn btn-success" :disabled="!senhaValida">
      Confirmar cadastro
    </button>
  </div>
</template>

<style></style>
