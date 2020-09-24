<template>
  <div class="principal">
    <div id="app">
      <img class="img-responsive img-logo" src="@/assets/photo.png" alt="Logo">
      <h1>SORTEIO do BRONX</h1>
      <div class="div-principal">
        <h2 class="h2">- Start the GAME! -</h2>
        <input type="text" placeholder="Nome" required="required" v-model="nomeField" autofocus>
        <small id="error" v-show="deuErro">Informação inválida !</small>
        <input type="email" placeholder="E-mail" required="required" v-model="emailField">
        <button @click="adicionarPessoa" class="btn-style">Add Informação</button>
        <hr class="hr">
        <h2 class="h2">- Click aqui para Ordernar! -</h2>
        <button @click="orderLista" class="btn-style">- ↑ ↓ -</button>
        <hr class="hr">
        <!-- Adicionando Pessoa a Lista-->
        <div v-for="(lista,index) in lista" :key="lista.id">
          <h4>{{ index + 1 }}</h4>
          <AddPessoa :addLista="lista" @meDelete="deletarPessoaLista($event)" />
        </div>

      </div>
    </div>
   <div>
   </div>
  </div>  
</template>

<script>

import _ from 'lodash';
import AddPessoa from './components/AddPessoa';

export default {
  name: 'App',
  data(){
    return {
      deuErro: false,
      nomeField: "",
      emailField: "",
      lista: [ {
        id: "1",
        nome: "WN SANTOS",
        email: "teste@teste.com" 
        }
      ]
    }    
  },
  components: {
    AddPessoa,
  },
  
  methods: {
    adicionarPessoa: function() {
      if (this.nomeField == "" || this.nomeField.length < 1) {
          this.deuErro = true;
      } else {
        this.lista.push({nome: this.nomeField, email:this.emailField, id:Date.now()})
        this.nomeField = "";
        this.emailField = "";
        this.deuErro = false;
      } 
    },
    deletarPessoaLista: function($event) {
      var id = $event.idPessoa;
      var novoArray = this.lista.filter(lista=> lista.id != id);
      this.lista = novoArray;
    }
  },
  computed:{
    orderLista: function(){
      return _.orderBy(this.lista,['nome'], ['asc']);
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

  #error {
    color: red;
  }
  .img-logo{
    max-width: 120px;
    margin: 0 auto;
  }
</style>
