<template>
  <div class="principal">
    <div id="app">
      <img class="img-responsive img-logo" src="@/assets/photo.png" alt="Logo">
      <h1>SORTEIO do BRONX</h1>
      <!-- div v-for="(AddPessoa,index) in add" key="add.id">
        <h6>{{index + 1 }}
        <AddPessoa :add="add"/>
      </div-->
      <AddPessoa/>
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

    }
  },
  components: {
    AddPessoa,
  },
}
</script>

<style>

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
    color: #2c3e55;
  }
</style>
