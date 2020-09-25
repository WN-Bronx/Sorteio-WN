<template>
    <div class="modal" :class="{ 'is-active': show }">
        <div class="modal-background"></div>
        <div class="modal-card">
            <header class="modal-card-head">
                    <p class="modal-card-title">Cadastro de Pessoa</p>
                    <button class="delete" aria-label="close" @click="$emit('close')"></button>
            </header>
            <form @submit.prevent="salvar" v-if="pessoaEditar">
                    <section class="modal-card-body">
                        <div class="field">
                            <label class="label">Nome:</label>
                            <input type="text" v-model="pessoaEditar.nome" class="input" required autofocus/>
                        </div>
                        <div class="field">
                            <label class="label">E-mail:</label>
                            <input type="text" v-model="pessoaEditar.email" class="input" required autofocus/>
                        </div>
                    </section>
                    <footer class="modal-card-foot">
                        <input type="submit" class="button is-success" value="Salvar"/>
                        <button class="button" @click="$emit('close')">Cancelar</button>
                    </footer>
            </form>
        </div>     
    </div>
</template>

<script>
//import Multiselect from 'vue-multiselect'

export default {
  components: {
     //Multiselect
  },     
    props: {
        show: Boolean,
        pessoa: Object,                              
    },  
    data() {
        return {
            pessoaEditar: null,
        }
    },
    methods: {
        salvar() {
            this.$emit('save', this.pessoaEditar)
        }
    },
    watch: {
        pessoa: function(val) {
            this.pessoaEditar = val
        } 
    }
}
</script>

<style src="vue-multiselect/dist/vue-multiselect.min.css"></style>

<style>

</style>
