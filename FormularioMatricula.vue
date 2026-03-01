<template>

  <form @submit.prevent="enviarFormulario"> 
    <input v-model="nome" placeholder="Nome Completo"/>
    <span v-if="erroNome">{{ erroNome }}</span>

    <input v-model="email" placeholder="E-mail"/>
    <span v-if="erroEmail">{{ erroEmail }}</span>

  <select v-model="curso">
    <option disabled value="">Selecione um curso</option>
    <option v-for="c in cursos" :key="c.id" :value="c.nome">{{c.nome}}</option> 
  </select>
  <span v-if="erroCurso">{{ erroCurso }}</span>

  <button  :disabled="!formValido">Matricular</button>

  <p v-if="mensagemSucesso">{{ mensagemSucesso }}</p>

  </form>
</template>  

<script>
export default {
  data() {
    return {
      nome: '',
      email: '',
      curso: '',
      cursos: [],
      mensagemSucesso: '',
    }
  },
  mounted() {
    this.cursos = [
    { id: 1, nome: "Análise e Desenvolvimento de Sistemas" },
    { id: 2, nome: "Ciência da Computação" },
    { id: 3, nome: "Engenharia da Computação" }
  ];
},
  computed:{
    erroNome(){
      return this.nome ? '' : 'Nome é obrigatório!';
    },
    erroEmail(){
      if (!this.email) return 'E-mail é obrigatório!';
      return /\S+@\S+\.\S+/.test (this.email) ? '' : 'Formato de e-mail inválido.';
    }, 
     erroCurso(){
      return this.curso ? '' : 'Selecione um curso.';
    },
    formValido() {
      return !this.erroNome && !this.erroEmail && !this.erroCurso;
      //o ! significa que só será verdadeiro se não existir erro. String vazia ('') = falso, "algum texto" = verdadeiro
    },
    formValido(){
      return !this.erroNome && !this.erroEmail && !this.erroCurso;
    }
  },
  methods: {
    enviarFormulario(){
    if (!this.formValido) return;

    this.mensagemSucesso = `Matrícula de ${this.nome} para o curso ${this.curso} criada com sucesso!`;

    this.nome = '';
    this.email = '';
    this.curso = '';
  }
}
}
  
</script>

<style scoped>
/* scoped significa que vai funcionar só nesse componente */
input, select, button {
  display: block; /*ajuda a alinhar */
  margin-bottom: 10px;
}

span {
  color: red;
  font-size: 12px;
}

button:disabled {
  background-color: gray;
  cursor: not-allowed;
}
</style>
