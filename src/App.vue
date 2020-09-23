<template>
  <div class="principal">
    <div id="app">
      <img class="img-responsive img-logo" src="@/assets/photo.png" alt="Logo">
      <h1>SORTEIO do BRONX</h1>
      <div class="div-principal">
        <h2 class="h2">- Start the GAME! -</h2>
        <input type="text" placeholder="Nome" v-model="nomeField">
        <input type="email" placeholder="E-mail" v-model="emailField">
        <button @click="adicionarPessoa" class="btn-style">Add Informação</button>
        <hr class="hr">
        <!-- Adicionando Pessoa a Lista-->
        <div v-for="(lista,index) in lista" :key="lista.id">
          <h4>{{ index + 1 }}</h4>
          <AddPessoa :addLista="lista"/>
        </div>

      </div>
    </div>
   <div>
   </div>
  </div>  
</template>

<script>

import AddPessoa from './components/AddPessoa'

export default {
  name: 'App',
  data(){
    return {
      nomeField: "",
      emailField: "",
      lista: [ {
        id: "1",
        nome: "WN Silva",
        email: "wn.silva@gmail.com"
        },{
        id: "2",
        nome: "WN Santos",
        email: "wn.santos@gmail.com"
        },
      ]
    }    
  },
  components: {
    AddPessoa,
  },
  
  methods: {
    adicionarPessoa: function() {
    this.lista.push({nome: this.nomeField, email:this.emailField, id:Date.now()})
    this.nomeField = "";
    this.emailField = "";
    }
  }  
}
</script>

<style>
  .div-principal{
    text-align: center;
    background-color: darkcyan;
    color: black;
    max-width: 950px;
    margin: 0 auto;
    margin-top: 1%;
    border: 2px solid black ;
  }

  .h2{
    color: black;
    font-family: 'Courier New', Courier, monospace;
    font-size: 20px;
    font-style: oblique;
  }
  
  .hr{
    max-width: 95%;
  }

  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  .img-logo{
    max-width: 120px;
    margin: 0 auto;
  }
</style>
