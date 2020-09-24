<template>
    <div class="div-principal">
        <div :class="{'lista': !iSorteado,'lista-sorteado': iSorteado}">
            <p>Descrição do Cleinte: {{ addLista.nome }}</p>
            <p>E-mail : {{ addLista.email }}</p>
            <button @click="corSorteada" class="btn-style">Mudar Cor</button>
            <button @click="eventoExcluir" class="btn-style">Excluir</button>
        </div>
    </div>
            
</template>

<script>
export default {
    data(){
        return {
            iSorteado: false
        }    
    },
    props:{
        addLista: Object
    },
    methods:{
        corSorteada: function(){
            this.iSorteado = !this.iSorteado;
        },
        eventoExcluir: function(){
          this.$emit("meDelete", {idPessoa: this.addLista.id, components: this});
        }
    } 
}
</script>

<style scoped>
    .div-principal{
        text-align: center;
        background-color: white;
        color: white;
        max-width: 950px;
        margin: 1%;
        margin-top: 1%;
        padding: 1%;
    }

    .lista{
        background-color: gray;
        color: white;
        margin: 15px;
        padding: 1%;
    }

    .lista-sorteado{
        background-color: black;
        color: yellow;
        margin: 15px;
        padding: 1%;
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
    }

    .btn-style{
        text-align: center;
        max-width: 150px;
        margin: 5px 5px 5px;
        padding: 5px 5px 5px 2px;
    }
    .hr{
        max-width: 95%;
    }

    hr{
        max-width: 50%;
    }

</style>