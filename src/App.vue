<template>
  <div class="principal">
    <div id="app">
      <img class="img-responsive img-logo" src="@/assets/photo.png" alt="Logo">
      <h1>SORTEIO do BRONX</h1>
      <div class="div-principal">
        <h2 class="h2">- Start the GAME! -</h2>
        <input type="text" v-model="addTeste.nome">
        <input type="text" v-model="addTeste.email">
        <hr class="hr">
        
        <AddPessoa :addLista="addTeste"/>
        <AddPessoa :addLista="addTeste"/>
      </div>



      <!--div v-for="(AddPessoa,index) in add" :key="AddPessoa.id">
        <h6>{{index + 1 }}
        <AddPessoa :add="add"/>
      </div-->
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
      nomeWN: "WN SANTOS",
      emailWN: "juca@gmail.com",
      addTeste: {
        nome: "Teste",
        email: "teste@gmail"
      }
    }    
  },
  components: {
    AddPessoa,
  },
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
