<template>
    <div class="div-principal">
        <div>
            <h2 class="h2">- Start the GAME! -</h2>
        </div>
        <input class="input-form" type="text" v-model="nomeField" id="name" placeholder="Informe seu Name">
        <input class="input-form" type="email" v-model="emailField" id="name" placeholder="Informe seu E-mail">
        
        <button @click="adicionarPessoa" class="btn-style">Add Informação</button>
    </div>
            
</template>

<script>
export default {
    data(){
        return {
            nomeField: "",
            emailField: "",
            add: [ 
                {
                    id: "",
                    nome: "",
                    email: ""
                } 
            ]
        }    
    },

    methods: {
        adicionarPessoa: function() {
        this.add.push({nome: this.nomeField, email:this.emailField, id:Date.now()})
        this.nomeField = "";
        this.emailField = "";
    }
  }
}
</script>

<style scoped>
    .div-principal{
        text-align: center;
        background-color: darkcyan;
        color: white;
        max-width: 950px;
        margin: 0 auto;
        border: 2px solid black ;
    }

    .h2{
        color: black;
        font-family: 'Courier New', Courier, monospace;
        font-size: 20px;
        font-style: oblique;
    }

    .input-form{
        max-width: 250px;
        min-width: 50px;
        text-align: center;
        margin-left: 15px;
        margin-bottom: 15px;
        padding: 5px 5px 5px 5px;
        border: 1px solid black;
    }

    .btn-style{
        text-align: center;
        max-width: 150px;
        margin: 5px 5px 5px;
        padding: 5px 5px 5px 2px;
    }
</style>